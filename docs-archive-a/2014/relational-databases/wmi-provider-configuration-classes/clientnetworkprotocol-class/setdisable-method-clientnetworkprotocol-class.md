---
title: Метод SetDisable (класс класс clientnetworkprotocol) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDisable Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDisable method
ms.assetid: bce69ab9-ea5b-43fd-8114-08b1b5890755
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 2bad312f1f7c7e9540acdaf3dd46df78b953d4ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669318"
---
# <a name="setdisable-method-clientnetworkprotocol-class"></a><span data-ttu-id="a7a00-102">Метод SetDisable (класс ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="a7a00-102">SetDisable Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="a7a00-103">Отключает сетевой протокол клиента, указанный в параметре [Настройка клиентских протоколов](https://technet.microsoft.com/library/ms181035.aspx).</span><span class="sxs-lookup"><span data-stu-id="a7a00-103">Disables the client network protocol that is specified by the [Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7a00-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7a00-104">Syntax</span></span>  
  
```  
  
object  
.SetDisable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="a7a00-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="a7a00-105">Parts</span></span>  
 <span data-ttu-id="a7a00-106">*object*</span><span class="sxs-lookup"><span data-stu-id="a7a00-106">*object*</span></span>  
 <span data-ttu-id="a7a00-107">A [класса ClientNetworkProtocol](clientnetworkprotocol-class.md) , который представляет сетевой протокол, используемый клиентом [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a7a00-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="a7a00-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a7a00-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="a7a00-109">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="a7a00-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7a00-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="a7a00-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7a00-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7a00-111">See Also</span></span>  
 [<span data-ttu-id="a7a00-112">Настройка сетевых протоколов клиента и сетевых библиотек</span><span class="sxs-lookup"><span data-stu-id="a7a00-112">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
