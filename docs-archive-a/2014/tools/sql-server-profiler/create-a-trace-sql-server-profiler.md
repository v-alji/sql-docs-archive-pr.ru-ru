---
title: Создание трассировки (SQL Server Profiler) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], creating
ms.assetid: 0302fa6d-d2b5-43fe-ad70-7a337575b112
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7d73333bbf0ba985ed4952e03584b4e4c130ab6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727597"
---
# <a name="create-a-trace-sql-server-profiler"></a><span data-ttu-id="f9bcf-102">создать трассировку (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="f9bcf-102">Create a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="f9bcf-103">В этом подразделе описывается, как создать трассировку при помощи [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f9bcf-103">This topic describes how to use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to create a trace.</span></span>  
  
### <a name="to-create-a-trace"></a><span data-ttu-id="f9bcf-104">Создание трассировки</span><span class="sxs-lookup"><span data-stu-id="f9bcf-104">To create a trace</span></span>  
  
1.  <span data-ttu-id="f9bcf-105">В меню **Файл** выберите пункт **Создать трассировку**, а затем подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9bcf-105">On the **File** menu, click **New Trace**, and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="f9bcf-106">отображается диалоговое окно **Свойства трассировки** .</span><span class="sxs-lookup"><span data-stu-id="f9bcf-106">The **Trace Properties** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f9bcf-107">Если выбран параметр **Начать трассировку немедленно после установления соединения** , диалоговое окно **Свойства трассировки** не появляется, и начинается трассировка.</span><span class="sxs-lookup"><span data-stu-id="f9bcf-107">The **Trace Properties** dialog box fails to appear, and the trace begins instead, if **Start tracing immediately after making connection** is selected.</span></span> <span data-ttu-id="f9bcf-108">Чтобы отключить этот параметр, в меню **Сервис**выберите пункт **Параметры**и снимите флажок **Начать трассировку немедленно после установления соединения** .</span><span class="sxs-lookup"><span data-stu-id="f9bcf-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="f9bcf-109">В поле **Имя трассировки** введите имя трассировки.</span><span class="sxs-lookup"><span data-stu-id="f9bcf-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="f9bcf-110">В списке **Использовать шаблон** выберите шаблон, на котором должна быть основана трассировка, или выберите **Пустой** , если использование шаблона не требуется.</span><span class="sxs-lookup"><span data-stu-id="f9bcf-110">In the **Use the template** list, select a trace template on which to base the trace, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="f9bcf-111">Для сохранения результатов трассировки сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="f9bcf-111">To save the trace results, do one of the following:</span></span>  
  
    -   <span data-ttu-id="f9bcf-112">Нажмите кнопку**Сохранить в файл** для фиксации трассировки в файле.</span><span class="sxs-lookup"><span data-stu-id="f9bcf-112">Click **Save to file**to capture the trace to a file.</span></span> <span data-ttu-id="f9bcf-113">Укажите значение **Установить максимальный размер файла**.</span><span class="sxs-lookup"><span data-stu-id="f9bcf-113">Specify a value for **Set maximum file size**.</span></span> <span data-ttu-id="f9bcf-114">Значение по умолчанию — 5 мегабайт.</span><span class="sxs-lookup"><span data-stu-id="f9bcf-114">The default value is 5 megabytes (MB).</span></span>  
  
         <span data-ttu-id="f9bcf-115">При необходимости выберите **Включить операцию переключения на файл продолжения** для автоматического создания новых файлов при достижении максимального размера файла.</span><span class="sxs-lookup"><span data-stu-id="f9bcf-115">Optionally, select **Enable file rollover** to automatically create new files when the maximum file size is reached.</span></span> <span data-ttu-id="f9bcf-116">Также можно дополнительно выбрать **Сервер обрабатывает данные трассировки**, что приведет к тому, что вместо приложения клиента данные трассировки будет обрабатывать служба, выполняющая трассировку.</span><span class="sxs-lookup"><span data-stu-id="f9bcf-116">You can also optionally select **Server processes trace data**, which causes the service that is running the trace to process trace data instead of the client application.</span></span> <span data-ttu-id="f9bcf-117">При обработке данных трассировки сервером исключена возможность пропуска события даже в тяжелых условиях, хотя это и приводит к снижению производительности сервера.</span><span class="sxs-lookup"><span data-stu-id="f9bcf-117">When the server processes trace data, no events are skipped even under stress conditions, but server performance may be affected.</span></span>  
  
    -   <span data-ttu-id="f9bcf-118">Выберите **Сохранить в таблицу** для сохранения результатов трассировки в таблицу базы данных.</span><span class="sxs-lookup"><span data-stu-id="f9bcf-118">Click **Save to table** to capture the trace to a database table.</span></span>  
  
         <span data-ttu-id="f9bcf-119">При необходимости установите флажок **Установить максимальное число строк**и укажите значение.</span><span class="sxs-lookup"><span data-stu-id="f9bcf-119">Optionally, click **Set maximum rows**, and specify a value.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="f9bcf-120">Если результаты трассировки не сохраняются в файлы или таблицы, их можно просмотреть, пока открыто приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f9bcf-120">When you do not save the trace results to a file or table, you can view the trace while [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] is open.</span></span> <span data-ttu-id="f9bcf-121">Однако результаты трассировки исчезнут после того, как будет остановлена трассировка и закрыто приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9bcf-121">However, you lose the trace results after you stop the trace and close [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="f9bcf-122">Чтобы избежать потерю данных трассировки, выберите **Сохранить** в меню **Файл** для сохранения результатов перед закрытием [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9bcf-122">To avoid losing the trace results in this way, click **Save** on the **File** menu to save the results before you close [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
5.  <span data-ttu-id="f9bcf-123">При необходимости установите флажок **Включить время остановки трассировки** и укажите дату и время остановки.</span><span class="sxs-lookup"><span data-stu-id="f9bcf-123">Optionally, select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="f9bcf-124">Чтобы добавить или удалить события, столбцы данных или фильтры, перейдите на вкладку **Выбор событий**.</span><span class="sxs-lookup"><span data-stu-id="f9bcf-124">To add or remove events, data columns or filters, click the **Events Selection**tab.</span></span> <span data-ttu-id="f9bcf-125">Дополнительные сведения см. в разделе [указать столбцы событий и данных для файла трассировки (приложение SQL Server Profiler)](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="f9bcf-125">For more information, see: [Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](sql-server-profiler.md)</span></span>  
  
7.  <span data-ttu-id="f9bcf-126">Чтобы запустить трассировку, нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="f9bcf-126">Click **Run** to start the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9bcf-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="f9bcf-127">See Also</span></span>  
 <span data-ttu-id="f9bcf-128">[Разрешения, необходимые для запуска приложения SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="f9bcf-128">[Permissions Required to Run SQL Server Profiler](permissions-required-to-run-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="f9bcf-129">[Шаблоны и разрешения приложения SQL Server Profiler](sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="f9bcf-129">[SQL Server Profiler Templates and Permissions](sql-server-profiler-templates-and-permissions.md) </span></span>  
 <span data-ttu-id="f9bcf-130">[Приложение SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="f9bcf-130">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="f9bcf-131">Сопоставить трассировку с данными журнала производительности Windows (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="f9bcf-131">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](../../database-engine/correlate-a-trace-with-windows-performance-log-data-sql-server-profiler.md)  
  
  
