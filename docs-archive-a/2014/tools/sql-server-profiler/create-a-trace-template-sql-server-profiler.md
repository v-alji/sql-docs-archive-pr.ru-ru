---
title: Создание шаблона трассировки (SQL Server Profiler) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], traces
- trace templates [SQL Server]
- saving trace template
ms.assetid: 025868b0-3790-4cda-8757-5a58327bfba0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 355f97c7fecd8a9e31f10de881d1ae6df3b8f122
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727578"
---
# <a name="create-a-trace-template-sql-server-profiler"></a><span data-ttu-id="82b0a-102">создать шаблон трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="82b0a-102">Create a Trace Template (SQL Server Profiler)</span></span>
  <span data-ttu-id="82b0a-103">В этом подразделе описывается создание нового шаблона трассировки при помощи [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82b0a-103">This topic describes how to create a new trace template by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-create-a-trace-template"></a><span data-ttu-id="82b0a-104">Создание шаблона трассировки</span><span class="sxs-lookup"><span data-stu-id="82b0a-104">To create a trace template</span></span>  
  
1.  <span data-ttu-id="82b0a-105">В меню **Файл** укажите пункт **Шаблоны**, а затем выберите **Создать шаблон**.</span><span class="sxs-lookup"><span data-stu-id="82b0a-105">On the **File** menu, point to **Templates**, and then click **New Template**.</span></span>  
  
2.  <span data-ttu-id="82b0a-106">В диалоговом окне **Свойства шаблона трассировки** выберите тип сервера из списка **Выберите тип сервера**.</span><span class="sxs-lookup"><span data-stu-id="82b0a-106">In the **Trace Template Properties** dialog box, select a server type from the **Select server type**list.</span></span>  
  
3.  <span data-ttu-id="82b0a-107">В окне **Имя нового шаблона** введите имя шаблона.</span><span class="sxs-lookup"><span data-stu-id="82b0a-107">In the **New template name** box, enter a template name.</span></span>  
  
4.  <span data-ttu-id="82b0a-108">При необходимости выберите **Использовать существующий шаблон в качестве основы**, а затем выберите шаблон из списка.</span><span class="sxs-lookup"><span data-stu-id="82b0a-108">Optionally, click **Base new template on existing one**, and then select a template from the list.</span></span>  
  
     <span data-ttu-id="82b0a-109">Все события, столбцы данных и фильтры изначально устанавливаются заданными в выбранном шаблоне.</span><span class="sxs-lookup"><span data-stu-id="82b0a-109">All events, data columns, and filters are initially set as specified in the selected template.</span></span>  
  
5.  <span data-ttu-id="82b0a-110">При необходимости выберите **Применять как шаблон по умолчанию для выбранного типа сервера**.</span><span class="sxs-lookup"><span data-stu-id="82b0a-110">Optionally, click **Use as a default template for selected server type**.</span></span>  
  
6.  <span data-ttu-id="82b0a-111">На вкладке **Выбор событий** добавьте, удалите или измените события, столбцы данных или фильтры.</span><span class="sxs-lookup"><span data-stu-id="82b0a-111">On the **Events Selection** tab, add, remove, or modify events, data columns, or filters.</span></span>  
  
7.  <span data-ttu-id="82b0a-112">В меню **Выбор событий**используйте сетку для добавления или удаления событий и столбцов данных в файле трассировки следующим образом:</span><span class="sxs-lookup"><span data-stu-id="82b0a-112">On the **Events Selection**tab, use the grid control to add or remove events and data columns from the trace file as follows:</span></span>  
  
    -   <span data-ttu-id="82b0a-113">Чтобы добавить событие, разверните соответствующую категорию событий в столбце **События** и выберите имя события.</span><span class="sxs-lookup"><span data-stu-id="82b0a-113">To add an event, expand the appropriate event category in the **Events** column, and then select the event name.</span></span>  
  
    -   <span data-ttu-id="82b0a-114">При добавлении события все относящиеся к нему столбцы данных включаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="82b0a-114">When you add an event, all relevant data columns are included by default.</span></span> <span data-ttu-id="82b0a-115">Чтобы удалить столбец данных для события из трассировки, снимите флажок в столбце данных для этого события.</span><span class="sxs-lookup"><span data-stu-id="82b0a-115">To remove a data column for an event from a trace, clear the check box in the data column for the event.</span></span>  
  
    -   <span data-ttu-id="82b0a-116">Чтобы добавить фильтры, щелкните имя столбца данных и определите критерии фильтра в диалоговом окне **Изменение фильтра** .</span><span class="sxs-lookup"><span data-stu-id="82b0a-116">To add filters, click the data column name and specify the filter criteria in the **Edit Filter** dialog box.</span></span> <span data-ttu-id="82b0a-117">Также можно щелкнуть имя столбца данных правой кнопкой мыши и выбрать пункт **Изменить фильтр столбца** , чтобы открыть диалоговое окно **Изменение фильтра** .</span><span class="sxs-lookup"><span data-stu-id="82b0a-117">You can also right-click the data column name, and click **Edit Column Filter** to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="82b0a-118">Нажмите кнопку **ОК** , чтобы добавить фильтр.</span><span class="sxs-lookup"><span data-stu-id="82b0a-118">Click **OK** to add the filter.</span></span>  
  
8.  <span data-ttu-id="82b0a-119">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="82b0a-119">Click **Save.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82b0a-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="82b0a-120">See Also</span></span>  
 <span data-ttu-id="82b0a-121">[Указание столбцов событий и данных для файла трассировки (приложение SQL Server Profiler)](specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="82b0a-121">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="82b0a-122">[Извлечение шаблона из выполняемой трассировки (приложение SQL Server Profiler)](derive-a-template-from-a-running-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="82b0a-122">[Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="82b0a-123">[Извлечение шаблона из файла трассировки или таблицы трассировки (приложение SQL Server Profiler)](derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="82b0a-123">[Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;](derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="82b0a-124">[Шаблоны и разрешения приложения SQL Server Profiler](sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="82b0a-124">[SQL Server Profiler Templates and Permissions](sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="82b0a-125">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="82b0a-125">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
