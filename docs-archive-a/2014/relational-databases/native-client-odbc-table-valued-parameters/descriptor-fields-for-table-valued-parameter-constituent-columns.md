---
title: Поля дескриптора для составных столбцов возвращающего табличное значение параметра | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), descriptor fields for constituent columns
ms.assetid: 944b3968-fd47-4847-98d6-b87e8ef2acdc
author: rothja
ms.author: jroth
ms.openlocfilehash: 7474a4a80309f6ce9754fefabfd0080c89f803b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667078"
---
# <a name="descriptor-fields-for-table-valued-parameter-constituent-columns"></a>Поля дескриптора для столбцов, содержащих параметры, возвращающие табличные значения
  Поля дескриптора возвращающего табличное значение параметра, описанные в этом разделе, управляются с помощью [SQLSetDescField](../native-client-odbc-api/sqlsetdescfield.md) и [SQLSetDescField](../native-client-odbc-api/sqlsetdescfield.md) с дескриптором для дескриптора параметра реализации (IPD).  
  
## <a name="remarks"></a>Remarks  
 SQL_DESC_AUTO_UNIQUE_VALUE используется для параметров, возвращающих табличные значения, и других компонентов.  
  
|Имя атрибута|Type|Описание|  
|--------------------|----------|-----------------|  
|SQL_DESC_AUTO_UNIQUE_VALUE|SQLINTEGER|SQL_TRUE указывает, что этот столбец является столбцом идентификаторов.<br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]может использовать эти сведения для оптимизации производительности, но не обязательно устанавливать их для столбцов идентификаторов.|  
  
 Следующие атрибуты добавляются к параметрам всех типов в дескрипторе параметра приложения (APD) и дескрипторе параметра реализации (IPD).  
  
|Имя атрибута|Type|Описание|  
|--------------------|----------|-----------------|  
|SQL_CA_SS_COLUMN_COMPUTED|SQLSMALLINT|SQL_TRUE указывает, что этот столбец является вычисляемым.<br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]может использовать эту информацию для оптимизации производительности, но приложения не обязательно устанавливать их для вычислений столбцов.<br /><br /> Этот атрибут пропускается в случае привязок, не являющихся столбцами параметров, возвращающих табличные значения.|  
|SQL_CA_SS_COLUMN_IN_UNIQUE_KEY|SQLSMALLINT|SQL_TRUE указывает, что столбец возвращающих табличное значение параметров является частью уникального ключа. Это может повысить производительность запросов. Этот атрибут пропускается в случае привязок, не являющихся столбцами параметров, возвращающих табличные значения.|  
|SQL_CA_SS_COLUMN_SORT_ORDER|SQLSMALLINT|Указывает порядок сортировки столбца возвращающих табличное значение параметров. Это может повысить производительность запросов. Этот атрибут пропускается в случае привязок, не являющихся столбцами параметров, возвращающих табличные значения. Возможные значения.<br /><br /> — SQL_SS_ASCENDING_ORDER<br />— SQL_SS_DESCENDING_ORDER<br />— SQL_SS_ORDER_UNSPECIFIED<br /><br /> Для значений, отличных от SQL_SS_ASCENDING_ORDER и SQL_SS_DESCENDING_ORDER, будет выдана ошибка с кодом SQLSTATE HY024 и сообщением «Недопустимое значение атрибута», а дальнейшая обработка произведена таким же образом, как и для значения SQL_SS_ORDER_UNSPECIFIED, которое является значением по умолчанию этого атрибута.|  
|SQL_CA_SS_COLUMN_SORT_ORDINAL|SQLSMALLINT|Указывает порядковый номер столбца параметра, возвращающего табличное значение, в наборе столбцов, которые определяют сквозной порядковый номер для параметра, возвращающего табличное значение. Это может повысить производительность запросов. Этот атрибут пропускается в случае привязок, не являющихся столбцами параметров, возвращающих табличные значения. Порядковые номера сортировки начинаются с 1. Значение 0 (устанавливаемое по умолчанию) указывает, что столбец параметра, возвращающего табличное значение, не упорядочен.|  
|SQL_CA_SS_COLUMN_HAS_DEFAULT_VALUE|SQLSMALLINT|Указывает, будут ли все строки параметра, возвращающего табличное значение, иметь значение по умолчанию для этого столбца. Для параметров, возвращающих табличное значение, значение по умолчанию не может выбираться построчно. Значение SQL_FALSE указывает на то, что строки будут иметь значения отличные от значений по умолчанию. Это значение по умолчанию. Значение SQL_TRUE указывает, что этот столбец будет иметь значения по умолчанию для всех строк.<br /><br /> Если установлено значение SQL_TRUE, то данные не будут отправляться на сервер.<br /><br /> Это поле также используется со столбцами идентификаторов или вычисляемых столбцов, если их обработка на сервере не требуется.|  
  
 Эти атрибуты доступны только для столбцов возвращающих табличные значения параметров. Для других параметров они не учитываются.  
  
 Если для столбца, возвращающего табличное значение параметра, установлен атрибут SQL_CA_SS_COL_HAS_DEFAULT_VALUE, то SQL_DESC_DATA_PTR для этого столбца должен быть равен null. В противном случае SQLExecute или SQLExecDirect возвратит SQL_ERROR. Будет создана диагностическая запись с параметром SQLSTATE = 07S01 и сообщением "Недопустимое использование параметра по умолчанию для параметра \<p> , столбца \<c> ", где \<p> — это порядковый номер параметра, а \<c> — порядковый номер столбца.  
  
## <a name="see-also"></a>См. также:  
 [Возвращающие табличное значение параметры &#40;ODBC&#41;](table-valued-parameters-odbc.md)  
  
  