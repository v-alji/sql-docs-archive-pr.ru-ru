---
title: Класс событий PreConnect:Starting | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- PreConnect:Starting Event Class
ms.assetid: d43ed0ad-3dbd-42e0-9cef-8320b8d87497
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67b642d369c73cc144af31f835786613766045f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666028"
---
# <a name="preconnectstarting-event-class"></a><span data-ttu-id="5f5f6-102">PreConnect:Starting, класс событий</span><span class="sxs-lookup"><span data-stu-id="5f5f6-102">PreConnect:Starting Event Class</span></span>
  <span data-ttu-id="5f5f6-103">Класс событий PreConnect:Starting показывает, когда начинается выполнение триггера LOGON или функции-классификатора регулятора ресурсов.</span><span class="sxs-lookup"><span data-stu-id="5f5f6-103">The PreConnect:Starting event class indicates when a LOGON trigger or the Resource Governor classifier function starts execution.</span></span>  
  
## <a name="preconnectstarting-event-class-data-columns"></a><span data-ttu-id="5f5f6-104">Столбцы данных класса событий PreConnect:Starting</span><span class="sxs-lookup"><span data-stu-id="5f5f6-104">PreConnect:Starting Event Class Data Columns</span></span>  
  
|<span data-ttu-id="5f5f6-105">Имя столбца данных</span><span class="sxs-lookup"><span data-stu-id="5f5f6-105">Data column name</span></span>|<span data-ttu-id="5f5f6-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="5f5f6-106">Data type</span></span>|<span data-ttu-id="5f5f6-107">Description</span><span class="sxs-lookup"><span data-stu-id="5f5f6-107">Description</span></span>|<span data-ttu-id="5f5f6-108">Идентификатор столбца</span><span class="sxs-lookup"><span data-stu-id="5f5f6-108">Column ID</span></span>|<span data-ttu-id="5f5f6-109">Фильтруемый</span><span class="sxs-lookup"><span data-stu-id="5f5f6-109">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="5f5f6-110">EventClass</span><span class="sxs-lookup"><span data-stu-id="5f5f6-110">EventClass</span></span>|`int`|<span data-ttu-id="5f5f6-111">215</span><span class="sxs-lookup"><span data-stu-id="5f5f6-111">215</span></span>|<span data-ttu-id="5f5f6-112">27</span><span class="sxs-lookup"><span data-stu-id="5f5f6-112">27</span></span>|<span data-ttu-id="5f5f6-113">Нет</span><span class="sxs-lookup"><span data-stu-id="5f5f6-113">No</span></span>|  
|<span data-ttu-id="5f5f6-114">SPID</span><span class="sxs-lookup"><span data-stu-id="5f5f6-114">SPID</span></span>|`int`|<span data-ttu-id="5f5f6-115">Идентификатор процесса сервера, создающего это событие.</span><span class="sxs-lookup"><span data-stu-id="5f5f6-115">The ID of server process that fires this event.</span></span>|<span data-ttu-id="5f5f6-116">12</span><span class="sxs-lookup"><span data-stu-id="5f5f6-116">12</span></span>|<span data-ttu-id="5f5f6-117">Да</span><span class="sxs-lookup"><span data-stu-id="5f5f6-117">Yes</span></span>|  
|<span data-ttu-id="5f5f6-118">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="5f5f6-118">EventSubClass</span></span>|`int`|<span data-ttu-id="5f5f6-119">1 для определяемой пользователем функции-классификатора.</span><span class="sxs-lookup"><span data-stu-id="5f5f6-119">1 for the user-defined classifier function.</span></span>|<span data-ttu-id="5f5f6-120">21</span><span class="sxs-lookup"><span data-stu-id="5f5f6-120">21</span></span>|<span data-ttu-id="5f5f6-121">Да</span><span class="sxs-lookup"><span data-stu-id="5f5f6-121">Yes</span></span>|  
|<span data-ttu-id="5f5f6-122">StartTime</span><span class="sxs-lookup"><span data-stu-id="5f5f6-122">StartTime</span></span>|`datetime`|<span data-ttu-id="5f5f6-123">Время начала выполнения определяемой пользователем функции-классификатора.</span><span class="sxs-lookup"><span data-stu-id="5f5f6-123">The time when the user-defined classifier function starts.</span></span>|<span data-ttu-id="5f5f6-124">14</span><span class="sxs-lookup"><span data-stu-id="5f5f6-124">14</span></span>|<span data-ttu-id="5f5f6-125">Да</span><span class="sxs-lookup"><span data-stu-id="5f5f6-125">Yes</span></span>|  
|<span data-ttu-id="5f5f6-126">ObjectID</span><span class="sxs-lookup"><span data-stu-id="5f5f6-126">ObjectID</span></span>|`int`|<span data-ttu-id="5f5f6-127">Идентификатор определяемого пользователем объекта-классификатора.</span><span class="sxs-lookup"><span data-stu-id="5f5f6-127">The ID of the user-defined classifier object.</span></span>|<span data-ttu-id="5f5f6-128">22</span><span class="sxs-lookup"><span data-stu-id="5f5f6-128">22</span></span>|<span data-ttu-id="5f5f6-129">Да</span><span class="sxs-lookup"><span data-stu-id="5f5f6-129">Yes</span></span>|  
|<span data-ttu-id="5f5f6-130">ObjectName</span><span class="sxs-lookup"><span data-stu-id="5f5f6-130">ObjectName</span></span>|`nvarchar(256)`|<span data-ttu-id="5f5f6-131">Двухкомпонентное имя определяемой пользователем функции-классификатора.</span><span class="sxs-lookup"><span data-stu-id="5f5f6-131">The two-part name of the classifier user-defined function.</span></span> <span data-ttu-id="5f5f6-132">Например, dbo.classifier.</span><span class="sxs-lookup"><span data-stu-id="5f5f6-132">For example, dbo.classifier.</span></span>|<span data-ttu-id="5f5f6-133">34</span><span class="sxs-lookup"><span data-stu-id="5f5f6-133">34</span></span>|<span data-ttu-id="5f5f6-134">Да</span><span class="sxs-lookup"><span data-stu-id="5f5f6-134">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5f5f6-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="5f5f6-135">See Also</span></span>  
 <span data-ttu-id="5f5f6-136">[Расширенные события](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="5f5f6-136">[Extended Events](../extended-events/extended-events.md) </span></span>  
 <span data-ttu-id="5f5f6-137">[Класс событий "Reconnect: Completed"](preconnect-completed-event-class.md) </span><span class="sxs-lookup"><span data-stu-id="5f5f6-137">[PreConnect:Completed Event Class](preconnect-completed-event-class.md) </span></span>  
 [<span data-ttu-id="5f5f6-138">Регулятор ресурсов</span><span class="sxs-lookup"><span data-stu-id="5f5f6-138">Resource Governor</span></span>](../resource-governor/resource-governor.md)  
  
  
