---
title: Метод SetOrderValue (класс класс clientnetworkprotocol) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetOrderValue Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetOrderValue method
ms.assetid: 15f693fd-37f6-41d9-9dab-d2c93db19895
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6839e85b6131c54e233d980c84a8727eeda2202a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668713"
---
# <a name="setordervalue-method-clientnetworkprotocol-class"></a><span data-ttu-id="d6981-102">Метод SetOrderValue (класс ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="d6981-102">SetOrderValue Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="d6981-103">Выбирает протокол с заданным порядковым значением из списка клиентских протоколов.</span><span class="sxs-lookup"><span data-stu-id="d6981-103">Selects the protocol with the specified order value from the client protocol list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6981-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d6981-104">Syntax</span></span>  
  
```  
  
object  
.SetOrderValue(  
OrderValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="d6981-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="d6981-105">Parts</span></span>  
 <span data-ttu-id="d6981-106">*object*</span><span class="sxs-lookup"><span data-stu-id="d6981-106">*object*</span></span>  
 <span data-ttu-id="d6981-107">A [класса ClientNetworkProtocol](clientnetworkprotocol-class.md) , который представляет сетевой протокол, используемый клиентом [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6981-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="d6981-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="d6981-108">Parameters</span></span>  
  
|<span data-ttu-id="d6981-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="d6981-109">Parameter</span></span>|<span data-ttu-id="d6981-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d6981-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d6981-111">*OrderValue*</span><span class="sxs-lookup"><span data-stu-id="d6981-111">*OrderValue*</span></span>|<span data-ttu-id="d6981-112">Значение u`int32`, задающее порядковый номер.</span><span class="sxs-lookup"><span data-stu-id="d6981-112">A u`int32` value that sets the order value.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d6981-113">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d6981-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="d6981-114">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="d6981-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6981-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="d6981-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6981-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="d6981-116">See Also</span></span>  
 [<span data-ttu-id="d6981-117">Свойства клиентских протоколов (вкладка «Порядок»)</span><span class="sxs-lookup"><span data-stu-id="d6981-117">Client Protocols Properties (Order Tab)</span></span>](https://technet.microsoft.com/library/ms187884.aspx)  
  
  
