---
title: Изменение шаблона трассировки (SQL Server Profiler) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], traces
- trace templates [SQL Server]
- modifying traces
ms.assetid: b81df2a1-e202-43d8-92b0-0beb145f0116
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2a93baedb1875ac740e74065ae7188f9b576e083
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655904"
---
# <a name="modify-a-trace-template-sql-server-profiler"></a><span data-ttu-id="4c896-102">редактировать шаблон трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="4c896-102">Modify a Trace Template (SQL Server Profiler)</span></span>
  <span data-ttu-id="4c896-103">В этом подразделе описывается модификация шаблона трассировки с помощью [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c896-103">This topic describes how to modify a trace template by using [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-modify-a-trace-template"></a><span data-ttu-id="4c896-104">Изменение шаблона трассировки</span><span class="sxs-lookup"><span data-stu-id="4c896-104">To modify a trace template</span></span>  
  
1.  <span data-ttu-id="4c896-105">В меню **Файл** выберите **Шаблоны**и затем выберите **Изменить шаблон**.</span><span class="sxs-lookup"><span data-stu-id="4c896-105">On the **File** menu, point to **Templates**, and then click **Edit Template**.</span></span>  
  
2.  <span data-ttu-id="4c896-106">В диалоговом окне **Свойства шаблона трассировки** на вкладке **Общие** можно изменить тип сервера и имя шаблона или выбрать использование шаблона по умолчанию для типа сервера.</span><span class="sxs-lookup"><span data-stu-id="4c896-106">In the **Trace Template Properties** dialog box, on the **General** tab, you can modify the server type and template name, or choose to use a default template for the server type.</span></span>  
  
3.  <span data-ttu-id="4c896-107">На вкладке **Выбор событий**используйте элемент управления Grid, чтобы добавить или удалить события и столбцы данных из файла трассировки, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="4c896-107">On the **Events Selection**tab, use the grid control to add or remove events and data columns from the trace file as follows.</span></span>  
  
    -   <span data-ttu-id="4c896-108">Чтобы добавить событие, разверните соответствующую категорию событий в столбце **События** и выберите имя события.</span><span class="sxs-lookup"><span data-stu-id="4c896-108">To add an event, expand the appropriate event category in the **Events** column, and then select the event name.</span></span>  
  
    -   <span data-ttu-id="4c896-109">При добавлении события все относящиеся к нему столбцы данных включаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="4c896-109">When you add an event, all relevant data columns are included by default.</span></span> <span data-ttu-id="4c896-110">Чтобы удалить столбец данных для события из трассировки, снимите флажок в столбце данных для этого события.</span><span class="sxs-lookup"><span data-stu-id="4c896-110">To remove a data column for an event from a trace, clear the check box in the data column for the event.</span></span>  
  
    -   <span data-ttu-id="4c896-111">Чтобы добавить фильтры, щелкните имя столбца данных и определите критерии фильтра в диалоговом окне **Изменение фильтра** .</span><span class="sxs-lookup"><span data-stu-id="4c896-111">To add filters, click the data column name and specify the filter criteria in the **Edit Filter** dialog box.</span></span> <span data-ttu-id="4c896-112">Также можно щелкнуть имя столбца данных правой кнопкой мыши и выбрать пункт **Изменить фильтр столбца** , чтобы открыть диалоговое окно **Изменение фильтра** .</span><span class="sxs-lookup"><span data-stu-id="4c896-112">You can also right-click the data column name, and click **Edit Column Filter** to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="4c896-113">Нажмите кнопку **ОК** , чтобы добавить фильтр.</span><span class="sxs-lookup"><span data-stu-id="4c896-113">Click **OK** to add the filter.</span></span>  
  
4.  <span data-ttu-id="4c896-114">Нажмите кнопку **Сохранить**или кнопку **Сохранить As**для сохранения шаблона трассировки под другим именем.</span><span class="sxs-lookup"><span data-stu-id="4c896-114">Click **Save**, or click **Save As**to save the trace template under another name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c896-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="4c896-115">See Also</span></span>  
 <span data-ttu-id="4c896-116">[Укажите события и столбцы данных для файла трассировки &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4c896-116">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4c896-117">[Извлечение шаблона из выполняемой трассировки (приложение SQL Server Profiler)](../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4c896-117">[Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4c896-118">[Извлечение шаблона из файла трассировки или таблицы трассировки (приложение SQL Server Profiler)](../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4c896-118">[Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4c896-119">[Шаблоны и разрешения приложения SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="4c896-119">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="4c896-120">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="4c896-120">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
