---
title: Метод SetEnable (класс класс clientnetworkprotocol) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetEnable Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEnable method
ms.assetid: a66c756a-1311-4f4a-8088-818f8ed90056
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: dfba695506dd04ded82083b85bfbb751913fbcbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668116"
---
# <a name="setenable-method-clientnetworkprotocol-class"></a><span data-ttu-id="6ef7a-102">Метод SetEnable (класс ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="6ef7a-102">SetEnable Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="6ef7a-103">Включает сетевой протокол клиента, указанный в параметре [Настройка клиентских протоколов](https://technet.microsoft.com/library/ms181035.aspx).</span><span class="sxs-lookup"><span data-stu-id="6ef7a-103">Enables the client network protocol that is specified by the [Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ef7a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ef7a-104">Syntax</span></span>  
  
```  
  
object  
.SetEnableMethod()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="6ef7a-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="6ef7a-105">Parts</span></span>  
 <span data-ttu-id="6ef7a-106">*object*</span><span class="sxs-lookup"><span data-stu-id="6ef7a-106">*object*</span></span>  
 <span data-ttu-id="6ef7a-107">A [класса ClientNetworkProtocol](clientnetworkprotocol-class.md) , который представляет сетевой протокол, используемый клиентом [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ef7a-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="6ef7a-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6ef7a-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="6ef7a-109">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="6ef7a-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ef7a-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="6ef7a-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ef7a-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="6ef7a-111">See Also</span></span>  
 [<span data-ttu-id="6ef7a-112">Настройка сетевых протоколов клиента и сетевых библиотек</span><span class="sxs-lookup"><span data-stu-id="6ef7a-112">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
