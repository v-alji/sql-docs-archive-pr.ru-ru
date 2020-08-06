---
title: Установка однопользовательского режима базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- single-user mode [SQL Server], database option
ms.assetid: fb5254eb-b635-4b39-8361-136fd36f2b1f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 16281b5fa7d4f6698bb6c498915bfa84779b3e14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728334"
---
# <a name="set-a-database-to-single-user-mode"></a><span data-ttu-id="6bafa-102">Установка однопользовательского режима базы данных</span><span class="sxs-lookup"><span data-stu-id="6bafa-102">Set a Database to Single-user Mode</span></span>
  <span data-ttu-id="6bafa-103">В этом разделе описывается, как установить однопользовательский режим в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6bafa-103">This topic describes how to set a user-defined database to single-user mode in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6bafa-104">Однопользовательский режим указывает, что одновременный доступ к базе данных получает только один пользователь. Это в основном используется для операций обслуживания.</span><span class="sxs-lookup"><span data-stu-id="6bafa-104">Single-user mode specifies that only one user at a time can access the database and is generally used for maintenance actions.</span></span>  
  
 <span data-ttu-id="6bafa-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="6bafa-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6bafa-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="6bafa-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6bafa-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="6bafa-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6bafa-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="6bafa-108">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="6bafa-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="6bafa-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6bafa-110">**Установка однопользовательского режима базы данных с помощью**</span><span class="sxs-lookup"><span data-stu-id="6bafa-110">**To set a database to single-user mode, using:**</span></span>  
  
     [<span data-ttu-id="6bafa-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6bafa-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6bafa-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6bafa-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6bafa-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="6bafa-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6bafa-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="6bafa-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6bafa-115">Если в процессе установки однопользовательского режима к базе данных подключены другие пользователи, то их подключения к базе данных будут закрыты без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="6bafa-115">If other users are connected to the database at the time that you set the database to single-user mode, their connections to the database will be closed without warning.</span></span>  
  
-   <span data-ttu-id="6bafa-116">База данных остается в однопользовательском режиме даже и в том случае, если пользователь, установивший этот параметр, отключился.</span><span class="sxs-lookup"><span data-stu-id="6bafa-116">The database remains in single-user mode even if the user that set the option logs off.</span></span> <span data-ttu-id="6bafa-117">В этот момент к базе данных могут подключаться и другие пользователи, но одновременно может быть подключен только один.</span><span class="sxs-lookup"><span data-stu-id="6bafa-117">At that point, a different user, but only one, can connect to the database.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="6bafa-118">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="6bafa-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="6bafa-119">Перед заданием параметра SINGLE_USER проверьте, чтобы параметру AUTO_UPDATE_STATISTICS_ASYNC было присвоено значение OFF.</span><span class="sxs-lookup"><span data-stu-id="6bafa-119">Before you set the database to SINGLE_USER, verify that the AUTO_UPDATE_STATISTICS_ASYNC option is set to OFF.</span></span> <span data-ttu-id="6bafa-120">Если этот параметр имеет значение ON, то фоновый поток, используемый для обновления статистики, соединится с базой данных и доступ к базе данных в однопользовательском режиме будет невозможен.</span><span class="sxs-lookup"><span data-stu-id="6bafa-120">When this option is set to ON, the background thread that is used to update statistics takes a connection against the database, and you will be unable to access the database in single-user mode.</span></span> <span data-ttu-id="6bafa-121">Дополнительные сведения см. в разделе [Параметры ALTER DATABASE SET (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="6bafa-121">For more information, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6bafa-122">безопасность</span><span class="sxs-lookup"><span data-stu-id="6bafa-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6bafa-123">Permissions</span><span class="sxs-lookup"><span data-stu-id="6bafa-123">Permissions</span></span>  
 <span data-ttu-id="6bafa-124">Необходимо разрешение ALTER на базу данных.</span><span class="sxs-lookup"><span data-stu-id="6bafa-124">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6bafa-125">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6bafa-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-a-database-to-single-user-mode"></a><span data-ttu-id="6bafa-126">Установка однопользовательского режима базы данных</span><span class="sxs-lookup"><span data-stu-id="6bafa-126">To set a database to single-user mode</span></span>  
  
1.  <span data-ttu-id="6bafa-127">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]и разверните его.</span><span class="sxs-lookup"><span data-stu-id="6bafa-127">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="6bafa-128">Щелкните правой кнопкой мыши базу данных, которую нужно изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="6bafa-128">Right-click the database to change, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="6bafa-129">В диалоговом окне **Свойства базы данных** выберите страницу **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="6bafa-129">In the **Database Properties** dialog box, click the **Options** page.</span></span>  
  
