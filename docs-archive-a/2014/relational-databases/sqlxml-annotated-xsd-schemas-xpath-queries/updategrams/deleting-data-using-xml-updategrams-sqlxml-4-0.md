---
title: Удаление данных с помощью XML диаграмм обновления (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- <after> block
- updategrams [SQLXML], deleting data
- <before> block
- mapping-schema attribute
- record deletions [SQLXML]
ms.assetid: 4fb116d7-7652-474a-a567-cb475a20765c
author: rothja
ms.author: jroth
ms.openlocfilehash: d941005c71dc33dd8c4f5c5cc15f645cd0e68177
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666989"
---
# <a name="deleting-data-using-xml-updategrams-sqlxml-40"></a><span data-ttu-id="3d454-102">Удаление данных с помощью диаграмм обновления XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="3d454-102">Deleting Data Using XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="3d454-103">Диаграмма обновления указывает операцию удаления, когда экземпляр записи появляется в **\<before>** блоке без соответствующих записей в **\<after>** блоке.</span><span class="sxs-lookup"><span data-stu-id="3d454-103">An updategram indicates a delete operation when a record instance appears in the **\<before>** block with no corresponding records in the **\<after>** block.</span></span> <span data-ttu-id="3d454-104">В этом случае диаграмма обновления удаляет запись **\<before>** из базы данных в блоке.</span><span class="sxs-lookup"><span data-stu-id="3d454-104">In this case, the updategram deletes the record in the **\<before>** block from the database.</span></span>  
  
 <span data-ttu-id="3d454-105">Формат диаграммы обновления для операции удаления:</span><span class="sxs-lookup"><span data-stu-id="3d454-105">This is the updategram format for a delete operation:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync [mapping-schema="SampleSchema.xml"]  >  
   <updg:before>  
       <ElementName />  
      [<ElementName .../>... ]  
   </updg:before>  
    [<updg:after>  
    </updg:after>]  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="3d454-106">Тег можно опустить, **\<after>** Если диаграмма обновления выполняет только операцию удаления.</span><span class="sxs-lookup"><span data-stu-id="3d454-106">You can omit the **\<after>** tag if the updategram is performing only a delete operation.</span></span> <span data-ttu-id="3d454-107">Если необязательный атрибут не указан `mapping-schema` , то **\<ElementName>** указанный в диаграмма обновления сопоставляется с таблицей базы данных, а дочерние элементы или атрибуты сопоставляются со столбцами в таблице.</span><span class="sxs-lookup"><span data-stu-id="3d454-107">If you do not specify the optional `mapping-schema` attribute, the **\<ElementName>** specified in the updategram maps to a database table and the child elements or attributes map to columns in the table.</span></span>  
  
 <span data-ttu-id="3d454-108">Если элемент, указанный в диаграмма обновления, либо соответствует нескольким строкам в таблице, либо не соответствует ни одной строке, диаграмма обновления возвращает ошибку и отменяет весь **\<sync>** блок.</span><span class="sxs-lookup"><span data-stu-id="3d454-108">If an element specified in the updategram either matches more than one row in the table or does not match any row, the updategram returns an error and cancels the entire **\<sync>** block.</span></span> <span data-ttu-id="3d454-109">В каждый момент времени лишь одна запись может быть удалена элементом в диаграмме обновления.</span><span class="sxs-lookup"><span data-stu-id="3d454-109">Only one record at a time can be deleted by an element in the updategram.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3d454-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="3d454-110">Examples</span></span>  
 <span data-ttu-id="3d454-111">В примерах этого раздела используется сопоставление по умолчанию (то есть в диаграмме обновления схема сопоставления не указана).</span><span class="sxs-lookup"><span data-stu-id="3d454-111">Examples in this section use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="3d454-112">Дополнительные примеры диаграмм обновления, в которых используются схемы сопоставления, см. [в разделе Указание схемы сопоставления с заметками в диаграмма обновления &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="3d454-112">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="3d454-113">Чтобы создать рабочие образцы с помощью следующих примеров, необходимо выполнить требования, указанные в [требованиях к запуску примеров SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="3d454-113">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-deleting-a-record-by-using-an-updategram"></a><span data-ttu-id="3d454-114">A.</span><span class="sxs-lookup"><span data-stu-id="3d454-114">A.</span></span> <span data-ttu-id="3d454-115">Удаление записи с помощью диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="3d454-115">Deleting a record by using an updategram</span></span>  
 <span data-ttu-id="3d454-116">Следующие диаграммы обновления удаляют две записи из таблицы HumanResources.Shift.</span><span class="sxs-lookup"><span data-stu-id="3d454-116">The following updategrams deletes two records from the HumanResources.Shift table.</span></span>  
  
 <span data-ttu-id="3d454-117">В этих примерах диаграмма обновления не указывает схему сопоставления.</span><span class="sxs-lookup"><span data-stu-id="3d454-117">In these examples, the updategram does not specify a mapping schema.</span></span> <span data-ttu-id="3d454-118">Поэтому диаграмма обновления использует сопоставление по умолчанию, в котором имя элемента соответствует имени таблицы, а атрибуты и вложенные элементы соответствуют столбцам.</span><span class="sxs-lookup"><span data-stu-id="3d454-118">Therefore, the updategram uses default mapping, in which the element name maps to table name and the attributes or subelements map to columns.</span></span>  
  
 <span data-ttu-id="3d454-119">Первый диаграмма обновления является атрибутивной и определяет две смены (Day-вечером и вечером-ночь) в **\<before>** блоке.</span><span class="sxs-lookup"><span data-stu-id="3d454-119">This first updategram is attribute-centric and identifies two shifts (Day-Evening and Evening-Night) in the **\<before>** block.</span></span> <span data-ttu-id="3d454-120">Так как в блоке нет соответствующей записи **\<after>** , это операция удаления.</span><span class="sxs-lookup"><span data-stu-id="3d454-120">Because there is no corresponding record in the **\<after>** block, this is a delete operation.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
       <HumanResources.Shift ShiftID="4"  
                        Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
       <HumanResources.Shift ShiftID="5"  
                        Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
  </updg:before>  
  <updg:after>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="3d454-121">Тестирование диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="3d454-121">To test the updategram</span></span>  
  
1.  <span data-ttu-id="3d454-122">Полный пример б ("Вставка нескольких записей с помощью диаграмма обновления") при [вставке данных с помощью XML диаграмм обновления &#40;SQLXML 4,0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="3d454-122">Complete example B ("Inserting multiple records by using an updategram") in [Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
2.  <span data-ttu-id="3d454-123">Скопируйте диаграмма обновления выше в блокнот и сохраните его как Updategram-RemoveShifts.xml в той же папке, которая использовалась для завершения ("Вставка нескольких записей с помощью диаграмма обновления") при [вставке данных с помощью XML диаграмм обновления &#40;SQLXML 4,0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="3d454-123">Copy the updategram above to Notepad and save it as Updategram-RemoveShifts.xml in the same folder as was used to complete ("Inserting multiple records by using an updategram") in [Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
3.  <span data-ttu-id="3d454-124">Создайте тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs) и воспользуйтесь им для выполнения диаграммы обновления.</span><span class="sxs-lookup"><span data-stu-id="3d454-124">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="3d454-125">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="3d454-125">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d454-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="3d454-126">See Also</span></span>  
 [<span data-ttu-id="3d454-127">Вопросы безопасности диаграмма обновления &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="3d454-127">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
