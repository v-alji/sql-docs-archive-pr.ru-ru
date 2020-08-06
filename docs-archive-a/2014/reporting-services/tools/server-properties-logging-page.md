---
title: Свойства сервера (страница "Ведение журнала") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.logging.f1
ms.assetid: b338deab-4868-4951-9f22-0605add2fc95
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2a04c27fd790a1ad5c4ba453b43af5983a6440e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665231"
---
# <a name="server-properties-logging-page"></a><span data-ttu-id="86950-102">Свойства сервера (страница «Регистрация»)</span><span class="sxs-lookup"><span data-stu-id="86950-102">Server Properties (Logging Page)</span></span>
  <span data-ttu-id="86950-103">Эта страница используется для задания предельных значений данных, собираемых сервером отчетов при выполнении отчета.</span><span class="sxs-lookup"><span data-stu-id="86950-103">Use this page to set limits on the report execution data that is collected by a report server.</span></span> <span data-ttu-id="86950-104">Данные выполнения сохраняются самим приложением в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="86950-104">Execution data is stored internally in the report server database.</span></span> <span data-ttu-id="86950-105">Предусмотрена возможность отслеживать действия с отчетами применительно к серверу отчетов, который работает в собственном режиме или в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="86950-105">You can track report activity for report server that runs in native mode or SharePoint integrated mode.</span></span> <span data-ttu-id="86950-106">Если сервер отчетов представляет собой часть масштабного развертывания, то в журнале выполнения отчета ведется регистрация всех действий с отчетами для всего проекта развертывания в виде одного файла журнала.</span><span class="sxs-lookup"><span data-stu-id="86950-106">If the report server is part of a scale-out deployment, the report execution log maintains a record of all report activity for the entire deployment in a single log file.</span></span>  
  
 <span data-ttu-id="86950-107">Чтобы открыть эту страницу, запустите среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], подключитесь к серверу отчетов, щелкните правой кнопкой мыши имя сервера отчетов и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="86950-107">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="86950-108">Нажмите кнопку **Ведение журнала** , чтобы открыть эту страницу.</span><span class="sxs-lookup"><span data-stu-id="86950-108">Click **Logging** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="86950-109">Варианты</span><span class="sxs-lookup"><span data-stu-id="86950-109">Options</span></span>  
 <span data-ttu-id="86950-110">**Включить ведение журнала выполнения отчета**</span><span class="sxs-lookup"><span data-stu-id="86950-110">**Enable report execution logging**</span></span>  
 <span data-ttu-id="86950-111">Щелкните, чтобы создать и сохранить данные о действиях с отчетами на сервере.</span><span class="sxs-lookup"><span data-stu-id="86950-111">Click to create and store information about report activity on the server.</span></span> <span data-ttu-id="86950-112">Если этот параметр включен, то сервер отчетов отслеживает используемые отчеты, частоту выполнения отчетов, типы выполненных операций с отчетами, форматы вывода и тех, кто вызвал отчет на выполнение.</span><span class="sxs-lookup"><span data-stu-id="86950-112">If this option is enabled, the report server will track which reports are used, the frequency of report processing, the type of report operation that was performed, the output format, and who ran the report.</span></span> <span data-ttu-id="86950-113">Дополнительные сведения о дополнительных точках данных, записанных в журнал, см. в разделе [Журнал выполнения сервера отчетов и представление ExecutionLog3](../report-server/report-server-executionlog-and-the-executionlog3-view.md).</span><span class="sxs-lookup"><span data-stu-id="86950-113">For more information about additional data points that are captured in the log, see [Report Server Execution Log and the ExecutionLog3 View](../report-server/report-server-executionlog-and-the-executionlog3-view.md).</span></span>  
  
 <span data-ttu-id="86950-114">**Удалить записи журнала, произведенные более заданного количества дней тому назад**</span><span class="sxs-lookup"><span data-stu-id="86950-114">**Remove log entries older than this number of days**</span></span>  
 <span data-ttu-id="86950-115">Задается количество дней, после которого записи журнала будут удалены из журнала выполнения отчета.</span><span class="sxs-lookup"><span data-stu-id="86950-115">Specify the number of days after which log entries will be trimmed from the report execution log.</span></span> <span data-ttu-id="86950-116">Значение по умолчанию — 60 суток.</span><span class="sxs-lookup"><span data-stu-id="86950-116">The default value is 60 days.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86950-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="86950-117">See Also</span></span>  
 <span data-ttu-id="86950-118">[Установка свойств сервера отчетов &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="86950-118">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="86950-119">[Соединение с сервером отчетов в Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="86950-119">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="86950-120">[Файлы и источники журналов служб Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="86950-120">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 <span data-ttu-id="86950-121">[Сервер отчетов в справке Management Studio F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="86950-121">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="86950-122">Журнал выполнения сервера отчетов и представление ExecutionLog3</span><span class="sxs-lookup"><span data-stu-id="86950-122">Report Server Execution Log and the ExecutionLog3 View</span></span>](../report-server/report-server-executionlog-and-the-executionlog3-view.md)  
  
  
