---
title: Метод SetStrValue (класс класс clientnetworkprotocolproperty) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStrValue Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStrValue method
ms.assetid: 4ff80124-6e2e-4d96-a692-57c17b53c55e
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f3c23eebdbe948e1b77c47ef56a04691fa391938
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749660"
---
# <a name="setstrvalue-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="01489-102">Метод SetStrValue (класс ClientNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="01489-102">SetStrValue Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="01489-103">Задает строковое значение текущего свойства, на которое ссылается значение [свойства PropertyIdx (класс ClientNetworkProtocolProperty)](clientnetworkprotocolproperty-class.md) .</span><span class="sxs-lookup"><span data-stu-id="01489-103">Sets the string value of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01489-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01489-104">Syntax</span></span>  
  
```  
  
object  
.SetStrValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="01489-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="01489-105">Parts</span></span>  
 <span data-ttu-id="01489-106">*object*</span><span class="sxs-lookup"><span data-stu-id="01489-106">*object*</span></span>  
 <span data-ttu-id="01489-107">A [класса ClientNetworkProtocolProperty](clientnetworkprotocolproperty-class.md) , который представляет атрибут сетевого протокола, используемого [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="01489-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="01489-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="01489-108">Parameters</span></span>  
  
|<span data-ttu-id="01489-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="01489-109">Parameter</span></span>|<span data-ttu-id="01489-110">Описание</span><span class="sxs-lookup"><span data-stu-id="01489-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="01489-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="01489-111">*StrValue*</span></span>|<span data-ttu-id="01489-112">Строка, указывающая новое значение текущего свойства.</span><span class="sxs-lookup"><span data-stu-id="01489-112">A string value that specifies the new value of the current property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="01489-113">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="01489-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="01489-114">Значение uint32, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="01489-114">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01489-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="01489-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01489-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="01489-116">See Also</span></span>  
 [<span data-ttu-id="01489-117">Настройка клиентских протоколов</span><span class="sxs-lookup"><span data-stu-id="01489-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
