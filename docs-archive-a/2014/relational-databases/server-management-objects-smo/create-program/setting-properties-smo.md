---
title: Настройка свойств | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SMO [SQL Server], properties
- SQL Server Management Objects, properties
- properties [SMO]
ms.assetid: 342569ba-d2f7-44d2-8f3f-ae9c701c7f0f
author: stevestein
ms.author: sstein
ms.openlocfilehash: de381f8e4e9dfe9f6590638742e988f866ccabdc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735177"
---
# <a name="setting-properties"></a><span data-ttu-id="f27ef-102">Установка свойств</span><span class="sxs-lookup"><span data-stu-id="f27ef-102">Setting Properties</span></span>
  <span data-ttu-id="f27ef-103">Свойства — это значения, которые хранят описательные сведения об объекте.</span><span class="sxs-lookup"><span data-stu-id="f27ef-103">Properties are values that store descriptive information about the object.</span></span> <span data-ttu-id="f27ef-104">Например, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Параметры конфигурации представлены <xref:Microsoft.SqlServer.Management.Smo.Server.Configuration%2A> свойствами объекта.</span><span class="sxs-lookup"><span data-stu-id="f27ef-104">For example, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] configuration options are represented by the <xref:Microsoft.SqlServer.Management.Smo.Server.Configuration%2A> object's properties.</span></span> <span data-ttu-id="f27ef-105">К свойствам можно получать как прямой, так и косвенный доступ при помощи коллекции свойств.</span><span class="sxs-lookup"><span data-stu-id="f27ef-105">Properties can be accessed either directly or indirectly by using the property collection.</span></span> <span data-ttu-id="f27ef-106">Для прямого доступа к свойствам используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="f27ef-106">Accessing properties directly uses the following syntax:</span></span>  
  
 `objInstance.PropertyName`  
  
 <span data-ttu-id="f27ef-107">Значение свойства можно изменить или получить в зависимости от того, доступно ли свойство для чтения и записи или только для чтения.</span><span class="sxs-lookup"><span data-stu-id="f27ef-107">A property value can be modified or retrieved depending on whether the property has read/write access or read-only access.</span></span> <span data-ttu-id="f27ef-108">Кроме того, некоторые свойства необходимо задавать перед тем, как можно будет создать объект.</span><span class="sxs-lookup"><span data-stu-id="f27ef-108">It is also necessary to set certain properties before an object can be created.</span></span> <span data-ttu-id="f27ef-109">Дополнительные сведения о конкретном объекте см. в справочнике по объектам SMO.</span><span class="sxs-lookup"><span data-stu-id="f27ef-109">For more information, see the SMO reference for the particular object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f27ef-110">Коллекции дочерних объектов отображаются в виде свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="f27ef-110">Collections of child objects appear as the property of an object.</span></span> <span data-ttu-id="f27ef-111">Например, коллекция `Tables` является свойством объекта `Server`.</span><span class="sxs-lookup"><span data-stu-id="f27ef-111">For example, the `Tables` collection is a property of a `Server` object.</span></span> <span data-ttu-id="f27ef-112">Дополнительные сведения см. в разделе [Using Collections](using-collections.md).</span><span class="sxs-lookup"><span data-stu-id="f27ef-112">For more information, see [Using Collections](using-collections.md).</span></span>  
  
 <span data-ttu-id="f27ef-113">Свойства объекта являются элементами коллекции Properties.</span><span class="sxs-lookup"><span data-stu-id="f27ef-113">The properties of an object are members of the Properties collection.</span></span> <span data-ttu-id="f27ef-114">С помощью коллекции Properties можно просматривать все свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="f27ef-114">The Properties collection can be used to iterate through every property of an object.</span></span>  
  
 <span data-ttu-id="f27ef-115">Иногда свойство недоступно по следующим причинам.</span><span class="sxs-lookup"><span data-stu-id="f27ef-115">Sometimes a property is not available for the following reasons:</span></span>  
  
