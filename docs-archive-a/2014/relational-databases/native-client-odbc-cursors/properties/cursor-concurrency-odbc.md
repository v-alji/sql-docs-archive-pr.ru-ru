---
title: Параллелизм курсоров (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- concurrency [ODBC]
- cursors [ODBC], concurrency
- ODBC cursors, concurrency
ms.assetid: 68228ece-cbf1-4f19-bfdc-053884c1af48
author: rothja
ms.author: jroth
ms.openlocfilehash: c47f24152978fedf8f2c3d49ec3b721969712814
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666561"
---
# <a name="cursor-concurrency-odbc"></a>Параллелизм курсоров (ODBC)
  Операции курсора, как и типы курсора, зависят от параметров параллелизма, устанавливаемых приложением. Параметры параллелизма задаются с помощью параметра SQL_ATTR_CONCURRENCY [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md). Существуют следующие типы параллелизма.  
  
-   Только для чтения (SQL_CONCUR_READONLY).  
  
-   Значения (SQL_CONCUR_VALUES).  
  
-   Версия строки (SQL_CONCUR_ROWVER).  
  
-   Блокировка (SQL_CONCUR_LOCK).  
  
## <a name="see-also"></a>См. также:  
 [Свойства курсора](cursor-properties.md)  
  
  
