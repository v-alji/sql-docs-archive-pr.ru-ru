---
title: Изменение предупреждения о данных в конструкторе предупреждений | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- editing, data alerts
- updating, data alerts
- editing, alerts
- updating, alerts
ms.assetid: dde3664d-90b5-4b12-969e-39152c86e58a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9906b33ae50d51733eaec1bf5c201c9f5b5d120e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735070"
---
# <a name="edit-a-data-alert-in-alert-designer"></a><span data-ttu-id="7c175-102">изменить предупреждение в конструкторе предупреждений</span><span class="sxs-lookup"><span data-stu-id="7c175-102">Edit a Data Alert in Alert Designer</span></span>
  <span data-ttu-id="7c175-103">Если вы хотите изменить определение предупреждения об изменении данных, его следует открыть в диспетчере предупреждений об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="7c175-103">You open the data alert definition that you want to edit from Data Alert Manager.</span></span> <span data-ttu-id="7c175-104">Изменить определение предупреждения может только пользователь, который его создал.</span><span class="sxs-lookup"><span data-stu-id="7c175-104">Only the user that created the alert definition can edit it.</span></span> <span data-ttu-id="7c175-105">Дополнительные сведения об открытии диспетчера предупреждений данных см. в разделе [Управление предупреждениями данных в диспетчере предупреждений данных](manage-my-data-alerts-in-data-alert-manager.md).</span><span class="sxs-lookup"><span data-stu-id="7c175-105">For more information about opening Data Alert Manager, see [Manage My Data Alerts in Data Alert Manager](manage-my-data-alerts-in-data-alert-manager.md).</span></span>

 <span data-ttu-id="7c175-106">На следующем рисунке показано контекстное меню предупреждения об изменении данных в диспетчере предупреждений об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="7c175-106">The following picture shows you the context menu on a data alert in Data Alert Manager.</span></span>

 <span data-ttu-id="7c175-107">![Открытие конструктора предупреждений о данных нажатием кнопки "Правка"](media/rs-alertmanageriwopendesigner.gif "Открытие конструктора предупреждений о данных нажатием кнопки "Правка"")</span><span class="sxs-lookup"><span data-stu-id="7c175-107">![Open Data Alert Designer by clicking Edit](media/rs-alertmanageriwopendesigner.gif "Open Data Alert Designer by clicking Edit")</span></span>

 <span data-ttu-id="7c175-108">Следующая процедура включает в себя шаги по открытию определения предупреждения для изменения в конструкторе предупреждений об изменении данных из диспетчера предупреждений об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="7c175-108">The following procedure includes the steps to open the alert definition for editing in Data Alert Designer from Data Alert Manager.</span></span>

### <a name="to-edit-a-data-alert-definition-in-data-alert-designer"></a><span data-ttu-id="7c175-109">Редактирование определения предупреждения об изменении данных в конструкторе предупреждений об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="7c175-109">To edit a data alert definition in Data Alert Designer</span></span>

1.  <span data-ttu-id="7c175-110">Щелкните правой кнопкой мыши определение предупреждения об изменении данных, которое требуется изменить в диспетчере предупреждений об изменении данных, и выберите команду **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="7c175-110">In Data Alert Manager, right-click the data alert definition that you want to edit and click **Edit**.</span></span>

     <span data-ttu-id="7c175-111">Определение предупреждения откроется в конструкторе предупреждений об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="7c175-111">The alert definition opens in Data Alert Designer.</span></span>

2.  <span data-ttu-id="7c175-112">Обновите правила, параметры расписания и параметры электронной почты.</span><span class="sxs-lookup"><span data-stu-id="7c175-112">Update the rules, schedule settings, and email settings.</span></span> <span data-ttu-id="7c175-113">Дополнительные сведения см. в разделах [Конструктор предупреждений данных](../../2014/reporting-services/data-alert-designer.md) и [Создание предупреждения данных в конструкторе предупреждений данных](create-a-data-alert-in-data-alert-designer.md).</span><span class="sxs-lookup"><span data-stu-id="7c175-113">For more information, see [Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) and [Create a Data Alert in Data Alert Designer](create-a-data-alert-in-data-alert-designer.md).</span></span>

    > [!NOTE]
    >  <span data-ttu-id="7c175-114">Выбрать другой веб-канал данных нельзя.</span><span class="sxs-lookup"><span data-stu-id="7c175-114">You cannot choose a different data feed.</span></span> <span data-ttu-id="7c175-115">Чтобы использовать другой веб-канал данных, следует создать новое определение предупреждения об изменении данных.</span><span class="sxs-lookup"><span data-stu-id="7c175-115">To use a different data feed, you must create a new data alert definition.</span></span>

3.  <span data-ttu-id="7c175-116">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7c175-116">Click **Save**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="7c175-117">Если отчет был изменен и изменились веб-каналы данных, созданные на основе отчета, то определение предупреждения может стать недопустимым.</span><span class="sxs-lookup"><span data-stu-id="7c175-117">If the report has changed and the data feeds generated from the report have changed the alert definition might no longer be valid.</span></span> <span data-ttu-id="7c175-118">Это происходит, когда столбец, на который ссылается определение предупреждения в своих правилах, удаляется из отчета или меняет тип данных, или если отчет удаляется или перемещается.</span><span class="sxs-lookup"><span data-stu-id="7c175-118">This occurs when a column that the alert definition references in its rules is deleted from the report or changes data type or the report is deleted or moved.</span></span> <span data-ttu-id="7c175-119">Недопустимое определение предупреждения можно открыть, но нельзя повторно сохранить до тех пор, пока оно не станет допустимым для текущей версии веб-канала данных отчета, на котором оно основано.</span><span class="sxs-lookup"><span data-stu-id="7c175-119">You can open an alert definition that is not valid, but you cannot resave it until it is valid based on the current version of the report data feed that it is built upon.</span></span> <span data-ttu-id="7c175-120">Дополнительные сведения о создании веб-каналов данных на основе отчетов см. в разделе [Формирование веб-каналов данных из отчетов (построитель отчетов и службы SSRS)](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7c175-120">To learn more about how data feeds are generated from reports, see [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7c175-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="7c175-121">See Also</span></span>
 <span data-ttu-id="7c175-122">[Диспетчер предупреждений об изменении данных для оповещений администраторов](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services предупреждения](../ssms/agent/alerts.md) об изменении данных</span><span class="sxs-lookup"><span data-stu-id="7c175-122">[Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>


