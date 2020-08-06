---
title: Свойства задания и создание задания (страница "Общие") | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.general.f1
ms.assetid: b6832840-1c18-4db8-94fc-080db880ae9f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7a5d2ab84ed211a03a3c217bd5f4cd54453a4dc5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731330"
---
# <a name="job-properties-and-new-job-general-page"></a><span data-ttu-id="9be14-102">Свойства задания и создание задания (страница "Общие")</span><span class="sxs-lookup"><span data-stu-id="9be14-102">Job Properties and New Job (General Page)</span></span>
  <span data-ttu-id="9be14-103">Эта страница используется для просмотра и изменения общих свойств [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] задания агента.</span><span class="sxs-lookup"><span data-stu-id="9be14-103">Use this page to view and modify the general properties of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9be14-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="9be14-104">Options</span></span>  
 <span data-ttu-id="9be14-105">**имя**;</span><span class="sxs-lookup"><span data-stu-id="9be14-105">**Name**</span></span>  
 <span data-ttu-id="9be14-106">Изменение имени задания.</span><span class="sxs-lookup"><span data-stu-id="9be14-106">Change the name of the job.</span></span>  
  
 <span data-ttu-id="9be14-107">**Владелец**</span><span class="sxs-lookup"><span data-stu-id="9be14-107">**Owner**</span></span>  
 <span data-ttu-id="9be14-108">Выбор владельца задания.</span><span class="sxs-lookup"><span data-stu-id="9be14-108">Select the owner for the job.</span></span>  
  
 <span data-ttu-id="9be14-109">**Категория**</span><span class="sxs-lookup"><span data-stu-id="9be14-109">**Category**</span></span>  
 <span data-ttu-id="9be14-110">Выбор категории задания.</span><span class="sxs-lookup"><span data-stu-id="9be14-110">Select the job category for the job.</span></span>  
  
 <span data-ttu-id="9be14-111">**...**</span><span class="sxs-lookup"><span data-stu-id="9be14-111">**...**</span></span>  
 <span data-ttu-id="9be14-112">Просмотр заданий в выбранной категории.</span><span class="sxs-lookup"><span data-stu-id="9be14-112">View the jobs in the selected category.</span></span>  
  
 <span data-ttu-id="9be14-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9be14-113">**Description**</span></span>  
 <span data-ttu-id="9be14-114">Изменение описания задания.</span><span class="sxs-lookup"><span data-stu-id="9be14-114">Change the description of the job.</span></span>  
  
 <span data-ttu-id="9be14-115">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="9be14-115">**Enabled**</span></span>  
 <span data-ttu-id="9be14-116">Включение задания.</span><span class="sxs-lookup"><span data-stu-id="9be14-116">Enable the job.</span></span> <span data-ttu-id="9be14-117">Если задание не включено, оно не будет выполняться по расписанию или предупреждению, но может быть запущено с помощью хранимой процедуры **sp_start_job** .</span><span class="sxs-lookup"><span data-stu-id="9be14-117">When the job is not enabled, the job does not run in response to a schedule or an alert, although you can still start the job using the **sp_start_job** stored procedure.</span></span>  
  
 <span data-ttu-id="9be14-118">**Source**</span><span class="sxs-lookup"><span data-stu-id="9be14-118">**Source**</span></span>  
 <span data-ttu-id="9be14-119">Отображается главный сервер для задания.</span><span class="sxs-lookup"><span data-stu-id="9be14-119">Displays the master server for the job.</span></span> <span data-ttu-id="9be14-120">Доступно только на странице **Свойства задания — общие** .</span><span class="sxs-lookup"><span data-stu-id="9be14-120">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="9be14-121">**Создан**</span><span class="sxs-lookup"><span data-stu-id="9be14-121">**Created**</span></span>  
 <span data-ttu-id="9be14-122">Отображаются дата и время создания задания.</span><span class="sxs-lookup"><span data-stu-id="9be14-122">Displays the date and time that the job was created.</span></span> <span data-ttu-id="9be14-123">Доступно только на странице **Свойства задания — общие** .</span><span class="sxs-lookup"><span data-stu-id="9be14-123">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="9be14-124">**Изменено**</span><span class="sxs-lookup"><span data-stu-id="9be14-124">**Last modified**</span></span>  
 <span data-ttu-id="9be14-125">Отображаются дата и время последнего изменения задания.</span><span class="sxs-lookup"><span data-stu-id="9be14-125">Displays the date and time that the job was last modified.</span></span> <span data-ttu-id="9be14-126">Доступно только на странице **Свойства задания — общие** .</span><span class="sxs-lookup"><span data-stu-id="9be14-126">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="9be14-127">**Последнее выполнение**</span><span class="sxs-lookup"><span data-stu-id="9be14-127">**Last executed**</span></span>  
 <span data-ttu-id="9be14-128">Отображаются дата и время последнего запуска задания.</span><span class="sxs-lookup"><span data-stu-id="9be14-128">Displays the date and time that the job last started running.</span></span> <span data-ttu-id="9be14-129">Доступно только на странице **Свойства задания — общие** .</span><span class="sxs-lookup"><span data-stu-id="9be14-129">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="9be14-130">**Просмотр журнала заданий**</span><span class="sxs-lookup"><span data-stu-id="9be14-130">**View Job History**</span></span>  
 <span data-ttu-id="9be14-131">Просмотр журнала заданий.</span><span class="sxs-lookup"><span data-stu-id="9be14-131">View the job history for the job.</span></span> <span data-ttu-id="9be14-132">Доступно только на странице **Свойства задания — общие** .</span><span class="sxs-lookup"><span data-stu-id="9be14-132">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9be14-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="9be14-133">See Also</span></span>  
 <span data-ttu-id="9be14-134">[Реализация заданий](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="9be14-134">[Implement Jobs](implement-jobs.md) </span></span>  
 [<span data-ttu-id="9be14-135">Категории задания: Управление категориями заданий</span><span class="sxs-lookup"><span data-stu-id="9be14-135">Job Categories: Manage Job Categories</span></span>](job-categories-manage-job-categories.md)  
  
  
