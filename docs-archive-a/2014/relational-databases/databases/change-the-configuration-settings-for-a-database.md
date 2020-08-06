---
title: Изменение настроек конфигурации базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- database configuration [SQL Server]
- configuration options [SQL Server], databases
- modifying database configuration settings
ms.assetid: c29c3385-5043-400f-bb4e-044a4c9a9a4b
author: stevestein
ms.author: sstein
ms.openlocfilehash: f9edecefae5154bb66a65e38724d9e77a94fdbb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751128"
---
# <a name="change-the-configuration-settings-for-a-database"></a><span data-ttu-id="55c8a-102">Изменение настроек конфигурации базы данных</span><span class="sxs-lookup"><span data-stu-id="55c8a-102">Change the Configuration Settings for a Database</span></span>
  <span data-ttu-id="55c8a-103">В этом разделе описывается изменение параметров уровня базы данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55c8a-103">This topic describes how to change database-level options in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="55c8a-104">Эти параметры уникальны для каждой базы данных и не влияют на другие базы данных.</span><span class="sxs-lookup"><span data-stu-id="55c8a-104">These options are unique to each database and do not affect other databases.</span></span>  
  
 <span data-ttu-id="55c8a-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="55c8a-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="55c8a-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="55c8a-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="55c8a-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="55c8a-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="55c8a-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="55c8a-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="55c8a-109">**Изменение настроек параметров для базы данных с помощью различных средств.**</span><span class="sxs-lookup"><span data-stu-id="55c8a-109">**To change the option settings for a database, using:**</span></span>  
  
     [<span data-ttu-id="55c8a-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="55c8a-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="55c8a-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="55c8a-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="55c8a-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="55c8a-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="55c8a-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="55c8a-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="55c8a-114">Только системный администратор, владелец базы данных, члены предопределенной роли сервера **sysadmin** и **dbcreator** и предопределенной роли базы данных **db_owner** могут изменять эти параметры.</span><span class="sxs-lookup"><span data-stu-id="55c8a-114">Only the system administrator, database owner, members of the **sysadmin** and **dbcreator** fixed server roles and **db_owner** fixed database roles can modify these options.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="55c8a-115">безопасность</span><span class="sxs-lookup"><span data-stu-id="55c8a-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="55c8a-116">Permissions</span><span class="sxs-lookup"><span data-stu-id="55c8a-116">Permissions</span></span>  
 <span data-ttu-id="55c8a-117">Необходимо разрешение ALTER на базу данных.</span><span class="sxs-lookup"><span data-stu-id="55c8a-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="55c8a-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="55c8a-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-option-settings-for-a-database"></a><span data-ttu-id="55c8a-119">Изменение настроек параметров для базы данных</span><span class="sxs-lookup"><span data-stu-id="55c8a-119">To change the option settings for a database</span></span>  
  
1.  <span data-ttu-id="55c8a-120">В обозревателе объектов подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , разверните сервер, разверните узел **Базы данных**, щелкните правой кнопкой мыши базу данных и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="55c8a-120">In Object Explorer, connect to a [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance, expand the server, expand **Databases**, right-click a database, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="55c8a-121">В диалоговом окне **Свойства базы данных** щелкните **Параметры** для обращения к большинству настроек конфигурации.</span><span class="sxs-lookup"><span data-stu-id="55c8a-121">In the **Database Properties** dialog box, click **Options** to access most of the configuration settings.</span></span> <span data-ttu-id="55c8a-122">Конфигурации файла и файловой группы, зеркального отображения и доставки журналов находятся на соответствующих им страницах.</span><span class="sxs-lookup"><span data-stu-id="55c8a-122">File and filegroup configurations, mirroring and log shipping are on their respective pages.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="55c8a-123">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="55c8a-123">Using Transact-SQL</span></span>  
  
#### <a name="to-change-the-option-settings-for-a-database"></a><span data-ttu-id="55c8a-124">Изменение настроек параметров для базы данных</span><span class="sxs-lookup"><span data-stu-id="55c8a-124">To change the option settings for a database</span></span>  
  
1.  <span data-ttu-id="55c8a-125">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55c8a-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="55c8a-126">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="55c8a-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="55c8a-127">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="55c8a-127">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="55c8a-128">В этом примере задается модель восстановления и параметры проверки страницы данных для образца базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="55c8a-128">This example sets the recovery model and data page verification options for the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase7](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase7)]  
  
 <span data-ttu-id="55c8a-129">Дополнительные сведения см. в статье [Параметры ALTER DATABASE SET (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="55c8a-129">For more examples, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c8a-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="55c8a-130">See Also</span></span>  
 <span data-ttu-id="55c8a-131">[Уровень совместимости инструкции ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span><span class="sxs-lookup"><span data-stu-id="55c8a-131">[ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span></span>  
 <span data-ttu-id="55c8a-132">[Зеркальное отображение базы данных ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="55c8a-132">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="55c8a-133">[ALTER DATABASE SET HADR (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span><span class="sxs-lookup"><span data-stu-id="55c8a-133">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span></span>  
 <span data-ttu-id="55c8a-134">[Переименование базы данных](rename-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="55c8a-134">[Rename a Database](rename-a-database.md) </span></span>  
 [<span data-ttu-id="55c8a-135">Сжатие базы данных</span><span class="sxs-lookup"><span data-stu-id="55c8a-135">Shrink a Database</span></span>](shrink-a-database.md)  
  
  
