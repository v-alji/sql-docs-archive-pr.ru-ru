---
title: Кодирование определяемых пользователем типов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- validation [CLR integration]
- UDTs [CLR integration], coding
- UserDefined serialization format [CLR integration]
- Point UDT
- Parse method
- null values [CLR integration]
- ToString method
- ValidatePoint method
- attributes [CLR integration]
- coding user-defined types [CLR integration]
- Read method
- Write method
- nullability [CLR integration]
- user-defined types [CLR integration], coding
- Currency UDT
- validating UDT values
- exposing UDT properties [CLR integration]
ms.assetid: 1e5b43b3-4971-45ee-a591-3f535e2ac722
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e88c4d8162e5c7c921f5c5062f5b3c23df40a2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656431"
---
# <a name="coding-user-defined-types"></a><span data-ttu-id="aaca8-102">Разработка кода для определяемых пользователем типов</span><span class="sxs-lookup"><span data-stu-id="aaca8-102">Coding User-Defined Types</span></span>
  <span data-ttu-id="aaca8-103">При разработке определяемого пользователем типа необходимо реализовать различные функциональные возможности в зависимости от того, реализуется ли определяемый пользователем тип в виде класса или структуры, а также от выбранных параметров формата и сериализации.</span><span class="sxs-lookup"><span data-stu-id="aaca8-103">When coding your user-defined type (UDT) definition, you must implement various features, depending on whether you are implementing the UDT as a class or a structure, as well as on the format and serialization options you have chosen.</span></span>  
  
 <span data-ttu-id="aaca8-104">Пример, приведенный в этом разделе, иллюстрирует реализацию определяемого пользователем типа `Point` в виде `struct` (или на языке Visual Basic — `Structure`).</span><span class="sxs-lookup"><span data-stu-id="aaca8-104">The example in this section illustrates implementing a `Point` UDT as a `struct` (or `Structure` in Visual Basic).</span></span> <span data-ttu-id="aaca8-105">Определяемый пользователем тип `Point` содержит координаты X и Y, реализованные как процедуры свойств.</span><span class="sxs-lookup"><span data-stu-id="aaca8-105">The `Point` UDT consists of X and Y coordinates implemented as property procedures.</span></span>  
  
 <span data-ttu-id="aaca8-106">При определении пользовательского типа необходимы следующие пространства имен:</span><span class="sxs-lookup"><span data-stu-id="aaca8-106">The following namespaces are required when defining a UDT:</span></span>  
  
```vb  
Imports System  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
```  
  
```csharp  
using System;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
```  
  
 <span data-ttu-id="aaca8-107">Пространство имен `Microsoft.SqlServer.Server` содержит объекты, необходимые для реализации различных атрибутов определяемого пользователем типа, а пространство имен `System.Data.SqlTypes` содержит классы, представляющие собственные типы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], доступные для сборки.</span><span class="sxs-lookup"><span data-stu-id="aaca8-107">The `Microsoft.SqlServer.Server` namespace contains the objects required for various attributes of your UDT, and the `System.Data.SqlTypes` namespace contains the classes that represent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data types available to the assembly.</span></span> <span data-ttu-id="aaca8-108">Разумеется, конкретной сборке для правильной работы могут понадобиться и другие пространства имен.</span><span class="sxs-lookup"><span data-stu-id="aaca8-108">There may of course be additional namespaces that your assembly requires in order to function correctly.</span></span> <span data-ttu-id="aaca8-109">Определяемый пользователем тип `Point` использует также пространство имен `System.Text` для работы со строками.</span><span class="sxs-lookup"><span data-stu-id="aaca8-109">The `Point` UDT also uses the `System.Text` namespace for working with strings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aaca8-110">Выполнение объектов базы данных Visual C++, например UDT, скомпилированных с помощью параметра `/clr:pure`, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="aaca8-110">Visual C++ database objects, such as UDTs, compiled with `/clr:pure` are not supported for execution.</span></span>  
  
## <a name="specifying-attributes"></a><span data-ttu-id="aaca8-111">Определение атрибутов</span><span class="sxs-lookup"><span data-stu-id="aaca8-111">Specifying Attributes</span></span>  
 <span data-ttu-id="aaca8-112">Атрибуты определяют, каким образом сериализация используется для создания хранимых представлений определяемых пользователем типов, а также для передачи таких типов клиенту по значению.</span><span class="sxs-lookup"><span data-stu-id="aaca8-112">Attributes determine how serialization is used to construct the storage representation of UDTs and to transmit UDTs by value to the client.</span></span>  
  
 <span data-ttu-id="aaca8-113">Атрибут `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="aaca8-113">The `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` is required.</span></span> <span data-ttu-id="aaca8-114">Атрибут `Serializable` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="aaca8-114">The `Serializable` attribute is optional.</span></span> <span data-ttu-id="aaca8-115">Также можно указать атрибут `Microsoft.SqlServer.Server.SqlFacetAttribute` для задания информации о возвращаемом типе, определяемом пользователем.</span><span class="sxs-lookup"><span data-stu-id="aaca8-115">You can also specify the `Microsoft.SqlServer.Server.SqlFacetAttribute` to provide information about the return type of a UDT.</span></span> <span data-ttu-id="aaca8-116">Дополнительные сведения см. в статье [Пользовательские атрибуты процедур CLR](../clr-integration/database-objects/clr-integration-custom-attributes-for-clr-routines.md).</span><span class="sxs-lookup"><span data-stu-id="aaca8-116">For more information, see [Custom Attributes for CLR Routines](../clr-integration/database-objects/clr-integration-custom-attributes-for-clr-routines.md).</span></span>  
  
### <a name="point-udt-attributes"></a><span data-ttu-id="aaca8-117">Атрибуты определяемого пользователем типа Point</span><span class="sxs-lookup"><span data-stu-id="aaca8-117">Point UDT Attributes</span></span>  
 <span data-ttu-id="aaca8-118">Метод `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` задает для определяемого пользователем типа `Point` формат хранения `Native`.</span><span class="sxs-lookup"><span data-stu-id="aaca8-118">The `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` sets the storage format for the `Point` UDT to `Native`.</span></span> <span data-ttu-id="aaca8-119">Свойству `IsByteOrdered` присваивается значение `true`, а это гарантирует, что результаты сравнения в SQL Server будут такими же, как если бы сравнение проводилось в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="aaca8-119">`IsByteOrdered` is set to `true`, which guarantees that the results of comparisons are the same in SQL Server as if the same comparison had taken place in managed code.</span></span> <span data-ttu-id="aaca8-120">Определяемый пользователем тип реализует интерфейс `System.Data.SqlTypes.INullable`, чтобы определяемый пользователем тип мог работать со значениями NULL.</span><span class="sxs-lookup"><span data-stu-id="aaca8-120">The UDT implements the `System.Data.SqlTypes.INullable` interface to make the UDT null aware.</span></span>  
  
 <span data-ttu-id="aaca8-121">В следующем фрагменте кода показаны атрибуты определяемого пользователем типа `Point`.</span><span class="sxs-lookup"><span data-stu-id="aaca8-121">The following code fragment shows the attributes for the `Point` UDT.</span></span>  
  
```vb  
<Serializable(), SqlUserDefinedTypeAttribute(Format.Native, _  
  IsByteOrdered:=True)> _  
  Public Structure Point  
    Implements INullable  
```  
  
```csharp  
[Serializable]  
[Microsoft.SqlServer.Server.SqlUserDefinedType(Format.Native,  
  IsByteOrdered=true)]  
