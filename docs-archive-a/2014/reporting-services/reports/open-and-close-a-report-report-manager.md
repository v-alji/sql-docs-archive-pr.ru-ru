---
title: Открытие и закрытие отчетов (диспетчер отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- opening reports
- closing reports
- reports [Reporting Services], opening
ms.assetid: a9db1caf-1e7d-41ee-9aed-e09fd0712f9b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ae9da3f95b7d754d16648e6b6a78ddfa39a499c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657002"
---
# <a name="open-and-close-a-report-report-manager"></a><span data-ttu-id="e33f2-102">Открытие и закрытие отчетов (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="e33f2-102">Open and Close a Report (Report Manager)</span></span>
  <span data-ttu-id="e33f2-103">Диспетчер отчетов можно использовать для просмотра отчетов, опубликованных на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="e33f2-103">You can use Report Manager to view reports that have been published to a report server.</span></span> <span data-ttu-id="e33f2-104">По умолчанию все отчеты открываются в формате HTML.</span><span class="sxs-lookup"><span data-stu-id="e33f2-104">By default, all reports open in HTML.</span></span> <span data-ttu-id="e33f2-105">После открытия отчета, его можно экспортировать для просмотра в формате других приложений.</span><span class="sxs-lookup"><span data-stu-id="e33f2-105">After a report is open, you can export it to view it in other application formats.</span></span> <span data-ttu-id="e33f2-106">Если отчет содержит интерактивные функции, либо разработан в построителе отчетов и содержит интерактивные данные, можно щелкать ссылки для просмотра дополнительных отчетов или данных.</span><span class="sxs-lookup"><span data-stu-id="e33f2-106">If the report contains interactive features or if it is a Report Builder report that contains interactive data, you can click the links to view additional reports or data.</span></span>  
  
### <a name="to-view-a-report"></a><span data-ttu-id="e33f2-107">Просмотр отчета</span><span class="sxs-lookup"><span data-stu-id="e33f2-107">To view a report</span></span>  
  
1.  <span data-ttu-id="e33f2-108">Запустите [Диспетчер отчетов (службы Reporting Services в основном режиме)](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="e33f2-108">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="e33f2-109">Найдите отчет непосредственно в папках или путем поиска по имени.</span><span class="sxs-lookup"><span data-stu-id="e33f2-109">Find a report by browsing folders or searching for a report by name.</span></span> <span data-ttu-id="e33f2-110">Для просмотра содержимого любой из папок нужно щелкнуть имя или значок соответствующей папки на странице **Содержимое** .</span><span class="sxs-lookup"><span data-stu-id="e33f2-110">Browse folder contents by clicking a folder name or folder icon in the **Contents** page.</span></span> <span data-ttu-id="e33f2-111">Для поиска отчета введите полностью или частично его имя в текстовом поле **Поиск** в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="e33f2-111">Search for a report by typing all or part of the report name in the **Search for** text box at the top of the page.</span></span>  
  
3.  <span data-ttu-id="e33f2-112">Чтобы просмотреть отчет, щелкните название отчета или значок.</span><span class="sxs-lookup"><span data-stu-id="e33f2-112">To view a report, click a report name or an icon.</span></span> <span data-ttu-id="e33f2-113">Отчет обозначается следующим значком:</span><span class="sxs-lookup"><span data-stu-id="e33f2-113">The following icon indicates a report:</span></span>  
  
     <span data-ttu-id="e33f2-114">![Значок отчета](../media/hlp-16doc.gif "Значок отчета")</span><span class="sxs-lookup"><span data-stu-id="e33f2-114">![Report icon](../media/hlp-16doc.gif "Report icon")</span></span>  
  
     <span data-ttu-id="e33f2-115">Для некоторых отчетов требуется ввести либо имя пользователя и пароль, либо значение параметра</span><span class="sxs-lookup"><span data-stu-id="e33f2-115">Some reports require you to provide either a user name and password or a parameter value</span></span>  
  
4.  <span data-ttu-id="e33f2-116">Чтобы закрыть отчет, закройте диспетчер отчетов или перейдите на другую страницу или другую папку (для этого нажмите кнопку **Назад** или щелкните ссылку на папку в верхней части страницы).</span><span class="sxs-lookup"><span data-stu-id="e33f2-116">To close the report, close Report Manager or browse to another page or folder (for example, by clicking the **Back** button or clicking a folder link at the top of the page).</span></span>  
  
     <span data-ttu-id="e33f2-117">Закрываемый отчет не удаляется из кэша браузера.</span><span class="sxs-lookup"><span data-stu-id="e33f2-117">Closing a report does not remove it from the browser cache.</span></span> <span data-ttu-id="e33f2-118">Для отключения от отчета необходимо закрыть браузер.</span><span class="sxs-lookup"><span data-stu-id="e33f2-118">You must close the browser to disconnect the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e33f2-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="e33f2-119">See Also</span></span>  
 <span data-ttu-id="e33f2-120">[Поиск отчетов и других элементов &#40;построитель отчетов и SSRS&#41;](../report-builder/searching-for-reports-and-other-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e33f2-120">[Searching for Reports and Other Items &#40;Report Builder  and SSRS&#41;](../report-builder/searching-for-reports-and-other-items-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e33f2-121">[Страница "содержимое" &#40;диспетчер отчетов&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="e33f2-121">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="e33f2-122">[Поиск, просмотр отчетов и управление ими &#40;построитель отчетов и SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e33f2-122">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e33f2-123">Управление содержимым сервера отчетов (службы Reporting Services в основном режиме)</span><span class="sxs-lookup"><span data-stu-id="e33f2-123">Report Server Content Management &#40;SSRS Native Mode&#41;</span></span>](../report-server/report-server-content-management-ssrs-native-mode.md)  
  
  
