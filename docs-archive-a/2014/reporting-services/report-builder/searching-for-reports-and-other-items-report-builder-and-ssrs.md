---
title: Поиск отчетов и других элементов (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6a586659-5c2b-453b-8f40-a3a469277b17
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a964cbdbc674fb3d29e18b5e5075695f0033801e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654861"
---
# <a name="searching-for-reports-and-other-items-report-builder--and-ssrs"></a><span data-ttu-id="be9b7-102">Поиск отчетов и других элементов (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="be9b7-102">Searching for Reports and Other Items (Report Builder  and SSRS)</span></span>
  <span data-ttu-id="be9b7-103">Можно использовать диспетчер отчетов для поиска на сервере отчетов заданных элементов по имени или описанию.</span><span class="sxs-lookup"><span data-stu-id="be9b7-103">You can use Report Manager to search a report server for specific items by name or description.</span></span> <span data-ttu-id="be9b7-104">Можно искать опубликованные отчеты, модели отчетов, папки, общие источники данных и ресурсы.</span><span class="sxs-lookup"><span data-stu-id="be9b7-104">You can search for published reports, report models, folders, shared data sources, and resources.</span></span> <span data-ttu-id="be9b7-105">Нельзя искать расписания, владельцев, назначения ролей, определенные моментальные снимки в журнале отчета или в подписках.</span><span class="sxs-lookup"><span data-stu-id="be9b7-105">You cannot search for schedules, owners, role assignments, specific snapshots in report history, or subscriptions.</span></span> <span data-ttu-id="be9b7-106">Поиск выполняется в базе данных сервера отчетов, в которой хранятся элементы.</span><span class="sxs-lookup"><span data-stu-id="be9b7-106">The search is performed on the report server database where the items are stored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="be9b7-107">Выполнение поиска системного файла не вернет результаты поиска для элементов, управляемых сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="be9b7-107">Performing a file system search will not return search results for items managed by a report server.</span></span>  
  
-   <span data-ttu-id="be9b7-108">Чтобы начать поиск элементов в диспетчере отчетов, введите строку поиска в текстовом поле **Поиск** вверху страницы.</span><span class="sxs-lookup"><span data-stu-id="be9b7-108">To search for items in Report Manager, type a search string in the **Search for** text box at the top of the page.</span></span> <span data-ttu-id="be9b7-109">Поиски начинаются с высшего узла иерархии папок и затем следуют через каждую ветку.</span><span class="sxs-lookup"><span data-stu-id="be9b7-109">Searches begin at the top node in the folder hierarchy and then proceed through every branch.</span></span> <span data-ttu-id="be9b7-110">Если отсутствует разрешение на доступ к определенной ветке, то эта ветка пропускается.</span><span class="sxs-lookup"><span data-stu-id="be9b7-110">If you do not have permission to access a specific branch, that branch is skipped.</span></span> <span data-ttu-id="be9b7-111">Это относится к папкам «Мои отчеты», принадлежащим другим пользователям и другим папкам, которые обычно не доступны.</span><span class="sxs-lookup"><span data-stu-id="be9b7-111">This applies to My Reports folders that belong to other users, and to other folders that are not generally available.</span></span> <span data-ttu-id="be9b7-112">Только отчеты и элементы, на которые есть разрешение просмотра, включаются в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="be9b7-112">Only reports and items that you have permission to view are included in the search results.</span></span>  
  
-   <span data-ttu-id="be9b7-113">Чтобы найти элемент по имени или описанию, укажите весь текст или часть текста, с которым нужно совпадение.</span><span class="sxs-lookup"><span data-stu-id="be9b7-113">To search for an item by name or description, specify all or part of the text that you want to match.</span></span> <span data-ttu-id="be9b7-114">В строке поиска регистр букв не учитывается.</span><span class="sxs-lookup"><span data-stu-id="be9b7-114">The search string is not case-sensitive.</span></span> <span data-ttu-id="be9b7-115">Для требования или исключения условия поиска нельзя использовать операторы поиска, такие как символы плюс (+) или минус (–).</span><span class="sxs-lookup"><span data-stu-id="be9b7-115">You cannot use search operators such as plus (+) or minus (-) symbols to require or exclude search criteria.</span></span>  
  
-   <span data-ttu-id="be9b7-116">Для поиска определенного текста в отчете используется панель инструментов, расположенная в верхней части отчета.</span><span class="sxs-lookup"><span data-stu-id="be9b7-116">To search for specific text within a report, use the toolbar at the top of the report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="be9b7-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="be9b7-117">See Also</span></span>  
 <span data-ttu-id="be9b7-118">[Поиск и просмотр отчетов в диспетчер отчетов &#40;построитель отчетов и служб SSRS&#41;](finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="be9b7-118">[Finding and Viewing Reports in Report Manager &#40;Report Builder and SSRS&#41;](finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="be9b7-119">[Использование Мои отчеты &#40;построитель отчетов и служб SSRS&#41;](using-my-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="be9b7-119">[Using My Reports &#40;Report Builder and SSRS&#41;](using-my-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="be9b7-120">[Поиск, просмотр отчетов и управление ими &#40;построитель отчетов и SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="be9b7-120">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="be9b7-121">Открытие и закрытие отчетов (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="be9b7-121">Open and Close a Report &#40;Report Manager&#41;</span></span>](../reports/open-and-close-a-report-report-manager.md)  
  
  
