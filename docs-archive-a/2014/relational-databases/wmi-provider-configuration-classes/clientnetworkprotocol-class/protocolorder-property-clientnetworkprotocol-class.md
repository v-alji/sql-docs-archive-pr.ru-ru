---
title: Свойство ProtocolOrder (класс класс clientnetworkprotocol) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ProtocolOrder Property (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ProtocolOrder property
ms.assetid: aa09b8ab-37db-4406-8973-acf503855fd2
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8bccb7109972dea4697e9e289081cbf47d2f9492
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668714"
---
# <a name="protocolorder-property-clientnetworkprotocol-class"></a><span data-ttu-id="a2446-102">Свойство ProtocolOrder (класс ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="a2446-102">ProtocolOrder Property (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="a2446-103">Возвращает порядковый номер текущего указанного сетевого протокола клиента, заданного методом [SetOrderValue (класс ClientNetworkProtocol)](clientnetworkprotocol-class.md) .</span><span class="sxs-lookup"><span data-stu-id="a2446-103">Gets the order number of the currently referenced client network protocol as specified by the [SetOrderValue Method (ClientNetworkProtocol Class)](clientnetworkprotocol-class.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2446-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2446-104">Syntax</span></span>  
  
```  
  
object  
.ProtocolOrder [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="a2446-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="a2446-105">Parts</span></span>  
 <span data-ttu-id="a2446-106">*object*</span><span class="sxs-lookup"><span data-stu-id="a2446-106">*object*</span></span>  
 <span data-ttu-id="a2446-107">A [класса ClientNetworkProtocol](clientnetworkprotocol-class.md) , который представляет сетевой протокол, используемый клиентом [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a2446-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="a2446-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a2446-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="a2446-109">Значение `uint32`, определяющее порядковый номер текущего указанного сетевого протокола клиента, заданного методом `OrderValue`.</span><span class="sxs-lookup"><span data-stu-id="a2446-109">A `uint32` value that specifies the order number of the currently referenced client network protocol as set by the `OrderValue` method.</span></span> <span data-ttu-id="a2446-110">Если сетевой протокол клиента отключен, это значение будет равно нулю.</span><span class="sxs-lookup"><span data-stu-id="a2446-110">If the client network protocol is disabled, this value will be zero.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2446-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="a2446-111">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2446-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="a2446-112">See Also</span></span>  
 <span data-ttu-id="a2446-113">[Настройка клиентских протоколов](https://technet.microsoft.com/library/ms181035.aspx) </span><span class="sxs-lookup"><span data-stu-id="a2446-113">[Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx) </span></span>  
 [<span data-ttu-id="a2446-114">Настройка сетевых протоколов клиента и сетевых библиотек</span><span class="sxs-lookup"><span data-stu-id="a2446-114">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
