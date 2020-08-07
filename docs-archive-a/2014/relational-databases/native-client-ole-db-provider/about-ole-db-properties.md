---
title: Сведения о свойствах OLE DB | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, properties
- SQL Server Native Client OLE DB provider, properties
- properties [OLE DB]
- property values [SQL Server Native Client]
ms.assetid: 0b36a61e-b542-400d-a3d2-e6f643caf2c6
author: rothja
ms.author: jroth
ms.openlocfilehash: d4eb80ab9c0ab90da11d8580e9a2983455b676bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730629"
---
# <a name="about-ole-db-properties"></a><span data-ttu-id="3df70-102">О свойствах OLE DB</span><span class="sxs-lookup"><span data-stu-id="3df70-102">About OLE DB Properties</span></span>
  <span data-ttu-id="3df70-103">Потребитель может устанавливать значения свойств, чтобы запросить определенное поведение объекта.</span><span class="sxs-lookup"><span data-stu-id="3df70-103">Consumers set property values to request specific object behavior.</span></span> <span data-ttu-id="3df70-104">Например, потребитель использует свойства для указания интерфейса, который должен предоставить набор строк.</span><span class="sxs-lookup"><span data-stu-id="3df70-104">For example, consumers use properties to specify the interfaces to be exposed by a rowset.</span></span> <span data-ttu-id="3df70-105">Потребители получают значения свойств для определения возможностей объекта, например набора строк, сеанса или объекта источника данных.</span><span class="sxs-lookup"><span data-stu-id="3df70-105">Consumers get the property values to determine the capabilities of an object, such as a rowset, a session, or a data source object.</span></span>  
  
 <span data-ttu-id="3df70-106">Каждое свойство имеет значение, тип, описание и атрибут чтения/записи, а для свойств набора строк — признак того, применим ли набор строк к отдельным столбцам.</span><span class="sxs-lookup"><span data-stu-id="3df70-106">Each property has a value, type, description, and read/write attribute, and for rowset properties, an indicator of whether it can be applied on a column-by-column basis.</span></span>  
  
 <span data-ttu-id="3df70-107">Свойство определяется по идентификатору GUID и целому числу, представляющему идентификатор свойства.</span><span class="sxs-lookup"><span data-stu-id="3df70-107">A property is identified by a GUID and an integer representing the property ID.</span></span> <span data-ttu-id="3df70-108">Набор свойств — это набор всех свойств с одинаковым идентификатором GUID.</span><span class="sxs-lookup"><span data-stu-id="3df70-108">A property set is a set of all properties that share the same GUID.</span></span> <span data-ttu-id="3df70-109">В дополнение к стандартным наборам свойств OLE DB, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента реализует в них наборы свойств и свойства, относящиеся к поставщику.</span><span class="sxs-lookup"><span data-stu-id="3df70-109">In addition to the predefined OLE DB property sets, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements provider-specific property sets and properties in them.</span></span> <span data-ttu-id="3df70-110">Каждое свойство принадлежит одной или нескольким группам свойств.</span><span class="sxs-lookup"><span data-stu-id="3df70-110">Each property belongs to one or more property groups.</span></span> <span data-ttu-id="3df70-111">Группа свойств — это группа всех свойств, применимых к определенному объекту.</span><span class="sxs-lookup"><span data-stu-id="3df70-111">A property group is the group of all properties that apply to a particular object.</span></span> <span data-ttu-id="3df70-112">Группой свойств может быть группа свойств инициализации, группа свойств источника данных, группа свойств сеанса, группа свойств набора строк, группа свойств таблицы и группа свойств столбца.</span><span class="sxs-lookup"><span data-stu-id="3df70-112">Some property groups include the initialization property group, data source property group, session property group, rowset property group, table property group, and column property group.</span></span> <span data-ttu-id="3df70-113">Ниже представлены свойства каждой из этих групп свойств.</span><span class="sxs-lookup"><span data-stu-id="3df70-113">There are properties in each of these property groups.</span></span>  
  
 <span data-ttu-id="3df70-114">Установка значения свойства предполагает следующее.</span><span class="sxs-lookup"><span data-stu-id="3df70-114">Setting property values involves:</span></span>  
  
1.  <span data-ttu-id="3df70-115">Определения свойств, которым присваиваются значения.</span><span class="sxs-lookup"><span data-stu-id="3df70-115">Determining the properties for which to set values.</span></span>  
  
2.  <span data-ttu-id="3df70-116">Определение набора свойств, содержащего идентифицированные свойства.</span><span class="sxs-lookup"><span data-stu-id="3df70-116">Determining the property sets that contain the identified properties.</span></span>  
  
3.  <span data-ttu-id="3df70-117">Выделение ресурсов для массива структур DBPROPSET — по одной на каждый идентифицированный набор свойств.</span><span class="sxs-lookup"><span data-stu-id="3df70-117">Allocating an array of DBPROPSET structures, one for each identified property set.</span></span>  
  
4.  <span data-ttu-id="3df70-118">Выделение ресурсов для массива структур DBPROP для каждого набора свойств.</span><span class="sxs-lookup"><span data-stu-id="3df70-118">Allocating an array of DBPROP structures for each property set.</span></span> <span data-ttu-id="3df70-119">Количество элементов в каждом массиве определяется числом свойств (идентифицированных на шаге 1), принадлежащих конкретному набору свойств.</span><span class="sxs-lookup"><span data-stu-id="3df70-119">The number of elements in each array is the number of properties (identified in Step 1) that belong to that property set.</span></span>  
  
5.  <span data-ttu-id="3df70-120">Заполнение структуры DBPROP для каждого свойства.</span><span class="sxs-lookup"><span data-stu-id="3df70-120">Filling in the DBPROP structure for each property.</span></span>  
  
6.  <span data-ttu-id="3df70-121">Заполнение сведений (идентификатор GUID, счетчик числа элементов и указатель на соответствующий массив DBPROP) в структуре DBPROPSET для каждого набора свойств.</span><span class="sxs-lookup"><span data-stu-id="3df70-121">Filling in information (property set GUID, count of number of elements, and a pointer to the corresponding DBPROP array) in the DBPROPSET structure for each property set.</span></span>  
  
7.  <span data-ttu-id="3df70-122">Вызов метода для установки свойств и передачи счетчика и массива структур DBPROPSET.</span><span class="sxs-lookup"><span data-stu-id="3df70-122">Calling a method to set properties and passing the count and the array of DBPROPSET structures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3df70-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="3df70-123">See Also</span></span>  
 <span data-ttu-id="3df70-124">[Создание приложения поставщика SQL Server Native Client OLE DB](creating-a-sql-server-native-client-ole-db-provider-application.md) </span><span class="sxs-lookup"><span data-stu-id="3df70-124">[Creating a SQL Server Native Client OLE DB Provider Application](creating-a-sql-server-native-client-ole-db-provider-application.md) </span></span>  
 [<span data-ttu-id="3df70-125">Свойства (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="3df70-125">Properties (OLE DB)</span></span>](https://go.microsoft.com/fwlink/?LinkId=112207)  
  
  
