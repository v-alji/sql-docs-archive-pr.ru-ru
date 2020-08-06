---
title: XML-соглашения ASSL | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- whitespace [Analysis Services Scripting Language]
- trailing whitespace
- XSD data types [Analysis Services Scripting Language]
- inheritance [Analysis Services Scripting Language]
- cardinality [Analysis Services Scripting Language]
- white space [Analysis Services Scripting Language]
- ASSL, XML conventions
- defaults [Analysis Services Scripting Language]
- leading whitespace
- Analysis Services Scripting Language, XML conventions
- XML [Analysis Services Scripting Language]
- hierarchies [Analysis Services Scripting Language]
- inherited defaults [Analysis Services Scripting Language]
ms.assetid: bce4edad-4420-41ce-9672-8c00c5c0dec6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b70742b07fd6450b01cf205147a05f40c4b6121
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736971"
---
# <a name="assl-xml-conventions"></a><span data-ttu-id="594e0-102">Обозначения в XML языка ASSL</span><span class="sxs-lookup"><span data-stu-id="594e0-102">ASSL XML Conventions</span></span>
  <span data-ttu-id="594e0-103">Язык ASSL представляет иерархию объектов в виде набора типов элементов, каждый из которых определяет дочерние элементы, которые они могут содержать.</span><span class="sxs-lookup"><span data-stu-id="594e0-103">Analysis Services Scripting Language (ASSL) represents the hierarchy of objects as a set of element types, each of which defines the child elements they can contain.</span></span>  
  
 <span data-ttu-id="594e0-104">Чтобы можно было представлять иерархию объектов в языке ASSL, используются следующие обозначения XML.</span><span class="sxs-lookup"><span data-stu-id="594e0-104">To represent the object hierarchy, ASSL uses the following XML conventions:</span></span>  
  
-   <span data-ttu-id="594e0-105">Все объекты и свойства представлены как элементы, за исключением стандартных атрибутов XML, таких как "XML: lang".</span><span class="sxs-lookup"><span data-stu-id="594e0-105">All objects and properties are represented as elements, except for standard XML attributes such as 'xml:lang'.</span></span>  
  
-   <span data-ttu-id="594e0-106">Имена элементов и значения перечисления соответствуют контексту именования в стиле языка Pascal, применяемому на платформе Microsoft .NET Framework, без символов подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="594e0-106">Both element names and enumeration values follow the Microsoft .NET Framework naming convention of Pascal casing with no underscores.</span></span>  
  
-   <span data-ttu-id="594e0-107">Регистр всех значений сохраняется.</span><span class="sxs-lookup"><span data-stu-id="594e0-107">The case of all values is preserved.</span></span> <span data-ttu-id="594e0-108">Значения для перечислений учитывают также регистр.</span><span class="sxs-lookup"><span data-stu-id="594e0-108">Values for enumerations are also case-sensitive.</span></span>  
  
 <span data-ttu-id="594e0-109">Помимо этого списка соглашений, в службах Analysis Services также соблюдаются определенные соглашения в отношении количества элементов, наследования, пробелов, типов данных и значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="594e0-109">In addition to this list of conventions, Analysis Services also follows certain conventions regarding cardinality, inheritance, whitespace, data types, and default values.</span></span>  
  
