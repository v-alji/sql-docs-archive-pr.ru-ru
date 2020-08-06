---
title: Построитель отчетов (службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 32be8fcc-e87d-4c45-a644-dff45776a981
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dae43dd86cd6b02c81f0fc90a05292458eb87200
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732333"
---
# <a name="report-builder-ssrs"></a><span data-ttu-id="017c7-102">Построитель отчетов (SSRS)</span><span class="sxs-lookup"><span data-stu-id="017c7-102">Report Builder (SSRS)</span></span>
  <span data-ttu-id="017c7-103">Построитель отчетов — это среда создания отчетов для бизнес-пользователей, предпочитающих работать в среде [!INCLUDE[msCoName](../../includes/msconame-md.md)] Office.</span><span class="sxs-lookup"><span data-stu-id="017c7-103">Report Builder is a report authoring environment for business users who prefer to work in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Office environment.</span></span> <span data-ttu-id="017c7-104">При создании отчета задается, откуда брать данные, какие данные брать и как их отображать.</span><span class="sxs-lookup"><span data-stu-id="017c7-104">When you design a report, you specify where to get the data, which data to get, and how to display the data.</span></span> <span data-ttu-id="017c7-105">При запуске отчета обработчик получает все указанные сведения, извлекает данные и объединяет их с макетом отчета, чтобы создать отчет.</span><span class="sxs-lookup"><span data-stu-id="017c7-105">When you run the report, the report processor takes all the information you have specified, retrieves the data, and combines it with the report layout to generate the report.</span></span>  
  
## <a name="benefits-of-report-builder"></a><span data-ttu-id="017c7-106">Преимущества построителя отчетов</span><span class="sxs-lookup"><span data-stu-id="017c7-106">Benefits of Report Builder</span></span>  
 <span data-ttu-id="017c7-107">Построитель отчетов позволяет делать следующее:</span><span class="sxs-lookup"><span data-stu-id="017c7-107">Report Builder enables you to:</span></span>  
  
-   <span data-ttu-id="017c7-108">Использовать ленту построителя отчетов для быстрого добавления элементов в отчеты, запуска мастеров таблиц, диаграмм и карт и форматирования данных отчета.</span><span class="sxs-lookup"><span data-stu-id="017c7-108">Use the Report Builder ribbon to quickly add items your reports, launch table, chart, and map wizards, and format report data.</span></span>  
  
-   <span data-ttu-id="017c7-109">Добавлять данные из встроенных поставщиков с помощью конструкторов запросов, которые помогают указать, какие данные включить в отчет.</span><span class="sxs-lookup"><span data-stu-id="017c7-109">Add data from built-in data providers by using query designers that help you specify which data to include in your report.</span></span>  
  
-   <span data-ttu-id="017c7-110">Создавать и использовать параметры отчета и другие интерактивные функции, позволяющие пользователям отчета настроить данные и представление отчета.</span><span class="sxs-lookup"><span data-stu-id="017c7-110">Create and use report parameters and other interactive features that enable your report readers to customize data and vary report presentation.</span></span>  
  
-   <span data-ttu-id="017c7-111">Создавать выражения на основе встроенных полей, коллекций, операторов и функций.</span><span class="sxs-lookup"><span data-stu-id="017c7-111">Create expressions from built-in fields, collections, operators, and functions.</span></span>  
  
-   <span data-ttu-id="017c7-112">Открывать отчеты прямо с сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="017c7-112">Open reports directly from a report server.</span></span>  
  
-   <span data-ttu-id="017c7-113">Предварительно просматривать отчеты, которые используют локальные или опубликованные общие источники данных и общие наборы данных.</span><span class="sxs-lookup"><span data-stu-id="017c7-113">Preview reports that use local or published shared data sources and shared datasets.</span></span>  
  
-   <span data-ttu-id="017c7-114">Просматривать отчеты в формате HTML или формате печати.</span><span class="sxs-lookup"><span data-stu-id="017c7-114">Preview reports in HTML or print format.</span></span>  
  
-   <span data-ttu-id="017c7-115">Экспортировать отчеты в другие форматы файлов, например в [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)].</span><span class="sxs-lookup"><span data-stu-id="017c7-115">Export reports to other file formats such as [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)].</span></span>  
  
-   <span data-ttu-id="017c7-116">Сохранять отчеты и связанные с ними элементы в библиотеке SharePoint, на сервере отчетов или на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="017c7-116">Save your report and related items s to a SharePoint library, a report server, or your local computer.</span></span>  
  
 <span data-ttu-id="017c7-117">У построителя отчетов и конструктора отчетов много общего.</span><span class="sxs-lookup"><span data-stu-id="017c7-117">Report Builder and Report Designer share many features.</span></span> <span data-ttu-id="017c7-118">Дополнительные сведения о построителе отчетов см. в документации по [построителю отчетов](https://go.microsoft.com/fwlink/?LinkId=154494) на сайте msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="017c7-118">For more information about Report Builder, see [Report Builder documentation](https://go.microsoft.com/fwlink/?LinkId=154494) on msdn.microsoft.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="017c7-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="017c7-119">See Also</span></span>  
 <span data-ttu-id="017c7-120">[Настройка доступа к построитель отчетов](../report-server/configure-report-builder-access.md) </span><span class="sxs-lookup"><span data-stu-id="017c7-120">[Configure Report Builder Access](../report-server/configure-report-builder-access.md) </span></span>  
 <span data-ttu-id="017c7-121">[Средства Reporting Services](reporting-services-tools.md) </span><span class="sxs-lookup"><span data-stu-id="017c7-121">[Reporting Services Tools](reporting-services-tools.md) </span></span>  
 [<span data-ttu-id="017c7-122">Разработка отчетов с использованием конструктора отчетов (SSRS)</span><span class="sxs-lookup"><span data-stu-id="017c7-122">Design Reports with Report Designer &#40;SSRS&#41;</span></span>](design-reporting-services-paginated-reports-with-report-designer-ssrs.md)  
  
  
