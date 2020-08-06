---
title: Создание и изменение объектов (XMLA) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- objects [XML for Analysis]
- subordinate objects [XML for Analysis]
- XML for Analysis, objects
- modifying objects
- removing objects
- deleting objects
- XMLA, objects
ms.assetid: a2080867-e130-440c-92eb-f768869f34a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2390c0b921368e7e06f0e5563a7eb59769d99c17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667455"
---
# <a name="creating-and-altering-objects-xmla"></a><span data-ttu-id="607ce-102">Создание и изменение объектов (XMLA)</span><span class="sxs-lookup"><span data-stu-id="607ce-102">Creating and Altering Objects (XMLA)</span></span>
  <span data-ttu-id="607ce-103">Основные объекты можно создавать, изменять и удалять независимо.</span><span class="sxs-lookup"><span data-stu-id="607ce-103">Major objects can be independently created, altered, and deleted.</span></span> <span data-ttu-id="607ce-104">Основные объекты включают следующие объекты:</span><span class="sxs-lookup"><span data-stu-id="607ce-104">Major objects include the following objects:</span></span>  
  
-   <span data-ttu-id="607ce-105">Серверы</span><span class="sxs-lookup"><span data-stu-id="607ce-105">Servers</span></span>  
  
-   <span data-ttu-id="607ce-106">Базы данных</span><span class="sxs-lookup"><span data-stu-id="607ce-106">Databases</span></span>  
  
-   <span data-ttu-id="607ce-107">Измерения</span><span class="sxs-lookup"><span data-stu-id="607ce-107">Dimensions</span></span>  
  
-   <span data-ttu-id="607ce-108">Кубы</span><span class="sxs-lookup"><span data-stu-id="607ce-108">Cubes</span></span>  
  
-   <span data-ttu-id="607ce-109">Группы мер</span><span class="sxs-lookup"><span data-stu-id="607ce-109">Measure groups</span></span>  
  
-   <span data-ttu-id="607ce-110">Секции</span><span class="sxs-lookup"><span data-stu-id="607ce-110">Partitions</span></span>  
  
-   <span data-ttu-id="607ce-111">Перспективы</span><span class="sxs-lookup"><span data-stu-id="607ce-111">Perspectives</span></span>  
  
-   <span data-ttu-id="607ce-112">Модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="607ce-112">Mining models</span></span>  
  
-   <span data-ttu-id="607ce-113">Роли</span><span class="sxs-lookup"><span data-stu-id="607ce-113">Roles</span></span>  
  
-   <span data-ttu-id="607ce-114">Команды, связанные с сервером или базой данных</span><span class="sxs-lookup"><span data-stu-id="607ce-114">Commands associated with a server or database</span></span>  
  