public struct Point : INullable  
{  
```  
  
## <a name="implementing-nullability"></a><span data-ttu-id="aaca8-122">Реализация допустимости значений NULL</span><span class="sxs-lookup"><span data-stu-id="aaca8-122">Implementing Nullability</span></span>  
 <span data-ttu-id="aaca8-123">Помимо задания необходимых атрибутов для сборок определяемый пользователем тип должен также поддерживать допустимость значений NULL.</span><span class="sxs-lookup"><span data-stu-id="aaca8-123">In addition to specifying the attributes for your assemblies correctly, your UDT must also support nullability.</span></span> <span data-ttu-id="aaca8-124">Определяемые пользователем типы, загружаемые в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], позволяют работать со значениями NULL, но условием того, чтобы определяемый пользователем тип распознавал значение NULL, является реализация интерфейса `System.Data.SqlTypes.INullable`.</span><span class="sxs-lookup"><span data-stu-id="aaca8-124">UDTs loaded into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are null-aware, but in order for the UDT to recognize a null value, the UDT must implement the `System.Data.SqlTypes.INullable` interface.</span></span>  
  
 <span data-ttu-id="aaca8-125">Следует создать свойство с именем `IsNull`, необходимое для распознавания значений NULL из кода CLR.</span><span class="sxs-lookup"><span data-stu-id="aaca8-125">You must create a property named `IsNull`, which is needed to determine whether a value is null from within CLR code.</span></span> <span data-ttu-id="aaca8-126">При обнаружении в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] экземпляра определяемого пользователем типа со значением NULL происходит его сохранение с использованием обычных методов работы со значениями NULL.</span><span class="sxs-lookup"><span data-stu-id="aaca8-126">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] finds a null instance of a UDT, the UDT is persisted using normal null-handling methods.</span></span> <span data-ttu-id="aaca8-127">Сервер не теряет времени на сериализацию и десериализацию определяемого пользователем типа, обнаруживая, что это не требуется, а также не расходует место для хранения определяемого пользователем типа со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="aaca8-127">The server does not waste time serializing or deserializing the UDT if it does not have to, and it does not waste space to store a null UDT.</span></span> <span data-ttu-id="aaca8-128">Проверка на наличие значений NULL проводится каждый раз, когда значение определяемого пользователем типа передается из среды CLR, а это означает, что конструкция языка [!INCLUDE[tsql](../../includes/tsql-md.md)] IS NULL для проверки определяемых пользователем типов на значения NULL всегда должна работать.</span><span class="sxs-lookup"><span data-stu-id="aaca8-128">This check for nulls is performed every time a UDT is brought over from the CLR, which means that using the [!INCLUDE[tsql](../../includes/tsql-md.md)] IS NULL construct to check for null UDTs should always work.</span></span> <span data-ttu-id="aaca8-129">Свойство `IsNull` используется также сервером для проверки равенства экземпляра значению NULL.</span><span class="sxs-lookup"><span data-stu-id="aaca8-129">The `IsNull` property is also used by the server to test whether an instance is null.</span></span> <span data-ttu-id="aaca8-130">Если сервер определил, что определяемый пользователем тип равен NULL, то может использовать собственные методы работы со значениями NULL.</span><span class="sxs-lookup"><span data-stu-id="aaca8-130">Once the server determines that the UDT is null, it can use its native null handling.</span></span>  
  
 <span data-ttu-id="aaca8-131">Метод `get()` свойства `IsNull` не рассчитан на возникновение каких-либо особых случаев.</span><span class="sxs-lookup"><span data-stu-id="aaca8-131">The `get()` method of `IsNull` is not special-cased in any way.</span></span> <span data-ttu-id="aaca8-132">Если переменная типа `Point``@p` равна `Null`, то выражение `@p.IsNull` по определению равно «NULL», а не «1».</span><span class="sxs-lookup"><span data-stu-id="aaca8-132">If a `Point` variable `@p` is `Null`, then `@p.IsNull` will, by default, evaluate to "NULL", not "1".</span></span> <span data-ttu-id="aaca8-133">Это объясняется тем, что атрибут `SqlMethod(OnNullCall)` метода `IsNull get()` по умолчанию имеет значение «false».</span><span class="sxs-lookup"><span data-stu-id="aaca8-133">This is because the `SqlMethod(OnNullCall)` attribute of the `IsNull get()` method defaults to false.</span></span> <span data-ttu-id="aaca8-134">Таким образом, объект равен `Null`, поэтому при запросе этого свойства объект не десериализуется, метод не вызывается и происходит возврат значения по умолчанию «NULL».</span><span class="sxs-lookup"><span data-stu-id="aaca8-134">Because the object is `Null`, when the property is requested the object is not deserialized, the method is not called, and a default value of "NULL" is returned.</span></span>  
  
### <a name="example"></a><span data-ttu-id="aaca8-135">Пример</span><span class="sxs-lookup"><span data-stu-id="aaca8-135">Example</span></span>  
 <span data-ttu-id="aaca8-136">В следующем примере переменная `is_Null` является закрытой и хранит состояние NULL экземпляра определяемого пользователем типа.</span><span class="sxs-lookup"><span data-stu-id="aaca8-136">In the following example, the `is_Null` variable is private and holds the state of null for the instance of the UDT.</span></span> <span data-ttu-id="aaca8-137">В программном коде должно поддерживаться соответствующее значение переменной `is_Null`.</span><span class="sxs-lookup"><span data-stu-id="aaca8-137">Your code must maintain an appropriate value for `is_Null`.</span></span> <span data-ttu-id="aaca8-138">Определяемый пользователем тип должен также иметь статическое свойство с именем `Null`, возвращающее экземпляр определяемого пользователем типа со значением (равным NULL).</span><span class="sxs-lookup"><span data-stu-id="aaca8-138">The UDT must also have a static property named `Null` that returns a null value instance of the UDT.</span></span> <span data-ttu-id="aaca8-139">Это позволяет возвращать значение NULL в определяемом пользователем типе, если экземпляр в базе данных действительно равен NULL.</span><span class="sxs-lookup"><span data-stu-id="aaca8-139">This allows the UDT to return a null value if the instance is indeed null in the database.</span></span>  
  
```vb  
Private is_Null As Boolean  
  
Public ReadOnly Property IsNull() As Boolean _  
   Implements INullable.IsNull  
    Get  
        Return (is_Null)  
    End Get  
End Property  
  
Public Shared ReadOnly Property Null() As Point  
    Get  
        Dim pt As New Point  
        pt.is_Null = True  
        Return (pt)  
    End Get  
End Property  
```  
  
```csharp  
private bool is_Null;  
  
public bool IsNull  
{  
    get  
    {  
        return (is_Null);  
    }  
}  
  
public static Point Null  
{  
    get  
    {  
        Point pt = new Point();  
        pt.is_Null = true;  
        return pt;  
    }  
}  
```  
  
### <a name="is-null-vs-isnull"></a><span data-ttu-id="aaca8-140">IS NULL и IsNull</span><span class="sxs-lookup"><span data-stu-id="aaca8-140">IS NULL vs. IsNull</span></span>  
 <span data-ttu-id="aaca8-141">Рассмотрим таблицу, содержащую схему Points(id int, location Point), где тип `Point` представляет собой определяемый пользователем тип среды CLR, и следующие запросы:</span><span class="sxs-lookup"><span data-stu-id="aaca8-141">Consider a table that contains the schema Points(id int, location Point), where `Point` is a CLR UDT, and the following queries:</span></span>  
  
```  
--Query 1  
SELECT ID  
FROM Points  
WHERE NOT (location IS NULL) -- Or, WHERE location IS NOT NULL;  
```  
  
```  
--Query 2:  
SELECT ID  
FROM Points  
WHERE location.IsNull = 0;  
```  
  
 <span data-ttu-id="aaca8-142">Оба запроса возвращают идентификаторы точек, местонахождение которых отлично от `Null`.</span><span class="sxs-lookup"><span data-stu-id="aaca8-142">Both queries return the IDs of points with non-`Null` locations.</span></span> <span data-ttu-id="aaca8-143">В запросе 1 используется нормальная обработка значений NULL, а десериализация определяемых пользователем типов не требуется.</span><span class="sxs-lookup"><span data-stu-id="aaca8-143">In Query 1, normal null-handling is used, and there no deserialization of UDTs is required.</span></span> <span data-ttu-id="aaca8-144">С другой стороны, в запросе 2 приходится обеспечивать десериализацию каждого объекта, отличного от `Null`, и вызывать среду CLR для получения значения свойства `IsNull`.</span><span class="sxs-lookup"><span data-stu-id="aaca8-144">Query 2, on the other hand, has to deserialize each non-`Null` object and call into the CLR to obtain the value of the `IsNull` property.</span></span> <span data-ttu-id="aaca8-145">Очевидно, что использование `IS NULL` позволяет достичь более высокой производительности, поэтому нет никакого смысла прибегать к чтению значения свойства `IsNull` определяемого пользователем типа из кода [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aaca8-145">Clearly, using `IS NULL` will exhibit better performance and there should never be a reason to read the `IsNull` property of a UDT from [!INCLUDE[tsql](../../includes/tsql-md.md)] code.</span></span>  
  
 <span data-ttu-id="aaca8-146">Так для чего же используется свойство `IsNull`?</span><span class="sxs-lookup"><span data-stu-id="aaca8-146">So, what is the use of the `IsNull` property?</span></span> <span data-ttu-id="aaca8-147">Во-первых, для определения того, получено ли значение `Null` из кода CLR.</span><span class="sxs-lookup"><span data-stu-id="aaca8-147">First, it is needed to determine whether a value is `Null` from within CLR code.</span></span> <span data-ttu-id="aaca8-148">Во-вторых, серверу требуется способ проверки того, имеет ли экземпляр значение `Null`, поэтому это свойство также используется сервером.</span><span class="sxs-lookup"><span data-stu-id="aaca8-148">Second, the server needs a way to test whether an instance is `Null`, so this property is used by the server.</span></span> <span data-ttu-id="aaca8-149">После определения, что экземпляр действительно равен `Null`, сервер может использовать собственные методы работы со значениями NULL.</span><span class="sxs-lookup"><span data-stu-id="aaca8-149">After it determines it is `Null`, then it can use its native null handling to handle it.</span></span>  
  
## <a name="implementing-the-parse-method"></a><span data-ttu-id="aaca8-150">Реализация синтаксического анализа</span><span class="sxs-lookup"><span data-stu-id="aaca8-150">Implementing the Parse Method</span></span>  
 <span data-ttu-id="aaca8-151">Методы `Parse` и `ToString` осуществляют прямые и обратные преобразования определяемых пользователем типов в строки.</span><span class="sxs-lookup"><span data-stu-id="aaca8-151">The `Parse` and `ToString` methods allow for conversions to and from string representations of the UDT.</span></span> <span data-ttu-id="aaca8-152">Метод `Parse` позволяет преобразовывать строку в определяемый пользователем тип.</span><span class="sxs-lookup"><span data-stu-id="aaca8-152">The `Parse` method allows a string to be converted into a UDT.</span></span> <span data-ttu-id="aaca8-153">Он должен быть объявлен как `static` (или `Shared` в Visual Basic) и принимать параметр типа `System.Data.SqlTypes.SqlString`.</span><span class="sxs-lookup"><span data-stu-id="aaca8-153">It must be declared as `static` (or `Shared` in Visual Basic), and take a parameter of type `System.Data.SqlTypes.SqlString`.</span></span>  
  
 <span data-ttu-id="aaca8-154">В данном примере реализован метод `Parse` для определяемого пользователем типа `Point`, который выделяет координаты X и Y.</span><span class="sxs-lookup"><span data-stu-id="aaca8-154">The following code implements the `Parse` method for the `Point` UDT, which separates out the X and Y coordinates.</span></span> <span data-ttu-id="aaca8-155">Метод `Parse` имеет единственный аргумент типа `System.Data.SqlTypes.SqlString`, причем предполагается, что величины X и Y передаются в виде строки, разделенной запятыми.</span><span class="sxs-lookup"><span data-stu-id="aaca8-155">The `Parse` method has a single argument of type `System.Data.SqlTypes.SqlString`, and assumes that X and Y values are supplied as a comma-delimited string.</span></span> <span data-ttu-id="aaca8-156">Присваивание атрибуту `Microsoft.SqlServer.Server.SqlMethodAttribute.OnNullCall` значения `false` гарантирует, что метод `Parse` не может быть вызван из экземпляра Point (равного NULL).</span><span class="sxs-lookup"><span data-stu-id="aaca8-156">Setting the `Microsoft.SqlServer.Server.SqlMethodAttribute.OnNullCall` attribute to `false` prevents the `Parse` method from being called from a null instance of Point.</span></span>  
  
```vb  
<SqlMethod(OnNullCall:=False)> _  
Public Shared Function Parse(ByVal s As SqlString) As Point  
    If s.IsNull Then  
        Return Null  
    End If  
  
