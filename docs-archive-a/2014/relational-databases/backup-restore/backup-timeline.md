---
title: Временная шкала резервного копирования | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.POINTINTIMERESTORE.F1
- sql12.swb.backuptimeline.f1
helpviewer_keywords:
- Backup Timeline
ms.assetid: ae3565f2-ddb2-4469-a992-7531d4f9ebb8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9b075f8c9ec32cfe483c64e34e9f9b4e4b6e80e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668946"
---
# <a name="backup-timeline"></a><span data-ttu-id="85681-102">Временная шкала резервного копирования</span><span class="sxs-lookup"><span data-stu-id="85681-102">Backup Timeline</span></span>
  <span data-ttu-id="85681-103">Диалоговое окно **Временная шкала резервного копирования** служит для поиска и указания резервных копий для восстановления базы данных на момент времени.</span><span class="sxs-lookup"><span data-stu-id="85681-103">Use the **Backup Timeline** dialog box to locate and specify backups to restore a database to a point-in-time.</span></span> <span data-ttu-id="85681-104">Чтобы открыть диалоговое окно **Временная шкала резервного копирования** , нажмите кнопку **Временная шкала** на панели **Восстановление базы данных (страница "Общие")** .</span><span class="sxs-lookup"><span data-stu-id="85681-104">The **Backup Timeline** dialog box is accessed by clicking **Timeline** on the **Restore Database (General Page)** pane.</span></span> <span data-ttu-id="85681-105">В этом диалоговом окне можно просмотреть временную шкалу операций восстановления, применявшихся к базе данных.</span><span class="sxs-lookup"><span data-stu-id="85681-105">This dialog box allows you to view a timeline of the restore operations performed on the database.</span></span>  
  
 <span data-ttu-id="85681-106">Помощник по восстановлению базы данных гарантирует, что будут выбраны только резервные копии, которые необходимы для восстановления из копии до указанного момента времени.</span><span class="sxs-lookup"><span data-stu-id="85681-106">The Database Recovery Advisor ensures that only backups that are required for restoring to that point in time are selected.</span></span> <span data-ttu-id="85681-107">Эти выбранные резервные копии составляют рекомендованный план восстановления для операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="85681-107">These selected backups make up the recommended restore plan for your restore operation.</span></span> <span data-ttu-id="85681-108">Следует использовать только выбранные резервные копии.</span><span class="sxs-lookup"><span data-stu-id="85681-108">You should use only the selected backups.</span></span> <span data-ttu-id="85681-109">Сведения о помощнике по восстановлению базы данных см. в статье [Обзор процессов восстановления (SQL Server)](restore-and-recovery-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="85681-109">For information about the Database Recovery Advisor, see [Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span></span>  
  
## <a name="restore-to"></a><span data-ttu-id="85681-110">Восстановление</span><span class="sxs-lookup"><span data-stu-id="85681-110">Restore to</span></span>  
 <span data-ttu-id="85681-111">По умолчанию выбран вариант**Последняя созданная резервная копия** .</span><span class="sxs-lookup"><span data-stu-id="85681-111">**Last backup taken** is selected by default.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="85681-112">выберет подходящие резервные копии для восстановления базы данных, после чего база данных восстанавливается до момента последнего резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="85681-112">will select the appropriate backups to restore the database, and will restore the database to the point of the last backup.</span></span> <span data-ttu-id="85681-113">Установите флажок **Указанные дата и время** , чтобы вручную задать дату и время (выбрав определенный момент времени).</span><span class="sxs-lookup"><span data-stu-id="85681-113">Click **A specific date and time** to manually set the date and time (selecting a specific point in time).</span></span>  
  
 <span data-ttu-id="85681-114">Вариант**Конкретные дата и время** позволяет остановить восстановление на конкретном выбранном значении даты и времени.</span><span class="sxs-lookup"><span data-stu-id="85681-114">**Specific date and time** permits you stop the restore at a specific date and time that you select.</span></span> <span data-ttu-id="85681-115">Временная шкала показывает представление операций резервного копирования, выполняемых в течение 24 часов от выбранных значений даты и времени.</span><span class="sxs-lookup"><span data-stu-id="85681-115">The timeline shows a representation of the backup operations performed in the 24 hours around the select date and time.</span></span>  
  
 <span data-ttu-id="85681-116">**Дата**</span><span class="sxs-lookup"><span data-stu-id="85681-116">**Date**</span></span>  
 <span data-ttu-id="85681-117">Введите или выберите дату из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="85681-117">Enter or select a date from the drop-down list.</span></span>  
  
 <span data-ttu-id="85681-118">**Time**</span><span class="sxs-lookup"><span data-stu-id="85681-118">**Time**</span></span>  
 <span data-ttu-id="85681-119">Введите или выберите дату для назначения конкретного момента времени, чтобы остановить восстановление.</span><span class="sxs-lookup"><span data-stu-id="85681-119">Enter or select a date to designate the specific point-in-time for the restore to stop.</span></span>  
  
 <span data-ttu-id="85681-120">**Интервал определения временной шкалы**</span><span class="sxs-lookup"><span data-stu-id="85681-120">**Timeline Interval**</span></span>  
 <span data-ttu-id="85681-121">Показывает параметры для типов интервалов, отображаемых на временной шкале.</span><span class="sxs-lookup"><span data-stu-id="85681-121">Displays the options for the interval types viewable on the timeline.</span></span>  
  
## <a name="timeline-and-legend"></a><span data-ttu-id="85681-122">Временная шкала и условные обозначения</span><span class="sxs-lookup"><span data-stu-id="85681-122">Timeline and Legend</span></span>  
 <span data-ttu-id="85681-123">Для перемещения курсора вперед и назад по линии временной шкалы служит расположенная под этой линией полоса прокрутки.</span><span class="sxs-lookup"><span data-stu-id="85681-123">Use the scroll bar beneath the timeline to move the cursor forward and backward along the timeline.</span></span> <span data-ttu-id="85681-124">Щелкните резервную копию, чтобы переместить позицию в полосе прокрутки к концу этой резервной копии.</span><span class="sxs-lookup"><span data-stu-id="85681-124">Click on a backup to move the scroll bar to the end of that backup.</span></span> <span data-ttu-id="85681-125">Установите указатель мыши над маркером, чтобы вывести на экран всплывающую подсказку, содержащую сведения о выбранном резервном наборе данных.</span><span class="sxs-lookup"><span data-stu-id="85681-125">Hover the mouse over a marker to display a ScreenTip providing information about the selected backup set.</span></span> <span data-ttu-id="85681-126">Сведения о резервной копии отображаются на временной шкале с помощью следующих маркеров.</span><span class="sxs-lookup"><span data-stu-id="85681-126">Backup information is shown on the timeline by the following markers.</span></span>  
  
 <span data-ttu-id="85681-127">Большой треугольник</span><span class="sxs-lookup"><span data-stu-id="85681-127">Larger triangle</span></span>  
 <span data-ttu-id="85681-128">Представляет полные резервные копии, созданные для базы данных, и отмечает конкретный момент времени проведения полного резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="85681-128">Represents the full backups performed on the database, denoting the specific point in time each full backup was performed.</span></span>  
  
 <span data-ttu-id="85681-129">Маленький треугольник</span><span class="sxs-lookup"><span data-stu-id="85681-129">Smaller triangle</span></span>  
 <span data-ttu-id="85681-130">Представляет разностные резервные копии, созданные для базы данных, и отмечает конкретный момент времени проведения каждого разностного резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="85681-130">Represents the differential backups performed on the database, denoting the specific point in time that each differential backup was performed.</span></span>  
  
 <span data-ttu-id="85681-131">Зеленые затененные области</span><span class="sxs-lookup"><span data-stu-id="85681-131">Green shaded areas</span></span>  
 <span data-ttu-id="85681-132">Представляют покрытие резервной копии журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="85681-132">Represents the transaction log backup coverage.</span></span>  
  
 <span data-ttu-id="85681-133">Красная линия</span><span class="sxs-lookup"><span data-stu-id="85681-133">Red line</span></span>  
 <span data-ttu-id="85681-134">Может размещаться на временной шкале только там, где возможно восстановление.</span><span class="sxs-lookup"><span data-stu-id="85681-134">Can only be positioned along the timeline where the restore is possible.</span></span> <span data-ttu-id="85681-135">Перемещая красную линию вдоль временной шкалы, можно откорректировать дату и время в полях **Дата** и **Время** .</span><span class="sxs-lookup"><span data-stu-id="85681-135">Moving the red line along the timeline adjusts the date and time displayed in the **Date** and **Time** boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85681-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="85681-136">See Also</span></span>  
 [<span data-ttu-id="85681-137">Восстановление базы данных (страница "Общие")</span><span class="sxs-lookup"><span data-stu-id="85681-137">Restore Database &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
  
