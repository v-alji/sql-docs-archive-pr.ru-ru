---
title: Пример. Создание оповещения агент SQL Server с помощью поставщика WMI для событий сервера | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- SQL Server Agent [WMI]
- WMI Provider for Server Events, samples
- sample applications [WMI]
ms.assetid: d44811c7-cd46-4017-b284-c863ca088e8f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f23a3a8738435dc6a27a230f4521300a3ee2470f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733682"
---
# <a name="sample-creating-a-sql-server-agent-alert-by-using-the-wmi-provider-for-server-events"></a><span data-ttu-id="5f834-102">Образец. Создание предупреждения агента SQL Server с помощью поставщика WMI для событий сервера</span><span class="sxs-lookup"><span data-stu-id="5f834-102">Sample: Creating a SQL Server Agent Alert by Using the WMI Provider for Server Events</span></span>
  <span data-ttu-id="5f834-103">Один из общепринятых способов использования поставщика событий WMI состоит в создании предупреждений агента SQL Server, которые отвечают на конкретные события.</span><span class="sxs-lookup"><span data-stu-id="5f834-103">One common way to use the WMI Event Provider is to create SQL Server Agent alerts that respond to specific events.</span></span> <span data-ttu-id="5f834-104">В следующем образце представлено простое предупреждение, которое сохраняет события графа взаимоблокировок XML в таблице для последующего анализа.</span><span class="sxs-lookup"><span data-stu-id="5f834-104">The following sample presents a simple alert that saves XML deadlock graph events in a table for later analysis.</span></span> <span data-ttu-id="5f834-105">Агент SQL Server отправляет запрос WQL, получает события WMI и запускает задание в ответ на событие.</span><span class="sxs-lookup"><span data-stu-id="5f834-105">SQL Server Agent submits a WQL request, receives WMI events, and runs a job in response to the event.</span></span> <span data-ttu-id="5f834-106">Обратите внимание, что в обработке сообщения уведомления участвуют несколько объектов компонента Service Broker, но детальные операции создания и управления этими объектами возлагаются на поставщика событий WMI.</span><span class="sxs-lookup"><span data-stu-id="5f834-106">Notice that, although several Service Broker objects are involved in processing the notification message, the WMI Event Provider handles the details of creating and managing these objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f834-107">Пример</span><span class="sxs-lookup"><span data-stu-id="5f834-107">Example</span></span>  
 <span data-ttu-id="5f834-108">Прежде всего в базе данных `AdventureWorks` создается таблица для хранения событий графа взаимоблокировок.</span><span class="sxs-lookup"><span data-stu-id="5f834-108">First, a table is created in the `AdventureWorks` database to hold the deadlock graph event.</span></span> <span data-ttu-id="5f834-109">Таблица содержит два столбца: `AlertTime` столбец содержит время запуска оповещения, а `DeadlockGraph` столбец содержит XML-документ, содержащий граф взаимоблокировок.</span><span class="sxs-lookup"><span data-stu-id="5f834-109">The table contains two columns: The `AlertTime` column holds the time that the alert runs, and the `DeadlockGraph` column holds the XML document that contains the deadlock graph.</span></span>  
  
 <span data-ttu-id="5f834-110">Затем создается предупреждение.</span><span class="sxs-lookup"><span data-stu-id="5f834-110">Then, the alert is created.</span></span> <span data-ttu-id="5f834-111">Скрипт сначала создает задание, которое запускается предупреждением, добавляет шаг задания к заданию и направляет задание в текущий экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f834-111">The script first creates the job that the alert will run, adds a job step to the job, and targets the job to the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5f834-112">После этого скрипт создает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="5f834-112">The script then creates the alert.</span></span>  
  
 <span data-ttu-id="5f834-113">Шаг задания извлекает свойство **TextData** экземпляра события WMI и вставляет это значение в столбец **DeadlockGraph** таблицы **DeadlockGraph** .</span><span class="sxs-lookup"><span data-stu-id="5f834-113">The job step retrieves the **TextData** property of the WMI event instance and inserts that value into the **DeadlockGraph** column of the **DeadlockEvents** table.</span></span> <span data-ttu-id="5f834-114">Обратите внимание, что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] неявно преобразует строку в формат XML.</span><span class="sxs-lookup"><span data-stu-id="5f834-114">Notice that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] implicitly converts the string into XML format.</span></span> <span data-ttu-id="5f834-115">Поскольку в шагах задания используется подсистема [!INCLUDE[tsql](../../includes/tsql-md.md)], шаг задания не задает учетной записи-посредника.</span><span class="sxs-lookup"><span data-stu-id="5f834-115">Because the job step uses the [!INCLUDE[tsql](../../includes/tsql-md.md)] subsystem, the job step does not specify a proxy.</span></span>  
  
 <span data-ttu-id="5f834-116">Предупреждение запускает задание каждый раз, когда регистрируется событие трассировки графа взаимоблокировок.</span><span class="sxs-lookup"><span data-stu-id="5f834-116">The alert runs the job whenever a deadlock graph trace event would be logged.</span></span> <span data-ttu-id="5f834-117">Для предупреждения WMI агент SQL Server создает запрос уведомления с использованием пространства имен и указанной инструкции WQL.</span><span class="sxs-lookup"><span data-stu-id="5f834-117">For a WMI alert, SQL Server Agent creates a notification query using the namespace and WQL statement specified.</span></span> <span data-ttu-id="5f834-118">Применительно к этому предупреждению агент SQL Server наблюдает за экземпляром по умолчанию на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5f834-118">For this alert, SQL Server Agent monitors the default instance on the local computer.</span></span> <span data-ttu-id="5f834-119">Инструкция WQL запрашивает любое событие `DEADLOCK_GRAPH` в экземпляре по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5f834-119">The WQL statement requests any `DEADLOCK_GRAPH` event in the default instance.</span></span> <span data-ttu-id="5f834-120">Чтобы изменить экземпляр, за которым ведется наблюдение с помощью предупреждения, измените имя экземпляра на `MSSQLSERVER` в `@wmi_namespace` для события.</span><span class="sxs-lookup"><span data-stu-id="5f834-120">To change the instance that the alert monitors, substitute the instance name for `MSSQLSERVER` in the `@wmi_namespace` for the alert.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f834-121">Для агент SQL Server получения событий WMI [!INCLUDE[ssSB](../../includes/sssb-md.md)] необходимо включить в **msdb** и [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5f834-121">For SQL Server Agent to receive WMI events, [!INCLUDE[ssSB](../../includes/sssb-md.md)] must be enabled in **msdb** and [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
IF OBJECT_ID('DeadlockEvents', 'U') IS NOT NULL  
BEGIN  
    DROP TABLE DeadlockEvents ;  
END ;  
GO  
  
CREATE TABLE DeadlockEvents  
    (AlertTime DATETIME, DeadlockGraph XML) ;  
GO  
-- Add a job for the alert to run.  
  
EXEC  msdb.dbo.sp_add_job @job_name=N'Capture Deadlock Graph',   
    @enabled=1,   
    @description=N'Job for responding to DEADLOCK_GRAPH events' ;  
GO  
  
-- Add a jobstep that inserts the current time and the deadlock graph into  
-- the DeadlockEvents table.  
  
EXEC msdb.dbo.sp_add_jobstep  
    @job_name = N'Capture Deadlock Graph',  
    @step_name=N'Insert graph into LogEvents',  
    @step_id=1,   
    @on_success_action=1,   
    @on_fail_action=2,   
    @subsystem=N'TSQL',   
    @command= N'INSERT INTO DeadlockEvents  
                (AlertTime, DeadlockGraph)  
                VALUES (getdate(), N''$(ESCAPE_SQUOTE(WMI(TextData)))'')',  
    @database_name=N'AdventureWorks' ;  
GO  
  
-- Set the job server for the job to the current instance of SQL Server.  
  
EXEC msdb.dbo.sp_add_jobserver @job_name = N'Capture Deadlock Graph' ;  
GO  
  
-- Add an alert that responds to all DEADLOCK_GRAPH events for  
-- the default instance. To monitor deadlocks for a different instance,  
-- change MSSQLSERVER to the name of the instance.  
  
EXEC msdb.dbo.sp_add_alert @name=N'Respond to DEADLOCK_GRAPH',   
@wmi_namespace=N'\\.\root\Microsoft\SqlServer\ServerEvents\MSSQLSERVER',   
    @wmi_query=N'SELECT * FROM DEADLOCK_GRAPH',   
    @job_name='Capture Deadlock Graph' ;  
GO  
```  
  
## <a name="testing-the-sample"></a><span data-ttu-id="5f834-122">Тестирование образца</span><span class="sxs-lookup"><span data-stu-id="5f834-122">Testing the Sample</span></span>  
 <span data-ttu-id="5f834-123">Чтобы увидеть выполнение задания, следует искусственно вызвать взаимоблокировку.</span><span class="sxs-lookup"><span data-stu-id="5f834-123">To see the job run, provoke a deadlock.</span></span> <span data-ttu-id="5f834-124">В [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] среде Откройте две вкладки **SQL запроса** и подключите оба запроса к одному и тому же экземпляру.</span><span class="sxs-lookup"><span data-stu-id="5f834-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open two **SQL Query** tabs and connect both queries to the same instance.</span></span> <span data-ttu-id="5f834-125">Запустите следующий скрипт в одной из вкладок запроса.</span><span class="sxs-lookup"><span data-stu-id="5f834-125">Run the following script in one of the query tabs.</span></span> <span data-ttu-id="5f834-126">Этот скрипт выдает один результирующий набор и завершает работу.</span><span class="sxs-lookup"><span data-stu-id="5f834-126">This script produces one result set and finishes.</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
BEGIN TRANSACTION ;  
GO  
  
SELECT TOP(1) Name FROM Production.Product WITH (XLOCK) ;  
GO  
```  
  
 <span data-ttu-id="5f834-127">Выполните следующий скрипт на вкладке второго запроса. Этот скрипт создает один результирующий набор, а затем блокирует, ожидая получения блокировки `Production.Product` .</span><span class="sxs-lookup"><span data-stu-id="5f834-127">Run the following script in the second query tab. This script produces one result set and then blocks, waiting to acquire a lock on `Production.Product`.</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
BEGIN TRANSACTION ;  
GO  
  
SELECT TOP(1) Name FROM Production.Location WITH (XLOCK) ;  
GO  
  
SELECT TOP(1) Name FROM Production.Product WITH (XLOCK) ;  
GO  
```  
  
 <span data-ttu-id="5f834-128">Выполните следующий скрипт на вкладке первого запроса. Этот скрипт блокирует, ожидая получения блокировки `Production.Location` .</span><span class="sxs-lookup"><span data-stu-id="5f834-128">Run the following script in the first query tab. This script blocks, waiting to acquire a lock on `Production.Location`.</span></span> <span data-ttu-id="5f834-129">После короткого времени ожидания [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выберет этот скрипт или скрипт в образце в качестве жертвы взаимоблокировки и завершит транзакцию.</span><span class="sxs-lookup"><span data-stu-id="5f834-129">After a short time-out, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will choose either this script or the script in the sample as the deadlock victim and end the transaction.</span></span>  
  
```  
SELECT TOP(1) Name FROM Production.Location WITH (XLOCK) ;  
GO  
```  
  
 <span data-ttu-id="5f834-130">После того как будет искусственно вызвана взаимоблокировка, подождите некоторое время, пока агент SQL Server активирует предупреждение и запустит задание.</span><span class="sxs-lookup"><span data-stu-id="5f834-130">After provoking the deadlock, wait several moments for SQL Server Agent to activate the alert and run the job.</span></span> <span data-ttu-id="5f834-131">Проанализируйте содержимое таблицы `DeadlockEvents`, запустив следующий скрипт:</span><span class="sxs-lookup"><span data-stu-id="5f834-131">Examine the contents of the `DeadlockEvents` table by running the following script:</span></span>  
  
```  
SELECT * FROM DeadlockEvents ;  
GO  
```  
  
 <span data-ttu-id="5f834-132">Столбец `DeadlockGraph` должен содержать XML-документ, который показывает все свойства события графа взаимоблокировок.</span><span class="sxs-lookup"><span data-stu-id="5f834-132">The `DeadlockGraph` column should contain an XML document that shows all the properties of the deadlock graph event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f834-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="5f834-133">See Also</span></span>  
 [<span data-ttu-id="5f834-134">Основные понятия о поставщике WMI для событий сервера</span><span class="sxs-lookup"><span data-stu-id="5f834-134">WMI Provider for Server Events Concepts</span></span>](wmi-provider-for-server-events-concepts.md)  
  
  
