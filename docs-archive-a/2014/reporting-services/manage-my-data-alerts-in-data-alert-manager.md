---
title: Управление предупреждениями данных в диспетчере предупреждений данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- managing, alerts
- managing, data alerts
ms.assetid: e0e4ffdf-bd4c-4ebd-872b-07486cbb47c2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 371c62c2f97334e20280a659c8039ab20852ccfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736125"
---
# <a name="manage-my-data-alerts-in-data-alert-manager"></a><span data-ttu-id="3ee0f-102">Управление предупреждениями данных в диспетчере предупреждений данных</span><span class="sxs-lookup"><span data-stu-id="3ee0f-102">Manage My Data Alerts in Data Alert Manager</span></span>
  <span data-ttu-id="3ee0f-103">Пользователи SharePoint могут просматривать список созданных ими предупреждений об изменении данных и сведения о них.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-103">SharePoint users can view a list of the data alerts that they created and information about the alerts.</span></span> <span data-ttu-id="3ee0f-104">Также вы можете удалять свои предупреждения, открывать определения предупреждений для их изменения в конструкторе предупреждений об изменении данных и запускать свои предупреждения.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-104">Users can also delete their alerts, open alert definitions for edit in Data Alert Designer, and run their alerts.</span></span> <span data-ttu-id="3ee0f-105">На следующем рисунке показаны функции, доступные пользователям в диспетчере предупреждений об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-105">The following picture shows the features available to users in Data Alert Manager.</span></span>  
  
 <span data-ttu-id="3ee0f-106">![Возможности диспетчера предупреждений для пользователей SharePoint](media/rs-alertmanageriw.gif "Возможности диспетчера предупреждений для пользователей SharePoint")</span><span class="sxs-lookup"><span data-stu-id="3ee0f-106">![Alert Manager features for SharePoint users](media/rs-alertmanageriw.gif "Alert Manager features for SharePoint users")</span></span>  
  
### <a name="to-view-a-list-of-your-alerts"></a><span data-ttu-id="3ee0f-107">Просмотр списка своих предупреждений</span><span class="sxs-lookup"><span data-stu-id="3ee0f-107">To view a list of your alerts</span></span>  
  
1.  <span data-ttu-id="3ee0f-108">Перейдите к библиотеке документов SharePoint, в которой сохранены отчеты, для которых были созданы предупреждения об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-108">Go to the SharePoint library where you saved the reports on which you created data alerts.</span></span>  
  
2.  <span data-ttu-id="3ee0f-109">Щелкните значок, чтобы развернуть раскрывающееся меню для отчета, и выберите пункт **Управление предупреждениями об изменении данных**.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-109">Click the icon for the expand drop-down menu on a report and click **Manage Data Alerts**.</span></span> <span data-ttu-id="3ee0f-110">Раскрывающееся меню показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-110">The following picture shows the drop-down menu.</span></span>  
  
     <span data-ttu-id="3ee0f-111">![Открытие конструктора предупреждений из контекстного меню отчета](media/rs-openalertmanager.gif "Открытие конструктора предупреждений из контекстного меню отчета")</span><span class="sxs-lookup"><span data-stu-id="3ee0f-111">![Open Alert Manager from report context menu](media/rs-openalertmanager.gif "Open Alert Manager from report context menu")</span></span>  
  
     <span data-ttu-id="3ee0f-112">Откроется диспетчер предупреждений об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-112">Data Alert Manager opens.</span></span> <span data-ttu-id="3ee0f-113">По умолчанию в нем перечислены предупреждения для отчета, выбранного в библиотеке.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-113">By default, it lists the alerts for the report that you selected in the library.</span></span>  
  
3.  <span data-ttu-id="3ee0f-114">Щелкните стрелку вниз рядом со списком **Просмотр предупреждений для отчета** и выберите отчет для просмотра его предупреждений или нажмите кнопку **Показать все** , чтобы получить список всех предупреждений.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-114">Click the down arrow next to the **View alerts for report** list and select a report to view its alerts, or click **Show All** to list all alerts.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3ee0f-115">Если выбранный отчет не имеет предупреждений, то возвращаться в библиотеку и искать отчет, имеющий их, не требуется.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-115">If the report that you selected does not have any alerts, you do not have to return to the SharePoint library to locate and select a report that hasalerts.</span></span> <span data-ttu-id="3ee0f-116">Вместо этого щелкните **Показать все** , чтобы увидеть список всех предупреждений.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-116">Instead, click **Show All** to see a list of all your alerts.</span></span>  
  
     <span data-ttu-id="3ee0f-117">Таблица содержит имя предупреждения, имя отчета, ваше имя в качестве имени создателя предупреждения, сколько раз предупреждение было отправлено, время последнего изменения определения предупреждения и состояние предупреждения.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-117">A table lists the alert name, report name, your name as the creator of the alert, the number the alert was sent, the last time the alert definition was modified, and the status of the alert.</span></span> <span data-ttu-id="3ee0f-118">Если предупреждение не удалось создать или отправить, в столбце состояния содержатся сведения об ошибке, которые помогают устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-118">If the alert cannot be generated or sent, the status column contains information about the error and helps you troubleshoot the problem.</span></span>  
  
