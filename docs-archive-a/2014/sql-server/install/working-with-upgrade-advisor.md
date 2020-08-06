---
title: Работа с советником по переходу | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server], when to use
- SQL Server Upgrade Advisor, when to use
- when to use Upgrade Advisor
ms.assetid: 5f26a7b9-1ac2-442c-8316-87b078db3baf
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 75a16e57734493cdd7ac00e7bad3124eb7a99d84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659088"
---
# <a name="working-with-upgrade-advisor"></a><span data-ttu-id="b8c8f-102">Работа с помощником по обновлению</span><span class="sxs-lookup"><span data-stu-id="b8c8f-102">Working with Upgrade Advisor</span></span>
  <span data-ttu-id="b8c8f-103">Чтобы обеспечить успешное обновление до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], советник по переходу содержит центральную консоль для выявления проблем с установкой перед обновлением до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8c8f-103">To help ensure that your upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] is successful, Upgrade Advisor provides a central console to identify issues to address in your installations before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="b8c8f-104">Помощник по обновлению можно использовать для выполнения следующих задач.</span><span class="sxs-lookup"><span data-stu-id="b8c8f-104">You can use Upgrade Advisor to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="b8c8f-105">Анализ компонентов предыдущей версии на локальном или удаленном сервере.</span><span class="sxs-lookup"><span data-stu-id="b8c8f-105">Analyze previous version's components on local or remote servers.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b8c8f-106">Нельзя анализировать удаленные экземпляры служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8c8f-106">You cannot analyze remote instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="b8c8f-107">Просмотр результатов анализа.</span><span class="sxs-lookup"><span data-stu-id="b8c8f-107">View the results of the analysis.</span></span>  
  
 <span data-ttu-id="b8c8f-108">В состав помощника по обновлению входит анализатор и средство просмотра.</span><span class="sxs-lookup"><span data-stu-id="b8c8f-108">Upgrade Advisor includes an analyzer and a viewer.</span></span> <span data-ttu-id="b8c8f-109">Мастер анализа помощника по обновлению анализирует выбранные компоненты.</span><span class="sxs-lookup"><span data-stu-id="b8c8f-109">The Upgrade Advisor Analysis Wizard analyzes the components you select.</span></span> <span data-ttu-id="b8c8f-110">Затем мастер анализа создает индивидуализированные отчеты о проблемах, которые нужно решить для обновления до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8c8f-110">The analyzer then generates custom reports about issues that you must handle before you can upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="b8c8f-111">Эти отчеты можно просматривать с помощью средства просмотра отчетов помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="b8c8f-111">You use the Upgrade Advisor Report Viewer to view the custom reports.</span></span> <span data-ttu-id="b8c8f-112">Дополнительные сведения об обнаружении анализа советника по переходу см. в разделе [Устранение проблем с обновлением](../../../2014/sql-server/install/resolving-upgrade-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b8c8f-112">For more information about what Upgrade Advisor analysis detects, see [Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md).</span></span>  
  
 <span data-ttu-id="b8c8f-113">Подразделы в этом разделе содержат общие сведения о функциях помощника по обновлению, сведения о его использовании и об использовании отчетов помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="b8c8f-113">The topics in this section provide an overview of Upgrade Advisor functionality and information about how to use Upgrade Advisor and Upgrade Advisor reports.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b8c8f-114">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="b8c8f-114">In This Section</span></span>  
  
|<span data-ttu-id="b8c8f-115">Раздел</span><span class="sxs-lookup"><span data-stu-id="b8c8f-115">Topic</span></span>|<span data-ttu-id="b8c8f-116">Описание</span><span class="sxs-lookup"><span data-stu-id="b8c8f-116">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b8c8f-117">Общие сведения о помощнике по обновлению</span><span class="sxs-lookup"><span data-stu-id="b8c8f-117">Overview of Upgrade Advisor</span></span>](../../../2014/sql-server/install/overview-of-upgrade-advisor.md)|<span data-ttu-id="b8c8f-118">Содержит общие сведения о процессе обновления, мастере анализа помощника по обновлению и средстве просмотра отчетов помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="b8c8f-118">Provides an overview of the upgrade process, the Upgrade Advisor Analysis Wizard, and the Upgrade Advisor Report Viewer.</span></span>|  
|[<span data-ttu-id="b8c8f-119">Инструкции по работе с помощником по обновлению</span><span class="sxs-lookup"><span data-stu-id="b8c8f-119">Upgrade Advisor How-to Topics</span></span>](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md)|<span data-ttu-id="b8c8f-120">Содержит инструкции по выполнению общих процедур помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="b8c8f-120">Provides instructions to perform common Upgrade Advisor procedures.</span></span>|  
|[<span data-ttu-id="b8c8f-121">Справочник по пользовательскому интерфейсу помощника по обновлению</span><span class="sxs-lookup"><span data-stu-id="b8c8f-121">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)|<span data-ttu-id="b8c8f-122">Содержит разделы, которые появляются при нажатии клавиши F1 или кнопки **Справка** на страницах мастера анализа помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="b8c8f-122">Contains topics that appear if you press the F1 key or click **Help** on the Upgrade Advisor Analysis Wizard pages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b8c8f-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="b8c8f-123">See Also</span></span>  
 <span data-ttu-id="b8c8f-124">[Установка помощника по обновлению](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="b8c8f-124">[Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="b8c8f-125">Решение проблем при обновлении</span><span class="sxs-lookup"><span data-stu-id="b8c8f-125">Resolving Upgrade Issues</span></span>](../../../2014/sql-server/install/resolving-upgrade-issues.md)  
  
  
