---
title: bcp_getcolfmt | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_getcolfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_getcolfmt function
ms.assetid: f8bdada5-7b2d-4475-8c98-f93e9d77b130
author: rothja
ms.author: jroth
ms.openlocfilehash: aabc811a5aa0babe5119c4ef0ed0e649586d73cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657774"
---
# <a name="bcp_getcolfmt"></a><span data-ttu-id="a0d37-102">bcp_getcolfmt</span><span class="sxs-lookup"><span data-stu-id="a0d37-102">bcp_getcolfmt</span></span>
  <span data-ttu-id="a0d37-103">Используется для нахождения значения свойства формата столбца.</span><span class="sxs-lookup"><span data-stu-id="a0d37-103">Used to find the column format property value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0d37-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0d37-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_getcolfmt (  
HDBC   
hdbc  
,  
INT   
field  
,  
INT   
property  
,  
void*   
pValue  
,  
INT   
cbvalue,  
INT*   
pcbLen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="a0d37-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a0d37-105">Arguments</span></span>  
 <span data-ttu-id="a0d37-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="a0d37-106">*hdbc*</span></span>  
 <span data-ttu-id="a0d37-107">Дескриптор соединения ODBC с поддержкой массового копирования.</span><span class="sxs-lookup"><span data-stu-id="a0d37-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="a0d37-108">*полями*</span><span class="sxs-lookup"><span data-stu-id="a0d37-108">*field*</span></span>  
 <span data-ttu-id="a0d37-109">Номер столбца, для которого получается свойство.</span><span class="sxs-lookup"><span data-stu-id="a0d37-109">Is the column number for which the property is retrieved.</span></span>  
  
 <span data-ttu-id="a0d37-110">*property*</span><span class="sxs-lookup"><span data-stu-id="a0d37-110">*property*</span></span>  
 <span data-ttu-id="a0d37-111">Одна из констант свойства.</span><span class="sxs-lookup"><span data-stu-id="a0d37-111">Is one of the property constants.</span></span>  
  
 <span data-ttu-id="a0d37-112">*pValue*</span><span class="sxs-lookup"><span data-stu-id="a0d37-112">*pValue*</span></span>  
 <span data-ttu-id="a0d37-113">Указатель на буфер, из которого получается значение свойства.</span><span class="sxs-lookup"><span data-stu-id="a0d37-113">Is the pointer to the buffer from which to retrieve the property value.</span></span>  
  
 <span data-ttu-id="a0d37-114">*кбвалуе*</span><span class="sxs-lookup"><span data-stu-id="a0d37-114">*cbValue*</span></span>  
 <span data-ttu-id="a0d37-115">Длина буфера свойств, в байтах.</span><span class="sxs-lookup"><span data-stu-id="a0d37-115">Is the length of the property buffer in bytes.</span></span>  
  
 <span data-ttu-id="a0d37-116">*pcbLen*</span><span class="sxs-lookup"><span data-stu-id="a0d37-116">*pcbLen*</span></span>  
 <span data-ttu-id="a0d37-117">Указатель длины данных, возвращаемых в буфер свойства.</span><span class="sxs-lookup"><span data-stu-id="a0d37-117">Pointer to length of the data that is being returned in the property buffer.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="a0d37-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a0d37-118">Returns</span></span>  
 <span data-ttu-id="a0d37-119">SUCCEED или FAIL.</span><span class="sxs-lookup"><span data-stu-id="a0d37-119">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0d37-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="a0d37-120">Remarks</span></span>  
 <span data-ttu-id="a0d37-121">Значения свойства формата столбца перечислены в разделе [bcp_setcolfmt](bcp-setcolfmt.md) .</span><span class="sxs-lookup"><span data-stu-id="a0d37-121">Column format property values are listed in the [bcp_setcolfmt](bcp-setcolfmt.md) topic.</span></span> <span data-ttu-id="a0d37-122">Они устанавливаются с помощью вызова функции **bcp_setcolfmt** , а для их поиска используется функция **bcp_getcolfmt** .</span><span class="sxs-lookup"><span data-stu-id="a0d37-122">The column format property values are set by calling the **bcp_setcolfmt** function, and the **bcp_getcolfmt** function is used to find the column format property value.</span></span>  
  
 <span data-ttu-id="a0d37-123">Изменения в поведении заметны при подключении к серверному компьютеру с [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] (или более поздней версии), если сравнивать с более ранними версиями [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a0d37-123">Behavior changes may be observed when connecting to a [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] (or later) server computer, compared to earlier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versions.</span></span> <span data-ttu-id="a0d37-124">Дополнительные сведения см. в разделе [Обнаружение метаданных](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="a0d37-124">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
## <a name="bcp_getcolfmt-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="a0d37-125">Поддержка функцией bcp_getcolfmt улучшенных возможностей даты-времени</span><span class="sxs-lookup"><span data-stu-id="a0d37-125">bcp_getcolfmt Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="a0d37-126">Типы, используемые со `BCP_FMT_TYPE` свойством для типов даты и времени, задаются в [инструкциях по расширению копирования для усовершенствованных типов даты и времени &#40;OLE DB и ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a0d37-126">The types used with the `BCP_FMT_TYPE` property for date/time types are as specified in [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="a0d37-127">Дополнительные сведения см. в разделе [улучшения даты и времени &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a0d37-127">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0d37-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="a0d37-128">See Also</span></span>  
 [<span data-ttu-id="a0d37-129">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="a0d37-129">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
