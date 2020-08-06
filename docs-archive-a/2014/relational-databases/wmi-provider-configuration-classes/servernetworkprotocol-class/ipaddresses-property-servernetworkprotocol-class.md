---
title: Свойство IpAddresses (класс класс servernetworkprotocol) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- IpAddresses Property (ServerNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- IpAddresses property
ms.assetid: e5d66f7e-9719-436e-b723-12d56f914a05
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b94c4c11327abc1f02bd1e99c414f806f75bc145
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654084"
---
# <a name="ipaddresses-property-servernetworkprotocol-class"></a><span data-ttu-id="6f0b8-102">Свойство IpAddresses (класс ServerNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="6f0b8-102">IpAddresses Property (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="6f0b8-103">Возвращает IP-адреса, связанные с сетевым протоколом сервера.</span><span class="sxs-lookup"><span data-stu-id="6f0b8-103">Gets the IP addresses associated with the server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f0b8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f0b8-104">Syntax</span></span>  
  
```  
  
object  
.IpAddresses [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="6f0b8-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="6f0b8-105">Parts</span></span>  
 <span data-ttu-id="6f0b8-106">*object*</span><span class="sxs-lookup"><span data-stu-id="6f0b8-106">*object*</span></span>  
 <span data-ttu-id="6f0b8-107">`ServerNetworkProtocol`Объект, представляющий сетевой протокол, используемый экземпляром [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6f0b8-107">A `ServerNetworkProtocol` object that represents the network protocol used by the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="6f0b8-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6f0b8-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="6f0b8-109">Массив объектов [класса объект servernetworkprotocolipadress](../servernetworkprotocolipaddress-class/servernetworkprotocolipaddress-class.md) , ПРЕДСТАВЛЯЮЩИХ IP-адреса, поддерживаемые сетевым протоколом сервера.</span><span class="sxs-lookup"><span data-stu-id="6f0b8-109">An array of [ServerNetworkProtocolIPAdress Class](../servernetworkprotocolipaddress-class/servernetworkprotocolipaddress-class.md) objects that represent the IP addresses supported by the server network protocol.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f0b8-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="6f0b8-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f0b8-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="6f0b8-111">See Also</span></span>  
 <span data-ttu-id="6f0b8-112">[Конфигурирование сетевых протоколов сервера и сетевых библиотек](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="6f0b8-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
