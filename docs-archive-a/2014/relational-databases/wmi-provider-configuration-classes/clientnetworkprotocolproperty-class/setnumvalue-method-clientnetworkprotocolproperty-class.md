---
title: Метод SetNumValue (класс класс clientnetworkprotocolproperty) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumValue Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumValue method
ms.assetid: c292e2ae-6d0a-44ad-ba54-5b0bd705ef37
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 82a5474c2330d0d5bc0ed8766614773ceb899bf9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664079"
---
# <a name="setnumvalue-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="5db06-102">Метод SetNumValue (класс ClientNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="5db06-102">SetNumValue Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="5db06-103">Задает числовое значение текущего свойства, на которое ссылается значение [свойства PropertyIdx (класс ClientNetworkProtocolProperty)](clientnetworkprotocolproperty-class.md) .</span><span class="sxs-lookup"><span data-stu-id="5db06-103">Sets the numeric value of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5db06-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5db06-104">Syntax</span></span>  
  
```  
  
object  
.SetNumValue [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="5db06-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="5db06-105">Parts</span></span>  
 <span data-ttu-id="5db06-106">*object*</span><span class="sxs-lookup"><span data-stu-id="5db06-106">*object*</span></span>  
 <span data-ttu-id="5db06-107">A [класса ClientNetworkProtocolProperty](clientnetworkprotocolproperty-class.md) , который представляет атрибут сетевого протокола, используемого [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5db06-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="5db06-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="5db06-108">Parameters</span></span>  
  
|<span data-ttu-id="5db06-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="5db06-109">Parameter</span></span>|<span data-ttu-id="5db06-110">Описание</span><span class="sxs-lookup"><span data-stu-id="5db06-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5db06-111">*value*</span><span class="sxs-lookup"><span data-stu-id="5db06-111">*value*</span></span>|<span data-ttu-id="5db06-112">Объект `uint32`, указывающий числовое значение упоминаемого свойства.</span><span class="sxs-lookup"><span data-stu-id="5db06-112">A `uint32` value that specifies the numeric value of the referenced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="5db06-113">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5db06-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="5db06-114">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="5db06-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5db06-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="5db06-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5db06-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="5db06-116">See Also</span></span>  
 [<span data-ttu-id="5db06-117">Настройка клиентских протоколов</span><span class="sxs-lookup"><span data-stu-id="5db06-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
