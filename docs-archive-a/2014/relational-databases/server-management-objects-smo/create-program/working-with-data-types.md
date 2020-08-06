---
title: Работа с типами данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- DataType object
- SQL Server Management Objects, data types
- data types [SMO]
- SMO [SQL Server], data types
ms.assetid: 1e0e736a-c709-4d89-aeb2-b32dcfd641fa
author: stevestein
ms.author: sstein
ms.openlocfilehash: cbffc1c59eb12fa0f448a7fcb26157d5e18dba3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656270"
---
# <a name="working-with-data-types"></a><span data-ttu-id="37af8-102">Работа с типами данных</span><span class="sxs-lookup"><span data-stu-id="37af8-102">Working with Data Types</span></span>
  <span data-ttu-id="37af8-103">Данные поступают в виде различных типов и размеров, таких как строка определенной длины, число с конкретной точностью или определяемый пользователем тип, представляющий собой другой объект, со своим набором правил.</span><span class="sxs-lookup"><span data-stu-id="37af8-103">Data comes in many types and sizes, such as a string that has a defined length, a number that has specific accuracy, or a user-defined data type that is another object that has its own set of rules.</span></span> <span data-ttu-id="37af8-104"><xref:Microsoft.SqlServer.Management.Smo.DataType>Объект классифицирует тип данных, чтобы их можно было правильно обработать с помощью [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="37af8-104">The <xref:Microsoft.SqlServer.Management.Smo.DataType> object classifies the type of data so that it can be handled correctly by [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="37af8-105">Объект <xref:Microsoft.SqlServer.Management.Smo.DataType> связан с объектами, принимающими данные.</span><span class="sxs-lookup"><span data-stu-id="37af8-105">The <xref:Microsoft.SqlServer.Management.Smo.DataType> object is associated with objects that accept data.</span></span> <span data-ttu-id="37af8-106">Следующие управляющие объекты [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (SMO) принимают данные, которые должны быть определены свойством объекта <xref:Microsoft.SqlServer.Management.Smo.DataType>.</span><span class="sxs-lookup"><span data-stu-id="37af8-106">The following [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) objects accept data that must be defined by a <xref:Microsoft.SqlServer.Management.Smo.DataType> object property:</span></span>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Column>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunctionParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.StoredProcedureParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunctionParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedAggregateParameter>  
  
 <span data-ttu-id="37af8-107">Свойство `DataType` для объектов, принимающих данные, можно задать несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="37af8-107">The `DataType` property for objects that accept data can be set in several ways.</span></span>  
  
-   <span data-ttu-id="37af8-108">Применение конструктора по умолчанию и явное определение свойств объекта <xref:Microsoft.SqlServer.Management.Smo.DataType>.</span><span class="sxs-lookup"><span data-stu-id="37af8-108">Use the default constructor and specify <xref:Microsoft.SqlServer.Management.Smo.DataType> object properties explicitly</span></span>  
  
-   <span data-ttu-id="37af8-109">Применение перегруженного конструктора и определение свойств объекта <xref:Microsoft.SqlServer.Management.Smo.DataType> как параметров.</span><span class="sxs-lookup"><span data-stu-id="37af8-109">Use an overloaded constructor and specify the <xref:Microsoft.SqlServer.Management.Smo.DataType> properties as parameters.</span></span>  
  
-   <span data-ttu-id="37af8-110">Определение встроенного параметра <xref:Microsoft.SqlServer.Management.Smo.DataType> в конструкторе объекта.</span><span class="sxs-lookup"><span data-stu-id="37af8-110">Specify the <xref:Microsoft.SqlServer.Management.Smo.DataType> inline in the object constructor.</span></span>  
  
-   <span data-ttu-id="37af8-111">Использование одного из статических членов класса <xref:Microsoft.SqlServer.Management.Smo.DataType>, например `Int`.</span><span class="sxs-lookup"><span data-stu-id="37af8-111">Use one of the static members of the <xref:Microsoft.SqlServer.Management.Smo.DataType> class, for example `Int`.</span></span> <span data-ttu-id="37af8-112">В результате будет возвращен экземпляр объекта <xref:Microsoft.SqlServer.Management.Smo.DataType>.</span><span class="sxs-lookup"><span data-stu-id="37af8-112">This will in fact return an instance of a <xref:Microsoft.SqlServer.Management.Smo.DataType> object.</span></span>  
  
 <span data-ttu-id="37af8-113">Объект <xref:Microsoft.SqlServer.Management.Smo.DataType> имеет несколько свойств, описывающих тип данных.</span><span class="sxs-lookup"><span data-stu-id="37af8-113">The <xref:Microsoft.SqlServer.Management.Smo.DataType> object has several properties that define the type of data.</span></span> <span data-ttu-id="37af8-114">Например, свойство <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> задает тип данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37af8-114">For example, the <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> property specifies the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type.</span></span> <span data-ttu-id="37af8-115">Постоянные величины, представляющие типы данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], приведены в перечислении <xref:Microsoft.SqlServer.Management.Smo.SqlDataType>.</span><span class="sxs-lookup"><span data-stu-id="37af8-115">The constant values that represent [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types are listed in the <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> enumeration.</span></span> <span data-ttu-id="37af8-116">Это относится к таким типам данных, как `varchar`, `nchar`, `currency`, `integer`, `float` и `datetime`.</span><span class="sxs-lookup"><span data-stu-id="37af8-116">This refers to data types such as `varchar`, `nchar`, `currency`, `integer`, `float`, and `datetime`.</span></span>  
  
 <span data-ttu-id="37af8-117">После установления типа данных необходимо задать для данных конкретные свойства.</span><span class="sxs-lookup"><span data-stu-id="37af8-117">When the data type is established, specific properties must be set for the data.</span></span> <span data-ttu-id="37af8-118">Например, если это тип `nchar`, необходимо задать в свойстве `Length` длину строковых данных.</span><span class="sxs-lookup"><span data-stu-id="37af8-118">For example, if it is an `nchar` type, the length of the string data must be set in the `Length` property.</span></span> <span data-ttu-id="37af8-119">Тоже относится к числовым значениям, для которых необходимо задать точность и масштаб.</span><span class="sxs-lookup"><span data-stu-id="37af8-119">The same applies for numeric values, where you would have to specify precision and scale.</span></span>  
  
 <span data-ttu-id="37af8-120">Типы данных <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> и <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> относятся к объектам, содержащим определение типа данных, созданного пользователем.</span><span class="sxs-lookup"><span data-stu-id="37af8-120"><xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> and <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> data types refer to objects that contain the definition of the type of data defined by the user.</span></span> <span data-ttu-id="37af8-121">Определяемый пользователем тип данных <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> основан на типах данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] из перечисления <xref:Microsoft.SqlServer.Management.Smo.SqlDataType>.</span><span class="sxs-lookup"><span data-stu-id="37af8-121">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> is based on [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types from the <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> enumeration.</span></span> <span data-ttu-id="37af8-122">Объект <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> основан на [!INCLUDE[msCoName](../../../includes/msconame-md.md)] типах данных .NET.</span><span class="sxs-lookup"><span data-stu-id="37af8-122">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> is based on [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET data types.</span></span> <span data-ttu-id="37af8-123">Обычно эти данные представляют собой данные конкретного типа, часто используемые повторно в базе данных, поскольку этого требуют бизнес-правила, определяемые организацией.</span><span class="sxs-lookup"><span data-stu-id="37af8-123">Typically, these would represent data of a specific type that is frequently reused by the database because of business rules defined by the organization.</span></span> <span data-ttu-id="37af8-124">Например, компания, которая проводит сделки с использованием нескольких валют, может использовать тип данных, предусматривающий хранение денежной суммы и кода валюты.</span><span class="sxs-lookup"><span data-stu-id="37af8-124">For example, a data type that stores an amount of money and a currency denominator would be helpful in a company that deals in multiple currencies.</span></span>  
  
 <span data-ttu-id="37af8-125">Перечисление <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> содержит список всех типов данных, поддерживаемых в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37af8-125">The <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> enumeration contains a list of all the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-supported data types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="37af8-126">Примеры</span><span class="sxs-lookup"><span data-stu-id="37af8-126">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="constructing-a-datatype-object-with-the-specification-in-the-constructor-in-visual-basic"></a><span data-ttu-id="37af8-127">Создание объекта DataType со спецификацией в конструкторе объекта на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="37af8-127">Constructing a DataType Object with the Specification in the Constructor in Visual Basic</span></span>  
 <span data-ttu-id="37af8-128">Этот пример кода показывает использование конструктора для создания экземпляров типов данных на основе различных типов данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="37af8-128">This code example shows how to use the constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37af8-129">Типы <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> и типы XML требуют использования имени для идентификации объекта.</span><span class="sxs-lookup"><span data-stu-id="37af8-129">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDataTypes1](SMO How to#SMO_VBDataTypes1)]  -->  
  
## <a name="constructing-a-datatype-object-with-the-specification-in-the-constructor-in-visual-c"></a><span data-ttu-id="37af8-130">Создание объекта DataType со спецификацией в конструкторе объекта на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="37af8-130">Constructing a DataType Object with the Specification in the Constructor in Visual C#</span></span>  
 <span data-ttu-id="37af8-131">Этот пример кода показывает использование конструктора для создания экземпляров типов данных на основе различных типов данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="37af8-131">This code example shows how to use the constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37af8-132">Типы <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> и типы XML требуют использования имени для идентификации объекта.</span><span class="sxs-lookup"><span data-stu-id="37af8-132">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
```  
{   
//Declare a DataType object variable and define the data type in the constructor.   
DataType dt;   
//For the decimal data type the following two arguments specify precision, and scale.   
dt = new DataType(SqlDataType.Decimal, 10, 2);   
}  
```  
  
## <a name="constructing-a-datatype-object-by-using-the-default-constructor-in-visual-basic"></a><span data-ttu-id="37af8-133">Создание объекта DataType с применением конструктора по умолчанию на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="37af8-133">Constructing a DataType Object by Using the Default Constructor in Visual Basic</span></span>  
 <span data-ttu-id="37af8-134">Этот пример кода показывает использование конструктора для создания экземпляров типов данных на основе различных типов данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="37af8-134">This code example shows how to use the default constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="37af8-135">После этого с помощью свойств задается тип данных.</span><span class="sxs-lookup"><span data-stu-id="37af8-135">The properties are then used to specify the data type.</span></span>  
  
 <span data-ttu-id="37af8-136">**Примечание** . <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> Для всех типов XML, и требуется значение имени для указания объекта.</span><span class="sxs-lookup"><span data-stu-id="37af8-136">**Note** The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDataTypes2](SMO How to#SMO_VBDataTypes2)]  -->  
  
## <a name="constructing-a-datatype-object-by-using-the-default-constructor-in-visual-c"></a><span data-ttu-id="37af8-137">Создание объекта DataType с применением конструктора по умолчанию на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="37af8-137">Constructing a DataType Object by Using the Default Constructor in Visual C#</span></span>  
 <span data-ttu-id="37af8-138">Этот пример кода показывает использование конструктора для создания экземпляров типов данных на основе различных типов данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="37af8-138">This code example shows how to use the default constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="37af8-139">После этого с помощью свойств задается тип данных.</span><span class="sxs-lookup"><span data-stu-id="37af8-139">The properties are then used to specify the data type.</span></span>  
  
 <span data-ttu-id="37af8-140">**Примечание** . <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> Для всех типов XML, и требуется значение имени для указания объекта.</span><span class="sxs-lookup"><span data-stu-id="37af8-140">**Note** The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
```  
{   
//Declare and create a DataType object variable.   
DataType dt;   
dt = new DataType();   
//Define the data type by setting the SqlDataType property.   
dt.SqlDataType = SqlDataType.VarChar;   
//The VarChar data type requires a value for the MaximumLength property.   
dt.MaximumLength = 100;   
}  
```  
  
  
