---
title: Страница "журнал отчета" (диспетчер отчетов) | Документация Майкрософт
ms.prod: sql-server-2014
ms.technology: reporting-services-native
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 06/13/2017
ms.openlocfilehash: 4070be8c1d6b0633131e96c665d4551c1b676a9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659358"
---
# <a name="report-history-page-report-manager"></a><span data-ttu-id="66902-102">Страница «Журнал отчета» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="66902-102">Report History Page (Report Manager)</span></span>

<span data-ttu-id="66902-103">Используйте страницу «Журнал отчета» для просмотра моментальных снимков ранее сформированных и сохраненных отчетов.</span><span class="sxs-lookup"><span data-stu-id="66902-103">Use the Report History page to view report snapshots that are generated and stored over time.</span></span> <span data-ttu-id="66902-104">В зависимости от параметров, заданных на сервере отчетов, в журнале отчетов могут содержаться только последние моментальные снимки.</span><span class="sxs-lookup"><span data-stu-id="66902-104">Depending on options that are set on the report server, report history may contain only the more recent snapshots.</span></span>  
  

<span data-ttu-id="66902-105">Журнал отчета всегда просматривается в контексте отчета, к которому он относится.</span><span class="sxs-lookup"><span data-stu-id="66902-105">Report history is always viewed within the context of the report from which it originates.</span></span> <span data-ttu-id="66902-106">Невозможно просмотреть журнал всех отчетов на сервере в одном окне.</span><span class="sxs-lookup"><span data-stu-id="66902-106">You cannot view the history of all reports on a report server in one place.</span></span>  
  
<span data-ttu-id="66902-107">Чтобы создать журнал отчета, отчет должен иметь возможность автоматического выполнения (то есть должен использовать сохраненные учетные данные; параметризованные отчеты должны содержать значения по умолчанию для всех параметров).</span><span class="sxs-lookup"><span data-stu-id="66902-107">To generate report history, the report must be able to run unattended (that is, it must use stored credentials; parameterized reports must contain default parameter values for all parameters).</span></span> <span data-ttu-id="66902-108">Создать журнал отчета можно вручную или по расписанию.</span><span class="sxs-lookup"><span data-stu-id="66902-108">Report history can be generated manually or as a scheduled operation.</span></span> <span data-ttu-id="66902-109">Способ создания журнала отчета определяется его свойствами.</span><span class="sxs-lookup"><span data-stu-id="66902-109">History properties on the report determine the ways in which report history can be created.</span></span>  
  
