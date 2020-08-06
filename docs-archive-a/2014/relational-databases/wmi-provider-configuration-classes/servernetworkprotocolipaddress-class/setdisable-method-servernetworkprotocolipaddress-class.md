---
title: Метод SetDisable (класс класс servernetworkprotocolipaddress) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDisable Method (ServerNetworkProtocolIPAddress Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDisable method
ms.assetid: 7a7cc8cc-9fb8-4bf5-b483-2150d633ee10
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 9fbe928de1144c3065ddabb07bfd48606fdcea51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729270"
---
# <a name="setdisable-method-servernetworkprotocolipaddress-class"></a><span data-ttu-id="16348-102">Метод SetDisable (класс ServerNetworkProtocolIPAddress)</span><span class="sxs-lookup"><span data-stu-id="16348-102">SetDisable Method (ServerNetworkProtocolIPAddress Class)</span></span>
  <span data-ttu-id="16348-103">Отключает IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="16348-103">Disables the IP address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16348-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16348-104">Syntax</span></span>  
  
```  
  
object  
.SetDisable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="16348-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="16348-105">Parts</span></span>  
 <span data-ttu-id="16348-106">*object*</span><span class="sxs-lookup"><span data-stu-id="16348-106">*object*</span></span>  
 <span data-ttu-id="16348-107">Объект [объект servernetworkprotocolipadress Class] класс servernetworkprotocolipaddress-class.md), который представляет IP-адрес сетевого протокола в экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="16348-107">A [ServerNetworkProtocolIPAdress Class]servernetworkprotocolipaddress-class.md) object that represents an IP address for the network protocol on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="16348-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="16348-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="16348-109">Значение uint32, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="16348-109">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16348-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="16348-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16348-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="16348-111">See Also</span></span>  
 <span data-ttu-id="16348-112">[Конфигурирование сетевых протоколов сервера и сетевых библиотек](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="16348-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
