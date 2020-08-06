---
title: Просмотр сведений о фильтре (SQL Server Profiler) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- displaying filter information
- filters [SQL Server], viewing
- filters [SQL Server], traces
- traces [SQL Server], filters
- viewing filter information
ms.assetid: 8d002dea-376a-452c-b3ca-3e93656ed75f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 931b83f8087d446cfc7b08d9582cbad5b02cf671
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657450"
---
# <a name="view-filter-information-sql-server-profiler"></a><span data-ttu-id="aa6fc-102">просмотреть сведения о фильтре (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="aa6fc-102">View Filter Information (SQL Server Profiler)</span></span>
  <span data-ttu-id="aa6fc-103">В этом разделе описывается, как просмотреть фильтры столбцов данных для классов событий, используя приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa6fc-103">This topic describes how to view filters on data columns for event classes by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-view-filter-information"></a><span data-ttu-id="aa6fc-104">Просмотр сведений о фильтре</span><span class="sxs-lookup"><span data-stu-id="aa6fc-104">To view filter information</span></span>  
  
1.  <span data-ttu-id="aa6fc-105">Откройте файл трассировки, таблицу трассировки или скрипт SQL и в меню **Файл** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="aa6fc-105">Open a trace file, trace table, or SQL script, and on the **File** menu, click **Properties**.</span></span> <span data-ttu-id="aa6fc-106">Пропустите этот шаг, если шаблон трассировки редактируется или создается новая трассировка.</span><span class="sxs-lookup"><span data-stu-id="aa6fc-106">If you are editing a trace template or creating a new trace, skip this step.</span></span>  
  
2.  <span data-ttu-id="aa6fc-107">На вкладке **Выбор событий** правой кнопкой мыши щелкните имя столбца данных для фильтра, который необходимо просмотреть, и выберите команду **Изменить фильтр столбца**.</span><span class="sxs-lookup"><span data-stu-id="aa6fc-107">On the **Events Selection** tab, right-click the data column name for the filter you want to view, and click **Edit Column Filter**.</span></span>  
  
3.  <span data-ttu-id="aa6fc-108">В диалоговом окне **Изменение фильтра** разверните операторы сравнения фильтра, чтобы просмотреть присвоенное значение для указанного критерия.</span><span class="sxs-lookup"><span data-stu-id="aa6fc-108">In the **Edit Filter** dialog box, expand the filter comparison operators to see the assigned value for the specified criterion.</span></span> <span data-ttu-id="aa6fc-109">Повторите шаги 2 и 3 относительно всех столбцов, для которых необходимо просмотреть сведения о фильтре.</span><span class="sxs-lookup"><span data-stu-id="aa6fc-109">Repeat Steps 2 and 3 for all columns for which you want to view filter information.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa6fc-110">Операторы сравнения с присвоенными значениями выделены полужирным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="aa6fc-110">Comparison operators with assigned values are formatted bold.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa6fc-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="aa6fc-111">See Also</span></span>  
 [<span data-ttu-id="aa6fc-112">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="aa6fc-112">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
