---
title: Свойство Properties (класс класс servernetworkprotocol) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- Properties Property (ServerNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- Properties property
ms.assetid: 6c971bfc-c277-4c1e-a06e-146dcc34e759
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 32d6ebf59d48639e3b65c60a726f6bd1bf4291f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654080"
---
# <a name="properties-property-servernetworkprotocol-class"></a><span data-ttu-id="3763c-102">Свойство Properties (класс ServerNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="3763c-102">Properties Property (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="3763c-103">Возвращает свойства, связанные с сетевым протоколом сервера.</span><span class="sxs-lookup"><span data-stu-id="3763c-103">Gets the properties associated with the server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3763c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3763c-104">Syntax</span></span>  
  
```  
  
object  
.Properties [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="3763c-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="3763c-105">Parts</span></span>  
 <span data-ttu-id="3763c-106">*object*</span><span class="sxs-lookup"><span data-stu-id="3763c-106">*object*</span></span>  
 <span data-ttu-id="3763c-107">A [класса ServerNetworkProtocol](servernetworkprotocol-class.md) , который представляет сетевой протокол, используемый экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3763c-107">A [ServerNetworkProtocol Class](servernetworkprotocol-class.md) object that represents the network protocol used by the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="3763c-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3763c-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="3763c-109">Массив объектов класса [ServerNetworkProtocolIPAdress](../servernetworkprotocolproperty-class/servernetworkprotocolproperty-class.md) , представляющих свойства, поддерживаемые сетевым протоколом сервера.</span><span class="sxs-lookup"><span data-stu-id="3763c-109">An array of [ServerNetworkProtocolProperty Class](../servernetworkprotocolproperty-class/servernetworkprotocolproperty-class.md) objects that represent the properties supported by the server network protocol.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3763c-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="3763c-110">Remarks</span></span>  
  
