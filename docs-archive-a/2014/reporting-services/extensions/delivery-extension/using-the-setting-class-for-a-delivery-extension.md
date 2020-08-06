---
title: Использование класса Setting для модуля доставки | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], settings
- Setting class
ms.assetid: 50746639-da7c-46a5-ac7b-e87dd6b91880
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 594cf28391ae4523e1a95ad79ee5b1280ff72218
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729126"
---
# <a name="using-the-setting-class-for-a-delivery-extension"></a><span data-ttu-id="1b454-102">Использование класса Setting для модуля доставки</span><span class="sxs-lookup"><span data-stu-id="1b454-102">Using the Setting Class for a Delivery Extension</span></span>
  <span data-ttu-id="1b454-103">Класс <xref:Microsoft.ReportingServices.Interfaces.Setting> находится в пространстве имен <xref:Microsoft.ReportingServices.Interfaces> и представляет сведения о параметрах настройки для модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="1b454-103">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class is located in the <xref:Microsoft.ReportingServices.Interfaces> namespace and represents information about extension settings for a delivery extension.</span></span> <span data-ttu-id="1b454-104">Класс <xref:Microsoft.ReportingServices.Interfaces.Setting> предусматривает инфраструктуру для хранения информации о параметрах, необходимых для нормального функционирования модуля доставки.</span><span class="sxs-lookup"><span data-stu-id="1b454-104">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class provides infrastructure for storing information about the settings that are required in order for a delivery extension to function properly.</span></span> <span data-ttu-id="1b454-105">Так, в модуле доставки электронной почты сервера отчетов необходимо указывать параметры, требуемые для доставки электронной почты, такие как адрес получателя, адрес отправителя, строка темы электронного письма и т.д.</span><span class="sxs-lookup"><span data-stu-id="1b454-105">For example, in Report Server E-Mail delivery, a user is required to supply settings specific to e-mail delivery, such as the recipient's address, the sender's address, the subject line of the e-mail, and more.</span></span> <span data-ttu-id="1b454-106">Разумеется, для того, чтобы модуль доставки мог доставлять уведомления и отчеты, нестандартные поставщики доставки будут требовать от пользователя указания соответствующих параметров.</span><span class="sxs-lookup"><span data-stu-id="1b454-106">Undoubtedly, your custom delivery providers will require the user to supply specific settings in order for the delivery extension to deliver notifications and reports.</span></span>  
  
 <span data-ttu-id="1b454-107">Класс <xref:Microsoft.ReportingServices.Interfaces.Setting> используется при реализации свойства <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ExtensionSettings%2A> интерфейса <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension>.</span><span class="sxs-lookup"><span data-stu-id="1b454-107">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class is used when implementing the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ExtensionSettings%2A> property of the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> interface.</span></span> <span data-ttu-id="1b454-108">Кроме того, класс <xref:Microsoft.ReportingServices.Interfaces.Setting> используется для обработки данных настройки модуля, предоставляемых пользователем при создании подписки или уведомления.</span><span class="sxs-lookup"><span data-stu-id="1b454-108">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class is also used for processing the extension setting data that is supplied by a user when a subscription or notification is created.</span></span>  
  
 <span data-ttu-id="1b454-109">Пример использования класса <xref:Microsoft.ReportingServices.Interfaces.Setting> см. в разделе [Образцы продуктов служб SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="1b454-109">For an example of how to use the <xref:Microsoft.ReportingServices.Interfaces.Setting> class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b454-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="1b454-110">See Also</span></span>  
 <span data-ttu-id="1b454-111">[Реализация модуля доставки](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="1b454-111">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="1b454-112">Библиотека модулей Reporting Services</span><span class="sxs-lookup"><span data-stu-id="1b454-112">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