4.  <span data-ttu-id="6bafa-130">Для параметра **Ограничение доступа** выберите **Один**.</span><span class="sxs-lookup"><span data-stu-id="6bafa-130">From the **Restrict Access** option, select **Single**.</span></span>  
  
5.  <span data-ttu-id="6bafa-131">Если к базе данных подключены другие пользователи, то появится сообщение **Открытые соединения** .</span><span class="sxs-lookup"><span data-stu-id="6bafa-131">If other users are connected to the database, an **Open Connections** message will appear.</span></span> <span data-ttu-id="6bafa-132">Чтобы изменить свойство и закрыть все другие подключения, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="6bafa-132">To change the property and close all other connections, click **Yes**.</span></span>  
  
 <span data-ttu-id="6bafa-133">С помощью этой процедуры можно также установить режим одновременного или ограниченного доступа к базе данных.</span><span class="sxs-lookup"><span data-stu-id="6bafa-133">You can also set the database to Multiple or Restricted access by using this procedure.</span></span> <span data-ttu-id="6bafa-134">Дополнительные сведения о параметрах ограниченного доступа см. в разделе [Свойства базы данных (страница "Параметры")](database-properties-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="6bafa-134">For more information about the Restrict Access options, see [Database Properties &#40;Options Page&#41;](database-properties-options-page.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6bafa-135">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6bafa-135">Using Transact-SQL</span></span>  
  
#### <a name="to-set-a-database-to-single-user-mode"></a><span data-ttu-id="6bafa-136">Установка однопользовательского режима базы данных</span><span class="sxs-lookup"><span data-stu-id="6bafa-136">To set a database to single-user mode</span></span>  
  
1.  <span data-ttu-id="6bafa-137">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6bafa-137">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6bafa-138">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="6bafa-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6bafa-139">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="6bafa-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="6bafa-140">В этом примере база данных устанавливается в режим `SINGLE_USER` для получения монопольного доступа.</span><span class="sxs-lookup"><span data-stu-id="6bafa-140">This example sets the database to `SINGLE_USER` mode to obtain exclusive access.</span></span> <span data-ttu-id="6bafa-141">Затем состояние базы данных [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] устанавливается в `READ_ONLY` и возвращается доступ к базе данных всем пользователям. Параметр прекращения `WITH ROLLBACK IMMEDIATE` указывается в первой инструкции `ALTER DATABASE` .</span><span class="sxs-lookup"><span data-stu-id="6bafa-141">The example then sets the state of the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database to `READ_ONLY` and returns access to the database to all users.The termination option `WITH ROLLBACK IMMEDIATE` is specified in the first `ALTER DATABASE` statement.</span></span> <span data-ttu-id="6bafa-142">Произойдет откат всех незавершенных транзакций, а любые другие соединения с базой данных [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] будут немедленно разорваны.</span><span class="sxs-lookup"><span data-stu-id="6bafa-142">This will cause all incomplete transactions to be rolled back and any other connections to the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database to be immediately disconnected.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase8](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase8)]  
  
## <a name="see-also"></a><span data-ttu-id="6bafa-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="6bafa-143">See Also</span></span>  
 [<span data-ttu-id="6bafa-144">ALTER DATABASE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6bafa-144">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
