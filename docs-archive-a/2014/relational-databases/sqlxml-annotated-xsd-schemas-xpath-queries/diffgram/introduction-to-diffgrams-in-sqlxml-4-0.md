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
# <a name="introduction-to-diffgrams-in-sqlxml-40"></a>Введение в работу с дельтами в SQLXML 4.0
  В этом разделе приводится краткое введение в дельты (DiffGram).  
  
## <a name="diffgram-format"></a>Формат дельт  
 Общий формат дельты имеет вид:  
  
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
  
 Формат дельты состоит из следующих блоков.  
  
 **\<DataInstance>**  
 Имя этого элемента, **instance**, используется для объяснения целей в этой документации. Например, если объект DiffGram был создан из набора данных в .NET Framework, то в качестве имени этого элемента будет использоваться значение свойства **Name** набора данных. Этот блок содержит все соответствующие данные после изменения, в том числе, возможно, данные, которые не были изменены. Логика обработки DiffGram игнорирует элементы в этом блоке, для которых не указан атрибут **diffgr: hasChanges** .  
  
 **\<diffgr:before>**  
 Этот необязательный блок содержит исходные экземпляры (элементы) записи, которые необходимо обновить или удалить. Все таблицы базы данных, изменяемые (обновленные или удаленные) с помощью DiffGram, должны отображаться в виде элементов верхнего уровня в **\<before>** блоке.  
  
 **\<diffgr:errors>**  
 Этот необязательный блок не учитывается средствами обработки дельт.  
  
## <a name="diffgram-annotations"></a>Заметки дельт  
 Эти заметки определены в пространстве имен DiffGram **"urn: schemas-microsoft-com: XML-DiffGram-01"**:  
  
 **id**  
 Этот атрибут используется для связывания элементов в **\<before>** **\<DataInstance>** блоках и.  
  
 **hasChanges**  
 Для операции вставки или обновления в DiffGram должен быть указан атрибут со значением **inserted** или **Modified**. Если этот атрибут отсутствует, соответствующий элемент в игнорируется **\<DataInstance>** логикой обработки и обновления не выполняются. Рабочие образцы см. в разделе [примеры DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).  
  
 **parentID**  
 Этот атрибут используется для определения связи «родители-потомки» между элементами в дельте. Этот атрибут отображается только в \<before> блоке. Он используется в SQLXML при применении обновлений. Связь типа «родители-потомки» используется для определения порядка, в котором обрабатываются элементы дельты.  
  
## <a name="understanding-the-diffgram-processing-logic"></a>Основные сведения о средствах обработки дельт  
 В средствах обработки дельт используются определенные правила для определения того, является ли операция вставкой, обновлением или удалением. Описание этих правил приведено в следующей таблице.  
  
|Операция|Описание|  
|---------------|-----------------|  
|Вставить|Объект DiffGram указывает операцию вставки, если элемент присутствует в **\<DataInstance>** блоке, но не находится в соответствующем **\<before>** блоке, а атрибут **diffgr: hasChanges** указан (**diffgr: hasChanges = inserted**) для элемента. В этом случае DiffGram вставляет в базу данных экземпляр записи, указанный в **\<DataInstance>** блоке.<br /><br /> Если атрибут **diffgr: hasChanges** не указан, элемент пропускается логикой обработки и вставка не выполняется. Рабочие образцы см. в разделе [примеры DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).|  
|Обновление|DiffGram указывает операцию обновления, если в блоке имеется элемент, \<before> для которого имеется соответствующий элемент в **\<DataInstance>** блоке (т. е. оба элемента имеют атрибут **diffgr: ID** с одинаковым значением), а атрибут **diffgr: hasChanges** указан со значением, **измененным** для элемента в **\<DataInstance>** блоке.<br /><br /> Если атрибут **diffgr: hasChanges** не задан для элемента в **\<DataInstance>** блоке, логика обработки возвращает ошибку. Рабочие образцы см. в разделе [примеры DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).<br /><br /> Если в блоке указан **diffgr: ParentID** **\<before>** , то связь типа «родители-потомки» элементов, заданных **ParentID** , используется для определения порядка, в котором обновляются записи.|  
|DELETE|Объект DiffGram обозначает операцию удаления, когда элемент появляется в **\<before>** блоке, но не находится в соответствующем **\<DataInstance>** блоке. В этом случае DiffGram удаляет экземпляр записи, указанный в **\<before>** блоке, из базы данных. Рабочие образцы см. в разделе [примеры DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).<br /><br /> Если в блоке указан **diffgr: ParentID** **\<before>** , то связь типа «родители-потомки» элементов, заданных **ParentID** , используется для определения порядка, в котором удаляются записи.|  
  
> [!NOTE]  
>  Передача параметров в дельты не предусмотрена.  
  
  