---
title: SQLNumResultCols | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLNumResultCols function
ms.assetid: f79d8b3c-521e-4e50-a564-21d73ae5767b
author: rothja
ms.author: jroth
ms.openlocfilehash: 45e72165eef621dc377b02ed3d2e7e1e3cf7ab8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668282"
---
# <a name="sqlnumresultcols"></a><span data-ttu-id="0b7ba-102">SQLNumResultCols</span><span class="sxs-lookup"><span data-stu-id="0b7ba-102">SQLNumResultCols</span></span>
  <span data-ttu-id="0b7ba-103">Для выполненных инструкций драйверу ODBC собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] нет необходимости обращаться к серверу для сообщения о числе столбцов результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="0b7ba-103">For executed statements, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not visit the server to report the number of columns in a result set.</span></span> <span data-ttu-id="0b7ba-104">В этом случае не `SQLNumResultCols` вызывает обмен данными с сервером.</span><span class="sxs-lookup"><span data-stu-id="0b7ba-104">In this case, `SQLNumResultCols` does not cause a server roundtrip.</span></span> <span data-ttu-id="0b7ba-105">Как и в [SQLDescribeCol](sqldescribecol.md) и [SQLColAttribute](sqlcolattribute.md), вызов `SQLNumResultCols` на подготовленных, но не выполненных инструкциях создает обмен данными между серверами.</span><span class="sxs-lookup"><span data-stu-id="0b7ba-105">Like [SQLDescribeCol](sqldescribecol.md) and [SQLColAttribute](sqlcolattribute.md), calling `SQLNumResultCols` on prepared but not executed statements generates a server roundtrip.</span></span>  
  
 <span data-ttu-id="0b7ba-106">Если инструкция или пакет инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] возвращает несколько результирующих наборов строк, можно изменить число столбцов одного результирующего набора на число столбцов в другом наборе.</span><span class="sxs-lookup"><span data-stu-id="0b7ba-106">When a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statement batch returns multiple result row sets, it is possible for the number of result set columns to change from one set to another.</span></span> <span data-ttu-id="0b7ba-107">`SQLNumResultCols`должен вызываться для каждого набора.</span><span class="sxs-lookup"><span data-stu-id="0b7ba-107">`SQLNumResultCols` should be called for each set.</span></span> <span data-ttu-id="0b7ba-108">При изменении числа столбцов приложение должно осуществить повторную привязку значений данных перед выборкой результатов строк.</span><span class="sxs-lookup"><span data-stu-id="0b7ba-108">When the number of columns changes, the application should rebind data values prior to fetching row results.</span></span> <span data-ttu-id="0b7ba-109">Дополнительные сведения об обработке запросов, возвращающих несколько результирующих наборов, см. в разделе [SQLMoreResults](sqlmoreresults.md).</span><span class="sxs-lookup"><span data-stu-id="0b7ba-109">For more information about handling multiple result set returns, see [SQLMoreResults](sqlmoreresults.md).</span></span>  
  
 <span data-ttu-id="0b7ba-110">Улучшения в ядре СУБД, начиная с, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] позволяют SQLNumResultCols получать более точные описания ожидаемых результатов.</span><span class="sxs-lookup"><span data-stu-id="0b7ba-110">Improvements in the database engine starting with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] allow SQLNumResultCols to obtain more accurate descriptions of the expected results.</span></span> <span data-ttu-id="0b7ba-111">Эти более точные результаты могут отличаться от значений, возвращаемых функцией SQLNumResultCols в предыдущих версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0b7ba-111">These more accurate results may differ from the values returned by SQLNumResultCols in previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0b7ba-112">Дополнительные сведения см. в разделе [Обнаружение метаданных](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="0b7ba-112">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b7ba-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="0b7ba-113">See Also</span></span>  
 <span data-ttu-id="0b7ba-114">[Функция SQLNumResultCols](https://go.microsoft.com/fwlink/?LinkId=59359) </span><span class="sxs-lookup"><span data-stu-id="0b7ba-114">[SQLNumResultCols Function](https://go.microsoft.com/fwlink/?LinkId=59359) </span></span>  
 [<span data-ttu-id="0b7ba-115">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="0b7ba-115">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
