---
title: Параметры (SQL Server AlwaysOn, страница панели мониторинга) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Alwayson.Dashboard
ms.assetid: 4369b588-e982-4b57-80a1-beb2e879ce0b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bef7622b56aabb2c908337fef4d110a12dd5a9bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657898"
---
# <a name="options-sql-server-alwayson-dashboard-page"></a><span data-ttu-id="0fcb1-102">Параметры (страница панели мониторинга SQL Server AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="0fcb1-102">Options (SQL Server AlwaysOn, Dashboard Page)</span></span>
  <span data-ttu-id="0fcb1-103">Для настройки панели мониторинга AlwaysOn используйте страницу **SQL Server AlwaysOn Dashboard** (Панель мониторинга SQL Server) диалогового окна [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]**в среде** .</span><span class="sxs-lookup"><span data-stu-id="0fcb1-103">Use the **SQL Server AlwaysOn Dashboard** page of the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]**Options** dialog box to configure the AlwaysOn Dashboard.</span></span>  
  
 <span data-ttu-id="0fcb1-104">**Открытие этой страницы**</span><span class="sxs-lookup"><span data-stu-id="0fcb1-104">**To access this page:**</span></span>  
  
 <span data-ttu-id="0fcb1-105">В меню **Сервис** щелкните **Параметры**, разверните папку **SQL Server AlwaysOn** и затем выберите **Панель мониторинга**.</span><span class="sxs-lookup"><span data-stu-id="0fcb1-105">On the **Tools** menu, click **Options**, expand the **SQL Server AlwaysOn** folder, and then click **Dashboard**.</span></span>  
  
## <a name="on-this-page"></a><span data-ttu-id="0fcb1-106">На этой странице</span><span class="sxs-lookup"><span data-stu-id="0fcb1-106">On This Page</span></span>  
 <span data-ttu-id="0fcb1-107">**Включить автоматическое обновление.**</span><span class="sxs-lookup"><span data-stu-id="0fcb1-107">**Turn on automatic refresh.**</span></span>  
 <span data-ttu-id="0fcb1-108">Выберите, чтобы включить автоматическое обновление.</span><span class="sxs-lookup"><span data-stu-id="0fcb1-108">Click to enable automatic refresh.</span></span> <span data-ttu-id="0fcb1-109">Доступны следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="0fcb1-109">The options are:</span></span>  
  
-   <span data-ttu-id="0fcb1-110">В поле **Интервал обновления (в секундах)** отображается количество секунд, через которое панель будет обновлена.</span><span class="sxs-lookup"><span data-stu-id="0fcb1-110">The **Refresh interval (in seconds)** field displays the number of seconds at which the dashboard will refresh.</span></span> <span data-ttu-id="0fcb1-111">Значение по умолчанию — 30.</span><span class="sxs-lookup"><span data-stu-id="0fcb1-111">The default value is 30.</span></span> <span data-ttu-id="0fcb1-112">Если автоматическое обновление включено, значение в этом поле можно изменить, чтобы указать новый интервал обновления.</span><span class="sxs-lookup"><span data-stu-id="0fcb1-112">When automatic refresh is enabled, you can edit this field to change the refresh interval.</span></span>  
  
-   <span data-ttu-id="0fcb1-113">В поле **Количество повторных попыток подключения** отображается, сколько раз панель мониторинга будет пытаться установить соединение с экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , на котором расположена реплика доступности группы доступности, мониторинг которой выполняет панель.</span><span class="sxs-lookup"><span data-stu-id="0fcb1-113">The **Number of connection retries** displays the number of times that the dashboard will attempt to connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts an availability replica for an availability group that the Dashboard is monitoring.</span></span> <span data-ttu-id="0fcb1-114">Значение по умолчанию — 65535.</span><span class="sxs-lookup"><span data-stu-id="0fcb1-114">The default value is 65535.</span></span> <span data-ttu-id="0fcb1-115">Если автоматическое обновление включено, значение в этом поле вы можете изменить, чтобы указать другое количество попыток.</span><span class="sxs-lookup"><span data-stu-id="0fcb1-115">When automatic refresh is enabled, you can edit this field to change the number of connection retries.</span></span>  
  
 <span data-ttu-id="0fcb1-116">**Включить собственную, определяемую пользователем политику AlwaysOn.**</span><span class="sxs-lookup"><span data-stu-id="0fcb1-116">**Enable your user-defined AlwaysOn policy.**</span></span>  
 <span data-ttu-id="0fcb1-117">Если вы определили собственную политику AlwaysOn, выберите этот параметр, чтобы включить ее.</span><span class="sxs-lookup"><span data-stu-id="0fcb1-117">If you have defined your own AlwaysOn policy, click this option to enable your policy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fcb1-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="0fcb1-118">See Also</span></span>  
 [<span data-ttu-id="0fcb1-119">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="0fcb1-119">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
