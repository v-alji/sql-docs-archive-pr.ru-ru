---
title: Свойства сервера (страница "Выполнение") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.execution.f1
ms.assetid: 53b77db1-b013-4dac-82dd-30c0de276639
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f0ec8725a0cec9e15cb6d8402f8d654320c38471
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665232"
---
# <a name="server-properties-execution-page"></a><span data-ttu-id="9aa9b-102">Свойства сервера (страница «Выполнение»)</span><span class="sxs-lookup"><span data-stu-id="9aa9b-102">Server Properties (Execution Page)</span></span>
  <span data-ttu-id="9aa9b-103">Используйте данную страницу для установки значения времени ожидания для выполнения отчета.</span><span class="sxs-lookup"><span data-stu-id="9aa9b-103">Use this page to set a timeout value for report execution.</span></span> <span data-ttu-id="9aa9b-104">Это значение применяется ко всем отчетам, обрабатываемым текущим экземпляром сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9aa9b-104">This value applies to all reports that are processed by the current report server instance.</span></span> <span data-ttu-id="9aa9b-105">Для отдельных отчетов это значение можно заменить.</span><span class="sxs-lookup"><span data-stu-id="9aa9b-105">You can override this value for individual reports.</span></span> <span data-ttu-id="9aa9b-106">Указанное значение должно охватывать все операции по обработке отчета, выполняемые на сервере отчетов, с учетом обработки запросов, выполняемой на сервере базы данных в то время, когда сервер отчетов получает данные, используемые в отчете.</span><span class="sxs-lookup"><span data-stu-id="9aa9b-106">The value you specify must accommodate all report processing that occurs on the report server, plus query processing performed on the database server when the report server retrieves data that is used in the report.</span></span>  
  
 <span data-ttu-id="9aa9b-107">Чтобы открыть эту страницу, в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]подключитесь к экземпляру сервера отчетов, щелкните его правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9aa9b-107">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server instance, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="9aa9b-108">Нажмите кнопку **Выполнение** , чтобы открыть эту страницу.</span><span class="sxs-lookup"><span data-stu-id="9aa9b-108">Click **Execution** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9aa9b-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="9aa9b-109">Options</span></span>  
 <span data-ttu-id="9aa9b-110">**Не задавать время ожидания для выполнения отчета**</span><span class="sxs-lookup"><span data-stu-id="9aa9b-110">**Do not timeout report execution**</span></span>  
 <span data-ttu-id="9aa9b-111">Допускать неограниченное время на сервере отчетов для завершения обработки отчета.</span><span class="sxs-lookup"><span data-stu-id="9aa9b-111">Allow a report server unlimited time to complete report processing.</span></span>  
  
 <span data-ttu-id="9aa9b-112">**Ограничить выполнение отчета следующим количество секунд**</span><span class="sxs-lookup"><span data-stu-id="9aa9b-112">**Limit report execution to the following number of seconds**</span></span>  
 <span data-ttu-id="9aa9b-113">Установить ограничение по продолжительности выполнения отчета.</span><span class="sxs-lookup"><span data-stu-id="9aa9b-113">Set a time constraint on report execution.</span></span> <span data-ttu-id="9aa9b-114">Этот период времени начинается во время запрашивания отчета.</span><span class="sxs-lookup"><span data-stu-id="9aa9b-114">The time period starts when the report is requested.</span></span> <span data-ttu-id="9aa9b-115">Если этот период времени заканчивается до полной обработки отчета, то сервер отчетов отменяет процесс и все связанные с ним запросы к внешним источникам данных.</span><span class="sxs-lookup"><span data-stu-id="9aa9b-115">If the time period ends before the report is fully processed, the report server cancels the process and any in-process queries to external data sources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aa9b-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="9aa9b-116">See Also</span></span>  
 <span data-ttu-id="9aa9b-117">[Установка свойств сервера отчетов (среда Management Studio)](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="9aa9b-117">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="9aa9b-118">[Подключение к серверу отчетов в среде Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="9aa9b-118">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="9aa9b-119">[Установка свойств обработки отчетов](../report-server/set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="9aa9b-119">[Set Report Processing Properties](../report-server/set-report-processing-properties.md) </span></span>  
 <span data-ttu-id="9aa9b-120">[Задание значений времени ожидания при обработке отчетов и общих наборов данных (SSRS)](../report-server/setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9aa9b-120">[Setting Time-out Values for Report and Shared Dataset Processing &#40;SSRS&#41;](../report-server/setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md) </span></span>  
 [<span data-ttu-id="9aa9b-121">Справка F1 по использованию сервера отчетов среде Management Studio</span><span class="sxs-lookup"><span data-stu-id="9aa9b-121">Report Server in Management Studio F1 Help</span></span>](report-server-in-management-studio-f1-help.md)  
  
  