-   <span data-ttu-id="607ce-115">Источники данных</span><span class="sxs-lookup"><span data-stu-id="607ce-115">Data sources</span></span>  
  
 <span data-ttu-id="607ce-116">Команда [CREATE](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla) используется для создания основного объекта в экземпляре служб [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , а команда [ALTER](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) — для изменения существующего основного объекта в экземпляре.</span><span class="sxs-lookup"><span data-stu-id="607ce-116">You use the [Create](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla) command to create a major object on an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], and the [Alter](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) command to alter an existing major object on an instance.</span></span> <span data-ttu-id="607ce-117">Обе команды выполняются с помощью метода [EXECUTE](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) .</span><span class="sxs-lookup"><span data-stu-id="607ce-117">Both commands are run using the [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="607ce-118">Создание объектов</span><span class="sxs-lookup"><span data-stu-id="607ce-118">Creating Objects</span></span>  
 <span data-ttu-id="607ce-119">Объекты можно создавать при помощи метода `Create`; для этого сначала необходимо определить родительский объект, содержащий объект служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], который должен быть создан.</span><span class="sxs-lookup"><span data-stu-id="607ce-119">When you create objects by using the `Create` method, you must first identify the parent object that contains the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] object to be created.</span></span> <span data-ttu-id="607ce-120">Вы определяете родительский объект, предоставив ссылку на объект в свойстве [ParentObject](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) `Create` команды.</span><span class="sxs-lookup"><span data-stu-id="607ce-120">You identify the parent object by providing an object reference in the [ParentObject](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `Create` command.</span></span> <span data-ttu-id="607ce-121">Каждая ссылка объекта содержит идентификаторы объекта, необходимые, чтобы идентифицировать родительский объект для команды `Create` уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="607ce-121">Each object reference contains the object identifiers needed to uniquely identify the parent object for the `Create` command.</span></span> <span data-ttu-id="607ce-122">Дополнительные сведения о ссылках на объекты см. в разделе [Определение и идентификация объектов &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span><span class="sxs-lookup"><span data-stu-id="607ce-122">For more information about object references, see [Defining and Identifying Objects &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span></span>  
  
 <span data-ttu-id="607ce-123">Например, следует указать ссылку объекта на куб, чтобы создать новую группу мер для этого куба.</span><span class="sxs-lookup"><span data-stu-id="607ce-123">For example, you must provide an object reference to a cube to create a new measure group for the cube.</span></span> <span data-ttu-id="607ce-124">Ссылка на объект для куба в свойстве `ParentObject` содержит идентификатор базы данных и идентификатор куба, поскольку тот же идентификатор куба может использоваться в другой базе данных.</span><span class="sxs-lookup"><span data-stu-id="607ce-124">The object reference for the cube in the `ParentObject` property contains both a database identifier and a cube identifier, as the same cube identifier could potentially be used on a different database.</span></span>  
  
 <span data-ttu-id="607ce-125">Элемент [ObjectDefinition](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/objectdefinition-element-xmla) содержит Analysis Services элементы языка ASSL, определяющие основной объект, который необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="607ce-125">The [ObjectDefinition](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/objectdefinition-element-xmla) element contains Analysis Services Scripting Language (ASSL) elements that define the major object to be created.</span></span> <span data-ttu-id="607ce-126">Дополнительные сведения о языке ASSL см. в разделе [Разработка с использованием Analysis Services языка сценариев &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span><span class="sxs-lookup"><span data-stu-id="607ce-126">For more information about ASSL, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span></span>  
  
 <span data-ttu-id="607ce-127">Если атрибуту `AllowOverwrite` команды `Create` задать значение TRUE, можно переписать существующий основной объект, имеющий указанный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="607ce-127">If you set the `AllowOverwrite` attribute of the `Create` command to true, you can overwrite an existing major object that has the specified identifier.</span></span> <span data-ttu-id="607ce-128">В противном случае, если основной объект с указанным идентификатором уже существует в родительском объекте, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="607ce-128">Otherwise, an error occurs if a major object that has the specified identifier already exists in the parent object.</span></span>  
  
 <span data-ttu-id="607ce-129">Дополнительные сведения о `Create` команде см. в разделе [создание элемента &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="607ce-129">For more information about the `Create` command, see [Create Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla).</span></span>  
  
### <a name="creating-session-objects"></a><span data-ttu-id="607ce-130">Создание объектов сеанса</span><span class="sxs-lookup"><span data-stu-id="607ce-130">Creating Session Objects</span></span>  
 <span data-ttu-id="607ce-131">Объекты сеанса — это временные объекты, доступные только для явных или неявных сеансов, которые используются клиентским приложением и удаляются по завершении сеанса.</span><span class="sxs-lookup"><span data-stu-id="607ce-131">Session objects are temporary objects that are available only to the explicit or implicit session used by a client application and are deleted when the session is ended.</span></span> <span data-ttu-id="607ce-132">Вы можете создавать объекты сеанса, присвоив `Scope` атрибуту `Create` команды значение *Session*.</span><span class="sxs-lookup"><span data-stu-id="607ce-132">You can create session objects by setting the `Scope` attribute of the `Create` command to *Session*.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="607ce-133">При использовании параметра *сеанса* `ObjectDefinition` элемент может содержать только [измерения](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [Кубы](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl)или [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) элементы ASSL.</span><span class="sxs-lookup"><span data-stu-id="607ce-133">When using the *Session* setting, the `ObjectDefinition` element can only contain [Dimension](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [Cube](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl), or [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) ASSL elements.</span></span>  
  
## <a name="altering-objects"></a><span data-ttu-id="607ce-134">Изменение объектов</span><span class="sxs-lookup"><span data-stu-id="607ce-134">Altering Objects</span></span>  
 <span data-ttu-id="607ce-135">При изменении объектов с помощью `Alter` метода необходимо сначала указать объект, который необходимо изменить, предоставив ссылку на объект в свойстве [объекта](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) `Alter` команды.</span><span class="sxs-lookup"><span data-stu-id="607ce-135">When modifying objects by using the `Alter` method, you must first identify the object to be modified by providing an object reference in the [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `Alter` command.</span></span> <span data-ttu-id="607ce-136">Каждая ссылка объекта содержит идентификаторы объекта, необходимые, чтобы уникальным образом идентифицировать объект для команды `Alter`.</span><span class="sxs-lookup"><span data-stu-id="607ce-136">Each object reference contains the object identifiers needed to uniquely identify the object for the `Alter` command.</span></span> <span data-ttu-id="607ce-137">Дополнительные сведения о ссылках на объекты см. в разделе [Определение и идентификация объектов &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span><span class="sxs-lookup"><span data-stu-id="607ce-137">For more information about object references, see [Defining and Identifying Objects &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span></span>  
  
 <span data-ttu-id="607ce-138">Например, чтобы изменить структуру куба, необходимо указать ссылку объекта на куб.</span><span class="sxs-lookup"><span data-stu-id="607ce-138">For example, you must provide an object reference to a cube in order to modify the structure of a cube.</span></span> <span data-ttu-id="607ce-139">Ссылка на объект для куба в свойстве `Object` содержит идентификатор базы данных и идентификатор куба, поскольку тот же идентификатор куба может использоваться в другой базе данных.</span><span class="sxs-lookup"><span data-stu-id="607ce-139">The object reference for the cube in the `Object` property contains both a database identifier and a cube identifier, as the same cube identifier could potentially be used on a different database.</span></span>  
  
 <span data-ttu-id="607ce-140">Элемент `ObjectDefinition` содержит элементы языка ASSL, определяющие основной объект, которые должен быть изменен.</span><span class="sxs-lookup"><span data-stu-id="607ce-140">The `ObjectDefinition` element contains ASSL elements that define the major object to be modified.</span></span> <span data-ttu-id="607ce-141">Дополнительные сведения о языке ASSL см. в разделе [Разработка с использованием Analysis Services языка сценариев &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span><span class="sxs-lookup"><span data-stu-id="607ce-141">For more information about ASSL, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span></span>  
  
 <span data-ttu-id="607ce-142">Если атрибуту `AllowCreate` команды `Alter` задать значение TRUE, можно создать указанный основной объект, если он не существует.</span><span class="sxs-lookup"><span data-stu-id="607ce-142">If you set the `AllowCreate` attribute of the `Alter` command to true, you can create the specified major object if the object does not exist.</span></span> <span data-ttu-id="607ce-143">В противном случае, если указанный основной объект еще не существует, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="607ce-143">Otherwise, an error occurs if a specified major object does not already exist.</span></span>  
  
### <a name="using-the-objectexpansion-attribute"></a><span data-ttu-id="607ce-144">Использование атрибута ObjectExpansion</span><span class="sxs-lookup"><span data-stu-id="607ce-144">Using the ObjectExpansion Attribute</span></span>  
 <span data-ttu-id="607ce-145">Если изменяются только свойства основного объекта и не переопределяются небольшие объекты, содержащиеся в основном объекте, можно установить `ObjectExpansion` атрибут `Alter` команды *ObjectProperties*.</span><span class="sxs-lookup"><span data-stu-id="607ce-145">If you are changing only the properties of the major object and are not redefining minor objects that are contained by the major object, you can set the `ObjectExpansion` attribute of the `Alter` command to *ObjectProperties*.</span></span> <span data-ttu-id="607ce-146">В этом случае свойство `ObjectDefinition` должно содержать только элементы для свойств основного объекта, а команда `Alter` оставляет второстепенные объекты, ассоциированные с основным объектом, без изменений.</span><span class="sxs-lookup"><span data-stu-id="607ce-146">The `ObjectDefinition` property then only has to contain the elements for the properties of the major object, and the `Alter` command leaves minor objects associated with the major object untouched.</span></span>  
  
 <span data-ttu-id="607ce-147">Чтобы переопределить незначительные объекты для основного объекта, необходимо задать `ObjectExpansion` для атрибута значение *ExpandFull* , а определение объекта должно включать все небольшие объекты, содержащиеся в основном объекте.</span><span class="sxs-lookup"><span data-stu-id="607ce-147">To redefine minor objects for a major object, you must set the `ObjectExpansion` attribute to *ExpandFull* and the object definition must include all minor objects that are contained by the major object.</span></span> <span data-ttu-id="607ce-148">Если в свойство `ObjectDefinition` команды `Alter` явно не включен второстепенный объект, содержащийся в основном объекте, то не указанный в нем второстепенный объект удаляется.</span><span class="sxs-lookup"><span data-stu-id="607ce-148">If the `ObjectDefinition` property of the `Alter` command does not explicitly include a minor object that is contained by the major object, the minor object that was not included is deleted.</span></span>  
  
### <a name="altering-session-objects"></a><span data-ttu-id="607ce-149">Изменение объектов сеанса</span><span class="sxs-lookup"><span data-stu-id="607ce-149">Altering Session Objects</span></span>  
 <span data-ttu-id="607ce-150">Чтобы изменить объекты сеанса `Create` , созданные командой, присвойте `Scope` атрибуту команды значение `Alter` *Session*.</span><span class="sxs-lookup"><span data-stu-id="607ce-150">To modify session objects created by the `Create` command, set the `Scope` attribute of the `Alter` command to *Session*.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="607ce-151">При использовании параметра *сеанса* `ObjectDefinition` элемент может содержать только [измерения](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [Кубы](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl)или [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) элементы ASSL.</span><span class="sxs-lookup"><span data-stu-id="607ce-151">When using the *Session* setting, the `ObjectDefinition` element can only contain [Dimension](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [Cube](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl), or [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) ASSL elements.</span></span>  
  
## <a name="creating-or-altering-subordinate-objects"></a><span data-ttu-id="607ce-152">Создание или изменение подчиненных объектов</span><span class="sxs-lookup"><span data-stu-id="607ce-152">Creating or Altering Subordinate Objects</span></span>  
 <span data-ttu-id="607ce-153">Хотя команда `Create` или `Alter` создает или изменяет только один самый верхний основной объект, создаваемый или изменяемый основной объект может содержать во включающем свойстве `ObjectDefinition` определения для других основных или второстепенных объектов, которые ему подчинены.</span><span class="sxs-lookup"><span data-stu-id="607ce-153">Although a `Create` or `Alter` command creates or alters only one topmost major object, the major object being created or modified can contain definitions within the enclosing `ObjectDefinition` property for other major and minor objects that are subordinate to it.</span></span> <span data-ttu-id="607ce-154">Например, при определении куба родительская база данных указывается в свойстве `ParentObject`, тогда как в рамках определения куба в свойстве `ObjectDefinition` можно определить группы мер для куба, а в рамках групп мер — определить секции для каждой группы мер.</span><span class="sxs-lookup"><span data-stu-id="607ce-154">For example, if you define a cube, you specify the parent database in `ParentObject`, and within the cube definition in `ObjectDefinition` you can define measure groups for the cube, and within the measure groups you can define partitions for each measure group.</span></span> <span data-ttu-id="607ce-155">Второстепенный объект можно определить только в содержащем его основном объекте.</span><span class="sxs-lookup"><span data-stu-id="607ce-155">A minor object can be defined only under the major object that contains it.</span></span> <span data-ttu-id="607ce-156">Дополнительные сведения о основных и вспомогательных объектах см. в разделе [Database objects &#40;Analysis Services многомерных данных&#41;](../multidimensional-models/olap-logical/database-objects-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="607ce-156">For more information about major and minor objects, see [Database Objects &#40;Analysis Services - Multidimensional Data&#41;](../multidimensional-models/olap-logical/database-objects-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="607ce-157">Примеры</span><span class="sxs-lookup"><span data-stu-id="607ce-157">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="607ce-158">Описание</span><span class="sxs-lookup"><span data-stu-id="607ce-158">Description</span></span>  
 <span data-ttu-id="607ce-159">В следующем примере создается реляционный источник данных, ссылающийся на [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] образец [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] базы данных.</span><span class="sxs-lookup"><span data-stu-id="607ce-159">The following example creates a relational data source that references the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
### <a name="code"></a><span data-ttu-id="607ce-160">Код</span><span class="sxs-lookup"><span data-stu-id="607ce-160">Code</span></span>  
  
```  
<Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    </ParentObject>  
    <ObjectDefinition>  
        <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
            <ID>AdventureWorksDW2012</ID>  
            <Name>AdventureWorksDW2012</Name>  
            <ConnectionString>Data Source=localhost;Initial Catalog=AdventureWorksDW2008R2;Integrated Security=True</ConnectionString>  
            <ImpersonationInfo>  
                <ImpersonationMode>ImpersonateServiceAccount</ImpersonationMode>  
            </ImpersonationInfo>  
            <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
            <Timeout>PT0S</Timeout>  
        </DataSource>  
    </ObjectDefinition>  
</Create>  
```  
  
### <a name="description"></a><span data-ttu-id="607ce-161">Описание</span><span class="sxs-lookup"><span data-stu-id="607ce-161">Description</span></span>  
 <span data-ttu-id="607ce-162">В следующем примере реляционный источник данных, созданный в предыдущем примере, изменяется путем задания времени ожидания запроса для источника данных, равного 30 секундам.</span><span class="sxs-lookup"><span data-stu-id="607ce-162">The following example alters the relational data source created in the previous example to set the query time-out for the data source to 30 seconds.</span></span>  
  
### <a name="code"></a><span data-ttu-id="607ce-163">Код</span><span class="sxs-lookup"><span data-stu-id="607ce-163">Code</span></span>  
  
```  
<Alter ObjectExpansion="ObjectProperties" xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DataSourceID>AdventureWorksDW2012</DataSourceID>  
    </Object>  
    <ObjectDefinition>  
        <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
            <ID>AdventureWorksDW2012</ID>  
            <Name>AdventureWorksDW2012</Name>  
            <ConnectionString>Data Source=fr-dwk-02;Initial Catalog=AdventureWorksDW2008R2;Integrated Security=True</ConnectionString>  
            <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
            <Timeout>PT30S</Timeout>  
        </DataSource>  
    </ObjectDefinition>  
</Alter>  
```  
  
### <a name="comments"></a><span data-ttu-id="607ce-164">Комментарии</span><span class="sxs-lookup"><span data-stu-id="607ce-164">Comments</span></span>  
 <span data-ttu-id="607ce-165">`ObjectExpansion`Атрибуту `Alter` команды было присвоено значение *ObjectProperties*.</span><span class="sxs-lookup"><span data-stu-id="607ce-165">The `ObjectExpansion` attribute of the `Alter` command was set to *ObjectProperties*.</span></span> <span data-ttu-id="607ce-166">Этот параметр позволяет исключить элемент [ImpersonationInfo](https://docs.microsoft.com/bi-reference/assl/properties/impersonationinfo-element-assl) , дополнительный объект, из источника данных, определенного в `ObjectDefinition` .</span><span class="sxs-lookup"><span data-stu-id="607ce-166">This setting allows the [ImpersonationInfo](https://docs.microsoft.com/bi-reference/assl/properties/impersonationinfo-element-assl) element, a minor object, to be excluded from the data source defined in `ObjectDefinition`.</span></span> <span data-ttu-id="607ce-167">Поэтому в качестве данных об олицетворении для этого источника данных остается заданной учетная запись службы, как указано в первом примере.</span><span class="sxs-lookup"><span data-stu-id="607ce-167">Therefore, the impersonation information for that data source remains set to the service account, as specified in the first example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="607ce-168">См. также:</span><span class="sxs-lookup"><span data-stu-id="607ce-168">See Also</span></span>  
 <span data-ttu-id="607ce-169">[Метод Execute &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) </span><span class="sxs-lookup"><span data-stu-id="607ce-169">[Execute Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) </span></span>  
 <span data-ttu-id="607ce-170">[Разработка с помощью Analysis Services языка сценариев &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md) </span><span class="sxs-lookup"><span data-stu-id="607ce-170">[Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md) </span></span>  
 [<span data-ttu-id="607ce-171">Разработка с использованием XMLA в службах Analysis Services</span><span class="sxs-lookup"><span data-stu-id="607ce-171">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
