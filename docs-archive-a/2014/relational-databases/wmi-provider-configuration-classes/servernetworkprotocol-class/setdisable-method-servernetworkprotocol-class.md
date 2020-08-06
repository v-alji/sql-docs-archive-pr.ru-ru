---
title: Метод SetDisable (класс класс servernetworkprotocol) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDisable Method (ServerNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDisable method
ms.assetid: 0ebbe0c5-07ad-4a76-a918-e379930adf71
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3176227aba4de1e5aca1be35ec1f071a15caa49e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657609"
---
# <a name="setdisable-method-servernetworkprotocol-class"></a><span data-ttu-id="0bbd3-102">Метод SetDisable (класс ServerNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="0bbd3-102">SetDisable Method (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="0bbd3-103">Отключает сетевой протокол сервера.</span><span class="sxs-lookup"><span data-stu-id="0bbd3-103">Disables the server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bbd3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0bbd3-104">Syntax</span></span>  
  
```  
  
object  
.SetDisable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="0bbd3-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="0bbd3-105">Parts</span></span>  
 <span data-ttu-id="0bbd3-106">*object*</span><span class="sxs-lookup"><span data-stu-id="0bbd3-106">*object*</span></span>  
 <span data-ttu-id="0bbd3-107">Объект [класс servernetworkprotocol Class] класс servernetworkprotocol-class.md), представляющий сетевой протокол, используемый экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0bbd3-107">A [ServerNetworkProtocol Class]servernetworkprotocol-class.md) object that represents the network protocol used by the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="0bbd3-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0bbd3-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="0bbd3-109">Значение uint32, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="0bbd3-109">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bbd3-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="0bbd3-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bbd3-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="0bbd3-111">See Also</span></span>  
 <span data-ttu-id="0bbd3-112">[Конфигурирование сетевых протоколов сервера и сетевых библиотек](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="0bbd3-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
