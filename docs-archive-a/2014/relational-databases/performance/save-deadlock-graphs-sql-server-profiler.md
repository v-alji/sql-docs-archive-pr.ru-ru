---
title: Сохранение графов взаимоблокировок (приложение SQL Server Profiler) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- deadlocks [SQL Server], saving deadlock graphs
- graphs [SQL Server]
- saving deadlock graphs
ms.assetid: bf1fc906-abd6-4a89-842e-da0d66b2defe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cdd0bd808ba4b934e5b2d91c9079909acf6e3997
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665993"
---
# <a name="save-deadlock-graphs-sql-server-profiler"></a><span data-ttu-id="66f2e-102">Сохранение графов взаимоблокировок (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="66f2e-102">Save Deadlock Graphs (SQL Server Profiler)</span></span>
  <span data-ttu-id="66f2e-103">В этом подразделе описывается, как сохранять графы взаимоблокировок с помощью приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66f2e-103">This topic describes how to save a deadlock graph by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="66f2e-104">Графы взаимоблокировок сохраняются в виде XML-файлов.</span><span class="sxs-lookup"><span data-stu-id="66f2e-104">Deadlock graphs are saved as XML files.</span></span>  
  
### <a name="to-save-deadlock-graph-events-separately"></a><span data-ttu-id="66f2e-105">Сохранение событий графа взаимоблокировок по отдельности</span><span class="sxs-lookup"><span data-stu-id="66f2e-105">To save deadlock graph events separately</span></span>  
  
1.  <span data-ttu-id="66f2e-106">В меню **Файл** выберите пункт **Создать трассировку**, а затем подключитесь к экземпляру SQL Server.</span><span class="sxs-lookup"><span data-stu-id="66f2e-106">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="66f2e-107">Отображается диалоговое окно **Свойства трассировки**.</span><span class="sxs-lookup"><span data-stu-id="66f2e-107">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="66f2e-108">Если установлен параметр **Начать трассировку немедленно после установления соединения** , диалоговое окно **Свойства трассировки**не отображается, а вместо этого начинается трассировка.</span><span class="sxs-lookup"><span data-stu-id="66f2e-108">If **Start tracing immediately after making connection** is selected, the **Trace Properties**dialog box fails to appear, and the trace begins instead.</span></span> <span data-ttu-id="66f2e-109">Чтобы отключить этот параметр, в меню **Сервис**выберите пункт **Параметры**и снимите флажок **Начать трассировку немедленно после установления соединения** .</span><span class="sxs-lookup"><span data-stu-id="66f2e-109">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="66f2e-110">Введите имя трассировки в поле**Имя трассировки** диалогового окна "Свойства трассировки".</span><span class="sxs-lookup"><span data-stu-id="66f2e-110">In the Trace Properties dialog box, type a name for the trace in the**Trace name** box.</span></span>  
  
3.  <span data-ttu-id="66f2e-111">В списке **Использовать шаблон** выберите шаблон, на котором должна быть основана трассировка, или выберите **Пустой** , если использование шаблона не требуется.</span><span class="sxs-lookup"><span data-stu-id="66f2e-111">In the **Use the template** list, select a trace template on which to base the trace, or select **Blank** if you do not want to use a template.</span></span>  
  
4.  <span data-ttu-id="66f2e-112">Используйте один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="66f2e-112">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="66f2e-113">Установите флажок**Сохранить в файл** для фиксации данных трассировки в файле.</span><span class="sxs-lookup"><span data-stu-id="66f2e-113">Select the**Save to file** check box to capture the trace to a file.</span></span> <span data-ttu-id="66f2e-114">Укажите значение **Установить максимальный размер файла**.</span><span class="sxs-lookup"><span data-stu-id="66f2e-114">Specify a value for **Set maximum file size**.</span></span>  
  
         <span data-ttu-id="66f2e-115">При необходимости укажите параметры **Включить операцию переключения на файл продолжения** и **Данные трассировки серверных процессов**.</span><span class="sxs-lookup"><span data-stu-id="66f2e-115">Optionally, select **Enable file rollover** and **Server processes trace data**.</span></span>  
  
    -   <span data-ttu-id="66f2e-116">Установите флажок **Сохранить в таблицу** для фиксации данных трассировки в таблице базы данных.</span><span class="sxs-lookup"><span data-stu-id="66f2e-116">Select the **Save to table** check box to capture the trace to a database table.</span></span>  
  
         <span data-ttu-id="66f2e-117">При необходимости щелкните **задать максимальное число строк**и укажите значение.</span><span class="sxs-lookup"><span data-stu-id="66f2e-117">Optionally, click **Set maximum rows**, and specify a value.</span></span>  
  
