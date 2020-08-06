---
title: Страница «Выбор баз данных» (мастер создания группы доступности — мастер добавления базы данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.adddatabasewizard.selectdatabases.f1
- sql12.swb.newagwizard.selectdatabases.f1
ms.assetid: 929c5e15-d087-438d-b1f2-aa97c5f8bff8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c626b8f0953f18a6dd4661124a09b7f542caeb82
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740475"
---
# <a name="select-databases-page-new-availability-group-wizard-add-database-wizard"></a><span data-ttu-id="f30c5-102">Страница «Выбор баз данных» (мастер создания группы доступности — мастер добавления базы данных)</span><span class="sxs-lookup"><span data-stu-id="f30c5-102">Select Databases Page (New Availability Group Wizard-Add Database Wizard)</span></span>
  <span data-ttu-id="f30c5-103"> В этом разделе описаны параметры на странице **Выбор баз данных**.</span><span class="sxs-lookup"><span data-stu-id="f30c5-103">This help topic describes the options of the **Specify Databases** page.</span></span> <span data-ttu-id="f30c5-104">Эта тема относится к [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] и [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f30c5-104">This topic applies to the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] and [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
##  <a name="select-databases-options"></a><a name="PageOptions"></a> <span data-ttu-id="f30c5-105">Выбор параметров баз данных</span><span class="sxs-lookup"><span data-stu-id="f30c5-105">Select Databases Options</span></span>  
 <span data-ttu-id="f30c5-106">В сетке **Пользовательские базы данных в этом экземпляре SQL Server** перечислены все локальные пользовательские базы данных.</span><span class="sxs-lookup"><span data-stu-id="f30c5-106">The **User databases on this instance of SQL Server** grid lists every local user database.</span></span> <span data-ttu-id="f30c5-107">Существуют следующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="f30c5-107">The columns are as follows:</span></span>  
  
 <span data-ttu-id="f30c5-108">**имя**;</span><span class="sxs-lookup"><span data-stu-id="f30c5-108">**Name**</span></span>  
 <span data-ttu-id="f30c5-109">Отображает имя локальной пользовательской базы данных.</span><span class="sxs-lookup"><span data-stu-id="f30c5-109">Displays the name of a local user database.</span></span>  
  
 <span data-ttu-id="f30c5-110">**Размер**</span><span class="sxs-lookup"><span data-stu-id="f30c5-110">**Size**</span></span>  
 <span data-ttu-id="f30c5-111">Отображает размер базы данных, если он доступен мастеру.</span><span class="sxs-lookup"><span data-stu-id="f30c5-111">Displays the database size, if the size is available to the wizard.</span></span>  
  
 <span data-ttu-id="f30c5-112">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="f30c5-112">**Status**</span></span>  
 <span data-ttu-id="f30c5-113">Отображает гиперссылку, текст которой показывает, отвечает ли база данных требованиям по добавлению в группу доступности.</span><span class="sxs-lookup"><span data-stu-id="f30c5-113">Displays a hyperlink whose text that indicates whether a given database meets the prerequisites for being added to an availability group.</span></span> <span data-ttu-id="f30c5-114">Если состояние — «**Отвечает требованиям**», то базу данных можно добавить в группу доступности.</span><span class="sxs-lookup"><span data-stu-id="f30c5-114">If the status is "**Meets prerequisites**" you can add the database to the availability group.</span></span> <span data-ttu-id="f30c5-115">Если база данных не отвечает всем требованиям, то по гиперссылке **Состояние** приводится краткое объяснение причин, по которым база данных не подходит.</span><span class="sxs-lookup"><span data-stu-id="f30c5-115">If a database does not meet all of the prerequisites, the **Status** hyperlink provides a brief explanation of why the database is ineligible.</span></span> <span data-ttu-id="f30c5-116">Для получения дополнительных сведений щелкните гиперссылку.</span><span class="sxs-lookup"><span data-stu-id="f30c5-116">For more information, click the hyperlink.</span></span>  
  
 <span data-ttu-id="f30c5-117">Можно выйти из мастера на странице **Выбор базы данных** на время действий, позволяющих сделать так, чтобы база данных отвечала требованиям.</span><span class="sxs-lookup"><span data-stu-id="f30c5-117">You can leave the wizard on the **Select Database** page while you take action on a database to meet a prerequisite.</span></span> <span data-ttu-id="f30c5-118">По возвращении на страницу **Выбор баз данных** нажмите кнопку **Обновить** для обновления сетки.</span><span class="sxs-lookup"><span data-stu-id="f30c5-118">When you return to the **Select Databases** page, click **Refresh** to update the grid.</span></span>  
  
 <span data-ttu-id="f30c5-119">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="f30c5-119">**Refresh**</span></span>  
 <span data-ttu-id="f30c5-120">Щелкните, чтобы обновить сетку.</span><span class="sxs-lookup"><span data-stu-id="f30c5-120">Click to refresh the grid.</span></span> <span data-ttu-id="f30c5-121">Это следует сделать после того, как были приняты действия по приведению базы данных в соответствие требованиям.</span><span class="sxs-lookup"><span data-stu-id="f30c5-121">This is useful after you take action on a database to meet a prerequisite.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="f30c5-122">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="f30c5-122">Related Tasks</span></span>  
  
-   [<span data-ttu-id="f30c5-123">Использование диалогового окна "Создание группы доступности" (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f30c5-123">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="f30c5-124">Использование мастера добавления базы данных в группу доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f30c5-124">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="f30c5-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="f30c5-125">See Also</span></span>  
 <span data-ttu-id="f30c5-126">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f30c5-126">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="f30c5-127">Предварительные требования, ограничения и рекомендации для группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f30c5-127">Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](prereqs-restrictions-recommendations-always-on-availability.md)  
  
  
