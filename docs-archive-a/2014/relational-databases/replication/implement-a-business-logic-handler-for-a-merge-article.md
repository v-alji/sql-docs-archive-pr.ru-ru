---
title: Реализация обработчика бизнес-логики для статьи публикации слиянием | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- merge replication conflict resolution [SQL Server replication], business logic handlers
- merge replication business logic handlers [SQL Server replication]
- conflict resolution [SQL Server replication], merge replication
- business logic handlers [SQL Server replication]
- BusinessLogicModule class
ms.assetid: ed477595-6d46-4fa2-b0d3-a5358903ec05
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c2996a8ca8471ef59d4781e21239a72262daa759
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655599"
---
# <a name="implement-a-business-logic-handler-for-a-merge-article"></a><span data-ttu-id="d34b3-102">Реализация обработчика бизнес-логики для статьи публикации слиянием</span><span class="sxs-lookup"><span data-stu-id="d34b3-102">Implement a Business Logic Handler for a Merge Article</span></span>
  <span data-ttu-id="d34b3-103">В данном разделе описывается процесс реализации обработчика бизнес-логики для статьи публикации слиянием в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью программирования репликации или объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="d34b3-103">This topic describes how to implement a business logic handler for a merge article in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using replication programming or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="d34b3-104">Пространство имен <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport> реализует интерфейс, позволяющий создавать сложную бизнес-логику для обработки событий, возникающих в процессе синхронизации слиянием.</span><span class="sxs-lookup"><span data-stu-id="d34b3-104">The <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport> namespace implements an interface that enables you to write complex business logic to handle events that occur during the merge replication synchronization process.</span></span> <span data-ttu-id="d34b3-105">Методы в обработчике бизнес-логики могут вызываться процессом репликации для каждой изменившейся строки, которая проходит репликацию в ходе синхронизации.</span><span class="sxs-lookup"><span data-stu-id="d34b3-105">Methods in the business logic handler can be invoked by the replication process for each changed row that is replicated during synchronization.</span></span>  
  
 <span data-ttu-id="d34b3-106">Общий порядок действий по реализации обработчика бизнес-логики следующий.</span><span class="sxs-lookup"><span data-stu-id="d34b3-106">The general process for implementing a business logic handler is:</span></span>  
  
1.  <span data-ttu-id="d34b3-107">Создайте сборку обработчика бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="d34b3-107">Create the business logic hander assembly.</span></span>  
  
2.  <span data-ttu-id="d34b3-108">Зарегистрируйте сборку на распространителе.</span><span class="sxs-lookup"><span data-stu-id="d34b3-108">Register the assembly at the Distributor.</span></span>  
  
3.  <span data-ttu-id="d34b3-109">Выполните развертывание сборки на сервере, где работает агент слияния.</span><span class="sxs-lookup"><span data-stu-id="d34b3-109">Deploy the assembly at the server on which the Merge Agent runs.</span></span> <span data-ttu-id="d34b3-110">Для подписок по запросу агент работает на подписчике, а для принудительных подписок — на распространителе.</span><span class="sxs-lookup"><span data-stu-id="d34b3-110">For a pull subscription the agent runs on the Subscriber, and for a push subscription the agent runs on the Distributor.</span></span> <span data-ttu-id="d34b3-111">Если используется веб-синхронизация, агент работает на веб-сервере.</span><span class="sxs-lookup"><span data-stu-id="d34b3-111">When you are using Web synchronization, the agent runs on the Web server.</span></span>  
  
