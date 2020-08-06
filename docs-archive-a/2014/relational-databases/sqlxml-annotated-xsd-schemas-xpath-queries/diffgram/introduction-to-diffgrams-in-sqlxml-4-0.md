---
title: Введение в дельтами в SQLXML 4,0 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotations [SQLXML]
- DiffGrams [SQLXML], about DiffGrams
ms.assetid: 1902d67f-baf3-46e6-a36c-b24b5ba6f8ea
author: rothja
ms.author: jroth
ms.openlocfilehash: e57d87d064ace47247f342ed002b162b920e627f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664809"
---
# <a name="introduction-to-diffgrams-in-sqlxml-40"></a><span data-ttu-id="5002b-102">Введение в работу с дельтами в SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="5002b-102">Introduction to DiffGrams in SQLXML 4.0</span></span>
  <span data-ttu-id="5002b-103">В этом разделе приводится краткое введение в дельты (DiffGram).</span><span class="sxs-lookup"><span data-stu-id="5002b-103">This topic provides a brief introduction to DiffGrams.</span></span>  
  
## <a name="diffgram-format"></a><span data-ttu-id="5002b-104">Формат дельт</span><span class="sxs-lookup"><span data-stu-id="5002b-104">DiffGram Format</span></span>  
 <span data-ttu-id="5002b-105">Общий формат дельты имеет вид:</span><span class="sxs-lookup"><span data-stu-id="5002b-105">This is the general DiffGram format:</span></span>  
  
```  
<?xml version="1.0"?>  
<diffgr:diffgram   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"  
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1"  
         xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
   <DataInstance>  
      ...  
   </DataInstance>  
   [<diffgr:before>  
        ...  
   </diffgr:before>]  
  
   [<diffgr:errors>  
        ...  
   </diffgr:errors>]  
</diffgr:diffgram>  
```  
  
 <span data-ttu-id="5002b-106">Формат дельты состоит из следующих блоков.</span><span class="sxs-lookup"><span data-stu-id="5002b-106">The DiffGram format consists of these blocks:</span></span>  
  
 **\<DataInstance>**  
 <span data-ttu-id="5002b-107">Имя этого элемента, **instance**, используется для объяснения целей в этой документации.</span><span class="sxs-lookup"><span data-stu-id="5002b-107">The name of this element, **DataInstance**, is used for explanation purposes in this documentation.</span></span> <span data-ttu-id="5002b-108">Например, если объект DiffGram был создан из набора данных в .NET Framework, то в качестве имени этого элемента будет использоваться значение свойства **Name** набора данных.</span><span class="sxs-lookup"><span data-stu-id="5002b-108">For example, if the DiffGram were generated from a dataset in the .NET Framework, the value of the **Name** property of the dataset would be used as the name of this element.</span></span> <span data-ttu-id="5002b-109">Этот блок содержит все соответствующие данные после изменения, в том числе, возможно, данные, которые не были изменены.</span><span class="sxs-lookup"><span data-stu-id="5002b-109">This block contains all relevant data after the change, possibly including data that has not been modified.</span></span> <span data-ttu-id="5002b-110">Логика обработки DiffGram игнорирует элементы в этом блоке, для которых не указан атрибут **diffgr: hasChanges** .</span><span class="sxs-lookup"><span data-stu-id="5002b-110">The DiffGram processing logic ignores the elements in this block for which the **diffgr:hasChanges** attribute is not specified.</span></span>  
  
 **\<diffgr:before>**  
 <span data-ttu-id="5002b-111">Этот необязательный блок содержит исходные экземпляры (элементы) записи, которые необходимо обновить или удалить.</span><span class="sxs-lookup"><span data-stu-id="5002b-111">This optional block contains the original record instances (elements) that must be updated or deleted.</span></span> <span data-ttu-id="5002b-112">Все таблицы базы данных, изменяемые (обновленные или удаленные) с помощью DiffGram, должны отображаться в виде элементов верхнего уровня в **\<before>** блоке.</span><span class="sxs-lookup"><span data-stu-id="5002b-112">All the database tables being modified (updated or deleted) by the DiffGram must appear as top-level elements in the **\<before>** block.</span></span>  
  
 **\<diffgr:errors>**  
 <span data-ttu-id="5002b-113">Этот необязательный блок не учитывается средствами обработки дельт.</span><span class="sxs-lookup"><span data-stu-id="5002b-113">This optional block is ignored by the DiffGram processing logic.</span></span>  
  
