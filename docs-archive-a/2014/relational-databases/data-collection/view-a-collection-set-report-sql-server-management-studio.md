---
title: Просмотр отчета о наборе элементов сбора (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.reporthistory.calendar.f1
helpviewer_keywords:
- collection sets [SQL Server], viewing reports
- reports [SQL Server], viewing collection set
ms.assetid: c3b1e791-9aa1-4bba-9622-4954568e1820
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cb8755c67e6c03bb318fdb86d703f6d647d5a3eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667230"
---
# <a name="view-a-collection-set-report-sql-server-management-studio"></a><span data-ttu-id="2d05b-102">Просмотр отчета о наборе элементов сбора (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="2d05b-102">View a Collection Set Report (SQL Server Management Studio)</span></span>
  <span data-ttu-id="2d05b-103">После настройки хранилища данных управления можно просмотреть отчет набора элементов сбора в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d05b-103">After you have configured the management data warehouse, you can view a collection set report in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2d05b-104">Для наборов сбора системных данных, устанавливаемых вместе с SQL Server, предоставляются отчеты.</span><span class="sxs-lookup"><span data-stu-id="2d05b-104">Reports are provided for the System Data collection sets that are installed during Setup.</span></span> <span data-ttu-id="2d05b-105">Содержимое этих отчетов:</span><span class="sxs-lookup"><span data-stu-id="2d05b-105">The reports include the following:</span></span>  
  
-   <span data-ttu-id="2d05b-106">Сводка по использованию дискового пространства.</span><span class="sxs-lookup"><span data-stu-id="2d05b-106">Disk Usage Summary</span></span>  
  
-   <span data-ttu-id="2d05b-107">Журнал статистики запросов.</span><span class="sxs-lookup"><span data-stu-id="2d05b-107">Query Statistics History</span></span>  
  
-   <span data-ttu-id="2d05b-108">Журнал активности сервера.</span><span class="sxs-lookup"><span data-stu-id="2d05b-108">Server Activity History</span></span>  
  
 <span data-ttu-id="2d05b-109">Эта процедура отображает отчет для набора элементов сбора **Занято места на диске** .</span><span class="sxs-lookup"><span data-stu-id="2d05b-109">This procedure displays the report for the **Disk Usage** collection set.</span></span> <span data-ttu-id="2d05b-110">Аналогично можно просматривать отчеты для других наборов элементов сбора системных данных.</span><span class="sxs-lookup"><span data-stu-id="2d05b-110">You can follow the same general procedure to view the reports for the other System Data collection sets.</span></span>  
  
### <a name="to-view-a-collection-set-report"></a><span data-ttu-id="2d05b-111">Просмотр отчета набора элементов сбора</span><span class="sxs-lookup"><span data-stu-id="2d05b-111">To view a collection set report</span></span>  
  
1.  <span data-ttu-id="2d05b-112">Таблицы для отчета создаются только при первой передаче собранных данных.</span><span class="sxs-lookup"><span data-stu-id="2d05b-112">The tables for a report are created the first time that the collected data is uploaded.</span></span> <span data-ttu-id="2d05b-113">При попытке просмотра отчета до первой передачи данных возникнет ошибка и отчет не отобразится.</span><span class="sxs-lookup"><span data-stu-id="2d05b-113">If you try to view a report before this first upload, an error occurs and no report is displayed.</span></span> <span data-ttu-id="2d05b-114">Чтобы передать данные для набора элементов сбора "Занято места на диске", разверните папку **Управление** в обозревателе решений, разверните узлы **Сбор данных**и **Системные наборы сбора**, щелкните правой кнопкой мыши набор сбора **Занято места на диске** и выберите пункт **Собрать и передать**.</span><span class="sxs-lookup"><span data-stu-id="2d05b-114">To upload data for the Disk Usage collection set, in Object Explorer, expand the **Management** folder, expand **Data Collection**, expand **System Data Collection Sets**, right-click the **Disk Usage** collection set, and then click **Collect and Upload Now**.</span></span>  
  
2.  <span data-ttu-id="2d05b-115">Чтобы просмотреть отчет, разверните папку **Управление** в обозревателе объектов, щелкните правой кнопкой мыши **Сбор данных**, выберите **Отчеты**и **Хранилище данных управления**, затем щелкните **Сводка по использованию дискового пространства**.</span><span class="sxs-lookup"><span data-stu-id="2d05b-115">To view the report, in Object Explorer, expand the **Management** folder, right-click **Data Collection**, point to **Reports**, point to **Management Data Warehouse**, and then click **Disk Usage Summary**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2d05b-116">Некоторые отчеты могут отображать кнопку календаря под временной шкалой сбора данных.</span><span class="sxs-lookup"><span data-stu-id="2d05b-116">Some reports might display a calendar button under the data collection timeline.</span></span> <span data-ttu-id="2d05b-117">Нажмите эту кнопку для доступа к **Календарю отчета сбора данных**.</span><span class="sxs-lookup"><span data-stu-id="2d05b-117">Click this button to access the **Data Collection Report Calendar**.</span></span>  
  
#### <a name="data-collection-report-calendar"></a><span data-ttu-id="2d05b-118">Календарю отчета сбора данных</span><span class="sxs-lookup"><span data-stu-id="2d05b-118">Data Collection Report Calendar</span></span>  
 <span data-ttu-id="2d05b-119">В этом диалоговом окне можно указать дату и время начала, а также срок, за который нужно подготовить отчет о данных.</span><span class="sxs-lookup"><span data-stu-id="2d05b-119">Use this dialog box to specify the start date, start time, and duration of the data that you want to report on.</span></span> <span data-ttu-id="2d05b-120">Например, можно создать отчет об использовании диска на сервере в течение конкретного 12-часового периода в прошлую среду.</span><span class="sxs-lookup"><span data-stu-id="2d05b-120">For example, you may want to report on the disk usage activity of a server for a specific 12-hour period last Wednesday.</span></span>  
  
 <span data-ttu-id="2d05b-121">**Дата начала**</span><span class="sxs-lookup"><span data-stu-id="2d05b-121">**Start date**</span></span>  
 <span data-ttu-id="2d05b-122">Введите начальную дату данных отчета или выберите дату в календаре.</span><span class="sxs-lookup"><span data-stu-id="2d05b-122">Enter a beginning date for the report data, or select one from the calendar.</span></span>  
  
 <span data-ttu-id="2d05b-123">**Время начала**</span><span class="sxs-lookup"><span data-stu-id="2d05b-123">**Start time**</span></span>  
 <span data-ttu-id="2d05b-124">Введите начальное время данных отчета или укажите его, нажимая стрелки.</span><span class="sxs-lookup"><span data-stu-id="2d05b-124">Enter a beginning time for the report data or specify one by clicking the arrows.</span></span>  
  
 <span data-ttu-id="2d05b-125">**Длительность**</span><span class="sxs-lookup"><span data-stu-id="2d05b-125">**Duration**</span></span>  
 <span data-ttu-id="2d05b-126">Выберите временной диапазон для включения в отчет.</span><span class="sxs-lookup"><span data-stu-id="2d05b-126">Specify the time range to include in the report.</span></span> <span data-ttu-id="2d05b-127">Значение по умолчанию составляет 240 минут.</span><span class="sxs-lookup"><span data-stu-id="2d05b-127">The default value is 240 minutes.</span></span> <span data-ttu-id="2d05b-128">Возможные значения для выбора составляют 15 мин, 60 мин, 240 мин (4 часа), 720 мин (12 часов) и 1440 мин (24 часа).</span><span class="sxs-lookup"><span data-stu-id="2d05b-128">The possible values to select from are 15 minutes, 60 minutes, 240 minutes (4 hours), 720 minutes (12 hours), and 1440 minutes (24 hours).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d05b-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="2d05b-129">See Also</span></span>  
 <span data-ttu-id="2d05b-130">[Сбор данных](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="2d05b-130">[Data Collection](data-collection.md) </span></span>  
 <span data-ttu-id="2d05b-131">[Пользовательские отчеты в среде Management Studio](../../ssms/object/custom-reports-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="2d05b-131">[Custom Reports in Management Studio](../../ssms/object/custom-reports-in-management-studio.md) </span></span>  
 [<span data-ttu-id="2d05b-132">Настройка хранилища данных управления (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="2d05b-132">Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;</span></span>](configure-the-management-data-warehouse-sql-server-management-studio.md)  
  
  
