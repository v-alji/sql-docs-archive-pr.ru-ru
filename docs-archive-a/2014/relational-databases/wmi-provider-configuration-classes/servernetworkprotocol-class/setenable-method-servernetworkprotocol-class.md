---
title: Метод SetEnable (класс класс servernetworkprotocol) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetEnable Method (ServerNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEnable method
ms.assetid: a287950b-086f-4b6d-a2d8-4d3973bd1b21
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8f77b7a92fe226e349a03ffba03cfe8d67c280e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657607"
---
# <a name="setenable-method-servernetworkprotocol-class"></a><span data-ttu-id="732cb-102">Метод SetEnable (класс ServerNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="732cb-102">SetEnable Method (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="732cb-103">Задействует сетевой протокол сервера.</span><span class="sxs-lookup"><span data-stu-id="732cb-103">Enables the server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="732cb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="732cb-104">Syntax</span></span>  
  
```  
  
object  
.SetEnable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="732cb-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="732cb-105">Parts</span></span>  
 <span data-ttu-id="732cb-106">*object*</span><span class="sxs-lookup"><span data-stu-id="732cb-106">*object*</span></span>  
 <span data-ttu-id="732cb-107">A [класса ServerNetworkProtocol](servernetworkprotocol-class.md) , который представляет сетевой протокол, используемый экземпляром [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="732cb-107">A [ServerNetworkProtocol Class](servernetworkprotocol-class.md) object that represents the network protocol used by the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="732cb-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="732cb-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="732cb-109">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="732cb-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="732cb-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="732cb-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="732cb-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="732cb-111">See Also</span></span>  
 <span data-ttu-id="732cb-112">[Конфигурирование сетевых протоколов сервера и сетевых библиотек](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="732cb-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
