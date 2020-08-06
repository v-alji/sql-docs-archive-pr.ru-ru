---
title: Метод SetProtocolsOrder (класс класс clientnetworkprotocol) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetProtocolsOrder Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetProtocolsOrder method
ms.assetid: b86d98b9-aae4-4e74-b4da-1ec984d5c8b4
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: aaa1d43c8a2f7f210f61761b28313a93ac6c7a90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668709"
---
# <a name="setprotocolsorder-method-clientnetworkprotocol-class"></a><span data-ttu-id="46213-102">Метод SetProtocolsOrder (класс ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="46213-102">SetProtocolsOrder Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="46213-103">Меняет порядок протоколов в списке.</span><span class="sxs-lookup"><span data-stu-id="46213-103">Changes the order of the protocol list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46213-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46213-104">Syntax</span></span>  
  
```  
  
object  
.SetProtocolsOrder(  
ProtocolOrderList  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="46213-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="46213-105">Parts</span></span>  
 <span data-ttu-id="46213-106">*object*</span><span class="sxs-lookup"><span data-stu-id="46213-106">*object*</span></span>  
 <span data-ttu-id="46213-107">A [класса ClientNetworkProtocol](clientnetworkprotocol-class.md) , который представляет сетевой протокол, используемый клиентом [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="46213-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="46213-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="46213-108">Parameters</span></span>  
  
|<span data-ttu-id="46213-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="46213-109">Parameter</span></span>|<span data-ttu-id="46213-110">Описание</span><span class="sxs-lookup"><span data-stu-id="46213-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="46213-111">*протоколордерлист*</span><span class="sxs-lookup"><span data-stu-id="46213-111">*ProtocolOrderList*</span></span>|<span data-ttu-id="46213-112">Массив значений string[], представляющий список сетевых протоколов клиента в новом порядке.</span><span class="sxs-lookup"><span data-stu-id="46213-112">A string[] array that lists the client network protocols in the new order.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="46213-113">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="46213-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="46213-114">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="46213-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46213-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="46213-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46213-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="46213-116">See Also</span></span>  
 <span data-ttu-id="46213-117">[Настройка клиентских протоколов](https://technet.microsoft.com/library/ms181035.aspx) </span><span class="sxs-lookup"><span data-stu-id="46213-117">[Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx) </span></span>  
 [<span data-ttu-id="46213-118">Настройка сетевых протоколов клиента и сетевых библиотек</span><span class="sxs-lookup"><span data-stu-id="46213-118">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
