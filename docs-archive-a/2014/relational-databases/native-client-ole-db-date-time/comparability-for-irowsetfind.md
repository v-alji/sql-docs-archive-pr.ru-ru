---
title: Сравнимость для IRowsetFind | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- IRowsetFind comparability [ODBC]
ms.assetid: 7d148b56-9bbe-4e55-b31f-43f115705402
author: rothja
ms.author: jroth
ms.openlocfilehash: 8ad359ca4957b434c3798d1a441eb0fd57644a59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656387"
---
# <a name="comparability-for-irowsetfind"></a>Сравнимость для IRowsetFind
  Интерфейс IRowsetFind поддерживает следующие сравнения (только для типов даты-времени).  
  
-   LT  
  
-   LE  
  
-   EQ  
  
-   GE  
  
-   GT  
  
-   NE  
  
-   IGNORE  
  
 При попытке любого другого сравнения возвращается ошибка DB_E_BADCOMPAREOP. Это согласуется со спецификацией OLE DB.  
  
## <a name="see-also"></a>См. также:  
 [Улучшения функций даты и времени &#40;OLE DB&#41;](date-and-time-improvements-ole-db.md)  
  
  
