---
title: Настройка контейнера «цикл по каждому элементу» | Документация Майкрософт
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Foreach Loop containers
- containers [Integration Services], Foreach Loop
ms.assetid: 519c6f96-5e1f-47d2-b96a-d49946948c25
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 85fb399f51e22e091fac9b1d8d332b9a12e7d77e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655882"
---
# <a name="configure-a-foreach-loop-container"></a><span data-ttu-id="4d170-102">Настройка контейнера "цикл по каждому элементу"</span><span class="sxs-lookup"><span data-stu-id="4d170-102">Configure a Foreach Loop Container</span></span>
  <span data-ttu-id="4d170-103">Эта процедура описывает принципы настройки контейнера «цикл по каждому элементу», включая выражения свойств на уровнях перечислителя и контейнера.</span><span class="sxs-lookup"><span data-stu-id="4d170-103">This procedure describes how to configure a Foreach Loop container, including property expressions at the enumerator and container levels.</span></span>  
  
### <a name="to-configure-the-foreach-loop-container"></a><span data-ttu-id="4d170-104">Настройка контейнера «цикл по каждому элементу»</span><span class="sxs-lookup"><span data-stu-id="4d170-104">To configure the Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="4d170-105">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="4d170-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="4d170-106">Перейдите на вкладку **Поток управления** и дважды щелкните "Цикл по каждому элементу".</span><span class="sxs-lookup"><span data-stu-id="4d170-106">Click the **Control Flow** tab and double-click the Foreach Loop.</span></span>  
  
3.  <span data-ttu-id="4d170-107">В диалоговом окне **Редактор циклов по каждому элементу** нажмите **Общие** и при необходимости измените имя и описание контейнера «цикл по каждому элементу».</span><span class="sxs-lookup"><span data-stu-id="4d170-107">In the **Foreach Loop Editor** dialog box, click **General** and, optionally, modify the name and description of the Foreach Loop.</span></span>  
  
4.  <span data-ttu-id="4d170-108">Щелкните **Коллекция** и выберите тип перечислителя из списка **Перечислитель** .</span><span class="sxs-lookup"><span data-stu-id="4d170-108">Click **Collection** and select an enumerator type from the **Enumerator** list.</span></span>  
  
