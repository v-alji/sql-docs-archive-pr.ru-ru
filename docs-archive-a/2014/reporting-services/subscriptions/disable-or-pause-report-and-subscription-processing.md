---
title: Приостановка обработки отчетов и подписок | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- pausing schedules
- subscriptions [Reporting Services], pausing
- report processing [Reporting Services], pausing
- shared data sources [Reporting Services]
- pausing subscription processing
- pausing report processing
- temporarily stopping report processing
- disabling shared data sources
- roles [Reporting Services], modifying
- shared schedules [Reporting Services], pausing
ms.assetid: 3cf9a240-24cc-46d4-bec6-976f82d8f830
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1607637630c507588602dd7e566917ce1eeb6080
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736010"
---
# <a name="pause-report-and-subscription-processing"></a><span data-ttu-id="31b41-102">Приостановка обработки отчета и подписки</span><span class="sxs-lookup"><span data-stu-id="31b41-102">Pause Report and Subscription Processing</span></span>
  <span data-ttu-id="31b41-103">Приостановить обработку отчетов или подписки напрямую невозможно.</span><span class="sxs-lookup"><span data-stu-id="31b41-103">You cannot pause a report or subscription directly.</span></span> <span data-ttu-id="31b41-104">Однако можно остановить обработку отчетов и подписки перед ее началом или после соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="31b41-104">However, you can interrupt report and subscription processing prior to the process starting or when a data source connection is made.</span></span> <span data-ttu-id="31b41-105">Также можно предотвратить обработку отчетов или подписки, запретив пользователям доступ к этим элементам.</span><span class="sxs-lookup"><span data-stu-id="31b41-105">You can also prevent a report or subscription from processing by making it inaccessible to users.</span></span>  
  
 <span data-ttu-id="31b41-106">Можно использовать перечисленные далее стратегии для установки временного запрета на процесс обработки.</span><span class="sxs-lookup"><span data-stu-id="31b41-106">The following strategies can be used to temporarily prevent a process from occurring.</span></span>  
  
## <a name="modify-role-assignments-to-prevent-access"></a><span data-ttu-id="31b41-107">Изменение назначений ролей для предотвращения доступа</span><span class="sxs-lookup"><span data-stu-id="31b41-107">Modify Role Assignments to Prevent Access</span></span>  
 <span data-ttu-id="31b41-108">Чтобы сделать отчет недоступным, лучше всего временно удалить назначение роли, которое предоставляет доступ к отчету.</span><span class="sxs-lookup"><span data-stu-id="31b41-108">The best way to make a report unavailable is to temporarily remove the role assignment that provides access to the report.</span></span> <span data-ttu-id="31b41-109">Этот подход можно использовать для всех отчетов независимо от того, было ли создано соединение с источником данных.</span><span class="sxs-lookup"><span data-stu-id="31b41-109">This approach can be used on all reports regardless of how the data source connection is made.</span></span> <span data-ttu-id="31b41-110">Этот подход затрагивает только конкретный отчет, не влияя на работу остальных отчетов или других элементов.</span><span class="sxs-lookup"><span data-stu-id="31b41-110">This approach targets only the report, without affecting the operation of other reports or items.</span></span>  
  
 <span data-ttu-id="31b41-111">Для удаления назначения ролей откройте страницу «Свойства безопасности» для отчета в диспетчере отчетов.</span><span class="sxs-lookup"><span data-stu-id="31b41-111">To remove the role assignment, open the Security Properties page of the report in Report Manager.</span></span> <span data-ttu-id="31b41-112">Если отчет наследует свойства безопасности от родительского объекта, то можно выбрать пункт **Изменить параметры безопасности элемента** , чтобы создать ограничивающую политику безопасности, исключающую назначения роли, которые обеспечивают доступ большому количеству пользователей (например, можно удалить назначения роли, которые предоставляют доступ всем пользователям, и оставить назначения роли, которые предоставляют доступ небольшой группе пользователей, например администраторам).</span><span class="sxs-lookup"><span data-stu-id="31b41-112">If the report inherits security from a parent, you can click **Edit Item Security** to create a restrictive security policy that omits role assignments that provide widespread access (for example, you can remove a role assignment that provides access to Everyone, and keep the role assignment that provides access to a small group of users, such as Administrators).</span></span>  
  
