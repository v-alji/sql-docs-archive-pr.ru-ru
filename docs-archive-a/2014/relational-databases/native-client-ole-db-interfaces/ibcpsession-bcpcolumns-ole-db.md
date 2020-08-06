---
title: IBCPSession::BCPColumns (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPColumns (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPColumns method
ms.assetid: c338abe8-9e30-4853-a7c6-b1a6c00095e1
author: rothja
ms.author: jroth
ms.openlocfilehash: c842b2a815074c0db7e6ab21e0a85eac68a986a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739821"
---
# <a name="ibcpsessionbcpcolumns-ole-db"></a><span data-ttu-id="4626d-102">IBCPSession::BCPColumns (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="4626d-102">IBCPSession::BCPColumns (OLE DB)</span></span>
  <span data-ttu-id="4626d-103">Задает количество полей для привязки к столбцам в таблице [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4626d-103">Sets the number of fields that are to be bound to the columns in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4626d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4626d-104">Syntax</span></span>  
  
```  
  
HRESULT BCPColumns(   
DBCOUNTITEMnColumns);  
```  
  
## <a name="remarks"></a><span data-ttu-id="4626d-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="4626d-105">Remarks</span></span>  
 <span data-ttu-id="4626d-106">Этот метод совершает внутренний вызов метода [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) для установки значений по умолчанию для полей данных.</span><span class="sxs-lookup"><span data-stu-id="4626d-106">Internally it calls [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) to set the default values for field data.</span></span> <span data-ttu-id="4626d-107">Эти значения по умолчанию получаются из информации о столбце SQL Server, которую внутренним образом возвращает поставщик, когда имя таблицы указывается через [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="4626d-107">These default values are obtained from the SQL Server column information that the provider internally retrieves when the table name is specified through [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4626d-108"> Данный метод можно вызывать только после того, как вызван метод **BCPInit** с допустимым именем файла.</span><span class="sxs-lookup"><span data-stu-id="4626d-108">This method can be called only after **BCPInit** has been called with a valid file name.</span></span>  
  
 <span data-ttu-id="4626d-109">Этот метод следует вызывать только в случае, когда планируется использовать нестандартный формат пользовательского файла.</span><span class="sxs-lookup"><span data-stu-id="4626d-109">You should call this method only if you intend to use a user-file format that differs from the default.</span></span> <span data-ttu-id="4626d-110">Дополнительную информацию об описании стандартного формата пользовательского файла см. в справке по методу **BCPInit** .</span><span class="sxs-lookup"><span data-stu-id="4626d-110">For more information about a description of the default user-file format, see the **BCPInit** method.</span></span>  
  
 <span data-ttu-id="4626d-111">После вызова метода **BCPColumns** следует вызвать метод **BCPColFmt** для каждого столбца в пользовательском файле, чтобы полностью описать нестандартный формат файла.</span><span class="sxs-lookup"><span data-stu-id="4626d-111">After calling the **BCPColumns** method, you must call the **BCPColFmt** method for each column in the user file to completely define a custom file format.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="4626d-112">Аргументы</span><span class="sxs-lookup"><span data-stu-id="4626d-112">Arguments</span></span>  
 <span data-ttu-id="4626d-113">*nColumns*[in]</span><span class="sxs-lookup"><span data-stu-id="4626d-113">*nColumns*[in]</span></span>  
 <span data-ttu-id="4626d-114">Общее число полей в пользовательском файле.</span><span class="sxs-lookup"><span data-stu-id="4626d-114">The total number of fields in the user file.</span></span> <span data-ttu-id="4626d-115">Даже если предполагается массовое копирование данных из пользовательского файла в таблицу SQL Server и не предполагается копирование всех полей в пользовательском файле, аргументу *nColumns* следует присвоить значение, равное общему числу полей в пользовательском файле.</span><span class="sxs-lookup"><span data-stu-id="4626d-115">Even if you are preparing to bulk copy data from the user file to a SQL Server table and do not intend to copy all fields in the user file, you must still set the *nColumns* argument to the total number of user-file fields.</span></span> <span data-ttu-id="4626d-116">Затем с помощью свойства **BCPColFmt**можно указать поля, которые нужно пропустить.</span><span class="sxs-lookup"><span data-stu-id="4626d-116">The skipped fields can then be specified through **BCPColFmt**.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="4626d-117">Значения кода возврата</span><span class="sxs-lookup"><span data-stu-id="4626d-117">Return Code Values</span></span>  
 <span data-ttu-id="4626d-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="4626d-118">S_OK</span></span>  
 <span data-ttu-id="4626d-119">Метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="4626d-119">The method succeeded.</span></span>  
  
 <span data-ttu-id="4626d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4626d-120">E_FAIL</span></span>  
 <span data-ttu-id="4626d-121">Произошла ошибка конкретного поставщика; для получения дополнительных сведений используйте интерфейс [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="4626d-121">A provider-specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="4626d-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="4626d-122">E_UNEXPECTED</span></span>  
 <span data-ttu-id="4626d-123">Непредвиденный вызов метода.</span><span class="sxs-lookup"><span data-stu-id="4626d-123">The call to the method was unexpected.</span></span> <span data-ttu-id="4626d-124">Например, перед вызовом этого метода не был вызван метод **BCPInit** .</span><span class="sxs-lookup"><span data-stu-id="4626d-124">For example, the **BCPInit** method was not called before calling this method.</span></span> <span data-ttu-id="4626d-125">Это значение возвращается также, если данный метод был вызван несколько раз для операции массового копирования.</span><span class="sxs-lookup"><span data-stu-id="4626d-125">Also occurs when this method is called more than once for a bulk copy operation.</span></span>  
  
 <span data-ttu-id="4626d-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4626d-126">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="4626d-127">Недостаточно памяти.</span><span class="sxs-lookup"><span data-stu-id="4626d-127">Out-of-memory error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4626d-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="4626d-128">See Also</span></span>  
 <span data-ttu-id="4626d-129">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="4626d-129">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="4626d-130">Выполнение операций массового копирования</span><span class="sxs-lookup"><span data-stu-id="4626d-130">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