    ' Parse input string here to separate out points.  
    Dim pt As New Point()  
    Dim xy() As String = s.Value.Split(",".ToCharArray())  
    pt.X = Int32.Parse(xy(0))  
    pt.Y = Int32.Parse(xy(1))  
    Return pt  
End Function  
```  
  
```csharp  
[SqlMethod(OnNullCall = false)]  
public static Point Parse(SqlString s)  
{  
    if (s.IsNull)  
        return Null;  
  
    // Parse input string to separate out points.  
    Point pt = new Point();  
    string[] xy = s.Value.Split(",".ToCharArray());  
    pt.X = Int32.Parse(xy[0]);  
    pt.Y = Int32.Parse(xy[1]);  
    return pt;  
}  
```  
  
## <a name="implementing-the-tostring-method"></a><span data-ttu-id="aaca8-157">Реализация метода ToString</span><span class="sxs-lookup"><span data-stu-id="aaca8-157">Implementing the ToString Method</span></span>  
 <span data-ttu-id="aaca8-158">Метод `ToString` преобразует значение определяемого пользователем типа `Point` в строку.</span><span class="sxs-lookup"><span data-stu-id="aaca8-158">The `ToString` method converts the `Point` UDT to a string value.</span></span> <span data-ttu-id="aaca8-159">В данном случае для экземпляра `Point`, равного NULL, будет возвращено строковое значение «NULL».</span><span class="sxs-lookup"><span data-stu-id="aaca8-159">In this case, the string "NULL" is returned for a Null instance of the `Point` type.</span></span> <span data-ttu-id="aaca8-160">Метод `ToString` является обратным по отношению к методу `Parse`, поскольку в нем используется класс `System.Text.StringBuilder` для возврата разделенной запятыми строки типа `System.String`, содержащей значения координат X и Y.</span><span class="sxs-lookup"><span data-stu-id="aaca8-160">The `ToString` method reverses the `Parse` method by using a `System.Text.StringBuilder` to return a comma-delimited `System.String` consisting of the X and Y coordinate values.</span></span> <span data-ttu-id="aaca8-161">Так как **инвокеифрецеивериснулл** по умолчанию имеет значение false, проверка экземпляра со значением NULL `Point` не требуется.</span><span class="sxs-lookup"><span data-stu-id="aaca8-161">Because **InvokeIfReceiverIsNull** defaults to false, the check for a null instance of `Point` is unnecessary.</span></span>  
  
```vb  
Private _x As Int32  
Private _y As Int32  
  
Public Overrides Function ToString() As String  
    If Me.IsNull Then  
        Return "NULL"  
    Else  
        Dim builder As StringBuilder = New StringBuilder  
        builder.Append(_x)  
        builder.Append(",")  
        builder.Append(_y)  
        Return builder.ToString  
    End If  
End Function  
```  
  
```csharp  
private Int32 _x;  
private Int32 _y;  
  
public override string ToString()  
{  
    if (this.IsNull)  
        return "NULL";  
    else  
    {  
        StringBuilder builder = new StringBuilder();  
        builder.Append(_x);  
        builder.Append(",");  
        builder.Append(_y);  
        return builder.ToString();  
    }  
}  
```  
  
## <a name="exposing-udt-properties"></a><span data-ttu-id="aaca8-162">Предоставление доступа к свойствам определяемого пользователем типа</span><span class="sxs-lookup"><span data-stu-id="aaca8-162">Exposing UDT Properties</span></span>  
 <span data-ttu-id="aaca8-163">Определяемый пользователем тип `Point` предоставляет доступ к координатам X и Y, реализованным как процедуры свойств для чтения и записи, относящиеся к типу `System.Int32`.</span><span class="sxs-lookup"><span data-stu-id="aaca8-163">The `Point` UDT exposes X and Y coordinates that are implemented as public read-write properties of type `System.Int32`.</span></span>  
  
```vb  
Public Property X() As Int32  
    Get  
        Return (Me._x)  
    End Get  
  
    Set(ByVal Value As Int32)  
        _x = Value  
    End Set  
End Property  
  
Public Property Y() As Int32  
    Get  
        Return (Me._y)  
    End Get  
  
