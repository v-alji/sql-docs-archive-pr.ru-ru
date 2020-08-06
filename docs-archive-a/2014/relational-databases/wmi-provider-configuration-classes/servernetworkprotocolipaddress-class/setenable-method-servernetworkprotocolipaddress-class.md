---
title: Метод SetEnable (класс класс servernetworkprotocolipaddress) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetEnable Method (ServerNetworkProtocolIPAddress Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEnable method
ms.assetid: baa86deb-95dd-416f-b2c7-cec1dfb91ab4
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5be9c30acacaedba320fd68363e531b178918271
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665248"
---
# <a name="setenable-method-servernetworkprotocolipaddress-class"></a><span data-ttu-id="4b2da-102">Метод SetEnable (класс ServerNetworkProtocolIPAddress)</span><span class="sxs-lookup"><span data-stu-id="4b2da-102">SetEnable Method (ServerNetworkProtocolIPAddress Class)</span></span>
  <span data-ttu-id="4b2da-103">Задействует IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="4b2da-103">Enables the IP address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b2da-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b2da-104">Syntax</span></span>  
  
```  
  
object  
.SetEnable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="4b2da-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="4b2da-105">Parts</span></span>  
 <span data-ttu-id="4b2da-106">*object*</span><span class="sxs-lookup"><span data-stu-id="4b2da-106">*object*</span></span>  
 <span data-ttu-id="4b2da-107">A [класса ServerNetworkProtocolIPAdress](servernetworkprotocolipaddress-class.md) , который представляет IP-адрес сетевого протокола для экземпляра [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b2da-107">A [ServerNetworkProtocolIPAdress Class](servernetworkprotocolipaddress-class.md) object that represents an IP address for the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="4b2da-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4b2da-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="4b2da-109">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="4b2da-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b2da-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="4b2da-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b2da-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="4b2da-111">See Also</span></span>  
 <span data-ttu-id="4b2da-112">[Конфигурирование сетевых протоколов сервера и сетевых библиотек](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="4b2da-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