## <a name="diffgram-annotations"></a><span data-ttu-id="5002b-114">Заметки дельт</span><span class="sxs-lookup"><span data-stu-id="5002b-114">DiffGram Annotations</span></span>  
 <span data-ttu-id="5002b-115">Эти заметки определены в пространстве имен DiffGram **"urn: schemas-microsoft-com: XML-DiffGram-01"**:</span><span class="sxs-lookup"><span data-stu-id="5002b-115">These annotations are defined in the DiffGram namespace **"urn:schemas-microsoft-com:xml-diffgram-01"**:</span></span>  
  
 <span data-ttu-id="5002b-116">**id**</span><span class="sxs-lookup"><span data-stu-id="5002b-116">**id**</span></span>  
 <span data-ttu-id="5002b-117">Этот атрибут используется для связывания элементов в **\<before>** **\<DataInstance>** блоках и.</span><span class="sxs-lookup"><span data-stu-id="5002b-117">This attribute is used to pair the elements in the **\<before>** and the **\<DataInstance>** blocks.</span></span>  
  
 <span data-ttu-id="5002b-118">**hasChanges**</span><span class="sxs-lookup"><span data-stu-id="5002b-118">**hasChanges**</span></span>  
 <span data-ttu-id="5002b-119">Для операции вставки или обновления в DiffGram должен быть указан атрибут со значением **inserted** или **Modified**.</span><span class="sxs-lookup"><span data-stu-id="5002b-119">For an insert or an update operation, the DiffGram must specify this attribute with the value **inserted** or **modified**.</span></span> <span data-ttu-id="5002b-120">Если этот атрибут отсутствует, соответствующий элемент в игнорируется **\<DataInstance>** логикой обработки и обновления не выполняются.</span><span class="sxs-lookup"><span data-stu-id="5002b-120">If this attribute is not present, the corresponding element in the **\<DataInstance>** is ignored by the processing logic and no updates are performed.</span></span> <span data-ttu-id="5002b-121">Рабочие образцы см. в разделе [примеры DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5002b-121">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="5002b-122">**parentID**</span><span class="sxs-lookup"><span data-stu-id="5002b-122">**parentID**</span></span>  
 <span data-ttu-id="5002b-123">Этот атрибут используется для определения связи «родители-потомки» между элементами в дельте.</span><span class="sxs-lookup"><span data-stu-id="5002b-123">This attribute is used to specify parent-child relationships among the elements in the DiffGram.</span></span> <span data-ttu-id="5002b-124">Этот атрибут отображается только в \<before> блоке.</span><span class="sxs-lookup"><span data-stu-id="5002b-124">This attribute appears only in the \<before> block.</span></span> <span data-ttu-id="5002b-125">Он используется в SQLXML при применении обновлений.</span><span class="sxs-lookup"><span data-stu-id="5002b-125">It is used by SQLXML when applying updates.</span></span> <span data-ttu-id="5002b-126">Связь типа «родители-потомки» используется для определения порядка, в котором обрабатываются элементы дельты.</span><span class="sxs-lookup"><span data-stu-id="5002b-126">The parent-child relationship is used in determining the order in which the elements in the DiffGram are processed.</span></span>  
  
## <a name="understanding-the-diffgram-processing-logic"></a><span data-ttu-id="5002b-127">Основные сведения о средствах обработки дельт</span><span class="sxs-lookup"><span data-stu-id="5002b-127">Understanding the DiffGram Processing Logic</span></span>  
 <span data-ttu-id="5002b-128">В средствах обработки дельт используются определенные правила для определения того, является ли операция вставкой, обновлением или удалением.</span><span class="sxs-lookup"><span data-stu-id="5002b-128">The DiffGram processing logic uses certain rules to determine whether an operation is an insert, update, or delete operation.</span></span> <span data-ttu-id="5002b-129">Описание этих правил приведено в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="5002b-129">These rules are described in the following table.</span></span>  
  
|<span data-ttu-id="5002b-130">Операция</span><span class="sxs-lookup"><span data-stu-id="5002b-130">Operation</span></span>|<span data-ttu-id="5002b-131">Описание</span><span class="sxs-lookup"><span data-stu-id="5002b-131">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5002b-132">Вставить</span><span class="sxs-lookup"><span data-stu-id="5002b-132">Insert</span></span>|<span data-ttu-id="5002b-133">Объект DiffGram указывает операцию вставки, если элемент присутствует в **\<DataInstance>** блоке, но не находится в соответствующем **\<before>** блоке, а атрибут **diffgr: hasChanges** указан (**diffgr: hasChanges = inserted**) для элемента.</span><span class="sxs-lookup"><span data-stu-id="5002b-133">A DiffGram indicates an insert operation when an element appears in the **\<DataInstance>** block but not in the corresponding **\<before>** block, and the **diffgr:hasChanges** attribute is specified (**diffgr:hasChanges=inserted**) on the element.</span></span> <span data-ttu-id="5002b-134">В этом случае DiffGram вставляет в базу данных экземпляр записи, указанный в **\<DataInstance>** блоке.</span><span class="sxs-lookup"><span data-stu-id="5002b-134">In this case, the DiffGram inserts the record instance that is specified in the **\<DataInstance>** block into the database.</span></span><br /><br /> <span data-ttu-id="5002b-135">Если атрибут **diffgr: hasChanges** не указан, элемент пропускается логикой обработки и вставка не выполняется.</span><span class="sxs-lookup"><span data-stu-id="5002b-135">If the **diffgr:hasChanges** attribute is not specified, the element is ignored by the processing logic and no insert is performed.</span></span> <span data-ttu-id="5002b-136">Рабочие образцы см. в разделе [примеры DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5002b-136">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span>|  
|<span data-ttu-id="5002b-137">Обновление</span><span class="sxs-lookup"><span data-stu-id="5002b-137">Update</span></span>|<span data-ttu-id="5002b-138">DiffGram указывает операцию обновления, если в блоке имеется элемент, \<before> для которого имеется соответствующий элемент в **\<DataInstance>** блоке (т. е. оба элемента имеют атрибут **diffgr: ID** с одинаковым значением), а атрибут **diffgr: hasChanges** указан со значением, **измененным** для элемента в **\<DataInstance>** блоке.</span><span class="sxs-lookup"><span data-stu-id="5002b-138">The DiffGram indicates an update operation when there is an element in the \<before> block for which there is a corresponding element in the **\<DataInstance>** block (that is, both elements have a **diffgr:id** attribute with same value) and the **diffgr:hasChanges** attribute is specified with the value **modified** on the element in the **\<DataInstance>** block.</span></span><br /><br /> <span data-ttu-id="5002b-139">Если атрибут **diffgr: hasChanges** не задан для элемента в **\<DataInstance>** блоке, логика обработки возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="5002b-139">If the **diffgr:hasChanges** attribute is not specified on the element in the **\<DataInstance>** block, an error is returned by the processing logic.</span></span> <span data-ttu-id="5002b-140">Рабочие образцы см. в разделе [примеры DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5002b-140">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span><br /><br /> <span data-ttu-id="5002b-141">Если в блоке указан **diffgr: ParentID** **\<before>** , то связь типа «родители-потомки» элементов, заданных **ParentID** , используется для определения порядка, в котором обновляются записи.</span><span class="sxs-lookup"><span data-stu-id="5002b-141">If **diffgr:parentID** is specified in the **\<before>** block, the parent-child relationship of elements that are specified by **parentID** are used in determining the order in which records are updated.</span></span>|  
|<span data-ttu-id="5002b-142">DELETE</span><span class="sxs-lookup"><span data-stu-id="5002b-142">Delete</span></span>|<span data-ttu-id="5002b-143">Объект DiffGram обозначает операцию удаления, когда элемент появляется в **\<before>** блоке, но не находится в соответствующем **\<DataInstance>** блоке.</span><span class="sxs-lookup"><span data-stu-id="5002b-143">A DiffGram indicates a delete operation when an element appears in the **\<before>** block but not in the corresponding **\<DataInstance>** block.</span></span> <span data-ttu-id="5002b-144">В этом случае DiffGram удаляет экземпляр записи, указанный в **\<before>** блоке, из базы данных.</span><span class="sxs-lookup"><span data-stu-id="5002b-144">In this case, the DiffGram deletes the record instance that is specified in the **\<before>** block from the database.</span></span> <span data-ttu-id="5002b-145">Рабочие образцы см. в разделе [примеры DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5002b-145">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span><br /><br /> <span data-ttu-id="5002b-146">Если в блоке указан **diffgr: ParentID** **\<before>** , то связь типа «родители-потомки» элементов, заданных **ParentID** , используется для определения порядка, в котором удаляются записи.</span><span class="sxs-lookup"><span data-stu-id="5002b-146">If **diffgr:parentID** is specified in the **\<before>** block, the parent-child relationship of elements that are specified by **parentID** are used in determining the order in which records are deleted.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="5002b-147">Передача параметров в дельты не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="5002b-147">Parameters cannot be passed to DiffGrams.</span></span>  
  
  