    Set(ByVal Value As Int32)  
        _y = Value  
    End Set  
End Property  
```  
  
```csharp  
public Int32 X  
{  
    get  
    {  
        return this._x;  
    }  
    set   
    {  
        _x = value;  
    }  
}  
  
public Int32 Y  
{  
    get  
    {  
        return this._y;  
    }  
    set  
    {  
        _y = value;  
    }  
}  
```  
  
## <a name="validating-udt-values"></a><span data-ttu-id="aaca8-164">Проверка значений определяемого пользователем типа</span><span class="sxs-lookup"><span data-stu-id="aaca8-164">Validating UDT Values</span></span>  
 <span data-ttu-id="aaca8-165">При работе с определяемым пользователем типом компонент [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] автоматически преобразовывает двоичные значения в значения определяемого пользователем типа.</span><span class="sxs-lookup"><span data-stu-id="aaca8-165">When working with UDT data, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] automatically converts binary values to UDT values.</span></span> <span data-ttu-id="aaca8-166">Этот процесс преобразования включает в себя проверку соответствия значений формату сериализации и проверку того, что значения могут быть десериализованы правильно.</span><span class="sxs-lookup"><span data-stu-id="aaca8-166">This conversion process involves checking that values are appropriate for the serialization format of the type and ensuring that the value can be deserialized correctly.</span></span> <span data-ttu-id="aaca8-167">Это гарантирует, что значение может быть преобразовано обратно в двоичную форму.</span><span class="sxs-lookup"><span data-stu-id="aaca8-167">This ensures that the value can be converted back to binary form.</span></span> <span data-ttu-id="aaca8-168">В случае определяемого пользователем типа с заданным порядком байтов это также гарантирует, что результирующее двоичное значение совпадет с исходным.</span><span class="sxs-lookup"><span data-stu-id="aaca8-168">In the case of byte-ordered UDTs, this also ensures that the resulting binary value matches the original binary value.</span></span> <span data-ttu-id="aaca8-169">Благодаря этому предотвращается сохранение недопустимых значений в базе данных.</span><span class="sxs-lookup"><span data-stu-id="aaca8-169">This prevents invalid values from being persisted in the database.</span></span> <span data-ttu-id="aaca8-170">В некоторых случаях такой уровень проверки недостаточен.</span><span class="sxs-lookup"><span data-stu-id="aaca8-170">In some cases, this level of checking may be inadequate.</span></span> <span data-ttu-id="aaca8-171">Если значения определяемого пользователем типа должны находиться в определенной области или диапазоне, то может потребоваться дополнительная проверка.</span><span class="sxs-lookup"><span data-stu-id="aaca8-171">Additional validation may be required when UDT values are required to be in an expected domain or range.</span></span> <span data-ttu-id="aaca8-172">Например, для определяемого пользователем типа, реализующего дату, может потребоваться, чтобы день был положительным числом, попадающим в определенный диапазон допустимых значений.</span><span class="sxs-lookup"><span data-stu-id="aaca8-172">For example, a UDT that implements a date might require the day value to be a positive number that falls within a certain range of valid values.</span></span>  
  
 <span data-ttu-id="aaca8-173">Свойство `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute.ValidationMethodName` класса `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` позволяет задавать имя метода проверки, запускаемого сервером, когда значение присваивается определяемому пользователем типу или преобразуется в определяемый пользователем тип.</span><span class="sxs-lookup"><span data-stu-id="aaca8-173">The `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute.ValidationMethodName` property of the `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` allows you to supply the name of a validation method that the server runs when data is assigned to a UDT or converted to a UDT.</span></span> <span data-ttu-id="aaca8-174">Свойство `ValidationMethodName` вызывается также при запуске программы bcp, инструкций BULK INSERT, DBCC CHECKDB, DBCC CHECKFILEGROUP, DBCC CHECKTABLE, распределенного запроса и операций удаленных вызовов процедур (RPC) для потоков табличных данных (TDS).</span><span class="sxs-lookup"><span data-stu-id="aaca8-174">`ValidationMethodName` is also called during the running of the bcp utility, BULK INSERT, DBCC CHECKDB, DBCC CHECKFILEGROUP, DBCC CHECKTABLE, distributed query, and tabular data stream (TDS) remote procedure call (RPC) operations.</span></span> <span data-ttu-id="aaca8-175">Значение по умолчанию для метода `ValidationMethodName` равно NULL. Это означает, что метод проверки не задан.</span><span class="sxs-lookup"><span data-stu-id="aaca8-175">The default value for `ValidationMethodName` is null, indicating that there is no validation method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="aaca8-176">Пример</span><span class="sxs-lookup"><span data-stu-id="aaca8-176">Example</span></span>  
 <span data-ttu-id="aaca8-177">В следующем фрагменте кода для класса `Point` показана декларация, которая задает свойство `ValidationMethodName` метода `ValidatePoint`.</span><span class="sxs-lookup"><span data-stu-id="aaca8-177">The following code fragment shows the declaration for the `Point` class, which specifies a `ValidationMethodName` of `ValidatePoint`.</span></span>  
  
```vb  
<Serializable(), SqlUserDefinedTypeAttribute(Format.Native, _  
  IsByteOrdered:=True, _  
  ValidationMethodName:="ValidatePoint")> _  
  Public Structure Point  
```  
  
```csharp  
[Serializable]  
[Microsoft.SqlServer.Server.SqlUserDefinedType(Format.Native,  
  IsByteOrdered=true,   
  ValidationMethodName = "ValidatePoint")]  
public struct Point : INullable  
{  
```  
  
 <span data-ttu-id="aaca8-178">Если метод проверки задан, то должен иметь подпись, которая выглядит, как показано в следующем фрагменте кода:</span><span class="sxs-lookup"><span data-stu-id="aaca8-178">If a validation method is specified, it must have a signature that looks like the following code fragment.</span></span>  
  
```vb  
Private Function ValidationFunction() As Boolean  
    If (validation logic here) Then  
        Return True  
    Else  
        Return False  
    End If  
End Function  
```  
  
```csharp  
private bool ValidationFunction()  
{  
    if (validation logic here)  
    {  
        return true;  
    }  
    else  
    {  
        return false;  
    }  
}  
```  
  
 <span data-ttu-id="aaca8-179">Метод проверки может иметь любую область действия, возвращая `true`, если значение допустимо, и `false` — в противном случае.</span><span class="sxs-lookup"><span data-stu-id="aaca8-179">The validation method can have any scope and should return `true` if the value is valid, and `false` otherwise.</span></span> <span data-ttu-id="aaca8-180">Если метод возвращает `false` или создает исключение, считается, что значение недопустимо, и выдается соответствующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="aaca8-180">If the method returns `false` or throws an exception, the value is treated as not valid and an error is raised.</span></span>  
  
 <span data-ttu-id="aaca8-181">В приведенном примере кода для координат X и Y разрешаются только нулевые и положительные значения.</span><span class="sxs-lookup"><span data-stu-id="aaca8-181">In the example below, the code allows only values of zero or greater the X and Y coordinates.</span></span>  
  
```vb  
Private Function ValidatePoint() As Boolean  
    If (_x >= 0) And (_y >= 0) Then  
        Return True  
    Else  
        Return False  
    End If  
End Function  
```  
  
```csharp  
private bool ValidatePoint()  
{  
    if ((_x >= 0) && (_y >= 0))  
    {  
        return true;  
    }  
    else  
    {  
        return false;  
    }  
}  
```  
  
### <a name="validation-method-limitations"></a><span data-ttu-id="aaca8-182">Ограничения метода проверки</span><span class="sxs-lookup"><span data-stu-id="aaca8-182">Validation Method Limitations</span></span>  
 <span data-ttu-id="aaca8-183">Сервер вызывает метод проверки при проведении преобразований, а не в тот момент, когда данные вставляются с помощью задания отдельных свойств или с помощью инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT.</span><span class="sxs-lookup"><span data-stu-id="aaca8-183">The server calls the validation method when the server is performing conversions, not when data is inserted by setting individual properties or when data is inserted using a [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT statement.</span></span>  
  
 <span data-ttu-id="aaca8-184">Необходимо явно вызвать метод проверки из методов задания свойств и `Parse` метода, если требуется, чтобы метод проверки выполнялся во всех ситуациях.</span><span class="sxs-lookup"><span data-stu-id="aaca8-184">You must explicitly call the validation method from property setters and the `Parse` method if you want the validation method to execute in all situations.</span></span> <span data-ttu-id="aaca8-185">Это не является требованием и в некоторых случаях даже нежелательно.</span><span class="sxs-lookup"><span data-stu-id="aaca8-185">This is not a requirement, and in some cases may not even be desirable.</span></span>  
  
### <a name="parse-validation-example"></a><span data-ttu-id="aaca8-186">Пример проверки при синтаксическом анализе</span><span class="sxs-lookup"><span data-stu-id="aaca8-186">Parse Validation Example</span></span>  
 <span data-ttu-id="aaca8-187">Чтобы обеспечить `ValidatePoint` вызов метода в `Point` классе, необходимо вызвать его из `Parse` метода и из процедур свойств, устанавливающих значения координат X и Y.</span><span class="sxs-lookup"><span data-stu-id="aaca8-187">To ensure that the `ValidatePoint` method is invoked in the `Point` class, you must call it from the `Parse` method and from the property procedures that set the X and Y coordinate values.</span></span> <span data-ttu-id="aaca8-188">В следующем фрагменте кода показано, как вызвать `ValidatePoint` метод проверки из `Parse` функции.</span><span class="sxs-lookup"><span data-stu-id="aaca8-188">The following code fragment shows how to call the `ValidatePoint` validation method from the `Parse` function.</span></span>  
  
```vb  
<SqlMethod(OnNullCall:=False)> _  
Public Shared Function Parse(ByVal s As SqlString) As Point  
    If s.IsNull Then  
        Return Null  
    End If  
  
