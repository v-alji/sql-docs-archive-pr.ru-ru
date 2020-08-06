---
title: Раздельное сохранение событий Showplan XML (приложение SQL Server Profiler) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Showplan XML events
- saving Showplan XML events
- events [SQL Server], Showplan XML
ms.assetid: 33320a7a-36e8-401c-876d-5b82c49abd85
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 240fb408bb3ed8585ecc915ba4829ac21285d241
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668256"
---
# <a name="save-showplan-xml-events-separately-sql-server-profiler"></a><span data-ttu-id="5a5ea-102">Раздельное сохранение события Showplan XML (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="5a5ea-102">Save Showplan XML Events Separately (SQL Server Profiler)</span></span>
  <span data-ttu-id="5a5ea-103">В этом разделе описано сохранение событий инструкции **Showplan XML** , захваченных при трассировке в отдельные файлы .SQLPlan с помощью приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a5ea-103">This topic describes how to save **Showplan XML** events that are captured in traces into separate .SQLPlan files by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="5a5ea-104">Файлы событий **Showplan XML** можно открыть в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], позволяющей просматривать графическое представление плана выполнения для каждого события.</span><span class="sxs-lookup"><span data-stu-id="5a5ea-104">You can open the **Showplan XML** event files in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], which enables you to view the graphical execution plan for each event.</span></span>  
  
### <a name="to-save-showplan-xml-events-separately"></a><span data-ttu-id="5a5ea-105">Отдельное сохранение событий Showplan XML</span><span class="sxs-lookup"><span data-stu-id="5a5ea-105">To save Showplan XML events separately</span></span>  
  
1.  <span data-ttu-id="5a5ea-106">В меню **Файл** выберите пункт **Создать трассировку**, а затем подключитесь к экземпляру SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5a5ea-106">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="5a5ea-107">Отображается диалоговое окно **Свойства трассировки**.</span><span class="sxs-lookup"><span data-stu-id="5a5ea-107">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5a5ea-108">Если установлен параметр **Начать трассировку немедленно после установления соединения**, диалоговое окно **Свойства трассировки**не отображается, а вместо этого начинается трассировка.</span><span class="sxs-lookup"><span data-stu-id="5a5ea-108">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="5a5ea-109">Чтобы отключить этот параметр, в меню **Сервис**выберите пункт **Параметры**и снимите флажок **Начать трассировку немедленно после установления соединения** .</span><span class="sxs-lookup"><span data-stu-id="5a5ea-109">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="5a5ea-110">В диалоговом окне **Свойства трассировки** введите имя трассировки в поле **Имя трассировки** .</span><span class="sxs-lookup"><span data-stu-id="5a5ea-110">In the **Trace Properties** dialog box, type a name for the trace in the **Trace name** box.</span></span>  
  
3.  <span data-ttu-id="5a5ea-111">В списке **Использовать шаблон** выберите шаблон, на котором должна быть основана трассировка, или выберите **Пустой** , если использование шаблона не требуется.</span><span class="sxs-lookup"><span data-stu-id="5a5ea-111">In the **Use the template** list, select a trace template on which to base the trace, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="5a5ea-112">Используйте один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="5a5ea-112">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="5a5ea-113">Установите флажок**Сохранить в файл** для фиксации данных трассировки в файле.</span><span class="sxs-lookup"><span data-stu-id="5a5ea-113">Select the**Save to file** check box to capture the trace to a file.</span></span> <span data-ttu-id="5a5ea-114">Укажите значение **Установить максимальный размер файла**.</span><span class="sxs-lookup"><span data-stu-id="5a5ea-114">Specify a value for **Set maximum file size**.</span></span> <span data-ttu-id="5a5ea-115">При необходимости установите флажки **Включить переключение файлов** и **Обработка данных трассировки сервером** .</span><span class="sxs-lookup"><span data-stu-id="5a5ea-115">Optionally, select the **Enable file rollover** and **Server processes trace data** check boxes.</span></span>  
  
    -   <span data-ttu-id="5a5ea-116">Установите флажок**Сохранить в таблицу** для фиксации данных трассировки в таблице базы данных.</span><span class="sxs-lookup"><span data-stu-id="5a5ea-116">Select the**Save to table** check box to capture the trace to a database table.</span></span> <span data-ttu-id="5a5ea-117">При необходимости установите флажок **Установить максимальное число строк**и укажите значение.</span><span class="sxs-lookup"><span data-stu-id="5a5ea-117">Optionally click **Set maximum rows**, and specify a value.</span></span>  
  
