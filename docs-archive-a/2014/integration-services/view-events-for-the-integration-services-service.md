---
title: Просмотр событий для службы Integration Services | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- events [Integration Services]
- service [Integration Services], events
- Integration Services service, events
ms.assetid: 37e23946-10d1-4116-8568-8fd24067102e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a513c8fc917da2987f3619c8eb9011e1170f7dcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667273"
---
# <a name="view-events-for-the-integration-services-service"></a><span data-ttu-id="e399d-102">просмотреть события службы Integration Services</span><span class="sxs-lookup"><span data-stu-id="e399d-102">View Events for the Integration Services Service</span></span>
  <span data-ttu-id="e399d-103">Для просмотра событий в службе [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] предусмотрены два средства.</span><span class="sxs-lookup"><span data-stu-id="e399d-103">There are two tools in which you can view events for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service:</span></span>  
  
-   <span data-ttu-id="e399d-104">Диалоговое окно **Средство просмотра журнала** в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e399d-104">The **Log File Viewer** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="e399d-105">Диалоговое окно **Средство просмотра журнала** имеет возможности экспорта, фильтрации, а также поиска по журналу.</span><span class="sxs-lookup"><span data-stu-id="e399d-105">The **Log File Viewer** dialog box includes options to export, filter, and search the log.</span></span> <span data-ttu-id="e399d-106">Дополнительные сведения о параметрах в окне **Средство просмотра журнала**см. в разделе [Справка средства просмотра журнала F1](../relational-databases/logs/log-file-viewer-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="e399d-106">For more information about the options in the **Log File Viewer**, see [Log File Viewer F1 Help](../relational-databases/logs/log-file-viewer-f1-help.md).</span></span>  
  
-   <span data-ttu-id="e399d-107">Средство просмотра событий Windows.</span><span class="sxs-lookup"><span data-stu-id="e399d-107">The Windows Event Viewer.</span></span>  
  
 <span data-ttu-id="e399d-108">Описание событий, записываемых в журнал службой [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , см. в разделе [События, зарегистрированные службами Integration Services](service/events-logged-by-the-integration-services-service.md).</span><span class="sxs-lookup"><span data-stu-id="e399d-108">For descriptions of the events logged by the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, see [Events Logged by the Integration Services Service](service/events-logged-by-the-integration-services-service.md).</span></span>  
  
### <a name="to-view-service-events-for-integration-services-in-sql-server-management-studio"></a><span data-ttu-id="e399d-109">Просмотр событий службы, относящихся к службам Integration Services, в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e399d-109">To view service events for Integration Services in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="e399d-110">Откройте среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e399d-110">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="e399d-111">В меню **Файл** выберите пункт **Подключить к обозревателю объектов**.</span><span class="sxs-lookup"><span data-stu-id="e399d-111">On the **File** menu, click **Connect Object Explorer**.</span></span>  
  
3.  <span data-ttu-id="e399d-112">В диалоговом окне **Соединение с сервером** , выберите тип сервера служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , выберите или укажите нахождение сервера для соединения, затем нажмите **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="e399d-112">In the **Connect to Server** dialog box, select the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server type, select or locate the server to connect to, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="e399d-113">Находясь в обозревателе объектов, щелкните правой кнопкой мыши службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , затем выберите пункт **Просмотр журналов**.</span><span class="sxs-lookup"><span data-stu-id="e399d-113">In Object Explorer, right-click [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] and click **View Logs**.</span></span>  
  
5.  <span data-ttu-id="e399d-114">Для просмотра событий служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] выберите **Службы SQL Server Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="e399d-114">To view [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] events, select **SQL Server Integration Services**.</span></span> <span data-ttu-id="e399d-115">Параметр **События NT** автоматически включается и отключается параметром **Службы SQL Server Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="e399d-115">The **NT Events** option is automatically selected and cleared with the **SQL Server Integration Services** option.</span></span>  
  
### <a name="to-view-service-events-for-integration-services-in-windows-event-viewer"></a><span data-ttu-id="e399d-116">Просмотр событий службы, относящихся к службам Integration Services, в программе просмотра событий</span><span class="sxs-lookup"><span data-stu-id="e399d-116">To view service events for Integration Services in Windows Event Viewer</span></span>  
  
1.  <span data-ttu-id="e399d-117">При использовании классического вида **панели управления**щелкните **Администрирование**; если используется вид по категориям, щелкните **Производительность и обслуживание** , а затем **Администрирование**.</span><span class="sxs-lookup"><span data-stu-id="e399d-117">In **Control Panel**, if you are using Classic View, click **Administrative Tools**, or, if you are using Category View, click **Performance and Maintenance** and then click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="e399d-118">Щелкните **Просмотр событий**.</span><span class="sxs-lookup"><span data-stu-id="e399d-118">Click **Event Viewer**.</span></span>  
  
3.  <span data-ttu-id="e399d-119">В диалоговом окне **Просмотр событий** выберите **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="e399d-119">In the **Event Viewer** dialog box, click **Application**.</span></span>  
  
4.  <span data-ttu-id="e399d-120">Найдите в столбце **Источник** оснастки **Приложение** запись со значением **SQLISService**, щелкните ее правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e399d-120">In the **Application** snap-in, locate an entry in the **Source** column that has the value **SQLISService**, right-click the entry, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="e399d-121">При необходимости щелкните стрелку вверх или вниз для просмотра предыдущего или следующего события.</span><span class="sxs-lookup"><span data-stu-id="e399d-121">Optionally, click the up or down arrow to show the previous or next event.</span></span>  
  
6.  <span data-ttu-id="e399d-122">При необходимости щелкните значок «Копировать в буфер обмена» для копирования сведений о событии.</span><span class="sxs-lookup"><span data-stu-id="e399d-122">Optionally, click the Copy to Clipboard icon to copy the event information.</span></span>  
  
7.  <span data-ttu-id="e399d-123">Выберите отображение данных о событии при помощи байтов или слов.</span><span class="sxs-lookup"><span data-stu-id="e399d-123">Choose to display event data using bytes or words.</span></span>  
  
8.  <span data-ttu-id="e399d-124">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e399d-124">Click **OK**.</span></span>  
  
9. <span data-ttu-id="e399d-125">В меню **Консоль** выберите **Выход** для закрытия диалогового окна **Просмотр событий** .</span><span class="sxs-lookup"><span data-stu-id="e399d-125">On the **File** menu, click **Exit** to close the **Event Viewer** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e399d-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="e399d-126">See Also</span></span>  
 <span data-ttu-id="e399d-127">[Управление службой Integration Services](../../2014/integration-services/manage-the-integration-services-service.md) </span><span class="sxs-lookup"><span data-stu-id="e399d-127">[Manage the Integration Services Service](../../2014/integration-services/manage-the-integration-services-service.md) </span></span>  
 [<span data-ttu-id="e399d-128">Добавление журнала для счетчиков производительности потока данных</span><span class="sxs-lookup"><span data-stu-id="e399d-128">Add a Log for Data Flow Performance Counters</span></span>](performance/performance-counters.md)  
  
  