    ' Parse input string here to separate out points.  
    Dim pt As New Point()  
    Dim xy() As String = s.Value.Split(",".ToCharArray())  
    pt.X = Int32.Parse(xy(0))  
    pt.Y = Int32.Parse(xy(1))  
  
    ' Call ValidatePoint to enforce validation  
    ' for string conversions.  
    If Not pt.ValidatePoint() Then  
        Throw New ArgumentException("Invalid XY coordinate values.")  
    End If  
    Return pt  
End Function  
```  
  
```csharp  
[SqlMethod(OnNullCall = false)]  
public static Point Parse(SqlString s)  
{  
    if (s.IsNull)  
        return Null;  
  
    // Parse input string to separate out points.  
    Point pt = new Point();  
    string[] xy = s.Value.Split(",".ToCharArray());  
    pt.X = Int32.Parse(xy[0]);  
    pt.Y = Int32.Parse(xy[1]);  
  
    // Call ValidatePoint to enforce validation  
    // for string conversions.  
    if (!pt.ValidatePoint())   
        throw new ArgumentException("Invalid XY coordinate values.");  
    return pt;  
}  
```  
  
### <a name="property-validation-example"></a><span data-ttu-id="aaca8-189">Пример проверки при операциях над свойствами</span><span class="sxs-lookup"><span data-stu-id="aaca8-189">Property Validation Example</span></span>  
 <span data-ttu-id="aaca8-190">В следующем фрагменте кода показано, как вызвать `ValidatePoint` метод проверки из процедур свойств, устанавливающих координаты X и Y.</span><span class="sxs-lookup"><span data-stu-id="aaca8-190">The following code fragment shows how to call the `ValidatePoint` validation method from the property procedures that set the X and Y coordinates.</span></span>  
  
```vb  
Public Property X() As Int32  
    Get  
        Return (Me._x)  
    End Get  
  
    Set(ByVal Value As Int32)  
        Dim temp As Int32 = _x  
        _x = Value  
        If Not ValidatePoint() Then  
            _x = temp  
            Throw New ArgumentException("Invalid X coordinate value.")  
        End If  
    End Set  
End Property  
  
Public Property Y() As Int32  
    Get  
        Return (Me._y)  
    End Get  
  