-   <span data-ttu-id="f27ef-116">Версия сервера не поддерживает это свойства (как при попытке получить доступ к свойству, которое представляет новую функцию [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] из более старой версии [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="f27ef-116">The server version does not support the property, such as if you try to access a property that represents a new [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] feature on an older version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="f27ef-117">Сервер не предоставляет данные для свойства (как при попытке доступа к свойству, представляющему компонент [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , который не установлен).</span><span class="sxs-lookup"><span data-stu-id="f27ef-117">The server does not provide data for the property, such as if you try to access a property that represents a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] component that is not installed.</span></span>  
  
 <span data-ttu-id="f27ef-118">Обрабатывать эти ситуации можно путем перехвата исключений SMO <xref:Microsoft.SqlServer.Management.Smo.UnknownPropertyException> и <xref:Microsoft.SqlServer.Management.Smo.PropertyCannotBeRetrievedException>.</span><span class="sxs-lookup"><span data-stu-id="f27ef-118">You can handle these circumstances by catching the <xref:Microsoft.SqlServer.Management.Smo.UnknownPropertyException> and the <xref:Microsoft.SqlServer.Management.Smo.PropertyCannotBeRetrievedException> SMO exceptions.</span></span>  
  
## <a name="setting-default-initialization-fields"></a><span data-ttu-id="f27ef-119">Задание полей инициализации по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f27ef-119">Setting Default Initialization Fields</span></span>  
 <span data-ttu-id="f27ef-120">При получении объектов SMO выполняет оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="f27ef-120">SMO performs an optimization when retrieving objects.</span></span> <span data-ttu-id="f27ef-121">Оптимизация заключается в сведении к минимуму загружаемых свойств за счет автоматического масштабирования между следующими состояниями.</span><span class="sxs-lookup"><span data-stu-id="f27ef-121">The optimization minimizes the number of properties loaded by automatically scaling between the following states:</span></span>  
  
1.  <span data-ttu-id="f27ef-122">Частично загружено.</span><span class="sxs-lookup"><span data-stu-id="f27ef-122">Partially loaded.</span></span> <span data-ttu-id="f27ef-123">При первой ссылке на объект выдается минимум свойств (например, имя и схема).</span><span class="sxs-lookup"><span data-stu-id="f27ef-123">When an object is first referenced it has a minimum of properties available (such as Name and Schema).</span></span>  
  
2.  <span data-ttu-id="f27ef-124">Полностью загружено.</span><span class="sxs-lookup"><span data-stu-id="f27ef-124">Fully loaded.</span></span> <span data-ttu-id="f27ef-125">При ссылке на любое свойство остальные свойства, которые можно быстро загрузить, инициализируются и делаются доступными.</span><span class="sxs-lookup"><span data-stu-id="f27ef-125">When any property is referenced, the remaining properties that are quick to load, are initialized and are made available.</span></span>  
  
3.  <span data-ttu-id="f27ef-126">Свойства, использующие много памяти.</span><span class="sxs-lookup"><span data-stu-id="f27ef-126">Properties that use lots of memory.</span></span> <span data-ttu-id="f27ef-127">Остальные недоступные свойства используют значительный объем памяти, а свойство <xref:Microsoft.SqlServer.Management.Smo.Property.Expensive%2A> в них имеет значение TRUE (например, <xref:Microsoft.SqlServer.Management.Smo.Database.DataSpaceUsage%2A>).</span><span class="sxs-lookup"><span data-stu-id="f27ef-127">The remaining unavailable properties use lots of memory and have an <xref:Microsoft.SqlServer.Management.Smo.Property.Expensive%2A> property value of true (such as <xref:Microsoft.SqlServer.Management.Smo.Database.DataSpaceUsage%2A>).</span></span> <span data-ttu-id="f27ef-128">Эти свойства загружаются только тогда, когда на них производится ссылка.</span><span class="sxs-lookup"><span data-stu-id="f27ef-128">These properties are loaded only when specifically referenced.</span></span>  
  
 <span data-ttu-id="f27ef-129">Если приложение загружает дополнительные свойства помимо тех, которые представлены в состоянии частичной загрузки, оно отправляет запрос для получения этих дополнительных свойств и масштабируется до состояния полной загрузки.</span><span class="sxs-lookup"><span data-stu-id="f27ef-129">If your application does fetch extra properties, besides the ones provided in the partially loaded state, it submits a query to retrieve these extra properties and scales up to the fully loaded state.</span></span> <span data-ttu-id="f27ef-130">Это может привести к образованию ненужного трафика между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="f27ef-130">This can cause unnecessary traffic between the client and server.</span></span> <span data-ttu-id="f27ef-131">Дополнительную оптимизацию можно достичь за счет вызова метода <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A>.</span><span class="sxs-lookup"><span data-stu-id="f27ef-131">More optimization can be achieved by calling the <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> method.</span></span> <span data-ttu-id="f27ef-132">Метод <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> позволяет создавать спецификацию свойств, которые загружаются при инициализации объекта.</span><span class="sxs-lookup"><span data-stu-id="f27ef-132">The <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> method allows specification of the properties that are loaded when the object is initialized.</span></span>  
  
 <span data-ttu-id="f27ef-133">Метод <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> задает поведение при загрузке свойств для остальной части приложения или до его сброса.</span><span class="sxs-lookup"><span data-stu-id="f27ef-133">The <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> method sets the property loading behavior for the rest of application or until it is reset.</span></span> <span data-ttu-id="f27ef-134">Первоначальное поведение можно сохранить с помощью метода <xref:Microsoft.SqlServer.Management.Smo.Server.GetDefaultInitFields%2A> и восстановить его при необходимости.</span><span class="sxs-lookup"><span data-stu-id="f27ef-134">You can save the original behavior by using the <xref:Microsoft.SqlServer.Management.Smo.Server.GetDefaultInitFields%2A> method and restore it as required.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f27ef-135">Примеры</span><span class="sxs-lookup"><span data-stu-id="f27ef-135">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="getting-and-setting-a-property-in-visual-basic"></a><span data-ttu-id="f27ef-136">Возвращение и задание свойства на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f27ef-136">Getting and Setting a Property in Visual Basic</span></span>  
 <span data-ttu-id="f27ef-137">Этот пример кода демонстрирует возвращение свойства <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> объекта <xref:Microsoft.SqlServer.Management.Smo.Information> и установку свойства <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> в свойстве <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> в элемент `ExecuteSql` перечислимого типа <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes>.</span><span class="sxs-lookup"><span data-stu-id="f27ef-137">This code example shows how to get the <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Information> object and how to set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> property to the `ExecuteSql` member of the <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes> enumerated type.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties1](SMO How to#SMO_VBProperties1)]  -->  
  
## <a name="getting-and-setting-a-property-in-visual-c"></a><span data-ttu-id="f27ef-138">Возвращение и задание свойства на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="f27ef-138">Getting and Setting a Property in Visual C#</span></span>  
 <span data-ttu-id="f27ef-139">Этот пример кода демонстрирует возвращение свойства <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> объекта <xref:Microsoft.SqlServer.Management.Smo.Information> и установку свойства <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> в свойстве <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> в элемент `ExecuteSql` перечислимого типа <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes>.</span><span class="sxs-lookup"><span data-stu-id="f27ef-139">This code example shows how to get the <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Information> object and how to set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> property to the `ExecuteSql` member of the <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes> enumerated type.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Get a property.   
Console.WriteLine(srv.Information.Version);   
//Set a property.   
srv.ConnectionContext.SqlExecutionModes = SqlExecutionModes.ExecuteSql;   
}  
```  
  
## <a name="setting-various-properties-before-an-object-is-created-in-visual-basic"></a><span data-ttu-id="f27ef-140">Задание различных свойств перед созданием объекта на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f27ef-140">Setting Various Properties Before an Object is Created in Visual Basic</span></span>  
 <span data-ttu-id="f27ef-141">В этом примере кода показана непосредственная установка свойства <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> объекта <xref:Microsoft.SqlServer.Management.Smo.Table>, а также создание и добавление столбцов перед созданием объекта <xref:Microsoft.SqlServer.Management.Smo.Table>.</span><span class="sxs-lookup"><span data-stu-id="f27ef-141">This code example shows how to directly set the <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Table> object, and how to create and add columns before you create the <xref:Microsoft.SqlServer.Management.Smo.Table> object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties2](SMO How to#SMO_VBProperties2)]  -->  
  
## <a name="setting-various-properties-before-an-object-is-created-in-visual-c"></a><span data-ttu-id="f27ef-142">Задание различных свойств перед созданием объекта на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="f27ef-142">Setting Various Properties Before an Object is Created in Visual C#</span></span>  
 <span data-ttu-id="f27ef-143">В этом примере кода показана непосредственная установка свойства <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> объекта <xref:Microsoft.SqlServer.Management.Smo.Table>, а также создание и добавление столбцов перед созданием объекта <xref:Microsoft.SqlServer.Management.Smo.Table>.</span><span class="sxs-lookup"><span data-stu-id="f27ef-143">This code example shows how to directly set the <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Table> object, and how to create and add columns before you create the <xref:Microsoft.SqlServer.Management.Smo.Table> object.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Create a new table in the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
Table tb;   
//Specify the parent database, table schema, and the table name in the constructor.   
tb = new Table(db, "Test_Table", "HumanResources");   
//Add columns because the table requires columns before it can be created.   
Column c1;   
//Specify the parent table, the column name, and data type in the constructor.   
c1 = new Column(tb, "ID", DataType.Int);   
tb.Columns.Add(c1);   
c1.Nullable = false;   
c1.Identity = true;   
c1.IdentityIncrement = 1;   
c1.IdentitySeed = 0;   
Column c2;   
c2 = new Column(tb, "Name", DataType.NVarChar(100));   
c2.Nullable = false;   
tb.Columns.Add(c2);   
tb.AnsiNullsStatus = true;   
//Create the table on the instance of SQL Server.   
tb.Create();   
}  
```  
  
## <a name="iterating-through-all-properties-of-an-object-in-visual-basic"></a><span data-ttu-id="f27ef-144">Проход по всем свойствам объекта на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f27ef-144">Iterating Through All Properties of an Object in Visual Basic</span></span>  
 <span data-ttu-id="f27ef-145">Этот пример кода проходит по коллекции `Properties` объекта <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> и отображает свойства на экране вывода [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f27ef-145">This code example iterates through the `Properties` collection of the <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> object and displays them on the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Output screen.</span></span>  
  
 <span data-ttu-id="f27ef-146">В этом примере объект <xref:Microsoft.SqlServer.Management.Smo.Property> заключен в квадратные скобки, поскольку он также является ключевым словом [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f27ef-146">In the example, the <xref:Microsoft.SqlServer.Management.Smo.Property> object has been put in square parentheses because it is also a [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] keyword.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties3](SMO How to#SMO_VBProperties3)]  -->  
  
## <a name="iterating-through-all-properties-of-an-object-in-visual-c"></a><span data-ttu-id="f27ef-147">Проход по всем свойствам объекта на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="f27ef-147">Iterating Through All Properties of an Object in Visual C#</span></span>  
 <span data-ttu-id="f27ef-148">Этот пример кода проходит по коллекции `Properties` объекта <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> и отображает свойства на экране вывода [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f27ef-148">This code example iterates through the `Properties` collection of the <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> object and displays them on the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Output screen.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Set properties on the uspGetEmployeedManagers stored procedure on the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
StoredProcedure sp;   
sp = db.StoredProcedures("uspGetEmployeeManagers");   
sp.AnsiNullsStatus = false;   
sp.QuotedIdentifierStatus = false;   
//Iterate through the properties of the stored procedure and display.   
  Property p;   
  foreach ( p in sp.Properties) {   
    Console.WriteLine(p.Name + p.Value);   
  }   
}  
```  
  
## <a name="setting-default-initialization-fields-in-visual-basic"></a><span data-ttu-id="f27ef-149">Задание полей инициализации по умолчанию на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f27ef-149">Setting Default Initialization Fields in Visual Basic</span></span>  
 <span data-ttu-id="f27ef-150">Этот пример кода демонстрирует, как свести к минимуму число свойств объекта, инициализируемых в программе SMO.</span><span class="sxs-lookup"><span data-stu-id="f27ef-150">This code example shows how to minimize the number of object properties initialized in an SMO program.</span></span> <span data-ttu-id="f27ef-151">Чтобы использовать объект <xref:System.Collections.Specialized.StringCollection>, необходимо включить инструкцию `using System.Collections.Specialized`.</span><span class="sxs-lookup"><span data-stu-id="f27ef-151">You have to include the `using System.Collections.Specialized`; statement to use the <xref:System.Collections.Specialized.StringCollection> object.</span></span>  
  
 <span data-ttu-id="f27ef-152">При помощи приложения [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] можно сравнивать числовые инструкции, оправляемые экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], с этой оптимизацией.</span><span class="sxs-lookup"><span data-stu-id="f27ef-152">[!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] can be used to compare the number statements sent to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with this optimization.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDefaultInitFields1](SMO How to#SMO_VBDefaultInitFields1)]  -->  
  
## <a name="setting-default-initialization-fields-in-visual-c"></a><span data-ttu-id="f27ef-153">Задание полей инициализации по умолчанию на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="f27ef-153">Setting Default Initialization Fields in Visual C#</span></span>  
 <span data-ttu-id="f27ef-154">Этот пример кода демонстрирует, как свести к минимуму число свойств объекта, инициализируемых в программе SMO.</span><span class="sxs-lookup"><span data-stu-id="f27ef-154">This code example shows how to minimize the number of object properties initialized in an SMO program.</span></span> <span data-ttu-id="f27ef-155">Чтобы использовать объект <xref:System.Collections.Specialized.StringCollection>, необходимо включить инструкцию `using System.Collections.Specialized`.</span><span class="sxs-lookup"><span data-stu-id="f27ef-155">You have to include the `using System.Collections.Specialized`; statement to use the <xref:System.Collections.Specialized.StringCollection> object.</span></span>  
  
 <span data-ttu-id="f27ef-156">При помощи приложения [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] можно сравнивать числовые инструкции, оправляемые экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], с этой оптимизацией.</span><span class="sxs-lookup"><span data-stu-id="f27ef-156">[!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] can be used to compare the number statements sent to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with this optimization.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Reference the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
//Assign the Table object type to a System.Type object variable.   
Table tb;   
Type typ;   
tb = new Table();   
typ = tb.GetType;   
//Assign the current default initialization fields for the Table object type to a   
//StringCollection object variable.   
StringCollection sc;   
sc = srv.GetDefaultInitFields(typ);   
//Set the default initialization fields for the Table object type to the CreateDate property.   
srv.SetDefaultInitFields(typ, "CreateDate");   
//Retrieve the Schema, Name, and CreateDate properties for every table in AdventureWorks2012.   
   //Note that the improvement in performance can be viewed in SQL Server Profiler.   
foreach ( tb in db.Tables) {   
   Console.WriteLine(tb.Schema + "." + tb.Name + " " + tb.CreateDate);   
}   
//Set the default initialization fields for the Table object type back to the original settings.   
srv.SetDefaultInitFields(typ, sc);   
}  
```  
  
  
