---
title: Удаление модуля доставки | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- removing delivery extensions
- deleting delivery extensions
- delivery extensions [Reporting Services], removing
ms.assetid: dcb7caf2-d19a-4bc5-afb3-2b61ad11cac5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7c4320f46b5013b0fa2accbc81792748c2d9f384
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669300"
---
# <a name="removing-a-delivery-extension"></a><span data-ttu-id="a1cb7-102">Удаление модуля доставки</span><span class="sxs-lookup"><span data-stu-id="a1cb7-102">Removing a Delivery Extension</span></span>
  <span data-ttu-id="a1cb7-103">Чтобы удалить модуль доставки служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], нужно просто удалить элемент **Extension** для модуля доставки из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a1cb7-103">To remove a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, simply remove the **Extension** element for your delivery extension from the configuration file.</span></span> <span data-ttu-id="a1cb7-104">После удаления сведений конфигурации модуль доставки перестает быть доступным для сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="a1cb7-104">After the configuration information is removed, the delivery extension is no longer available to the report server.</span></span>  
  
 <span data-ttu-id="a1cb7-105">После удаления соответствующего модулю доставки элемента **Extension** из файла конфигурации для этого модуля отменяется регистрация на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="a1cb7-105">Once a delivery extension's corresponding **Extension** element is removed from the configuration file, it is no longer registered with the report server.</span></span> <span data-ttu-id="a1cb7-106">Сервер отчетов удаляет запись из списка модулей доставки и отменяет активацию подписок, использующих этот модуль доставки.</span><span class="sxs-lookup"><span data-stu-id="a1cb7-106">The report server removes the entry from the list of delivery extensions and deactivates any subscriptions which use that delivery extension.</span></span> <span data-ttu-id="a1cb7-107">После удаления модуля доставки пользователи не смогут выбрать его в качестве метода уведомления.</span><span class="sxs-lookup"><span data-stu-id="a1cb7-107">When a delivery extension is removed, users are no longer able to select it as a method of notification.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1cb7-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="a1cb7-108">See Also</span></span>  
 <span data-ttu-id="a1cb7-109">[Реализация модуля доставки](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="a1cb7-109">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="a1cb7-110">Библиотека модулей Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a1cb7-110">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
