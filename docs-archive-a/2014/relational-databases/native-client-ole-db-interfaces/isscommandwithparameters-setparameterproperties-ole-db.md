---
title: ISSCommandWithParameters::SetParameterProperties (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSCommandWithParameters::SetParameterProperties (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- SetParameterProperties method
ms.assetid: 4cd0281a-a2a0-43df-8e46-eb478b64cb4b
author: rothja
ms.author: jroth
ms.openlocfilehash: 4bf8e5cde9885a5d9b55d84c6384b76aecf50b8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729434"
---
# <a name="isscommandwithparameterssetparameterproperties-ole-db"></a><span data-ttu-id="602eb-102">ISSCommandWithParameters::SetParameterProperties (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="602eb-102">ISSCommandWithParameters::SetParameterProperties (OLE DB)</span></span>
  <span data-ttu-id="602eb-103">Задает свойства каждого параметра по порядковому номеру или задает массовые свойства параметра, указывая массив структур SSPARAMPROPS.</span><span class="sxs-lookup"><span data-stu-id="602eb-103">Sets the parameter properties on a per parameter basis by ordinal, or sets bulk parameter properties by specifying an array of SSPARAMPROPS structures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="602eb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="602eb-104">Syntax</span></span>  
  
```  
  
HRESULT SetParameterProperties(  
DB_UPARAMS cParams,   
SSPARAMPROPS rgParamProperties[]);  
```  
  
## <a name="arguments"></a><span data-ttu-id="602eb-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="602eb-105">Arguments</span></span>  
 <span data-ttu-id="602eb-106">*cParams*[in]</span><span class="sxs-lookup"><span data-stu-id="602eb-106">*cParams*[in]</span></span>  
 <span data-ttu-id="602eb-107">Количество структур SSPARAMPROPS в массиве *rgParamProperties*.</span><span class="sxs-lookup"><span data-stu-id="602eb-107">The number of SSPARAMPROPS structures in the *rgParamProperties* array.</span></span> <span data-ttu-id="602eb-108">Если это число равно нулю, `ISSCommandWithParameters::SetParameterProperties` то удаляет все свойства, которые могли быть указаны для любых параметров в команде.</span><span class="sxs-lookup"><span data-stu-id="602eb-108">If this number is zero, `ISSCommandWithParameters::SetParameterProperties` will delete all properties that might have been specified for any parameters in the command.</span></span>  
  
 <span data-ttu-id="602eb-109">*rgParamProperties*[in]</span><span class="sxs-lookup"><span data-stu-id="602eb-109">*rgParamProperties*[in]</span></span>  
 <span data-ttu-id="602eb-110">Массив задаваемых структур SSPARAMPROPS.</span><span class="sxs-lookup"><span data-stu-id="602eb-110">An array of SSPARAMPROPS structures to be set.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="602eb-111">Значения кода возврата</span><span class="sxs-lookup"><span data-stu-id="602eb-111">Return Code Values</span></span>  
 <span data-ttu-id="602eb-112">`ISSCommandWithParameters::SetParameterProperties`Метод возвращает те же коды ошибок, что и метод core OLE DB **ICommandProperties:: SetProperties** .</span><span class="sxs-lookup"><span data-stu-id="602eb-112">The `ISSCommandWithParameters::SetParameterProperties` method returns the same error codes as the core OLE DB **ICommandProperties::SetProperties** method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="602eb-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="602eb-113">Remarks</span></span>  
 <span data-ttu-id="602eb-114">Задание свойств параметра с помощью этого метода допускается для каждого параметра по порядковому номеру или с помощью одного `ISSCommandWithParameters::SetParameterProperties` вызова после того, как SSPARAMPROPS был построен из массива свойств.</span><span class="sxs-lookup"><span data-stu-id="602eb-114">Setting parameter properties with this method is allowed on a per parameter basis by ordinal, or with a single `ISSCommandWithParameters::SetParameterProperties` call once the SSPARAMPROPS has been built from the property array.</span></span>  
  
 <span data-ttu-id="602eb-115">Перед вызовом метода необходимо вызвать метод **SetParameterInfo** `ISSCommandWithParameters::SetParameterProperties` .</span><span class="sxs-lookup"><span data-stu-id="602eb-115">The **SetParameterInfo** method must be called before calling the `ISSCommandWithParameters::SetParameterProperties` method.</span></span> <span data-ttu-id="602eb-116">Вызов метода `SetParameterProperties(0, NULL)` очищает все указанные свойства параметра, тогда как вызов метода `SetParameterInfo(0,NULL,NULL)` очищает все сведения о параметре, в том числе все свойства, которые могут быть связаны с параметром.</span><span class="sxs-lookup"><span data-stu-id="602eb-116">Calling `SetParameterProperties(0, NULL)` clears all specified parameter properties, while calling `SetParameterInfo(0,NULL,NULL)` clears all the parameter info including any properties that might be associated with a parameter.</span></span>  
  
 <span data-ttu-id="602eb-117">Вызов `ISSCommandWithParameters::SetParameterProperties` для указания свойств параметра, который не относится к типу DBTYPE_XML или DBTYPE_UDT возвращает DB_E_ERRORSOCCURRED или DB_S_ERRORSOCCURRED и помечает поле *Dwstatus устанавливается* всех дбпропс, содержащихся в SSPARAMPROPS для этого параметра, с DBPROPSTATUS_NOTSET.</span><span class="sxs-lookup"><span data-stu-id="602eb-117">Calling `ISSCommandWithParameters::SetParameterProperties` to specify properties for a parameter which is not of type DBTYPE_XML or DBTYPE_UDT returns DB_E_ERRORSOCCURRED or DB_S_ERRORSOCCURRED and marks the *dwStatus* field of all DBPROPs contained in SSPARAMPROPS for that parameter with DBPROPSTATUS_NOTSET.</span></span> <span data-ttu-id="602eb-118">Чтобы обнаружить, к какому параметру относится DB_E_ERRORSOCCURRED или DB_S_ERRORSOCCURRED, необходимо пройти по массиву DBPROP каждого набора DBPROPSET, содержащегося в структуре SSPARAMPROPS.</span><span class="sxs-lookup"><span data-stu-id="602eb-118">The DBPROP array of each DBPROPSET contained in SSPARAMPROPS should be traversed to detect which parameter the DB_E_ERRORSOCCURRED or DB_S_ERRORSOCCURRED refers to.</span></span>  
  
 <span data-ttu-id="602eb-119">Если `ISSCommandWithParameters::SetParameterProperties` вызывается для указания свойств параметров, сведения о параметрах которых еще не заданы с помощью **SetParameterInfo**, поставщик возвращает E_UNEXPECTED со следующим сообщением об ошибке:</span><span class="sxs-lookup"><span data-stu-id="602eb-119">If `ISSCommandWithParameters::SetParameterProperties` is called to specify the properties of parameters whose parameter info have not been set yet with **SetParameterInfo**, the provider returns E_UNEXPECTED with the following error message:</span></span>  
  
 <span data-ttu-id="602eb-120">Невозможно вызвать метод SetParameterProperties для указанных параметров, не вызывая предварительно метод SetParameterInfo.</span><span class="sxs-lookup"><span data-stu-id="602eb-120">SetParameterProperties method cannot be called for the specified parameters without first calling SetParameterInfo method.</span></span> <span data-ttu-id="602eb-121">До задания свойств параметров необходимо задать сведения о параметрах.</span><span class="sxs-lookup"><span data-stu-id="602eb-121">The parameter information must be set before setting the parameter properties.</span></span>  
  
 <span data-ttu-id="602eb-122">Если вызов `ISSCommandWithParameters::SetParameterProperties` содержит некоторые параметры, в которых заданы сведения о параметрах, и некоторые параметры, в которых не заданы сведения о параметрах, свойства dwstatus устанавливается в DBPROPSET набора свойств SSPARAMPROPS будут возвращаться с DBSTATUS_NOTSET.</span><span class="sxs-lookup"><span data-stu-id="602eb-122">If the call to `ISSCommandWithParameters::SetParameterProperties` contains some parameters where the parameter info has been set, and some parameters where the parameter info has not been set, the dwStatus properties in the DBPROPSET of the SSPARAMPROPS property set will return with DBSTATUS_NOTSET.</span></span>  
  
 <span data-ttu-id="602eb-123">Структура SSPARAMPROPS определена следующим образом.</span><span class="sxs-lookup"><span data-stu-id="602eb-123">The SSPARAMPROPS structure is defined as follows:</span></span>  
  
 `struct SSPARAMPROPS {`  
  
 `DBORDINAL iOrdinal;`  
  
 `ULONG cPropertySets;`  
  
 `DBPROPSET *rgPropertySets;`  
  
 `};`  
  
 <span data-ttu-id="602eb-124">Улучшения ядра СУБД, появившиеся с версии [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], позволяют методу ISSCommandWithParameters::SetParameterProperties получать более точные описания ожидаемых результатов.</span><span class="sxs-lookup"><span data-stu-id="602eb-124">Improvements in the database engine starting with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] allow ISSCommandWithParameters::SetParameterProperties to obtain more accurate descriptions of the expected results.</span></span> <span data-ttu-id="602eb-125">Эти более точные результаты могут отличаться от значений, которые метод ISSCommandWithParameters::SetParameterProperties возвращает в предыдущих версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="602eb-125">These more accurate results may differ from the values returned by ISSCommandWithParameters::SetParameterProperties in previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="602eb-126">Дополнительные сведения см. в разделе [Обнаружение метаданных](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="602eb-126">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
|<span data-ttu-id="602eb-127">Член</span><span class="sxs-lookup"><span data-stu-id="602eb-127">Member</span></span>|<span data-ttu-id="602eb-128">Описание</span><span class="sxs-lookup"><span data-stu-id="602eb-128">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="602eb-129">*iOrdinal*</span><span class="sxs-lookup"><span data-stu-id="602eb-129">*iOrdinal*</span></span>|<span data-ttu-id="602eb-130">Порядковый номер переданного параметра.</span><span class="sxs-lookup"><span data-stu-id="602eb-130">The ordinal of the passed parameter.</span></span>|  
|<span data-ttu-id="602eb-131">*cPropertySets*</span><span class="sxs-lookup"><span data-stu-id="602eb-131">*cPropertySets*</span></span>|<span data-ttu-id="602eb-132">Количество структур DBPROPSET в *rgPropertySets*.</span><span class="sxs-lookup"><span data-stu-id="602eb-132">The number of DBPROPSET structures in *rgPropertySets*.</span></span>|  
|<span data-ttu-id="602eb-133">*rgPropertySets*</span><span class="sxs-lookup"><span data-stu-id="602eb-133">*rgPropertySets*</span></span>|<span data-ttu-id="602eb-134">Указатель на буфер, в который будет возвращен массив структур DBPROPSET.</span><span class="sxs-lookup"><span data-stu-id="602eb-134">A pointer to memory in which to return an array of DBPROPSET structures.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="602eb-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="602eb-135">See Also</span></span>  
 [<span data-ttu-id="602eb-136">ISSCommandWithParameters (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="602eb-136">ISSCommandWithParameters &#40;OLE DB&#41;</span></span>](isscommandwithparameters-ole-db.md)  
  
  
