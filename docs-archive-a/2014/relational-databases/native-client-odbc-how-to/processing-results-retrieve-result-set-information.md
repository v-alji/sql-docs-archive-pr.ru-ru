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
# <a name="retrieve-result-set-information-odbc"></a><span data-ttu-id="31246-102">Получение сведений о результирующем наборе (ODBC)</span><span class="sxs-lookup"><span data-stu-id="31246-102">Retrieve Result Set Information (ODBC)</span></span>
    
### <a name="to-get-information-about-a-result-set"></a><span data-ttu-id="31246-103">Получение сведений о результирующем наборе</span><span class="sxs-lookup"><span data-stu-id="31246-103">To get information about a result set</span></span>  
  
1.  <span data-ttu-id="31246-104">Вызовите [SQLNumResultCols](../native-client-odbc-api/sqlnumresultcols.md) , чтобы получить количество столбцов в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="31246-104">Call [SQLNumResultCols](../native-client-odbc-api/sqlnumresultcols.md) to get the number of columns in the result set.</span></span>  
  
2.  <span data-ttu-id="31246-105">Для каждого столбца в результирующем наборе:</span><span class="sxs-lookup"><span data-stu-id="31246-105">For each column in the result set:</span></span>  
  
    -   <span data-ttu-id="31246-106">Вызовите [SQLDescribeCol](../native-client-odbc-api/sqldescribecol.md) , чтобы получить сведения о столбце Result.</span><span class="sxs-lookup"><span data-stu-id="31246-106">Call [SQLDescribeCol](../native-client-odbc-api/sqldescribecol.md) to get information about the result column.</span></span>  
  
     <span data-ttu-id="31246-107">Или</span><span class="sxs-lookup"><span data-stu-id="31246-107">Or</span></span>  
  
    -   <span data-ttu-id="31246-108">Вызовите [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) , чтобы получить конкретные сведения о дескрипторе столбца результатов.</span><span class="sxs-lookup"><span data-stu-id="31246-108">Call [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) to get specific descriptor information about the result column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31246-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="31246-109">See Also</span></span>  
 <span data-ttu-id="31246-110">[Разделы руководства по обработке результатов &#40;ODBC&#41;](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="31246-110">[Processing Results How-to Topics &#40;ODBC&#41;](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md) </span></span>  
 [<span data-ttu-id="31246-111">Определение характеристик результирующего набора &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="31246-111">Determining the Characteristics of a Result Set &#40;ODBC&#41;</span></span>](../native-client-odbc-results/determining-the-characteristics-of-a-result-set-odbc.md)  
  
  
