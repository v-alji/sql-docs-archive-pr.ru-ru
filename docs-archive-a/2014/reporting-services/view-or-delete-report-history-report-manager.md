---
title: Просмотр или удаление журнала отчета (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report history [Reporting Services], viewing snapshots
- report history [Reporting Services], creating snapshots
- historical data [Reporting Services]
- viewing report snapshots
- report snapshots [Reporting Services], viewing
- report history [Reporting Services], deleting snapshots
- snapshots [Reporting Services], deleting
- snapshots [Reporting Services], viewing
- snapshots [Reporting Services], creating
- removing report snapshots
- report snapshots [Reporting Services], deleting
- deleting report snapshots
- displaying report snapshots
- report snapshots [Reporting Services], creating
ms.assetid: 44cb1e6f-a6b8-498a-8e8b-ca28e7ab1007
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a05c9dccabcf9b937ebd67fb264022761b1ca249
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658067"
---
# <a name="view-or-delete-report-history-report-manager"></a><span data-ttu-id="945d8-102">Просмотр или удаление журнала отчета (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="945d8-102">View or Delete Report History (Report Manager)</span></span>
  <span data-ttu-id="945d8-103">Журнал отчета хранится вместе с отчетом, на основе которого он создан.</span><span class="sxs-lookup"><span data-stu-id="945d8-103">Report history is kept with the report upon which it is based.</span></span> <span data-ttu-id="945d8-104">Журнал отчета может просмотреть любой пользователь, имеющий соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="945d8-104">Any user who has permission to view a report can view its history.</span></span>  
  
### <a name="to-view-a-history-snapshot"></a><span data-ttu-id="945d8-105">Просмотр моментального снимка журнала</span><span class="sxs-lookup"><span data-stu-id="945d8-105">To view a history snapshot</span></span>  
  
1.  <span data-ttu-id="945d8-106">Запустите [Диспетчер отчетов (службы Reporting Services в основном режиме)](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="945d8-106">Start [Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="945d8-107">В диспетчер отчетов перейдите на страницу **содержимое** .</span><span class="sxs-lookup"><span data-stu-id="945d8-107">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="945d8-108">Перейдите к нужному отчету и откройте его.</span><span class="sxs-lookup"><span data-stu-id="945d8-108">Navigate to the report that you want to create or view history snapshots for, and click the report to open it.</span></span>  
  
3.  <span data-ttu-id="945d8-109">Перейдите на вкладку **Журнал** . Моментальные снимки журнала отображаются в столбце **время выполнения** .</span><span class="sxs-lookup"><span data-stu-id="945d8-109">Click the **History** tab. The history snapshots are displayed in the **When Run** column.</span></span>  
  
4.  <span data-ttu-id="945d8-110">Чтобы просмотреть моментального снимка журнала, щелкните этот моментальный снимок.</span><span class="sxs-lookup"><span data-stu-id="945d8-110">To view the history snapshot, click the snapshot.</span></span>  
  
### <a name="to-delete-a-history-snapshot"></a><span data-ttu-id="945d8-111">Удаление моментальных снимков журнала</span><span class="sxs-lookup"><span data-stu-id="945d8-111">To delete a history snapshot</span></span>  
  
1.  <span data-ttu-id="945d8-112">В диспетчер отчетов перейдите на страницу **содержимое** .</span><span class="sxs-lookup"><span data-stu-id="945d8-112">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="945d8-113">Перейдите к отчету, для которого нужно удалить моментальные снимки журналов, и откройте его.</span><span class="sxs-lookup"><span data-stu-id="945d8-113">Navigate to the report that you want to create history snapshots for, and click the report to open it.</span></span>  
  
2.  <span data-ttu-id="945d8-114">Перейдите на вкладку **Журнал** . Моментальные снимки журнала отображаются в столбце **время выполнения** .</span><span class="sxs-lookup"><span data-stu-id="945d8-114">Click the **History** tab. The history snapshots are displayed in the **When Run** column.</span></span>  
  
3.  <span data-ttu-id="945d8-115">Установите флажок напротив моментального снимка журнала, который необходимо удалить, и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="945d8-115">Select the check box next to the history snapshot you want to delete, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="945d8-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="945d8-116">See Also</span></span>  
 <span data-ttu-id="945d8-117">[Добавление моментального снимка в журнал отчета &#40;диспетчер отчетов&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="945d8-117">[Add a Snapshot to Report History &#40;Report Manager&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span></span>  
 <span data-ttu-id="945d8-118">[Диспетчер отчетов &#40;страницы журнала отчета&#41;](../../2014/reporting-services/report-history-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="945d8-118">[Report History Page &#40;Report Manager&#41;](../../2014/reporting-services/report-history-page-report-manager.md) </span></span>  
 <span data-ttu-id="945d8-119">[Установка свойств обработки отчета](report-server/set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="945d8-119">[Set Report Processing Properties](report-server/set-report-processing-properties.md) </span></span>  
 <span data-ttu-id="945d8-120">[Диспетчер отчетов (службы Reporting Services в основном режиме)](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="945d8-120">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="945d8-121">Создание, изменение и удаление моментальных снимков в журнале отчетов</span><span class="sxs-lookup"><span data-stu-id="945d8-121">Create, Modify, and Delete Snapshots in Report History</span></span>](report-server/create-modify-and-delete-snapshots-in-report-history.md)  
  
  