4.  <span data-ttu-id="d34b3-112">Создание новых статей и настройка существующих статей на использование обработчика бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="d34b3-112">Create an article that uses the business logic handler or modify an existing article to use the business logic handler.</span></span>  
  
 <span data-ttu-id="d34b3-113">Указанный обработчик бизнес-логики выполняется для каждой синхронизируемой строки.</span><span class="sxs-lookup"><span data-stu-id="d34b3-113">The business logic handler you specify is executed for every row that is synchronized.</span></span> <span data-ttu-id="d34b3-114">Сложная логика и вызовы других приложений или сетевых служб могут влиять на производительность.</span><span class="sxs-lookup"><span data-stu-id="d34b3-114">Complex logic and calls to other applications or network services can impact performance.</span></span> <span data-ttu-id="d34b3-115">Дополнительные сведения об обработчиках бизнес-логики см. в статье [Выполнение бизнес логики во время синхронизации слияния](merge/execute-business-logic-during-merge-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="d34b3-115">For more information about business logic handlers, see [Execute Business Logic During Merge Synchronization](merge/execute-business-logic-during-merge-synchronization.md).</span></span>  
  
 <span data-ttu-id="d34b3-116">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="d34b3-116">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d34b3-117">**Для реализации обработчика бизнес-логики для статьи публикации слиянием используется:**</span><span class="sxs-lookup"><span data-stu-id="d34b3-117">**To implement a business logic handler for a merge article, using:**</span></span>  
  
     [<span data-ttu-id="d34b3-118">Программирование репликации</span><span class="sxs-lookup"><span data-stu-id="d34b3-118">Replication Programming</span></span>](#ReplProg)  
  
     [<span data-ttu-id="d34b3-119">объекты RMO;</span><span class="sxs-lookup"><span data-stu-id="d34b3-119">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-replication-programming"></a><a name="ReplProg"></a> <span data-ttu-id="d34b3-120">При помощи программирования репликации</span><span class="sxs-lookup"><span data-stu-id="d34b3-120">Using Replication Programming</span></span>  
  
#### <a name="to-create-and-deploy-a-business-logic-handler"></a><span data-ttu-id="d34b3-121">Создание и развертывание обработчика бизнес-логики</span><span class="sxs-lookup"><span data-stu-id="d34b3-121">To create and deploy a business logic handler</span></span>  
  
1.  <span data-ttu-id="d34b3-122">В среде [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio создайте новый проект для сборки .NET, которая содержит код, реализующий обработчик бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="d34b3-122">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio, create a new project for the .NET assembly that contains the code that implements the business logic handler.</span></span>  
  
2.  <span data-ttu-id="d34b3-123">Добавьте в проект ссылки на следующие пространства имен.</span><span class="sxs-lookup"><span data-stu-id="d34b3-123">Add references to the project for the following namespaces.</span></span>  
  
    |<span data-ttu-id="d34b3-124">Ссылка на сборку</span><span class="sxs-lookup"><span data-stu-id="d34b3-124">Assembly Reference</span></span>|<span data-ttu-id="d34b3-125">Расположение</span><span class="sxs-lookup"><span data-stu-id="d34b3-125">Location</span></span>|  
    |------------------------|--------------|  
    |<xref:Microsoft.SqlServer.Replication.BusinessLogicSupport>|[!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)]<span data-ttu-id="d34b3-126">COM (место установки по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d34b3-126">COM (default installation)</span></span>|  
    |<xref:System.Data>|<span data-ttu-id="d34b3-127">Глобальный кэш сборок (компонент платформы .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="d34b3-127">GAC (component of the .NET Framework)</span></span>|  
    |<xref:System.Data.Common>|<span data-ttu-id="d34b3-128">Глобальный кэш сборок (компонент платформы .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="d34b3-128">GAC (component of the .NET Framework)</span></span>|  
  
3.  <span data-ttu-id="d34b3-129">Добавьте класс, переопределяющий класс <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> .</span><span class="sxs-lookup"><span data-stu-id="d34b3-129">Add a class that overrides the <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> class.</span></span>  
  
4.  <span data-ttu-id="d34b3-130">Реализуйте свойство <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.HandledChangeStates%2A> , чтобы показать обрабатываемые типы изменений.</span><span class="sxs-lookup"><span data-stu-id="d34b3-130">Implement the <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.HandledChangeStates%2A> property to indicate the types of changes that are handled.</span></span>  
  
5.  <span data-ttu-id="d34b3-131">Переопределите один или несколько следующих методов класса <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> :</span><span class="sxs-lookup"><span data-stu-id="d34b3-131">Override one or more of the following methods of the <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> class:</span></span>  
  
    -   <span data-ttu-id="d34b3-132"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.CommitHandler%2A> — вызывается, когда изменение данных фиксируется в ходе синхронизации;</span><span class="sxs-lookup"><span data-stu-id="d34b3-132"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.CommitHandler%2A> - invoked when a data change is committed during synchronization.</span></span>  
  
    -   <span data-ttu-id="d34b3-133"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.DeleteErrorHandler%2A> — вызывается, когда возникает ошибка при загрузке или передаче инструкции DELETE;</span><span class="sxs-lookup"><span data-stu-id="d34b3-133"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.DeleteErrorHandler%2A> - invoked when an error occurs when a DELETE statement is being uploaded or downloaded.</span></span>  
  
    -   <span data-ttu-id="d34b3-134"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.DeleteHandler%2A> — вызывается, когда передаются или загружаются инструкции DELETE;</span><span class="sxs-lookup"><span data-stu-id="d34b3-134"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.DeleteHandler%2A> - invoked when DELETE statements are being uploaded or downloaded.</span></span>  
  
    -   <span data-ttu-id="d34b3-135"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.InsertErrorHandler%2A> — вызывается, когда возникает ошибка при загрузке или передаче инструкции INSERT;</span><span class="sxs-lookup"><span data-stu-id="d34b3-135"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.InsertErrorHandler%2A> - invoked when an error occurs when an INSERT statement is being uploaded or downloaded.</span></span>  
  
    -   <span data-ttu-id="d34b3-136"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.InsertHandler%2A> — вызывается, когда передаются или загружаются инструкции INSERT;</span><span class="sxs-lookup"><span data-stu-id="d34b3-136"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.InsertHandler%2A> - invoked when INSERT statements are being uploaded or downloaded.</span></span>  
  
    -   <span data-ttu-id="d34b3-137"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.UpdateConflictsHandler%2A> — вызывается, когда на издателе или на подписчике возникает конфликт инструкций UPDATE;</span><span class="sxs-lookup"><span data-stu-id="d34b3-137"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.UpdateConflictsHandler%2A> - invoked when conflicting UPDATE statements occur at the Publisher and Subscriber.</span></span>  
  
    -   <span data-ttu-id="d34b3-138"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.UpdateDeleteConflictHandler%2A> — вызывается, когда инструкции UPDATE вызывают конфликт с инструкциями DELETE на издателе и на подписчике;</span><span class="sxs-lookup"><span data-stu-id="d34b3-138"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.UpdateDeleteConflictHandler%2A> - invoked when UPDATE statements conflict with DELETE statements at the Publisher and Subscriber.</span></span>  
  
    -   <span data-ttu-id="d34b3-139"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.UpdateErrorHandler%2A> — вызывается, когда возникает ошибка при загрузке или передаче инструкции UPDATE;</span><span class="sxs-lookup"><span data-stu-id="d34b3-139"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.UpdateErrorHandler%2A> - invoked when an error occurs when an UPDATE statement is being uploaded or downloaded.</span></span>  
  
    -   <span data-ttu-id="d34b3-140"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.UpdateHandler%2A> — вызывается, когда передаются или загружаются инструкции UPDATE.</span><span class="sxs-lookup"><span data-stu-id="d34b3-140"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.UpdateHandler%2A> - invoked when UPDATE statements are being uploaded or downloaded.</span></span>  
  
6.  <span data-ttu-id="d34b3-141">Постройте проект, чтобы создать сборку обработчика бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="d34b3-141">Build the project to create the business logic handler assembly.</span></span>  
  
7.  <span data-ttu-id="d34b3-142">Произведите развертывание сборки в каталоге, содержащем исполняемый файл агента слияния (replmerg.exe), который по умолчанию устанавливается в каталог [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)]COM, либо установите его в глобальный кэш сборок .NET.</span><span class="sxs-lookup"><span data-stu-id="d34b3-142">Deploy the assembly in the directory that contains the Merge Agent executable file (replmerg.exe), which for a default installation is [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)]COM, or install it in the .NET global assembly cache (GAC).</span></span> <span data-ttu-id="d34b3-143">Если эта сборка используется не только агентом слияния, то она должна быть помещена в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="d34b3-143">You should only install the assembly in the GAC if applications other than the Merge Agent require access to the assembly.</span></span> <span data-ttu-id="d34b3-144">Установка сборки в глобальный кэш производится с помощью соответствующей программы (**Gacutil.exe)** , поставляемой в пакете .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="d34b3-144">The assembly can be installed into the GAC using the Global Assembly Cache tool (**Gacutil.exe)** provided in the .NET Framework SDK.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d34b3-145">Обработчик бизнес-логики должен быть развернут на всех серверах, на которых работает агент слияния, включая север IIS, на котором во время веб-синхронизации находится файл replisapi.dll.</span><span class="sxs-lookup"><span data-stu-id="d34b3-145">A business logic handler must be deployed on every server on which the Merge Agent runs, which includes the IIS server that hosts the replisapi.dll when using Web synchronization.</span></span>  
  
#### <a name="to-register-a-business-logic-handler"></a><span data-ttu-id="d34b3-146">Регистрация обработчика бизнес-логики</span><span class="sxs-lookup"><span data-stu-id="d34b3-146">To register a business logic handler</span></span>  
  
1.  <span data-ttu-id="d34b3-147">Чтобы убедиться, что сборка не была зарегистрирована ранее как обработчик бизнес-логики, выполните на издателе процедуру [sp_enumcustomresolvers (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-enumcustomresolvers-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d34b3-147">At the Publisher, execute [sp_enumcustomresolvers &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-enumcustomresolvers-transact-sql) to verify that the assembly has not already been registered as a business logic handler.</span></span>  
  
2.  <span data-ttu-id="d34b3-148">На распространителе выполните [sp_registercustomresolver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-registercustomresolver-transact-sql), указав Понятное имя обработчика бизнес-логики для **@article_resolver** , значение для, `true` **@is_dotnet_assembly** имя сборки для **@dotnet_assembly_name** и полное имя класса, переопределяющий <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> для **@dotnet_class_name** .</span><span class="sxs-lookup"><span data-stu-id="d34b3-148">At the Distributor, execute [sp_registercustomresolver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-registercustomresolver-transact-sql), specifying a friendly name for the business logic handler for **@article_resolver**, a value of `true` for **@is_dotnet_assembly**, the name of the assembly for **@dotnet_assembly_name**, and the fully-qualified name of the class that overrides <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> for **@dotnet_class_name**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d34b3-149">Если сборка не развернута в том же каталоге, что и исполняемый файл агент слияния, в том же каталоге, что и приложение, синхронно запускающее агент слияния, или в глобальном кэше сборок (GAC), необходимо указать полный путь с именем сборки для **@dotnet_assembly_name** .</span><span class="sxs-lookup"><span data-stu-id="d34b3-149">If the assembly is not deployed in the same directory as the Merge Agent executable, in the same directory as the application that synchronously starts the Merge Agent, or in the global assembly cache (GAC), you need to specify the full path with the assembly name for **@dotnet_assembly_name**.</span></span> <span data-ttu-id="d34b3-150">При проведении сеанса веб-синхронизации необходимо указать местоположение сборки на веб-сервере.</span><span class="sxs-lookup"><span data-stu-id="d34b3-150">When using Web synchronization, you must specify the location of assembly at the Web server.</span></span>  
  
#### <a name="to-use-a-business-logic-handler-with-a-new-table-article"></a><span data-ttu-id="d34b3-151">Использование обработчика бизнес-логики со статьей в новой таблице</span><span class="sxs-lookup"><span data-stu-id="d34b3-151">To use a business logic handler with a new table article</span></span>  
  
1.  <span data-ttu-id="d34b3-152">Чтобы определить статью, запустите хранимую процедуру [sp_addmergearticle (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql), указав понятное имя обработчика бизнес-логики в параметре **@article_resolver**.</span><span class="sxs-lookup"><span data-stu-id="d34b3-152">Execute [sp_addmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql) to define an article, specifying the friendly name of the business logic handler for **@article_resolver**.</span></span> <span data-ttu-id="d34b3-153">Дополнительные сведения см. в статье [определить статью](publish/define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="d34b3-153">For more information, see [Define an Article](publish/define-an-article.md).</span></span>  
  
#### <a name="to-use-a-business-logic-handler-with-an-existing-table-article"></a><span data-ttu-id="d34b3-154">Использование обработчика бизнес-логики со статьей в существующей таблице</span><span class="sxs-lookup"><span data-stu-id="d34b3-154">To use a business logic handler with an existing table article</span></span>  
  
1.  <span data-ttu-id="d34b3-155">Выполните [sp_changemergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql), указав **@publication** , **@article** , значение **article_resolver** в параметре **@property** и понятное имя обработчика бизнес-логики для **@value** .</span><span class="sxs-lookup"><span data-stu-id="d34b3-155">Execute [sp_changemergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql), specifying **@publication**, **@article**, a value of **article_resolver** for **@property**, and the friendly name of the business logic handler for **@value**.</span></span>  
  
###  <a name="examples-replication-programming"></a><a name="TsqlExample"></a> <span data-ttu-id="d34b3-156">Примеры (программирование репликации)</span><span class="sxs-lookup"><span data-stu-id="d34b3-156">Examples (Replication Programming)</span></span>  
 <span data-ttu-id="d34b3-157">В следующем примере представлен обработчик бизнес-логики, осуществляющий запись в журнал аудита.</span><span class="sxs-lookup"><span data-stu-id="d34b3-157">This example shows a business logic handler that creates an audit log.</span></span>  
  
 [!code-csharp[HowTo#rmo_BusinessLogicCode](../../snippets/csharp/SQL15/replication/howto/cs/businesslogic.cs#rmo_businesslogiccode)]  
  
 [!code-vb[HowTo#rmo_vb_BusinessLogicCode](../../snippets/visualbasic/SQL15/replication/howto/vb/businesslogic.vb#rmo_vb_businesslogiccode)]  
  
 <span data-ttu-id="d34b3-158">Следующий пример осуществляет регистрацию обработчика бизнес-логики на сервере распространителя и настройку существующих статей публикации на его использование.</span><span class="sxs-lookup"><span data-stu-id="d34b3-158">The following example registers a business logic handler assembly at the Distributor and changes an existing merge article to use this custom business logic.</span></span>  
  
 [!code-sql[HowTo#sp_RegisterBLH_10](../../snippets/tsql/SQL15/replication/howto/tsql/registerblh_10.sql#sp_registerblh_10)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="d34b3-159">При помощи объектов RMO</span><span class="sxs-lookup"><span data-stu-id="d34b3-159">Using Replication Management Objects (RMO)</span></span>  
  
#### <a name="to-create-a-business-logic-handler"></a><span data-ttu-id="d34b3-160">Создание обработчика бизнес-логики</span><span class="sxs-lookup"><span data-stu-id="d34b3-160">To create a business logic handler</span></span>  
  
1.  <span data-ttu-id="d34b3-161">В среде [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio создайте новый проект для сборки .NET, которая содержит код, реализующий обработчик бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="d34b3-161">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio, create a new project for the .NET assembly that contains the code that implements the business logic handler.</span></span>  
  
2.  <span data-ttu-id="d34b3-162">Добавьте в проект ссылки на следующие пространства имен.</span><span class="sxs-lookup"><span data-stu-id="d34b3-162">Add references to the project for the following namespaces.</span></span>  
  
    |<span data-ttu-id="d34b3-163">Ссылка на сборку</span><span class="sxs-lookup"><span data-stu-id="d34b3-163">Assembly Reference</span></span>|<span data-ttu-id="d34b3-164">Расположение</span><span class="sxs-lookup"><span data-stu-id="d34b3-164">Location</span></span>|  
    |------------------------|--------------|  
    |<xref:Microsoft.SqlServer.Replication.BusinessLogicSupport>|[!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)]<span data-ttu-id="d34b3-165">COM (место установки по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d34b3-165">COM (default installation)</span></span>|  
    |<xref:System.Data>|<span data-ttu-id="d34b3-166">Глобальный кэш сборок (компонент платформы .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="d34b3-166">GAC (component of the .NET Framework)</span></span>|  
    |<xref:System.Data.Common>|<span data-ttu-id="d34b3-167">Глобальный кэш сборок (компонент платформы .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="d34b3-167">GAC (component of the .NET Framework)</span></span>|  
  
3.  <span data-ttu-id="d34b3-168">Добавьте класс, переопределяющий класс <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> .</span><span class="sxs-lookup"><span data-stu-id="d34b3-168">Add a class that overrides the <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> class.</span></span>  
  
4.  <span data-ttu-id="d34b3-169">Реализуйте свойство <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.HandledChangeStates%2A> , чтобы показать обрабатываемые типы изменений.</span><span class="sxs-lookup"><span data-stu-id="d34b3-169">Implement the <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.HandledChangeStates%2A> property to indicate the types of changes that are handled.</span></span>  
  
5.  <span data-ttu-id="d34b3-170">Переопределите один или несколько следующих методов класса <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> :</span><span class="sxs-lookup"><span data-stu-id="d34b3-170">Override one or more of the following methods of the <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> class:</span></span>  
  
    -   <span data-ttu-id="d34b3-171"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.CommitHandler%2A> — вызывается, когда изменение данных фиксируется в ходе синхронизации;</span><span class="sxs-lookup"><span data-stu-id="d34b3-171"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.CommitHandler%2A> - invoked when a data change is committed during synchronization.</span></span>  
  
    -   <span data-ttu-id="d34b3-172"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.DeleteErrorHandler%2A> — вызывается, когда возникает ошибка при загрузке или передаче инструкции DELETE;</span><span class="sxs-lookup"><span data-stu-id="d34b3-172"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.DeleteErrorHandler%2A> - invoked if an error occurs while a DELETE statement is being uploaded or downloaded.</span></span>  
  
    -   <span data-ttu-id="d34b3-173"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.DeleteHandler%2A> — вызывается, когда передаются или загружаются инструкции DELETE;</span><span class="sxs-lookup"><span data-stu-id="d34b3-173"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.DeleteHandler%2A> - invoked when DELETE statements are being uploaded or downloaded.</span></span>  
  
    -   <span data-ttu-id="d34b3-174"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.InsertErrorHandler%2A> — вызывается, когда возникает ошибка при загрузке или передаче инструкции INSERT;</span><span class="sxs-lookup"><span data-stu-id="d34b3-174"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.InsertErrorHandler%2A> - invoked if an error occurs when an INSERT statement is being uploaded or downloaded.</span></span>  
  
    -   <span data-ttu-id="d34b3-175"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.InsertHandler%2A> — вызывается, когда передаются или загружаются инструкции INSERT;</span><span class="sxs-lookup"><span data-stu-id="d34b3-175"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.InsertHandler%2A> - invoked when INSERT statements are being uploaded or downloaded.</span></span>  
  
    -   <span data-ttu-id="d34b3-176"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.UpdateConflictsHandler%2A> — вызывается, когда на издателе или на подписчике возникает конфликт инструкций UPDATE;</span><span class="sxs-lookup"><span data-stu-id="d34b3-176"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.UpdateConflictsHandler%2A> - invoked when conflicting UPDATE statements occur at the Publisher and Subscriber.</span></span>  
  
    -   <span data-ttu-id="d34b3-177"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.UpdateDeleteConflictHandler%2A> — вызывается, когда инструкции UPDATE вызывают конфликт с инструкциями DELETE на издателе и на подписчике;</span><span class="sxs-lookup"><span data-stu-id="d34b3-177"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.UpdateDeleteConflictHandler%2A> - invoked when UPDATE statements conflict with DELETE statements at the Publisher and Subscriber.</span></span>  
  
    -   <span data-ttu-id="d34b3-178"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.UpdateErrorHandler%2A> — вызывается, когда возникает ошибка в инструкции UPDATE при передаче или загрузке;</span><span class="sxs-lookup"><span data-stu-id="d34b3-178"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.UpdateErrorHandler%2A> - invoked if an error occurs when an UPDATE statement is being uploaded or downloaded.</span></span>  
  
    -   <span data-ttu-id="d34b3-179"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.UpdateHandler%2A> — вызывается, когда передаются или загружаются инструкции UPDATE.</span><span class="sxs-lookup"><span data-stu-id="d34b3-179"><xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule.UpdateHandler%2A> - invoked when UPDATE statements are being uploaded or downloaded.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d34b3-180">Все конфликты статей, не обработанные пользовательской бизнес-логикой явным образом, обрабатываются сопоставителем конфликтов по умолчанию, назначенным для данной статьи.</span><span class="sxs-lookup"><span data-stu-id="d34b3-180">Any article conflicts not explicitly handled by your custom business logic are handled by the default resolver for the article.</span></span>  
  
6.  <span data-ttu-id="d34b3-181">Постройте проект, чтобы создать сборку обработчика бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="d34b3-181">Build the project to create the business logic handler assembly.</span></span>  
  
#### <a name="to-register-a-business-logic-handler"></a><span data-ttu-id="d34b3-182">Регистрация обработчика бизнес-логики</span><span class="sxs-lookup"><span data-stu-id="d34b3-182">To register a business logic handler</span></span>  
  
1.  <span data-ttu-id="d34b3-183">Создайте соединение с распространителем с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="d34b3-183">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="d34b3-184">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="d34b3-184">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span> <span data-ttu-id="d34b3-185">Передайте объект <xref:Microsoft.SqlServer.Management.Common.ServerConnection> , созданный на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="d34b3-185">Pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1.</span></span>  
  
3.  <span data-ttu-id="d34b3-186">Чтобы убедиться, что сборка не была ранее зарегистрирована в качестве обработчика бизнес-логики, вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationServer.EnumBusinessLogicHandlers%2A> и просмотрите возвращенный объект <xref:System.Collections.ArrayList> .</span><span class="sxs-lookup"><span data-stu-id="d34b3-186">Call <xref:Microsoft.SqlServer.Replication.ReplicationServer.EnumBusinessLogicHandlers%2A> and check the returned <xref:System.Collections.ArrayList> object to ensure that the assembly has not already been registered as a business logic handler.</span></span>  
  
4.  <span data-ttu-id="d34b3-187">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.BusinessLogicHandler>.</span><span class="sxs-lookup"><span data-stu-id="d34b3-187">Create an instance of the <xref:Microsoft.SqlServer.Replication.BusinessLogicHandler> class.</span></span> <span data-ttu-id="d34b3-188">Задайте следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="d34b3-188">Specify the following properties:</span></span>  
  
    -   <span data-ttu-id="d34b3-189"><xref:Microsoft.SqlServer.Replication.BusinessLogicHandler.DotNetAssemblyName%2A> — имя сборки .NET.</span><span class="sxs-lookup"><span data-stu-id="d34b3-189"><xref:Microsoft.SqlServer.Replication.BusinessLogicHandler.DotNetAssemblyName%2A> - the name of the .NET assembly.</span></span> <span data-ttu-id="d34b3-190">Если сборка не найдена ни в том же каталоге, что и исполняемый файл агента слияния, ни в папке приложения, производящего синхронный запуск агента слияния, ни в глобальном кэше сборок (GAC), то ее имя должно включать полный путь.</span><span class="sxs-lookup"><span data-stu-id="d34b3-190">If the assembly is not deployed in the same directory as the Merge Agent executable, in the same directory as the application that synchronously starts the Merge Agent, or in the GAC, you must include the full path with the assembly name.</span></span> <span data-ttu-id="d34b3-191">При использовании обработчика бизнес-логики во время сеанса веб-синхронизации необходимо перед именем сборки указывать ее полный путь.</span><span class="sxs-lookup"><span data-stu-id="d34b3-191">You must include the full path with the assembly name when using a business logic handler with Web synchronization.</span></span>  
  
    -   <span data-ttu-id="d34b3-192"><xref:Microsoft.SqlServer.Replication.BusinessLogicHandler.DotNetClassName%2A> — полное имя класса, который замещает класс <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> и реализует обработчик бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="d34b3-192"><xref:Microsoft.SqlServer.Replication.BusinessLogicHandler.DotNetClassName%2A> - the fully-qualified name of the class that overrides <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> and implements the business logic handler.</span></span>  
  
    -   <span data-ttu-id="d34b3-193"><xref:Microsoft.SqlServer.Replication.BusinessLogicHandler.FriendlyName%2A> — понятное имя, используемое для доступа к обработчику бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="d34b3-193"><xref:Microsoft.SqlServer.Replication.BusinessLogicHandler.FriendlyName%2A> - a friendly name you use when you access the business logic handler.</span></span>  
  
    -   <span data-ttu-id="d34b3-194"><xref:Microsoft.SqlServer.Replication.BusinessLogicHandler.IsDotNetAssembly%2A> — значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d34b3-194"><xref:Microsoft.SqlServer.Replication.BusinessLogicHandler.IsDotNetAssembly%2A> - a value of `true`.</span></span>  
  
#### <a name="to-deploy-a-business-logic-handler"></a><span data-ttu-id="d34b3-195">Развертывание обработчика бизнес-логики</span><span class="sxs-lookup"><span data-stu-id="d34b3-195">To deploy a business logic handler</span></span>  
  
1.  <span data-ttu-id="d34b3-196">Произведите развертывание сборки на сервере, где запущен агент слияния, в папке, заданной при регистрации обработчика бизнес-логики на распространителе.</span><span class="sxs-lookup"><span data-stu-id="d34b3-196">Deploy the assembly on the server where the Merge Agent runs in the file location specified when the business logic handler was registered at the Distributor.</span></span> <span data-ttu-id="d34b3-197">Для подписок по запросу агент работает на подписчике, а для принудительных подписок — на распространителе.</span><span class="sxs-lookup"><span data-stu-id="d34b3-197">For a pull subscription the agent runs on the Subscriber, and for a push subscription the agent runs on the Distributor.</span></span> <span data-ttu-id="d34b3-198">Если используется веб-синхронизация, агент работает на веб-сервере.</span><span class="sxs-lookup"><span data-stu-id="d34b3-198">When you are using Web synchronization, the agent runs on the Web server.</span></span> <span data-ttu-id="d34b3-199">Если в процессе регистрации обработчика бизнес-логики не был указан полный путь сборки, то ее развертывание необходимо производить в том же каталоге, что и исполняемый объект агента слияния, либо в папке приложения, осуществляющего запуск агента слияния в синхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="d34b3-199">If the full path was not included with the assembly name when the business logic handler was registered, deploy the assembly in the same directory as the Merge Agent executable, in the same directory as the application that synchronously starts the Merge Agent.</span></span> <span data-ttu-id="d34b3-200">Если сборка используется несколькими приложениями, то ее необходимо установить в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="d34b3-200">You may install the assembly in the GAC if there are multiple applications that use the same assembly.</span></span>  
  
#### <a name="to-use-a-business-logic-handler-with-a-new-table-article"></a><span data-ttu-id="d34b3-201">Использование обработчика бизнес-логики со статьей в новой таблице</span><span class="sxs-lookup"><span data-stu-id="d34b3-201">To use a business logic handler with a new table article</span></span>  
  
1.  <span data-ttu-id="d34b3-202">Создайте соединение с издателем с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="d34b3-202">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="d34b3-203">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.MergeArticle>.</span><span class="sxs-lookup"><span data-stu-id="d34b3-203">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeArticle> class.</span></span> <span data-ttu-id="d34b3-204">Задайте следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="d34b3-204">Set the following properties:</span></span>  
  
    -   <span data-ttu-id="d34b3-205">Имя статьи для <xref:Microsoft.SqlServer.Replication.Article.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="d34b3-205">The name of the article for <xref:Microsoft.SqlServer.Replication.Article.Name%2A>.</span></span>  
  
    -   <span data-ttu-id="d34b3-206">Имя публикации в свойстве <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="d34b3-206">The name of the publication for <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="d34b3-207">Имя базы данных публикации в свойстве <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="d34b3-207">The name of the publication database for <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="d34b3-208">Понятное имя обработчика бизнес-логики (<xref:Microsoft.SqlServer.Replication.BusinessLogicHandler.FriendlyName%2A>) в свойстве <xref:Microsoft.SqlServer.Replication.MergeArticle.ArticleResolver%2A>.</span><span class="sxs-lookup"><span data-stu-id="d34b3-208">The friendly name of the business logic handler (<xref:Microsoft.SqlServer.Replication.BusinessLogicHandler.FriendlyName%2A>) for <xref:Microsoft.SqlServer.Replication.MergeArticle.ArticleResolver%2A>.</span></span>  
  
3.  <span data-ttu-id="d34b3-209">Вызовите метод <xref:Microsoft.SqlServer.Replication.Article.Create%2A> .</span><span class="sxs-lookup"><span data-stu-id="d34b3-209">Call the <xref:Microsoft.SqlServer.Replication.Article.Create%2A> method.</span></span> <span data-ttu-id="d34b3-210">Дополнительные сведения см. в статье [определить статью](publish/define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="d34b3-210">For more information, see [Define an Article](publish/define-an-article.md).</span></span>  
  
#### <a name="to-use-a-business-logic-handler-with-an-existing-table-article"></a><span data-ttu-id="d34b3-211">Использование обработчика бизнес-логики со статьей в существующей таблице</span><span class="sxs-lookup"><span data-stu-id="d34b3-211">To use a business logic handler with an existing table article</span></span>  
  
1.  <span data-ttu-id="d34b3-212">Создайте соединение с издателем с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="d34b3-212">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="d34b3-213">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.MergeArticle>.</span><span class="sxs-lookup"><span data-stu-id="d34b3-213">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeArticle> class.</span></span>  
  
3.  <span data-ttu-id="d34b3-214">Установите свойства <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>и <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="d34b3-214">Set the <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>, and <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="d34b3-215">Установите полученное на шаге 1 соединение в качестве значения свойства <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="d34b3-215">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="d34b3-216">Чтобы получить свойства объекта, вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="d34b3-216">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="d34b3-217">Если этот метод возвращает `false`, то либо на шаге 3 были неверно определены свойства статьи, либо статья не существует.</span><span class="sxs-lookup"><span data-stu-id="d34b3-217">If this method returns `false`, either the article properties in step 3 were defined incorrectly or the article does not exist.</span></span> <span data-ttu-id="d34b3-218">Дополнительные сведения см. в статье [View and Modify Article Properties](publish/view-and-modify-article-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d34b3-218">For more information, see [View and Modify Article Properties](publish/view-and-modify-article-properties.md).</span></span>  
  
6.  <span data-ttu-id="d34b3-219">Задайте понятное имя обработчика бизнес-логики в параметре <xref:Microsoft.SqlServer.Replication.MergeArticle.ArticleResolver%2A>.</span><span class="sxs-lookup"><span data-stu-id="d34b3-219">Set the friendly name of the business logic handler for <xref:Microsoft.SqlServer.Replication.MergeArticle.ArticleResolver%2A>.</span></span> <span data-ttu-id="d34b3-220">Это значение свойства <xref:Microsoft.SqlServer.Replication.BusinessLogicHandler.FriendlyName%2A> , указанного при регистрации обработчика бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="d34b3-220">This is the value of the <xref:Microsoft.SqlServer.Replication.BusinessLogicHandler.FriendlyName%2A> property specified when registering the business logic handler.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="d34b3-221">Примеры (объекты RMO)</span><span class="sxs-lookup"><span data-stu-id="d34b3-221">Examples (RMO)</span></span>  
 <span data-ttu-id="d34b3-222">В следующем примере реализуется обработчик бизнес-логики, осуществляющий запись в журнал операций вставки, обновления и удаления на подписчике.</span><span class="sxs-lookup"><span data-stu-id="d34b3-222">This example is a business logic handler that logs information about inserts, updates, and deletes at the Subscriber.</span></span>  
  
 [!code-csharp[HowTo#rmo_BusinessLogicCode](../../snippets/csharp/SQL15/replication/howto/cs/businesslogic.cs#rmo_businesslogiccode)]  
  
 [!code-vb[HowTo#rmo_vb_BusinessLogicCode](../../snippets/visualbasic/SQL15/replication/howto/vb/businesslogic.vb#rmo_vb_businesslogiccode)]  
  
 <span data-ttu-id="d34b3-223">В следующем примере производится регистрация обработчика бизнес-логики на распространителе.</span><span class="sxs-lookup"><span data-stu-id="d34b3-223">This example registers a business logic handler at the Distributor.</span></span>  
  
 [!code-csharp[HowTo#rmo_RegisterBLH_10](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_registerblh_10)]  
  
 [!code-vb[HowTo#rmo_vb_RegisterBLH_10](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_registerblh_10)]  
  
 <span data-ttu-id="d34b3-224">В следующем примере производится настройка существующей статьи на использование обработчика бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="d34b3-224">This example changes an existing article to use the business logic handler.</span></span>  
  
 [!code-csharp[HowTo#rmo_ChangeMergeArticle_BLH](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_changemergearticle_blh)]  
  
 [!code-vb[HowTo#rmo_vb_ChangeMergeArticle_BLH](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_changemergearticle_blh)]  
  
## <a name="see-also"></a><span data-ttu-id="d34b3-225">См. также:</span><span class="sxs-lookup"><span data-stu-id="d34b3-225">See Also</span></span>  
 <span data-ttu-id="d34b3-226">[Реализация пользовательского сопоставителя конфликтов для статьи публикации слиянием](implement-a-custom-conflict-resolver-for-a-merge-article.md) </span><span class="sxs-lookup"><span data-stu-id="d34b3-226">[Implement a Custom Conflict Resolver for a Merge Article](implement-a-custom-conflict-resolver-for-a-merge-article.md) </span></span>  
 <span data-ttu-id="d34b3-227">[Отладка обработчика бизнес-логики &#40;программирование репликации&#41;](debug-a-business-logic-handler-replication-programming.md) </span><span class="sxs-lookup"><span data-stu-id="d34b3-227">[Debug a Business Logic Handler &#40;Replication Programming&#41;](debug-a-business-logic-handler-replication-programming.md) </span></span>  
 <span data-ttu-id="d34b3-228">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="d34b3-228">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="d34b3-229">Основные понятия объектов RMO</span><span class="sxs-lookup"><span data-stu-id="d34b3-229">Replication Management Objects Concepts</span></span>](concepts/replication-management-objects-concepts.md)  
  
  
