---
title: Монитор активности | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Activity Monitor [SQL Server]
ms.assetid: 1e6c430d-3a2a-468e-a3d5-ef5459c36c15
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 71fd0d1172b4fcd5739a3af1a60246cc7dce3b93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739758"
---
# <a name="activity-monitor"></a><span data-ttu-id="e0d7e-102">Монитор активности</span><span class="sxs-lookup"><span data-stu-id="e0d7e-102">Activity Monitor</span></span>
  <span data-ttu-id="e0d7e-103">Монитор активности отображает сведения о процессах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и о том, как функционирование этих процессов влияет на текущий экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0d7e-103">Activity Monitor displays information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes and how these processes affect the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="benefits-of-activity-monitor"></a><span data-ttu-id="e0d7e-104">Преимущества монитора активности</span><span class="sxs-lookup"><span data-stu-id="e0d7e-104">Benefits of Activity Monitor</span></span>  
 <span data-ttu-id="e0d7e-105">Монитор активности — это окно документов с вкладками со следующими развертываемыми и свертываемыми панелями: **Общие сведения**, **Активные пользовательские задачи**, **Ожидание ресурсов**, **Ввод-вывод в файл данных**и **Последние ресурсоемкие запросы**.</span><span class="sxs-lookup"><span data-stu-id="e0d7e-105">Activity Monitor is a tabbed document window that has the following expandable and collapsible panes: **Overview**, **Active User Tasks**, **Resource Waits**, **Data File I/O**, and **Recent Expensive Queries**.</span></span> <span data-ttu-id="e0d7e-106">После развертывания любой панели монитор активности выполняет запрос к экземпляру для получения необходимых сведений.</span><span class="sxs-lookup"><span data-stu-id="e0d7e-106">When any pane is expanded, Activity Monitor queries the instance for information.</span></span> <span data-ttu-id="e0d7e-107">При свертывании панели выполнение всех операций запроса для этой панели приостанавливается.</span><span class="sxs-lookup"><span data-stu-id="e0d7e-107">When a pane is collapsed, all querying activity stops for that pane.</span></span> <span data-ttu-id="e0d7e-108">Также можно одновременно развернуть одну или более панелей для просмотра различных типов активности в экземпляре.</span><span class="sxs-lookup"><span data-stu-id="e0d7e-108">You can also expand one or more panes at the same time to view different kinds of activity on the instance.</span></span>  
  
 <span data-ttu-id="e0d7e-109">Для столбцов на панели **Активные пользовательские задачи**, **Ожидание ресурсов**, **Ввод-вывод в файл данных**и **Последние ресурсоемкие запросы** можно настроить отображение следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e0d7e-109">For the columns that are included in the **Active User Tasks**, **Resource Waits**, **Data File I/O**, and **Recent Expensive Queries** panes, you can customize the display in the following ways:</span></span>  
  
1.  <span data-ttu-id="e0d7e-110">Чтобы изменить порядок столбцов, щелкните заголовок столбца и перетащите его в другое место ленты заголовков.</span><span class="sxs-lookup"><span data-stu-id="e0d7e-110">To rearrange the order of the columns, click the column heading and drag it to another location in the heading ribbon.</span></span>  
  
2.  <span data-ttu-id="e0d7e-111">Чтобы отсортировать столбец, щелкните имя столбца.</span><span class="sxs-lookup"><span data-stu-id="e0d7e-111">To sort a column, click the column name.</span></span>  
  
3.  <span data-ttu-id="e0d7e-112">Чтобы выполнить фильтрацию по одному или нескольким столбцам, щелкните стрелку раскрывающегося списка в заголовке столбца и выберите значение.</span><span class="sxs-lookup"><span data-stu-id="e0d7e-112">To filter on one or more columns, click the drop-down arrow in the column heading, and then select a value.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="e0d7e-113">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="e0d7e-113">Related Tasks</span></span>  
 <span data-ttu-id="e0d7e-114">Используйте следующие задачи, чтобы начать работу с монитором активности:</span><span class="sxs-lookup"><span data-stu-id="e0d7e-114">Use the following tasks to get started with Activity Monitor:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e0d7e-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e0d7e-115">**Description**</span></span>|<span data-ttu-id="e0d7e-116">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="e0d7e-116">**Topic**</span></span>|  
|<span data-ttu-id="e0d7e-117">Содержит сведения о том, как открыть монитор активности и настроить интервал обновления монитора активности.</span><span class="sxs-lookup"><span data-stu-id="e0d7e-117">Describes how to open Activity Monitor and how to set the Activity Monitor refresh interval.</span></span>|[<span data-ttu-id="e0d7e-118">Открытие монитора активности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="e0d7e-118">Open Activity Monitor &#40;SQL Server Management Studio&#41;</span></span>](../performance-monitor/open-activity-monitor-sql-server-management-studio.md)|  
|<span data-ttu-id="e0d7e-119">Ссылки на разделы с описанием производительности сервера и отслеживания действий.</span><span class="sxs-lookup"><span data-stu-id="e0d7e-119">Links to topics for server performance and activity monitoring.</span></span>|[<span data-ttu-id="e0d7e-120">Мониторинг производительности и действий сервера</span><span class="sxs-lookup"><span data-stu-id="e0d7e-120">Server Performance and Activity Monitoring</span></span>](../performance/server-performance-and-activity-monitoring.md)|  
  
  
