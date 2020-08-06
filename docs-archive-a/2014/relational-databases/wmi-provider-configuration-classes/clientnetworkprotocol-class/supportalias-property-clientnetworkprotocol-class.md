---
title: Свойство SupportAlias (класс класс clientnetworkprotocol) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SupportAlias Property (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SupportAlias property
ms.assetid: 1e7a2e87-c356-40a6-a6d9-e492467629f9
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6fd06ad0921dbb113a89af77e46733a28c2226c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668707"
---
# <a name="supportalias-property-clientnetworkprotocol-class"></a><span data-ttu-id="a6c96-102">Свойство SupportAlias (класс ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="a6c96-102">SupportAlias Property (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="a6c96-103">Возвращает логическое свойство, указывающее, поддерживает ли текущий сетевой протокол, заданный [методом SetOrderValue (класс класс clientnetworkprotocol)](clientnetworkprotocol-class.md) , псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="a6c96-103">Gets the Boolean property that specifies whether the current network protocol specified by the [SetOrderValue Method (ClientNetworkProtocol Class)](clientnetworkprotocol-class.md) support aliases.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6c96-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6c96-104">Syntax</span></span>  
  
```  
  
object  
.SupportAlias [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="a6c96-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="a6c96-105">Parts</span></span>  
 <span data-ttu-id="a6c96-106">*object*</span><span class="sxs-lookup"><span data-stu-id="a6c96-106">*object*</span></span>  
 <span data-ttu-id="a6c96-107">A [класса ClientNetworkProtocol](clientnetworkprotocol-class.md) , который представляет сетевой протокол, используемый клиентом [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6c96-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="a6c96-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a6c96-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="a6c96-109">Логическое значение, которое указывает, поддерживает ли псевдонимы сетевой протокол клиента:</span><span class="sxs-lookup"><span data-stu-id="a6c96-109">A Boolean value that specifies whether the client network protocol supports aliases.</span></span>  
  
 <span data-ttu-id="a6c96-110">если значение равно True, сетевой протокол клиента поддерживает псевдонимы;</span><span class="sxs-lookup"><span data-stu-id="a6c96-110">If True, the client network protocol supports aliases.</span></span>  
  
 <span data-ttu-id="a6c96-111">если значение равно False, сетевой протокол клиента не поддерживает псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="a6c96-111">If False, the client network protocol does not support aliases.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6c96-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="a6c96-112">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6c96-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="a6c96-113">See Also</span></span>  
 [<span data-ttu-id="a6c96-114">Настройка клиентских протоколов</span><span class="sxs-lookup"><span data-stu-id="a6c96-114">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
