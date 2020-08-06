---
title: Свойство MultiIpConfigurationSupport (класс класс servernetworkprotocol) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- MultiIpConfigurationSupport Property (ServerNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- MultiIpConfigurationSupport property
ms.assetid: 442c6133-4038-42db-a67d-2631285ac76b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 80401a607c9155451a869082162affcca401ebca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654083"
---
# <a name="multiipconfigurationsupport-property-servernetworkprotocol-class"></a><span data-ttu-id="8b8e5-102">Свойство MultiIpConfigurationSupport (класс ServerNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="8b8e5-102">MultiIpConfigurationSupport Property (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="8b8e5-103">Возвращает логическое свойство, определяющее, поддерживаются ли несколько IP-адресов сетевым протоколом сервера.</span><span class="sxs-lookup"><span data-stu-id="8b8e5-103">Gets the Boolean property that specifies whether multiple IP addresses are supported by a server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b8e5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b8e5-104">Syntax</span></span>  
  
```  
  
object  
.MultiIpConfigurationSupport [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="8b8e5-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="8b8e5-105">Parts</span></span>  
 <span data-ttu-id="8b8e5-106">*object*</span><span class="sxs-lookup"><span data-stu-id="8b8e5-106">*object*</span></span>  
 <span data-ttu-id="8b8e5-107">Объект [Свойства ProtocolName (класс класс servernetworkprotocol)](servernetworkprotocol-class.md) , представляющий сетевой протокол, используемый экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8b8e5-107">A [ProtocolName Property (ServerNetworkProtocol Class)](servernetworkprotocol-class.md) object that represents the network protocol used by the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="8b8e5-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8b8e5-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="8b8e5-109">Логическое значение, определяющее, поддерживает ли сетевой протокол сервера несколько IP-адресов: `true`, если поддерживает; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="8b8e5-109">A Boolean value that specifies whether multiple IP addresses are supported by the server network protocol: `true` if multiple IP addresses are supported by the server network protocol, or `false` if multiple IP addresses are not supported by the server network protocol.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b8e5-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="8b8e5-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b8e5-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="8b8e5-111">See Also</span></span>  
 <span data-ttu-id="8b8e5-112">[Конфигурирование сетевых протоколов сервера и сетевых библиотек](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="8b8e5-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
