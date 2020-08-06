---
title: Редактор задачи «Перемещение имен входа» (страница «имена входа») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferloginstask.logins.f1
helpviewer_keywords:
- Transfer Logins Task Editor
ms.assetid: bf244c24-bd45-4ece-b66b-78b488f35c5b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b33fea6c78df75b7eebe8987f952dce33bdc4407
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669464"
---
# <a name="transfer-logins-task-editor-logins-page"></a><span data-ttu-id="2b202-102">Редактор задачи «Передача имен входа» (страница «Имена входа»)</span><span class="sxs-lookup"><span data-stu-id="2b202-102">Transfer Logins Task Editor (Logins Page)</span></span>
  <span data-ttu-id="2b202-103">Страница **Имена входа** диалогового окна **Редактор задачи «Передача имен входа»** используется для задания свойств для копирования одного или более имен входа [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] из одного экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] в другой.</span><span class="sxs-lookup"><span data-stu-id="2b202-103">Use the **Logins** page of the **Transfer Logins Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="2b202-104">Дополнительные сведения об этой задаче см. в разделе [Transfer Logins Task](control-flow/transfer-logins-task.md).</span><span class="sxs-lookup"><span data-stu-id="2b202-104">For more information about this task, see [Transfer Logins Task](control-flow/transfer-logins-task.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2b202-105">При выполнении задачи «Передача имен входа» имена создаются на целевом сервере со случайными паролями, и эти пароли отключаются.</span><span class="sxs-lookup"><span data-stu-id="2b202-105">When the Transfer Logins task is executed, logins are created on the destination server with random passwords and the passwords are disabled.</span></span> <span data-ttu-id="2b202-106">Для использования этих имен входа элемент предопределенной роли сервера **sysadmin** должен изменить пароли и затем включить их.</span><span class="sxs-lookup"><span data-stu-id="2b202-106">To use these logins, a member of the **sysadmin** fixed server role must change the passwords and then enable them.</span></span> <span data-ttu-id="2b202-107">Имя входа **sa** передать нельзя.</span><span class="sxs-lookup"><span data-stu-id="2b202-107">The **sa** login cannot be transferred.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2b202-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="2b202-108">Options</span></span>  
 <span data-ttu-id="2b202-109">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="2b202-109">**SourceConnection**</span></span>  
 <span data-ttu-id="2b202-110">Выберите из списка диспетчер подключений SMO или нажмите кнопку **\<New connection...>** , чтобы создать новое подключение к исходному серверу.</span><span class="sxs-lookup"><span data-stu-id="2b202-110">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="2b202-111">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="2b202-111">**DestinationConnection**</span></span>  
 <span data-ttu-id="2b202-112">Выберите из списка диспетчер подключений SMO или нажмите кнопку **\<New connection...>** , чтобы создать новое подключение к целевому серверу.</span><span class="sxs-lookup"><span data-stu-id="2b202-112">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="2b202-113">**LoginsToTransfer**</span><span class="sxs-lookup"><span data-stu-id="2b202-113">**LoginsToTransfer**</span></span>  
 <span data-ttu-id="2b202-114">Выберите имена входа [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] для копирования их с исходного сервера на целевой.</span><span class="sxs-lookup"><span data-stu-id="2b202-114">Select the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins to copy from the source to the destination server.</span></span> <span data-ttu-id="2b202-115">Параметры этого свойства приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="2b202-115">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="2b202-116">Значение</span><span class="sxs-lookup"><span data-stu-id="2b202-116">Value</span></span>|<span data-ttu-id="2b202-117">Description</span><span class="sxs-lookup"><span data-stu-id="2b202-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2b202-118">**AllLogins**</span><span class="sxs-lookup"><span data-stu-id="2b202-118">**AllLogins**</span></span>|<span data-ttu-id="2b202-119">Все имена входа [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] на исходном сервере будут скопированы на целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="2b202-119">All [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins on the source server will be copied to the destination server.</span></span>|  
|<span data-ttu-id="2b202-120">**SelectedLogins**</span><span class="sxs-lookup"><span data-stu-id="2b202-120">**SelectedLogins**</span></span>|<span data-ttu-id="2b202-121">На целевой сервер будут скопированы только имена входа, заданные списком **LoginsList** .</span><span class="sxs-lookup"><span data-stu-id="2b202-121">Only logins specified with **LoginsList** will be copied to the destination server.</span></span>|  
|<span data-ttu-id="2b202-122">**AllLoginsFromSelectedDatabases**</span><span class="sxs-lookup"><span data-stu-id="2b202-122">**AllLoginsFromSelectedDatabases**</span></span>|<span data-ttu-id="2b202-123">Все имена входа из баз данных, заданных списком **DatabasesList** , будут скопированы на целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="2b202-123">All logins from the databases specified with **DatabasesList** will be copied to the destination server.</span></span>|  
  
 <span data-ttu-id="2b202-124">**LoginsList**</span><span class="sxs-lookup"><span data-stu-id="2b202-124">**LoginsList**</span></span>  
 <span data-ttu-id="2b202-125">Определяет имена входа на исходном сервере для копирования на целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="2b202-125">Select the logins on the source server to be copied to the destination server.</span></span> <span data-ttu-id="2b202-126">Этот параметр доступен только в том случае, если значение **SelectedLogins** выбрано для **LoginsToTransfer**.</span><span class="sxs-lookup"><span data-stu-id="2b202-126">This option is only available when **SelectedLogins** is selected for **LoginsToTransfer**.</span></span>  
  
 <span data-ttu-id="2b202-127">**DatabasesList**</span><span class="sxs-lookup"><span data-stu-id="2b202-127">**DatabasesList**</span></span>  
 <span data-ttu-id="2b202-128">Определяет базы данных на исходном сервере, которые содержат имена входа для копирования на целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="2b202-128">Select the databases on the source server that contain logins to be copied to the destination server.</span></span> <span data-ttu-id="2b202-129">Этот параметр доступен только в том случае, если значение **AllLoginsFromSelectedDatabases** выбрано для **LoginsToTransfer**.</span><span class="sxs-lookup"><span data-stu-id="2b202-129">This option is only available when **AllLoginsFromSelectedDatabases** is selected for **LoginsToTransfer**.</span></span>  
  
 <span data-ttu-id="2b202-130">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="2b202-130">**IfObjectExists**</span></span>  
 <span data-ttu-id="2b202-131">Определяет то, как задача должна обрабатывать имена входа с тем же названием, что и у существующих на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="2b202-131">Select how the task should handle logins of the same name that already exist on the destination server.</span></span>  
  
 <span data-ttu-id="2b202-132">Параметры этого свойства приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="2b202-132">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="2b202-133">Значение</span><span class="sxs-lookup"><span data-stu-id="2b202-133">Value</span></span>|<span data-ttu-id="2b202-134">Description</span><span class="sxs-lookup"><span data-stu-id="2b202-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2b202-135">**FailTask**</span><span class="sxs-lookup"><span data-stu-id="2b202-135">**FailTask**</span></span>|<span data-ttu-id="2b202-136">Задача не выполняется, если такое же имя входа уже существует на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="2b202-136">Task fails if logins of the same name already exist on the destination server.</span></span>|  
|<span data-ttu-id="2b202-137">**Overwrite**</span><span class="sxs-lookup"><span data-stu-id="2b202-137">**Overwrite**</span></span>|<span data-ttu-id="2b202-138">Задача перезаписывает имя входа на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="2b202-138">Task overwrites logins of the same name on the destination server.</span></span>|  
|<span data-ttu-id="2b202-139">**Skip**</span><span class="sxs-lookup"><span data-stu-id="2b202-139">**Skip**</span></span>|<span data-ttu-id="2b202-140">Задача пропускает обработку имени входа, если такое же имя входа уже существует на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="2b202-140">Task skips logins of the same name that exist on the destination server.</span></span>|  
  
 <span data-ttu-id="2b202-141">**CopySids**</span><span class="sxs-lookup"><span data-stu-id="2b202-141">**CopySids**</span></span>  
 <span data-ttu-id="2b202-142">Определяет, будут ли скопированы на целевой сервер идентификаторы безопасности, связанные с именами входа.</span><span class="sxs-lookup"><span data-stu-id="2b202-142">Select whether the security identifiers associated with the logins should be copied to the destination server.</span></span> <span data-ttu-id="2b202-143">Параметр**CopySids** должен иметь значение **True** , если задача «Передача имен входа» используется вместе с задачей «Передача базы данных».</span><span class="sxs-lookup"><span data-stu-id="2b202-143">**CopySids** must be set to **True** if the Transfer Logins task is used along with the Transfer Database task.</span></span> <span data-ttu-id="2b202-144">В противном случае скопированные имена входа не будут распознаны переданными базами данных.</span><span class="sxs-lookup"><span data-stu-id="2b202-144">Otherwise, the copied logins will not be recognized by the transferred database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b202-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="2b202-145">See Also</span></span>  
 <span data-ttu-id="2b202-146">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2b202-146">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="2b202-147">[Задачи служб Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="2b202-147">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="2b202-148">[Редактор задачи "Перемещение имен входа" &#40;общие&#41;страницы](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="2b202-148">[Transfer Logins Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="2b202-149">[Страница «Выражения»](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="2b202-149">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="2b202-150">[Диспетчер соединений SMO](connection-manager/smo-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="2b202-150">[SMO Connection Manager](connection-manager/smo-connection-manager.md) </span></span>  
 <span data-ttu-id="2b202-151">[Надежные пароли](../relational-databases/security/strong-passwords.md) </span><span class="sxs-lookup"><span data-stu-id="2b202-151">[Strong Passwords](../relational-databases/security/strong-passwords.md) </span></span>  
 [<span data-ttu-id="2b202-152">Вопросы безопасности при установке SQL Server</span><span class="sxs-lookup"><span data-stu-id="2b202-152">Security Considerations for a SQL Server Installation</span></span>](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
  