5.  <span data-ttu-id="4d170-109">Укажите перечислитель и установите параметры перечислителя, как показано далее.</span><span class="sxs-lookup"><span data-stu-id="4d170-109">Specify an enumerator and set enumerator options as follows:</span></span>  
  
    -   <span data-ttu-id="4d170-110">Чтобы использовать перечислитель с циклом по каждому файлу, укажите папку, в которой содержатся необходимые для перечисления файлы, фильтр для имени и типа файла и укажите, нужно ли возвращать полное имя файла.</span><span class="sxs-lookup"><span data-stu-id="4d170-110">To usethe Foreach File enumerator, provide the folder that contains the files to enumerate, specify a filter for the file name and type, and specify whether the fully qualified file name should be returned.</span></span> <span data-ttu-id="4d170-111">Также укажите, нужно ли для поиска файлов обращаться ко вложенным папкам.</span><span class="sxs-lookup"><span data-stu-id="4d170-111">Also, indicate whether to recurse through subfolders for more files.</span></span>  
  
    -   <span data-ttu-id="4d170-112">Чтобы использовать перечислитель по каждому элементу, нажмите кнопку **Столбцы**и в диалоговом окне **Столбцы For Each Item** для добавления столбцов нажмите кнопку **Добавить** .</span><span class="sxs-lookup"><span data-stu-id="4d170-112">To use the Foreach Item enumerator, click **Columns**, and, in the **For Each Item Columns** dialog box, click **Add** to add columns.</span></span> <span data-ttu-id="4d170-113">Выберите тип данных из списка **Тип данных** для каждого столбца и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4d170-113">Select a data type in the **Data Type** list for each column, and click **OK**.</span></span>  
  
         <span data-ttu-id="4d170-114">Введите значения в столбцах или выберите их из списков.</span><span class="sxs-lookup"><span data-stu-id="4d170-114">Type values in the columns or select values from lists.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="4d170-115">Чтобы добавить новую строку, щелкните в любом месте за пределами ячейки, в которую было введено значение.</span><span class="sxs-lookup"><span data-stu-id="4d170-115">To add a new row, click anywhere outside the cell in which you typed.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="4d170-116">Если значение несовместимо с типом данных столбца, текст будет выделен.</span><span class="sxs-lookup"><span data-stu-id="4d170-116">If a value is not compatible with the column data type, the text is highlighted.</span></span>  
  
    -   <span data-ttu-id="4d170-117">Чтобы использовать перечислитель ADO по каждой строке, выберите существующую переменную или нажмите **Создать переменную** в списке **Переменная источника объекта ADO** , чтобы указать переменную, содержащую необходимое для перечисления имя объекта ADO, и выберите параметр режима перечисления.</span><span class="sxs-lookup"><span data-stu-id="4d170-117">To use the Foreach ADO enumerator, select an existing variable or click **New variable** in the **ADO object source variable** list to specify the variable that contains the name of the ADO object to enumerate, and select an enumeration mode option.</span></span>  
  
         <span data-ttu-id="4d170-118">Если создается новая переменная, установите ее свойства в диалоговом окне **Добавить переменную** .</span><span class="sxs-lookup"><span data-stu-id="4d170-118">If creating a new variable, set the variable properties in the **Add Variable** dialog box.</span></span>  
  
    -   <span data-ttu-id="4d170-119">Чтобы использовать перечислитель ADO.NET по набору строк схемы, выберите существующее соединение ADO.NET или нажмите **Создать соединение** в списке **Соединение** , а затем выберите схему.</span><span class="sxs-lookup"><span data-stu-id="4d170-119">To use the Foreach ADO.NET Schema Rowset enumerator, select an existing ADO.NET connection or click **New connection** in the **Connection** list, and then select a schema.</span></span>  
  
         <span data-ttu-id="4d170-120">При необходимости нажмите кнопку **Задать ограничения** и выберите ограничения схемы, переменную, содержащую значение ограничения, или введите значение ограничения, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4d170-120">Optionally, click **Set Restrictions** and select schema restrictions, select the variable that contains the restriction value or type the restriction value, and click **OK**.</span></span>  
  
    -   <span data-ttu-id="4d170-121">Чтобы использовать перечислитель по объекту из переменной, выберите переменную из списка **Переменные** .</span><span class="sxs-lookup"><span data-stu-id="4d170-121">To use the Foreach From Variable enumerator, select a variable in the **Variable** list.</span></span>  
  
    -   <span data-ttu-id="4d170-122">Чтобы использовать перечислитель по набору узлов, щелкните DocumentSourceType, выберите из списка тип источника, а затем щелкните DocumentSource.</span><span class="sxs-lookup"><span data-stu-id="4d170-122">To use the Foreach NodeList enumerator, click DocumentSourceType and select the source type from the list, and then click DocumentSource.</span></span> <span data-ttu-id="4d170-123">В зависимости от значения, выбранного для DocumentSourceType, выберите из списка переменную или подключение файла, создайте новую переменную или подключение файла или введите источник XML в **Редакторе исходного текста документа**.</span><span class="sxs-lookup"><span data-stu-id="4d170-123">Depending on the value selected for DocumentSourceType, select a variable or a file connection from the list, create a new variable or file connection, or type the XML source in the **Document Source Editor**.</span></span>  
  
         <span data-ttu-id="4d170-124">Затем щелкните EnumerationType и выберите тип перечисления из списка.</span><span class="sxs-lookup"><span data-stu-id="4d170-124">Next, click EnumerationType and select an enumeration type from the list.</span></span> <span data-ttu-id="4d170-125">Если значением EnumerationType является **Navigator, Node или NodeText**, щелкните OuterXPathStringSourceType и выберите тип источника, затем щелкните OuterXPathString.</span><span class="sxs-lookup"><span data-stu-id="4d170-125">If EnumerationType is **Navigator, Node, or NodeText**, click OuterXPathStringSourceType and select the source type, and then click OuterXPathString.</span></span> <span data-ttu-id="4d170-126">В зависимости от значения, установленного для OuterXPathStringSourceType, выберите из списка переменную или подключение файла, создайте новую переменную или подключение файла или введите строку для внешнего выражения языка пути XML (XPath).</span><span class="sxs-lookup"><span data-stu-id="4d170-126">Depending on the value set for OuterXPathStringSourceType, select a variable or a file connection from the list, create a new variable or file connection, or type the string for the outer XML Path Language (XPath) expression.</span></span>  
  
         <span data-ttu-id="4d170-127">Если значением EnumerationType является **ElementCollection**, задайте OuterXPathStringSourceType и OuterXPathString, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="4d170-127">If EnumerationType is **ElementCollection**,set OuterXPathStringSourceType and OuterXPathString as described above.</span></span> <span data-ttu-id="4d170-128">Затем щелкните InnerElementType и выберите тип перечисления для внутренних элементов, потом щелкните InnerXPathStringSourceType.</span><span class="sxs-lookup"><span data-stu-id="4d170-128">Then, click InnerElementType and select an enumeration type for the inner elements, and then click InnerXPathStringSourceType.</span></span> <span data-ttu-id="4d170-129">В зависимости от значения, установленного для InnerXPathStringSourceType, выберите переменную или подключение файла или введите строку для внутреннего выражения XPath.</span><span class="sxs-lookup"><span data-stu-id="4d170-129">Depending on the value set for InnerXPathStringSourceType, select a variable or a file connection, create a new variable or file connection, or type the string for the inner XPath expression.</span></span>  
  
    -   <span data-ttu-id="4d170-130">Чтобы использовать перечислитель по объектам SMO, выберите существующее соединение ADO.NET или нажмите **Создать соединение** в списке **Соединения** , затем либо введите строку для использования, либо нажмите **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="4d170-130">To use the Foreach SMO enumerator, select an existing ADO.NET connection or click **New connection** in the **Connection** list, and then either type the string to use or click **Browse**.</span></span> <span data-ttu-id="4d170-131">Если выбран **Обзор**, в диалоговом окне **Выбор перечисления SMO** выберите необходимый для перечисления тип объекта и тип перечисления, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4d170-131">If you click **Browse**, in the **Select SMO Enumeration** dialog box, select the object type to enumerate and the enumeration type, and click **OK**.</span></span>  
  
