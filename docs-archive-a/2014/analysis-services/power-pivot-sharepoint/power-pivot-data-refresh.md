---
title: Обновление данных PowerPivot | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- unattended data refresh [Analysis Services with SharePoint]
- scheduled data refresh [Analysis Services with SharePoint]
- data refresh [Analysis Services with SharePoint]
ms.assetid: ac8358a3-ee71-44c7-8ee6-ac7afe3ebaa4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6f7d5ed5c2f8882cbc0c47a1c711748d26e0193c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664548"
---
# <a name="powerpivot-data-refresh"></a><span data-ttu-id="60da1-102">Обновление данных PowerPivot</span><span class="sxs-lookup"><span data-stu-id="60da1-102">PowerPivot Data Refresh</span></span>
  <span data-ttu-id="60da1-103">После создания книги, содержащей данные PowerPivot, их придется периодически обновлять путем повторного выполнения запроса или команды, чтобы получать новые данные из источников, которые использовались при создании книги.</span><span class="sxs-lookup"><span data-stu-id="60da1-103">After you create a workbook that contains PowerPivot data, you might want to periodically refresh the data by rerunning a query or command to get updated information from the sources you used originally to create the workbook.</span></span> <span data-ttu-id="60da1-104">Этот процесс называется `data refresh`. Обновление данных может производиться по запросу [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)] или как запланированная операция путем запуска процесса служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] на сервере приложений фермы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="60da1-104">This process is called `data refresh`, and you can refresh data on demand in [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], or as a scheduled operation that runs as an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] process on an application server in a SharePoint farm.</span></span> <span data-ttu-id="60da1-105">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="60da1-105">For more information, see:</span></span>  
  
-   [<span data-ttu-id="60da1-106">Обновление данных PowerPivot с SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="60da1-106">PowerPivot Data Refresh with SharePoint 2010</span></span>](../powerpivot-data-refresh-with-sharepoint-2010.md)  
  
-   [<span data-ttu-id="60da1-107">Настройте учетную запись автоматического обновления данных PowerPivot &#40;PowerPivot для SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="60da1-107">Configure the PowerPivot Unattended Data Refresh Account &#40;PowerPivot for SharePoint&#41;</span></span>](../configure-unattended-data-refresh-account-powerpivot-sharepoint.md)  
  
-   [<span data-ttu-id="60da1-108">Настройка сохраненных учетных данных для &#40;обновления данных PowerPivot PowerPivot для SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="60da1-108">Configure Stored Credentials for PowerPivot Data Refresh &#40;PowerPivot for SharePoint&#41;</span></span>](../configure-stored-credentials-data-refresh-powerpivot-sharepoint.md)  
  
-   [<span data-ttu-id="60da1-109">Планирование &#40;обновления данных PowerPivot для SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="60da1-109">Schedule a Data Refresh &#40;PowerPivot for SharePoint&#41;</span></span>](../schedule-a-data-refresh-powerpivot-for-sharepoint.md)  
  
-   [<span data-ttu-id="60da1-110">Просмотр журнала обновления данных &#40;PowerPivot для SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="60da1-110">View Data Refresh History &#40;PowerPivot for SharePoint&#41;</span></span>](view-data-refresh-history-power-pivot-for-sharepoint.md)  
  
> [!NOTE]
>  <span data-ttu-id="60da1-111">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] и SharePoint Server 2013 Excel Services используется другая архитектура для обновления данных в моделях данных PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="60da1-111">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] and SharePoint Server 2013 Excel Services use a different architecture for data refresh of PowerPivot data models.</span></span> <span data-ttu-id="60da1-112">Архитектура SharePoint 2013 в качестве основного компонента для загрузки моделей данных PowerPivot использует службы Excel.</span><span class="sxs-lookup"><span data-stu-id="60da1-112">The SharePoint 2013 supported architecture utilizes Excel Services as the primary component to load PowerPivot data models.</span></span> <span data-ttu-id="60da1-113">В прежней архитектуре обновления данных для загрузки моделей данных использовался сервер с PowerPivot System Service и [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в режиме SharePoint.</span><span class="sxs-lookup"><span data-stu-id="60da1-113">The previous data refresh architecture used relied on a server running PowerPivot System Service and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in SharePoint mode to load data models.</span></span> <span data-ttu-id="60da1-114">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="60da1-114">For more information, see the following:</span></span>  
> 
>  -   [<span data-ttu-id="60da1-115">Обновление данных PowerPivot с SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="60da1-115">PowerPivot Data Refresh with SharePoint 2013</span></span>](power-pivot-data-refresh-with-sharepoint-2013.md)  
> -   [<span data-ttu-id="60da1-116">Обновление книг и обновление данных по расписанию &#40;SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="60da1-116">Upgrade Workbooks and Scheduled Data Refresh &#40;SharePoint 2013&#41;</span></span>](../instances/install-windows/upgrade-workbooks-and-scheduled-data-refresh-sharepoint-2013.md)  
  
  
