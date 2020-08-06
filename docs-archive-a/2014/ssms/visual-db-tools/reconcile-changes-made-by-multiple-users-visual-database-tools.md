---
title: Согласование изменений, внесенных несколькими пользователями (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- table modifications [SQL Server], multiple users
- reconciling changes made by multiple users
- modifications made by multiple users
ms.assetid: fc7ed4f2-ad3d-47fc-a3ef-51e5bb069ef0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 337d505fce474a33301c18313fe6137f6bc0ec1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729973"
---
# <a name="reconcile-changes-made-by-multiple-users-visual-database-tools"></a><span data-ttu-id="06324-102">Согласование изменений, внесенных несколькими пользователями (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="06324-102">Reconcile Changes Made by Multiple Users (Visual Database Tools)</span></span>
  <span data-ttu-id="06324-103">В многопользовательской среде изменение одного и того же объекта могут выполнять одновременно несколько пользователей.</span><span class="sxs-lookup"><span data-stu-id="06324-103">In a multiuser environment, changes can be made on the same object by multiple users at once.</span></span> <span data-ttu-id="06324-104">Это происходит при работе над структурой объекта в конструкторе таблиц или конструкторе диаграмм баз данных либо при изменении значений, когда они возвращаются в панели результатов конструктора запросов и представлений.</span><span class="sxs-lookup"><span data-stu-id="06324-104">This can happen when you're working on the structure of the object in the Table or Database Diagram designers or it can happen to values in the results returned in the Query and View designer's Results pane.</span></span> <span data-ttu-id="06324-105">Это может приводить к конфликтам, которые придется разрешать.</span><span class="sxs-lookup"><span data-stu-id="06324-105">This can cause conflicts that you'll want to resolve.</span></span>  
  
## <a name="conflicts-in-the-table-or-database-diagram-designers"></a><span data-ttu-id="06324-106">Конфликты в конструкторе таблиц или диаграмм баз данных</span><span class="sxs-lookup"><span data-stu-id="06324-106">Conflicts in the Table or Database Diagram Designers</span></span>  
 <span data-ttu-id="06324-107">Например, когда один пользователь работает с таблицей в конструкторе таблиц, другой пользователь может попытаться удалить или переименовать данную или связанную с ней таблицу.</span><span class="sxs-lookup"><span data-stu-id="06324-107">For example, another user might delete or rename a table while you are working with the same or a related table in Table Designer.</span></span> <span data-ttu-id="06324-108">При попытке сохранить таблицу [Диалоговое окно "Обнаружены изменения базы данных" (визуальные инструменты для баз данных)](visual-database-tools.md) сообщит, что с момента открытия этой таблицы база данных была обновлена.</span><span class="sxs-lookup"><span data-stu-id="06324-108">When you attempt to save your table, the [Database Changes Detected Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) notifies you that the database has been updated since you opened the table.</span></span>  
  
 <span data-ttu-id="06324-109">Кроме того, в этом диалоговом окне выводится список объектов базы данных, на которые повлияет сохранение этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="06324-109">This dialog box also displays a list of database objects that will be affected as a result of saving your table.</span></span> <span data-ttu-id="06324-110">Можно выполнить одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="06324-110">At this point, you can take one of these actions:</span></span>  
  
-   <span data-ttu-id="06324-111">Нажмите кнопку **Да** — таблица будет сохранена, а в базу данных будут записаны новые значения, указанные в списке.</span><span class="sxs-lookup"><span data-stu-id="06324-111">Choose **Yes** to save your table and update the database with all the changes in the list.</span></span>  
  
     <span data-ttu-id="06324-112">Это действие может повлиять на таблицы, совместно использующие одни и те же объекты базы данных.</span><span class="sxs-lookup"><span data-stu-id="06324-112">This action could affect tables that share the same database objects.</span></span> <span data-ttu-id="06324-113">Например, предположим, что изменяется столбец `au`_`id` в таблице `titleauthors` , а в это время другой пользователь работает в таблице `authors` , связанной с таблицей `titleauthors` столбцом `au`\_`id` .</span><span class="sxs-lookup"><span data-stu-id="06324-113">For example, suppose you edit the `au`_`id` column in the `titleauthors` table while another user is working on the `authors` table which is related to the `titleauthors` table by the `au`\_`id` column.</span></span> <span data-ttu-id="06324-114">Сохранение одной таблицы повлияет на другую.</span><span class="sxs-lookup"><span data-stu-id="06324-114">Saving your table will affect the other user's table.</span></span> <span data-ttu-id="06324-115">Точно так же, допустим, что другой пользователь задал проверочное ограничение для столбца `qty` в таблице `sales` .</span><span class="sxs-lookup"><span data-stu-id="06324-115">Similarly, suppose that another user defined a check constraint for the `qty` column in the `sales` table.</span></span> <span data-ttu-id="06324-116">Удаление столбца `qty` и сохранение таблицы `sales` коснется проверочного ограничения другого пользователя.</span><span class="sxs-lookup"><span data-stu-id="06324-116">If you delete the `qty` column and save the `sales` table, the other user's check constraint will be affected.</span></span>  
  
-   <span data-ttu-id="06324-117">Нажмите кнопку **Нет** — сохранение будет отменено.</span><span class="sxs-lookup"><span data-stu-id="06324-117">Choose **No** to cancel the save action.</span></span>  
  
     <span data-ttu-id="06324-118">После этого можно закрыть таблицу без сохранения.</span><span class="sxs-lookup"><span data-stu-id="06324-118">You can then close the table without saving it.</span></span> <span data-ttu-id="06324-119">При ее повторном открытии она будет соответствовать таблице в базе данных.</span><span class="sxs-lookup"><span data-stu-id="06324-119">When you reopen the table it will match what is in the database.</span></span>  
  
-   <span data-ttu-id="06324-120">Выберите команду **Сохранить текстовый файл** — будет сохранен список изменений.</span><span class="sxs-lookup"><span data-stu-id="06324-120">Choose **Save Text File** to save a list of the changes.</span></span>  
  
     <span data-ttu-id="06324-121">Список изменений, показанный в диалоговом окне **Обнаружены изменения базы данных** , можно сохранить в текстовый файл, чтобы затем проанализировать причину изменений, внесенных другим пользователем.</span><span class="sxs-lookup"><span data-stu-id="06324-121">You can save the list of database changes shown in the **Database Changes Detected** dialog box to a text file so that you can investigate the cause of other users' changes.</span></span> <span data-ttu-id="06324-122">Например, если другой пользователь изменил таблицу, которая помечена к удалению, то можно проанализировать, следует ли удалять эту таблицу перед обновлением базы данных.</span><span class="sxs-lookup"><span data-stu-id="06324-122">For example, if another user edited a table that you marked for deletion, you may want to research whether the table should be deleted before updating the database.</span></span>  
  
## <a name="conflicts-in-the-query-and-view-designer"></a><span data-ttu-id="06324-123">Конфликты в конструкторе запросов и представлений</span><span class="sxs-lookup"><span data-stu-id="06324-123">Conflicts in the Query and View Designer</span></span>  
 <span data-ttu-id="06324-124">При запуске запроса или возврате результатов представления данные отображаются в [панели результатов](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="06324-124">If you run a query or return the results of a view, the data is shown in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="06324-125">С одним набором данных могут одновременно работать несколько пользователей, что может вызвать конфликты.</span><span class="sxs-lookup"><span data-stu-id="06324-125">Multiple users can work on the same set of data at the same time, which can cause conflicts.</span></span>  
  
 <span data-ttu-id="06324-126">Например, допустим, что сотрудники по отдельности выполняют запрос, выводящий все данные в таблице `titleauthors` .</span><span class="sxs-lookup"><span data-stu-id="06324-126">For example, lets say you and a colleague each run a query to show all the data in the `titleauthors` table.</span></span> <span data-ttu-id="06324-127">Сотрудник изменяет имя, которое возвращает первая запись, с Barb на Barbara.</span><span class="sxs-lookup"><span data-stu-id="06324-127">Your colleague changes the first name in the first record returned from Barb to Barbara.</span></span> <span data-ttu-id="06324-128">В этот момент запись содержит имя Barbara, в то время как результирующий набор другого сотрудника содержит запись Barb.</span><span class="sxs-lookup"><span data-stu-id="06324-128">At this point the database has Barbara in that field, while your result set still shows Barb.</span></span> <span data-ttu-id="06324-129">Вводите «Barbara» и сохраняете строку.</span><span class="sxs-lookup"><span data-stu-id="06324-129">Now you type in Barbara and click off of the row.</span></span> <span data-ttu-id="06324-130">Появляется сообщение с вопросом, как разрешить конфликт.</span><span class="sxs-lookup"><span data-stu-id="06324-130">You will receive a message asking you how you want to resolve the conflict.</span></span>  
  
-   <span data-ttu-id="06324-131">Нажмите кнопку **Да** — база данных будет обновлена, в нее будут записаны внесенные изменения.</span><span class="sxs-lookup"><span data-stu-id="06324-131">Click **Yes** to update the database with your changes.</span></span>  
  
     <span data-ttu-id="06324-132">Они переопределят изменения, внесенные сотрудником.</span><span class="sxs-lookup"><span data-stu-id="06324-132">This will override your colleague's changes.</span></span>  
  
-   <span data-ttu-id="06324-133">Нажмите кнопку **Нет** — результирующий набор обновится текущими значениями базы данных.</span><span class="sxs-lookup"><span data-stu-id="06324-133">Click **No** to have your result set updated to what's currently in the database.</span></span>  
  
     <span data-ttu-id="06324-134">Значения, внесенные одним сотрудником, переопределят изменения, внесенные другим.</span><span class="sxs-lookup"><span data-stu-id="06324-134">This will override your changes with those of your colleague's.</span></span>  
  
-   <span data-ttu-id="06324-135">Нажмите кнопку **Отмена** , чтобы продолжить редактирование без разрешения конфликта.</span><span class="sxs-lookup"><span data-stu-id="06324-135">Click **Cancel** to continue to edit without resolving the conflict.</span></span>  
  
     <span data-ttu-id="06324-136">В этом случае невозможно зафиксировать изменения.</span><span class="sxs-lookup"><span data-stu-id="06324-136">In this case you will not be able to commit your changes to the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06324-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="06324-137">See Also</span></span>  
 [<span data-ttu-id="06324-138">Диалоговое окно "Обнаружены изменения базы данных" (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="06324-138">Database Changes Detected Dialog Box &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
