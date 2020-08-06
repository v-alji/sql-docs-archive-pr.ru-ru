---
title: Удаление объектов из каталога (среда Management Studio) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.deleteitems.f1
ms.assetid: b0599e01-6dc3-4484-80d4-022a412e0ebd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d2a1824f2611165c9ae891fcb702418244f3621e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658648"
---
# <a name="delete-catalog-items-management-studio"></a><span data-ttu-id="d0e2b-102">Удаление объектов из каталога (среда Management Studio)</span><span class="sxs-lookup"><span data-stu-id="d0e2b-102">Delete Catalog Items (Management Studio)</span></span>
  <span data-ttu-id="d0e2b-103">Используйте эту страницу для удаления общих расписаний и определений ролей.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-103">Use this page to delete shared schedules and role definitions.</span></span>  
  
 <span data-ttu-id="d0e2b-104">При удалении общего расписания, используемого несколькими отчетами и подписками, сервер отчетов создаст для каждого из них отдельное расписание.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-104">If you delete a shared schedule that is used by multiple reports and subscriptions, the report server will create individual schedules for each report and subscription that previously used the shared schedule.</span></span> <span data-ttu-id="d0e2b-105">В созданных расписаниях будут содержаться дата, время и шаблон повторений, которые были заданы в общем расписании.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-105">Each new individual schedule will contain the date, time, and recurrence pattern that was specified in the shared schedule.</span></span> <span data-ttu-id="d0e2b-106">Обратите внимание, что службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] не обеспечивают централизованного управления отдельными расписаниями.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-106">Note that [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not provide central management of individual schedules.</span></span> <span data-ttu-id="d0e2b-107">Удаление общего расписания влечет за собой необходимость поддерживать расписание для каждого отдельного элемента.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-107">If you delete a shared schedule, you will now need to maintain the schedule information for each individual item.</span></span> <span data-ttu-id="d0e2b-108">Перед удалением общего расписания определите при помощи страницы [Отчеты](schedule-properties-reports-page.md) , какие отчеты используют в настоящее время это расписание.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-108">Before deleting a shared schedule, use the [Reports page](schedule-properties-reports-page.md) to determine which reports are currently using the shared schedule.</span></span>  
  
 <span data-ttu-id="d0e2b-109">Что касается определений ролей, то допускается удаление только тех определений, которые не используются в назначениях роли.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-109">For role definitions, you can only delete those that are not actively used in a role assignment.</span></span> <span data-ttu-id="d0e2b-110">При попытке удалить роль, которая используется в настоящий момент, сервер отчетов не удаляет эту роль и выдает сообщение о соответствующей ошибке.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-110">If you try to delete a role that is currently in use, the report server will not delete the role and you will see an error message to that effect.</span></span> <span data-ttu-id="d0e2b-111">Если эта страница содержит единственное определение роли, которое не используется в настоящее время, то оно будет удалено после нажатия кнопки **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-111">If this page contains a single role definition that is not currently in use, it will be deleted when you click **OK**.</span></span> <span data-ttu-id="d0e2b-112">Если эта страница содержит несколько определений ролей, то на ней нельзя выбрать, какие роли должны быть сохранены или удалены.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-112">If this page contains multiple roles, you cannot select which roles to keep or remove.</span></span> <span data-ttu-id="d0e2b-113">После нажатия кнопки **OK**будут удалены все неиспользуемые определения ролей.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-113">All unused role definitions will be deleted when you click **OK**.</span></span>  
  
 <span data-ttu-id="d0e2b-114">Операцию удаления нельзя отменить.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-114">You cannot undo a delete operation.</span></span> <span data-ttu-id="d0e2b-115">При необходимости восстановления удаленного элемента необходимо или снова создать этот элемент, или восстановить резервную копию базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-115">If you want to recover an item that you deleted, you must either recreate it or restore a backup copy of the report server database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d0e2b-116">Параметры</span><span class="sxs-lookup"><span data-stu-id="d0e2b-116">Options</span></span>  
 <span data-ttu-id="d0e2b-117">**Название**</span><span class="sxs-lookup"><span data-stu-id="d0e2b-117">**Name**</span></span>  
 <span data-ttu-id="d0e2b-118">Определяет имя удаляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-118">Specifies the name of the item you are deleting.</span></span>  
  
 <span data-ttu-id="d0e2b-119">**Тип**</span><span class="sxs-lookup"><span data-stu-id="d0e2b-119">**Type**</span></span>  
 <span data-ttu-id="d0e2b-120">Отображает тип удаляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-120">Shows the type of item you are deleting.</span></span>  
  
 <span data-ttu-id="d0e2b-121">**Владелец**</span><span class="sxs-lookup"><span data-stu-id="d0e2b-121">**Owner**</span></span>  
 <span data-ttu-id="d0e2b-122">Отображает имя владельца.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-122">Shows the name of the owner.</span></span> <span data-ttu-id="d0e2b-123">В большинстве случаев это System.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-123">In most cases, this is System.</span></span>  
  
 <span data-ttu-id="d0e2b-124">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="d0e2b-124">**Status**</span></span>  
 <span data-ttu-id="d0e2b-125">Отображает сведения о ходе выполнения операции удаления.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-125">Shows progress information for a delete operation.</span></span>  
  
 <span data-ttu-id="d0e2b-126">**Ошибка**</span><span class="sxs-lookup"><span data-stu-id="d0e2b-126">**Error**</span></span>  
 <span data-ttu-id="d0e2b-127">Выводит код ошибки, произошедшей при удалении элемента.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-127">Displays an error code if an error occurs while deleting an item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0e2b-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="d0e2b-128">See Also</span></span>  
 <span data-ttu-id="d0e2b-129">[Удаление элемента (среда Management Studio)](delete-an-item-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="d0e2b-129">[Delete an Item &#40;Management Studio&#41;](delete-an-item-management-studio.md) </span></span>  
 <span data-ttu-id="d0e2b-130">[Справка F1 по использованию сервера отчетов среде Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="d0e2b-130">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="d0e2b-131">Создание, изменение и удаление расписаний</span><span class="sxs-lookup"><span data-stu-id="d0e2b-131">Create, Modify, and Delete Schedules</span></span>](../subscriptions/create-modify-and-delete-schedules.md)  
  
  
