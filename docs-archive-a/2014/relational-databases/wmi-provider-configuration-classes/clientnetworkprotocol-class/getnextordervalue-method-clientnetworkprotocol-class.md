---
title: Метод GetNextOrderValue (класс класс clientnetworkprotocol) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetNextOrderValue Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetNextOrderValue method
ms.assetid: d741dc5c-c225-43d9-a730-7ad664ac525f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: bdc3eecd9e151d7da32a5fd65a90552c0743b3d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669323"
---
# <a name="getnextordervalue-method-clientnetworkprotocol-class"></a><span data-ttu-id="eb292-102">Метод GetNextOrderValue (класс ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="eb292-102">GetNextOrderValue Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="eb292-103">Выбирает следующий протокол в списке протоколов.</span><span class="sxs-lookup"><span data-stu-id="eb292-103">Selects the protocol that is in the next position in the list of protocols.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb292-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb292-104">Syntax</span></span>  
  
```  
  
object  
.GetNextOrderValue()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="eb292-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="eb292-105">Parts</span></span>  
 <span data-ttu-id="eb292-106">*object*</span><span class="sxs-lookup"><span data-stu-id="eb292-106">*object*</span></span>  
 <span data-ttu-id="eb292-107">A [класса ClientNetworkProtocol](clientnetworkprotocol-class.md) , который представляет сетевой протокол, используемый клиентом [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eb292-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="eb292-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="eb292-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="eb292-109">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="eb292-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb292-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="eb292-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb292-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="eb292-111">See Also</span></span>  
 <span data-ttu-id="eb292-112">[Настройка клиентских протоколов](https://technet.microsoft.com/library/ms181035.aspx) </span><span class="sxs-lookup"><span data-stu-id="eb292-112">[Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx) </span></span>  
 [<span data-ttu-id="eb292-113">Настройка сетевых протоколов клиента и сетевых библиотек</span><span class="sxs-lookup"><span data-stu-id="eb292-113">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
