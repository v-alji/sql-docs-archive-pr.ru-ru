---
title: Сохранение плана выполнения в формате XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- XML query plans [SQL Server]
- opening execution plans
- XML Showplans [SQL Server]
- execution plans [SQL Server], saving
- saving execution plans
ms.assetid: c439e53b-56f3-4442-97c6-dabd48a203d8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 84ed341d186993ed77260e8361156b324c597839
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665996"
---
# <a name="save-an-execution-plan-in-xml-format"></a><span data-ttu-id="e7249-102">Сохранение плана выполнения в формате XML</span><span class="sxs-lookup"><span data-stu-id="e7249-102">Save an Execution Plan in XML Format</span></span>
  <span data-ttu-id="e7249-103">Используйте среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , чтобы сохранить планы выполнения в XML-файле и открыть их для просмотра.</span><span class="sxs-lookup"><span data-stu-id="e7249-103">Use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to save execution plans as an XML file, and to open them for viewing.</span></span>  
  
 <span data-ttu-id="e7249-104">Чтобы использовать функциональные возможности плана выполнения в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]или параметры XML Showplan SET, пользователи должны иметь соответствующие разрешения на выполнение запроса [!INCLUDE[tsql](../../includes/tsql-md.md)] , для которого формируется план выполнения, и им нужно предоставить разрешение SHOWPLAN для всех баз данных, на которые ссылается запрос.</span><span class="sxs-lookup"><span data-stu-id="e7249-104">To use the execution plan feature in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], or to use the XML Showplan SET options, users must have the appropriate permissions to execute the [!INCLUDE[tsql](../../includes/tsql-md.md)] query for which an execution plan is being generated, and they must be granted the SHOWPLAN permission for all databases referenced by the query.</span></span>  
  
### <a name="to-save-a-query-plan-by-using-the-xml-showplan-set-options"></a><span data-ttu-id="e7249-105">Сохранение плана запроса с помощью параметров XML Showplan SET</span><span class="sxs-lookup"><span data-stu-id="e7249-105">To save a query plan by using the XML Showplan SET options</span></span>  
  
