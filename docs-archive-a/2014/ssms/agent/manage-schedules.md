---
title: Управление расписаниями | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.manageschedules.f1
ms.assetid: f56c0736-dccc-41d2-afcf-71344aff143a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6fa18d620d630484815966372d5de83bb52e8caf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658062"
---
# <a name="manage-schedules"></a><span data-ttu-id="5c8c7-102">Управление расписаниями</span><span class="sxs-lookup"><span data-stu-id="5c8c7-102">Manage Schedules</span></span>
  <span data-ttu-id="5c8c7-103">Позволяет просматривать и изменять свойства [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] расписаний заданий агента.</span><span class="sxs-lookup"><span data-stu-id="5c8c7-103">Allows you to view and change properties for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job schedules.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5c8c7-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="5c8c7-104">Options</span></span>  
 <span data-ttu-id="5c8c7-105">**Доступные расписания**</span><span class="sxs-lookup"><span data-stu-id="5c8c7-105">**Available schedules**</span></span>  
 <span data-ttu-id="5c8c7-106">Приводит список расписаний, доступных пользователю.</span><span class="sxs-lookup"><span data-stu-id="5c8c7-106">Lists the schedules available for this user.</span></span> <span data-ttu-id="5c8c7-107">Обратите внимание, что у задания и у расписания должен быть один владелец.</span><span class="sxs-lookup"><span data-stu-id="5c8c7-107">Notice that a job and a schedule must have the same owner.</span></span> <span data-ttu-id="5c8c7-108">Следовательно, в этом списке приводятся только расписания, которые принадлежат владельцу задания.</span><span class="sxs-lookup"><span data-stu-id="5c8c7-108">Therefore, this list only includes schedules owned by the owner of the job.</span></span>  
  
 <span data-ttu-id="5c8c7-109">**имя**;</span><span class="sxs-lookup"><span data-stu-id="5c8c7-109">**Name**</span></span>  
 <span data-ttu-id="5c8c7-110">Отображает имя расписания.</span><span class="sxs-lookup"><span data-stu-id="5c8c7-110">Displays the name of the schedule.</span></span>  
  
 <span data-ttu-id="5c8c7-111">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="5c8c7-111">**Enabled**</span></span>  
 <span data-ttu-id="5c8c7-112">Выберите этот параметр, чтобы включить расписание.</span><span class="sxs-lookup"><span data-stu-id="5c8c7-112">Select this option to enable the schedule.</span></span>  
  
 <span data-ttu-id="5c8c7-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5c8c7-113">**Description**</span></span>  
 <span data-ttu-id="5c8c7-114">Описывает условия, при которых расписание запускает задание.</span><span class="sxs-lookup"><span data-stu-id="5c8c7-114">Describes the conditions under which the schedule runs the job.</span></span>  
  
 <span data-ttu-id="5c8c7-115">**Задания в расписании**</span><span class="sxs-lookup"><span data-stu-id="5c8c7-115">**Jobs in schedule**</span></span>  
 <span data-ttu-id="5c8c7-116">Приводит список номеров заданий, внесенных в расписание.</span><span class="sxs-lookup"><span data-stu-id="5c8c7-116">Lists the job numbers attached to the schedule.</span></span> <span data-ttu-id="5c8c7-117">Щелкните номер, чтобы увидеть свойства задания.</span><span class="sxs-lookup"><span data-stu-id="5c8c7-117">Click a number to view the properties of the job.</span></span>  
  
 <span data-ttu-id="5c8c7-118">**Создать**</span><span class="sxs-lookup"><span data-stu-id="5c8c7-118">**New**</span></span>  
 <span data-ttu-id="5c8c7-119">Нажмите эту кнопку, чтобы создать новое расписание.</span><span class="sxs-lookup"><span data-stu-id="5c8c7-119">Click this button to create a new schedule.</span></span>  
  
 <span data-ttu-id="5c8c7-120">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="5c8c7-120">**Delete**</span></span>  
 <span data-ttu-id="5c8c7-121">Нажмите эту кнопку, чтобы удалить выбранное расписание.</span><span class="sxs-lookup"><span data-stu-id="5c8c7-121">Click this button to delete the selected schedule.</span></span>  
  
 <span data-ttu-id="5c8c7-122">**Свойства**</span><span class="sxs-lookup"><span data-stu-id="5c8c7-122">**Properties**</span></span>  
 <span data-ttu-id="5c8c7-123">Нажмите эту кнопку, чтобы изменить свойства выбранного расписания.</span><span class="sxs-lookup"><span data-stu-id="5c8c7-123">Click this button to change the properties of the selected schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c8c7-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="5c8c7-124">See Also</span></span>  
 [<span data-ttu-id="5c8c7-125">Создание и присоединение расписаний к заданиям</span><span class="sxs-lookup"><span data-stu-id="5c8c7-125">Create and Attach Schedules to Jobs</span></span>](create-and-attach-schedules-to-jobs.md)  
  
  
