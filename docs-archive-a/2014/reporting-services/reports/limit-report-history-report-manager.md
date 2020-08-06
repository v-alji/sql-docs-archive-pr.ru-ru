---
title: Ограничение размеров журнала отчета (диспетчер отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- viewing report history
- report history [Reporting Services], viewing history
- report history [Reporting Services], configuring history
- historical data [Reporting Services]
- displaying report history
ms.assetid: 8e255792-d9ef-496f-a26c-9e969c1209a0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01318b1e1ccf0b0bf4512ab57de90cbf5ebc7365
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730102"
---
# <a name="limit-report-history-report-manager"></a><span data-ttu-id="9bcce-102">Ограничение размеров журнала отчета (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="9bcce-102">Limit Report History (Report Manager)</span></span>
  <span data-ttu-id="9bcce-103">Журнал отчета — это коллекция моментальных снимков отчета, созданных на протяжении определенного времени.</span><span class="sxs-lookup"><span data-stu-id="9bcce-103">Report history is a collection of report snapshots that you create over time.</span></span> <span data-ttu-id="9bcce-104">Можно создавать журнал отчета по запросу или определить в расписании, насколько часто должен создаваться моментальный снимок и добавляться к журналу.</span><span class="sxs-lookup"><span data-stu-id="9bcce-104">You can create report history on demand, or schedule how often a snapshot is created and added to report history.</span></span>  
  
 <span data-ttu-id="9bcce-105">Журнал отчета хранится в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9bcce-105">Report history is stored in the report server database.</span></span> <span data-ttu-id="9bcce-106">Если моментальные снимки отчета содержат большое количество данных, можно ограничить объема журнала отчета, чтобы свести к минимуму влияние сохранения моментального снимка на размер базы данных.</span><span class="sxs-lookup"><span data-stu-id="9bcce-106">If report snapshots contain a large amount of data, you might consider limiting report history to minimize the affect of snapshot retention on database size.</span></span>  
  
### <a name="to-configure-report-history-for-a-report-server"></a><span data-ttu-id="9bcce-107">Настройка журнала отчетов на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="9bcce-107">To configure report history for a report server</span></span>  
  
1.  <span data-ttu-id="9bcce-108">В диспетчере отчетов щелкните **Параметры веб-сайта** на главной панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="9bcce-108">In Report Manager, click **Site Settings** on the global toolbar.</span></span>  
  
2.  <span data-ttu-id="9bcce-109">Для сохранения всех без исключения моментальных снимков журнала отчетов выберите **Хранить в журнале отчета неограниченное количество моментальных снимков** .</span><span class="sxs-lookup"><span data-stu-id="9bcce-109">Select **Keep an unlimited number of snapshots in report history** if you want to keep all report history indefinitely.</span></span> <span data-ttu-id="9bcce-110">Кроме того, чтобы задать максимальное число моментальных снимков, которые могут храниться для каждого отчета, выберите **Ограничить количество копий журнала отчета** .</span><span class="sxs-lookup"><span data-stu-id="9bcce-110">Otherwise, select **Limit the copies of report history** to specify the maximum number of snapshots that can be kept for any given report.</span></span>  
  
3.  <span data-ttu-id="9bcce-111">Щелкните **Применить**.</span><span class="sxs-lookup"><span data-stu-id="9bcce-111">Click **Apply**.</span></span>  
  
### <a name="to-configure-report-history-for-a-specific-report"></a><span data-ttu-id="9bcce-112">Настройка журнала для определенного отчета</span><span class="sxs-lookup"><span data-stu-id="9bcce-112">To configure report history for a specific report</span></span>  
  
1.  <span data-ttu-id="9bcce-113">В диспетчере отчетов перейдите к отчету, журнал которого нужно настроить, и щелкните отчет, чтобы открыть его.</span><span class="sxs-lookup"><span data-stu-id="9bcce-113">In Report Manager, navigate to the report for which you want to configure history, and then click the report to open it.</span></span>  
  
2.  <span data-ttu-id="9bcce-114">Щелкните вкладку **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9bcce-114">Click the **Properties** tab.</span></span>  
  
3.  <span data-ttu-id="9bcce-115">Перейдите на вкладку **Журнал**.</span><span class="sxs-lookup"><span data-stu-id="9bcce-115">Click the **History** tab.</span></span>  
  
4.  <span data-ttu-id="9bcce-116">Выберите параметры отчета и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="9bcce-116">Select the options for your report and click **Apply**.</span></span> <span data-ttu-id="9bcce-117">Подробные сведения о каждом параметре см. в разделе [Страница "Свойства параметров моментального снимка" (диспетчер отчетов)](../snapshot-options-properties-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="9bcce-117">For details about each option, see [Snapshot Options Properties Page &#40;Report Manager&#41;](../snapshot-options-properties-page-report-manager.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bcce-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="9bcce-118">See Also</span></span>  
 <span data-ttu-id="9bcce-119">[Добавление моментального снимка в журнал отчета &#40;диспетчер отчетов&#41;](../report-server/add-a-snapshot-to-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="9bcce-119">[Add a Snapshot to Report History &#40;Report Manager&#41;](../report-server/add-a-snapshot-to-report-history-report-manager.md) </span></span>  
 [<span data-ttu-id="9bcce-120">Диспетчер отчетов (службы Reporting Services в основном режиме)</span><span class="sxs-lookup"><span data-stu-id="9bcce-120">Report Manager  &#40;SSRS Native Mode&#41;</span></span>](../report-manager-ssrs-native-mode.md)  
  
  
