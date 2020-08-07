---
title: Запуск SQL Server Profiler | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- Profiler [SQL Server Profiler], starting
- SQL Server Profiler, starting
- starting SQL Server Profiler
ms.assetid: 22e57ffa-63b0-4de3-b92e-df297dda1226
author: stevestein
ms.author: sstein
ms.openlocfilehash: 05743927420865a9b6341fc050ca999f494d64d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734745"
---
# <a name="start-sql-server-profiler"></a><span data-ttu-id="207c2-102">Запуск приложения SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="207c2-102">Start SQL Server Profiler</span></span>
  <span data-ttu-id="207c2-103">[!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] можно запустить несколькими способами, позволяющими получать данные трассировки в различных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="207c2-103">You can start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] in several different ways to support gathering trace output in a variety of scenarios.</span></span> <span data-ttu-id="207c2-104">Можно запустить приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] из меню **Пуск** , из меню **Сервис** в помощнике по настройке компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] и из нескольких мест в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="207c2-104">You can start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] include from the **Start** menu, from the **Tools** menu in [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor, and from several locations in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="207c2-105">При первом запуске [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] и выборе в меню **Файл** пункта **Создать трассировку** приложение отображает диалоговое окно **Соединение с сервером** , где можно указать экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , к которому необходимо подключиться.</span><span class="sxs-lookup"><span data-stu-id="207c2-105">When you first start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and select **New Trace** from the **File** menu, the application displays a **Connect to Server** dialog box where you can specify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to which you want to connect.</span></span>  
  
### <a name="to-start-sql-server-profiler-from-the-start-menu"></a><span data-ttu-id="207c2-106">Запуск приложения SQL Server Profiler из меню «Пуск»</span><span class="sxs-lookup"><span data-stu-id="207c2-106">To start SQL Server Profiler from the Start menu</span></span>  
  
1.  <span data-ttu-id="207c2-107">В меню **Пуск** последовательно укажите **Все программы**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Средства обеспечения производительности**и выберите пункт **SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="207c2-107">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Performance Tools**, and then click **SQL Server Profiler**.</span></span>  
  
### <a name="to-start-sql-server-profiler-in-database-engine-tuning-advisor"></a><span data-ttu-id="207c2-108">Запуск SQL Server Profiler в помощнике по настройке ядра СУБД</span><span class="sxs-lookup"><span data-stu-id="207c2-108">To start SQL Server Profiler in Database Engine Tuning Advisor</span></span>  
  
1.  <span data-ttu-id="207c2-109">В меню [!INCLUDE[ssDE](../../includes/ssde-md.md)] Сервис **помощника по настройке компонента** выберите **SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="207c2-109">On the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor **Tools** menu, click **SQL Server Profiler**.</span></span>  
  
## <a name="starting-sql-server-profiler-in-management-studio"></a><span data-ttu-id="207c2-110">Запуск приложения SQL Server Profiler в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="207c2-110">Starting SQL Server Profiler in Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="207c2-111">запускает каждый сеанс профайлера в отдельном экземпляре, выполнение которого продолжается после завершения работы [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="207c2-111">starts each profiler session in its own instance and continues to run if you shutdown [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="207c2-112">Приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] можно запустить из нескольких мест в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], как показано в следующих процедурах.</span><span class="sxs-lookup"><span data-stu-id="207c2-112">You can start [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] from several locations in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], as illustrated in the following procedures.</span></span> <span data-ttu-id="207c2-113">При запуске приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] загружается контекст соединения, шаблон трассировки и выполняется фильтрация контекста точки запуска.</span><span class="sxs-lookup"><span data-stu-id="207c2-113">When [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] starts it loads the connection context, trace template, and filter context of its launch point.</span></span>  
  
#### <a name="to-start-sql-server-profiler-from-the-tools-menu"></a><span data-ttu-id="207c2-114">Запуск приложения SQL Server Profiler из меню «Инструменты»</span><span class="sxs-lookup"><span data-stu-id="207c2-114">To start SQL Server Profiler from the Tools menu</span></span>  
  
1.  <span data-ttu-id="207c2-115">В меню [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Инструменты** щелкните **SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="207c2-115">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Tools** menu, click **SQL Server Profiler**.</span></span>  
  
#### <a name="to-start-sql-server-profiler-from-the-query-editor"></a><span data-ttu-id="207c2-116">Запуск приложения SQL Server Profiler из редактора запросов</span><span class="sxs-lookup"><span data-stu-id="207c2-116">To start SQL Server Profiler from the Query Editor</span></span>  
  
1.  <span data-ttu-id="207c2-117">В строке меню среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="207c2-117">On the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] menu bar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="207c2-118">В редакторе запросов щелкните правой кнопкой мыши, а затем выберите пункт **Трассировка запроса в приложении SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="207c2-118">In Query Editor, right-click and then select **Trace Query in SQL Server Profiler**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="207c2-119">Контекстом соединения является редактор соединения, шаблон трассировки — TSQL_SP, а применяемый фильтр SPID = окно запроса SPID.</span><span class="sxs-lookup"><span data-stu-id="207c2-119">The connection context is the editor connection, the trace template is TSQL_SPs, and the applied filter is SPID = query window SPID.</span></span>  
  
#### <a name="to-start-sql-server-profiler-from-activity-monitor"></a><span data-ttu-id="207c2-120">Запуск приложения SQL Server Profiler из монитора активности</span><span class="sxs-lookup"><span data-stu-id="207c2-120">To start SQL Server Profiler from Activity Monitor</span></span>  
  
1.  <span data-ttu-id="207c2-121">В обозревателе объектов щелкните правой кнопкой мыши экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]и выберите **Монитор активности**.</span><span class="sxs-lookup"><span data-stu-id="207c2-121">In Object Explorer, right-click an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and then click **Activity Monitor**.</span></span>  
  
