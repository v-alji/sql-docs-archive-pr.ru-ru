---
title: Метод SetFlag (класс класс clientnetworkprotocolproperty) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetFlag Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetFlag method
ms.assetid: 0407520f-2f84-4f68-b2b7-429697286c1b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1c83a1d647b62f0e5c5acf0659d54bf787bf0c96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738138"
---
# <a name="setflag-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="8fc39-102">Метод SetFlag (класс ClientNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="8fc39-102">SetFlag Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="8fc39-103">Задает флаг текущего свойства, на которое ссылается значение [свойства PropertyIdx (класс ClientNetworkProtocolProperty)](clientnetworkprotocolproperty-class.md) .</span><span class="sxs-lookup"><span data-stu-id="8fc39-103">Sets the flag of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fc39-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8fc39-104">Syntax</span></span>  
  
```  
  
object  
.SetFlag(  
BoolValue  
) [=]  
```  
  
## <a name="parts"></a><span data-ttu-id="8fc39-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="8fc39-105">Parts</span></span>  
 <span data-ttu-id="8fc39-106">*object*</span><span class="sxs-lookup"><span data-stu-id="8fc39-106">*object*</span></span>  
 <span data-ttu-id="8fc39-107">A [класса ClientNetworkProtocolProperty](clientnetworkprotocolproperty-class.md) , который представляет атрибут сетевого протокола, используемого [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8fc39-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="8fc39-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="8fc39-108">Parameters</span></span>  
  
|<span data-ttu-id="8fc39-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="8fc39-109">Parameter</span></span>|<span data-ttu-id="8fc39-110">Описание</span><span class="sxs-lookup"><span data-stu-id="8fc39-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8fc39-111">*булвалуе*</span><span class="sxs-lookup"><span data-stu-id="8fc39-111">*BoolValue*</span></span>|<span data-ttu-id="8fc39-112">Логическое значение, указывающее новое состояние флага.</span><span class="sxs-lookup"><span data-stu-id="8fc39-112">A Boolean value that specifies the new value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="8fc39-113">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8fc39-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="8fc39-114">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="8fc39-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fc39-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="8fc39-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fc39-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="8fc39-116">See Also</span></span>  
 [<span data-ttu-id="8fc39-117">Настройка клиентских протоколов</span><span class="sxs-lookup"><span data-stu-id="8fc39-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
