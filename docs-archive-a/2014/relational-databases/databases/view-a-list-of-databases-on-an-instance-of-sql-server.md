---
title: Просмотр списка баз данных в экземпляре SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- current databases
- databases currently on server [SQL Server]
- database list [SQL Server]
- viewing database list
- displaying database list
- databases [SQL Server], viewing
- servers [SQL Server], databases listed on
- listing databases
ms.assetid: 7ee7a789-db36-4be9-8a0e-0362a1e152dd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 47283fa9065a0b9d6238dab804094d9a65d17897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749971"
---
# <a name="view-a-list-of-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="57b8b-102">Просмотр списка баз данных в экземпляре SQL Server</span><span class="sxs-lookup"><span data-stu-id="57b8b-102">View a List of Databases on an Instance of SQL Server</span></span>
  <span data-ttu-id="57b8b-103">В этой теме описывается, как просмотреть список баз данных в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57b8b-103">This topic describes how to view a list of databases on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="57b8b-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="57b8b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="57b8b-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="57b8b-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="57b8b-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="57b8b-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="57b8b-107">**Просмотр списка баз данных в экземпляре SQL Server выполняется при помощи следующих средств.**</span><span class="sxs-lookup"><span data-stu-id="57b8b-107">**To view a list of databases on an instance of SQL Server, using:**</span></span>  
  
     [<span data-ttu-id="57b8b-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="57b8b-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="57b8b-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="57b8b-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="57b8b-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="57b8b-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="57b8b-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="57b8b-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="57b8b-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="57b8b-112">Permissions</span></span>  
 <span data-ttu-id="57b8b-113">Если участник, вызывающий представление каталога **sys.databases** , не является владельцем базы данных, а база данных не является базой данных **master** или **tempdb**, минимально необходимыми разрешениями для просмотра соответствующей строки являются разрешения уровня сервера ALTER ANY DATABASE или VIEW ANY DATABASE, или разрешение CREATE DATABASE в базе данных **master** .</span><span class="sxs-lookup"><span data-stu-id="57b8b-113">If the caller of **sys.databases** is not the owner of the database and the database is not **master** or **tempdb**, the minimum permissions required to see the corresponding row are ALTER ANY DATABASE or VIEW ANY DATABASE server-level permission, or CREATE DATABASE permission in the **master** database.</span></span> <span data-ttu-id="57b8b-114">Узнать базу данных, к которой подключен участник, можно в представлении каталога **sys.databases**.</span><span class="sxs-lookup"><span data-stu-id="57b8b-114">The database to which the caller is connected can always be viewed in **sys.databases**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="57b8b-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="57b8b-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-a-list-of-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="57b8b-116">Просмотр списка баз данных в экземпляре SQL Server</span><span class="sxs-lookup"><span data-stu-id="57b8b-116">To view a list of databases on an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="57b8b-117">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]и разверните его.</span><span class="sxs-lookup"><span data-stu-id="57b8b-117">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="57b8b-118">Для просмотра списка всех баз данных в экземпляре разверните список **Базы данных**.</span><span class="sxs-lookup"><span data-stu-id="57b8b-118">To see a list of all databases on the instance, expand **Databases**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="57b8b-119">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="57b8b-119">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-list-of-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="57b8b-120">Просмотр списка баз данных в экземпляре SQL Server</span><span class="sxs-lookup"><span data-stu-id="57b8b-120">To view a list of databases on an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="57b8b-121">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57b8b-121">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="57b8b-122">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="57b8b-122">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="57b8b-123">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="57b8b-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="57b8b-124">Этот пример возвращает список баз данных, размещенных в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57b8b-124">This example returns a list of databases on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="57b8b-125">Список содержит имена баз данных, их идентификаторы и даты создания.</span><span class="sxs-lookup"><span data-stu-id="57b8b-125">The list includes the names of the databases, their database IDs, and the dates when the databases were created.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT name, database_id, create_date  
FROM sys.databases ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="57b8b-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="57b8b-126">See Also</span></span>  
 <span data-ttu-id="57b8b-127">[Представления каталогов баз данных и файлов (Transact-SQL)](/sql/relational-databases/system-catalog-views/databases-and-files-catalog-views-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="57b8b-127">[Databases and Files Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/databases-and-files-catalog-views-transact-sql) </span></span>  
 [<span data-ttu-id="57b8b-128">sys.databases (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="57b8b-128">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
