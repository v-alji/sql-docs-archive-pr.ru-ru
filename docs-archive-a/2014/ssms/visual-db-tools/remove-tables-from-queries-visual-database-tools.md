---
title: Удаление таблиц из запросов (визуальные инструменты для базы данных) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- deleting tables
- removing tables
- dropping tables
- queries [SQL Server], tables
ms.assetid: 8fea0b4f-99b7-4050-8d6f-a97ffb839619
author: stevestein
ms.author: sstein
ms.openlocfilehash: fab5380e13742f3cd289ce17f26ad2e5fb9089ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659069"
---
# <a name="remove-tables-from-queries-visual-database-tools"></a><span data-ttu-id="ebe1f-102">Удаление таблиц из запросов (визуальные инструменты для базы данных)</span><span class="sxs-lookup"><span data-stu-id="ebe1f-102">Remove Tables from Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="ebe1f-103">Из запроса можно удалить таблицу или любой возвращающий табличное значение объект.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-103">You can remove a table - or any table-valued object - from the query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ebe1f-104">Удаление таблицы или возвращающего табличное значение объекта из текущего запроса не приводит к их удалению из базы данных.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-104">Removing a table or table-valued object does not delete anything from the database; it only removes it from the current query.</span></span> <span data-ttu-id="ebe1f-105">Дополнительные сведения об удалении таблицы из базы данных см. в разделе [Удаление таблиц &#40;ядро СУБД&#41;](../../relational-databases/tables/delete-tables-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="ebe1f-105">For details about removing a table from a database, see [Delete Tables &#40;Database Engine&#41;](../../relational-databases/tables/delete-tables-database-engine.md).</span></span>  
  
### <a name="to-remove-a-table-or-table-structured-object"></a><span data-ttu-id="ebe1f-106">Удаление таблицы или табличного объекта</span><span class="sxs-lookup"><span data-stu-id="ebe1f-106">To remove a table or table-structured object</span></span>  
  
-   <span data-ttu-id="ebe1f-107">На **панели диаграммы**выберите таблицу, представление, определяемую пользователем функцию, синоним или запрос и нажмите клавишу DELETE, либо щелкните объект правой кнопкой мыши и в контекстном меню выберите команду **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="ebe1f-107">In the **Diagram Pane**, select the table, view, user-defined function, synonym, or query, and then press DELETE, or right-click the object and then choose **Remove** in the resulting dialog box.</span></span> <span data-ttu-id="ebe1f-108">Можно выбрать и одновременно удалить несколько объектов.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-108">You can select and remove multiple objects at one time.</span></span>  
  
     <span data-ttu-id="ebe1f-109">-или-</span><span class="sxs-lookup"><span data-stu-id="ebe1f-109">-or-</span></span>  
  
-   <span data-ttu-id="ebe1f-110">Удалите все ссылки на объект на **панели SQL**.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-110">Remove all references to the object in the **SQL Pane.**</span></span>  
  
 <span data-ttu-id="ebe1f-111">При удалении таблицы или возвращающего табличное значение объекта конструктор запросов и представлений автоматически удаляет все включающие их соединения и ссылки на столбцы объектов на **панели SQL** и **панели критериев**.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-111">When you remove a table or table-valued object, the Query and View Designer automatically removes joins that involve that table or table-valued object and removes references to the object's columns in the **SQL Pane** and **Criteria Pane**.</span></span> <span data-ttu-id="ebe1f-112">Однако если запрос содержит сложные выражения, включающие объект, то он может быть автоматически удален только после удаления всех ссылок на него.</span><span class="sxs-lookup"><span data-stu-id="ebe1f-112">However, if the query contains complex expressions involving the object, the object is not automatically removed until all references to it are removed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebe1f-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="ebe1f-113">See Also</span></span>  
 <span data-ttu-id="ebe1f-114">[Добавление таблиц в запросы &#40;визуальных инструментов для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ebe1f-114">[Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="ebe1f-115">[Создание псевдонимов таблиц &#40;визуальных инструментов для баз данных&#41;](create-table-aliases-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ebe1f-115">[Create Table Aliases &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) </span></span>  
 <span data-ttu-id="ebe1f-116">[Укажите условия поиска &#40;визуальные инструменты для баз данных&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ebe1f-116">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="ebe1f-117">[Суммировать результаты запроса &#40;визуальных инструментов для баз данных&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ebe1f-117">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="ebe1f-118">Выполнение основных операций с запросами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="ebe1f-118">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