5.  <span data-ttu-id="66f2e-118">При необходимости установите флажок **Включить время остановки трассировки** и укажите дату и время остановки.</span><span class="sxs-lookup"><span data-stu-id="66f2e-118">Optionally, select the **Enable trace stop time** check box, and specify a stop date and time.</span></span>  
  
6.  <span data-ttu-id="66f2e-119">Перейдите на вкладку **Выбор событий**.</span><span class="sxs-lookup"><span data-stu-id="66f2e-119">Click the **Events Selection**tab.</span></span>  
  
7.  <span data-ttu-id="66f2e-120">В столбце данных **События**разверните категорию событий **Блокировки**и установите флажок **Граф взаимоблокировок**.</span><span class="sxs-lookup"><span data-stu-id="66f2e-120">In the **Events**data column, expand the **Locks**event category, and then select the **Deadlock graph**check box.</span></span> <span data-ttu-id="66f2e-121">Если категория событий «Блокировки» недоступна, установите флажок **Показать все события** , чтобы отобразить ее.</span><span class="sxs-lookup"><span data-stu-id="66f2e-121">If the Locks event category is not available, check **Show all events** to display it.</span></span>  
  
     <span data-ttu-id="66f2e-122">Вкладка **Параметры извлечения событий**добавляется в диалоговое окно **Свойства трассировки**.</span><span class="sxs-lookup"><span data-stu-id="66f2e-122">The **Events Extraction Settings**tab is added to the **Trace Properties**dialog box.</span></span>  
  
8.  <span data-ttu-id="66f2e-123">На вкладке **Параметры извлечения событий**щелкните **Сохранение событий XML взаимоблокировок по отдельности**.</span><span class="sxs-lookup"><span data-stu-id="66f2e-123">On the **Events Extraction Settings**tab, click **Save Deadlock XML Events Separately**.</span></span>  
  
9. <span data-ttu-id="66f2e-124">В диалоговом окне **Сохранить как** введите имя файла, куда будут сохранены события графа взаимоблокировок.</span><span class="sxs-lookup"><span data-stu-id="66f2e-124">In the **Save As** dialog box, enter the name of the file in which to store the deadlock graph events.</span></span>  
  
10. <span data-ttu-id="66f2e-125">Щелкните **Все пакеты XML взаимоблокировок в один файл** , чтобы сохранить события графа взаимоблокировок в одном XML-файле, или **Каждый пакет XML взаимоблокировок в отдельный файл**, чтобы создавать новые XML-файлы для каждого графа взаимоблокировок.</span><span class="sxs-lookup"><span data-stu-id="66f2e-125">Click **All Deadlock XML batches in a single file** to save all deadlock graph events in a single XML file, or click **Each Deadlock XML batch in a distinct file**to create a new XML file for each deadlock graph.</span></span>  
  
 <span data-ttu-id="66f2e-126">После сохранения файла взаимоблокировок его можно открыть в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66f2e-126">After you have saved the deadlock file, you can open the file in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="66f2e-127">Дополнительные сведения см. [в разделе Открытие, просмотр и печать файла взаимоблокировок &#40;SQL Server Management Studio&#41;](open-view-and-print-a-deadlock-file-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="66f2e-127">For more information, see [Open, View, and Print a Deadlock File &#40;SQL Server Management Studio&#41;](open-view-and-print-a-deadlock-file-sql-server-management-studio.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66f2e-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="66f2e-128">See Also</span></span>  
 [<span data-ttu-id="66f2e-129">Анализ взаимоблокировок в приложении SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="66f2e-129">Analyze Deadlocks with SQL Server Profiler</span></span>](../../tools/sql-server-profiler/analyze-deadlocks-with-sql-server-profiler.md)  
  
  
