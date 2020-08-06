---
title: Методы подписки и доставки | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- reports [Reporting Services], delivering
- delivery [Reporting Services]
- methods [Reporting Services], subscription and delivery
- subscriptions [Reporting Services], about subscriptions
ms.assetid: a8637501-1817-4ccc-b07d-dd9ed5608805
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c6ae92a6abd5c25b9ab1236a2b5b11429d210cba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730137"
---
# <a name="subscription-and-delivery-methods"></a><span data-ttu-id="89410-102">Методы подписки и доставки</span><span class="sxs-lookup"><span data-stu-id="89410-102">Subscription and Delivery Methods</span></span>
  <span data-ttu-id="89410-103">Эти методы позволяют создавать подписки и управлять подписками и доставкой элементов каталога.</span><span class="sxs-lookup"><span data-stu-id="89410-103">You can use these methods to create and manage subscriptions and delivery of catalog items.</span></span>  
  
|<span data-ttu-id="89410-104">Метод</span><span class="sxs-lookup"><span data-stu-id="89410-104">Method</span></span>|<span data-ttu-id="89410-105">Действие</span><span class="sxs-lookup"><span data-stu-id="89410-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateDataDrivenSubscription%2A>|<span data-ttu-id="89410-106">Создает управляемую данными подписку для указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="89410-106">Creates a data-driven subscription for a specified item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetDataDrivenSubscriptionProperties%2A>|<span data-ttu-id="89410-107">Возвращает свойства управляемой данными подписки.</span><span class="sxs-lookup"><span data-stu-id="89410-107">Returns the properties for a data-driven subscription.</span></span>|  
|<xref:ReportService2010.ReportingService2010.CreateSubscription%2A>|<span data-ttu-id="89410-108">Создает подписку для указанного элемента в базе данных сервера отчетов или библиотеке SharePoint.</span><span class="sxs-lookup"><span data-stu-id="89410-108">Creates a subscription for the specified item in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteSubscription%2A>|<span data-ttu-id="89410-109">Удаляет подписку из базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="89410-109">Deletes a subscription from the report server database.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSubscriptionProperties%2A>|<span data-ttu-id="89410-110">Возвращает свойства подписки.</span><span class="sxs-lookup"><span data-stu-id="89410-110">Returns the properties of a subscription.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListMySubscriptions%2A>|<span data-ttu-id="89410-111">Получает список подписок, созданных текущим пользователем сервера отчетов или сайта SharePoint для данного элемента каталога.</span><span class="sxs-lookup"><span data-stu-id="89410-111">Retrieves a list of subscriptions that have been created by the current user of the report server or SharePoint site for the given catalog item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListSubscriptions%2A>|<span data-ttu-id="89410-112">Получает список подписок, созданных для данного элемента.</span><span class="sxs-lookup"><span data-stu-id="89410-112">Retrieves a list of subscriptions that have been created for a given item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.PrepareQuery%2A>|<span data-ttu-id="89410-113">Возвращает набор данных, содержащий поля, полученные запросом доставки для управляемой данными подписки.</span><span class="sxs-lookup"><span data-stu-id="89410-113">Returns a data set containing the fields retrieved by the delivery query for a data-driven subscription.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetDataDrivenSubscriptionProperties%2A>|<span data-ttu-id="89410-114">Задает значения свойств управляемой данными подписки.</span><span class="sxs-lookup"><span data-stu-id="89410-114">Sets the values of properties of a data-driven subscription.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetSubscriptionProperties%2A>|<span data-ttu-id="89410-115">Задает значения свойств подписки.</span><span class="sxs-lookup"><span data-stu-id="89410-115">Sets the values of properties of a subscription.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="89410-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="89410-116">See Also</span></span>  
 <span data-ttu-id="89410-117">[Создание приложений с помощью веб-службы и .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="89410-117">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="89410-118">[Веб-служба сервера отчетов](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="89410-118">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="89410-119">[Методы веб-службы сервера отчетов](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="89410-119">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="89410-120">Технический справочник (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="89410-120">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
