---
title: Режим предварительного просмотра | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.previewview.f1
helpviewer_keywords:
- Preview view [Reporting Services]
ms.assetid: 108255d1-5be8-47c1-80f3-1f2a055e4d02
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1ff7c59c3ac5143d4f4103edea1a5ee309046547
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732341"
---
# <a name="preview-view"></a><span data-ttu-id="86671-102">Предварительный просмотр</span><span class="sxs-lookup"><span data-stu-id="86671-102">Preview View</span></span>
  <span data-ttu-id="86671-103">Представление **Предварительный просмотр** отображает отчет, готовый для просмотра.</span><span class="sxs-lookup"><span data-stu-id="86671-103">Use **Preview** view to display the rendered report.</span></span> <span data-ttu-id="86671-104">При предварительном просмотре отчета конструктор отчетов выполняет его локально и выводит в представлении «Предварительный просмотр».</span><span class="sxs-lookup"><span data-stu-id="86671-104">When a report is previewed, Report Designer runs the report locally and displays it in the Preview view.</span></span> <span data-ttu-id="86671-105">В режиме просмотра отчет обрабатывается полностью.</span><span class="sxs-lookup"><span data-stu-id="86671-105">In preview mode, the report is processed in full.</span></span> <span data-ttu-id="86671-106">Если отчет содержит сложный запрос или большой объем данных, при первом предварительном просмотре на его формирование может потребоваться несколько минут.</span><span class="sxs-lookup"><span data-stu-id="86671-106">If the report has a complex query or has a large amount of data, preview might take several minutes to complete the first time you view it.</span></span> <span data-ttu-id="86671-107">При внесении последующих изменений, затрагивающих только форматирование отчета, в предварительном просмотре используются кэшированные данные.</span><span class="sxs-lookup"><span data-stu-id="86671-107">For subsequent changes that affect only the format of the report, preview uses cached data.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="86671-108">Если [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] выполняется как удаленное приложение RemoteApp, не удается отобразить отчеты в представлении **Просмотр** в [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86671-108">When [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] is run as a RemoteApp, reports cannot be displayed in **Preview** view in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="86671-109">Программы удаленного приложения RemoteApp — это программы, к которым предоставляется удаленный доступ с помощью служб удаленных рабочих столов.</span><span class="sxs-lookup"><span data-stu-id="86671-109">RemoteApp programs are programs that are accessed remotely through Remote Desktop Services.</span></span> <span data-ttu-id="86671-110">Дополнительные сведения см. в разделе [Пошаговое руководство по удаленному приложению RemoteApp служб терминалов](https://technet.microsoft.com/library/cc730673\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="86671-110">For more information, see [TS RemoteApp Step-by-Step Guide](https://technet.microsoft.com/library/cc730673\(WS.10\).aspx).</span></span>  
  
## <a name="options"></a><span data-ttu-id="86671-111">Варианты</span><span class="sxs-lookup"><span data-stu-id="86671-111">Options</span></span>  
 <span data-ttu-id="86671-112">Панель инструментов позволяет управлять функциями просмотра.</span><span class="sxs-lookup"><span data-stu-id="86671-112">Use the toolbar to manage preview functions.</span></span>  
  
 <span data-ttu-id="86671-113">**Показать или скрыть схему документа**</span><span class="sxs-lookup"><span data-stu-id="86671-113">**Show or Hide Document Map**</span></span>  
 <span data-ttu-id="86671-114">Этот параметр показывает или скрывает схему документа, если она существует.</span><span class="sxs-lookup"><span data-stu-id="86671-114">Choose this option to show or hide the document map if one exists.</span></span>  
  
 <span data-ttu-id="86671-115">**Показать или скрыть область параметров**</span><span class="sxs-lookup"><span data-stu-id="86671-115">**Show or Hide Parameter Area**</span></span>  
 <span data-ttu-id="86671-116">Этот параметр показывает или скрывает поля параметров для отчетов с параметрами.</span><span class="sxs-lookup"><span data-stu-id="86671-116">Choose this option to show or hide the parameters boxes for reports with parameters.</span></span>  
  
 <span data-ttu-id="86671-117">**Первая страница**</span><span class="sxs-lookup"><span data-stu-id="86671-117">**First Page**</span></span>  
 <span data-ttu-id="86671-118">Выберите этот режим для перехода к первой странице отчета.</span><span class="sxs-lookup"><span data-stu-id="86671-118">Choose this option to go to the first page of the report.</span></span>  
  
 <span data-ttu-id="86671-119">**Предыдущая страница**</span><span class="sxs-lookup"><span data-stu-id="86671-119">**Previous Page**</span></span>  
 <span data-ttu-id="86671-120">Выберите этот режим для перехода к предыдущей странице отчета.</span><span class="sxs-lookup"><span data-stu-id="86671-120">Choose this option to go to the previous page of the report.</span></span>  
  
 <span data-ttu-id="86671-121">**Текущая страница**</span><span class="sxs-lookup"><span data-stu-id="86671-121">**Current Page**</span></span>  
 <span data-ttu-id="86671-122">Выводит текущую страницу отчета.</span><span class="sxs-lookup"><span data-stu-id="86671-122">Displays the current page of the report.</span></span>  
  
 <span data-ttu-id="86671-123">**Всего страниц**</span><span class="sxs-lookup"><span data-stu-id="86671-123">**Total Pages**</span></span>  
 <span data-ttu-id="86671-124">Выводит общее количество страниц в данном отчете.</span><span class="sxs-lookup"><span data-stu-id="86671-124">Displays the total number of pages in the report.</span></span>  
  
 <span data-ttu-id="86671-125">**Следующая страница**</span><span class="sxs-lookup"><span data-stu-id="86671-125">**Next Page**</span></span>  
 <span data-ttu-id="86671-126">Выберите этот режим для перехода к следующей странице отчета.</span><span class="sxs-lookup"><span data-stu-id="86671-126">Choose this option to go to the next page of the report.</span></span>  
  
 <span data-ttu-id="86671-127">**Последняя страница**</span><span class="sxs-lookup"><span data-stu-id="86671-127">**Last Page**</span></span>  
 <span data-ttu-id="86671-128">Выберите этот режим для перехода к последней странице отчета.</span><span class="sxs-lookup"><span data-stu-id="86671-128">Choose this option to go to the last page of the report.</span></span>  
  
 <span data-ttu-id="86671-129">**Назад к родительскому отчету**</span><span class="sxs-lookup"><span data-stu-id="86671-129">**Back to Parent Report**</span></span>  
 <span data-ttu-id="86671-130">Выберите для перехода к родительскому отчету.</span><span class="sxs-lookup"><span data-stu-id="86671-130">Choose this option to go to the parent report.</span></span> <span data-ttu-id="86671-131">Этот параметр используется для навигации в детализированном отчете.</span><span class="sxs-lookup"><span data-stu-id="86671-131">This option is used to navigate drillthrough reports.</span></span>  
  
 <span data-ttu-id="86671-132">**Остановить подготовку**</span><span class="sxs-lookup"><span data-stu-id="86671-132">**Stop Rendering**</span></span>  
 <span data-ttu-id="86671-133">Этот параметр останавливает процесс подготовки отчета.</span><span class="sxs-lookup"><span data-stu-id="86671-133">Choose this option to stop the rendering process.</span></span>  
  
 <span data-ttu-id="86671-134">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="86671-134">**Refresh**</span></span>  
 <span data-ttu-id="86671-135">Выберите этот параметр, чтобы обновить кэш данных, и повторно запустите отчет.</span><span class="sxs-lookup"><span data-stu-id="86671-135">Choose this option to refresh the data cache and run the report again.</span></span>  
  
 <span data-ttu-id="86671-136">**Печать**</span><span class="sxs-lookup"><span data-stu-id="86671-136">**Print**</span></span>  
 <span data-ttu-id="86671-137">Выберите этот параметр для печати отчета.</span><span class="sxs-lookup"><span data-stu-id="86671-137">Choose this option to print the report.</span></span>  
  
 <span data-ttu-id="86671-138">**Разметка страницы**</span><span class="sxs-lookup"><span data-stu-id="86671-138">**Print Layout**</span></span>  
 <span data-ttu-id="86671-139">Выберите этот параметр для переключения между предварительным просмотром и просмотром отчета в том виде, в каком он будет напечатан на странице.</span><span class="sxs-lookup"><span data-stu-id="86671-139">Choose this option to toggle between the preview report and the view of the report as it will appear on the printed page.</span></span>  
  
 <span data-ttu-id="86671-140">**Параметры страницы**</span><span class="sxs-lookup"><span data-stu-id="86671-140">**Page Setup**</span></span>  
 <span data-ttu-id="86671-141">Выберите этот параметр для удобного изменения свойств страницы и печати.</span><span class="sxs-lookup"><span data-stu-id="86671-141">Choose this option to conveniently change page and print properties.</span></span> <span data-ttu-id="86671-142">Для просмотра изменений перед печатью воспользуйтесь параметром «Разметка страницы».</span><span class="sxs-lookup"><span data-stu-id="86671-142">Use Print Layout to view changes before printing.</span></span>  
  
 <span data-ttu-id="86671-143">**Экспорт**</span><span class="sxs-lookup"><span data-stu-id="86671-143">**Export**</span></span>  
 <span data-ttu-id="86671-144">Выберите этот параметр, чтобы выполнить экспорт готового к просмотру отчета в другом формате.</span><span class="sxs-lookup"><span data-stu-id="86671-144">Choose this option to export the rendered report in a specific format.</span></span>  
  
 <span data-ttu-id="86671-145">**Масштаб**</span><span class="sxs-lookup"><span data-stu-id="86671-145">**Zoom**</span></span>  
 <span data-ttu-id="86671-146">Выберите значение масштаба, чтобы увеличить или уменьшить отчет.</span><span class="sxs-lookup"><span data-stu-id="86671-146">Select a zoom factor to zoom in or out on the report.</span></span>  
  
 <span data-ttu-id="86671-147">**Поиск текста**</span><span class="sxs-lookup"><span data-stu-id="86671-147">**Search Text**</span></span>  
 <span data-ttu-id="86671-148">Введите текст для поиска в отчете.</span><span class="sxs-lookup"><span data-stu-id="86671-148">Type text to search for a match within the report.</span></span> <span data-ttu-id="86671-149">Использовать операторы поиска нельзя.</span><span class="sxs-lookup"><span data-stu-id="86671-149">You cannot use search operators.</span></span> <span data-ttu-id="86671-150">Выберите пункт **Найти** для поиска первого экземпляра строки.</span><span class="sxs-lookup"><span data-stu-id="86671-150">Click **Find** to search for the first instance.</span></span>  
  
 <span data-ttu-id="86671-151">**Найдено**</span><span class="sxs-lookup"><span data-stu-id="86671-151">**Find**</span></span>  
 <span data-ttu-id="86671-152">Выберите этот параметр для начала поиска в отчете указанного текста.</span><span class="sxs-lookup"><span data-stu-id="86671-152">Choose this option to begin searching the report for the search text.</span></span>  
  
 <span data-ttu-id="86671-153">**Следующий**</span><span class="sxs-lookup"><span data-stu-id="86671-153">**Find Next**</span></span>  
 <span data-ttu-id="86671-154">Выберите этот параметр для поиска следующего экземпляра искомого текста.</span><span class="sxs-lookup"><span data-stu-id="86671-154">Choose this option to search for the next instance of the search text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86671-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="86671-155">See Also</span></span>  
 <span data-ttu-id="86671-156">[Предварительный просмотр отчетов](../reports/previewing-reports.md) </span><span class="sxs-lookup"><span data-stu-id="86671-156">[Previewing Reports](../reports/previewing-reports.md) </span></span>  
 [<span data-ttu-id="86671-157">Справка F1 конструктора отчетов</span><span class="sxs-lookup"><span data-stu-id="86671-157">Report Designer F1 Help</span></span>](report-designer-f1-help.md)  
  
  
