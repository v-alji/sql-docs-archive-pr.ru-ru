---
title: bcp_readfmt | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_readfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_readfmt function
ms.assetid: 654001c8-ae9f-425c-b820-f0191bf89367
author: rothja
ms.author: jroth
ms.openlocfilehash: 37032ec276be8b914d73e834453cc5d87cdedbbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657768"
---
# <a name="bcp_readfmt"></a><span data-ttu-id="98552-102">bcp_readfmt</span><span class="sxs-lookup"><span data-stu-id="98552-102">bcp_readfmt</span></span>
  <span data-ttu-id="98552-103">Считывает определение формата файла данных из указанного файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="98552-103">Reads a data file format definition from the specified format file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98552-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98552-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_readfmt (  
HDBC   
hdbc  
,  
LPCTSTR   
szFormatFile  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="98552-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="98552-105">Arguments</span></span>  
 <span data-ttu-id="98552-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="98552-106">*hdbc*</span></span>  
 <span data-ttu-id="98552-107">Дескриптор соединения ODBC с поддержкой массового копирования.</span><span class="sxs-lookup"><span data-stu-id="98552-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="98552-108">*szFormatFile*</span><span class="sxs-lookup"><span data-stu-id="98552-108">*szFormatFile*</span></span>  
 <span data-ttu-id="98552-109">Путь и имя файла, содержащего значения формата для файла данных.</span><span class="sxs-lookup"><span data-stu-id="98552-109">Is the path and file name of the file containing the format values for the data file.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="98552-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="98552-110">Returns</span></span>  
 <span data-ttu-id="98552-111">SUCCEED или FAIL.</span><span class="sxs-lookup"><span data-stu-id="98552-111">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98552-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="98552-112">Remarks</span></span>  
 <span data-ttu-id="98552-113">После `bcp_readfmt` считывания значений формата они выполняют соответствующие вызовы [bcp_columns](bcp-columns.md) и [bcp_colfmt](bcp-colfmt.md).</span><span class="sxs-lookup"><span data-stu-id="98552-113">After `bcp_readfmt` reads the format values, it makes the appropriate calls to [bcp_columns](bcp-columns.md) and [bcp_colfmt](bcp-colfmt.md).</span></span> <span data-ttu-id="98552-114">Пользователю не требуется анализировать файл форматирования и выполнять эти вызовы.</span><span class="sxs-lookup"><span data-stu-id="98552-114">There is no need for you to parse a format file and make these calls.</span></span>  
  
 <span data-ttu-id="98552-115">Чтобы сохранить файл форматирования, вызовите функцию [bcp_writefmt](bcp-writefmt.md).</span><span class="sxs-lookup"><span data-stu-id="98552-115">To persist a format file, call [bcp_writefmt](bcp-writefmt.md).</span></span> <span data-ttu-id="98552-116">Вызовы метода `bcp_readfmt` могут ссылаться на сохраненные форматы.</span><span class="sxs-lookup"><span data-stu-id="98552-116">Calls to `bcp_readfmt` can reference saved formats.</span></span> <span data-ttu-id="98552-117">Дополнительные сведения см. в разделе [bcp_init](bcp-init.md).</span><span class="sxs-lookup"><span data-stu-id="98552-117">For more information, see [bcp_init](bcp-init.md).</span></span>  
  
 <span data-ttu-id="98552-118">Кроме того, программа полного копирования (**bcp**) может сохранять пользовательские форматы данных в файлах, на которые может ссылаться `bcp_readfmt` .</span><span class="sxs-lookup"><span data-stu-id="98552-118">Alternately, the bulk-copy utility (**bcp**) can save user-defined data formats in files that can be referenced by `bcp_readfmt`.</span></span> <span data-ttu-id="98552-119">Дополнительные сведения о программе **bcp** и структуре файлов формата данных **bcp** см. в статье инструкции по [импорту и экспорту данных &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="98552-119">For more information about the **bcp** utility and the structure of **bcp** data format files, see [Bulk Import and Export of Data &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="98552-120">`BCPDELAYREADFMT`Значение параметра *eOption* [bcp_control](bcp-control.md) изменяет поведение bcp_readfmt.</span><span class="sxs-lookup"><span data-stu-id="98552-120">The `BCPDELAYREADFMT` value of the *eOption* parameter of [bcp_control](bcp-control.md) modifies the behavior of bcp_readfmt.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98552-121">Файл форматирования должен быть создан с помощью программы **bcp** версии 4.2 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="98552-121">The format file must have been produced by version 4.2 or later of the **bcp** utility.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98552-122">Пример</span><span class="sxs-lookup"><span data-stu-id="98552-122">Example</span></span>  
  
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
if (bcp_init(hdbc, _T("myTable"), _T("myData.csv"),  
   _T("myErrors"),    DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_readfmt(hdbc, _T("myFmtFile.fmt")) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_exec(hdbc, &nRowsProcessed) == SUCCEED)  
   {  
   cout << nRowsProcessed << " rows copied to SQL Server\n";  
   }  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="98552-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="98552-123">See Also</span></span>  
 [<span data-ttu-id="98552-124">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="98552-124">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
