---
title: Реализация модуля доставки | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery [Reporting Services]
- custom delivery extensions [Reporting Services]
- extensions [Reporting Services], delivery
- delivery extensions [Reporting Services]
ms.assetid: 600cd229-efcd-480e-8c95-3c3c39ff4e7a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af1e804e029dae77fb7836577aa8d4a45ad20109
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669308"
---
# <a name="implementing-a-delivery-extension"></a><span data-ttu-id="cdc46-102">Реализация модуля доставки</span><span class="sxs-lookup"><span data-stu-id="cdc46-102">Implementing a Delivery Extension</span></span>
  <span data-ttu-id="cdc46-103">С помощью среды [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] пользователи могут создавать и публиковать отчеты, которые затем можно доставлять в различные места.</span><span class="sxs-lookup"><span data-stu-id="cdc46-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] enables users to create and publish reports that, once created and published, can be delivered to various locations.</span></span> <span data-ttu-id="cdc46-104">Кроме того, службы [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] содержат несколько модулей доставки и API-интерфейс доставки, который позволяет разработчикам создавать дополнительные модули доставки, расширяя возможности доставки в службах [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cdc46-104">In addition, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] includes several delivery extensions and a delivery API that enable developers to create additional delivery extensions to further extend the functionality of delivery in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="cdc46-105">Образец реализации модуля доставки см. в разделе [Образцы продуктов служб SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="cdc46-105">For a sample implementation of a delivery extension, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cdc46-106">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="cdc46-106">In This Section</span></span>  
 <span data-ttu-id="cdc46-107">[Общие сведения о модулях доставки] Delivery-Extensions-overview.md)</span><span class="sxs-lookup"><span data-stu-id="cdc46-107">[Delivery Extensions Overview]delivery-extensions-overview.md)</span></span>  
 <span data-ttu-id="cdc46-108">Введение в процесс написания пользовательского модуля доставки для служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cdc46-108">Introduces how to write a custom delivery extension for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="cdc46-109">Подготовка к реализации модуля доставки</span><span class="sxs-lookup"><span data-stu-id="cdc46-109">Preparing to Implement a Delivery Extension</span></span>](preparing-to-implement-a-delivery-extension.md)  
 <span data-ttu-id="cdc46-110">Описывает интерфейсы и классы, доступные при реализации модуля доставки служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], а также вопросы, которые следует обдумать перед реализацией.</span><span class="sxs-lookup"><span data-stu-id="cdc46-110">Describes the interfaces and classes available when implementing an [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, as well as issues to consider before implementation.</span></span>  
  
 [<span data-ttu-id="cdc46-111">Создание библиотеки модулей доставки</span><span class="sxs-lookup"><span data-stu-id="cdc46-111">Creating a Delivery Extension Library</span></span>](creating-a-delivery-extension-library.md)  
 <span data-ttu-id="cdc46-112">Описывается процесс присвоения пространства имен модулю доставки служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] и процесс компиляции модуля доставки в DLL-библиотеку.</span><span class="sxs-lookup"><span data-stu-id="cdc46-112">Describes assigning a namespace for your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension and compiling your delivery extension into a library DLL.</span></span>  
  
 [<span data-ttu-id="cdc46-113">Реализация интерфейса IDeliveryExtension для модуля доставки</span><span class="sxs-lookup"><span data-stu-id="cdc46-113">Implementing the IDeliveryExtension Interface for a Delivery Extension</span></span>](implementing-the-ideliveryextension-interface-for-a-delivery-extension.md)  
 <span data-ttu-id="cdc46-114">Описывает атрибуты модуля доставки и процесс реализации собственного класса модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="cdc46-114">Describes the attributes of a delivery extension, and how to implement your own delivery extension class.</span></span>  
  
 [<span data-ttu-id="cdc46-115">Использование класса Notification для модуля доставки</span><span class="sxs-lookup"><span data-stu-id="cdc46-115">Using a Notification Class for a Delivery Extension</span></span>](using-a-notification-class-for-a-delivery-extension.md)  
 <span data-ttu-id="cdc46-116">Описывает атрибуты класса **Notification** и способ его использования в реализации модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="cdc46-116">Describes the attributes of a **Notification** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="cdc46-117">Использование класса Setting для модуля доставки</span><span class="sxs-lookup"><span data-stu-id="cdc46-117">Using the Setting Class for a Delivery Extension</span></span>](using-the-setting-class-for-a-delivery-extension.md)  
 <span data-ttu-id="cdc46-118">Описывает атрибуты класса **Setting** и способ его использования в реализации модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="cdc46-118">Describes the attributes of a **Setting** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="cdc46-119">Использование интерфейса IDeliveryReportServerInformation в модуле доставки</span><span class="sxs-lookup"><span data-stu-id="cdc46-119">Using the IDeliveryReportServerInformation Interface for a Delivery Extension</span></span>](using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension.md)  
 <span data-ttu-id="cdc46-120">Описывает атрибуты интерфейса **IDeliveryReportServerInformation** и способ его использования в реализации модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="cdc46-120">Describes the attributes of a **IDeliveryReportServerInformation** interface and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="cdc46-121">Использование класса Report в модуле доставки</span><span class="sxs-lookup"><span data-stu-id="cdc46-121">Using the Report Class for a Delivery Extension</span></span>](using-the-report-class-for-a-delivery-extension.md)  
 <span data-ttu-id="cdc46-122">Описывает атрибуты класса **Report** и способ его использования в реализации модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="cdc46-122">Describes the attributes of a **Report** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="cdc46-123">Использование класса RenderedOutputFile для модуля доставки</span><span class="sxs-lookup"><span data-stu-id="cdc46-123">Using the RenderedOutputFile Class for a Delivery Extension</span></span>](using-the-renderedoutputfile-class-for-a-delivery-extension.md)  
 <span data-ttu-id="cdc46-124">Описывает атрибуты класса **RenderedOutputFile** и способ его использования в реализации модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="cdc46-124">Describes the attributes of a **RenderedOutputFile** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="cdc46-125">Реализация интерфейса ISubscriptionBaseUIUserControl для модуля доставки</span><span class="sxs-lookup"><span data-stu-id="cdc46-125">Implementing the ISubscriptionBaseUIUserControl Interface for a Delivery Extension</span></span>](implementing-the-isubscriptionbaseuiusercontrol-interface.md)  
 <span data-ttu-id="cdc46-126">Описывает атрибуты управления пользователями модуля доставки и способ реализации собственного пользовательского интерфейса для подписки.</span><span class="sxs-lookup"><span data-stu-id="cdc46-126">Describes the attributes of a delivery extension user control and how to implement your own user interface for a subscription.</span></span>  
  
 [<span data-ttu-id="cdc46-127">Развертывание модуля доставки</span><span class="sxs-lookup"><span data-stu-id="cdc46-127">Deploying a Delivery Extension</span></span>](deploying-a-delivery-extension.md)  
 <span data-ttu-id="cdc46-128">Описывается процесс развертывания модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="cdc46-128">Describes how to deploy your delivery extension.</span></span>  
  
 [<span data-ttu-id="cdc46-129">Отладка кода модулей доставки</span><span class="sxs-lookup"><span data-stu-id="cdc46-129">Debugging Delivery Extension Code</span></span>](debugging-delivery-extension-code.md)  
 <span data-ttu-id="cdc46-130">Описывается процесс отладки кода модулей доставки.</span><span class="sxs-lookup"><span data-stu-id="cdc46-130">Describes how to debug code in your delivery extension.</span></span>  
  
 [<span data-ttu-id="cdc46-131">Удаление модуля доставки</span><span class="sxs-lookup"><span data-stu-id="cdc46-131">Removing a Delivery Extension</span></span>](removing-a-delivery-extension.md)  
 <span data-ttu-id="cdc46-132">Описывается процесс удаления модуля доставки с сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="cdc46-132">Describes how to remove a delivery extension from a report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdc46-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="cdc46-133">See Also</span></span>  
 <span data-ttu-id="cdc46-134">[Расширения Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="cdc46-134">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="cdc46-135">Библиотека модулей служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="cdc46-135">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
