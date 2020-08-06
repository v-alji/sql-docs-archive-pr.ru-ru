---
title: Добавление столбцов в таблицу (ядро СУБД) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- inserting columns
- columns [SQL Server], adding
- adding columns
ms.assetid: abeb8d52-d562-4e29-9e1e-2923ae874859
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7e9294de10be0df9ef470c75d0934e9f8787b55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664099"
---
# <a name="add-columns-to-a-table-database-engine"></a><span data-ttu-id="2f01e-102">Добавление столбцов в таблицу (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="2f01e-102">Add Columns to a Table (Database Engine)</span></span>
  <span data-ttu-id="2f01e-103">В данном разделе содержатся инструкции по добавлению новых столбцов в таблицу в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f01e-103">This topic describes how to add new columns to a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2f01e-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="2f01e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2f01e-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="2f01e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2f01e-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="2f01e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2f01e-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="2f01e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2f01e-108">**Вставка столбцов с помощью:**</span><span class="sxs-lookup"><span data-stu-id="2f01e-108">**To insert columns, using:**</span></span>  
  
     [<span data-ttu-id="2f01e-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2f01e-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2f01e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2f01e-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2f01e-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="2f01e-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2f01e-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="2f01e-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="2f01e-113">Использование инструкции ALTER TABLE для добавления столбцов в таблицу приводит к автоматическому добавлению этих столбцов в конец таблицы.</span><span class="sxs-lookup"><span data-stu-id="2f01e-113">Using the ALTER TABLE statement to add columns to a table automatically adds those columns to the end of the table.</span></span> <span data-ttu-id="2f01e-114">Если требуется, чтобы столбцы располагались в таблице в определенном порядке, воспользуйтесь [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f01e-114">If you want the columns in a specific order in the table, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2f01e-115">Однако помните, что это не рекомендуемый метод конструирования баз данных.</span><span class="sxs-lookup"><span data-stu-id="2f01e-115">However, note that this is not a database design best practice.</span></span> <span data-ttu-id="2f01e-116">Рекомендуется указывать порядок, в котором возвращаются столбцы, на уровне приложения и запроса.</span><span class="sxs-lookup"><span data-stu-id="2f01e-116">Best practice is to specify the order in which the columns are returned at the application and query level.</span></span> <span data-ttu-id="2f01e-117">Не следует предполагать, что SELECT \* будет возвращать все столбцы в ожидаемом порядке, основанном на порядке их определения в таблице.</span><span class="sxs-lookup"><span data-stu-id="2f01e-117">You should not rely on the use of SELECT \* to return all columns in an expected order based on the order in which they are defined in the table.</span></span> <span data-ttu-id="2f01e-118">Всегда указывайте столбцы в запросах и приложениях по именам в том порядке, в котором они должны следовать.</span><span class="sxs-lookup"><span data-stu-id="2f01e-118">Always specify the columns by name in your queries and applications in the order in which you would like them to appear.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2f01e-119">безопасность</span><span class="sxs-lookup"><span data-stu-id="2f01e-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2f01e-120">Permissions</span><span class="sxs-lookup"><span data-stu-id="2f01e-120">Permissions</span></span>  
 <span data-ttu-id="2f01e-121">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="2f01e-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2f01e-122">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2f01e-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-insert-columns-into-a-table-with-table-designer"></a><span data-ttu-id="2f01e-123">Вставка в таблицу столбцов с помощью конструктора таблиц</span><span class="sxs-lookup"><span data-stu-id="2f01e-123">To insert columns into a table with Table Designer</span></span>  
  
1.  <span data-ttu-id="2f01e-124">В **обозревателе объектов**щелкните правой кнопкой мыши таблицу, в которую необходимо добавить столбцы, и выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="2f01e-124">In **Object Explorer**, right-click the table to which you want to add columns and choose **Design**.</span></span>  
  
2.  <span data-ttu-id="2f01e-125">Щелкните первую пустую ячейку в столбце **Имя столбца** .</span><span class="sxs-lookup"><span data-stu-id="2f01e-125">Click in the first blank cell in the **Column Name** column.</span></span>  
  
3.  <span data-ttu-id="2f01e-126">Введите имя столбца в ячейку.</span><span class="sxs-lookup"><span data-stu-id="2f01e-126">Type the column name in the cell.</span></span> <span data-ttu-id="2f01e-127">Имя столбца — значение, которое необходимо указать.</span><span class="sxs-lookup"><span data-stu-id="2f01e-127">The column name is a required value.</span></span>  
  
4.  <span data-ttu-id="2f01e-128">Нажмите клавишу TAB, чтобы перейти к ячейке **Тип данных** и выбрать тип данных из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="2f01e-128">Press the TAB key to go to the **Data Type** cell and select a data type from the dropdown.</span></span> <span data-ttu-id="2f01e-129">Это также обязательно указываемое значение и если оно не будет установлено, тогда будет использоваться значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2f01e-129">This too is a required value, and will be assigned the default value if you don't choose one.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2f01e-130"> Значения по умолчанию можно установить или изменить в диалоговом окне **Параметры** в **Инструменты для баз данных**.</span><span class="sxs-lookup"><span data-stu-id="2f01e-130">You can change the default value in the **Options** dialog box under **Database Tools**.</span></span>  
  
5.  <span data-ttu-id="2f01e-131">Продолжайте определение других свойств столбца во вкладке **Свойства столбца** .</span><span class="sxs-lookup"><span data-stu-id="2f01e-131">Continue to define any other column properties in the **Column Properties** tab.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2f01e-132"> При создании нового столбца для свойств столбца устанавливаются значения по умолчанию, но их можно изменить во вкладке **Свойства столбца** .</span><span class="sxs-lookup"><span data-stu-id="2f01e-132">The default values for your column properties are added when you create a new column, but you can change them in the **Column Properties** tab.</span></span>  
  
6.  <span data-ttu-id="2f01e-133">По окончании добавления столбцов из меню **Файл** выберите пункт **Сохранить**_имя таблицы_.</span><span class="sxs-lookup"><span data-stu-id="2f01e-133">When you are finished adding columns, from the **File** menu, choose **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2f01e-134">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2f01e-134">Using Transact-SQL</span></span>  
  
#### <a name="to-insert-columns-into-a-table"></a><span data-ttu-id="2f01e-135">Вставка столбцов в таблицу</span><span class="sxs-lookup"><span data-stu-id="2f01e-135">To insert columns into a table</span></span>  
  
1.  <span data-ttu-id="2f01e-136">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f01e-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2f01e-137">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="2f01e-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2f01e-138">В следующем примере добавляются два столбца в таблицу `dbo.doc_exa`.</span><span class="sxs-lookup"><span data-stu-id="2f01e-138">The following example adds two columns to the table `dbo.doc_exa`.</span></span> <span data-ttu-id="2f01e-139">Скопируйте и вставьте следующий пример в окно запроса и нажмите кнопку **Выполнить**</span><span class="sxs-lookup"><span data-stu-id="2f01e-139">Copy and paste the following example into the query window and click **Execute**</span></span>  
  
```  
ALTER TABLE dbo.doc_exa ADD column_b VARCHAR(20) NULL, column_c INT NULL ;  
```  
  
##  <a name="for-more-information-see-alter-table-40transact-sql41"></a><a name="FollowUp"></a><span data-ttu-id="2f01e-140">Дополнительные сведения см. в разделе [ALTER table &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="2f01e-140">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span></span>  
  
  
