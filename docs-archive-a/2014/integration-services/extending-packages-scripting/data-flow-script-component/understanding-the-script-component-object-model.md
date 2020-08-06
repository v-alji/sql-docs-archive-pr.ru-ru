---
title: Основные сведения о модели COM скриптов | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], object model
ms.assetid: 2a0aae82-39cc-4423-b09a-72d2f61033bd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a11556b00efc5749e8ddb895712d6c61f2459d8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658905"
---
# <a name="understanding-the-script-component-object-model"></a><span data-ttu-id="32dcc-102">Основные сведения о модели объектов компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="32dcc-102">Understanding the Script Component Object Model</span></span>
  <span data-ttu-id="32dcc-103">Как описано в разделе [написание кода и отладка компонента скрипта] (.. /екстендинг-паккажес-скриптинг/Дата-Флов-скрипт-компонент/кодинг-Анд-дебуггинг-СЕ-скрипт-компонент.МД, проект компонента скрипта содержит три элемента проекта:</span><span class="sxs-lookup"><span data-stu-id="32dcc-103">As discussed in [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md, the Script component project contains three project items:</span></span>

1.  <span data-ttu-id="32dcc-104">Элемент `ScriptMain`, который содержит класс `ScriptMain` для создания кода.</span><span class="sxs-lookup"><span data-stu-id="32dcc-104">The `ScriptMain` item, which contains the `ScriptMain` class in which you write your code.</span></span> <span data-ttu-id="32dcc-105">Класс `ScriptMain` наследуется от класса `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="32dcc-105">The `ScriptMain` class inherits from the `UserComponent` class.</span></span>

2.  <span data-ttu-id="32dcc-106">Элемент `ComponentWrapper`, который содержит класс `UserComponent`, экземпляр объекта <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>, который содержит методы и свойства для обработки данных и взаимодействия с пакетом.</span><span class="sxs-lookup"><span data-stu-id="32dcc-106">The `ComponentWrapper` item, which contains the `UserComponent` class, an instance of <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> that contains the methods and properties that you will use to process data and to interact with the package.</span></span> <span data-ttu-id="32dcc-107">Элемент `ComponentWrapper` содержит также классы коллекций `Connections` и `Variables`.</span><span class="sxs-lookup"><span data-stu-id="32dcc-107">The `ComponentWrapper` item also contains `Connections` and `Variables` collection classes.</span></span>

3.  <span data-ttu-id="32dcc-108">Элемент `BufferWrapper`, который содержит классы, унаследованные от класса <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> для каждого входа и выхода и типизированные свойства для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="32dcc-108">The `BufferWrapper` item, which contains classes that inherits from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> for each input and output, and typed properties for each column.</span></span>

 <span data-ttu-id="32dcc-109">При создании кода для элемента `ScriptMain` используются объекты, методы и свойства, обсуждаемые в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="32dcc-109">As you write your code in the `ScriptMain` item, you will use the objects, methods, and properties discussed in this topic.</span></span> <span data-ttu-id="32dcc-110">Компонент может использовать не все перечисленные здесь методы. Однако если они используются, то используются в указанной последовательности.</span><span class="sxs-lookup"><span data-stu-id="32dcc-110">Each component will not use all the methods listed here; however, when used, they are used in the sequence shown.</span></span>

 <span data-ttu-id="32dcc-111">Базовый класс <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> не содержит кода, реализующего методы, которые обсуждаются в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="32dcc-111">The <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class does not contain any implementation code for the methods discussed in this topic.</span></span> <span data-ttu-id="32dcc-112">Поэтому вызов базового класса в вашей собственной реализации этого метода не обязателен, но безопасен.</span><span class="sxs-lookup"><span data-stu-id="32dcc-112">Therefore it is unnecessary, but harmless, to add a call to the base class implementation to your own implementation of the method.</span></span>

 <span data-ttu-id="32dcc-113">Сведения об использовании методов и свойств этих классов в компоненте скрипта определенного типа см. в разделе [Дополнительные примеры компонента скрипта](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span><span class="sxs-lookup"><span data-stu-id="32dcc-113">For information about how to use the methods and properties of these classes in a particular type of Script component, see the section [Additional Script Component Examples](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span></span> <span data-ttu-id="32dcc-114">В разделах примеров также приведен полный образец кода.</span><span class="sxs-lookup"><span data-stu-id="32dcc-114">The example topics also contain complete code samples.</span></span>

## <a name="acquireconnections-method"></a><span data-ttu-id="32dcc-115">Метод AcquireConnections</span><span class="sxs-lookup"><span data-stu-id="32dcc-115">AcquireConnections Method</span></span>
 <span data-ttu-id="32dcc-116">Источники и назначения обычно должны быть соединены с внешним источником данных.</span><span class="sxs-lookup"><span data-stu-id="32dcc-116">Sources and destinations generally must connect to an external data source.</span></span> <span data-ttu-id="32dcc-117">Переопределите метод <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A> базового класса <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>, чтобы получить соединение или сведения о соединении из соответствующего диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="32dcc-117">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class to retrieve the connection or the connection information from the appropriate connection manager.</span></span>

 <span data-ttu-id="32dcc-118">Следующий пример возвращает соединение `System.Data.SqlClient.SqlConnection` из диспетчера соединений ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="32dcc-118">The following example returns a `System.Data.SqlClient.SqlConnection` from an ADO.NET connection manager.</span></span>

```vb
Dim connMgr As IDTSConnectionManager100
Dim sqlConn As SqlConnection

Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

    connMgr = Me.Connections.MyADONETConnection
    sqlConn = CType(connMgr.AcquireConnection(Nothing), SqlConnection)

End Sub
```

 <span data-ttu-id="32dcc-119">Следующий пример возвращает полный путь и имя файла из диспетчера соединений с неструктурированными файлами, после чего открывает соответствующий файл с помощью объекта `System.IO.StreamReader`.</span><span class="sxs-lookup"><span data-stu-id="32dcc-119">The following example returns a complete path and file name from a Flat File Connection Manager, and then opens the file by using a `System.IO.StreamReader`.</span></span>

```vb
Private textReader As StreamReader
Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

    Dim connMgr As IDTSConnectionManager100 = _
        Me.Connections.MyFlatFileSrcConnectionManager
    Dim exportedAddressFile As String = _
        CType(connMgr.AcquireConnection(Nothing), String)
    textReader = New StreamReader(exportedAddressFile)

End Sub
```

## <a name="preexecute-method"></a><span data-ttu-id="32dcc-120">Метод PreExecute</span><span class="sxs-lookup"><span data-stu-id="32dcc-120">PreExecute Method</span></span>
 <span data-ttu-id="32dcc-121">Переопределите метод <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PreExecute%2A> базового класса <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>, если необходимо однократно выполнить некоторые действия перед началом обработки строк данных.</span><span class="sxs-lookup"><span data-stu-id="32dcc-121">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PreExecute%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class whenever you have processing that you must perform one time only before you start processing rows of data.</span></span> <span data-ttu-id="32dcc-122">Например, в назначении может потребоваться настроить параметризованную команду, которая будет использоваться назначением для вставки строк данных в источник данных.</span><span class="sxs-lookup"><span data-stu-id="32dcc-122">For example, in a destination, you may want to configure the parameterized command that the destination will use to insert each row of data into the data source.</span></span>

```vb
    Dim sqlConn As SqlConnection
    Dim sqlCmd As SqlCommand
    Dim sqlParam As SqlParameter
...
    Public Overrides Sub PreExecute()

        sqlCmd = New SqlCommand("INSERT INTO Person.Address2(AddressID, City) " & _
            "VALUES(@addressid, @city)", sqlConn)
        sqlParam = New SqlParameter("@addressid", SqlDbType.Int)
        sqlCmd.Parameters.Add(sqlParam)
        sqlParam = New SqlParameter("@city", SqlDbType.NVarChar, 30)
        sqlCmd.Parameters.Add(sqlParam)

    End Sub
```

```csharp
SqlConnection sqlConn; 
SqlCommand sqlCmd; 
SqlParameter sqlParam; 

public override void PreExecute() 
{ 

    sqlCmd = new SqlCommand("INSERT INTO Person.Address2(AddressID, City) " + "VALUES(@addressid, @city)", sqlConn); 
    sqlParam = new SqlParameter("@addressid", SqlDbType.Int); 
    sqlCmd.Parameters.Add(sqlParam); 
    sqlParam = new SqlParameter("@city", SqlDbType.NVarChar, 30); 
    sqlCmd.Parameters.Add(sqlParam); 

}
```

## <a name="processing-inputs-and-outputs"></a><span data-ttu-id="32dcc-123">Обработка входов и выходов</span><span class="sxs-lookup"><span data-stu-id="32dcc-123">Processing Inputs and Outputs</span></span>

### <a name="processing-inputs"></a><span data-ttu-id="32dcc-124">Обработка входов</span><span class="sxs-lookup"><span data-stu-id="32dcc-124">Processing Inputs</span></span>
 <span data-ttu-id="32dcc-125">Компоненты скрипта, настроенные как преобразования или назначения, имеют один вход.</span><span class="sxs-lookup"><span data-stu-id="32dcc-125">Script components that are configured as transformations or destinations have one input.</span></span>

#### <a name="what-the-bufferwrapper-project-item-provides"></a><span data-ttu-id="32dcc-126">Содержимое элемента проекта BufferWrapper</span><span class="sxs-lookup"><span data-stu-id="32dcc-126">What the BufferWrapper Project Item Provides</span></span>
 <span data-ttu-id="32dcc-127">Для каждого настроенного входа элемент проекта `BufferWrapper` содержит класс, порожденный от класса <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> и совпадающий по имени с входом.</span><span class="sxs-lookup"><span data-stu-id="32dcc-127">For each input that you have configured, the `BufferWrapper` project item contains a class that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> and has the same name as the input.</span></span> <span data-ttu-id="32dcc-128">Каждый класс входного буфера содержит перечисленные далее свойства, функции и методы.</span><span class="sxs-lookup"><span data-stu-id="32dcc-128">Each input buffer class contains the following properties, functions, and methods:</span></span>

-   <span data-ttu-id="32dcc-129">Именованные и типизированные свойства метода доступа для каждого выбранного входного столбца.</span><span class="sxs-lookup"><span data-stu-id="32dcc-129">Named, typed accessor properties for each selected input column.</span></span> <span data-ttu-id="32dcc-130">Эти свойства доступны только для чтения или для чтения и записи в зависимости от **типа применения**, указанного для столбца на странице **Входные столбцы** диалогового окна **Редактор преобразования "скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="32dcc-130">These properties are read-only or read/write depending on the **Usage Type** specified for the column on the **Input Columns** page of the **Script Transformation Editor**.</span></span>

-   <span data-ttu-id="32dcc-131">Свойство **\<column>_IsNull** для каждого выбранного входного столбца.</span><span class="sxs-lookup"><span data-stu-id="32dcc-131">A **\<column>_IsNull** property for each selected input column.</span></span> <span data-ttu-id="32dcc-132">Это свойство также доступно только для чтения или для чтения и записи в зависимости от **типа применения**, указанного для этого столбца.</span><span class="sxs-lookup"><span data-stu-id="32dcc-132">This property is also read-only or read/write depending on the **Usage Type** specified for the column.</span></span>

-   <span data-ttu-id="32dcc-133">Метод **DirectRowTo\<outputbuffer>** для каждого настроенного выхода.</span><span class="sxs-lookup"><span data-stu-id="32dcc-133">A **DirectRowTo\<outputbuffer>** method for each configured output.</span></span> <span data-ttu-id="32dcc-134">Эти методы используются при фильтрации строк в один или несколько выходов одной и той же группы `ExclusionGroup`.</span><span class="sxs-lookup"><span data-stu-id="32dcc-134">You will use these methods when filtering rows to one of several outputs in the same `ExclusionGroup`.</span></span>

-   <span data-ttu-id="32dcc-135">Функция `NextRow` для получения следующей входной строки и функция `EndOfRowset` для определения того, был ли обработан последний буфер данных.</span><span class="sxs-lookup"><span data-stu-id="32dcc-135">A `NextRow` function to get the next input row, and an `EndOfRowset` function to determine whether the last buffer of data has been processed.</span></span> <span data-ttu-id="32dcc-136">Обычно эти функции не нужны, если используются методы обработки ввода, реализованные в базовом классе `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="32dcc-136">You typically do not need these functions when you use the input processing methods implemented in the `UserComponent` base class.</span></span> <span data-ttu-id="32dcc-137">В следующем разделе приводится более подробная информация о базовом классе `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="32dcc-137">The next section provides more information about the `UserComponent` base class.</span></span>

#### <a name="what-the-componentwrapper-project-item-provides"></a><span data-ttu-id="32dcc-138">Содержимое элемента проекта ComponentWrapper</span><span class="sxs-lookup"><span data-stu-id="32dcc-138">What the ComponentWrapper Project Item Provides</span></span>
 <span data-ttu-id="32dcc-139">Элемент проекта ComponentWrapper содержит класс с именем `UserComponent`, производный от класса <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="32dcc-139">The ComponentWrapper project item contains a class named `UserComponent` that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span></span> <span data-ttu-id="32dcc-140">Класс `ScriptMain`, в котором создается пользовательский код, в свою очередь, является производным от класса `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="32dcc-140">The `ScriptMain` class in which you write your custom code derives in turn from `UserComponent`.</span></span> <span data-ttu-id="32dcc-141">Класс `UserComponent` содержит следующие методы.</span><span class="sxs-lookup"><span data-stu-id="32dcc-141">The `UserComponent` class contains the following methods:</span></span>

-   <span data-ttu-id="32dcc-142">Переопределенная реализация метода `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="32dcc-142">An overridden implementation of the `ProcessInput` method.</span></span> <span data-ttu-id="32dcc-143">Этот метод вызывается подсистемой обработки потока данных во время выполнения сразу за методом `PreExecute`. Он может быть вызван более одного раза.</span><span class="sxs-lookup"><span data-stu-id="32dcc-143">This is the method that the data flow engine calls next at run time after the `PreExecute` method, and it may be called multiple times.</span></span> <span data-ttu-id="32dcc-144">`ProcessInput`передает обработку методу \*\* \<inputbuffer> _ProcessInput\*\* .</span><span class="sxs-lookup"><span data-stu-id="32dcc-144">`ProcessInput` hands off processing to the **\<inputbuffer>_ProcessInput** method.</span></span> <span data-ttu-id="32dcc-145">После этого метод `ProcessInput` проверяет, достигнут ли конец входного буфера, и в этом случае вызывает переопределяемый метод `FinishOutputs`, а также частный метод `MarkOutputsAsFinished`.</span><span class="sxs-lookup"><span data-stu-id="32dcc-145">Then the `ProcessInput` method checks for the end of the input buffer and, if the end of the buffer has been reached, calls the overridable `FinishOutputs` method and the private `MarkOutputsAsFinished` method.</span></span> <span data-ttu-id="32dcc-146">Затем метод `MarkOutputsAsFinished` вызывает метод `SetEndOfRowset` для последнего выходного буфера.</span><span class="sxs-lookup"><span data-stu-id="32dcc-146">The `MarkOutputsAsFinished` method then calls `SetEndOfRowset` on the last output buffer.</span></span>

-   <span data-ttu-id="32dcc-147">Переопределяемая реализация метода **\<inputbuffer>_ProcessInput**.</span><span class="sxs-lookup"><span data-stu-id="32dcc-147">An overridable implementation of the **\<inputbuffer>_ProcessInput** method.</span></span> <span data-ttu-id="32dcc-148">Эта реализация по умолчанию просто перебирает входящие строки и вызывает метод **\<inputbuffer>_ProcessInputRow**.</span><span class="sxs-lookup"><span data-stu-id="32dcc-148">This default implementation simply loops through each input row and calls **\<inputbuffer>_ProcessInputRow**.</span></span>

-   <span data-ttu-id="32dcc-149">Переопределяемая реализация метода **\<inputbuffer>_ProcessInputRow**.</span><span class="sxs-lookup"><span data-stu-id="32dcc-149">An overridable implementation of the **\<inputbuffer>_ProcessInputRow** method.</span></span> <span data-ttu-id="32dcc-150">Реализация по умолчанию пуста.</span><span class="sxs-lookup"><span data-stu-id="32dcc-150">The default implementation is empty.</span></span> <span data-ttu-id="32dcc-151">Этот метод обычно переопределяется, чтобы написать пользовательский код обработки данных.</span><span class="sxs-lookup"><span data-stu-id="32dcc-151">This is the method that you will normally override to write your custom data processing code.</span></span>

#### <a name="what-your-custom-code-should-do"></a><span data-ttu-id="32dcc-152">Задачи, выполняемые в пользовательском коде</span><span class="sxs-lookup"><span data-stu-id="32dcc-152">What Your Custom Code Should Do</span></span>
 <span data-ttu-id="32dcc-153">Для обработки входа в классе `ScriptMain` можно использовать перечисленные далее методы.</span><span class="sxs-lookup"><span data-stu-id="32dcc-153">You can use the following methods to process input in the `ScriptMain` class:</span></span>

-   <span data-ttu-id="32dcc-154">Переопределите метод **\<inputbuffer>_ProcessInputRow** для обработки данных в каждой входной строке по мере ее прохождения.</span><span class="sxs-lookup"><span data-stu-id="32dcc-154">Override **\<inputbuffer>_ProcessInputRow** to process the data in each input row as it passes through.</span></span>

-   <span data-ttu-id="32dcc-155">Переопределите метод **\<inputbuffer>_ProcessInput**, только если необходимо выполнять дополнительные действия по мере перебора входных строк.</span><span class="sxs-lookup"><span data-stu-id="32dcc-155">Override **\<inputbuffer>_ProcessInput** only if you have to do something additional while looping through input rows.</span></span> <span data-ttu-id="32dcc-156">(Например, необходимо протестировать `EndOfRowset` , чтобы выполнить какое-либо другое действие после обработки всех строк.) Вызовите \*\* \<inputbuffer> _ProcessInputRow\*\* для выполнения обработки строк.</span><span class="sxs-lookup"><span data-stu-id="32dcc-156">(For example, you have to test for `EndOfRowset` to take some other action after all rows have been processed.) Call **\<inputbuffer>_ProcessInputRow** to perform the row processing.</span></span>

-   <span data-ttu-id="32dcc-157">Переопределите метод `FinishOutputs`, если нужно выполнять действия с выходами перед их закрытием.</span><span class="sxs-lookup"><span data-stu-id="32dcc-157">Override `FinishOutputs` if you have to do something to the outputs before they are closed.</span></span>

 <span data-ttu-id="32dcc-158">Метод `ProcessInput` обеспечивает, что эти методы будут вызываться в нужное время.</span><span class="sxs-lookup"><span data-stu-id="32dcc-158">The `ProcessInput` method ensures that these methods are called at the appropriate times.</span></span>

### <a name="processing-outputs"></a><span data-ttu-id="32dcc-159">Обработка выходов</span><span class="sxs-lookup"><span data-stu-id="32dcc-159">Processing Outputs</span></span>
 <span data-ttu-id="32dcc-160">Компоненты скрипта, настроенные в качестве источников или преобразований, имеют один или несколько выходов.</span><span class="sxs-lookup"><span data-stu-id="32dcc-160">Script components configured as sources or transformations have one or more outputs.</span></span>

#### <a name="what-the-bufferwrapper-project-item-provides"></a><span data-ttu-id="32dcc-161">Содержимое элемента проекта BufferWrapper</span><span class="sxs-lookup"><span data-stu-id="32dcc-161">What the BufferWrapper Project Item Provides</span></span>
 <span data-ttu-id="32dcc-162">Для каждого настроенного выхода элемент проекта BufferWrapper содержит класс, порожденный от класса <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> и совпадающий по имени с выходом.</span><span class="sxs-lookup"><span data-stu-id="32dcc-162">For each output that you have configured, the BufferWrapper project item contains a class that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> and has the same name as the output.</span></span> <span data-ttu-id="32dcc-163">Каждый класс входного буфера содержит перечисленные далее свойства и методы.</span><span class="sxs-lookup"><span data-stu-id="32dcc-163">Each input buffer class contains the following properties and methods:</span></span>

-   <span data-ttu-id="32dcc-164">Именованные и типизированные свойства метода доступа только для записи для каждого выходного столбца.</span><span class="sxs-lookup"><span data-stu-id="32dcc-164">Named, typed, write-only accessor properties for each output column.</span></span>

-   <span data-ttu-id="32dcc-165">Свойство \*\* \<column> _IsNull\*\* только для записи для каждого выбранного выходного столбца, которое можно использовать для задания значения столбца `null` .</span><span class="sxs-lookup"><span data-stu-id="32dcc-165">A write-only **\<column>_IsNull** property for each selected output column that you can use to set the column value to `null`.</span></span>

-   <span data-ttu-id="32dcc-166">Метод `AddRow` для добавления новой пустой строки в выходной буфер.</span><span class="sxs-lookup"><span data-stu-id="32dcc-166">An `AddRow` method to add an empty new row to the output buffer.</span></span>

-   <span data-ttu-id="32dcc-167">Метод `SetEndOfRowset` для оповещения подсистемы обработки потока данных о том, что буферов данных больше не ожидается.</span><span class="sxs-lookup"><span data-stu-id="32dcc-167">A `SetEndOfRowset` method to let the data flow engine know that no more buffers of data are expected.</span></span> <span data-ttu-id="32dcc-168">Имеется также функция `EndOfRowset` для определения того, является ли текущий буфер данных последним.</span><span class="sxs-lookup"><span data-stu-id="32dcc-168">There is also an `EndOfRowset` function to determine whether the current buffer is the last buffer of data.</span></span> <span data-ttu-id="32dcc-169">Обычно эти функции не нужны, если используются методы обработки ввода, реализованные в базовом классе `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="32dcc-169">You generally do not need these functions when you use the input processing methods implemented in the `UserComponent` base class.</span></span>

#### <a name="what-the-componentwrapper-project-item-provides"></a><span data-ttu-id="32dcc-170">Содержимое элемента проекта ComponentWrapper</span><span class="sxs-lookup"><span data-stu-id="32dcc-170">What the ComponentWrapper Project Item Provides</span></span>
 <span data-ttu-id="32dcc-171">Элемент проекта ComponentWrapper содержит класс с именем `UserComponent`, производный от класса <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="32dcc-171">The ComponentWrapper project item contains a class named `UserComponent` that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span></span> <span data-ttu-id="32dcc-172">Класс `ScriptMain`, в котором создается пользовательский код, в свою очередь, является производным от класса `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="32dcc-172">The `ScriptMain` class in which you write your custom code derives in turn from `UserComponent`.</span></span> <span data-ttu-id="32dcc-173">Класс `UserComponent` содержит следующие методы.</span><span class="sxs-lookup"><span data-stu-id="32dcc-173">The `UserComponent` class contains the following methods:</span></span>

-   <span data-ttu-id="32dcc-174">Переопределенная реализация метода `PrimeOutput`.</span><span class="sxs-lookup"><span data-stu-id="32dcc-174">An overridden implementation of the `PrimeOutput` method.</span></span> <span data-ttu-id="32dcc-175">Подсистема обработки потока данных вызывает этот метод перед методом `ProcessInput` во время выполнения. Он вызывается только один раз.</span><span class="sxs-lookup"><span data-stu-id="32dcc-175">The data flow engine calls this method before `ProcessInput` at run time, and it is only called one time.</span></span> <span data-ttu-id="32dcc-176">`PrimeOutput` передает обработку методу `CreateNewOutputRows`.</span><span class="sxs-lookup"><span data-stu-id="32dcc-176">`PrimeOutput` hands off processing to the `CreateNewOutputRows` method.</span></span> <span data-ttu-id="32dcc-177">Затем, если компонент является источником (то есть не имеет входов), `PrimeOutput` вызывает переопределяемый метод `FinishOutputs` и частный метод `MarkOutputsAsFinished`.</span><span class="sxs-lookup"><span data-stu-id="32dcc-177">Then, if the component is a source (that is, the component has no inputs), `PrimeOutput` calls the overridable `FinishOutputs` method and the private `MarkOutputsAsFinished` method.</span></span> <span data-ttu-id="32dcc-178">Метод `MarkOutputsAsFinished` вызывает метод `SetEndOfRowset` для последнего выходного буфера.</span><span class="sxs-lookup"><span data-stu-id="32dcc-178">The `MarkOutputsAsFinished` method calls `SetEndOfRowset` on the last output buffer.</span></span>

-   <span data-ttu-id="32dcc-179">Реализация метода `CreateNewOutputRows`, доступная для переопределения.</span><span class="sxs-lookup"><span data-stu-id="32dcc-179">An overridable implementation of the `CreateNewOutputRows` method.</span></span> <span data-ttu-id="32dcc-180">Реализация по умолчанию пуста.</span><span class="sxs-lookup"><span data-stu-id="32dcc-180">The default implementation is empty.</span></span> <span data-ttu-id="32dcc-181">Этот метод обычно переопределяется, чтобы написать пользовательский код обработки данных.</span><span class="sxs-lookup"><span data-stu-id="32dcc-181">This is the method that you will normally override to write your custom data processing code.</span></span>

#### <a name="what-your-custom-code-should-do"></a><span data-ttu-id="32dcc-182">Задачи, выполняемые в пользовательском коде</span><span class="sxs-lookup"><span data-stu-id="32dcc-182">What Your Custom Code Should Do</span></span>
 <span data-ttu-id="32dcc-183">Для обработки выходов в классе `ScriptMain` можно использовать следующие методы.</span><span class="sxs-lookup"><span data-stu-id="32dcc-183">You can use the following methods to process outputs in the `ScriptMain` class:</span></span>

-   <span data-ttu-id="32dcc-184">Переопределите метод `CreateNewOutputRows`, только если возможно добавление и заполнение выходных строк перед обработкой входных строк.</span><span class="sxs-lookup"><span data-stu-id="32dcc-184">Override `CreateNewOutputRows` only when you can add and populate output rows before processing input rows.</span></span> <span data-ttu-id="32dcc-185">Например, метод `CreateNewOutputRows` можно использовать на источнике, но при преобразовании с использованием асинхронных выходов необходимо вызывать метод `AddRow` во время или после обработки входных данных.</span><span class="sxs-lookup"><span data-stu-id="32dcc-185">For example, you can use `CreateNewOutputRows` in a source, but in a transformation with asynchronous outputs, you should call `AddRow` during or after the processing of input data.</span></span>

-   <span data-ttu-id="32dcc-186">Переопределите метод `FinishOutputs`, если нужно выполнять действия с выходами перед их закрытием.</span><span class="sxs-lookup"><span data-stu-id="32dcc-186">Override `FinishOutputs` if you have to do something to the outputs before they are closed.</span></span>

 <span data-ttu-id="32dcc-187">Метод `PrimeOutput` обеспечивает, что эти методы будут вызываться в нужное время.</span><span class="sxs-lookup"><span data-stu-id="32dcc-187">The `PrimeOutput` method ensures that these methods are called at the appropriate times.</span></span>

## <a name="postexecute-method"></a><span data-ttu-id="32dcc-188">Метод PostExecute</span><span class="sxs-lookup"><span data-stu-id="32dcc-188">PostExecute Method</span></span>
 <span data-ttu-id="32dcc-189">Переопределите метод <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PostExecute%2A> базового класса <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>, если необходимо однократно выполнить некоторые действия после обработки всех строк данных.</span><span class="sxs-lookup"><span data-stu-id="32dcc-189">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PostExecute%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class whenever you have processing that you must perform one time only after you have processed the rows of data.</span></span> <span data-ttu-id="32dcc-190">Например, можно закрыть на источнике объект `System.Data.SqlClient.SqlDataReader`, который используется для загрузки данных в поток данных.</span><span class="sxs-lookup"><span data-stu-id="32dcc-190">For example, in a source, you may want to close the `System.Data.SqlClient.SqlDataReader` that you have used to load data into the data flow.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="32dcc-191">Коллекция `ReadWriteVariables` доступна только в методе `PostExecute`.</span><span class="sxs-lookup"><span data-stu-id="32dcc-191">The collection of `ReadWriteVariables` is available only in the `PostExecute` method.</span></span> <span data-ttu-id="32dcc-192">Поэтому нельзя непосредственно увеличивать значение переменной пакета после обработки каждой строки данных.</span><span class="sxs-lookup"><span data-stu-id="32dcc-192">Therefore you cannot directly increment the value of a package variable as you process each row of data.</span></span> <span data-ttu-id="32dcc-193">Вместо этого увеличьте значение локальной переменной и задайте это же значение переменной пакета в методе `PostExecute` после того, как все данные обработаны.</span><span class="sxs-lookup"><span data-stu-id="32dcc-193">Instead, increment the value of a local variable, and set the value of the package variable to the value of the local variable in the `PostExecute` method after all data has been processed.</span></span>

## <a name="releaseconnections-method"></a><span data-ttu-id="32dcc-194">Метод ReleaseConnections</span><span class="sxs-lookup"><span data-stu-id="32dcc-194">ReleaseConnections Method</span></span>
 <span data-ttu-id="32dcc-195">Источники и назначения обычно должны быть соединены с внешним источником данных.</span><span class="sxs-lookup"><span data-stu-id="32dcc-195">Sources and destinations typically must connect to an external data source.</span></span> <span data-ttu-id="32dcc-196">Переопределите метод <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ReleaseConnections%2A> базового класса <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>, чтобы закрыть и освободить соединение, ранее открытое в методе <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="32dcc-196">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ReleaseConnections%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class to close and release the connection that you have opened previously in the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A> method.</span></span>

```vb
    Dim connMgr As IDTSConnectionManager100
...
    Public Overrides Sub ReleaseConnections()

        connMgr.ReleaseConnection(sqlConn)

    End Sub
```

```csharp
IDTSConnectionManager100 connMgr;

public override void ReleaseConnections()
{

    connMgr.ReleaseConnection(sqlConn);

}
```

<span data-ttu-id="32dcc-197">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="32dcc-197">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="32dcc-198">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="32dcc-198">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="32dcc-199">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="32dcc-199">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="32dcc-200">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="32dcc-200">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="32dcc-201">См. также:</span><span class="sxs-lookup"><span data-stu-id="32dcc-201">See Also</span></span>
 <span data-ttu-id="32dcc-202">[Настройка компонента скрипта в редакторе компонента скрипта](configuring-the-script-component-in-the-script-component-editor.md) [написание кода и отладка компонента скрипта] (.. /екстендинг-паккажес-скриптинг/дата-флов-скрипт-компонент/кодинг-анд-дебуггинг-се-скрипт-компонент.мд</span><span class="sxs-lookup"><span data-stu-id="32dcc-202">[Configuring the Script Component in the Script Component Editor](configuring-the-script-component-in-the-script-component-editor.md) [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md</span></span>


