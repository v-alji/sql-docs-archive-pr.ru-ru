---
title: Элемент Server (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Server element
ms.assetid: 9fe0bfb4-3aa6-4eb2-a83e-c0d0e7d4e9f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: ab67e0303c2b629c3774886441474f5ef5b10a43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666312"
---
# <a name="server-element-dta"></a>Элемент Server (DTA)
  Содержит сведения идентификации сервера, на котором находятся настраиваемые базы данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
<DTAInput>  
    <Server>  
    ...code removed here...  
    </Server>  
```  
  
## <a name="element-characteristics"></a>Характеристики элемента  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|**Тип данных и длина**|Нет.|  
|**Значение по умолчанию**|Нет.|  
|**Наличие**|Требуется один раз на каждый элемент `DTAInput`.|  
  
## <a name="element-relationships"></a>Связи элемента  
  
|Связь|Элементы|  
|------------------|--------------|  
|**Родительский элемент**|[Элемент DTAInput (DTA)](dtainput-element-dta.md)|  
|**Дочерние элементы**|[Элемент Name описания сервера (DTA)](name-element-for-server-dta.md)<br /><br /> [Элемент Database описания сервера (DTA)](database-element-for-server-dta.md)|  
  
## <a name="remarks"></a>Remarks  
 Для элемента можно указать только один `Server` элемент `DTAInput` . Этот элемент с именем **ServerDetailsTypecomplexType** определен в схеме XML DTA. Не следует путать данный элемент `Server` с дочерним элементом элемента `Configuration`. Дополнительные сведения см. в разделе [Элемент Server описания конфигурации (DTA)](server-element-for-configuration-dta.md).  
  
## <a name="example"></a>Пример  
 Следующий пример иллюстрирует, как указать таблицу **Sales.SalesPerson** в базе данных **AdventureWorks** на сервере SERVER001:  
  
```xml  
<Server>  
  <Name>SERVER001</Name>  
  <Database>  
    <Name>AdventureWorks</Name>  
    <Schema>  
      <Name>Sales</Name>  
      <Table>  
        <Name>SalesPerson</Name>  
      </Table>  
    </Schema>  
  </Database>  
</Server  
```  
  
## <a name="see-also"></a>См. также:  
 [Справочник по входным XML-файлам (помощник по настройке ядра СУБД)](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