    Set(ByVal Value As Int32)  
        Dim temp As Int32 = _y  
        _y = Value  
        If Not ValidatePoint() Then  
            _y = temp  
            Throw New ArgumentException("Invalid Y coordinate value.")  
        End If  
    End Set  
End Property  
```  
  
```csharp  
    public Int32 X  
{  
    get  
    {  
        return this._x;  
    }  
    // Call ValidatePoint to ensure valid range of Point values.  
    set   
    {  
        Int32 temp = _x;  
        _x = value;  
        if (!ValidatePoint())  
        {  
            _x = temp;  
            throw new ArgumentException("Invalid X coordinate value.");  
        }  
    }  
}  
  
public Int32 Y  
{  
    get  
    {  
        return this._y;  
    }  
    set  
    {  
        Int32 temp = _y;  
        _y = value;  
        if (!ValidatePoint())  
        {  
            _y = temp;  
            throw new ArgumentException("Invalid Y coordinate value.");  
        }  
    }  
}  
```  
  
## <a name="coding-udt-methods"></a><span data-ttu-id="aaca8-191">Реализация методов определяемого пользователем типа</span><span class="sxs-lookup"><span data-stu-id="aaca8-191">Coding UDT Methods</span></span>  
 <span data-ttu-id="aaca8-192">При реализации методов определяемого пользователем типа следует учитывать возможность изменения алгоритма в будущем.</span><span class="sxs-lookup"><span data-stu-id="aaca8-192">When coding UDT methods, consider whether the algorithm used could possibly change over time.</span></span> <span data-ttu-id="aaca8-193">Если такая возможность имеется, то следует создать отдельный класс для методов, используемых определяемым пользователем типом.</span><span class="sxs-lookup"><span data-stu-id="aaca8-193">If so, you may want to consider creating a separate class for the methods your UDT uses.</span></span> <span data-ttu-id="aaca8-194">Если алгоритм изменится, можно будет перекомпилировать класс с новым кодом и загрузить сборку в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], не затрагивая определяемый пользователем тип.</span><span class="sxs-lookup"><span data-stu-id="aaca8-194">If the algorithm changes, you can recompile the class with the new code and load the assembly into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without affecting the UDT.</span></span> <span data-ttu-id="aaca8-195">Во многих случаях определяемые пользователем типы можно загружать заново с помощью инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] ALTER ASSEMBLY, но это может вызвать проблемы с существующими данными.</span><span class="sxs-lookup"><span data-stu-id="aaca8-195">In many cases UDTs can be reloaded using the [!INCLUDE[tsql](../../includes/tsql-md.md)] ALTER ASSEMBLY statement, but that could potentially cause problems with existing data.</span></span> <span data-ttu-id="aaca8-196">Например, `Currency` определяемый пользователем тип, входящий в образец базы данных **AdventureWorks** , использует функцию **ConvertCurrency** для преобразования значений валют, которые реализуются в отдельном классе.</span><span class="sxs-lookup"><span data-stu-id="aaca8-196">For example, the `Currency` UDT included with the **AdventureWorks** sample database uses a **ConvertCurrency** function to convert currency values, which is implemented in a separate class.</span></span> <span data-ttu-id="aaca8-197">Возможно, что в будущем алгоритмы преобразования изменятся непредсказуемым образом или потребуются новые функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="aaca8-197">It is possible that conversion algorithms may change in unpredictable ways in the future, or that new functionality may be required.</span></span> <span data-ttu-id="aaca8-198">Отделение функции **ConvertCurrency** от `Currency` реализации определяемого пользователем типа обеспечивает большую гибкость при планировании будущих изменений.</span><span class="sxs-lookup"><span data-stu-id="aaca8-198">Separating the **ConvertCurrency** function from the `Currency` UDT implementation provides greater flexibility when planning for future changes.</span></span>  
  
### <a name="example"></a><span data-ttu-id="aaca8-199">Пример</span><span class="sxs-lookup"><span data-stu-id="aaca8-199">Example</span></span>  
 <span data-ttu-id="aaca8-200">`Point`Класс содержит три простых метода для вычисления расстояния: **Distance**, **дистанцефром** и **дистанцефромкси**.</span><span class="sxs-lookup"><span data-stu-id="aaca8-200">The `Point` class contains three simple methods for calculating distance: **Distance**, **DistanceFrom** and **DistanceFromXY**.</span></span> <span data-ttu-id="aaca8-201">Каждый из методов возвращает значение `double`, равное расстоянию от `Point` до начала координат, от указанной точки до объекта `Point` и от заданных координат X и Y до объекта `Point`.</span><span class="sxs-lookup"><span data-stu-id="aaca8-201">Each returns a `double` calculating the distance from `Point` to zero, the distance from a specified point to `Point`, and the distance from specified X and Y coordinates to `Point`.</span></span> <span data-ttu-id="aaca8-202">**Distance** и **Дистанцефром** каждый вызов **дистанцефромкси**и демонстрирует, как использовать разные аргументы для каждого метода.</span><span class="sxs-lookup"><span data-stu-id="aaca8-202">**Distance** and **DistanceFrom** each call **DistanceFromXY**, and demonstrate how to use different arguments for each method.</span></span>  
  
```vb  
' Distance from 0 to Point.  
<SqlMethod(OnNullCall:=False)> _  
Public Function Distance() As Double  
    Return DistanceFromXY(0, 0)  
End Function  
  
' Distance from Point to the specified point.  
<SqlMethod(OnNullCall:=False)> _  
Public Function DistanceFrom(ByVal pFrom As Point) As Double  
    Return DistanceFromXY(pFrom.X, pFrom.Y)  
End Function  
  
' Distance from Point to the specified x and y values.  
<SqlMethod(OnNullCall:=False)> _  
Public Function DistanceFromXY(ByVal ix As Int32, ByVal iy As Int32) _  
    As Double  
    Return Math.Sqrt(Math.Pow(ix - _x, 2.0) + Math.Pow(iy - _y, 2.0))  
End Function  
```  
  
```csharp  
// Distance from 0 to Point.  
[SqlMethod(OnNullCall = false)]  
public Double Distance()  
{  
    return DistanceFromXY(0, 0);  
}  
  
// Distance from Point to the specified point.  
[SqlMethod(OnNullCall = false)]  
public Double DistanceFrom(Point pFrom)  
{  
    return DistanceFromXY(pFrom.X, pFrom.Y);  
}  
  
// Distance from Point to the specified x and y values.  
[SqlMethod(OnNullCall = false)]  
public Double DistanceFromXY(Int32 iX, Int32 iY)  
{  
    return Math.Sqrt(Math.Pow(iX - _x, 2.0) + Math.Pow(iY - _y, 2.0));  
}  
```  
  
### <a name="using-sqlmethod-attributes"></a><span data-ttu-id="aaca8-203">Использование атрибутов SqlMethod</span><span class="sxs-lookup"><span data-stu-id="aaca8-203">Using SqlMethod Attributes</span></span>  
 <span data-ttu-id="aaca8-204">Класс `Microsoft.SqlServer.Server.SqlMethodAttribute` предоставляет настраиваемые атрибуты, которые можно использовать в определениях метода, чтобы пометить метод как детерминированный, задать поведение при вызове на экземпляре (равном NULL) или указать, что метод является мутатором.</span><span class="sxs-lookup"><span data-stu-id="aaca8-204">The `Microsoft.SqlServer.Server.SqlMethodAttribute` class provides custom attributes that can be used to mark method definitions in order to specify determinism, on null call behavior, and to specify whether a method is a mutator.</span></span> <span data-ttu-id="aaca8-205">Предполагается, что эти свойства имеют определенные значения по умолчанию, а настраиваемый атрибут используется только тогда, когда необходимо задать другое значение.</span><span class="sxs-lookup"><span data-stu-id="aaca8-205">Default values for these properties are assumed, and the custom attribute is only used when a non-default value is needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aaca8-206">Класс `SqlMethodAttribute` наследуется от `SqlFunctionAttribute`, поэтому класс `SqlMethodAttribute` наследует поля `FillRowMethodName` и `TableDefinition` от класса `SqlFunctionAttribute`.</span><span class="sxs-lookup"><span data-stu-id="aaca8-206">The `SqlMethodAttribute` class inherits from the `SqlFunctionAttribute` class, so `SqlMethodAttribute` inherits the `FillRowMethodName` and `TableDefinition` fields from `SqlFunctionAttribute`.</span></span> <span data-ttu-id="aaca8-207">Это подразумевает, что существует возможность написать возвращающий табличное значение метод, который не является вариантом.</span><span class="sxs-lookup"><span data-stu-id="aaca8-207">This implies that it is possible to write a table-valued method, which is not the case.</span></span> <span data-ttu-id="aaca8-208">Метод компилируется, и сборка развертывается, но ошибка `IEnumerable` типа возвращаемого значения вызывается во время выполнения со следующим сообщением: "метод, свойство или поле" \<name> "в классе" \<class> "в сборке" \<assembly> "имеет недопустимый возвращаемый тип."</span><span class="sxs-lookup"><span data-stu-id="aaca8-208">The method compiles and the assembly deploys, but an error about the `IEnumerable` return type is raised at runtime with the following message: "Method, property, or field '\<name>' in class '\<class>' in assembly '\<assembly>' has invalid return type."</span></span>  
  
 <span data-ttu-id="aaca8-209">В следующей таблице рассматриваются некоторые важные свойства класса `Microsoft.SqlServer.Server.SqlMethodAttribute`, которые можно использовать для методов определяемого пользователем типа, и перечисляются их значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aaca8-209">The following table describes some of the relevant `Microsoft.SqlServer.Server.SqlMethodAttribute` properties that can be used in UDT methods, and lists their default values.</span></span>  
  
 <span data-ttu-id="aaca8-210">DataAccess</span><span class="sxs-lookup"><span data-stu-id="aaca8-210">DataAccess</span></span>  
 <span data-ttu-id="aaca8-211">Указывает, что функция производит доступ к пользовательским данным, хранимым в локальном экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aaca8-211">Indicates whether the function involves access to user data stored in the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="aaca8-212">Значение по умолчанию — `DataAccessKind``None`.</span><span class="sxs-lookup"><span data-stu-id="aaca8-212">Default is `DataAccessKind`.`None`.</span></span>  
  
 <span data-ttu-id="aaca8-213">IsDeterministic</span><span class="sxs-lookup"><span data-stu-id="aaca8-213">IsDeterministic</span></span>  
 <span data-ttu-id="aaca8-214">Указывает, производит ли функция одни и те же выходные значения при одинаковых наборах входных значений и одинаковых состояниях базы данных.</span><span class="sxs-lookup"><span data-stu-id="aaca8-214">Indicates whether the function produces the same output values given the same input values and the same database state.</span></span> <span data-ttu-id="aaca8-215">По умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="aaca8-215">Default is `false`.</span></span>  
  
 <span data-ttu-id="aaca8-216">IsMutator</span><span class="sxs-lookup"><span data-stu-id="aaca8-216">IsMutator</span></span>  
 <span data-ttu-id="aaca8-217">Указывает, вызывает ли метод изменение состояния экземпляра определяемого пользователем типа.</span><span class="sxs-lookup"><span data-stu-id="aaca8-217">Indicates whether the method causes a state change in the UDT instance.</span></span> <span data-ttu-id="aaca8-218">По умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="aaca8-218">Default is `false`.</span></span>  
  
 <span data-ttu-id="aaca8-219">IsPrecise</span><span class="sxs-lookup"><span data-stu-id="aaca8-219">IsPrecise</span></span>  
 <span data-ttu-id="aaca8-220">Указывает, содержит ли функция вычисления с потерей точности (например, операции с плавающей запятой).</span><span class="sxs-lookup"><span data-stu-id="aaca8-220">Indicates whether the function involves imprecise computations, such as floating point operations.</span></span> <span data-ttu-id="aaca8-221">По умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="aaca8-221">Default is `false`.</span></span>  
  
 <span data-ttu-id="aaca8-222">OnNullCall</span><span class="sxs-lookup"><span data-stu-id="aaca8-222">OnNullCall</span></span>  
 <span data-ttu-id="aaca8-223">Указывает, вызывается ли метод, если в качестве ссылки на входные аргументы заданы значения NULL.</span><span class="sxs-lookup"><span data-stu-id="aaca8-223">Indicates whether the method is called when null reference input arguments are specified.</span></span> <span data-ttu-id="aaca8-224">По умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="aaca8-224">Default is `true`.</span></span>  
  
### <a name="example"></a><span data-ttu-id="aaca8-225">Пример</span><span class="sxs-lookup"><span data-stu-id="aaca8-225">Example</span></span>  
 <span data-ttu-id="aaca8-226">Свойство `Microsoft.SqlServer.Server.SqlMethodAttribute.IsMutator` позволяет указать, что метод производит изменение состояния экземпляра определяемого пользователем типа.</span><span class="sxs-lookup"><span data-stu-id="aaca8-226">The `Microsoft.SqlServer.Server.SqlMethodAttribute.IsMutator` property allows you to mark a method that allows a change in the state of an instance of a UDT.</span></span> <span data-ttu-id="aaca8-227">Язык [!INCLUDE[tsql](../../includes/tsql-md.md)] не позволяет задать два свойства определяемого пользователем типа в предложении SET одной инструкции UPDATE.</span><span class="sxs-lookup"><span data-stu-id="aaca8-227">[!INCLUDE[tsql](../../includes/tsql-md.md)] does not allow you to set two UDT properties in the SET clause of one UPDATE statement.</span></span> <span data-ttu-id="aaca8-228">Однако можно создать метод-мутатор, изменяющий два члена определяемого пользователем типа сразу.</span><span class="sxs-lookup"><span data-stu-id="aaca8-228">However, you can have a method marked as a mutator that changes the two members.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aaca8-229">Методы-мутаторы в запросах не допускаются.</span><span class="sxs-lookup"><span data-stu-id="aaca8-229">Mutator methods are not allowed in queries.</span></span> <span data-ttu-id="aaca8-230">Их можно вызывать только в инструкциях присваивания или изменения данных.</span><span class="sxs-lookup"><span data-stu-id="aaca8-230">They can be called only in assignment statements or data modification statements.</span></span> <span data-ttu-id="aaca8-231">Если метод, помеченный как мутатор, не возвращает `void` (или в языке Visual Basic не представляет собой `Sub`), то выполнение инструкции CREATE TYPE завершится с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="aaca8-231">If a method marked as mutator does not return `void` (or is not a `Sub` in Visual Basic), CREATE TYPE fails with an error.</span></span>  
  
 <span data-ttu-id="aaca8-232">Следующая инструкция подразумевает наличие определяемого пользователем типа `Triangles`, имеющего метод `Rotate`.</span><span class="sxs-lookup"><span data-stu-id="aaca8-232">The following statement assumes the existence of a `Triangles` UDT that has a `Rotate` method.</span></span> <span data-ttu-id="aaca8-233">В следующей инструкции изменения данных языка [!INCLUDE[tsql](../../includes/tsql-md.md)] вызывается метод `Rotate`:</span><span class="sxs-lookup"><span data-stu-id="aaca8-233">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] update statement invokes the `Rotate` method:</span></span>  
  
```  
UPDATE Triangles SET t.RotateY(0.6) WHERE id=5  
```  
  
 <span data-ttu-id="aaca8-234">Метод `Rotate` обозначается атрибутом `SqlMethod` со свойством `IsMutator` (равным `true`), так что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может пометить этот метод как мутатор.</span><span class="sxs-lookup"><span data-stu-id="aaca8-234">The `Rotate` method is decorated with the `SqlMethod` attribute setting `IsMutator` to `true` so that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can mark the method as a mutator method.</span></span> <span data-ttu-id="aaca8-235">Кроме того, в данном коде для атрибута `OnNullCall` задается значение `false`, а это служит для сервера указанием, что метод возвращает ссылку, равную NULL (в языке Visual Basic — `Nothing`), если любой из входных параметров представляет собой ссылку, равную NULL.</span><span class="sxs-lookup"><span data-stu-id="aaca8-235">The code also sets `OnNullCall` to `false`, which indicates to the server that the method returns a null reference (`Nothing` in Visual Basic) if any of the input parameters are null references.</span></span>  
  
```vb  
<SqlMethod(IsMutator:=True, OnNullCall:=False)> _  
Public Sub Rotate(ByVal anglex as Double, _  
  ByVal angley as Double, ByVal anglez As Double)   
   RotateX(anglex)  
   RotateY(angley)  
   RotateZ(anglez)  
End Sub  
```  
  
```csharp  
[SqlMethod(IsMutator = true, OnNullCall = false)]  
public void Rotate(double anglex, double angley, double anglez)   
{  
   RotateX(anglex);  
   RotateY(angley);  
   RotateZ(anglez);  
}  
```  
  
## <a name="implementing-a-udt-with-a-user-defined-format"></a><span data-ttu-id="aaca8-236">Реализация определяемого пользователем типа в определяемом пользователем формате</span><span class="sxs-lookup"><span data-stu-id="aaca8-236">Implementing a UDT with a User-Defined Format</span></span>  
 <span data-ttu-id="aaca8-237">При реализации определяемого пользователем типа в определяемом пользователем формате необходимо реализовать методы `Read` и `Write`, реализующие интерфейс Microsoft.SqlServer.Server.IBinarySerialize для сериализации и десериализации данных определяемого пользователем типа.</span><span class="sxs-lookup"><span data-stu-id="aaca8-237">When implementing a UDT with a user-defined format, you must implement `Read` and `Write` methods that implement the Microsoft.SqlServer.Server.IBinarySerialize interface to handle serializing and deserializing UDT data.</span></span> <span data-ttu-id="aaca8-238">Необходимо также задать свойство `MaxByteSize` класса `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute`.</span><span class="sxs-lookup"><span data-stu-id="aaca8-238">You must also specify the `MaxByteSize` property of the `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute`.</span></span>  
  
### <a name="the-currency-udt"></a><span data-ttu-id="aaca8-239">Определяемый пользователем тип Currency</span><span class="sxs-lookup"><span data-stu-id="aaca8-239">The Currency UDT</span></span>  
 <span data-ttu-id="aaca8-240">Определяемый пользователем тип `Currency` входит в число образцов CLR, которые можно установить вместе с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (начиная с версии [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="aaca8-240">The `Currency` UDT is included with the CLR samples that can be installed with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="aaca8-241">Определяемый пользователем тип `Currency` поддерживает обработку денежных сумм в денежной системе конкретной культуры.</span><span class="sxs-lookup"><span data-stu-id="aaca8-241">The `Currency` UDT supports handling amounts of money in the monetary system of a particular culture.</span></span> <span data-ttu-id="aaca8-242">Должны быть определены два поля: значение типа `string` для поля `CultureInfo`, задающее источник определения валюты (например, en-us), и значение типа `decimal` для поля `CurrencyValue`, представляющего денежные суммы.</span><span class="sxs-lookup"><span data-stu-id="aaca8-242">You must define two fields: a `string` for `CultureInfo`, which specifies who issued the currency (en-us, for example) and a `decimal` for `CurrencyValue`, the amount of money.</span></span>  
  
 <span data-ttu-id="aaca8-243">Определяемый пользователем тип `Currency` реализует интерфейс `System.IComparable`, предоставляющий единственный метод `System.IComparable.CompareTo`, хотя сервер не использует этот метод для операций сравнения.</span><span class="sxs-lookup"><span data-stu-id="aaca8-243">Although it is not used by the server for performing comparisons, the `Currency` UDT implements the `System.IComparable` interface, which exposes a single method, `System.IComparable.CompareTo`.</span></span> <span data-ttu-id="aaca8-244">Он используется на клиенте в ситуациях, когда необходимо провести точное сравнение или сортировку значений денежных сумм внутри культур.</span><span class="sxs-lookup"><span data-stu-id="aaca8-244">This is used on the client side in situations where it is desirable to accurately compare or order currency values within cultures.</span></span>  
  
 <span data-ttu-id="aaca8-245">Код, работающий в среде CLR, сравнивает культуры отдельно от значений суммы.</span><span class="sxs-lookup"><span data-stu-id="aaca8-245">Code running in the CLR compares the culture separately from the currency value.</span></span> <span data-ttu-id="aaca8-246">Для кода на языке [!INCLUDE[tsql](../../includes/tsql-md.md)] сравнение определяется следующими действиями.</span><span class="sxs-lookup"><span data-stu-id="aaca8-246">For [!INCLUDE[tsql](../../includes/tsql-md.md)] code, the following actions determine the comparison:</span></span>  
  
1.  <span data-ttu-id="aaca8-247">Для атрибута `IsByteOrdered` задается значение true, а это служит для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] указанием, что для сравнения необходимо использовать сохраненные на диске двоичные представления.</span><span class="sxs-lookup"><span data-stu-id="aaca8-247">Set the `IsByteOrdered` attribute to true, which tells [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use the persisted binary representation on disk for comparisons.</span></span>  
  
2.  <span data-ttu-id="aaca8-248">С помощью метода `Write` определяемого пользователем типа `Currency` определяется, как сохраняется значение данного типа на диске и, следовательно, как проводятся сравнение и сортировка данного типа в операциях языка [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aaca8-248">Use the `Write` method for the `Currency` UDT to determine how the UDT is persisted on disk and therefore how UDT values are compared and ordered for [!INCLUDE[tsql](../../includes/tsql-md.md)] operations.</span></span>  
  
3.  <span data-ttu-id="aaca8-249">Значения определяемого пользователем типа `Currency` нужно сохранять в следующем двоичном формате.</span><span class="sxs-lookup"><span data-stu-id="aaca8-249">Save the `Currency` UDT using the following binary format:</span></span>  
  
    1.  <span data-ttu-id="aaca8-250">Культура сохраняется в виде строки в кодировке UTF-16 для байтов 0-19 с дополнением нулевыми символами справа.</span><span class="sxs-lookup"><span data-stu-id="aaca8-250">Save the culture as a UTF-16 encoded string for bytes 0-19 with padding to the right with null characters.</span></span>  
  
    2.  <span data-ttu-id="aaca8-251">Байты с 20 и выше используются для сохранения десятичного значения денежной суммы.</span><span class="sxs-lookup"><span data-stu-id="aaca8-251">Use bytes 20 and above to contain the decimal value of the currency.</span></span>  
  
 <span data-ttu-id="aaca8-252">Дополнение нужно для того, чтобы гарантировать полное отделение значения культуры от значения суммы. Тогда при сравнении одного значения определяемого пользователем типа с другим в коде [!INCLUDE[tsql](../../includes/tsql-md.md)] значение одной культуры можно будет побайтно сравнить со значением другой культуры, а значения байтов одной денежной суммы — со значениями байтов другой денежной суммы.</span><span class="sxs-lookup"><span data-stu-id="aaca8-252">The purpose of the padding is to ensure that the culture is completely separated from the currency value, so that when one UDT is compared against another in [!INCLUDE[tsql](../../includes/tsql-md.md)] code, culture bytes are compared against culture bytes, and currency byte values are compared against currency byte values.</span></span>  
  
 <span data-ttu-id="aaca8-253">Чтобы получить полный листинг кода для `Currency` определяемого пользователем типа, следуйте указаниям по установке примеров среды CLR в [SQL Server ядро СУБД Samples](https://msftengprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="aaca8-253">For the complete code listing for the `Currency` UDT, follow the directions for installing the CLR samples in [SQL Server Database Engine Samples](https://msftengprodsamples.codeplex.com/).</span></span>  
  
### <a name="currency-attributes"></a><span data-ttu-id="aaca8-254">Атрибуты Currency</span><span class="sxs-lookup"><span data-stu-id="aaca8-254">Currency Attributes</span></span>  
 <span data-ttu-id="aaca8-255">Определяемый пользователем тип `Currency` содержит следующие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="aaca8-255">The `Currency` UDT is defined with the following attributes.</span></span>  
  
```vb  
<Serializable(), Microsoft.SqlServer.Server.SqlUserDefinedType( _  
    Microsoft.SqlServer.Server.Format.UserDefined, _  
    IsByteOrdered:=True, MaxByteSize:=32), _  
    CLSCompliant(False)> _  
Public Structure Currency  
Implements INullable, IComparable, _  
Microsoft.SqlServer.Server.IBinarySerialize  
```  
  
```csharp  
[Serializable]  
[SqlUserDefinedType(Format.UserDefined,   
    IsByteOrdered = true, MaxByteSize = 32)]  
    [CLSCompliant(false)]  
    public struct Currency : INullable, IComparable, IBinarySerialize  
    {  
```  
  
## <a name="creating-read-and-write-methods-with-ibinaryserialize"></a><span data-ttu-id="aaca8-256">Создание методов чтения и записи с помощью интерфейса IBinarySerialize</span><span class="sxs-lookup"><span data-stu-id="aaca8-256">Creating Read and Write Methods with IBinarySerialize</span></span>  
 <span data-ttu-id="aaca8-257">При выборе формата сериализации `UserDefined` необходимо также реализовать интерфейс `IBinarySerialize` и создать собственные методы `Read` и `Write`.</span><span class="sxs-lookup"><span data-stu-id="aaca8-257">When you choose `UserDefined` serialization format, you also must implement the `IBinarySerialize` interface and create your own `Read` and `Write` methods.</span></span> <span data-ttu-id="aaca8-258">Следующие процедуры определяемого пользователем типа `Currency` используют классы `System.IO.BinaryReader` и `System.IO.BinaryWriter` для чтения данных из определяемого пользователем типа и записи в него.</span><span class="sxs-lookup"><span data-stu-id="aaca8-258">The following procedures from the `Currency` UDT use the `System.IO.BinaryReader` and `System.IO.BinaryWriter` to read from and write to the UDT.</span></span>  
  
```vb  
' IBinarySerialize methods  
' The binary layout is as follow:  
'    Bytes 0 - 19: Culture name, padded to the right with null  
'    characters, UTF-16 encoded  
'    Bytes 20+: Decimal value of money  
' If the culture name is empty, the currency is null.  
Public Sub Write(ByVal w As System.IO.BinaryWriter) _  
  Implements Microsoft.SqlServer.Server.IBinarySerialize.Write  
    If Me.IsNull Then  
        w.Write(nullMarker)  
        w.Write(System.Convert.ToDecimal(0))  
        Return  
    End If  
  
