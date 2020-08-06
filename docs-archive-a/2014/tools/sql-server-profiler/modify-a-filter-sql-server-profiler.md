---
title: Изменение фильтра (SQL Server Profiler) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], modifying
- modifying filters, modifying
- filters [SQL Server], traces
ms.assetid: 8b317813-4918-4485-b930-77b1951aa00c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5a7bab18952820a3dc49c9479797a411521f8e71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658597"
---
# <a name="modify-a-filter-sql-server-profiler"></a><span data-ttu-id="232ba-102">изменить фильтр (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="232ba-102">Modify a Filter (SQL Server Profiler)</span></span>
  <span data-ttu-id="232ba-103">Фильтры добавляются в шаблоны трассировки, которые содержат определение трассировки, чтобы ограничить число событий, собираемых трассировкой.</span><span class="sxs-lookup"><span data-stu-id="232ba-103">You add filters to trace templates, which contain the trace definitions, to limit the number of events that are gathered by a trace.</span></span> <span data-ttu-id="232ba-104">Ограничение числа собираемых событий может уменьшить влияние трассировки на производительность.</span><span class="sxs-lookup"><span data-stu-id="232ba-104">Limiting the number of events gathered can reduce the performance effects of tracing.</span></span> <span data-ttu-id="232ba-105">Если были установлены фильтры для шаблона трассировки, и обнаружилось, что трассировка не собирает необходимый вид сведений, то фильтр может быть отредактирован.</span><span class="sxs-lookup"><span data-stu-id="232ba-105">If you set filters for a trace template and find that the trace is not gathering the kind of information that you need, you can edit the filter.</span></span>  
  
### <a name="to-modify-a-filter"></a><span data-ttu-id="232ba-106">Изменение фильтра</span><span class="sxs-lookup"><span data-stu-id="232ba-106">To modify a filter</span></span>  
  
1.  <span data-ttu-id="232ba-107">В приложении [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]откройте проект шаблона трассировки, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="232ba-107">In [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], open the template for the trace filter that you want to modify.</span></span> <span data-ttu-id="232ba-108">В меню **Файл** выберите пункт **Шаблоны**и далее пункт **Изменить шаблон**.</span><span class="sxs-lookup"><span data-stu-id="232ba-108">On the **File** menu, click **Templates**, and then choose **Edit Template**.</span></span>  
  
2.  <span data-ttu-id="232ba-109">На вкладке **Общие** диалогового окна **Свойства шаблона трассировки** выберите шаблон из списка **Выбор имени шаблона** .</span><span class="sxs-lookup"><span data-stu-id="232ba-109">In the **General** tab of the **Trace Template Properties** dialog, select a template from the **Select template name** list.</span></span>  
  
3.  <span data-ttu-id="232ba-110">Перейдите на вкладку **Выбор событий** .</span><span class="sxs-lookup"><span data-stu-id="232ba-110">Click the **Events Selection** tab.</span></span>  
  
     <span data-ttu-id="232ba-111">Вкладка **Выбор событий** содержит сетку.</span><span class="sxs-lookup"><span data-stu-id="232ba-111">The **Events Selection** tab contains a grid control.</span></span> <span data-ttu-id="232ba-112">Сетка — это таблица, которая содержит каждый из классов событий, доступных для трассировки.</span><span class="sxs-lookup"><span data-stu-id="232ba-112">The grid control is a table that contains each of the traceable event classes.</span></span> <span data-ttu-id="232ba-113">На каждый класс событий в таблице приходится по одной строке.</span><span class="sxs-lookup"><span data-stu-id="232ba-113">The table contains one row for each event class.</span></span> <span data-ttu-id="232ba-114">Классы событий могут незначительно различаться в зависимости от типа и версии сервера, к которому они подключены.</span><span class="sxs-lookup"><span data-stu-id="232ba-114">The event classes may differ slightly, depending on the type and version of server to which you are connected.</span></span> <span data-ttu-id="232ba-115">Классы событий идентифицируются в столбце **События**сетки и группируются по категориям событий.</span><span class="sxs-lookup"><span data-stu-id="232ba-115">The event classes are identified in the **Events**column of the grid and are grouped by event category.</span></span> <span data-ttu-id="232ba-116">В оставшихся столбцах перечислены столбцы данных, которые могут быть возвращены для каждого класса событий.</span><span class="sxs-lookup"><span data-stu-id="232ba-116">The remaining columns list the data columns that can be returned for each event class.</span></span>  
  
4.  <span data-ttu-id="232ba-117">Выберите пункт **Фильтры столбцов**.</span><span class="sxs-lookup"><span data-stu-id="232ba-117">Click **Column Filters**.</span></span>  
  
5.  <span data-ttu-id="232ba-118">В диалоговом окне **Изменение фильтра** выберите значения рядом с оператором сравнения, которые необходимо изменить, и введите новое значение или удалите существующее.</span><span class="sxs-lookup"><span data-stu-id="232ba-118">In the **Edit Filter** dialog box, click the value next to the comparison operator that you want to edit, and type the new value or delete a value.</span></span> <span data-ttu-id="232ba-119">Можно также добавлять дополнительные фильтры.</span><span class="sxs-lookup"><span data-stu-id="232ba-119">You can also add additional filters.</span></span>  
  
6.  <span data-ttu-id="232ba-120">Нажмите кнопку **ОК** , чтобы сохранить шаблон.</span><span class="sxs-lookup"><span data-stu-id="232ba-120">Click **OK** and save the template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="232ba-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="232ba-121">See Also</span></span>  
 [<span data-ttu-id="232ba-122">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="232ba-122">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
