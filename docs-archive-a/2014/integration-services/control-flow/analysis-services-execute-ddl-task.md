---
title: Задача "Выполнение инструкции DDL служб Analysis Services" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asexecuteddltask.f1
helpviewer_keywords:
- Analysis Services Execute DDL task
- DDL
ms.assetid: 7f25c8c6-b601-41f2-9553-be0a2ee0751a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a75bae174c816cdabd07ce688e068cbadb016b45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664431"
---
# <a name="analysis-services-execute-ddl-task"></a><span data-ttu-id="c7b75-102">Задача «Выполнение инструкции DDL служб Analysis Services»</span><span class="sxs-lookup"><span data-stu-id="c7b75-102">Analysis Services Execute DDL Task</span></span>
  <span data-ttu-id="c7b75-103">задача «Выполнение инструкции DDL служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] » запускает инструкции языка DDL, которые могут создавать, удалять или изменять модели интеллектуального анализа данных и многомерные объекты, такие как кубы и измерения.</span><span class="sxs-lookup"><span data-stu-id="c7b75-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL task runs data definition language (DDL) statements that can create, drop, or alter mining models and multidimensional objects such as cubes and dimensions.</span></span> <span data-ttu-id="c7b75-104">Например, инструкция DDL позволяет создать секцию в кубе **Adventure Works** или удалить измерение в [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], образце базы данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , входящем в состав [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7b75-104">For example, a DDL statement can create a partition in the **Adventure Works** cube, or delete a dimension in [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], the sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c7b75-105">Задача «Выполнение инструкции DDL служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] » использует диспетчер соединений служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] для подключения к экземпляру служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] или к проекту [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c7b75-105">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL task uses an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] or an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="c7b75-106">Дополнительные сведения см. в статье [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c7b75-106">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="c7b75-107">содержат ряд задач, выполняющих операции бизнес-аналитики, таких как обработка аналитических объектов и запуск запросов прогнозирования интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="c7b75-107">includes a number of tasks that perform business intelligence operations, such as processing analytic objects and running data mining prediction queries.</span></span>  
  
 <span data-ttu-id="c7b75-108">Дополнительные сведения о задачах, связанных с бизнес-аналитикой, см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="c7b75-108">For more information about related business intelligence tasks, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="c7b75-109">Задача «Обработка средствами Analysis Services»</span><span class="sxs-lookup"><span data-stu-id="c7b75-109">Analysis Services Processing Task</span></span>](analysis-services-processing-task.md)  
  
-   [<span data-ttu-id="c7b75-110">Задача «Запрос интеллектуального анализа данных»</span><span class="sxs-lookup"><span data-stu-id="c7b75-110">Data Mining Query Task</span></span>](data-mining-query-task.md)  
  
## <a name="ddl-statements"></a><span data-ttu-id="c7b75-111">Инструкции DDL</span><span class="sxs-lookup"><span data-stu-id="c7b75-111">DDL Statements</span></span>  
 <span data-ttu-id="c7b75-112">Инструкции DDL представлены как инструкции в службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Scripting Language (ASSL) и встроены в команду XML для аналитики (XMLA).</span><span class="sxs-lookup"><span data-stu-id="c7b75-112">The DDL statements are represented as statements in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Scripting Language (ASSL), and framed in an XML for Analysis (XMLA) command.</span></span>  
  
