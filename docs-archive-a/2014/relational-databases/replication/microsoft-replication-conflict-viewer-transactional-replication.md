---
title: Средство просмотра конфликтов репликации (Майкрософт) (репликация транзакций) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replconflictviewer.cvqueued.f1
ms.assetid: eec59d8e-cadb-4623-a31f-9f42ec09c97f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8cc3f2ea3d1d2b29fba9c9d9121e23bf4bcd88bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654194"
---
# <a name="microsoft-replication-conflict-viewer-transactional-replication"></a><span data-ttu-id="864e0-102">Средство просмотра конфликтов репликации Майкрософт (репликация транзакций)</span><span class="sxs-lookup"><span data-stu-id="864e0-102">Microsoft Replication Conflict Viewer (Transactional Replication)</span></span>
  <span data-ttu-id="864e0-103">Средство просмотра конфликтов репликации позволяет просматривать конфликты, возникшие во время синхронизации для одноранговой репликации транзакций и репликации транзакций с подписками, обновляемыми посредством очередей.</span><span class="sxs-lookup"><span data-stu-id="864e0-103">The Replication Conflict Viewer enables you to view conflicts that have occurred during synchronization for peer-to-peer transactional replication and transactional replication with queued updating subscriptions.</span></span> <span data-ttu-id="864e0-104">Дополнительные сведения см. в статье [Просмотр конфликтов данных для публикаций транзакций (среда SQL Server Management Studio)](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="864e0-104">For more information, see [View Data Conflicts for Transactional Publications &#40;SQL Server Management Studio&#41;](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="864e0-105">Средство просмотра конфликтов репликации отображает конфликты, возникшие в репликации слиянием и репликации транзакций.</span><span class="sxs-lookup"><span data-stu-id="864e0-105">The Replication Conflict Viewer displays conflicts that occur in merge replication and in transactional replication.</span></span> <span data-ttu-id="864e0-106">В случае репликации транзакций средство просмотра конфликтов можно использовать для просмотра данных конфликта, но нельзя выбрать другое разрешение конфликта.</span><span class="sxs-lookup"><span data-stu-id="864e0-106">For transactional replication, you can use Replication Conflict Viewer to view conflict data, but you cannot choose a different resolution for the conflict.</span></span>  
  
## <a name="options"></a><span data-ttu-id="864e0-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="864e0-107">Options</span></span>  
 <span data-ttu-id="864e0-108">Средство просмотра конфликтов репликации разделено на две части.</span><span class="sxs-lookup"><span data-stu-id="864e0-108">The Replication Conflict Viewer is divided into two sections.</span></span> <span data-ttu-id="864e0-109">Верхняя часть диалогового окна отображает список конфликтов для выбранной таблицы.</span><span class="sxs-lookup"><span data-stu-id="864e0-109">The upper section of the dialog box shows the conflict list for the selected table.</span></span> <span data-ttu-id="864e0-110">При выборе элемента в списке конфликтов в нижней части диалогового окна отображаются подробные данные о конфликте.</span><span class="sxs-lookup"><span data-stu-id="864e0-110">When you click an item in the conflict list, the details of the conflict are displayed in the lower section of the dialog box.</span></span>  
  
 <span data-ttu-id="864e0-111">Конфликтующие данные в нижней части отображаются в двух соответствующих столбцах (**Выигравший вариант** и **Проигравший вариант**).</span><span class="sxs-lookup"><span data-stu-id="864e0-111">The conflict data in the lower section is displayed in two corresponding columns (**Conflict Winner** and **Conflict Loser**).</span></span> <span data-ttu-id="864e0-112">Если существует конфликт между обновленными и удаленными данными, то для удаленной части конфликта может не быть отображаемых данных.</span><span class="sxs-lookup"><span data-stu-id="864e0-112">If the conflict is between updated and deleted data, there may be no data to show for the deleted side of the conflict.</span></span> <span data-ttu-id="864e0-113">В таком случае средство просмотра конфликтов репликации отображает сообщение в одном из столбцов, указывая, что строка была удалена в одном расположении и обновлена в другом.</span><span class="sxs-lookup"><span data-stu-id="864e0-113">In this case, the Replication Conflict Viewer displays a message in one of the columns, indicating the row was deleted at one location and updated at another.</span></span> <span data-ttu-id="864e0-114">Также указывается предлагаемое разрешение.</span><span class="sxs-lookup"><span data-stu-id="864e0-114">It also indicates the suggested resolution.</span></span>  
  
 <span data-ttu-id="864e0-115">**База данных**</span><span class="sxs-lookup"><span data-stu-id="864e0-115">**Database**</span></span>  
 <span data-ttu-id="864e0-116">Выберите базу данных, содержащую публикации с конфликтами.</span><span class="sxs-lookup"><span data-stu-id="864e0-116">Choose a database that includes publications with conflicts.</span></span>  
  
 <span data-ttu-id="864e0-117">**Публикация**</span><span class="sxs-lookup"><span data-stu-id="864e0-117">**Publication**</span></span>  
 <span data-ttu-id="864e0-118">Выберите публикацию, содержащую таблицу с конфликтами.</span><span class="sxs-lookup"><span data-stu-id="864e0-118">Choose a publication that includes tables with conflicts.</span></span>  
  
 <span data-ttu-id="864e0-119">**Таблица**</span><span class="sxs-lookup"><span data-stu-id="864e0-119">**Table**</span></span>  
 <span data-ttu-id="864e0-120">Выберите таблицу, содержащую конфликты.</span><span class="sxs-lookup"><span data-stu-id="864e0-120">Choose a table that includes conflicts.</span></span>  
  
 <span data-ttu-id="864e0-121">**Определить фильтр**</span><span class="sxs-lookup"><span data-stu-id="864e0-121">**Define Filter**</span></span>  
 <span data-ttu-id="864e0-122">Нажмите для открытия диалогового окна **Определение фильтров** .</span><span class="sxs-lookup"><span data-stu-id="864e0-122">Click to open the **Define Filters** dialog box.</span></span>  
  
 <span data-ttu-id="864e0-123">**Применить или удалить фильтр**</span><span class="sxs-lookup"><span data-stu-id="864e0-123">**Apply or Remove Filter**</span></span>  
 <span data-ttu-id="864e0-124">Нажмите для применения или удаления фильтра, определенного в диалоговом окне **Определение фильтров** .</span><span class="sxs-lookup"><span data-stu-id="864e0-124">Click to apply or remove a filter that has been defined in the **Define Filters** dialog box.</span></span>  
  
 <span data-ttu-id="864e0-125">**Выделить все**</span><span class="sxs-lookup"><span data-stu-id="864e0-125">**Select All**</span></span>  
 <span data-ttu-id="864e0-126">Нажмите для выбора всех перечисленных в сетке конфликтов.</span><span class="sxs-lookup"><span data-stu-id="864e0-126">Click to select all conflicts listed in the grid.</span></span>  
  
 <span data-ttu-id="864e0-127">**Выбрать нет**</span><span class="sxs-lookup"><span data-stu-id="864e0-127">**Select None**</span></span>  
 <span data-ttu-id="864e0-128">Нажмите для отмены выбора всех перечисленных в сетке конфликтов.</span><span class="sxs-lookup"><span data-stu-id="864e0-128">Click to deselect all conflicts listed in the grid.</span></span>  
  
 <span data-ttu-id="864e0-129">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="864e0-129">**Remove**</span></span>  
 <span data-ttu-id="864e0-130">Нажмите для удаления выбранных конфликтов из средства просмотра и их ассоциированных метаданных из таблиц системы репликации.</span><span class="sxs-lookup"><span data-stu-id="864e0-130">Click to remove selected conflicts from the viewer and their associated metadata from the replication system tables.</span></span>  
  
 <span data-ttu-id="864e0-131">**Показать все столбцы**</span><span class="sxs-lookup"><span data-stu-id="864e0-131">**Show all columns**</span></span>  
 <span data-ttu-id="864e0-132">Выберите для отображения всех столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="864e0-132">Select to show all columns of the table.</span></span>  
  
 <span data-ttu-id="864e0-133">**Показывать первые пять столбцов и другие столбцы с конфликтующими данными**</span><span class="sxs-lookup"><span data-stu-id="864e0-133">**Show first five columns and other columns with conflicting data**</span></span>  
 <span data-ttu-id="864e0-134">Выберите для показа первых пяти столбцов и любых столбцов с конфликтами.</span><span class="sxs-lookup"><span data-stu-id="864e0-134">Select to display the first five columns and any columns that have conflicts.</span></span> <span data-ttu-id="864e0-135">Это полезно, если таблица содержит много столбцов, но требуется видеть только те столбцы, которые имеют наибольшее отношение к разрешению конфликта.</span><span class="sxs-lookup"><span data-stu-id="864e0-135">This is helpful when the table has a large number of columns, but you want to see only the columns most relevant to resolving the conflict.</span></span> <span data-ttu-id="864e0-136">Первые пять столбцов всегда включены в данное представление, поскольку поля, определяющие строки, такие как первичный ключ или поля имен, часто встречаются среди первых столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="864e0-136">The first five columns are always included in this view, as fields that identify a row, such as the primary key or name fields, are often among the first columns of the table.</span></span>  
  
 <span data-ttu-id="864e0-137">**Отображать данные о столбце** (**…**)</span><span class="sxs-lookup"><span data-stu-id="864e0-137">**Display Column Information** (**...**)</span></span>  
 <span data-ttu-id="864e0-138">Щелкните для просмотра данных о столбце: **Имя таблицы**, **Имя столбца**, **Тип данных**и **Значение столбца**.</span><span class="sxs-lookup"><span data-stu-id="864e0-138">Click to view column information: **Table Name**, **Column Name**, **Data Type**, and **Column Value**.</span></span>  
  
 <span data-ttu-id="864e0-139">**Записать в журнал подробные сведения о конфликте.**</span><span class="sxs-lookup"><span data-stu-id="864e0-139">**Log the details of the conflict**</span></span>  
 <span data-ttu-id="864e0-140">Установите этот флажок для записи сведений о конфликте в файл.</span><span class="sxs-lookup"><span data-stu-id="864e0-140">Check this box to log the details of the conflict to a file.</span></span> <span data-ttu-id="864e0-141">Для указания размещения файла укажите меню **Вид** и выберите пункт **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="864e0-141">To specify a location for the file, point to the **View** menu and click **Options**.</span></span> <span data-ttu-id="864e0-142">Введите значение или нажмите кнопку обзора (**...**) и перейдите к необходимому файлу.</span><span class="sxs-lookup"><span data-stu-id="864e0-142">Enter a value, or click the browse (**...**) and navigate to the appropriate file.</span></span> <span data-ttu-id="864e0-143">Нажмите кнопку **ОК** для выхода из диалогового окна **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="864e0-143">Click **OK** to exit the **Options** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="864e0-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="864e0-144">See Also</span></span>  
 <span data-ttu-id="864e0-145">[Обнаружение конфликтов в одноранговой репликации](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) </span><span class="sxs-lookup"><span data-stu-id="864e0-145">[Conflict Detection in Peer-to-Peer Replication](transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md) </span></span>  
 [<span data-ttu-id="864e0-146">Просмотр конфликтов данных для публикаций транзакций (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="864e0-146">View Data Conflicts for Transactional Publications &#40;SQL Server Management Studio&#41;</span></span>](view-data-conflicts-for-transactional-publications-sql-server-management-studio.md)  
  
  