## <a name="disable-a-shared-data-source"></a><span data-ttu-id="31b41-113">Отключение общего источника данных</span><span class="sxs-lookup"><span data-stu-id="31b41-113">Disable a Shared Data Source</span></span>  
 <span data-ttu-id="31b41-114">Одним из преимуществ использования общих источников данных является возможность отключения их, что позволяет избежать формирования отчета или запуска управляемой данными подписки.</span><span class="sxs-lookup"><span data-stu-id="31b41-114">One advantage to using shared data sources is that you can disable it to prevent a report or data-driven subscription from running.</span></span> <span data-ttu-id="31b41-115">При отключении общих источников данных происходит разрыв соединения между отчетом и его внешним источником.</span><span class="sxs-lookup"><span data-stu-id="31b41-115">Disabling a shared data source disconnects the report from its external source.</span></span> <span data-ttu-id="31b41-116">После отключения источник данных становится недоступным для всех отчетов и подписок, которые его использовали.</span><span class="sxs-lookup"><span data-stu-id="31b41-116">While it is disabled, the data source is unavailable to all reports and subscriptions that use it.</span></span> <span data-ttu-id="31b41-117">Для отключения общего источника данных откройте источник данных в диспетчере отчетов и снимите флажок с пункта **Включить этот источник данных** .</span><span class="sxs-lookup"><span data-stu-id="31b41-117">To disable a shared data source, open the data source in Report Manager and clear the **Enable this data source** check box.</span></span>  
  
 <span data-ttu-id="31b41-118">Обратите внимание на то, что отчет продолжает загружаться, даже если источник данных недоступен.</span><span class="sxs-lookup"><span data-stu-id="31b41-118">Note that the report still loads even if the data source is unavailable.</span></span> <span data-ttu-id="31b41-119">В отчете не содержится данных, но пользователи, обладающие соответствующими разрешениями, имеют доступ к страницам свойств отчета, настройкам безопасности, журналу отчета и информации о подписке, связанной с данным отчетом.</span><span class="sxs-lookup"><span data-stu-id="31b41-119">The report does not contain data, but users with appropriate permissions can access the property pages, security settings, report history, and subscription information associated with the report.</span></span>  
  
## <a name="pause-a-shared-schedule"></a><span data-ttu-id="31b41-120">Приостановка общего расписания</span><span class="sxs-lookup"><span data-stu-id="31b41-120">Pause a Shared Schedule</span></span>  
 <span data-ttu-id="31b41-121">Если отчет или подписка выполняется по общему расписанию, можно приостановить расписание для предотвращения процесса обработки.</span><span class="sxs-lookup"><span data-stu-id="31b41-121">If a report or subscription runs from a shared schedule, you can pause the schedule to prevent processing.</span></span> <span data-ttu-id="31b41-122">Обработка всех отчетов и подписок, управляемая данным расписанием, откладывается до возобновления выполнения расписания.</span><span class="sxs-lookup"><span data-stu-id="31b41-122">All report and subscription processing that is driven by the schedule is deferred until the schedule is resumed.</span></span> <span data-ttu-id="31b41-123">Дополнительные сведения см. в разделе [Приостановка и возобновление общих расписаний](schedules.md).</span><span class="sxs-lookup"><span data-stu-id="31b41-123">For more information, see [Pause and Resume Shared Schedules](schedules.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31b41-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="31b41-124">See Also</span></span>  
 <span data-ttu-id="31b41-125">[Сервер отчетов служб Reporting Services (основной режим)](../report-server/reporting-services-report-server-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="31b41-125">[Reporting Services Report Server &#40;Native Mode&#41;](../report-server/reporting-services-report-server-native-mode.md) </span></span>  
 <span data-ttu-id="31b41-126">[Диспетчер отчетов (службы Reporting Services в основном режиме)](../report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="31b41-126">[Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="31b41-127">Страница "Свойства безопасности", элементы (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="31b41-127">Security Properties Page, Items &#40;Report Manager&#41;</span></span>](../security-properties-page-items-report-manager.md)  
  
  
