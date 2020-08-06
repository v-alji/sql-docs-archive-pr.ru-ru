---
title: Получение сведений о результирующем наборе (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- result sets [ODBC]
- result sets [ODBC], fetching
ms.assetid: 34f235e4-f80b-4123-8764-9deb18506f14
author: rothja
ms.author: jroth
ms.openlocfilehash: 0f7ed275eb9b6558a77160c3c7fb2fc233c199cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657756"
---
# <a name="retrieve-result-set-information-odbc"></a>Получение сведений о результирующем наборе (ODBC)
    
### <a name="to-get-information-about-a-result-set"></a>Получение сведений о результирующем наборе  
  
1.  Вызовите [SQLNumResultCols](../native-client-odbc-api/sqlnumresultcols.md) , чтобы получить количество столбцов в результирующем наборе.  
  
2.  Для каждого столбца в результирующем наборе:  
  
    -   Вызовите [SQLDescribeCol](../native-client-odbc-api/sqldescribecol.md) , чтобы получить сведения о столбце Result.  
  
     Или  
  
    -   Вызовите [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) , чтобы получить конкретные сведения о дескрипторе столбца результатов.  
  
## <a name="see-also"></a>См. также:  
 [Разделы руководства по обработке результатов &#40;ODBC&#41;](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md)   
 [Определение характеристик результирующего набора &#40;ODBC&#41;](../native-client-odbc-results/determining-the-characteristics-of-a-result-set-odbc.md)  
  
  
