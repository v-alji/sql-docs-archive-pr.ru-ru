---
title: Раздельное сохранение событий профиля статистики Showplan XML (приложение SQL Server Profiler) | Документация Майкрософт
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
ms.assetid: df393f13-d538-4d94-8155-9c2fdf5f755d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: be0c02f8396df81af803c365b9ede42610353ed3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732606"
---
# <a name="save-showplan-xml-statistics-profile-events-separately-sql-server-profiler"></a><span data-ttu-id="f05b5-102">раздельно сохранить события «Профиль статистики Showplan XML» (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="f05b5-102">Save Showplan XML Statistics Profile Events Separately (SQL Server Profiler)</span></span>
  <span data-ttu-id="f05b5-103">В этом подразделе описывается сохранение событий **профиля статистики Showplan XML** , фиксируемых трассировкой, в отдельные файлы с расширением SQLPlan при помощи приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f05b5-103">This topic describes how to save **Showplan XML Statistics Profile** events that are captured in traces into separate .SQLPlan files by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="f05b5-104">Файлы событий **профиля статистики Showplan XML** можно открыть в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], что позволит посмотреть графический план выполнения для каждого события.</span><span class="sxs-lookup"><span data-stu-id="f05b5-104">You can open the **Showplan XML Statistics Profile** event files in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], which enables you to view the graphical execution plan for each event.</span></span>  
  
### <a name="to-save-showplan-xml-statistics-events-separately"></a><span data-ttu-id="f05b5-105">Раздельное сохранение событий статистики Showplan XML</span><span class="sxs-lookup"><span data-stu-id="f05b5-105">To save Showplan XML statistics events separately</span></span>  
  
1.  <span data-ttu-id="f05b5-106">В меню **Файл** выберите пункт **Создать трассировку**, а затем подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f05b5-106">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="f05b5-107">отображается диалоговое окно **Свойства трассировки** .</span><span class="sxs-lookup"><span data-stu-id="f05b5-107">The **Trace Properties** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f05b5-108">Если выбран параметр **Начать трассировку немедленно после установления соединения**, диалоговое окно **Свойства трассировки**не появляется и начинается трассировка.</span><span class="sxs-lookup"><span data-stu-id="f05b5-108">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box does not appear and the trace begins instead.</span></span> <span data-ttu-id="f05b5-109">Чтобы отключить этот параметр, в меню **Сервис**выберите пункт **Параметры**и снимите флажок **Начать трассировку немедленно после установления соединения** .</span><span class="sxs-lookup"><span data-stu-id="f05b5-109">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="f05b5-110">В диалоговом окне **Свойства трассировки** введите имя трассировки в поле **Имя трассировки** .</span><span class="sxs-lookup"><span data-stu-id="f05b5-110">In the **Trace Properties** dialog box, type a name for the trace in the **Trace name** box.</span></span>  
  
3.  <span data-ttu-id="f05b5-111">В списке **Использовать шаблон** выберите шаблон, на котором должна быть основана трассировка, или выберите **Пустой** , если использование шаблона не требуется.</span><span class="sxs-lookup"><span data-stu-id="f05b5-111">In the **Use the template** list, select a trace template to base the trace on, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="f05b5-112">Используйте один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="f05b5-112">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="f05b5-113">Нажмите кнопку**Сохранить в файл**для фиксации трассировки в файле.</span><span class="sxs-lookup"><span data-stu-id="f05b5-113">Click**Save to file**to capture the trace to a file.</span></span> <span data-ttu-id="f05b5-114">Укажите значение **Установить максимальный размер файла**.</span><span class="sxs-lookup"><span data-stu-id="f05b5-114">Specify a value for **Set maximum file size**.</span></span>  
  
         <span data-ttu-id="f05b5-115">При необходимости установите флажок **включить переключение файлов** и **обработка данных трассировки сервером**.</span><span class="sxs-lookup"><span data-stu-id="f05b5-115">Optionally select **Enable file rollover** and **Server processes trace data**.</span></span>  
  
    -   <span data-ttu-id="f05b5-116">Нажмите кнопку**Сохранить в таблицу** для фиксации трассировки в таблице базы данных.</span><span class="sxs-lookup"><span data-stu-id="f05b5-116">Click**Save to table** to capture the trace to a database table.</span></span>  
  
         <span data-ttu-id="f05b5-117">При необходимости установите флажок **Установить максимальное число строк**и укажите значение.</span><span class="sxs-lookup"><span data-stu-id="f05b5-117">Optionally click **Set maximum rows**, and specify a value.</span></span>  
  
