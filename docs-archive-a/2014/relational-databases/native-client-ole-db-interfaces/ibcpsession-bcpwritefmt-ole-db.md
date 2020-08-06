---
title: IBCPSession::BCPWriteFmt (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPWriteFmt (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPWriteFmt method
ms.assetid: add50425-2ed6-411a-a391-4ce63c364892
author: rothja
ms.author: jroth
ms.openlocfilehash: ee4dcb5809c0f0fbb6d3f7aba6f4af5f6991e0e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667718"
---
# <a name="ibcpsessionbcpwritefmt-ole-db"></a><span data-ttu-id="02fe0-102">IBCPSession::BCPWriteFmt (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="02fe0-102">IBCPSession::BCPWriteFmt (OLE DB)</span></span>
  <span data-ttu-id="02fe0-103">Записывает в файл форматирования сведения о формате каждого из столбцов.</span><span class="sxs-lookup"><span data-stu-id="02fe0-103">Writes format information for each column to the format file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02fe0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02fe0-104">Syntax</span></span>  
  
```  
  
HRESULT BCPWriteFmt(   
const wchar_t *pwszFormatFile);  
```  
  
## <a name="remarks"></a><span data-ttu-id="02fe0-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="02fe0-105">Remarks</span></span>  
 <span data-ttu-id="02fe0-106">Файл форматирования определяет формат данных, содержащихся в файле данных, создаваемом при массовом копировании.</span><span class="sxs-lookup"><span data-stu-id="02fe0-106">The format file specifies the data format of a data file created by bulk copy.</span></span> <span data-ttu-id="02fe0-107">Вызовы методов [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) и [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) определяют формат файла данных.</span><span class="sxs-lookup"><span data-stu-id="02fe0-107">Calls to the [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) and [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) methods define the format of the data file.</span></span> <span data-ttu-id="02fe0-108">Метод **BCPWriteFmt** сохраняет это определение в файле, на который ссылается аргумент pwszFormatFile.</span><span class="sxs-lookup"><span data-stu-id="02fe0-108">The **BCPWriteFmt** method saves this definition in the file referenced by the pwszFormatFile argument.</span></span>  
  
 <span data-ttu-id="02fe0-109">Метод **BCPWriteFmt** может сохранять файлы форматирования в формате xml или текстовом формате.</span><span class="sxs-lookup"><span data-stu-id="02fe0-109">The **BCPWriteFmt** method can save the format files in either xml or text format.</span></span> <span data-ttu-id="02fe0-110">Это должно определяться с помощью параметра управления BCP_OPTION_XML методом [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="02fe0-110">This must be indicated by using the BCP_OPTION_XML control option with the [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md) method.</span></span>  
  
 <span data-ttu-id="02fe0-111">Для загрузки сохраненного файла форматирования используется метод [IBCPSession::BCPReadFmt](ibcpsession-bcpreadfmt-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="02fe0-111">To load a saved format file, use the [IBCPSession::BCPReadFmt](ibcpsession-bcpreadfmt-ole-db.md) method.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="02fe0-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="02fe0-112">Arguments</span></span>  
 <span data-ttu-id="02fe0-113">*pwszFormatFile*[in]</span><span class="sxs-lookup"><span data-stu-id="02fe0-113">*pwszFormatFile*[in]</span></span>  
 <span data-ttu-id="02fe0-114">Путь и имя файла, содержащего значения формата для файла данных.</span><span class="sxs-lookup"><span data-stu-id="02fe0-114">The path and file name of the file containing the format values for the data file.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="02fe0-115">Значения кода возврата</span><span class="sxs-lookup"><span data-stu-id="02fe0-115">Return Code Values</span></span>  
 <span data-ttu-id="02fe0-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="02fe0-116">S_OK</span></span>  
 <span data-ttu-id="02fe0-117">Метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="02fe0-117">The method succeeded.</span></span>  
  
 <span data-ttu-id="02fe0-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="02fe0-118">E_FAIL</span></span>  
 <span data-ttu-id="02fe0-119">Произошла ошибка конкретного поставщика; для получения дополнительных сведений используйте интерфейс [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="02fe0-119">A provider-specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="02fe0-120">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="02fe0-120">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="02fe0-121">Недостаточно памяти.</span><span class="sxs-lookup"><span data-stu-id="02fe0-121">Out-of-memory error.</span></span>  
  
 <span data-ttu-id="02fe0-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="02fe0-122">E_UNEXPECTED</span></span>  
 <span data-ttu-id="02fe0-123">Непредвиденный вызов метода.</span><span class="sxs-lookup"><span data-stu-id="02fe0-123">The call to the method was unexpected.</span></span> <span data-ttu-id="02fe0-124">Например, перед вызовом этого метода не был вызван метод [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="02fe0-124">For example, the [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) method was not called before calling this method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02fe0-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="02fe0-125">See Also</span></span>  
 <span data-ttu-id="02fe0-126">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="02fe0-126">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="02fe0-127">Выполнение операций массового копирования</span><span class="sxs-lookup"><span data-stu-id="02fe0-127">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
