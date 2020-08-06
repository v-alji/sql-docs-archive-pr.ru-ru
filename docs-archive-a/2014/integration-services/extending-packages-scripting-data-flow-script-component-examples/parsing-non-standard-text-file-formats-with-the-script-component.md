---
title: Синтаксический анализ текстовых файлов нестандартного формата в компоненте скрипта | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- text file reading [Integration Services]
- Script component [Integration Services], non-standard text file formats
- transformations [Integration Services], components
- Script component [Integration Services], examples
ms.assetid: 1fda034d-09e4-4647-9a9f-e8d508c2cc8f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6a0ca1a0d10bdad40d39a366864a07d2b0a61d13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729637"
---
# <a name="parsing-non-standard-text-file-formats-with-the-script-component"></a><span data-ttu-id="f44cb-102">Синтаксический анализ текстовых файлов нестандартного формата в компоненте скрипта</span><span class="sxs-lookup"><span data-stu-id="f44cb-102">Parsing Non-Standard Text File Formats with the Script Component</span></span>
  <span data-ttu-id="f44cb-103">Если исходные данные организованы в нестандартном формате, может оказаться удобнее объединить всю логику синтаксического анализа в единый скрипт вместо создания цепочки преобразований служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], приводящих к тому же результату.</span><span class="sxs-lookup"><span data-stu-id="f44cb-103">When your source data is arranged in a non-standard format, you may find it more convenient to consolidate all your parsing logic in a single script than to chain together multiple [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] transformations to achieve the same result.</span></span>  
  
 [<span data-ttu-id="f44cb-104">Пример 1. Синтаксический анализ записей, разделенных на строки</span><span class="sxs-lookup"><span data-stu-id="f44cb-104">Example 1: Parsing Row-Delimited Records</span></span>](#example1)  
  
 [<span data-ttu-id="f44cb-105">Пример 2. Разделение родительских и дочерних записей</span><span class="sxs-lookup"><span data-stu-id="f44cb-105">Example 2: Splitting Parent and Child Records</span></span>](#example2)  
  
> [!NOTE]  
>  <span data-ttu-id="f44cb-106">Если нужно создать компонент, который будет полезен в нескольких задачах потока данных и нескольких пакетах, рекомендуется в качестве основы использовать этот образец компонента скрипта.</span><span class="sxs-lookup"><span data-stu-id="f44cb-106">If you want to create a component that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in this Script component sample as the starting point for a custom data flow component.</span></span> <span data-ttu-id="f44cb-107">Дополнительные сведения см. в разделе [Разработка пользовательского компонента потока данных](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="f44cb-107">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
##  <a name="example-1-parsing-row-delimited-records"></a><a name="example1"></a> <span data-ttu-id="f44cb-108">Пример 1. Синтаксический анализ записей, разделенных на строки</span><span class="sxs-lookup"><span data-stu-id="f44cb-108">Example 1: Parsing Row-Delimited Records</span></span>  
 <span data-ttu-id="f44cb-109">В этом примере берется текстовый файл, в котором каждый столбец данных размещается на новой строке, и с помощью синтаксического анализа, реализованного в компоненте скрипта, преобразуется в целевую таблицу.</span><span class="sxs-lookup"><span data-stu-id="f44cb-109">This example shows how to take a text file in which each column of data appears on a separate line and parse it into a destination table by using the Script component.</span></span>  
  
 <span data-ttu-id="f44cb-110">Дополнительные сведения о настройке компонента скрипта для использования в качестве преобразования в потоке данных см. в разделе [Создание синхронного преобразования с помощью компонента скрипта](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)и [Создание асинхронного преобразования с помощью компонента скрипта](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="f44cb-110">For more information about how to configure the Script component for use as a transformation in the data flow, see [Creating a Synchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)and [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="f44cb-111">Настройка этого примера компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="f44cb-111">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="f44cb-112">Создайте и сохраните под именем **rowdelimiteddata.txt** текстовый файл, содержащий следующие исходные данные:</span><span class="sxs-lookup"><span data-stu-id="f44cb-112">Create and save a text file named **rowdelimiteddata.txt** that contains the following source data:</span></span>  
  
    ```  
    FirstName: Nancy  
    LastName: Davolio  
    Title: Sales Representative  
    City: Seattle  
    StateProvince: WA  
  
    FirstName: Andrew  
    LastName: Fuller  
    Title: Vice President, Sales  
    City: Tacoma  
    StateProvince: WA  
  
    FirstName: Steven  
    LastName: Buchanan  
    Title: Sales Manager  
    City: London  
    StateProvince:  
  
    ```  
  
2.  <span data-ttu-id="f44cb-113">Откройте среду [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] и установите соединение с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f44cb-113">Open [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="f44cb-114">Выберите целевую базу данных и откройте окно нового запроса.</span><span class="sxs-lookup"><span data-stu-id="f44cb-114">Select a destination database, and open a new query window.</span></span> <span data-ttu-id="f44cb-115">Чтобы создать целевую таблицу, выполните в окне запросов следующий скрипт.</span><span class="sxs-lookup"><span data-stu-id="f44cb-115">In the query window, execute the following script to create the destination table:</span></span>  
  
    ```  
    create table RowDelimitedData  
    (  
    FirstName varchar(32),  
    LastName varchar(32),  
    Title varchar(32),  
    City varchar(32),  
    StateProvince varchar(32)  
    )  
  
    ```  
  
4.  <span data-ttu-id="f44cb-116">В среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] создайте новый пакет служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] с именем ParseRowDelim.dtsx.</span><span class="sxs-lookup"><span data-stu-id="f44cb-116">Open [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] and create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package named ParseRowDelim.dtsx.</span></span>  
  
5.  <span data-ttu-id="f44cb-117">Добавьте в пакет диспетчер соединений с неструктурированными файлами, назовите этот диспетчер «RowDelimitedData» и настройте на соединение с файлом rowdelimiteddata.txt, созданным на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="f44cb-117">Add a Flat File connection manager to the package, name it RowDelimitedData, and configure it to connect to the rowdelimiteddata.txt file that you created in a previous step.</span></span>  
  
6.  <span data-ttu-id="f44cb-118">Добавьте в пакет диспетчер соединений OLE DB и настройте его на соединение с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и базой данных, в которой создана целевая таблица.</span><span class="sxs-lookup"><span data-stu-id="f44cb-118">Add an OLE DB connection manager to the package and configure it to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the database in which you created the destination table.</span></span>  
  
7.  <span data-ttu-id="f44cb-119">Добавьте в пакет задачу потока данных и щелкните вкладку **Поток данных** конструктора служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="f44cb-119">Add a Data Flow task to the package and click the **Data Flow** tab of SSIS Designer.</span></span>  
  
8.  <span data-ttu-id="f44cb-120">Добавьте к потоку данных источник «Неструктурированный файл» и настройте его на использование диспетчера соединений RowDelimitedData.</span><span class="sxs-lookup"><span data-stu-id="f44cb-120">Add a Flat File Source to the data flow and configure it to use the RowDelimitedData connection manager.</span></span> <span data-ttu-id="f44cb-121">На странице **Столбцы** в редакторе источника **Неструктурированный файл** выберите единственный доступный внешний столбец.</span><span class="sxs-lookup"><span data-stu-id="f44cb-121">On the **Columns** page of the **Flat File Source Editor**, select the single available external column.</span></span>  
  
9. <span data-ttu-id="f44cb-122">Добавьте в поток данных компонент скрипта и настройте его в качестве преобразования.</span><span class="sxs-lookup"><span data-stu-id="f44cb-122">Add a Script Component to the data flow and configure it as a transformation.</span></span> <span data-ttu-id="f44cb-123">Соедините выход источника «Неструктурированный файл» с компонентом скрипта.</span><span class="sxs-lookup"><span data-stu-id="f44cb-123">Connect the output of the Flat File Source to the Script Component.</span></span>  
  
10. <span data-ttu-id="f44cb-124">Дважды щелкните компонент скрипта, чтобы открыть **редактор преобразования "Скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="f44cb-124">Double-click the Script component to display the **Script Transformation Editor**.</span></span>  
  
11. <span data-ttu-id="f44cb-125">На странице **Входные столбцы** в **редакторе преобразования "Скрипт"** выберите единственный доступный входной столбец.</span><span class="sxs-lookup"><span data-stu-id="f44cb-125">On the **Input Columns** page of the **Script Transformation Editor**, select the single available input column.</span></span>  
  
12. <span data-ttu-id="f44cb-126">На странице **входы и выходы** окна **Редактор преобразования "Скрипт**" выберите выходные данные 0 и установите для параметра значение `SynchronousInputID` нет.</span><span class="sxs-lookup"><span data-stu-id="f44cb-126">On the **Inputs and Outputs** page of the **Script Transformation Editor**, select Output 0 and set its `SynchronousInputID` to None.</span></span> <span data-ttu-id="f44cb-127">Создайте 5 выходных столбцов со строковым типом [DT_STR] и длиной 32:</span><span class="sxs-lookup"><span data-stu-id="f44cb-127">Create 5 output columns, all of type string [DT_STR] with a length of 32:</span></span>  
  
    -   <span data-ttu-id="f44cb-128">FirstName</span><span class="sxs-lookup"><span data-stu-id="f44cb-128">FirstName</span></span>  
  
    -   <span data-ttu-id="f44cb-129">LastName</span><span class="sxs-lookup"><span data-stu-id="f44cb-129">LastName</span></span>  
  
    -   <span data-ttu-id="f44cb-130">Title</span><span class="sxs-lookup"><span data-stu-id="f44cb-130">Title</span></span>  
  
    -   <span data-ttu-id="f44cb-131">Город</span><span class="sxs-lookup"><span data-stu-id="f44cb-131">City</span></span>  
  
    -   <span data-ttu-id="f44cb-132">StateProvince</span><span class="sxs-lookup"><span data-stu-id="f44cb-132">StateProvince</span></span>  
  
13. <span data-ttu-id="f44cb-133">На странице **Скрипт** в **редакторе преобразования "Скрипт**" щелкните **изменить скрипт** и введите код, показанный в `ScriptMain` классе примера.</span><span class="sxs-lookup"><span data-stu-id="f44cb-133">On the **Script** page of the **Script Transformation Editor**, click **Edit Script** and enter the code shown in the `ScriptMain` class of the example.</span></span> <span data-ttu-id="f44cb-134">Закройте среду разработки скриптов и **редактор преобразования "Скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="f44cb-134">Close the script development environment and the **Script Transformation Editor**.</span></span>  
  
14. <span data-ttu-id="f44cb-135">Добавьте в поток данных назначение «SQL Server».</span><span class="sxs-lookup"><span data-stu-id="f44cb-135">Add a SQL Server Destination to the data flow.</span></span> <span data-ttu-id="f44cb-136">Настройте его на использование диспетчера соединений OLE DB и таблицы RowDelimitedData.</span><span class="sxs-lookup"><span data-stu-id="f44cb-136">Configure it to use the OLE DB connection manager and the RowDelimitedData table.</span></span> <span data-ttu-id="f44cb-137">Настройте выход компонента скрипта на это назначение.</span><span class="sxs-lookup"><span data-stu-id="f44cb-137">Connect the output of the Script Component to this destination.</span></span>  
  
15. <span data-ttu-id="f44cb-138">Запустите пакет.</span><span class="sxs-lookup"><span data-stu-id="f44cb-138">Run the package.</span></span> <span data-ttu-id="f44cb-139">По завершении работы пакета исследуйте записи в целевой таблице [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f44cb-139">After the package has finished, examine the records in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination table.</span></span>  
  
```vb  
Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
    Dim columnName As String  
    Dim columnValue As String  
  
    ' Check for an empty row.  
    If Row.Column0.Trim.Length > 0 Then  
        columnName = Row.Column0.Substring(0, Row.Column0.IndexOf(":"))  
        ' Check for an empty value after the colon.  
        If Row.Column0.Substring(Row.Column0.IndexOf(":")).TrimEnd.Length > 1 Then  
            ' Extract the column value from after the colon and space.  
            columnValue = Row.Column0.Substring(Row.Column0.IndexOf(":") + 2)  
            Select Case columnName  
                Case "FirstName"  
                    ' The FirstName value indicates a new record.  
                    Me.Output0Buffer.AddRow()  
                    Me.Output0Buffer.FirstName = columnValue  
                Case "LastName"  
                    Me.Output0Buffer.LastName = columnValue  
                Case "Title"  
                    Me.Output0Buffer.Title = columnValue  
                Case "City"  
                    Me.Output0Buffer.City = columnValue  
                Case "StateProvince"  
                    Me.Output0Buffer.StateProvince = columnValue  
            End Select  
        End If  
    End If  
  
End Sub  
```  
  
```csharp  
public override void Input0_ProcessInputRow(Input0Buffer Row)  
    {  
  
        string columnName;  
        string columnValue;  
  
        // Check for an empty row.  
        if (Row.Column0.Trim().Length > 0)  
        {  
            columnName = Row.Column0.Substring(0, Row.Column0.IndexOf(":"));  
            // Check for an empty value after the colon.  
            if (Row.Column0.Substring(Row.Column0.IndexOf(":")).TrimEnd().Length > 1)  
            // Extract the column value from after the colon and space.  
            {  
                columnValue = Row.Column0.Substring(Row.Column0.IndexOf(":") + 2);  
                switch (columnName)  
                {  
                    case "FirstName":  
                        // The FirstName value indicates a new record.  
                        this.Output0Buffer.AddRow();  
                        this.Output0Buffer.FirstName = columnValue;  
                        break;  
                    case "LastName":  
                        this.Output0Buffer.LastName = columnValue;  
                        break;  
                    case "Title":  
                        this.Output0Buffer.Title = columnValue;  
                        break;  
                    case "City":  
                        this.Output0Buffer.City = columnValue;  
                        break;  
                    case "StateProvince":  
                        this.Output0Buffer.StateProvince = columnValue;  
                        break;  
                }  
            }  
        }  
  
    }  
```  
  
##  <a name="example-2-splitting-parent-and-child-records"></a><a name="example2"></a> <span data-ttu-id="f44cb-140">Пример 2. Разделение родительских и дочерних записей</span><span class="sxs-lookup"><span data-stu-id="f44cb-140">Example 2: Splitting Parent and Child Records</span></span>  
 <span data-ttu-id="f44cb-141">В этом примере берется текстовый файл, в котором за строкой-разделителем следует родительская строка, а за ней — неопределенное количество дочерних строк, и с помощью синтаксического анализа, реализованного в компоненте скрипта, преобразуется в две правильным образом нормализованные целевые таблицы — родительскую и дочернюю.</span><span class="sxs-lookup"><span data-stu-id="f44cb-141">This example shows how to take a text file, in which a separator row precedes a parent record row that is followed by an indefinite number of child record rows, and parse it into properly normalized parent and child destination tables by using the Script component.</span></span> <span data-ttu-id="f44cb-142">Этот простой пример легко адаптировать для исходных файлов, использующих несколько строк или столбцов для каждой родительской и дочерней записи: главное, чтобы начало и конец каждой записи были как-то обозначены.</span><span class="sxs-lookup"><span data-stu-id="f44cb-142">This simple example could easily be adapted for source files that use more than one row or column for each parent and child record, as long as there is some way to identify the beginning and end of each record.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="f44cb-143">Данный образец предназначен только для демонстрационных целей.</span><span class="sxs-lookup"><span data-stu-id="f44cb-143">This sample is intended for demonstration purposes only.</span></span> <span data-ttu-id="f44cb-144">Если запустить образец несколько раз, он вставит в целевую таблицу повторяющиеся ключевые значения.</span><span class="sxs-lookup"><span data-stu-id="f44cb-144">If you run the sample more than once, it inserts duplicate key values into the destination table.</span></span>  
  
 <span data-ttu-id="f44cb-145">Дополнительные сведения о настройке компонента скрипта для использования в качестве преобразования в потоке данных см. в разделе [Создание синхронного преобразования с помощью компонента скрипта](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)и [Создание асинхронного преобразования с помощью компонента скрипта](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="f44cb-145">For more information about how to configure the Script component for use as a transformation in the data flow, see [Creating a Synchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)and [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="f44cb-146">Настройка этого примера компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="f44cb-146">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="f44cb-147">Создайте и сохраните под именем **parentchilddata.txt** текстовый файл, содержащий следующие исходные данные:</span><span class="sxs-lookup"><span data-stu-id="f44cb-147">Create and save a text file named **parentchilddata.txt** that contains the following source data:</span></span>  
  
    ```  
    **********  
    PARENT 1 DATA  
    child 1 data  
    child 2 data  
    child 3 data  
    child 4 data  
    **********  
    PARENT 2 DATA  
    child 5 data  
    child 6 data  
    child 7 data  
    child 8 data  
    **********  
  
    ```  
  
2.  <span data-ttu-id="f44cb-148">Откройте среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] и установите соединение с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f44cb-148">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="f44cb-149">Выберите целевую базу данных и откройте окно нового запроса.</span><span class="sxs-lookup"><span data-stu-id="f44cb-149">Select a destination database, and open a new query window.</span></span> <span data-ttu-id="f44cb-150">Чтобы создать целевые таблицы, выполните в окне запросов следующий скрипт.</span><span class="sxs-lookup"><span data-stu-id="f44cb-150">In the query window, execute the following script to create the destination tables:</span></span>  
  
    ```  
    CREATE TABLE [dbo].[Parents]([ParentID] [int] NOT NULL,  
    [ParentRecord] [varchar](32) NOT NULL,  
     CONSTRAINT [PK_Parents] PRIMARY KEY CLUSTERED   
    ([ParentID] ASC))  
    GO  
    CREATE TABLE [dbo].[Children]([ChildID] [int] NOT NULL,  
    [ParentID] [int] NOT NULL,  
    [ChildRecord] [varchar](32) NOT NULL,  
     CONSTRAINT [PK_Children] PRIMARY KEY CLUSTERED   
    ([ChildID] ASC))  
    GO  
    ALTER TABLE [dbo].[Children] ADD CONSTRAINT [FK_Children_Parents] FOREIGN KEY([ParentID])  
    REFERENCES [dbo].[Parents] ([ParentID])  
  
    ```  
  
4.  <span data-ttu-id="f44cb-151">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] создайте новый пакет служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] с именем «SplitParentChild.dtsx».</span><span class="sxs-lookup"><span data-stu-id="f44cb-151">Open [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package named SplitParentChild.dtsx.</span></span>  
  
5.  <span data-ttu-id="f44cb-152">Добавьте в пакет диспетчер соединений с неструктурированными файлами, назовите этот диспетчер «ParentChildData» и настройте на соединение с файлом parentchilddata.txt, созданным на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="f44cb-152">Add a Flat File connection manager to the package, name it ParentChildData, and configure it to connect to the parentchilddata.txt file that you created in a previous step.</span></span>  
  
6.  <span data-ttu-id="f44cb-153">Добавьте в пакет диспетчер соединений OLE DB и настройте его на соединение с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и базой данных, в которой созданы целевые таблицы.</span><span class="sxs-lookup"><span data-stu-id="f44cb-153">Add an OLE DB connection manager to the package and configure it to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the database in which you created the destination tables.</span></span>  
  
7.  <span data-ttu-id="f44cb-154">Добавьте в пакет задачу потока данных и щелкните вкладку **Поток данных** конструктора служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="f44cb-154">Add a Data Flow task to the package and click the **Data Flow** tab of SSIS Designer.</span></span>  
  
8.  <span data-ttu-id="f44cb-155">Добавьте к потоку данных источник «Неструктурированный файл» и настройте его на использование диспетчера соединений ParentChildData.</span><span class="sxs-lookup"><span data-stu-id="f44cb-155">Add a Flat File Source to the data flow and configure it to use the ParentChildData connection manager.</span></span> <span data-ttu-id="f44cb-156">На странице **Столбцы** в редакторе источника **Неструктурированный файл** выберите единственный доступный внешний столбец.</span><span class="sxs-lookup"><span data-stu-id="f44cb-156">On the **Columns** page of the **Flat File Source Editor**, select the single available external column.</span></span>  
  
9. <span data-ttu-id="f44cb-157">Добавьте в поток данных компонент скрипта и настройте его в качестве преобразования.</span><span class="sxs-lookup"><span data-stu-id="f44cb-157">Add a Script Component to the data flow and configure it as a transformation.</span></span> <span data-ttu-id="f44cb-158">Соедините выход источника «Неструктурированный файл» с компонентом скрипта.</span><span class="sxs-lookup"><span data-stu-id="f44cb-158">Connect the output of the Flat File Source to the Script Component.</span></span>  
  
10. <span data-ttu-id="f44cb-159">Дважды щелкните компонент скрипта, чтобы открыть **редактор преобразования "Скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="f44cb-159">Double-click the Script component to display the **Script Transformation Editor**.</span></span>  
  
11. <span data-ttu-id="f44cb-160">На странице **Входные столбцы** в **редакторе преобразования "Скрипт"** выберите единственный доступный входной столбец.</span><span class="sxs-lookup"><span data-stu-id="f44cb-160">On the **Input Columns** page of the **Script Transformation Editor**, select the single available input column.</span></span>  
  
12. <span data-ttu-id="f44cb-161">На странице **входы и выходы** окна **Редактор преобразования "Скрипт**" выберите выходные данные 0, переименуйте их в парентрекордс и установите для параметра значение `SynchronousInputID` None.</span><span class="sxs-lookup"><span data-stu-id="f44cb-161">On the **Inputs and Outputs** page of the **Script Transformation Editor**, select Output 0, rename it to ParentRecords, and set its `SynchronousInputID` to None.</span></span> <span data-ttu-id="f44cb-162">Создайте 2 выходных столбца.</span><span class="sxs-lookup"><span data-stu-id="f44cb-162">Create 2 output columns:</span></span>  
  
    -   <span data-ttu-id="f44cb-163">ParentID (первичный ключ), имеющий тип четырехбайтового целого числа со знаком [DT_I4].</span><span class="sxs-lookup"><span data-stu-id="f44cb-163">ParentID (the primary key), of type four-byte signed integer [DT_I4]</span></span>  
  
    -   <span data-ttu-id="f44cb-164">ParentRecord, строкового типа [DT_STR], длиной 32 символа.</span><span class="sxs-lookup"><span data-stu-id="f44cb-164">ParentRecord, of type string [DT_STR] with a length of 32.</span></span>  
  
13. <span data-ttu-id="f44cb-165">Создайте второй вывод и установите для него имя ChildRecords.</span><span class="sxs-lookup"><span data-stu-id="f44cb-165">Create a second output and name it ChildRecords.</span></span> <span data-ttu-id="f44cb-166">Параметр `SynchronousInputID` для нового вывода уже установлен в значение «Нет».</span><span class="sxs-lookup"><span data-stu-id="f44cb-166">The `SynchronousInputID` of the new output is already set to None.</span></span> <span data-ttu-id="f44cb-167">Создайте 3 выходных столбца.</span><span class="sxs-lookup"><span data-stu-id="f44cb-167">Create 3 output columns:</span></span>  
  
    -   <span data-ttu-id="f44cb-168">ChildID (первичный ключ), имеющий тип четырехбайтового целого числа со знаком [DT_I4].</span><span class="sxs-lookup"><span data-stu-id="f44cb-168">ChildID (the primary key), of type four-byte signed integer [DT_I4]</span></span>  
  
    -   <span data-ttu-id="f44cb-169">ParentID (внешний ключ), также типа «четырехбайтовое целое число со знаком» [DT_I4].</span><span class="sxs-lookup"><span data-stu-id="f44cb-169">ParentID (the foreign key), also of type four-byte signed integer [DT_I4]</span></span>  
  
    -   <span data-ttu-id="f44cb-170">ChildRecord, строкового типа [DT_STR], длиной 50 символов.</span><span class="sxs-lookup"><span data-stu-id="f44cb-170">ChildRecord, of type string [DT_STR] with a length of 50</span></span>  
  
14. <span data-ttu-id="f44cb-171">На странице **Скрипт** **редактора преобразования "Скрипт"** нажмите кнопку **Изменить скрипт**.</span><span class="sxs-lookup"><span data-stu-id="f44cb-171">On the **Script** page of the **Script Transformation Editor**, click **Edit Script**.</span></span> <span data-ttu-id="f44cb-172">Вставьте код, приведенный в примере, в класс `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="f44cb-172">In the `ScriptMain` class, enter the code shown in the example.</span></span> <span data-ttu-id="f44cb-173">Закройте среду разработки скриптов и **редактор преобразования "Скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="f44cb-173">Close the script development environment and the **Script Transformation Editor**.</span></span>  
  
15. <span data-ttu-id="f44cb-174">Добавьте в поток данных назначение «SQL Server».</span><span class="sxs-lookup"><span data-stu-id="f44cb-174">Add a SQL Server Destination to the data flow.</span></span> <span data-ttu-id="f44cb-175">Подключите выход ParentRecords компонента скрипта к этому назначению. Настройте его на использование диспетчера соединений OLE DB и таблицы Parents.</span><span class="sxs-lookup"><span data-stu-id="f44cb-175">Connect the ParentRecords output of the Script Component to this destination.Configure it to use the OLE DB connection manager and the Parents table.</span></span>  
  
16. <span data-ttu-id="f44cb-176">Добавьте к потоку данных еще одно назначение «SQL Server».</span><span class="sxs-lookup"><span data-stu-id="f44cb-176">Add another SQL Server Destination to the data flow.</span></span> <span data-ttu-id="f44cb-177">Настройте выход ChildRecords компонента скрипта на это назначение.</span><span class="sxs-lookup"><span data-stu-id="f44cb-177">Connect the ChildRecords output of the Script Component to this destination.</span></span> <span data-ttu-id="f44cb-178">Настройте его на использование диспетчера соединений OLE DB и таблицы Children.</span><span class="sxs-lookup"><span data-stu-id="f44cb-178">Configure it to use the OLE DB connection manager and the Children table.</span></span>  
  
17. <span data-ttu-id="f44cb-179">Запустите пакет.</span><span class="sxs-lookup"><span data-stu-id="f44cb-179">Run the package.</span></span> <span data-ttu-id="f44cb-180">По завершении работы пакета исследуйте записи в двух целевых таблицах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f44cb-180">After the package has finished, examine the parent and child records in the two [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination tables.</span></span>  
  
```vb  
Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
    Static nextRowIsParent As Boolean = False  
    Static parentCounter As Integer = 0  
    Static childCounter As Integer = 0  
  
    ' If current row starts with separator characters,  
    '  then following row contains new parent record.  
    If Row.Column0.StartsWith("***") Then  
        nextRowIsParent = True  
    Else  
        If nextRowIsParent Then  
            ' Current row contains parent record.  
            parentCounter += 1  
            Me.ParentRecordsBuffer.AddRow()  
            Me.ParentRecordsBuffer.ParentID = parentCounter  
            Me.ParentRecordsBuffer.ParentRecord = Row.Column0  
            nextRowIsParent = False  
        Else  
            ' Current row contains child record.  
            childCounter += 1  
            Me.ChildRecordsBuffer.AddRow()  
            Me.ChildRecordsBuffer.ChildID = childCounter  
            Me.ChildRecordsBuffer.ParentID = parentCounter  
            Me.ChildRecordsBuffer.ChildRecord = Row.Column0  
        End If  
    End If  
  
End Sub  
```  
  
```csharp  
public override void Input0_ProcessInputRow(Input0Buffer Row)  
    {  
  
    int static_Input0_ProcessInputRow_childCounter = 0;  
    int static_Input0_ProcessInputRow_parentCounter = 0;  
    bool static_Input0_ProcessInputRow_nextRowIsParent = false;  
  
        // If current row starts with separator characters,   
        // then following row contains new parent record.   
        if (Row.Column0.StartsWith("***"))  
        {  
            static_Input0_ProcessInputRow_nextRowIsParent = true;  
        }  
        else  
        {  
            if (static_Input0_ProcessInputRow_nextRowIsParent)  
            {  
                // Current row contains parent record.   
                static_Input0_ProcessInputRow_parentCounter += 1;  
                this.ParentRecordsBuffer.AddRow();  
                this.ParentRecordsBuffer.ParentID = static_Input0_ProcessInputRow_parentCounter;  
                this.ParentRecordsBuffer.ParentRecord = Row.Column0;  
                static_Input0_ProcessInputRow_nextRowIsParent = false;  
            }  
            else  
            {  
                // Current row contains child record.   
                static_Input0_ProcessInputRow_childCounter += 1;  
                this.ChildRecordsBuffer.AddRow();  
                this.ChildRecordsBuffer.ChildID = static_Input0_ProcessInputRow_childCounter;  
                this.ChildRecordsBuffer.ParentID = static_Input0_ProcessInputRow_parentCounter;  
                this.ChildRecordsBuffer.ChildRecord = Row.Column0;  
            }  
        }  
  
    }  
```  
  
<span data-ttu-id="f44cb-181">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="f44cb-181">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="f44cb-182">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="f44cb-182">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="f44cb-183">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="f44cb-183">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="f44cb-184">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="f44cb-184">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f44cb-185">См. также:</span><span class="sxs-lookup"><span data-stu-id="f44cb-185">See Also</span></span>  
 [<span data-ttu-id="f44cb-186">Создание синхронного преобразования с помощью компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="f44cb-186">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)  
 [<span data-ttu-id="f44cb-187">Создание асинхронного преобразования с помощью компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="f44cb-187">Creating an Asynchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)  
  
  
