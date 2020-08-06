---
title: Просмотр журналов набора элементов сбора (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], viewing
- collection sets [SQL Server], viewing logs
ms.assetid: 428908b8-fb6a-4d0c-8339-ee133e23aad2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ab7c49e72690b76fa9f416a835f7b5b7b3a4553d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667229"
---
# <a name="view-collection-set-logs-sql-server-management-studio"></a><span data-ttu-id="5fd1a-102">Просмотр журналов набора элементов сбора (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5fd1a-102">View Collection Set Logs (SQL Server Management Studio)</span></span>
  <span data-ttu-id="5fd1a-103">Просмотреть журналы набора сбора, все сразу или по отдельности, можно в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fd1a-103">You can view all the collection set logs or individual collection set logs from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
### <a name="to-view-collection-set-logs"></a><span data-ttu-id="5fd1a-104">Просмотр журналов набора сбора</span><span class="sxs-lookup"><span data-stu-id="5fd1a-104">To view collection set logs</span></span>  
  
1.  <span data-ttu-id="5fd1a-105">В обозревателе объектов раскройте папку **Управление** .</span><span class="sxs-lookup"><span data-stu-id="5fd1a-105">In Object Explorer, expand the **Management** folder.</span></span>  
  
2.  <span data-ttu-id="5fd1a-106">Щелкните правой кнопкой мыши **Сбор данных**и выберите пункт **Просмотр журналов**.</span><span class="sxs-lookup"><span data-stu-id="5fd1a-106">Right-click **Data Collection**, and then click **View Logs**.</span></span>  
  
     <span data-ttu-id="5fd1a-107">При этом открывается **средство просмотра журнала**. Все файлы журнала для каждого набора сбора будут перечислены и предварительно выбраны в узле **Сбор данных** .</span><span class="sxs-lookup"><span data-stu-id="5fd1a-107">This opens the **Log File Viewer**.All the log files for each collection set are listed and pre-selected under the **Data Collection** node in the viewer.</span></span>  
  
3.  <span data-ttu-id="5fd1a-108">Для просмотра журналов только определенных наборов сбора снимите флажки рядом с каждым набором сбора, журналы которых просматривать нет необходимости.</span><span class="sxs-lookup"><span data-stu-id="5fd1a-108">To view specific collection set logs, clear the check box next to each collection set whose log you do not want to view.</span></span> <span data-ttu-id="5fd1a-109">Сведения о журнале для этих наборов сбора будут удалены из панели данных **средства просмотра файлов журнала** .</span><span class="sxs-lookup"><span data-stu-id="5fd1a-109">The log information for that collection set is removed from the **Log File Viewer** details pane.</span></span>  
  
### <a name="to-view-a-specific-collection-set-log-file"></a><span data-ttu-id="5fd1a-110">Просмотр определенного файла журнала набора сбора</span><span class="sxs-lookup"><span data-stu-id="5fd1a-110">To view a specific collection set log file</span></span>  
  
1.  <span data-ttu-id="5fd1a-111">В обозревателе объектов разверните папку **Управление** , затем узел **Сбор данных**.</span><span class="sxs-lookup"><span data-stu-id="5fd1a-111">In Object Explorer, expand the **Management** folder, and then expand **Data Collection**.</span></span>  
  
2.  <span data-ttu-id="5fd1a-112">Щелкните правой кнопкой мыши набор сбора, журнал которого нужно просмотреть, и выберите пункт **Просмотр журналов**.</span><span class="sxs-lookup"><span data-stu-id="5fd1a-112">Right-click the collection set whose log you want to view, and then click **View Logs**.</span></span>  
  
     <span data-ttu-id="5fd1a-113">Откроется **средство просмотра файлов журнала** , отображающий файл журнала только для выбранного набора сбора.</span><span class="sxs-lookup"><span data-stu-id="5fd1a-113">The **Log File Viewer** opens, displaying only the log file for the collection set that you selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fd1a-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="5fd1a-114">See Also</span></span>  
 <span data-ttu-id="5fd1a-115">[Сбор данных](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="5fd1a-115">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="5fd1a-116">Управление сбором данных</span><span class="sxs-lookup"><span data-stu-id="5fd1a-116">Manage Data Collection</span></span>](manage-data-collection.md)  
  
  