1.  <span data-ttu-id="e7249-106">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] откройте редактор запросов и подключитесь к компоненту [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7249-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] open a query editor and connect to [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e7249-107">Включите SHOWPLAN_XML с помощью следующей инструкции:</span><span class="sxs-lookup"><span data-stu-id="e7249-107">Turn SHOWPLAN_XML on with the following statement:</span></span>  
  
    ```  
    SET SHOWPLAN_XML ON;  
    GO  
    ```  
  
     <span data-ttu-id="e7249-108">Для включения STATISTICS XML воспользуйтесь следующей инструкцией:</span><span class="sxs-lookup"><span data-stu-id="e7249-108">To turn STATISTICS XML on, use the following statement:</span></span>  
  
    ```  
    SET STATISTICS XML ON;  
    GO  
    ```  
  
     <span data-ttu-id="e7249-109">Инструкция SHOWPLAN_XML создает сведения о плане выполнения запроса во время компиляции, но не выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="e7249-109">SHOWPLAN_XML generates compile-time query execution plan information for a query, but does not execute the query.</span></span> <span data-ttu-id="e7249-110">Инструкция STATISTICS XML создает сведения о плане выполнения запроса во время выполнения и выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="e7249-110">STATISTICS XML generates run-time query execution plan information for a query, and executes the query.</span></span>  
  
3.  <span data-ttu-id="e7249-111">Выполните запрос.</span><span class="sxs-lookup"><span data-stu-id="e7249-111">Execute a query.</span></span> <span data-ttu-id="e7249-112">Пример</span><span class="sxs-lookup"><span data-stu-id="e7249-112">Example:</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SET SHOWPLAN_XML ON;  
    GO  
    -- Execute a query.  
    SELECT BusinessEntityID   
    FROM HumanResources.Employee  
    WHERE NationalIDNumber = '509647174';  
    GO  
    SET SHOWPLAN_XML OFF;  
    ```  
  
4.  <span data-ttu-id="e7249-113">На панели **Результаты** щелкните правой кнопкой мыши поле **Microsoft SQL Server XML Showplan** , содержащее план запроса, и выберите пункт **Сохранить результаты как**.</span><span class="sxs-lookup"><span data-stu-id="e7249-113">In the **Results** pane, right-click the **Microsoft SQL Server XML Showplan** that contains the query plan, and then click **Save Results As**.</span></span>  
  
5.  <span data-ttu-id="e7249-114">В диалоговом окне **Сохранить** \<Grid or Text> **Результаты** в окне **Сохранить как тип** нажмите **Все файлы (\*.\*)** .</span><span class="sxs-lookup"><span data-stu-id="e7249-114">In the **Save** \<Grid or Text> **Results** dialog box, in the **Save as type** box, click **All files (\*.\*)**.</span></span>  
  
6.  <span data-ttu-id="e7249-115">В поле **Имя файла** укажите имя в формате \<name**>.sqlplan\*\*, после чего нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e7249-115">In the **File name** box provide a name, in the format \<name**>.sqlplan\*\*, and then click **Save**.</span></span>  
  
### <a name="to-save-an-execution-plan-by-using-sql-server-management-studio-options"></a><span data-ttu-id="e7249-116">Сохранение плана выполнения с помощью параметров среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e7249-116">To save an execution plan by using SQL Server Management Studio options</span></span>  
  
1.  <span data-ttu-id="e7249-117">Сформируйте либо прогнозируемый, либо фактический план выполнения с помощью среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7249-117">Generate either an estimated execution plan or an actual execution plan by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="e7249-118">Дополнительные сведения см. в разделах [Отображение предполагаемого плана выполнения](display-the-estimated-execution-plan.md) или [Отображение фактического плана выполнения](display-an-actual-execution-plan.md).</span><span class="sxs-lookup"><span data-stu-id="e7249-118">For more information, see [Display the Estimated Execution Plan](display-the-estimated-execution-plan.md) or [Display an Actual Execution Plan](display-an-actual-execution-plan.md).</span></span>  
  
2.  <span data-ttu-id="e7249-119">На вкладке **План выполнения** панели результатов щелкните правой кнопкой мыши графический план выполнения и выберите **Сохранить план выполнения как**.</span><span class="sxs-lookup"><span data-stu-id="e7249-119">In the **Execution plan** tab of the results pane, right-click the graphical execution plan, and choose **Save Execution Plan As**.</span></span>  
  
     <span data-ttu-id="e7249-120">Как альтернативный вариант можно также выбрать **Сохранить план выполнения как** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="e7249-120">As an alternative, you can also choose **Save Execution Plan As** on the **File** menu.</span></span>  
  
3.  <span data-ttu-id="e7249-121">В диалоговом окне **Сохранение** убедитесь, что в поле **Тип файла** установлено значение **Файлы плана выполнения (\*.sqlplan)** .</span><span class="sxs-lookup"><span data-stu-id="e7249-121">In the **Save As** dialog box, make sure that the **Save as type** is set to **Execution Plan Files (\*.sqlplan)**.</span></span>  
  
4.  <span data-ttu-id="e7249-122">В поле **Имя файла** укажите имя в формате \<name**>.sqlplan\*\*, после чего нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e7249-122">In the **File name** box provide a name, in the format \<name**>.sqlplan\*\*, and then click **Save**.</span></span>  
  
### <a name="to-open-a-saved-xml-query-plan-in-sql-server-management-studio"></a><span data-ttu-id="e7249-123">Открытие сохраненного плана запроса в формате XML в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e7249-123">To open a saved XML query plan in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="e7249-124">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]в меню **Файл** выберите **Открыть**, а затем нажмите **Файл**.</span><span class="sxs-lookup"><span data-stu-id="e7249-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **File** menu, choose **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="e7249-125">В диалоговом окне **Открытие файла** установите в поле **Файлы типа** значение **Файлы плана выполнения (\*.sqlplan)** , чтобы получить отфильтрованный список сохраненных файлов XML с планами запросов.</span><span class="sxs-lookup"><span data-stu-id="e7249-125">In the **Open File** dialog box, set **Files of type** to **Execution Plan Files (\*.sqlplan)** to produce a filtered list of saved XML query plan files.</span></span>  
  
3.  <span data-ttu-id="e7249-126">Выберите файл плана запроса XML, который нужно просмотреть, и нажмите **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="e7249-126">Select the XML query plan file that you want to view, and click **Open**.</span></span>  
  
     <span data-ttu-id="e7249-127">Также можно дважды щелкнуть файл с расширением **sqlplan**в проводнике Windows.</span><span class="sxs-lookup"><span data-stu-id="e7249-127">As an alternative, in Windows Explorer, double-click a file with extension **.sqlplan**.</span></span> <span data-ttu-id="e7249-128">План откроется в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7249-128">The plan opens in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7249-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="e7249-129">See Also</span></span>  
 <span data-ttu-id="e7249-130">[SET SHOWPLAN_XML (Transact-SQL)](/sql/t-sql/statements/set-showplan-xml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e7249-130">[SET SHOWPLAN_XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-showplan-xml-transact-sql) </span></span>  
 [<span data-ttu-id="e7249-131">SET STATISTICS XML (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e7249-131">SET STATISTICS XML &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-statistics-xml-transact-sql)  
  
  