5.  <span data-ttu-id="5a5ea-118">При необходимости установите флажок **Включить время остановки трассировки** и укажите дату и время остановки.</span><span class="sxs-lookup"><span data-stu-id="5a5ea-118">Optionally, select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="5a5ea-119">Перейдите на вкладку **Выбор событий**.</span><span class="sxs-lookup"><span data-stu-id="5a5ea-119">Click the **Events Selection**tab.</span></span>  
  
7.  <span data-ttu-id="5a5ea-120">В столбце данных **События**разверните категорию событий **Производительность**и установите флажок **Showplan XML**.</span><span class="sxs-lookup"><span data-stu-id="5a5ea-120">In the **Events**data column, expand the **Performance**event category, and then select the **Showplan XML**check box.</span></span> <span data-ttu-id="5a5ea-121">Если категория событий **Производительность** недоступна, установите флажок **Показать все события** , чтобы отобразить ее.</span><span class="sxs-lookup"><span data-stu-id="5a5ea-121">If the **Performance** event category is not available, check **Show all events** to display it.</span></span>  
  
     <span data-ttu-id="5a5ea-122">Вкладка **Параметры извлечения событий**добавляется в диалоговое окно **Свойства трассировки**.</span><span class="sxs-lookup"><span data-stu-id="5a5ea-122">The **Events Extraction Settings**tab is added to the **Trace Properties**dialog box.</span></span>  
  
8.  <span data-ttu-id="5a5ea-123">На вкладке **Настройки извлечения событий**установите флажок **Сохранить события XML Showplan отдельно**.</span><span class="sxs-lookup"><span data-stu-id="5a5ea-123">On the **Events Extraction Settings**tab, click **Save XML Showplan events separately**.</span></span>  
  
9. <span data-ttu-id="5a5ea-124">В диалоговом окне **Сохранить как** введите имя файла для сохранения событий **Showplan XML** .</span><span class="sxs-lookup"><span data-stu-id="5a5ea-124">In the **Save As** dialog box, enter the name of the file in which to store the **Showplan XML** events.</span></span>  
  
10. <span data-ttu-id="5a5ea-125">Щелкните **Все пакеты XML Showplan в один файл** , чтобы сохранить все события **Showplan XML** в одном XML-файле, или щелкните **Каждый пакет XML Showplan в отдельный файл**, чтобы создать новый XML-файл для каждого события **Showplan XML** .</span><span class="sxs-lookup"><span data-stu-id="5a5ea-125">Click **All XML Showplan batches in a single file** to save all **Showplan XML** events in a single XML file, or click **Each XML Showplan batch in a distinct file**to create a new XML file for each **Showplan XML** event.</span></span>  
  
11. <span data-ttu-id="5a5ea-126">Для просмотра события **Showplan XML** в среде SQL Server Management Studio выберите в меню **Файл** пункт **Открыть**, затем выберите **Файл**.</span><span class="sxs-lookup"><span data-stu-id="5a5ea-126">To view the **Showplan XML** event file in SQL Server Management Studio, on the **File** menu, point to **Open**, and click **File**.</span></span> <span data-ttu-id="5a5ea-127">Чтобы выбрать и открыть один из файлов событий **Showplan XML** , перейдите в каталог с этими файлами.</span><span class="sxs-lookup"><span data-stu-id="5a5ea-127">Navigate to the directory where you saved the **Showplan XML** event file or files to select one and open it.</span></span> <span data-ttu-id="5a5ea-128">Файлы событий**Showplan XML** имеют расширение .SQLPlan.</span><span class="sxs-lookup"><span data-stu-id="5a5ea-128">**Showplan XML** event files have a .SQLPlan file extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a5ea-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="5a5ea-129">See Also</span></span>  
 [<span data-ttu-id="5a5ea-130">Анализ запросов с помощью результатов инструкции SHOWPLAN в приложении SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="5a5ea-130">Analyze Queries with SHOWPLAN Results in SQL Server Profiler</span></span>](../../tools/sql-server-profiler/analyze-queries-with-showplan-results-in-sql-server-profiler.md)  
  
  
