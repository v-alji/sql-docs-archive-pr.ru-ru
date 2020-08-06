---
title: Управление всеми предупреждениями на сайте SharePoint в диспетчере предупреждений данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- managing, alerts
- managing, data alerts
ms.assetid: 9c70b0f4-2db8-4c2e-acbf-96e2a55ddc48
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b41fdbd18a0b1b4a7a69a3ca202de1c555c070de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736122"
---
# <a name="manage-all-data-alerts-on-a-sharepoint-site-in-data-alert-manager"></a><span data-ttu-id="925e2-102">Управление всеми предупреждениями данных на сайте SharePoint в диспетчере предупреждений данных</span><span class="sxs-lookup"><span data-stu-id="925e2-102">Manage All Data Alerts on a SharePoint Site in Data Alert Manager</span></span>
  <span data-ttu-id="925e2-103">Администраторы предупреждений SharePoint могут просматривать списки предупреждений об изменении данных, созданных любыми пользователями сайта, и сведения об этих предупреждениях.</span><span class="sxs-lookup"><span data-stu-id="925e2-103">SharePoint alerting administrators can view a list of the data alerts that were created by any site user and information about the alerts.</span></span> <span data-ttu-id="925e2-104">Администраторы системы предупреждений могут также удалять предупреждения.</span><span class="sxs-lookup"><span data-stu-id="925e2-104">Alerting administrators can also delete alerts.</span></span> <span data-ttu-id="925e2-105">На следующем рисунке показаны функции, предоставляемые администраторам предупреждений в диспетчере предупреждений об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="925e2-105">The following picture shows the features available to alerting administrators in Data Alert Manager.</span></span>  
  
 <span data-ttu-id="925e2-106">![Диспетчер предупреждений для администраторов сайта SharePoint](media/rs-alertmanagersite.gif "Диспетчер предупреждений для администраторов сайта SharePoint")</span><span class="sxs-lookup"><span data-stu-id="925e2-106">![Alert Manager for SharePoin tsite administrators](media/rs-alertmanagersite.gif "Alert Manager for SharePoin tsite administrators")</span></span>  
  
### <a name="to-view-a-list-of-alerts-created-by-a-site-user"></a><span data-ttu-id="925e2-107">Просмотр списка предупреждений, созданных пользователем сайта</span><span class="sxs-lookup"><span data-stu-id="925e2-107">To view a list of alerts created by a site user</span></span>  
  
1.  <span data-ttu-id="925e2-108">Перейдите на сайт SharePoint, на котором сохранены определения предупреждений об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="925e2-108">Go to the SharePoint site where data alerts definitions are saved.</span></span>  
  
2.  <span data-ttu-id="925e2-109">На домашней странице выберите **Действия сайта**.</span><span class="sxs-lookup"><span data-stu-id="925e2-109">On the Home page, click **Site Actions**.</span></span>  
  
3.  <span data-ttu-id="925e2-110">Прокрутите список до конца и щелкните **Параметры сайта**.</span><span class="sxs-lookup"><span data-stu-id="925e2-110">Scroll to the bottom of the list and click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="925e2-111">В разделе служб **Reporting Services**щелкните **Управление предупреждениями об изменении данных**.</span><span class="sxs-lookup"><span data-stu-id="925e2-111">Under **Reporting Services**, click **Manage Data Alerts**.</span></span>  
  
5.  <span data-ttu-id="925e2-112">Щелкните стрелку вниз рядом со списком **Просмотр предупреждений для пользователя** и выберите пользователя, чьи предупреждения требуется просмотреть.</span><span class="sxs-lookup"><span data-stu-id="925e2-112">Click the down arrow by the **View alerts for user** list and select the user whose alerts you want to view.</span></span>  
  
6.  <span data-ttu-id="925e2-113">Щелкните стрелку вниз рядом со списком **Просмотр предупреждений для отчета** и выберите конкретные предупреждения или нажмите кнопку **Показать все** , чтобы получить список всех предупреждений, созданных выбранным пользователем.</span><span class="sxs-lookup"><span data-stu-id="925e2-113">Click the down arrow next to the **View alerts for report** list and select a specific alert to view, or click **Show All** to list all alerts created by the selected user.</span></span>  
  
     <span data-ttu-id="925e2-114">В таблице перечисляются имя предупреждения, имя отчета, имя пользователя, создавшего предупреждение об изменении данных, сколько раз предупреждение об изменении данных было отправлено, время, когда в последний раз было изменено определение предупреждения об изменении данных, а также состояние предупреждения об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="925e2-114">A table lists the name, report name, name of the person who created the data alert, the number times the data alert was sent, the last time the data alert definition was modified, and the status of the data alert.</span></span> <span data-ttu-id="925e2-115">Если предупреждение об изменении данных не удалось создать или отправить, в столбце состояния содержатся сведения об ошибке, которые помогают устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="925e2-115">If the data alert cannot be generated or sent, the status column contains information about the error and helps you troubleshoot the problem.</span></span>  
  
### <a name="to-delete-an-alert-definition"></a><span data-ttu-id="925e2-116">Удаление определения предупреждения</span><span class="sxs-lookup"><span data-stu-id="925e2-116">To delete an alert definition</span></span>  
  
-   <span data-ttu-id="925e2-117">Щелкните правой кнопкой мыши предупреждение об изменении данных, которое необходимо удалить, и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="925e2-117">Right-click the data alert that you want to delete and click **Delete**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="925e2-118">После того как предупреждение будет удалено, дальнейшая отправка предупреждающих сообщений прекращается.</span><span class="sxs-lookup"><span data-stu-id="925e2-118">After you delete the alert, no further alert messages are sent.</span></span> <span data-ttu-id="925e2-119">Тем не менее при запросе к базе данных предупреждений может оказаться, что определение предупреждения все еще существует.</span><span class="sxs-lookup"><span data-stu-id="925e2-119">However, if you query the alerting database you might find that the alert definition still exists.</span></span> <span data-ttu-id="925e2-120">Служба предупреждений выполняет очистку по расписанию и окончательно удаляет определение предупреждения при следующей очистке.</span><span class="sxs-lookup"><span data-stu-id="925e2-120">The alerting service performs clean up on a schedule and the alert definition is deleted permanently in the next cleanup.</span></span> <span data-ttu-id="925e2-121">Значение интервала очистки по умолчанию составляет 20 минут.</span><span class="sxs-lookup"><span data-stu-id="925e2-121">The default cleanup interval is 20 minutes.</span></span> <span data-ttu-id="925e2-122">Этот и другие интервалы выполнения очистки являются настраиваемыми.</span><span class="sxs-lookup"><span data-stu-id="925e2-122">This and other cleanup intervals are configurable.</span></span> <span data-ttu-id="925e2-123">Дополнительные сведения см. в разделе [Предупреждения об изменении данных в службах Reporting Services](../ssms/agent/alerts.md).</span><span class="sxs-lookup"><span data-stu-id="925e2-123">For more information, see [Reporting Services Data Alerts](../ssms/agent/alerts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="925e2-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="925e2-124">See Also</span></span>  
 <span data-ttu-id="925e2-125">[Диспетчер предупреждений данных для оповещения администраторов](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="925e2-125">[Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span></span>  
 [<span data-ttu-id="925e2-126">Предупреждения об изменении данных в службах Reporting Services</span><span class="sxs-lookup"><span data-stu-id="925e2-126">Reporting Services Data Alerts</span></span>](../ssms/agent/alerts.md)  
  
  