<span data-ttu-id="66902-110">Чтобы просмотреть моментальный снимок журнала отчета, щелкните журнал отчета.</span><span class="sxs-lookup"><span data-stu-id="66902-110">You can click a report history snapshot to view it.</span></span> <span data-ttu-id="66902-111">Моментальные снимки в журнале отчета различаются только датой и временем создания.</span><span class="sxs-lookup"><span data-stu-id="66902-111">Snapshots that appear in report history are distinguished only by the date and time at which they were created.</span></span> <span data-ttu-id="66902-112">Визуально никак не отображаются данные о том, как был создан моментальный снимок — по расписанию или вручную.</span><span class="sxs-lookup"><span data-stu-id="66902-112">There is no visual indication to distinguish whether a snapshot was generated in response to a schedule or a manual operation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66902-113">Эта функция поддерживается не во всех выпусках [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66902-113">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="66902-114">Перечень функций, поддерживаемых в разных выпусках [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], см. в разделе [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="66902-114">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="66902-115">Навигация</span><span class="sxs-lookup"><span data-stu-id="66902-115">Navigation</span></span>  
 <span data-ttu-id="66902-116">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="66902-116">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-report-history-page"></a><span data-ttu-id="66902-117">Открытие страницы «Журнал отчета»</span><span class="sxs-lookup"><span data-stu-id="66902-117">To open the Report History page</span></span>  
  
1.  <span data-ttu-id="66902-118">Откройте диспетчер отчетов и найдите отчет, для которого необходимо просмотреть моментальные снимки.</span><span class="sxs-lookup"><span data-stu-id="66902-118">Open Report Manager, and locate the report for which you want to view report snapshots.</span></span>  
  
2.  <span data-ttu-id="66902-119">Подведите курсор к отчету и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="66902-119">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="66902-120">В раскрывающемся меню выберите **Просмотр журнала отчета**.</span><span class="sxs-lookup"><span data-stu-id="66902-120">In the drop-down menu, click **View Report History**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="66902-121">Варианты</span><span class="sxs-lookup"><span data-stu-id="66902-121">Options</span></span>  
 <span data-ttu-id="66902-122">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="66902-122">**Delete**</span></span>  
 <span data-ttu-id="66902-123">Нажмите, чтобы удалить моментальные снимки.</span><span class="sxs-lookup"><span data-stu-id="66902-123">Click to delete one or more snapshots.</span></span> <span data-ttu-id="66902-124">Перед нажатием кнопки **Удалить**установите флажок рядом с каждым моментальным снимком, который необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="66902-124">Before clicking **Delete**, select the check box next to the snapshot that you want to delete.</span></span>  
  
 <span data-ttu-id="66902-125">**Создать моментальный снимок**</span><span class="sxs-lookup"><span data-stu-id="66902-125">**New Snapshot**</span></span>  
 <span data-ttu-id="66902-126">Нажмите, чтобы добавить моментальный снимок в журнал отчета.</span><span class="sxs-lookup"><span data-stu-id="66902-126">Click to add a snapshot to report history.</span></span> <span data-ttu-id="66902-127">Это кнопка доступна, если на странице свойств отчета «Журнал» установлен флажок **Разрешить создание журнала отчетов вручную** .</span><span class="sxs-lookup"><span data-stu-id="66902-127">This button is available when you choose the option **Allow history to be created manually** on the History properties page of the report.</span></span>  
  
 <span data-ttu-id="66902-128">**Последний запуск**</span><span class="sxs-lookup"><span data-stu-id="66902-128">**Last Run**</span></span>  
 <span data-ttu-id="66902-129">Позволяет отобразить дату и время создания моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="66902-129">Displays the date and time at which the snapshot was created.</span></span> <span data-ttu-id="66902-130">Для просмотра отдельного моментального снимка щелкните описание.</span><span class="sxs-lookup"><span data-stu-id="66902-130">Click a description to view a particular snapshot.</span></span>  
  
 <span data-ttu-id="66902-131">**Размер**</span><span class="sxs-lookup"><span data-stu-id="66902-131">**Size**</span></span>  
 <span data-ttu-id="66902-132">Позволяет отобразить размер определения отчета, а также данных в отчете.</span><span class="sxs-lookup"><span data-stu-id="66902-132">Displays the size of the report definition plus the data in the report.</span></span> <span data-ttu-id="66902-133">Это значение указывает, сколько места в базе данных сервера отчета занято определением отчетов и данными.</span><span class="sxs-lookup"><span data-stu-id="66902-133">This value indicates how much space in the report server database is used by the report definition and data.</span></span> <span data-ttu-id="66902-134">Отчет, готовый для просмотра, включая форматирование, имеет больший размер.</span><span class="sxs-lookup"><span data-stu-id="66902-134">The size of the rendered report, which includes formatting, is actually larger.</span></span> <span data-ttu-id="66902-135">Общий размер, указанный в скобках, представляет собой сумму размеров всех моментальных снимков в журнале текущего отчета.</span><span class="sxs-lookup"><span data-stu-id="66902-135">The total size, indicated in parentheses, sums the sizes of all snapshots in the report history for the current report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66902-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="66902-136">See Also</span></span>  
 <span data-ttu-id="66902-137">[Просмотр или удаление &#40;журнала отчета диспетчер отчетов&#41;](../../2014/reporting-services/view-or-delete-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="66902-137">[View or Delete Report History &#40;Report Manager&#41;](../../2014/reporting-services/view-or-delete-report-history-report-manager.md) </span></span>  
 <span data-ttu-id="66902-138">[Добавление моментального снимка в журнал отчета &#40;диспетчер отчетов&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="66902-138">[Add a Snapshot to Report History &#40;Report Manager&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span></span>  
 <span data-ttu-id="66902-139">[Страница «Общие свойства», отчеты &#40;диспетчер отчетов&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="66902-139">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 <span data-ttu-id="66902-140">[Справка F1 диспетчер отчетов](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="66902-140">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 [<span data-ttu-id="66902-141">Страница свойств параметров моментального снимка &#40;диспетчер отчетов&#41;</span><span class="sxs-lookup"><span data-stu-id="66902-141">Snapshot Options Properties Page &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/snapshot-options-properties-page-report-manager.md)