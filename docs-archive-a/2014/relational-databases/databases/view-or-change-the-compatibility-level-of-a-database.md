---
title: Просмотр или изменение уровня совместимости базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- compatibility levels [SQL Server], viewing
- compatibility [SQL Server], databases
- compatibility levels [SQL Server], changing
ms.assetid: 579867ec-57cb-4cb8-af35-9688c1e9e15d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35cf7af50eba333440c42a1bac428df1fff156b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749979"
---
# <a name="view-or-change-the-compatibility-level-of-a-database"></a><span data-ttu-id="2f0a4-102">Просмотр или изменение уровня совместимости базы данных</span><span class="sxs-lookup"><span data-stu-id="2f0a4-102">View or Change the Compatibility Level of a Database</span></span>
  <span data-ttu-id="2f0a4-103">В этом разделе описывается просмотр и изменение уровня совместимости базы данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f0a4-103">This topic describes how to view or change the compatibility level of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2f0a4-104">Перед изменением уровня совместимости базы данных проанализируйте, как это повлияет на имеющиеся приложения.</span><span class="sxs-lookup"><span data-stu-id="2f0a4-104">Before you change the compatibility level of a database, you should understand the impact of the change on your applications.</span></span> <span data-ttu-id="2f0a4-105">Дополнительные сведения см. в разделе [Уровень совместимости инструкции ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span><span class="sxs-lookup"><span data-stu-id="2f0a4-105">For more information, see [ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span></span>  
  
 <span data-ttu-id="2f0a4-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="2f0a4-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2f0a4-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="2f0a4-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2f0a4-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="2f0a4-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2f0a4-109">**Просмотр или изменение уровня совместимости базы данных с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="2f0a4-109">**To view or change the compatibility level of a database, using:**</span></span>  
  
     [<span data-ttu-id="2f0a4-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2f0a4-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2f0a4-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2f0a4-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2f0a4-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="2f0a4-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2f0a4-113">безопасность</span><span class="sxs-lookup"><span data-stu-id="2f0a4-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2f0a4-114">Permissions</span><span class="sxs-lookup"><span data-stu-id="2f0a4-114">Permissions</span></span>  
 <span data-ttu-id="2f0a4-115">Необходимо разрешение ALTER на базу данных.</span><span class="sxs-lookup"><span data-stu-id="2f0a4-115">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2f0a4-116">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2f0a4-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-compatibility-level-of-a-database"></a><span data-ttu-id="2f0a4-117">Просмотр или изменение уровня совместимости базы данных</span><span class="sxs-lookup"><span data-stu-id="2f0a4-117">To view or change the compatibility level of a database</span></span>  
  
1.  <span data-ttu-id="2f0a4-118">После соединения с соответствующим экземпляром [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]в обозревателе объектов нажмите имя сервера.</span><span class="sxs-lookup"><span data-stu-id="2f0a4-118">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name.</span></span>  
  
2.  <span data-ttu-id="2f0a4-119">Раскройте узел **Базы данных**и в зависимости от типа восстанавливаемой базы данных выберите пользовательскую базу данных или раскройте узел **Системные базы данных** и выберите системную базу данных.</span><span class="sxs-lookup"><span data-stu-id="2f0a4-119">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="2f0a4-120">Щелкните правой кнопкой мыши базу данных, а затем выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="2f0a4-120">Right-click the database, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="2f0a4-121">Откроется диалоговое окно **Свойства базы данных** .</span><span class="sxs-lookup"><span data-stu-id="2f0a4-121">The **Database Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="2f0a4-122">На панели **Выбор страницы** щелкните **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="2f0a4-122">In the **Select a page** pane, click **Options**.</span></span>  
  
     <span data-ttu-id="2f0a4-123">Текущий уровень совместимости будет указан в списке **Уровень совместимости** .</span><span class="sxs-lookup"><span data-stu-id="2f0a4-123">The current compatibility level is displayed in the **Compatibility level** list box.</span></span>  
  
5.  <span data-ttu-id="2f0a4-124">Чтобы изменить уровень совместимости, выберите в списке другой параметр.</span><span class="sxs-lookup"><span data-stu-id="2f0a4-124">To change the compatibility level, select a different option from the list.</span></span> <span data-ttu-id="2f0a4-125">Доступны следующие значения: **SQL Server 2008 (100)**, **SQL Server 2012 (110)** и **SQL Server 2014 (120)**.</span><span class="sxs-lookup"><span data-stu-id="2f0a4-125">The choices are **SQL Server 2008 (100)**, **SQL Server 2012 (110)**, or **SQL Server 2014 (120)**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2f0a4-126">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2f0a4-126">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-compatibility-level-of-a-database"></a><span data-ttu-id="2f0a4-127">Просмотр уровня совместимости базы данных</span><span class="sxs-lookup"><span data-stu-id="2f0a4-127">To view the compatibility level of a database</span></span>  
  
1.  <span data-ttu-id="2f0a4-128">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f0a4-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2f0a4-129">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="2f0a4-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2f0a4-130">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2f0a4-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2f0a4-131">В этом примере возвращается уровень совместимости базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f0a4-131">This example returns the compatibility level of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT compatibility_level  
FROM sys.databases WHERE name = 'AdventureWorks2012';  
GO  
  
```  
  
#### <a name="to-change-the-compatibility-level-of-a-database"></a><span data-ttu-id="2f0a4-132">Изменение уровня совместимости базы данных</span><span class="sxs-lookup"><span data-stu-id="2f0a4-132">To change the compatibility level of a database</span></span>  
  
1.  <span data-ttu-id="2f0a4-133">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f0a4-133">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2f0a4-134">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="2f0a4-134">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2f0a4-135">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2f0a4-135">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2f0a4-136">В этом примере изменяется уровень совместимости [!INCLUDE[ssSampleDBobject](../../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f0a4-136">This example changes the compatibility level of the [!INCLUDE[ssSampleDBobject](../../includes/sssql14-md.md)].</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012  
SET COMPATIBILITY_LEVEL = 120;  
GO  
```  
  
  
