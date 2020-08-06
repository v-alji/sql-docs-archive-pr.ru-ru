---
title: IBCPSession::BCPReadFmt (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPReadFmt (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPReadFmt method
ms.assetid: e2a12050-94e4-48a3-8a48-b780d646f116
author: rothja
ms.author: jroth
ms.openlocfilehash: ca811dceb8ab6771e3bdd6689a8e11eca6a0e3ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739806"
---
# <a name="ibcpsessionbcpreadfmt-ole-db"></a><span data-ttu-id="6e46a-102">Метод IBCPSession::BCPReadFmt (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="6e46a-102">IBCPSession::BCPReadFmt (OLE DB)</span></span>
  <span data-ttu-id="6e46a-103">Считывает сведения о формате для каждого столбца из файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="6e46a-103">Reads format information for each column from the format file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e46a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e46a-104">Syntax</span></span>  
  
```  
  
HRESULT BCPReadFmt(   
const wchar_t *pwszFormatFile);  
```  
  
## <a name="remarks"></a><span data-ttu-id="6e46a-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="6e46a-105">Remarks</span></span>  
 <span data-ttu-id="6e46a-106">Метод **BCPReadFmt** используется для считывания данных из файла форматирования, указывающего формат данных в файле данных.</span><span class="sxs-lookup"><span data-stu-id="6e46a-106">The **BCPReadFmt** method is used for reading data from a format file that specifies the format of data in the data file.</span></span> <span data-ttu-id="6e46a-107">Данный метод способен определить правильную версию файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="6e46a-107">This method is capable of detecting the correct version of the format file.</span></span> <span data-ttu-id="6e46a-108">Он может автоматически определить, в каком формате находится файл форматирования — XML или формат текста по старому стилю, —и действовать соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="6e46a-108">It can automatically detect whether the format file is in xml or old style text format and behaves accordingly.</span></span> <span data-ttu-id="6e46a-109">Программа BCP поставщика OLE DB собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает версии файла форматирования 6.0 и следующие.</span><span class="sxs-lookup"><span data-stu-id="6e46a-109">The format file versions supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider BCP are version 6.0 or newer.</span></span>  
  
 <span data-ttu-id="6e46a-110">После того как метод **BCPReadFmt** считывает значения формата, он выполняет соответствующие вызовы методов [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) и [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="6e46a-110">After the **BCPReadFmt** method reads the format values, it makes the appropriate calls to the [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) and [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) methods.</span></span> <span data-ttu-id="6e46a-111">Пользователю не требуется производить анализ файла форматирования и выполнять эти вызовы.</span><span class="sxs-lookup"><span data-stu-id="6e46a-111">There is no need for the user to parse a format file and make these calls.</span></span>  
  
 <span data-ttu-id="6e46a-112">Чтобы сохранить файл форматирования, вызовите метод [IBCPSession::BCPWriteFmt](ibcpsession-bcpwritefmt-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="6e46a-112">To save a format file, call the [IBCPSession::BCPWriteFmt](ibcpsession-bcpwritefmt-ole-db.md) method.</span></span> <span data-ttu-id="6e46a-113">Вызовы метода **BCPReadFmt** могут ссылаться на сохраненные форматы.</span><span class="sxs-lookup"><span data-stu-id="6e46a-113">Calls to the **BCPReadFmt** method can reference saved formats.</span></span> <span data-ttu-id="6e46a-114">Кроме того, программа массового копирования (**bcp**) может сохранять определяемые пользователем форматы данных в файлах, на которые может ссылаться метод **BCPReadFmt** .</span><span class="sxs-lookup"><span data-stu-id="6e46a-114">Alternatively, the bulk-copy utility (**bcp**) can save user-defined data formats in files that can be referenced by the **BCPReadFmt** method.</span></span>  
  
 <span data-ttu-id="6e46a-115">`BCP_OPTION_DELAYREADFMT`Значение параметра *eOption* [IBCPSession:: BCPControl](ibcpsession-bcpcontrol-ole-db.md) изменяет поведение IBCPSession:: BCPReadFmt.</span><span class="sxs-lookup"><span data-stu-id="6e46a-115">The `BCP_OPTION_DELAYREADFMT` value of the *eOption* parameter of [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md) modifies the behavior of IBCPSession::BCPReadFmt.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="6e46a-116">Аргументы</span><span class="sxs-lookup"><span data-stu-id="6e46a-116">Arguments</span></span>  
 <span data-ttu-id="6e46a-117">*pwszFormatFile*[in]</span><span class="sxs-lookup"><span data-stu-id="6e46a-117">*pwszFormatFile*[in]</span></span>  
 <span data-ttu-id="6e46a-118">Путь и имя файла, содержащего значения формата для файла данных.</span><span class="sxs-lookup"><span data-stu-id="6e46a-118">The path and file name of the file containing the format values for the data file.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="6e46a-119">Значения кода возврата</span><span class="sxs-lookup"><span data-stu-id="6e46a-119">Return Code Values</span></span>  
 <span data-ttu-id="6e46a-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="6e46a-120">S_OK</span></span>  
 <span data-ttu-id="6e46a-121">Метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="6e46a-121">The method succeeded.</span></span>  
  
 <span data-ttu-id="6e46a-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6e46a-122">E_FAIL</span></span>  
 <span data-ttu-id="6e46a-123">Произошла ошибка, связанная с поставщиком. Подробные сведения можно получить с помощью интерфейса [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="6e46a-123">A provider-specific error occurred, for detailed information use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="6e46a-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6e46a-124">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="6e46a-125">Ошибка, связанная с нехваткой памяти.</span><span class="sxs-lookup"><span data-stu-id="6e46a-125">Out of memory error.</span></span>  
  
 <span data-ttu-id="6e46a-126">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="6e46a-126">E_UNEXPECTED</span></span>  
 <span data-ttu-id="6e46a-127">Непредвиденный вызов метода.</span><span class="sxs-lookup"><span data-stu-id="6e46a-127">The call to the method was unexpected.</span></span> <span data-ttu-id="6e46a-128">Например, перед вызовом этого метода не был вызван метод [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="6e46a-128">For example, the [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) method was not called before calling this method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e46a-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="6e46a-129">See Also</span></span>  
 <span data-ttu-id="6e46a-130">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="6e46a-130">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="6e46a-131">Выполнение операций массового копирования</span><span class="sxs-lookup"><span data-stu-id="6e46a-131">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