### <a name="to-edit-an-alert-definition"></a><span data-ttu-id="3ee0f-119">Редактирование определения предупреждения</span><span class="sxs-lookup"><span data-stu-id="3ee0f-119">To edit an alert definition</span></span>  
  
-   <span data-ttu-id="3ee0f-120">Щелкните правой кнопкой мыши предупреждение, определение которого требуется изменить, и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-120">Right-click the data alert for which you want to edit the alert definition and click **Edit**.</span></span>  
  
     <span data-ttu-id="3ee0f-121">Определение предупреждения откроется в конструкторе предупреждений об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-121">The alert definition opens in Data Alert Designer.</span></span> <span data-ttu-id="3ee0f-122">Дополнительные сведения см. в разделах [Изменение предупреждения в конструкторе предупреждений](edit-a-data-alert-in-alert-designer.md) и [Конструктор предупреждений данных](../../2014/reporting-services/data-alert-designer.md).</span><span class="sxs-lookup"><span data-stu-id="3ee0f-122">For more information, see [Edit a Data Alert in Alert Designer](edit-a-data-alert-in-alert-designer.md) and [Data Alert Designer](../../2014/reporting-services/data-alert-designer.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3ee0f-123">Изменить определение предупреждения об изменении данных может только пользователь, который его создал.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-123">Only the user that created the data alert definition can edit it.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3ee0f-124">Если отчет был изменен и изменились веб-каналы данных, созданные на основе отчета, то определение предупреждения может стать недопустимым.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-124">If the report has changed and the data feeds generated from the report have changed the alert definition might no longer be valid.</span></span> <span data-ttu-id="3ee0f-125">Это происходит, когда столбец, на который ссылается предупреждение в своих правилах, удаляется из отчета, меняет тип данных или включается в другой веб-канал данных или в случае, когда отчет был удален или перемещен.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-125">This occurs when a column that the alert references in its rules is deleted from the report, changes data type, or is included in a different data feed or the report is deleted or moved.</span></span> <span data-ttu-id="3ee0f-126">Недопустимое определение предупреждения можно открыть, но нельзя повторно сохранить до тех пор, пока оно не станет допустимым для текущей версии веб-канала данных отчета, на котором оно основано.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-126">You can open an alert definition that is not valid, but you cannot resave it until it is valid based on the current version of the report data feed that it is built upon.</span></span> <span data-ttu-id="3ee0f-127">Дополнительные сведения о создании веб-каналов данных на основе отчетов см. в разделе [Формирование веб-каналов данных из отчетов (построитель отчетов и службы SSRS)](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3ee0f-127">To learn more about how data feeds are generated from reports, see [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-delete-an-alert-definition"></a><span data-ttu-id="3ee0f-128">Удаление определения предупреждения</span><span class="sxs-lookup"><span data-stu-id="3ee0f-128">To delete an alert definition</span></span>  
  
-   <span data-ttu-id="3ee0f-129">Щелкните правой кнопкой мыши предупреждение об изменении данных, которое необходимо удалить, и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-129">Right-click the data alert that you want to delete and click **Delete**.</span></span>  
  
     <span data-ttu-id="3ee0f-130">Если предупреждение было удалено, дальнейшая отправка предупреждающих сообщений прекращается.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-130">When you delete the alert, no further alert messages are sent.</span></span>  
  
### <a name="to-run-an-alert"></a><span data-ttu-id="3ee0f-131">Запуск предупреждения</span><span class="sxs-lookup"><span data-stu-id="3ee0f-131">To run an alert</span></span>  
  
-   <span data-ttu-id="3ee0f-132">Щелкните правой кнопкой мыши предупреждение об изменении данных, которое необходимо запустить, и выберите пункт **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-132">Right-click the data alert that you want to run and click **Run**.</span></span>  
  
     <span data-ttu-id="3ee0f-133">Вне зависимости от того, какие параметры расписания были заданы в диспетчере предупреждений об изменении данных, будет создан экземпляр предупреждения и будет немедленно отправлено предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-133">The alert instance is created and the data alert message is immediately sent, regardless of the schedule options you specified in Data Alert Designer.</span></span> <span data-ttu-id="3ee0f-134">Например, предупреждение, настроенное на еженедельную отправку и только в случае изменения результатов.</span><span class="sxs-lookup"><span data-stu-id="3ee0f-134">For example, an alert configured to be sent weekly and then only if the results change is sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ee0f-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="3ee0f-135">See Also</span></span>  
 <span data-ttu-id="3ee0f-136">[Диспетчер предупреждений данных для оповещения администраторов](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="3ee0f-136">[Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span></span>  
 [<span data-ttu-id="3ee0f-137">Предупреждения об изменении данных в службах Reporting Services</span><span class="sxs-lookup"><span data-stu-id="3ee0f-137">Reporting Services Data Alerts</span></span>](../ssms/agent/alerts.md)  
  
  
