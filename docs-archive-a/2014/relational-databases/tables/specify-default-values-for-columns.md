---
title: Указание значений по умолчанию для столбцов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], defaults
- default values
ms.assetid: 64514aed-b846-407b-992e-cf813f9a1a91
author: stevestein
ms.author: sstein
ms.openlocfilehash: 650347c29e1175c5a1fe646fc079478520dc8c6d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666975"
---
# <a name="specify-default-values-for-columns"></a><span data-ttu-id="a24e8-102">Указание значений по умолчанию для столбца</span><span class="sxs-lookup"><span data-stu-id="a24e8-102">Specify Default Values for Columns</span></span>
  <span data-ttu-id="a24e8-103">Можно указать значение по умолчанию, которое будет введено в столбец в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , при помощи [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a24e8-103">You can specify a default value that will be entered in the column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a24e8-104">Если значение по умолчанию не задано и пользователь оставляет столбец пустым, происходит следующее:</span><span class="sxs-lookup"><span data-stu-id="a24e8-104">If you do not assign a default value and the user leaves the column blank, then:</span></span>  
  
-   <span data-ttu-id="a24e8-105">если активирована поддержка значений NULL, в столбец вставляется значение NULL;</span><span class="sxs-lookup"><span data-stu-id="a24e8-105">If you set the option to allow null values, NULL will be inserted into the column.</span></span>  
  
-   <span data-ttu-id="a24e8-106">если поддержка значений NULL не активирована, столбец остается пустым, но пользователь не сможет сохранить строку, пока не предоставит какое-либо значение.</span><span class="sxs-lookup"><span data-stu-id="a24e8-106">If you do not set the option to allow null values, the column will remain blank, but the user will not be able to save the row until they supply a value for the column.</span></span>  
  
 <span data-ttu-id="a24e8-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="a24e8-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a24e8-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="a24e8-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a24e8-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="a24e8-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a24e8-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a24e8-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a24e8-111">**Задание значения по умолчанию с использованием:**</span><span class="sxs-lookup"><span data-stu-id="a24e8-111">**To specify a default value, using:**</span></span>  
  
     [<span data-ttu-id="a24e8-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a24e8-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a24e8-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a24e8-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a24e8-114">Перед началом</span><span class="sxs-lookup"><span data-stu-id="a24e8-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a24e8-115">Ограничения</span><span class="sxs-lookup"><span data-stu-id="a24e8-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="a24e8-116">Если данные, введенные в поле **Значение по умолчанию** , заменяют связанное со столбцом значение по умолчанию (которое отображается без скобок), то будет предложено отменить привязку значения по умолчанию и заменить его новым значением.</span><span class="sxs-lookup"><span data-stu-id="a24e8-116">If your entry in the **Default Value** field replaces a bound default (which is shown without parentheses), you will be prompted to unbind the default and replace it with your new default.</span></span>  
  
-   <span data-ttu-id="a24e8-117">При вводе текстовых строк заключайте их в одинарные кавычки ('); не используйте двойные кавычки ("), потому что они зарезервированы для идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="a24e8-117">To enter a text string, enclose the value in single quotation marks ('); do not use double quotation marks (") because they are reserved for quoted identifiers.</span></span>  
  
-   <span data-ttu-id="a24e8-118">Чтобы задать численное значение по умолчанию, введите число без одинарных кавычек.</span><span class="sxs-lookup"><span data-stu-id="a24e8-118">To enter a numeric default, enter the number without quotation marks around it.</span></span>  
  
-   <span data-ttu-id="a24e8-119">Чтобы задать объект или функцию, введите имя объекта или функции без двойных кавычек.</span><span class="sxs-lookup"><span data-stu-id="a24e8-119">To enter an object/function, enter the name of the object/function without quotation marks around it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a24e8-120">безопасность</span><span class="sxs-lookup"><span data-stu-id="a24e8-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a24e8-121">Permissions</span><span class="sxs-lookup"><span data-stu-id="a24e8-121">Permissions</span></span>  
 <span data-ttu-id="a24e8-122">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="a24e8-122">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a24e8-123">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a24e8-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-default-value-for-a-column"></a><span data-ttu-id="a24e8-124">Указание для столбца значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a24e8-124">To specify a default value for a column</span></span>  
  
1.  <span data-ttu-id="a24e8-125">В **Обозревателе объектов**щелкните правой кнопкой мыши таблицу со столбцами, масштаб которых необходимо изменить, и выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="a24e8-125">In **Object Explorer**, right-click the table with columns for which you want to change the scale and click **Design**.</span></span>  
  
2.  <span data-ttu-id="a24e8-126">Выберите столбец, для которого нужно задать значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a24e8-126">Select the column for which you want to specify a default value.</span></span>  
  
3.  <span data-ttu-id="a24e8-127">На вкладке **Свойства столбца** введите новое значение по умолчанию в свойстве **Значение по умолчанию или привязка** .</span><span class="sxs-lookup"><span data-stu-id="a24e8-127">In the **Column Properties** tab, enter the new default value in the **Default Value or Binding** property.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a24e8-128">Чтобы задать численное значение по умолчанию, введите число.</span><span class="sxs-lookup"><span data-stu-id="a24e8-128">To enter a numeric default value, enter the number.</span></span> <span data-ttu-id="a24e8-129">В случае объекта или функции нужно ввести его или ее имя.</span><span class="sxs-lookup"><span data-stu-id="a24e8-129">For an object or function enter its name.</span></span> <span data-ttu-id="a24e8-130">Чтобы задать алфавитно-цифровое значение по умолчанию, введите его, заключив в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="a24e8-130">For an alphanumeric default enter the value inside single quotes.</span></span>  
  
4.  <span data-ttu-id="a24e8-131">В меню **Файл** выберите команду **Сохранить**_имя_таблицы_.</span><span class="sxs-lookup"><span data-stu-id="a24e8-131">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a24e8-132">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a24e8-132">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-default-value-for-a-column"></a><span data-ttu-id="a24e8-133">Указание для столбца значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a24e8-133">To specify a default value for a column</span></span>  
  
1.  <span data-ttu-id="a24e8-134">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a24e8-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a24e8-135">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="a24e8-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a24e8-136">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a24e8-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    CREATE TABLE dbo.doc_exz ( column_a INT, column_b INT) ;  
    GO  
    INSERT INTO dbo.doc_exz (column_a)VALUES ( 7 ) ;  
    GO  
    ALTER TABLE dbo.doc_exz  
    ADD CONSTRAINT col_b_def  
    DEFAULT 50 FOR column_b ;  
    GO  
  
    ```  
  
 <span data-ttu-id="a24e8-137">Дополнительные сведения см. в разделе [ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a24e8-137">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
