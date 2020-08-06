---
title: Переименование базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], renaming
- renaming databases
ms.assetid: 44c69d35-abcb-4da3-9370-5e0bc9a28496
author: stevestein
ms.author: sstein
ms.openlocfilehash: dd25a78e3d3b9be2e7191ce6ed3d6bdcbb0f9606
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658809"
---
# <a name="rename-a-database"></a><span data-ttu-id="b0ddc-102">Переименование базы данных</span><span class="sxs-lookup"><span data-stu-id="b0ddc-102">Rename a Database</span></span>
  <span data-ttu-id="b0ddc-103">В этом подразделе описывается, как переименовать пользовательскую базу данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0ddc-103">This topic describes how to rename a user-defined database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b0ddc-104">Имя базы данных может содержать все символы, соответствующие правилам для идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="b0ddc-104">The name of the database can include any characters that follow the rules for identifiers.</span></span>  
  
 <span data-ttu-id="b0ddc-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="b0ddc-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b0ddc-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="b0ddc-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b0ddc-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b0ddc-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b0ddc-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="b0ddc-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b0ddc-109">**Переименование базы данных с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="b0ddc-109">**To rename a database, using:**</span></span>  
  
     [<span data-ttu-id="b0ddc-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b0ddc-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b0ddc-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b0ddc-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="b0ddc-112">**Дальнейшие действия.**  [После переименования базы данных](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="b0ddc-112">**Follow Up:**  [After renaming a database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b0ddc-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="b0ddc-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b0ddc-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b0ddc-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b0ddc-115">Системные базы данных не могут быть переименованы.</span><span class="sxs-lookup"><span data-stu-id="b0ddc-115">System databases cannot be renamed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b0ddc-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="b0ddc-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b0ddc-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="b0ddc-117">Permissions</span></span>  
 <span data-ttu-id="b0ddc-118">Необходимо разрешение ALTER на базу данных.</span><span class="sxs-lookup"><span data-stu-id="b0ddc-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b0ddc-119">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b0ddc-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-database"></a><span data-ttu-id="b0ddc-120">Переименование базы данных</span><span class="sxs-lookup"><span data-stu-id="b0ddc-120">To rename a database</span></span>  
  
1.  <span data-ttu-id="b0ddc-121">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]и разверните его.</span><span class="sxs-lookup"><span data-stu-id="b0ddc-121">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="b0ddc-122">Убедитесь в том, что никто не использует эту базу данных, а затем [переведите ее в однопользовательский режим работы](set-a-database-to-single-user-mode.md).</span><span class="sxs-lookup"><span data-stu-id="b0ddc-122">Make sure that no one is using the database, and then [set the database to single-user mode](set-a-database-to-single-user-mode.md).</span></span>  
  
3.  <span data-ttu-id="b0ddc-123">Раскройте узел **Базы данных**, щелкните правой кнопкой мыши базу данных, которую необходимо переименовать, а затем выберите пункт **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="b0ddc-123">Expand **Databases**, right-click the database to rename, and then click **Rename**.</span></span>  
  
4.  <span data-ttu-id="b0ddc-124">Введите новое имя базы данных и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b0ddc-124">Enter the new database name, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b0ddc-125">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b0ddc-125">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-database"></a><span data-ttu-id="b0ddc-126">Переименование базы данных</span><span class="sxs-lookup"><span data-stu-id="b0ddc-126">To rename a database</span></span>  
  
1.  <span data-ttu-id="b0ddc-127">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0ddc-127">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b0ddc-128">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b0ddc-128">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b0ddc-129">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="b0ddc-129">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b0ddc-130">В этом примере имя базы данных `AdventureWorks2012` изменяется на `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="b0ddc-130">This example changes the name of the `AdventureWorks2012` database to `Northwind`.</span></span>  
  
```sql  
USE master;  
GO  
ALTER DATABASE AdventureWorks2012  
Modify Name = Northwind ;  
GO  
```  
  
###  <a name="TsqlExample"></a>   
##  <a name="follow-up-after-renaming-a-database"></a><a name="FollowUp"></a> <span data-ttu-id="b0ddc-131">Дальнейшие действия. После переименования базы данных</span><span class="sxs-lookup"><span data-stu-id="b0ddc-131">Follow Up: After renaming a database</span></span>  
 <span data-ttu-id="b0ddc-132">Создавайте резервную копию базы данных **master** после переименования любой базы данных.</span><span class="sxs-lookup"><span data-stu-id="b0ddc-132">Back up the **master** database after you rename any database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0ddc-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="b0ddc-133">See Also</span></span>  
 <span data-ttu-id="b0ddc-134">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b0ddc-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="b0ddc-135">Идентификаторы баз данных</span><span class="sxs-lookup"><span data-stu-id="b0ddc-135">Database Identifiers</span></span>](database-identifiers.md)  
  
  
