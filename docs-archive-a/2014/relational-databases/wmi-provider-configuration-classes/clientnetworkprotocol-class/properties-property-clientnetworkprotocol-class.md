---
title: Свойство Properties (класс класс clientnetworkprotocol) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- Properties Property (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- Properties property
ms.assetid: 7e0a4e38-4555-4750-8fd3-4425b29e6aa1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 09836db1f510ac77635924c51e5341686627d54d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669321"
---
# <a name="properties-property-clientnetworkprotocol-class"></a><span data-ttu-id="ecad6-102">Свойство Properties (класс ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="ecad6-102">Properties Property (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="ecad6-103">Возвращает свойства, связанные с текущим сетевым протоколом клиента, заданным в параметре [Настройка клиентских протоколов](https://technet.microsoft.com/library/ms181035.aspx).</span><span class="sxs-lookup"><span data-stu-id="ecad6-103">Gets the properties associated with the current client network protocol specified by the [Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecad6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ecad6-104">Syntax</span></span>  
  
```  
  
object  
.Properties [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="ecad6-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="ecad6-105">Parts</span></span>  
 <span data-ttu-id="ecad6-106">*object*</span><span class="sxs-lookup"><span data-stu-id="ecad6-106">*object*</span></span>  
 <span data-ttu-id="ecad6-107">A [класса ClientNetworkProtocol](clientnetworkprotocol-class.md) , который представляет сетевой протокол, используемый клиентом [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ecad6-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ecad6-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ecad6-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="ecad6-109">Массив объектов [класса класс clientnetworkprotocolproperty](../clientnetworkprotocolproperty-class/clientnetworkprotocolproperty-class.md) , представляющих свойства, поддерживаемые текущим сетевым протоколом клиента, на который ссылается `OrderValue` свойство.</span><span class="sxs-lookup"><span data-stu-id="ecad6-109">An array of [ClientNetworkProtocolProperty Class](../clientnetworkprotocolproperty-class/clientnetworkprotocolproperty-class.md) objects that represent the properties supported by the current client network protocol that is referenced by the `OrderValue` property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecad6-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="ecad6-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecad6-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="ecad6-111">See Also</span></span>  
 [<span data-ttu-id="ecad6-112">Настройка сетевых протоколов клиента и сетевых библиотек</span><span class="sxs-lookup"><span data-stu-id="ecad6-112">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