## <a name="cardinality"></a><span data-ttu-id="594e0-110">Кратность</span><span class="sxs-lookup"><span data-stu-id="594e0-110">Cardinality</span></span>  
 <span data-ttu-id="594e0-111">Если элемент допускает применение количества элементов больше 1, то существует коллекция элементов XML, которая инкапсулирует этот элемент.</span><span class="sxs-lookup"><span data-stu-id="594e0-111">When an element has a cardinality that is greater than 1, there is an XML element collection that encapsulates this element.</span></span> <span data-ttu-id="594e0-112">В имени коллекции используется представленное во множественном числе имя содержащихся в ней элементов.</span><span class="sxs-lookup"><span data-stu-id="594e0-112">The name of collection uses the plural form of the elements contained in the collection.</span></span> <span data-ttu-id="594e0-113">Например, следующий фрагмент XML представляет коллекцию `Dimensions` в элементе `Database`:</span><span class="sxs-lookup"><span data-stu-id="594e0-113">For example, the following XML fragment represents the `Dimensions` collection within a `Database` element:</span></span>  
  
 `<Database>`  
  
 `...`  
  
 `<Dimensions>`  
  
 `<Dimension>`  
  
 `...`  
  
 `</Dimension>`  
  
 `<Dimension>`  
  
 `...`  
  
 `</Dimension>`  
  
 `</Dimensions>`  
  
 `</Database>`  
  
 ``  
  
 <span data-ttu-id="594e0-114">Порядок следования элементов не важен.</span><span class="sxs-lookup"><span data-stu-id="594e0-114">The order in which elements appear is unimportant.</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="594e0-115">Наследование</span><span class="sxs-lookup"><span data-stu-id="594e0-115">Inheritance</span></span>  
 <span data-ttu-id="594e0-116">Наследование используется при наличии отдельных объектов, имеющих пересекающиеся, однако значительно отличающиеся наборы свойств.</span><span class="sxs-lookup"><span data-stu-id="594e0-116">Inheritance is used when there are distinct objects that have overlapping but significantly different sets of properties.</span></span> <span data-ttu-id="594e0-117">Примерами таких пересекающихся, но все же отдельных объектов являются виртуальные кубы, связанные кубы и обычные кубы.</span><span class="sxs-lookup"><span data-stu-id="594e0-117">Examples of such overlapping but distinct objects are virtual cubes, linked cubes, and regular cubes.</span></span> <span data-ttu-id="594e0-118">Для указания наследования в пересекающихся, но отдельных объектах в службах Analysis Services используется стандартный атрибут `type` из пространства имен экземпляра XML.</span><span class="sxs-lookup"><span data-stu-id="594e0-118">For overlapping but distinct object, Analysis Services uses the standard `type` attribute from the XML Instance Namespace to indicate the inheritance.</span></span> <span data-ttu-id="594e0-119">Например, в следующем фрагменте XML можно видеть, что атрибут `type` указывает, будет ли элемент `Cube` наследовать от обычного куба или от виртуального:</span><span class="sxs-lookup"><span data-stu-id="594e0-119">For example, the following XML fragment shows how the `type` attribute identifies whether a `Cube` element inherits from a regular cube or from a virtual cube:</span></span>  
  
 `<Cubes>`  
  
 `<Cube xsi:type="RegularCube">`  
  
 `<Name>Sales</Name>`  
  
 `...`  
  
 `</Cube>`  
  
 `<Cube xsi:type="VirtualCube">`  
  
 `<Name>SalesAndInventory</Name>`  
  
 `...`  
  
 `</Cube>`  
  
 `</Cubes>`  
  
 ``  
  
 <span data-ttu-id="594e0-120">В целом наследование не применяется, когда у нескольких типов есть свойство с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="594e0-120">Inheritance is generally not used when multiple types have a property of the same name.</span></span> <span data-ttu-id="594e0-121">Например, многие элементы имеют свойства `Name` и `ID`, однако эти свойства не были повышены до абстрактного типа.</span><span class="sxs-lookup"><span data-stu-id="594e0-121">For example, the `Name` and `ID` properties appear on many elements, but these properties have not been promoted to an abstract type.</span></span>  
  
## <a name="whitespace"></a><span data-ttu-id="594e0-122">Пробел</span><span class="sxs-lookup"><span data-stu-id="594e0-122">Whitespace</span></span>  
 <span data-ttu-id="594e0-123">Пробелы в значении элемента сохраняются.</span><span class="sxs-lookup"><span data-stu-id="594e0-123">Whitespace within an element value is preserved.</span></span> <span data-ttu-id="594e0-124">При этом начальный и замыкающий пробелы всегда отсекаются.</span><span class="sxs-lookup"><span data-stu-id="594e0-124">However, leading and trailing whitespace is always trimmed.</span></span> <span data-ttu-id="594e0-125">Например, текст в следующих элементах одинаковый, но количество пробелов в нем разное, поэтому считается, что у них разные значения:</span><span class="sxs-lookup"><span data-stu-id="594e0-125">For example, the following elements have the same text but differing amounts of whitespace within that text, and are therefore treated as if they have different values:</span></span>  
  
 `<Description>My text<Description>`  
  
 `<Description>My  text<Description>`  
  
 ``  
  
 <span data-ttu-id="594e0-126">Однако следующие элементы отличаются только наличием начального и замыкающего пробелов, поэтому считается, что у них одинаковые значения:</span><span class="sxs-lookup"><span data-stu-id="594e0-126">However, the following elements vary only in leading and trailing whitespace, and are therefore treated as if they have equivalent values:</span></span>  
  
 `<Description>My text<Description>`  
  
 `<Description>  My text  <Description>`  
  
 ``  
  
