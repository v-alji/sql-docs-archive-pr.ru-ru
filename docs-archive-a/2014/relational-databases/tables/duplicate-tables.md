---
title: Дублирование таблиц | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- copying tables
- tables [SQL Server], duplicating
- duplicating tables
- table copying [SQL Server]
ms.assetid: c6b07423-d1e5-4e5e-8681-5088921f5df3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 793a38416f86a5b43a3e3bb2420127d7acf2af1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657630"
---
# <a name="duplicate-tables"></a><span data-ttu-id="a8945-102">Дублирование таблиц</span><span class="sxs-lookup"><span data-stu-id="a8945-102">Duplicate Tables</span></span>
  <span data-ttu-id="a8945-103">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно создать копию существующей таблицы с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] , создав новую таблицу и скопировав в нее сведения о столбцах из существующей таблицы.</span><span class="sxs-lookup"><span data-stu-id="a8945-103">You can duplicate an existing table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] by creating a new table and then copying column information from an existing table.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a8945-104">Эта операция дублирует только структуру таблицы. При этом не происходит дублирования строк таблицы.</span><span class="sxs-lookup"><span data-stu-id="a8945-104">This operation duplicates only the structure of a table; it does not duplicate any table rows.</span></span>  
  
 <span data-ttu-id="a8945-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="a8945-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a8945-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="a8945-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a8945-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a8945-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a8945-108">**Дублирование таблицы с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="a8945-108">**To duplicate a table, using:**</span></span>  
  
     [<span data-ttu-id="a8945-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a8945-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a8945-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a8945-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a8945-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="a8945-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a8945-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="a8945-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a8945-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="a8945-113">Permissions</span></span>  
 <span data-ttu-id="a8945-114">Требуется разрешение CREATE TABLE в целевой базе данных.</span><span class="sxs-lookup"><span data-stu-id="a8945-114">Requires CREATE TABLE permission in the destination database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a8945-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a8945-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-duplicate-a-table"></a><span data-ttu-id="a8945-116">Дублирование таблицы</span><span class="sxs-lookup"><span data-stu-id="a8945-116">To duplicate a table</span></span>  
  
1.  <span data-ttu-id="a8945-117">Убедитесь, что есть подключение к базе данных, в которой нужно создать таблицу, и эта база данных выбрана в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="a8945-117">Make sure you are connected to the database in which you want to create the table and that the database is selected in Object Explorer.</span></span>  
  
2.  <span data-ttu-id="a8945-118">В обозревателе объектов щелкните правой кнопкой мыши пункт **Таблицы** , а затем выберите **Создать таблицу**.</span><span class="sxs-lookup"><span data-stu-id="a8945-118">In Object Explorer, right-click **Tables** and click **New Table**.</span></span>  
  
3.  <span data-ttu-id="a8945-119">В обозревателе объектов щелкните правой кнопкой мыши таблицу, которую нужно скопировать, и выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="a8945-119">In Object Explorer right-click the table you want to copy and click **Design**.</span></span>  
  
4.  <span data-ttu-id="a8945-120">Выделите столбец из существующей таблицы и в меню **Правка** выберите **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="a8945-120">Select the columns in the existing table and, from the **Edit** menu, click **Copy**.</span></span>  
  
5.  <span data-ttu-id="a8945-121">Перейдите в новую таблицу и выберите первую строку.</span><span class="sxs-lookup"><span data-stu-id="a8945-121">Switch back to the new table and select the first row.</span></span>  
  
6.  <span data-ttu-id="a8945-122">В меню **Правка** выберите **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="a8945-122">From the **Edit** menu, click **Paste**.</span></span>  
  
7.  <span data-ttu-id="a8945-123">В меню **Файл** выберите пункт **Сохранить**_table name_.</span><span class="sxs-lookup"><span data-stu-id="a8945-123">From the **File** menu, click **Save**_table name_.</span></span>  
  
8.  <span data-ttu-id="a8945-124">В диалоговом окне **Выбор имени** введите имя новой таблицы и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a8945-124">In the **Choose Name** dialog box, type a name for the new table and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a8945-125">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a8945-125">Using Transact-SQL</span></span>  
  
#### <a name="to-duplicate-a-table-in-query-editor"></a><span data-ttu-id="a8945-126">Дублирование таблицы в редакторе запросов</span><span class="sxs-lookup"><span data-stu-id="a8945-126">To duplicate a table in Query Editor</span></span>  
  
1.  <span data-ttu-id="a8945-127">Убедитесь, что есть подключение к базе данных, в которой нужно создать таблицу, и эта база данных выбрана в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="a8945-127">Make sure you are connected to the database in which you want to create the table and that the database is selected in Object Explorer.</span></span>  
  
2.  <span data-ttu-id="a8945-128">Щелкните правой кнопкой таблицу, копию которой необходимо создать, выберите команду **Создать скрипт таблицы как**, укажите **CREATE для**и выберите вариант **Создать окно редактора запросов**.</span><span class="sxs-lookup"><span data-stu-id="a8945-128">Right-click the table you wish to duplicate, point to **Script Table as**, then point to **CREATE to**, and then select **New Query Editor Window**.</span></span>  
  
3.  <span data-ttu-id="a8945-129">Измените имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="a8945-129">Change the name of the table.</span></span>  
  
4.  <span data-ttu-id="a8945-130">Удалите все столбцы, которые не требуются в новой таблице.</span><span class="sxs-lookup"><span data-stu-id="a8945-130">Remove any columns that are not needed in the new table.</span></span>  
  
5.  <span data-ttu-id="a8945-131">Нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a8945-131">Click **Execute**.</span></span>  
  
  