-   <span data-ttu-id="c7b75-113">ASSL используется для определения и описания экземпляра служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , базы данных и объектов базы данных, которые он содержит.</span><span class="sxs-lookup"><span data-stu-id="c7b75-113">ASSL is used to define and describe an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and the databases and database objects it contains.</span></span> <span data-ttu-id="c7b75-114">Дополнительные сведения см. в статье [Analysis Services языка сценариев &#40;языке ASSL&#41; справочнике](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla).</span><span class="sxs-lookup"><span data-stu-id="c7b75-114">For more information, see [Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla).</span></span>  
  
-   <span data-ttu-id="c7b75-115">XML для аналитики — это язык команд, используемый для отправки команд-действий, таких как «Создать», «Изменить» или «Обработать», экземпляру служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7b75-115">XMLA is a command language that is used to send action commands, such as Create, Alter, or Process, to an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="c7b75-116">Дополнительные сведения см. в разделе [Справочник по XML для аналитики (XMLA)](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span><span class="sxs-lookup"><span data-stu-id="c7b75-116">For more information, see [XML for Analysis  &#40;XMLA&#41; Reference](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span></span>  
  
 <span data-ttu-id="c7b75-117">Если DDL-код хранится в отдельном файле, задача «Выполнение инструкции DDL служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] » использует диспетчер подключения файлов для указания пути файла.</span><span class="sxs-lookup"><span data-stu-id="c7b75-117">If the DDL code is stored in a separate file, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL task uses a File connection manager to specify the path of the file.</span></span> <span data-ttu-id="c7b75-118">Дополнительные сведения см. в статье [File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c7b75-118">For more information, see [File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="c7b75-119">Так как инструкции DDL могут содержать пароли и другие важные сведения, пакет, содержащий одну или несколько задач «Выполнение инструкции DDL служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]», должен использовать уровень защиты пакета `EncryptAllWithUserKey` или `EncryptAllWithPassword`.</span><span class="sxs-lookup"><span data-stu-id="c7b75-119">Because DDL statements can contain passwords and other sensitive information, a package that contains one or more [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL tasks should use the package protection level `EncryptAllWithUserKey` or `EncryptAllWithPassword`.</span></span> <span data-ttu-id="c7b75-120">Дополнительные сведения см. в разделе [Пакеты служб Integration Services (SSIS)](../integration-services-ssis-packages.md).</span><span class="sxs-lookup"><span data-stu-id="c7b75-120">For more information, see [Integration Services &#40;SSIS&#41; Packages](../integration-services-ssis-packages.md).</span></span>  
  
### <a name="ddl-examples"></a><span data-ttu-id="c7b75-121">Примеры DDL</span><span class="sxs-lookup"><span data-stu-id="c7b75-121">DDL Examples</span></span>  
 <span data-ttu-id="c7b75-122">Следующие три инструкции DDL были сформированы объектами сценария в [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], базе данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , входящей в состав [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7b75-122">The following three DDL statements were generated by scripting objects in the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c7b75-123">Следующая инструкция DDL удаляет измерение **Promotion** .</span><span class="sxs-lookup"><span data-stu-id="c7b75-123">The following DDL statement deletes the **Promotion** dimension.</span></span>  
  
```  
<Delete xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DimensionID>Dim Promotion</DimensionID>  
    </Object>  
</Delete>  
  
```  
  
 <span data-ttu-id="c7b75-124">Следующая инструкция DDL обрабатывает куб [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c7b75-124">The following DDL statement processes the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] cube.</span></span>  
  
```  
<Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Parallel>  
    <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
      <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      </Object>  
      <Type>ProcessFull</Type>  
      <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
    </Process>  
  </Parallel>  
</Batch>  
  
```  
  
 <span data-ttu-id="c7b75-125">Следующая инструкция DDL создает модель интеллектуального анализа данных **Forecasting** .</span><span class="sxs-lookup"><span data-stu-id="c7b75-125">The following DDL statement creates the **Forecasting** mining model.</span></span>  
  
```  
<Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <MiningStructureID>Forecasting</MiningStructureID>  
    </ParentObject>  
    <ObjectDefinition>  
        <MiningModel xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
            <ID>Forecasting</ID>  
            <Name>Forecasting</Name>  
            <Algorithm>Microsoft_Time_Series</Algorithm>  
            <AlgorithmParameters>  
                <AlgorithmParameter>  
                    <Name>PERIODICITY_HINT</Name>  
                    <Value xsi:type="xsd:string">{12}</Value>  
                </AlgorithmParameter>  
            </AlgorithmParameters>  
            <Columns>  
                <Column>  
                    <ID>Amount</ID>  
                    <Name>Amount</Name>  
                    <SourceColumnID>Amount</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Model Region</ID>  
                    <Name>Model Region</Name>  
                    <SourceColumnID>Model Region</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
                <Column>  
                    <ID>Quantity</ID>  
                    <Name>Quantity</Name>  
                    <SourceColumnID>Quantity</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Time Index</ID>  
                    <Name>Time Index</Name>  
                    <SourceColumnID>Time Index</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
            </Columns>  
            <Collation>Latin1_General_CS_AS_KS</Collation>  
        </MiningModel>  
    </ObjectDefinition>  
</Create>  
  
```  
  
 <span data-ttu-id="c7b75-126">Следующие три инструкции DDL были сформированы объектами сценария в [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], базе данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , входящей в состав [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7b75-126">The following three DDL statements were generated by scripting objects in the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c7b75-127">Следующая инструкция DDL удаляет измерение **Promotion** .</span><span class="sxs-lookup"><span data-stu-id="c7b75-127">The following DDL statement deletes the **Promotion** dimension.</span></span>  
  
```  
<Delete xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DimensionID>Dim Promotion</DimensionID>  
    </Object>  
</Delete>  
  
```  
  
 <span data-ttu-id="c7b75-128">Следующая инструкция DDL обрабатывает куб [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c7b75-128">The following DDL statement processes the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] cube.</span></span>  
  
```  
<Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Parallel>  
    <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
      <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      </Object>  
      <Type>ProcessFull</Type>  
      <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
    </Process>  
  </Parallel>  
</Batch>  
  
```  
  
 <span data-ttu-id="c7b75-129">Следующая инструкция DDL создает модель интеллектуального анализа данных **Forecasting** .</span><span class="sxs-lookup"><span data-stu-id="c7b75-129">The following DDL statement creates the **Forecasting** mining model.</span></span>  
  
```  
<Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <MiningStructureID>Forecasting</MiningStructureID>  
    </ParentObject>  
    <ObjectDefinition>  
        <MiningModel xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
            <ID>Forecasting</ID>  
            <Name>Forecasting</Name>  
            <Algorithm>Microsoft_Time_Series</Algorithm>  
            <AlgorithmParameters>  
                <AlgorithmParameter>  
                    <Name>PERIODICITY_HINT</Name>  
                    <Value xsi:type="xsd:string">{12}</Value>  
                </AlgorithmParameter>  
            </AlgorithmParameters>  
            <Columns>  
                <Column>  
                    <ID>Amount</ID>  
                    <Name>Amount</Name>  
                    <SourceColumnID>Amount</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Model Region</ID>  
                    <Name>Model Region</Name>  
                    <SourceColumnID>Model Region</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
                <Column>  
                    <ID>Quantity</ID>  
                    <Name>Quantity</Name>  
                    <SourceColumnID>Quantity</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Time Index</ID>  
                    <Name>Time Index</Name>  
                    <SourceColumnID>Time Index</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
            </Columns>  
            <Collation>Latin1_General_CS_AS_KS</Collation>  
        </MiningModel>  
    </ObjectDefinition>  
</Create>  
  
```  
  
## <a name="configuration-of-the-analysis-services-execute-ddl-task"></a><span data-ttu-id="c7b75-130">Настройка задачи «Выполнение инструкции DDL служб Analysis Services»</span><span class="sxs-lookup"><span data-stu-id="c7b75-130">Configuration of the Analysis Services Execute DDL Task</span></span>  
 <span data-ttu-id="c7b75-131">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="c7b75-131">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="c7b75-132">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="c7b75-132">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="c7b75-133">Редактор задачи "Выполнение инструкции DDL служб Analysis Services" (страница "Общие")</span><span class="sxs-lookup"><span data-stu-id="c7b75-133">Analysis Services Execute DDL Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="c7b75-134">Редактор задачи "Выполнение инструкции DDL служб Analysis Services" (страница "DDL")</span><span class="sxs-lookup"><span data-stu-id="c7b75-134">Analysis Services Execute DDL Task Editor &#40;DDL Page&#41;</span></span>](../analysis-services-execute-ddl-task-editor-ddl-page.md)  
  
-   [<span data-ttu-id="c7b75-135">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="c7b75-135">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="c7b75-136">Дополнительные сведения об установке этих свойств в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="c7b75-136">For more information about setting these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="c7b75-137">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="c7b75-137">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-analysis-services-execute-ddl-task"></a><span data-ttu-id="c7b75-138">Программная настройка задачи «Выполнение инструкции DDL служб Analysis Services»</span><span class="sxs-lookup"><span data-stu-id="c7b75-138">Programmatic Configuration of the Analysis Services Execute DDL Task</span></span>  
 <span data-ttu-id="c7b75-139">Дополнительные сведения об установке этих свойств программными средствами см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="c7b75-139">For more information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.DataTransformationServices.Tasks.DTSProcessingTask.ASExecuteDDLTask>  
  
  