    If cultureName.Length > cultureNameMaxSize Then  
        Throw New ApplicationException(String.Format(CultureInfo.CurrentUICulture, _  
           "{0} is an invalid culture name for currency as it is too long.", cultureNameMaxSize))  
    End If  
  
    Dim paddedName As String = cultureName.PadRight(cultureNameMaxSize, CChar(vbNullChar))  
  
    For i As Integer = 0 To cultureNameMaxSize - 1  
        w.Write(paddedName(i))  
    Next i  
  
    ' Normalize decimal value to two places  
    currencyVal = Decimal.Floor(currencyVal * 100) / 100  
    w.Write(currencyVal)  
End Sub  
  
Public Sub Read(ByVal r As System.IO.BinaryReader) _  
  Implements Microsoft.SqlServer.Server.IBinarySerialize.Read  
    Dim name As Char() = r.ReadChars(cultureNameMaxSize)  
    Dim stringEnd As Integer = Array.IndexOf(name, CChar(vbNullChar))  
  
    If stringEnd = 0 Then  
        cultureName = Nothing  
        Return  
    End If  
  
    cultureName = New String(name, 0, stringEnd)  
    currencyVal = r.ReadDecimal()  
End Sub  
  
```  
  
```csharp  
// IBinarySerialize methods  
// The binary layout is as follow:  
//    Bytes 0 - 19:Culture name, padded to the right   
//    with null characters, UTF-16 encoded  
//    Bytes 20+:Decimal value of money  
// If the culture name is empty, the currency is null.  
public void Write(System.IO.BinaryWriter w)  
{  
    if (this.IsNull)  
    {  
        w.Write(nullMarker);  
        w.Write((decimal)0);  
        return;  
    }  
  
    if (cultureName.Length > cultureNameMaxSize)  
    {  
        throw new ApplicationException(string.Format(  
            CultureInfo.InvariantCulture,   
            "{0} is an invalid culture name for currency as it is too long.",   
            cultureNameMaxSize));  
    }  
  
    String paddedName = cultureName.PadRight(cultureNameMaxSize, '\0');  
    for (int i = 0; i < cultureNameMaxSize; i++)  
    {  
        w.Write(paddedName[i]);  
    }  
  
    // Normalize decimal value to two places  
    currencyValue = Decimal.Floor(currencyValue * 100) / 100;  
    w.Write(currencyValue);  
}  
public void Read(System.IO.BinaryReader r)  
{  
    char[] name = r.ReadChars(cultureNameMaxSize);  
    int stringEnd = Array.IndexOf(name, '\0');  
  
    if (stringEnd == 0)  
    {  
        cultureName = null;  
        return;  
    }  
  
    cultureName = new String(name, 0, stringEnd);  
    currencyValue = r.ReadDecimal();  
}  
```  
  
 <span data-ttu-id="aaca8-259">Полный листинг кода для `Currency` определяемого пользователем типа см. в разделе [SQL Server ядро СУБД Samples](https://msftengprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="aaca8-259">For the complete code listing for the `Currency` UDT, see [SQL Server Database Engine Samples](https://msftengprodsamples.codeplex.com/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaca8-260">См. также:</span><span class="sxs-lookup"><span data-stu-id="aaca8-260">See Also</span></span>  
 [<span data-ttu-id="aaca8-261">Создание определяемого пользователем типа</span><span class="sxs-lookup"><span data-stu-id="aaca8-261">Creating a User-Defined Type</span></span>](creating-user-defined-types.md)  
  
