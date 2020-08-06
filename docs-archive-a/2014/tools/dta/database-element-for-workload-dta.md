---
title: Элемент Database для рабочей нагрузки (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database element
ms.assetid: 112fca2a-37e5-4162-b2e7-b56eb8ab0c6f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2774bc7ed981c84c966a394c95347208cbc6d656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727657"
---
# <a name="database-element-for-workload-dta"></a>Элемент Database описания рабочей нагрузки (DTA)
  Указывает базу данных, в которой находится таблица трассировки рабочей нагрузки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
<Workload>  
  <Database>  
   ...code removed here...  
  </Database>  
```  
  
## <a name="element-characteristics"></a>Характеристики элемента  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|**Тип данных и длина**|Нет.|  
|**Значение по умолчанию**|Нет.|  
|**Наличие**|Необходимо наличие одного такого элемента, если не задан никакой другой тип рабочей нагрузки. Для родительского элемента `EventString` необходимо задать дочерний элемент `File`, `Database` или `Workload`, однако одновременно может использоваться только один из них. Например, если рабочая нагрузка определена посредством элемента `Database`, в том же входном XML-файле нельзя указывать рабочую нагрузку также с помощью элемента `File`.|  
  
## <a name="element-relationships"></a>Связи элемента  
  
|Связь|Элементы|  
|------------------|--------------|  
|**Родительский элемент**|[Элемент Workload (DTA)](workload-element-dta.md)|  
|**Дочерние элементы**|[Элемент Name для базы данных (DTA)](name-element-for-database-dta.md)<br /><br /> [Элемент Schema описания базы данных (DTA)](schema-element-for-database-dta.md)|  
  
## <a name="remarks"></a>Remarks  
 Этот элемент с именем **DatabaseDetailsTypecomplexType** определен в схеме XML помощника по настройке ядра СУБД. Не путайте этот элемент `Database` с элементом, корневым родительским элементом которого является `Configuration`. (См. раздел [Элемент Database описания конфигурации (DTA)](database-element-for-configuration-dta.md).)  
  
## <a name="example"></a>Пример  
 Пример использования этого `Database` элемента см. в примере кода в [элементе рабочей нагрузки &#40;dta&#41;](workload-element-dta.md).  
  
## <a name="see-also"></a>См. также:  
 [Справочник по входным XML-файлам (помощник по настройке ядра СУБД)](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
