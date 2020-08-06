---
title: bcp_exec | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_exec
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_exec function
ms.assetid: b23ea2cc-8545-4873-b0c1-57e76b0a3a7b
author: rothja
ms.author: jroth
ms.openlocfilehash: f925c6cb1e3a36f79ba4f560a06c5b6d499ece4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654244"
---
# <a name="bcp_exec"></a><span data-ttu-id="630a6-102">bcp_exec</span><span class="sxs-lookup"><span data-stu-id="630a6-102">bcp_exec</span></span>
  <span data-ttu-id="630a6-103">Выполняет полное массовое копирование данных из пользовательского файла в таблицу базы данных или обратно.</span><span class="sxs-lookup"><span data-stu-id="630a6-103">Executes a complete bulk copy of data between a database table and a user file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="630a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="630a6-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_exec (  
HDBC   
hdbc  
,  
LPDBINT   
pnRowsProcessed  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="630a6-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="630a6-105">Arguments</span></span>  
 <span data-ttu-id="630a6-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="630a6-106">*hdbc*</span></span>  
 <span data-ttu-id="630a6-107">Дескриптор соединения ODBC с поддержкой массового копирования.</span><span class="sxs-lookup"><span data-stu-id="630a6-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="630a6-108">*pnRowsProcessed*</span><span class="sxs-lookup"><span data-stu-id="630a6-108">*pnRowsProcessed*</span></span>  
 <span data-ttu-id="630a6-109">Указатель на переменную DBINT.</span><span class="sxs-lookup"><span data-stu-id="630a6-109">Is a pointer to a DBINT.</span></span> <span data-ttu-id="630a6-110">Функция **bcp_exec** заполняет DBINT числом успешно скопированных строк.</span><span class="sxs-lookup"><span data-stu-id="630a6-110">The **bcp_exec** function fills this DBINT with the number of rows successfully copied.</span></span> <span data-ttu-id="630a6-111">Если значение параметра *pnRowsProcessed* равно NULL, то оно не учитывается функцией **bcp_exec**.</span><span class="sxs-lookup"><span data-stu-id="630a6-111">If *pnRowsProcessed* is NULL, it is ignored by **bcp_exec**.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="630a6-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="630a6-112">Returns</span></span>  
 <span data-ttu-id="630a6-113">SUCCEED, SUCCEED_ASYNC или FAIL.</span><span class="sxs-lookup"><span data-stu-id="630a6-113">SUCCEED, SUCCEED_ASYNC, or FAIL.</span></span> <span data-ttu-id="630a6-114">Функция **bcp_exec** возвращает значение SUCCEED, если были скопированы все строки.</span><span class="sxs-lookup"><span data-stu-id="630a6-114">The **bcp_exec** function returns SUCCEED if all rows are copied.</span></span> <span data-ttu-id="630a6-115">Если асинхронная операция массового копирование еще не завершена, то функция**bcp_exec** возвращает значение SUCCEED_ASYNC.</span><span class="sxs-lookup"><span data-stu-id="630a6-115">**bcp_exec** returns SUCCEED_ASYNC if an asynchronous bulk copy operation is still outstanding.</span></span> <span data-ttu-id="630a6-116">Функция**bcp_exec** возвращает значение FAIL, если возникла неисправимая ошибка либо если число ошибочных строк достигло значения, заданного в параметре BCPMAXERRS с помощью программы [bcp_control](bcp-control.md).</span><span class="sxs-lookup"><span data-stu-id="630a6-116">**bcp_exec** returns FAIL if a complete failure occurs, or if the number of rows generating errors reaches the value specified for BCPMAXERRS using [bcp_control](bcp-control.md).</span></span> <span data-ttu-id="630a6-117">Значение BCPMAXERRS по умолчанию равно 10.</span><span class="sxs-lookup"><span data-stu-id="630a6-117">BCPMAXERRS defaults to 10.</span></span> <span data-ttu-id="630a6-118">Параметр BCPMAXERRS относится только к синтаксическим ошибкам, обнаруживаемым поставщиком при чтении строк из файла данных (а не к строкам, отправляемым на сервер).</span><span class="sxs-lookup"><span data-stu-id="630a6-118">The BCPMAXERRS option affects only the syntax errors detected by the provider while reading the rows from the data file (and not the rows sent to the server).</span></span> <span data-ttu-id="630a6-119">Сервер прерывает выполнение пакета при обнаружении ошибки в строке.</span><span class="sxs-lookup"><span data-stu-id="630a6-119">Server aborts the batch when it detects an error with a row.</span></span> <span data-ttu-id="630a6-120">Проверьте параметр *pnRowsProcessed* , чтобы получить число успешно скопированных строк.</span><span class="sxs-lookup"><span data-stu-id="630a6-120">Check the *pnRowsProcessed* parameter for the number of rows successfully copied.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="630a6-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="630a6-121">Remarks</span></span>  
 <span data-ttu-id="630a6-122">Эта функция копирует данные из пользовательского файла в таблицу базы данных или наоборот в зависимости от значения параметра *eDirection* в функции [bcp_init](bcp-init.md).</span><span class="sxs-lookup"><span data-stu-id="630a6-122">This function copies data from a user file to a database table or vice versa, depending on the value of the *eDirection* parameter in [bcp_init](bcp-init.md).</span></span>  
  
 <span data-ttu-id="630a6-123">Перед вызовом функции **bcp_exec**необходимо вызвать функцию **bcp_init** с допустимым именем пользовательского файла.</span><span class="sxs-lookup"><span data-stu-id="630a6-123">Before calling **bcp_exec**, call **bcp_init** with a valid user file name.</span></span> <span data-ttu-id="630a6-124">Несоблюдение этого правила приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="630a6-124">Failure to do so results in an error.</span></span>  
  
 <span data-ttu-id="630a6-125">Функция**bcp_exec** представляет собой только функцию массового копирования, которая с большой долей вероятности остается необработанной в течение неограниченного отрезка времени.</span><span class="sxs-lookup"><span data-stu-id="630a6-125">**bcp_exec** is the only bulk copy function that is likely to be outstanding for any length of time.</span></span> <span data-ttu-id="630a6-126">Вот почему это единственная функция массового копирования, поддерживающая асинхронный режим.</span><span class="sxs-lookup"><span data-stu-id="630a6-126">It is therefore the only bulk copy function that supports asynchronous mode.</span></span> <span data-ttu-id="630a6-127">Для установки асинхронного режима используется функция [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) , чтобы выставить атрибуту SQL_ATTR_ASYNC_ENABLE значение SQL_ASYNC_ENABLE_ON перед вызовом функции **bcp_exec**.</span><span class="sxs-lookup"><span data-stu-id="630a6-127">To set asynchronous mode, use [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) to set SQL_ATTR_ASYNC_ENABLE to SQL_ASYNC_ENABLE_ON before calling **bcp_exec**.</span></span> <span data-ttu-id="630a6-128">Для проверки завершения копирования необходимо вызвать функцию **bcp_exec** с такими же параметрами.</span><span class="sxs-lookup"><span data-stu-id="630a6-128">To test for completion, call **bcp_exec** with the same parameters.</span></span> <span data-ttu-id="630a6-129">Если массовое копирование еще не завершено, функция **bcp_exec** возвращает значение SUCCEED_ASYNC.</span><span class="sxs-lookup"><span data-stu-id="630a6-129">If the bulk copy has not yet completed, **bcp_exec** returns SUCCEED_ASYNC.</span></span> <span data-ttu-id="630a6-130">Она также возвращает в параметре *pnRowsProcessed* состояние счетчика числа строк, которые были отправлены серверу.</span><span class="sxs-lookup"><span data-stu-id="630a6-130">It also returns in *pnRowsProcessed* a status count of the number of rows that have been sent to the server.</span></span> <span data-ttu-id="630a6-131">Строки, отправленные на сервер, не фиксируются до тех пор, пока не будет достигнут конец пакета.</span><span class="sxs-lookup"><span data-stu-id="630a6-131">Rows sent to the server are not committed until the end of a batch has been reached.</span></span>  
  
 <span data-ttu-id="630a6-132">Дополнительные сведения о критическом изменении в разделе Выполнение операций с массовым копированием, начиная с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , см. в статье [осуществление операции копирования &#40;&#41;ODBC ](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="630a6-132">For information about a breaking change in bulk-copying beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], see [Performing Bulk Copy Operations &#40;ODBC&#41;](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="630a6-133">Пример</span><span class="sxs-lookup"><span data-stu-id="630a6-133">Example</span></span>  
 <span data-ttu-id="630a6-134">Следующий пример иллюстрирует использование функции **bcp_exec**:</span><span class="sxs-lookup"><span data-stu-id="630a6-134">The following example shows how to use **bcp_exec**:</span></span>  
  
```  
// Variables like henv not specified.  
HDBC      hdbc;  
DBINT      nRowsProcessed;  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source, return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bulk copy.   
if (bcp_init(hdbc, _T("pubs..authors"), _T("authors.sav"), NULL, DB_OUT)  
   == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Now, execute the bulk copy.   
if (bcp_exec(hdbc, &nRowsProcessed) == FAIL)  
   {  
   if (nRowsProcessed == -1)  
      {  
      printf_s("No rows processed on bulk copy execution.\n");  
      }  
   else  
      {  
      printf_s("Incomplete bulk copy.   Only %ld row%s copied.\n",  
         nRowsProcessed, (nRowsProcessed == 1) ? "": "s");  
      }  
   return;  
   }  
  
printf_s("%ld rows processed.\n", nRowsProcessed);  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="630a6-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="630a6-135">See Also</span></span>  
 [<span data-ttu-id="630a6-136">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="630a6-136">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
