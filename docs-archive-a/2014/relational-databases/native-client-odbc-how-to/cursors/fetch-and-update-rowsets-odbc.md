---
title: Выборка и обновление наборов строк (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowsets [ODBC]
ms.assetid: cf0eb3b4-8b72-49fc-a845-95edc360cf93
author: rothja
ms.author: jroth
ms.openlocfilehash: e09a3033e0883452ecd69b82c9375ed28c920da0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654245"
---
# <a name="fetch-and-update-rowsets-odbc"></a><span data-ttu-id="467d5-102">Выбор и обновление наборов строк (ODBC)</span><span class="sxs-lookup"><span data-stu-id="467d5-102">Fetch and Update Rowsets (ODBC)</span></span>
    
### <a name="to-fetch-and-update-rowsets"></a><span data-ttu-id="467d5-103">Получение и обновление наборов строк</span><span class="sxs-lookup"><span data-stu-id="467d5-103">To fetch and update rowsets</span></span>  
  
1.  <span data-ttu-id="467d5-104">При необходимости вызовите [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) с SQL_ROW_ARRAY_SIZE, чтобы изменить число строк (R) в наборе строк.</span><span class="sxs-lookup"><span data-stu-id="467d5-104">Optionally, call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) with SQL_ROW_ARRAY_SIZE to change the number of rows (R) in the rowset.</span></span>  
  
2.  <span data-ttu-id="467d5-105">Вызовите [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) или [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) , чтобы получить набор строк.</span><span class="sxs-lookup"><span data-stu-id="467d5-105">Call [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) to get a rowset.</span></span>  
  
3.  <span data-ttu-id="467d5-106">Если используются связанные столбцы, используйте для набора строк значения данных и длины данных, доступные теперь в буферах связанных столбцов.</span><span class="sxs-lookup"><span data-stu-id="467d5-106">If bound columns are used, use the data values and data lengths now available in the bound column buffers for the rowset.</span></span>  
  
     <span data-ttu-id="467d5-107">Если используются несвязанные столбцы, вызовите для каждой строки [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) с параметром SQL_POSITION, чтобы установить позицию курсора, а затем выполните следующие действия для каждого несвязанного столбца.</span><span class="sxs-lookup"><span data-stu-id="467d5-107">If unbound columns are used, for each row call [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) with SQL_POSITION to set the cursor position; then, for each unbound column:</span></span>  
  
    -   <span data-ttu-id="467d5-108">Вызовите [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) один или более раз, чтобы получить данные для несвязанных столбцов после последнего связанного столбца в наборе строк.</span><span class="sxs-lookup"><span data-stu-id="467d5-108">Call [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) one or more times to get the data for unbound columns after the last bound column of the rowset.</span></span> <span data-ttu-id="467d5-109">Вызовы [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) должны происходить в порядке возрастания номеров столбцов.</span><span class="sxs-lookup"><span data-stu-id="467d5-109">Calls to [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) should be in order of increasing column number.</span></span>  
  
    -   <span data-ttu-id="467d5-110">Получение данных из столбца типа text или image производится многократным вызовом функции [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) .</span><span class="sxs-lookup"><span data-stu-id="467d5-110">Call [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) multiple times to get data from a text or image column.</span></span>  
  
4.  <span data-ttu-id="467d5-111">Настройте текстовые столбцы или столбцы изображений, получающие данные во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="467d5-111">Set up any data-at-execution text or image columns.</span></span>  
  
5.  <span data-ttu-id="467d5-112">Используйте вызовы [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) или [SQLBulkOperations](https://go.microsoft.com/fwlink/?LinkId=58398) для установки положения курсора, обновления, удаления или добавления строк в наборе строк.</span><span class="sxs-lookup"><span data-stu-id="467d5-112">Call [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) or [SQLBulkOperations](https://go.microsoft.com/fwlink/?LinkId=58398) to set the cursor position, refresh, update, delete, or add row(s) within the rowset.</span></span>  
  
     <span data-ttu-id="467d5-113">Если для операций обновления и удаления используются текстовые столбцы или столбцы изображений, получающие данные во время выполнения, обработайте их.</span><span class="sxs-lookup"><span data-stu-id="467d5-113">If data-at-execution text or image columns are used for an update or add operation, handle them.</span></span>  
  
6.  <span data-ttu-id="467d5-114">Выполните инструкцию позиционирования UPDATE или DELETE, задав имя курсора (его можно получить с помощью [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md)) и используя дескриптор другой инструкции в том же соединении (необязательно).</span><span class="sxs-lookup"><span data-stu-id="467d5-114">Optionally, execute a positioned UPDATE or DELETE statement, specifying the cursor name (available from [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md)) and using a different statement handle on the same connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="467d5-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="467d5-115">See Also</span></span>  
 [<span data-ttu-id="467d5-116">Инструкции по использованию курсоров &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="467d5-116">Using Cursors How-to Topics &#40;ODBC&#41;</span></span>](using-cursors-how-to-topics-odbc.md)  
  
  