5.  <span data-ttu-id="f05b5-118">При необходимости установите флажок **Включить время окончания трассировки** и укажите дату и время окончания.</span><span class="sxs-lookup"><span data-stu-id="f05b5-118">Optionally select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="f05b5-119">Перейдите на вкладку **Выбор событий**.</span><span class="sxs-lookup"><span data-stu-id="f05b5-119">Click the **Events Selection**tab.</span></span>  
  
7.  <span data-ttu-id="f05b5-120">В столбце данных **События**разверните категорию событий **Производительность**и установите флажок **Showplan XML Statistics Profile**(Профиль статистики Showplan XML).</span><span class="sxs-lookup"><span data-stu-id="f05b5-120">In the **Events**data column, expand the **Performance**event category, and then select the **Showplan XML Statistics Profile**check box.</span></span> <span data-ttu-id="f05b5-121">Если категория событий **Производительность** недоступна, установите флажок **Показать все события** , чтобы отобразить ее.</span><span class="sxs-lookup"><span data-stu-id="f05b5-121">If the **Performance** event category is not available, check **Show all events** to display it.</span></span>  
  
     <span data-ttu-id="f05b5-122">Вкладка **Настройки извлечения событий**добавлена в диалоговое окно **Свойства трассировки**.</span><span class="sxs-lookup"><span data-stu-id="f05b5-122">The **Events Extraction Settings**tab is added to the **Trace Properties**dialog.</span></span>  
  
8.  <span data-ttu-id="f05b5-123">На вкладке **Настройки извлечения событий**установите флажок **Сохранить события XML Showplan отдельно**.</span><span class="sxs-lookup"><span data-stu-id="f05b5-123">On the **Events Extraction Settings**tab, click **Save XML Showplan events separately**.</span></span>  
  
9. <span data-ttu-id="f05b5-124">В диалоговом окне **Сохранить как** введите имя файла для сохранения событий **профиля статистики Showplan XML** .</span><span class="sxs-lookup"><span data-stu-id="f05b5-124">In the **Save As** dialog box, enter the file name to store the **Showplan XML Statistics Profile** events.</span></span>  
  
10. <span data-ttu-id="f05b5-125">Щелкните **Все пакеты XML Showplan в один файл** , чтобы сохранить все события **профиля статистики Showplan XML** в одном XML-файле, или щелкните **Каждый пакет XML Showplan в отдельный файл**, чтобы создать новый XML-файл для каждого события **профиля статистики Showplan XML** .</span><span class="sxs-lookup"><span data-stu-id="f05b5-125">Click **All batches in a single file** to save all **Showplan XML Statistics Profile** events in a single XML file, or click **Each XML Showplan batch in a distinct file**to create a new XML file for each **Showplan XML Statistics Profile** event.</span></span>  
  
11. <span data-ttu-id="f05b5-126">Чтобы просмотреть файл событий **профиля статистики Showplan XML** в среде SQL Server Management Studio, в меню **Файл** выберите **Открыть**и щелкните **Файл**.</span><span class="sxs-lookup"><span data-stu-id="f05b5-126">To view the **Showplan XML Statistics Profile** event file in SQL Server Management Studio, on the **File** menu, point to **Open**, and click **File**.</span></span> <span data-ttu-id="f05b5-127">Перейдите в каталог, в котором был сохранен файл или файлы событий **профиля статистики Showplan XML** , выберите один файл и откройте его.</span><span class="sxs-lookup"><span data-stu-id="f05b5-127">Navigate to the directory where you saved the **Showplan XML Statistics Profile** event file or files to select one and open it.</span></span> <span data-ttu-id="f05b5-128">Файлы событий**профиля статистики Showplan XML** имеют расширение «SQLPlan».</span><span class="sxs-lookup"><span data-stu-id="f05b5-128">**Showplan XML Statistics Profile** event files have a .SQLPlan file extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f05b5-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="f05b5-129">See Also</span></span>  
 [<span data-ttu-id="f05b5-130">Анализ запросов с помощью результатов инструкции SHOWPLAN в приложении SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f05b5-130">Analyze Queries with SHOWPLAN Results in SQL Server Profiler</span></span>](../../tools/sql-server-profiler/analyze-queries-with-showplan-results-in-sql-server-profiler.md)  
  
  