6.  <span data-ttu-id="4d170-132">При необходимости нажмите кнопку обзора **(…)** в текстовом поле **Выражения** на странице **Коллекция**, чтобы создать выражения, при помощи которых происходит обновление значений свойств.</span><span class="sxs-lookup"><span data-stu-id="4d170-132">Optionally, click the browse button **(...)** in the **Expressions** text box on the **Collection** page to create expressions that update property values.</span></span> <span data-ttu-id="4d170-133">Дополнительные сведения см. в разделе [Добавление или изменение выражение свойства](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="4d170-133">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4d170-134"> Свойства, представленные в списке **Свойства** , меняются в зависимости от перечислителя.</span><span class="sxs-lookup"><span data-stu-id="4d170-134">The properties listed in the **Property** list varies by enumerator.</span></span>  
  
7.  <span data-ttu-id="4d170-135">При необходимости нажмите **Сопоставления переменной** для сопоставления свойств объектов со значениями коллекции, затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="4d170-135">Optionally, click **Variable Mappings** to map object properties to the collection value, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="4d170-136">В списке **Переменные** выберите переменную или щелкните **\<New Variable>** , чтобы создать ее.</span><span class="sxs-lookup"><span data-stu-id="4d170-136">In the **Variables** list, select a variable or click **\<New Variable>** to create a new variable.</span></span>  
  
    2.  <span data-ttu-id="4d170-137">Если создается новая переменная, установите ее свойства в диалоговом окне **Добавить переменные** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4d170-137">If you add a new variable, set the variable properties in the **Add Variable** dialog box and click **OK**.</span></span>  
  
    3.  <span data-ttu-id="4d170-138">При использовании перечислителя по каждому элементу можно обновить значение индекса в списке **Индекс** .</span><span class="sxs-lookup"><span data-stu-id="4d170-138">If you use the For Each Item enumerator, you can update the index value in the **Index** list.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="4d170-139">Значение индекса показывает, какой столбец в элементе нужно сопоставить с переменной.</span><span class="sxs-lookup"><span data-stu-id="4d170-139">The index value indicates which column in the item to map to the variable.</span></span> <span data-ttu-id="4d170-140">Только перечислитель по каждому элементу может использовать значение индекса, отличное от 0.</span><span class="sxs-lookup"><span data-stu-id="4d170-140">Only the For Each Item enumerator can use an index value other than 0.</span></span>  
  
8.  <span data-ttu-id="4d170-141">При необходимости нажмите **Выражения** и на странице **Выражения** создайте выражения свойств для свойств контейнера «цикл по каждому элементу».</span><span class="sxs-lookup"><span data-stu-id="4d170-141">Optionally, click **Expressions** and, on the **Expressions** page, create property expressions for the properties of the Foreach Loop container.</span></span> <span data-ttu-id="4d170-142">Дополнительные сведения см. в разделе [Добавление или изменение выражение свойства](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="4d170-142">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
9. <span data-ttu-id="4d170-143">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4d170-143">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d170-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="4d170-144">See Also</span></span>  
 [<span data-ttu-id="4d170-145">Контейнер «цикл по каждому элементу»</span><span class="sxs-lookup"><span data-stu-id="4d170-145">Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
