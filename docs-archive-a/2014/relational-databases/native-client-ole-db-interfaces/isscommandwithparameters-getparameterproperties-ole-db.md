---
title: ISSCommandWithParameters::GetParameterProperties (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSCommandWithParameters::GetParameterProperties (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- GetParameterProperties method
ms.assetid: 7f4cc5ea-d028-4fe5-9192-bd153ab3c26c
author: rothja
ms.author: jroth
ms.openlocfilehash: 2160c93748375a4aa3bee3d530d441182204134a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657751"
---
# <a name="isscommandwithparametersgetparameterproperties-ole-db"></a><span data-ttu-id="41437-102">ISSCommandWithParameters::GetParameterProperties (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="41437-102">ISSCommandWithParameters::GetParameterProperties (OLE DB)</span></span>
  <span data-ttu-id="41437-103">Возвращает массив структур SSPARAMPROPS, представляющих собой множества свойств, по одному множеству свойств SSPARAMPROPS на каждый параметр определяемого пользователем типа или XML.</span><span class="sxs-lookup"><span data-stu-id="41437-103">Returns an array of SSPARAMPROPS property set structures, one SSPARAMPROPS property set for each UDT or XML parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41437-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41437-104">Syntax</span></span>  
  
```  
  
HRESULT GetParameterProperties(  
DB_UPARAMS *pcParams,  
SSPARAMPROPS **prgParamProperties);  
```  
  
## <a name="arguments"></a><span data-ttu-id="41437-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="41437-105">Arguments</span></span>  
 <span data-ttu-id="41437-106">*pcParams*[out][in]</span><span class="sxs-lookup"><span data-stu-id="41437-106">*pcParams*[out][in]</span></span>  
 <span data-ttu-id="41437-107">Указатель на область памяти, где содержится количество структур SSPARAMPROPS, возвращаемых в параметре *prgParamProperties*.</span><span class="sxs-lookup"><span data-stu-id="41437-107">A pointer to memory that contains the number of SSPARAMPROPS structures returned in *prgParamProperties*.</span></span>  
  
 <span data-ttu-id="41437-108">*prgParamProperties*[out]</span><span class="sxs-lookup"><span data-stu-id="41437-108">*prgParamProperties*[out]</span></span>  
 <span data-ttu-id="41437-109">Указатель на область памяти, в которую будет возвращен массив структур SSPARAMPROPS.</span><span class="sxs-lookup"><span data-stu-id="41437-109">A pointer to memory in which an array of SSPARAMPROPS structures is returned.</span></span> <span data-ttu-id="41437-110">Поставщик выделяет память для структур и возвращает адрес в эту память. Потребитель освобождает эту память с помощью **unalloc:: Free** , если она больше не нуждается в структурах.</span><span class="sxs-lookup"><span data-stu-id="41437-110">The provider allocates memory for the structures and returns the address to this memory; the consumer releases this memory with **IMalloc::Free** when it no longer needs the structures.</span></span> <span data-ttu-id="41437-111">Перед вызовом метода **unalloc:: Free** для *пргпарампропертиес*потребитель должен также вызвать **вариантклеар** для свойства *управляемое vValue* каждой структуры DBPROP, чтобы предотвратить утечку памяти в случаях, когда вариант содержит ссылочный тип (например, BSTR). Если *пкпарамс* имеет нулевое значение на выходе или возникает ошибка, отличная от DB_E_ERRORSOCCURRED, поставщик не выделяет память и гарантирует, что *пргпарампропертиес* является пустым указателем на выходе.</span><span class="sxs-lookup"><span data-stu-id="41437-111">Before calling **IMalloc::Free** for *prgParamProperties*, the consumer must also call **VariantClear** for the *vValue* property of each DBPROP structure in order to prevent a memory leak in cases where the variant contains a reference type (such as a BSTR.) If *pcParams* is zero on output or an error other than DB_E_ERRORSOCCURRED occurs, the provider does not allocate any memory and ensures that *prgParamProperties* is a null pointer on output.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="41437-112">Значения кода возврата</span><span class="sxs-lookup"><span data-stu-id="41437-112">Return Code Values</span></span>  
 <span data-ttu-id="41437-113">Метод **GetParameterProperties** возвращает те же коды ошибок, что и метод Core OLE DB **ICommandProperties::** , за исключением того, что DB_S_ERRORSOCCURRED и DB_E_ERRORSOCCURED не могут быть вызваны.</span><span class="sxs-lookup"><span data-stu-id="41437-113">The **GetParameterProperties** method returns the same error codes as the core OLE DB **ICommandProperties::GetProperties** method, except that DB_S_ERRORSOCCURRED and DB_E_ERRORSOCCURED cannot be raised.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41437-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="41437-114">Remarks</span></span>  
 <span data-ttu-id="41437-115">**ISSCommandWithParameters:: GetParameterProperties** действует согласованно с уважением **GetParameterInfo**.</span><span class="sxs-lookup"><span data-stu-id="41437-115">**ISSCommandWithParameters::GetParameterProperties** behaves consistently with respect to **GetParameterInfo**.</span></span> <span data-ttu-id="41437-116">Если [ISSCommandWithParameters:: SetParameterProperties](isscommandwithparameters-setparameterproperties-ole-db.md) или **SetParameterInfo** не были вызваны или вызваны с кпарамс равными нулю, **GetParameterInfo** наследует сведения о параметрах и возвращает this.</span><span class="sxs-lookup"><span data-stu-id="41437-116">If [ISSCommandWithParameters::SetParameterProperties](isscommandwithparameters-setparameterproperties-ole-db.md) or **SetParameterInfo** have not been called or have been called with cParams equal to zero, **GetParameterInfo** derives parameter information and returns this.</span></span> <span data-ttu-id="41437-117">Если **ISSCommandWithParameters:: SetParameterProperties** или **SetParameterInfo** были вызваны по крайней мере для одного параметра, **ISSCommandWithParameters:: GetParameterProperties** Возвращает свойства только для тех параметров, для которых был вызван **ISSCommandWithParameters:: SetParameterProperties** .</span><span class="sxs-lookup"><span data-stu-id="41437-117">If **ISSCommandWithParameters::SetParameterProperties** or **SetParameterInfo** have been called for at least one parameter, **ISSCommandWithParameters::GetParameterProperties** returns properties only for those parameters for which **ISSCommandWithParameters::SetParameterProperties** has been called.</span></span> <span data-ttu-id="41437-118">Если **ISSCommandWithParameters:: SetParameterProperties** вызывается после **ISSCommandWithParameters:: GetParameterProperties** или **GetParameterInfo**, последующие вызовы **ISSCommandWithParameters:: GetParameterProperties** возвращают переопределенные значения для этих параметров, для которых был вызван **ISSCommandWithParameters:: SetParameterProperties** .</span><span class="sxs-lookup"><span data-stu-id="41437-118">If **ISSCommandWithParameters::SetParameterProperties** is called after **ISSCommandWithParameters::GetParameterProperties** or **GetParameterInfo**, subsequent calls to **ISSCommandWithParameters::GetParameterProperties** return the overridden values for those parameters for which **ISSCommandWithParameters::SetParameterProperties** has been called.</span></span>  
  
 <span data-ttu-id="41437-119">Структура SSPARAMPROPS определена следующим образом.</span><span class="sxs-lookup"><span data-stu-id="41437-119">The SSPARAMPROPS structure is defined as follows:</span></span>  
  
 `struct SSPARAMPROPS {`  
  
 `DBORDINAL iOrdinal;`  
  
 `ULONG cPropertySets;`  
  
 `DBPROPSET *rgPropertySets;`  
  
 `};`  
  
|<span data-ttu-id="41437-120">Член</span><span class="sxs-lookup"><span data-stu-id="41437-120">Member</span></span>|<span data-ttu-id="41437-121">Описание</span><span class="sxs-lookup"><span data-stu-id="41437-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="41437-122">*iOrdinal*</span><span class="sxs-lookup"><span data-stu-id="41437-122">*iOrdinal*</span></span>|<span data-ttu-id="41437-123">Порядковый номер переданного параметра.</span><span class="sxs-lookup"><span data-stu-id="41437-123">The ordinal of the passed parameter.</span></span>|  
|<span data-ttu-id="41437-124">*cPropertySets*</span><span class="sxs-lookup"><span data-stu-id="41437-124">*cPropertySets*</span></span>|<span data-ttu-id="41437-125">Количество структур DBPROPSET в *rgPropertySets*.</span><span class="sxs-lookup"><span data-stu-id="41437-125">The number of DBPROPSET structures in *rgPropertySets*.</span></span>|  
|<span data-ttu-id="41437-126">*rgPropertySets*</span><span class="sxs-lookup"><span data-stu-id="41437-126">*rgPropertySets*</span></span>|<span data-ttu-id="41437-127">Указатель на буфер, в который будет возвращен массив структур DBPROPSET.</span><span class="sxs-lookup"><span data-stu-id="41437-127">A pointer to memory in which to return an array of DBPROPSET structures.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="41437-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="41437-128">See Also</span></span>  
 [<span data-ttu-id="41437-129">ISSCommandWithParameters (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="41437-129">ISSCommandWithParameters &#40;OLE DB&#41;</span></span>](isscommandwithparameters-ole-db.md)  
  
  
