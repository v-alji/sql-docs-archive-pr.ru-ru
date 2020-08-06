---
title: Свойства полнотекстового индекса (страница «расписания») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.fulltextindexproperties.schedule.f1
ms.assetid: a828e284-097e-4854-8c49-931934eb73bf
author: rothja
ms.author: jroth
ms.openlocfilehash: f49fb37295f0b3eb2f1a2dd04d44ab86236f109a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669057"
---
# <a name="full-text-index-properties-schedules-page"></a><span data-ttu-id="668ba-102">Свойства полнотекстового индекса (страница «Расписания»)</span><span class="sxs-lookup"><span data-stu-id="668ba-102">Full-Text Index Properties (Schedules Page)</span></span>
  <span data-ttu-id="668ba-103">Эта страница предназначена для просмотра и создания расписаний выполнения для задания агента SQL Server, которое запускает добавочное заполнение в ходе обновлений базовой таблицы полнотекстового индекса.</span><span class="sxs-lookup"><span data-stu-id="668ba-103">Use this page to view and create schedules for running a SQL Server Agent job that starts an incremental population of updates to the base table of the full-text index.</span></span> <span data-ttu-id="668ba-104">Если базовая таблица или представление не содержат столбец типа данных `timestamp`, то выполняется полное заполнение.</span><span class="sxs-lookup"><span data-stu-id="668ba-104">If the base table or view does not contain a column of the `timestamp` data type, a full population is performed.</span></span>  
  
 <span data-ttu-id="668ba-105">**Просмотр или изменение свойств полнотекстового индекса**</span><span class="sxs-lookup"><span data-stu-id="668ba-105">**To view or change the properties of a full-text index**</span></span>  
  
-   [<span data-ttu-id="668ba-106">Управление полнотекстовыми индексами</span><span class="sxs-lookup"><span data-stu-id="668ba-106">Manage Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="668ba-107">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="668ba-107">UI element list</span></span>  
 <span data-ttu-id="668ba-108">**Расписания**</span><span class="sxs-lookup"><span data-stu-id="668ba-108">**Schedules**</span></span>  
 <span data-ttu-id="668ba-109">Выводит список всех запланированных добавочных заполнений (если таковые имеются) для базовой таблицы полнотекстового индекса.</span><span class="sxs-lookup"><span data-stu-id="668ba-109">Lists each scheduled incremental population, if any, on the base table for the full-text index.</span></span>  
  
 <span data-ttu-id="668ba-110">**имя**;</span><span class="sxs-lookup"><span data-stu-id="668ba-110">**Name**</span></span>  
 <span data-ttu-id="668ba-111">Выводит имя каждого из запланированных заполнений.</span><span class="sxs-lookup"><span data-stu-id="668ba-111">Displays the name of the each scheduled population.</span></span>  
  
 <span data-ttu-id="668ba-112">**Тип заполнения**</span><span class="sxs-lookup"><span data-stu-id="668ba-112">**Population Type**</span></span>  
 <span data-ttu-id="668ba-113">Выводит тип каждого из запланированных заполнений.</span><span class="sxs-lookup"><span data-stu-id="668ba-113">Displays the type of each scheduled population.</span></span>  
  
 <span data-ttu-id="668ba-114">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="668ba-114">**Enabled**</span></span>  
 <span data-ttu-id="668ba-115">Указывает, включено или отключено запланированное заполнение в данный момент.</span><span class="sxs-lookup"><span data-stu-id="668ba-115">Indicates whether the scheduled population is currently enabled or disabled.</span></span>  
  
 <span data-ttu-id="668ba-116">**Описание**</span><span class="sxs-lookup"><span data-stu-id="668ba-116">**Description**</span></span>  
 <span data-ttu-id="668ba-117">Выводит описание, указанное в момент создания расписания.</span><span class="sxs-lookup"><span data-stu-id="668ba-117">Displays the description that was specified when the schedule was created.</span></span>  
  
 <span data-ttu-id="668ba-118">**Создать**</span><span class="sxs-lookup"><span data-stu-id="668ba-118">**New**</span></span>  
 <span data-ttu-id="668ba-119">Нажмите, чтобы создать новое расписание для заполнения полнотекстового индекса.</span><span class="sxs-lookup"><span data-stu-id="668ba-119">Click to create a new schedule for populating the full-text index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="668ba-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="668ba-120">See Also</span></span>  
 <span data-ttu-id="668ba-121">[Использование мастера полнотекстового индексирования](../relational-databases/search/use-the-full-text-indexing-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="668ba-121">[Use the Full-Text Indexing Wizard](../relational-databases/search/use-the-full-text-indexing-wizard.md) </span></span>  
 [<span data-ttu-id="668ba-122">Заполнение полнотекстовых индексов</span><span class="sxs-lookup"><span data-stu-id="668ba-122">Populate Full-Text Indexes</span></span>](../relational-databases/search/populate-full-text-indexes.md)  
  
  
