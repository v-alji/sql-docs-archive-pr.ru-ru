---
title: Изменение поведения драйвера ODBC при обработке преобразований символов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 682a232a-bf89-4849-88a1-95b2fbac1467
author: rothja
ms.author: jroth
ms.openlocfilehash: 5334b4268559ba155a53b3be655d87f7867779df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730585"
---
# <a name="odbc-driver-behavior-change-when-handling-character-conversions"></a><span data-ttu-id="0b0f7-102">Изменение поведения драйвера ODBC при обработке преобразования символов</span><span class="sxs-lookup"><span data-stu-id="0b0f7-102">ODBC Driver Behavior Change When Handling Character Conversions</span></span>
  <span data-ttu-id="0b0f7-103">[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]Драйвер ODBC для собственного клиента (SQLNCLI11.dll) изменил то, как он выполняет преобразование SQL_WCHAR \* (nchar/nvarchar/nvarchar (max)) и SQL_CHAR \* (char/varchar/НАРЧАР (max)).</span><span class="sxs-lookup"><span data-stu-id="0b0f7-103">The [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client ODBC Driver (SQLNCLI11.dll) changed how it does of SQL_WCHAR\* (NCHAR/NVARCHAR/NVARCHAR(MAX)) and SQL_CHAR\* (CHAR/VARCHAR/NARCHAR(MAX)) conversions.</span></span> <span data-ttu-id="0b0f7-104">При использовании драйвера Native Client ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2012 функции ODBC, например SQLGetData, SQLBindCol и SQLBindParameter, возвращают (-4) SQL_NO_TOTAL в качестве параметра длины или индикатора.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-104">ODBC functions, such as SQLGetData, SQLBindCol, SQLBindParameter, return (-4) SQL_NO_TOTAL as the length/indicator parameter when using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2012 Native Client ODBC driver.</span></span> <span data-ttu-id="0b0f7-105">Предыдущие версии драйвера Native Client ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] возвращали значение длины, которое могло быть неверным.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-105">Prior versions of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver returned a length value, which can be incorrect.</span></span>  
  
## <a name="sqlgetdata-behavior"></a><span data-ttu-id="0b0f7-106">Поведение SQLGetData</span><span class="sxs-lookup"><span data-stu-id="0b0f7-106">SQLGetData Behavior</span></span>  
 <span data-ttu-id="0b0f7-107">Многие функции Windows позволяют указывать нулевой размер буфера, при этом возвращаемая длина является размером возвращаемых данных.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-107">Many Windows functions let you specify a buffer size of 0 and the returned length is the size of the returned data.</span></span> <span data-ttu-id="0b0f7-108">Следующий вариант является стандартным для программистов Windows:</span><span class="sxs-lookup"><span data-stu-id="0b0f7-108">The following pattern is common for Windows programmers:</span></span>  
  
```  
int iSize = 0;  
BYTE * pBuffer = NULL;  
GetMyFavoriteAPI(pBuffer, &iSize);   // Returns needed size in iSize  
pBuffer = new BYTE[iSize];   // Allocate buffer   
GetMyFavoriteAPI(pBuffer, &iSize);   // Retrieve actual data  
```  
  
 <span data-ttu-id="0b0f7-109">Однако **SQLGetData** не следует использовать в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-109">However, **SQLGetData** should not be used in this scenario.</span></span> <span data-ttu-id="0b0f7-110">Не следует использовать следующий вариант.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-110">The following pattern should not be used:</span></span>  
  
```  
// bad  
int iSize = 0;  
WCHAR * pBuffer = NULL;  
SQLGetData(hstmt, SQL_W_CHAR, ...., (SQLPOINTER*)0x1, 0, &iSize);   // Get storage size needed  
pBuffer = new WCHAR[(iSize/sizeof(WCHAR)) + 1];   // Allocate buffer  
SQLGetData(hstmt, SQL_W_CHAR, ...., (SQLPOINTER*)pBuffer, iSize, &iSize);   // Retrieve data  
```  
  
 <span data-ttu-id="0b0f7-111">**SQLGetData** можно вызывать только для получения фрагментов фактических данных.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-111">**SQLGetData** can only be called to retrieve chunks of actual data.</span></span> <span data-ttu-id="0b0f7-112">Использование **SQLGetData** для получения размера данных не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-112">Using **SQLGetData** to get the size of data is not unsupported.</span></span>  
  
 <span data-ttu-id="0b0f7-113">Далее показано влияние изменения драйвера, которое проявляется при использовании неверного варианта.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-113">The following shows the impact of the driver change when you use the incorrect pattern.</span></span> <span data-ttu-id="0b0f7-114">Это приложение запрашивает столбец и привязку `varchar` как Юникод (SQL_UNICODE/SQL_WCHAR):</span><span class="sxs-lookup"><span data-stu-id="0b0f7-114">This application queries a `varchar` column and binding as Unicode (SQL_UNICODE/SQL_WCHAR):</span></span>  
  
 <span data-ttu-id="0b0f7-115">Выбор`select convert(varchar(36), '123')`</span><span class="sxs-lookup"><span data-stu-id="0b0f7-115">Query:  `select convert(varchar(36), '123')`</span></span>  
  
```  
SQLGetData(hstmt, SQL_WCHAR, ....., (SQLPOINTER*) 0x1, 0 , &iSize);   // Attempting to determine storage size needed  
```  
  
|<span data-ttu-id="0b0f7-116">Версия драйвера Native Client ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b0f7-116">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver version</span></span>|<span data-ttu-id="0b0f7-117">Итоговая длина или индикатор</span><span class="sxs-lookup"><span data-stu-id="0b0f7-117">Length or Indicator Outcome</span></span>|<span data-ttu-id="0b0f7-118">Описание</span><span class="sxs-lookup"><span data-stu-id="0b0f7-118">Description</span></span>|  
|-----------------------------------------------------------------|---------------------------------|-----------------|  
|<span data-ttu-id="0b0f7-119">Native Client [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] или более ранняя версия</span><span class="sxs-lookup"><span data-stu-id="0b0f7-119">[!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] Native Client or earlier</span></span>|<span data-ttu-id="0b0f7-120">6</span><span class="sxs-lookup"><span data-stu-id="0b0f7-120">6</span></span>|<span data-ttu-id="0b0f7-121">Драйвер ошибочно предположил, что преобразование CHAR в WCHAR можно было выполнить как умножение длины на 2.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-121">The driver incorrectly assumed that converting CHAR to WCHAR could be accomplished as length \* 2.</span></span>|  
|<span data-ttu-id="0b0f7-122">Native Client [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] (версия 11.0.2100.60) или более поздняя версия</span><span class="sxs-lookup"><span data-stu-id="0b0f7-122">[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client (version 11.0.2100.60) or later</span></span>|<span data-ttu-id="0b0f7-123">-4 (SQL_NO_TOTAL)</span><span class="sxs-lookup"><span data-stu-id="0b0f7-123">-4 (SQL_NO_TOTAL)</span></span>|<span data-ttu-id="0b0f7-124">Драйвер больше не предполагает, что преобразование типа CHAR в тип WCHAR или WCHAR в CHAR является действием (умножение) \* 2 или (деление)/2.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-124">The driver no longer assumes that converting from CHAR to WCHAR or WCHAR to CHAR is a (multiply) \*2 or (divide)/2 action.</span></span><br /><br /> <span data-ttu-id="0b0f7-125">Вызов **SQLGetData** больше не возвращает длину ожидаемого преобразования.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-125">Calling **SQLGetData** no longer returns the length of the expected conversion.</span></span> <span data-ttu-id="0b0f7-126">Драйвер обнаруживает преобразование из CHAR в WCHAR или обратное преобразование и возвращает (-4) SQL_NO_TOTAL вместо \*2 или /2, что могло быть неверным.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-126">The driver detects the conversion to or from CHAR and WCHAR and returns (-4) SQL_NO_TOTAL instead of \*2 or /2 behavior that could be incorrect.</span></span>|  
  
 <span data-ttu-id="0b0f7-127">Используйте **SQLGetData** для извлечения фрагментов данных.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-127">Use **SQLGetData** to retrieve the chunks of the data.</span></span> <span data-ttu-id="0b0f7-128">(Показан псевдокод).</span><span class="sxs-lookup"><span data-stu-id="0b0f7-128">(Pseudo code shown:)</span></span>  
  
```  
while( (SQL_SUCCESS or SQL_SUCCESS_WITH_INFO) == SQLFetch(...) ) {  
   SQLNumCols(...iTotalCols...)  
   for(int iCol = 1; iCol < iTotalCols; iCol++) {  
      WCHAR* pBufOrig, pBuffer = new WCHAR[100];  
      SQLGetData(.... iCol ... pBuffer, 100, &iSize);   // Get original chunk  
      while(NOT ALL DATA RETREIVED (SQL_NO_TOTAL, ...) ) {  
         pBuffer += 50;   // Advance buffer for data retrieved  
         // May need to realloc the buffer when you reach current size  
         SQLGetData(.... iCol ... pBuffer, 100, &iSize);   // Get next chunk  
      }  
   }  
}  
```  
  
## <a name="sqlbindcol-behavior"></a><span data-ttu-id="0b0f7-129">Поведение функции SQLBindCol</span><span class="sxs-lookup"><span data-stu-id="0b0f7-129">SQLBindCol Behavior</span></span>  
 <span data-ttu-id="0b0f7-130">Выбор`select convert(varchar(36), '1234567890')`</span><span class="sxs-lookup"><span data-stu-id="0b0f7-130">Query:  `select convert(varchar(36), '1234567890')`</span></span>  
  
```  
SQLBindCol(... SQL_W_CHAR, ...)   // Only bound a buffer of WCHAR[4] - Expecting String Data Right Truncation behavior  
```  
  
|<span data-ttu-id="0b0f7-131">Версия драйвера Native Client ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b0f7-131">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver version</span></span>|<span data-ttu-id="0b0f7-132">Итоговая длина или индикатор</span><span class="sxs-lookup"><span data-stu-id="0b0f7-132">Length or Indicator Outcome</span></span>|<span data-ttu-id="0b0f7-133">Описание</span><span class="sxs-lookup"><span data-stu-id="0b0f7-133">Description</span></span>|  
|-----------------------------------------------------------------|---------------------------------|-----------------|  
|<span data-ttu-id="0b0f7-134">Native Client [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] или более ранняя версия</span><span class="sxs-lookup"><span data-stu-id="0b0f7-134">[!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] Native Client or earlier</span></span>|<span data-ttu-id="0b0f7-135">20</span><span class="sxs-lookup"><span data-stu-id="0b0f7-135">20</span></span>|<span data-ttu-id="0b0f7-136">-   **SQLFetch** сообщает, что в правой части данных имеется усечение.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-136">-   **SQLFetch** reports that there is a truncation on the right side of the data.</span></span><br /><span data-ttu-id="0b0f7-137">-Length — это Длина возвращаемых данных, а не то, что было сохранено (предполагает преобразование \* 2 CHAR в WCHAR, которое может быть неправильным для глифов).</span><span class="sxs-lookup"><span data-stu-id="0b0f7-137">-   Length is the length of the data returned, not what was stored (assumes \*2 CHAR to WCHAR conversion which can be incorrect for glyphs).</span></span><br /><span data-ttu-id="0b0f7-138">— Данные, хранящиеся в буфере, имеют значение 123 \ 0.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-138">-   Data stored in buffer is 123\0.</span></span> <span data-ttu-id="0b0f7-139">Буфер гарантированно заканчивается на NULL.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-139">Buffer is guaranteed to be NULL terminated.</span></span>|  
|<span data-ttu-id="0b0f7-140">Native Client [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] (версия 11.0.2100.60) или более поздняя версия</span><span class="sxs-lookup"><span data-stu-id="0b0f7-140">[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client (version 11.0.2100.60) or later</span></span>|<span data-ttu-id="0b0f7-141">-4 (SQL_NO_TOTAL)</span><span class="sxs-lookup"><span data-stu-id="0b0f7-141">-4 (SQL_NO_TOTAL)</span></span>|<span data-ttu-id="0b0f7-142">-   **SQLFetch** сообщает, что в правой части данных имеется усечение.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-142">-   **SQLFetch** reports that there is a truncation on the right side of the data.</span></span><br /><span data-ttu-id="0b0f7-143">-Length означает-4 (SQL_NO_TOTAL), так как остальные данные не были преобразованы.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-143">-   Length indicates -4 (SQL_NO_TOTAL) because the rest of the data was not converted.</span></span><br /><span data-ttu-id="0b0f7-144">— Данные, хранящиеся в буфере, имеют значение 123 \ 0.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-144">-   Data stored in the buffer is 123\0.</span></span> <span data-ttu-id="0b0f7-145">- Буфер гарантированно заканчивается на NULL.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-145">- Buffer is guaranteed to be NULL terminated.</span></span>|  
  
## <a name="sqlbindparameter-output-parameter-behavior"></a><span data-ttu-id="0b0f7-146">SQLBindParameter (поведение параметра OUTPUT)</span><span class="sxs-lookup"><span data-stu-id="0b0f7-146">SQLBindParameter (OUTPUT Parameter Behavior)</span></span>  
 <span data-ttu-id="0b0f7-147">Выбор`create procedure spTest @p1 varchar(max) OUTPUT`</span><span class="sxs-lookup"><span data-stu-id="0b0f7-147">Query:  `create procedure spTest @p1 varchar(max) OUTPUT`</span></span>  
  
 `select @p1 = replicate('B', 1234)`  
  
```  
SQLBindParameter(... SQL_W_CHAR, ...)   // Only bind up to first 64 characters  
```  
  
|<span data-ttu-id="0b0f7-148">Версия драйвера Native Client ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b0f7-148">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver version</span></span>|<span data-ttu-id="0b0f7-149">Итоговая длина или индикатор</span><span class="sxs-lookup"><span data-stu-id="0b0f7-149">Length or Indicator Outcome</span></span>|<span data-ttu-id="0b0f7-150">Описание</span><span class="sxs-lookup"><span data-stu-id="0b0f7-150">Description</span></span>|  
|-----------------------------------------------------------------|---------------------------------|-----------------|  
|<span data-ttu-id="0b0f7-151">Native Client [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] или более ранняя версия</span><span class="sxs-lookup"><span data-stu-id="0b0f7-151">[!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] Native Client or earlier</span></span>|<span data-ttu-id="0b0f7-152">2468</span><span class="sxs-lookup"><span data-stu-id="0b0f7-152">2468</span></span>|<span data-ttu-id="0b0f7-153">-   **SQLFetch** больше не возвращает данные.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-153">-   **SQLFetch** returns no more data available.</span></span><br /><span data-ttu-id="0b0f7-154">-   **SQLMoreResults** больше не возвращает данные.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-154">-   **SQLMoreResults** returns no more data available.</span></span><br /><span data-ttu-id="0b0f7-155">-Length указывает размер данных, возвращаемых с сервера, не хранимых в буфере.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-155">-   Length indicates the size of the data returned from server, not stored in buffer.</span></span><br /><span data-ttu-id="0b0f7-156">— Исходный буфер содержит 63 байт и знак завершения NULL.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-156">-   Original buffer contains 63 bytes and a NULL terminator.</span></span> <span data-ttu-id="0b0f7-157">Буфер гарантированно заканчивается на NULL.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-157">Buffer is guaranteed to be NULL terminated.</span></span>|  
|<span data-ttu-id="0b0f7-158">Native Client [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] (версия 11.0.2100.60) или более поздняя версия</span><span class="sxs-lookup"><span data-stu-id="0b0f7-158">[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client (version 11.0.2100.60) or later</span></span>|<span data-ttu-id="0b0f7-159">-4 (SQL_NO_TOTAL)</span><span class="sxs-lookup"><span data-stu-id="0b0f7-159">-4 (SQL_NO_TOTAL)</span></span>|<span data-ttu-id="0b0f7-160">-   **SQLFetch** больше не возвращает данные.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-160">-   **SQLFetch** returns no more data available.</span></span><br /><span data-ttu-id="0b0f7-161">-   **SQLMoreResults** больше не возвращает данные.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-161">-   **SQLMoreResults** returns no more data available.</span></span><br /><span data-ttu-id="0b0f7-162">-Length указывает (-4) SQL_NO_TOTAL, так как остальные данные не были преобразованы.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-162">-   Length indicates (-4) SQL_NO_TOTAL because the rest of the data was not converted.</span></span><br /><span data-ttu-id="0b0f7-163">— Исходный буфер содержит 63 байт и знак завершения NULL.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-163">-   Original buffer contains 63 bytes and a NULL terminator.</span></span> <span data-ttu-id="0b0f7-164">Буфер гарантированно заканчивается на NULL.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-164">Buffer is guaranteed to be NULL terminated.</span></span>|  
  
## <a name="performing-char-and-wchar-conversions"></a><span data-ttu-id="0b0f7-165">Выполнение преобразований CHAR и WCHAR</span><span class="sxs-lookup"><span data-stu-id="0b0f7-165">Performing CHAR and WCHAR Conversions</span></span>  
 <span data-ttu-id="0b0f7-166">Драйвер Native Client ODBC [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] предлагает несколько вариантов выполнения преобразования CHAR и WCHAR.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-166">The [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client ODBC driver offers several ways to perform CHAR and WCHAR conversions.</span></span> <span data-ttu-id="0b0f7-167">Логика аналогична манипуляции с большими двоичными объектами (varchar (max), nvarchar (max),...):</span><span class="sxs-lookup"><span data-stu-id="0b0f7-167">The logic is similar to manipulating blobs (varchar(max), nvarchar(max), ...):</span></span>  
  
-   <span data-ttu-id="0b0f7-168">Данные сохраняются или усекаются в указанном буфере при привязке с помощью **SQLBindCol** или **SQLBindParameter**.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-168">Data is saved or truncated into the specified buffer when binding with **SQLBindCol** or **SQLBindParameter**.</span></span>  
  
-   <span data-ttu-id="0b0f7-169">Если не выполнить привязку, можно получить данные в блоках с помощью **SQLGetData** и **метод SQLParamData**.</span><span class="sxs-lookup"><span data-stu-id="0b0f7-169">If you do not bind, you can retrieve the data in chunks by using **SQLGetData** and **SQLParamData**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b0f7-170">См. также:</span><span class="sxs-lookup"><span data-stu-id="0b0f7-170">See Also</span></span>  
 [<span data-ttu-id="0b0f7-171">Компоненты собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="0b0f7-171">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