## <a name="data-types"></a><span data-ttu-id="594e0-127">Типы данных</span><span class="sxs-lookup"><span data-stu-id="594e0-127">Data Types</span></span>  
 <span data-ttu-id="594e0-128">В службах Analysis Services используются следующие типы данных языка XSD стандартной схемы XML.</span><span class="sxs-lookup"><span data-stu-id="594e0-128">Analysis Services uses the following standard XML Schema definition language (XSD) data types:</span></span>  
  
 `Int`  
 <span data-ttu-id="594e0-129">Целочисленное значение в диапазоне от-231 до 231-1.</span><span class="sxs-lookup"><span data-stu-id="594e0-129">An integer value in the range of -231 to 231 - 1.</span></span>  
  
 `Long`  
 <span data-ttu-id="594e0-130">Целочисленное значение в диапазоне от-263 до 263-1.</span><span class="sxs-lookup"><span data-stu-id="594e0-130">An integer value in range of -263 to 263 - 1.</span></span>  
  
 `String`  
 <span data-ttu-id="594e0-131">Строковое значение, соответствующее следующим глобальным правилам.</span><span class="sxs-lookup"><span data-stu-id="594e0-131">A string value that conforms to the following global rules:</span></span>  
  
-   <span data-ttu-id="594e0-132">Управляющие символы удалены.</span><span class="sxs-lookup"><span data-stu-id="594e0-132">Control characters are stripped out.</span></span>  
  
-   <span data-ttu-id="594e0-133">Начальные и замыкающие пробелы отсечены.</span><span class="sxs-lookup"><span data-stu-id="594e0-133">Leading and trailing white space is trimmed.</span></span>  
  