2.  <span data-ttu-id="207c2-122">Щелкните панель **Процессы** , щелкните правой кнопкой процесс, который хотите профилировать, а затем выберите пункт **Трассировать процесс в приложении SQL Server Profiler**.</span><span class="sxs-lookup"><span data-stu-id="207c2-122">Click the **Processes** pane, right-click the process that you want to profile, and then click **Trace Process in SQL Server Profiler**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="207c2-123">Когда выбран процесс, контекстом соединения является соединение обозревателя объектов при открытии монитора активности.</span><span class="sxs-lookup"><span data-stu-id="207c2-123">When a process is selected, the connection context is the Object Explorer connection when Activity Monitor was opened.</span></span> <span data-ttu-id="207c2-124">Шаблон трассировки — это шаблон по умолчанию в зависимости от типа сервера, а идентификатор SPID равен идентификатору SPID для выбранного процесса.</span><span class="sxs-lookup"><span data-stu-id="207c2-124">The trace template is the default based on the server type, and the SPID equals the SPID for the selected process.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="207c2-125">Безопасность .NET Framework</span><span class="sxs-lookup"><span data-stu-id="207c2-125">.NET Framework Security</span></span>  
 <span data-ttu-id="207c2-126">В режиме проверки подлинности Windows учетная запись пользователя, от имени которой запускается приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , должна иметь разрешение на соединение с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="207c2-126">In Windows Authentication mode, the user account that runs [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] must have permission to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="207c2-127">Для выполнения трассировки в [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]пользователь должен также иметь разрешение ALTER TRACE.</span><span class="sxs-lookup"><span data-stu-id="207c2-127">To perform tracing with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], users must also have the ALTER TRACE permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="207c2-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="207c2-128">See Also</span></span>  
 <span data-ttu-id="207c2-129">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="207c2-129">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="207c2-130">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="207c2-130">Use SQL Server Management Studio</span></span>](../../database-engine/use-sql-server-management-studio.md)  
  
  
