---
title: bcp_moretext | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_moretext
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_moretext function
ms.assetid: 23e98015-a8e4-4434-9b3f-9c7350cf965f
author: rothja
ms.author: jroth
ms.openlocfilehash: 00c0eb1c8739e94380b12034cebc70d8e22b79c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657771"
---
# <a name="bcp_moretext"></a><span data-ttu-id="83528-102">bcp_moretext</span><span class="sxs-lookup"><span data-stu-id="83528-102">bcp_moretext</span></span>
  <span data-ttu-id="83528-103">Отправляет в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] часть значения длинного типа данных переменной длины.</span><span class="sxs-lookup"><span data-stu-id="83528-103">Sends part of a long, variable-length data type value to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83528-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83528-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_moretext (  
HDBC   
hdbc  
,  
DBINT   
cbData  
,  
LPCBYTE   
pData  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="83528-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="83528-105">Arguments</span></span>  
 <span data-ttu-id="83528-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="83528-106">*hdbc*</span></span>  
 <span data-ttu-id="83528-107">Дескриптор соединения ODBC с поддержкой массового копирования.</span><span class="sxs-lookup"><span data-stu-id="83528-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="83528-108">*cbData*</span><span class="sxs-lookup"><span data-stu-id="83528-108">*cbData*</span></span>  
 <span data-ttu-id="83528-109">Число байтов данных, копируемых в SQL Server из данных, на которые ссылается *pData*.</span><span class="sxs-lookup"><span data-stu-id="83528-109">Is the number of bytes of data being copied to SQL Server from the data referenced by *pData*.</span></span> <span data-ttu-id="83528-110">Значение SQL_NULL_DATA соответствует значению NULL.</span><span class="sxs-lookup"><span data-stu-id="83528-110">A value of SQL_NULL_DATA indicates NULL.</span></span>  
  
 <span data-ttu-id="83528-111">*pData*</span><span class="sxs-lookup"><span data-stu-id="83528-111">*pData*</span></span>  
 <span data-ttu-id="83528-112">Представляет собой указатель на ту часть значения поддерживаемого длинного типа данных переменной длины, которую нужно переслать в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83528-112">Is a pointer to the supported, long, variable-length data chunk to be sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="returns"></a><span data-ttu-id="83528-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="83528-113">Returns</span></span>  
 <span data-ttu-id="83528-114">SUCCEED или FAIL.</span><span class="sxs-lookup"><span data-stu-id="83528-114">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83528-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="83528-115">Remarks</span></span>  
 <span data-ttu-id="83528-116">Эта функция может использоваться в сочетании с [bcp_bind](bcp-bind.md) и [bcp_sendrow](bcp-sendrow.md) для копирования длинных значений данных переменной длины, которые SQL Serverся в нескольких меньших фрагментах.</span><span class="sxs-lookup"><span data-stu-id="83528-116">This function can be used in conjunction with [bcp_bind](bcp-bind.md) and [bcp_sendrow](bcp-sendrow.md) to copy long, variable-length data values to SQL Server in a number of smaller chunks.</span></span> <span data-ttu-id="83528-117">**bcp_moretext** можно использовать со столбцами, имеющими следующие SQL Server типов данных: `text` , `ntext` , `image` ,,, `varchar(max)` `nvarchar(max)` `varbinary(max)` , определяемый пользователем тип (UDT) и XML.</span><span class="sxs-lookup"><span data-stu-id="83528-117">**bcp_moretext** can be used with columns that have the following SQL Server data types: `text`, `ntext`, `image`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, user-defined type (UDT), and XML.</span></span> <span data-ttu-id="83528-118">**bcp_moretext** не поддерживает преобразования данных, указанные данные должны соответствовать типу данных целевого столбца.</span><span class="sxs-lookup"><span data-stu-id="83528-118">**bcp_moretext** does not support data conversions, the data supplied must match the data type of the target column.</span></span>  
  
 <span data-ttu-id="83528-119">Если **bcp_bind** вызывается с параметром *pData* , не равным null, для типов данных, поддерживаемых **bcp_moretext**, `bcp_sendrow` отправляет все значения данных, независимо от длины.</span><span class="sxs-lookup"><span data-stu-id="83528-119">If **bcp_bind** is called with a nonNULL *pData* parameter for data types that are supported by **bcp_moretext**, `bcp_sendrow` sends the entire data value, regardless of length.</span></span> <span data-ttu-id="83528-120">Однако, если **bcp_bind** имеет параметр *pData* NULL для поддерживаемых типов данных, **bcp_moretext** можно использовать для копирования данных сразу после успешного возврата с того, `bcp_sendrow` что все связанные столбцы с данными уже обработаны.</span><span class="sxs-lookup"><span data-stu-id="83528-120">If, however, **bcp_bind** has a NULL *pData* parameter for supported data types, **bcp_moretext** can be used to copy data immediately after a successful return from `bcp_sendrow` indicating that any bound columns with data present have been processed.</span></span>  
  
 <span data-ttu-id="83528-121">Если для отправки одного столбца поддерживаемого типа данных в строке используется **bcp_moretext** , необходимо также использовать его для отправки всех остальных поддерживаемых столбцов типа данных в строке.</span><span class="sxs-lookup"><span data-stu-id="83528-121">If you use **bcp_moretext** to send one supported data type column in a row, you must also use it to send all other supported data type columns in the row.</span></span> <span data-ttu-id="83528-122">Ни один столбец не может быть пропущен.</span><span class="sxs-lookup"><span data-stu-id="83528-122">No columns may be skipped.</span></span> <span data-ttu-id="83528-123">Поддерживаемыми типами данных являются SQLTEXT, SQLNTEXT, SQLIMAGE, SQLUDT и SQLXML.</span><span class="sxs-lookup"><span data-stu-id="83528-123">Supported data types are SQLTEXT, SQLNTEXT, SQLIMAGE, SQLUDT and SQLXML.</span></span> <span data-ttu-id="83528-124">То же относится к типам данных SQLCHARACTER, SQLVARCHAR, SQNCHAR, SQLBINARY и SQLVARBINARY, если столбец имеет тип varchar(max), nvarchar(max) или varbinary(max) соответственно.</span><span class="sxs-lookup"><span data-stu-id="83528-124">SQLCHARACTER, SQLVARCHAR, SQNCHAR, SQLBINARY and SQLVARBINARY also fall into this category if the column is a varchar(max), nvarchar(max) or varbinary(max), respectively.</span></span>  
  
 <span data-ttu-id="83528-125">Вызов либо **bcp_bind** , либо [bcp_collen](bcp-collen.md) задает общую длину всех частей данных, копируемых в столбец SQL Server.</span><span class="sxs-lookup"><span data-stu-id="83528-125">Calling either **bcp_bind** or [bcp_collen](bcp-collen.md) sets the total length of all data parts to be copied to the SQL Server column.</span></span> <span data-ttu-id="83528-126">Попытка отправить SQL Server больше байтов, чем указано в вызове функции **bcp_bind** или `bcp_collen` выдает ошибку.</span><span class="sxs-lookup"><span data-stu-id="83528-126">An attempt to send SQL Server more bytes than specified in the call to **bcp_bind** or `bcp_collen` generates an error.</span></span> <span data-ttu-id="83528-127">Эта ошибка может возникнуть, например, в приложении, которое использовалось `bcp_collen` для установки длины доступных данных для SQL Server `text` столбца в 4500, затем вызывается **bcp_moretext** пять раз, указывая на каждый вызов, длина буфера данных которой составила 1000 байт.</span><span class="sxs-lookup"><span data-stu-id="83528-127">This error would arise, for example, in an application which used `bcp_collen` to set the length of available data for an SQL Server `text` column to 4500, then called **bcp_moretext** five times while indicating on each call that the data buffer length was 1000 bytes long.</span></span>  
  
 <span data-ttu-id="83528-128">Если скопированная строка содержит более одного столбца переменной длины, **bcp_moretext** сначала отправляет свои данные в столбец с наименьшим порядковым номером, за которым следует столбец с наименьшим порядковым номером и так далее.</span><span class="sxs-lookup"><span data-stu-id="83528-128">If a copied row contains more than one long, variable-length column, **bcp_moretext** first sends its data to the lowest ordinally numbered column, followed by the next lowest ordinally numbered column, and so on.</span></span> <span data-ttu-id="83528-129">Необходимо правильно задать длину ожидаемых данных.</span><span class="sxs-lookup"><span data-stu-id="83528-129">Correct setting of the total length of expected data is important.</span></span> <span data-ttu-id="83528-130">Какой-либо иной способ определения того, что в операции массового копирования получены все данные столбца, кроме проверки по заданной длине, отсутствует.</span><span class="sxs-lookup"><span data-stu-id="83528-130">There is no way to signal, outside of the length setting, that all data for a column has been received by bulk copy.</span></span>  
  
 <span data-ttu-id="83528-131">Если `var(max)` значения отправляются на сервер с помощью bcp_sendrow и bcp_moretext, нет необходимости вызывать bcp_collen для задания длины столбца.</span><span class="sxs-lookup"><span data-stu-id="83528-131">When `var(max)` values are sent to the server using bcp_sendrow and bcp_moretext, it is not necessary to call bcp_collen to set the column length.</span></span> <span data-ttu-id="83528-132">Вместо этого для этих типов значение завершается вызовом bcp_sendrow с нулевой длиной.</span><span class="sxs-lookup"><span data-stu-id="83528-132">Instead, for these types only, the value is terminated by calling bcp_sendrow with a length of zero.</span></span>  
  
 <span data-ttu-id="83528-133">Приложение обычно вызывает `bcp_sendrow` и **bcp_moretext** в циклах для отправки нескольких строк данных.</span><span class="sxs-lookup"><span data-stu-id="83528-133">An application normally calls `bcp_sendrow` and **bcp_moretext** within loops to send a number of rows of data.</span></span> <span data-ttu-id="83528-134">Ниже приведена схема того, как это сделать для таблицы, содержащей два `text` столбца:</span><span class="sxs-lookup"><span data-stu-id="83528-134">Here's an outline of how to do this for a table containing two `text` columns:</span></span>  
  
```  
while (there are still rows to send)  
{  
bcp_sendrow(...);  
  
for (all the data in the first varbinary(max) column)  
bcp_moretext(...);  
bcp_moretext(hdbc, 0, NULL);  
  
for (all the data in the second varbinary(max) column)  
bcp_moretext(...);  
bcp_moretext(hdbc, 0, NULL);  
  
}  
  
```  
  
## <a name="example"></a><span data-ttu-id="83528-135">Пример</span><span class="sxs-lookup"><span data-stu-id="83528-135">Example</span></span>  
 <span data-ttu-id="83528-136">В этом примере показано, как использовать **bcp_moretext** с **bcp_bind** и `bcp_sendrow` :</span><span class="sxs-lookup"><span data-stu-id="83528-136">This example shows how to use **bcp_moretext** with **bcp_bind** and `bcp_sendrow`:</span></span>  
  
```  
// Variables like henv not specified.  
HDBC      hdbc;  
DBINT      idRow = 5;  
char*      pPart1 = "This text value isn't very long,";  
char*      pPart2 = " but it's broken into three parts";  
char*      pPart3 = " anyhow.";  
DBINT      cbAllParts;  
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
if (bcp_init(hdbc, "comdb..articles", NULL, NULL, DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Bind program variables to table columns.   
if (bcp_bind(hdbc, (LPCBYTE) &idRow, 0, SQL_VARLEN_DATA, NULL, 0,  
   SQLINT4, 1)    == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
cbAllParts = (DBINT) (strnlen(pPart1, sizeof(pPart1) + 1) + strnlen(pPart2, sizeof(pPart2) + 1) + strnlen(pPart3, sizeof(pPart3) + 1));  
if (bcp_bind(hdbc, NULL, 0, cbAllParts, NULL, 0, SQLTEXT, 2) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Send this row, with the text value broken into three chunks.   
if (bcp_sendrow(hdbc) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_moretext(hdbc, (DBINT) strnlen(pPart1, sizeof(pPart1) + 1), pPart1) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
if (bcp_moretext(hdbc, (DBINT) strnlen(pPart2, sizeof(pPart2) + 1), pPart2) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
if (bcp_moretext(hdbc, (DBINT) strnlen(pPart3, sizeof(pPart3) + 1), pPart3) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// All done. Get the number of rows processed (should be one).  
nRowsProcessed = bcp_done(hdbc);  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="83528-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="83528-137">See Also</span></span>  
 [<span data-ttu-id="83528-138">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="83528-138">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