-   <span data-ttu-id="594e0-134">Пробелы внутри текста сохранены.</span><span class="sxs-lookup"><span data-stu-id="594e0-134">Internal white space is preserved.</span></span>  
  
 <span data-ttu-id="594e0-135">Свойства `Name` и `ID` имеют особые ограничения на допустимые символы в строковых элементах.</span><span class="sxs-lookup"><span data-stu-id="594e0-135">`Name` and `ID` properties have special limitations on valid characters in string elements.</span></span> <span data-ttu-id="594e0-136">Дополнительные сведения о `Name` `ID` соглашениях и см. в разделе [объекты и характеристики объектов ASSL](assl-objects-and-object-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="594e0-136">For additional information about `Name` and `ID` conventions, see [ASSL Objects and Object Characteristics](assl-objects-and-object-characteristics.md).</span></span>  
  
 `DateTime`  
 <span data-ttu-id="594e0-137">`DateTime`Структура из .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="594e0-137">A `DateTime` structure from the .NET Framework.</span></span> <span data-ttu-id="594e0-138">Значение `DateTime` не может быть NULL.</span><span class="sxs-lookup"><span data-stu-id="594e0-138">A `DateTime` value cannot be NULL.</span></span> <span data-ttu-id="594e0-139">Самая давняя дата, которую поддерживает тип данных `DataTime`, —1 января 1601 года; программисты могут использовать ее в форме `DateTime.MinValue`.</span><span class="sxs-lookup"><span data-stu-id="594e0-139">The lowest date supported by the `DataTime` data type is January 1, 1601, which is available to programmers as `DateTime.MinValue`.</span></span> <span data-ttu-id="594e0-140">Самая давняя поддерживаемая дата указывает, что значение `DateTime` отсутствует.</span><span class="sxs-lookup"><span data-stu-id="594e0-140">The lowest supported date indicates that a `DateTime` value is missing.</span></span>  
  
 `Boolean`  
 <span data-ttu-id="594e0-141">Перечисление только с двумя значениями, например {true, false} или {0, 1}.</span><span class="sxs-lookup"><span data-stu-id="594e0-141">An enumeration with only two values, such as {true, false} or {0, 1}.</span></span>  
  
## <a name="default-values"></a><span data-ttu-id="594e0-142">Значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="594e0-142">Default Values</span></span>  
 <span data-ttu-id="594e0-143">В службах Analysis Services используются значения по умолчанию, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="594e0-143">Analysis Services uses the defaults listed in the following table.</span></span>  
  
|<span data-ttu-id="594e0-144">Тип данных XML</span><span class="sxs-lookup"><span data-stu-id="594e0-144">XML data type</span></span>|<span data-ttu-id="594e0-145">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="594e0-145">Default value</span></span>|  
|-------------------|-------------------|  
|`Boolean`|<span data-ttu-id="594e0-146">Неверно</span><span class="sxs-lookup"><span data-stu-id="594e0-146">False</span></span>|  
|`String`|<span data-ttu-id="594e0-147">"" (пустая строка)</span><span class="sxs-lookup"><span data-stu-id="594e0-147">"" (empty string)</span></span>|  
|<span data-ttu-id="594e0-148">`Integer` или `Long`</span><span class="sxs-lookup"><span data-stu-id="594e0-148">`Integer` or `Long`</span></span>|<span data-ttu-id="594e0-149">0 (ноль)</span><span class="sxs-lookup"><span data-stu-id="594e0-149">0 (zero)</span></span>|  
|`Timestamp`|<span data-ttu-id="594e0-150">12:00:00 AM, 1/1/0001 (соответствует платформам .NET Framework `System.DateTime` с 0 тактовами)</span><span class="sxs-lookup"><span data-stu-id="594e0-150">12:00:00 AM, 1/1/0001 (corresponding to a the .NET Frameworks `System.DateTime` with 0 ticks)</span></span>|  
  
 <span data-ttu-id="594e0-151">Элемент, который имеется в наличии, но является пустым, интерпретируется как имеющий значение пустой строки, а не значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="594e0-151">An element that is present but empty is interpreted as having a value of a null string, not the default value.</span></span>  
  
### <a name="inherited-defaults"></a><span data-ttu-id="594e0-152">Унаследованные значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="594e0-152">Inherited Defaults</span></span>  
 <span data-ttu-id="594e0-153">Некоторые свойства, заданные в объекте, предоставляют применяемые по умолчанию значения для дочерних объектов или объектов-потомков.</span><span class="sxs-lookup"><span data-stu-id="594e0-153">Some properties that are specified on an object provide default values for the same property on child or descendant objects.</span></span> <span data-ttu-id="594e0-154">Например, свойство `Cube.StorageMode` предоставляет значение по умолчанию для свойства `Partition.StorageMode`.</span><span class="sxs-lookup"><span data-stu-id="594e0-154">For example, `Cube.StorageMode` provides the default value for `Partition.StorageMode`.</span></span> <span data-ttu-id="594e0-155">В службах Analysis Services к унаследованным значениям по умолчанию применяются следующие правила.</span><span class="sxs-lookup"><span data-stu-id="594e0-155">The rules that Analysis Services applies for inherited default values are as follows:</span></span>  
  
-   <span data-ttu-id="594e0-156">Если свойство для дочернего объекта не определено в элементе XML, то по умолчанию в качестве его значения применяется унаследованное значение.</span><span class="sxs-lookup"><span data-stu-id="594e0-156">When the property for the child object is null in the XML, its value defaults to the inherited value.</span></span> <span data-ttu-id="594e0-157">Но если выполняется запрос этого значения с сервера, то сервер возвращает неопределенное значение элемента XML.</span><span class="sxs-lookup"><span data-stu-id="594e0-157">However, if you query the value from the server, the server returns the null value of the XML element.</span></span>  
  
-   <span data-ttu-id="594e0-158">Возможность определить программным путем, было ли задано свойство дочернего объекта непосредственно на дочернем объекте или унаследовано, отсутствует.</span><span class="sxs-lookup"><span data-stu-id="594e0-158">It is not possible to determine programmatically whether the property of a child object has been set directly on the child object or inherited.</span></span>  
  
 <span data-ttu-id="594e0-159">Для некоторых элементов определены значения по умолчанию, которые применяются при отсутствии элемента.</span><span class="sxs-lookup"><span data-stu-id="594e0-159">Some elements have defined defaults that apply when the element is missing.</span></span> <span data-ttu-id="594e0-160">Например, элементы `Dimension` в следующем фрагменте XML эквивалентны, даже несмотря на то, что один элемент `Dimension` содержит элемент `Visible`, а другой элемент `Dimension` — нет.</span><span class="sxs-lookup"><span data-stu-id="594e0-160">For example, the `Dimension` elements in the following XML fragment are equivalent even though one `Dimension` element contains a `Visible` element, but the other `Dimension` element does not.</span></span>  
  
 `<Dimension>`  
  
 `<Name>Product</Name>`  
  
 `</Dimension>`  
  
 `<Dimension>`  
  
 `<Name>Product</ Name>`  
  
 `<Visible>true</Visible>`  
  
 `</Dimension>`  
  
 <span data-ttu-id="594e0-161">Дополнительные сведения о наследуемых значениях по умолчанию см. в разделе [объекты и характеристики объектов ASSL](assl-objects-and-object-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="594e0-161">For more information on inherited defaults, see [ASSL Objects and Object Characteristics](assl-objects-and-object-characteristics.md).</span></span>  
  
  
