---
title: Установка интервала опроса на целевых серверах | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- interval for polling [SQL Server]
- target servers [SQL Server], polling interval
- polling interval [SQL Server]
ms.assetid: 4ffbbefa-77fb-442e-a77c-cb8c6cab9f3c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 36517f60a99a1a844f6d14d489587eef1de9cb13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751631"
---
# <a name="set-the-polling-interval-for-target-servers"></a><span data-ttu-id="a2e2c-102">Set the Polling Interval for Target Servers</span><span class="sxs-lookup"><span data-stu-id="a2e2c-102">Set the Polling Interval for Target Servers</span></span>
  <span data-ttu-id="a2e2c-103">В этом разделе описывается, как задать частоту, с которой [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Агент обновляет данные с главного сервера на целевые серверы.</span><span class="sxs-lookup"><span data-stu-id="a2e2c-103">This topic describes how to set the frequency that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent refreshes information from the master to the target servers.</span></span> <span data-ttu-id="a2e2c-104">Задание — это указанная последовательность действий, выполняемых агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a2e2c-104">A job is a specified series of actions that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent performs.</span></span> <span data-ttu-id="a2e2c-105">Многосерверное задание — это задание, которое главный сервер выполняет на одном или нескольких целевых серверах.</span><span class="sxs-lookup"><span data-stu-id="a2e2c-105">A multiserver job is a job that a master server runs on one or more target servers.</span></span>  
  
-   <span data-ttu-id="a2e2c-106">**Перед началом работы**  [Безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="a2e2c-106">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="a2e2c-107">**Установка интервала опроса на целевых серверах с использованием следующих средств:**  [SQL Server Management Studio](#SSMS), [Transact-SQL](#TSQL)</span><span class="sxs-lookup"><span data-stu-id="a2e2c-107">**To set the polling interval for target servers, using:**  [SQL Server Management Studio](#SSMS), [Transact-SQL](#TSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a2e2c-108">Перед началом</span><span class="sxs-lookup"><span data-stu-id="a2e2c-108">Before You Begin</span></span>  
 <span data-ttu-id="a2e2c-109">На каждом целевом сервере может одновременно выполняться только один экземпляр одного и того же задания.</span><span class="sxs-lookup"><span data-stu-id="a2e2c-109">Each target server can run one instance of the same job at the same time.</span></span> <span data-ttu-id="a2e2c-110">Каждый целевой сервер периодически опрашивает главный сервер, загружает копию новых назначенных ему заданий и отключается.</span><span class="sxs-lookup"><span data-stu-id="a2e2c-110">Each target server periodically polls the master server, downloads a copy of any new jobs assigned to the target server, and then disconnects.</span></span> <span data-ttu-id="a2e2c-111">Целевой сервер выполняет задание локально, а затем снова подключается к главному серверу, чтобы передать результирующее состояние задания.</span><span class="sxs-lookup"><span data-stu-id="a2e2c-111">The target server runs the job locally and then reconnects to the master server to upload the job outcome status.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a2e2c-112">Если главный сервер недоступен в момент, когда целевой сервер пытается передать состояние задания, то сведения о состоянии задания помещаются в очередь, пока главный сервер не станет доступен.</span><span class="sxs-lookup"><span data-stu-id="a2e2c-112">If the master server is inaccessible when the target server tries to upload job status, the job status is spooled until the master server can be accessed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a2e2c-113">безопасность</span><span class="sxs-lookup"><span data-stu-id="a2e2c-113">Security</span></span>  
 <span data-ttu-id="a2e2c-114">Дополнительные сведения см. в разделах [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) и [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span><span class="sxs-lookup"><span data-stu-id="a2e2c-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) and [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="a2e2c-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a2e2c-115">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="a2e2c-116">**Установка интервала опроса на целевых серверах**</span><span class="sxs-lookup"><span data-stu-id="a2e2c-116">**To set the polling interval for target servers**</span></span>  
  
1.  <span data-ttu-id="a2e2c-117">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="a2e2c-117">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="a2e2c-118">Щелкните правой кнопкой мыши элемент **Агент SQL Server**, укажите пункт **Администрирование нескольких серверов**, а затем выберите пункт **Управление целевыми серверами**.</span><span class="sxs-lookup"><span data-stu-id="a2e2c-118">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="a2e2c-119">На вкладке **Состояние целевого сервера** выберите **Разместить инструкции**.</span><span class="sxs-lookup"><span data-stu-id="a2e2c-119">On the **Target Server Status** tab, click **Post Instructions**.</span></span>  
  
4.  <span data-ttu-id="a2e2c-120">В списке **Тип инструкции** выберите **Установить интервал опроса**.</span><span class="sxs-lookup"><span data-stu-id="a2e2c-120">In the **Instruction type** list, select **Set polling interval**.</span></span>  
  
5.  <span data-ttu-id="a2e2c-121">В диалоговом окне **Интервал опроса** введите количество секунд от 10 до 28 800, которое должно пройти до того, как целевой сервер начнет опрос главного сервера.</span><span class="sxs-lookup"><span data-stu-id="a2e2c-121">In the **Polling interval** box, enter the number of seconds from 10 through 28,800 that must pass before the target server polls the master server.</span></span>  
  
6.  <span data-ttu-id="a2e2c-122">В пункте **Адресаты**выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="a2e2c-122">Under **Recipients**, do one of the following:</span></span>  
  
    1.  <span data-ttu-id="a2e2c-123">Выберите пункт **Все целевые серверы** , если они имеют общий интервал опроса.</span><span class="sxs-lookup"><span data-stu-id="a2e2c-123">Click **All target servers** if all target servers share the same polling interval.</span></span>  
  
    2.  <span data-ttu-id="a2e2c-124">Выберите пункт **Эти целевые серверы** , если не все серверы имеют общий интервал опроса, и выберите каждый целевой сервер, который будет использовать указанный интервал.</span><span class="sxs-lookup"><span data-stu-id="a2e2c-124">Click **These target servers** if not all target servers share the same polling interval, and then select each target server that will use this polling interval.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="a2e2c-125">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a2e2c-125">Using Transact-SQL</span></span>  
 <span data-ttu-id="a2e2c-126">**Установка интервала опроса на целевых серверах**</span><span class="sxs-lookup"><span data-stu-id="a2e2c-126">**To set the polling interval for target servers**</span></span>  
  
1.  <span data-ttu-id="a2e2c-127">В обозревателе объектов подключитесь к экземпляру компонента Database Engine и разверните его.</span><span class="sxs-lookup"><span data-stu-id="a2e2c-127">In Object Explorer, connect to an instance of the Database Engine, and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="a2e2c-128">На панели инструментов нажмите кнопку **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="a2e2c-128">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a2e2c-129">В окне запроса используйте системную хранимую процедуру [sp_post_msx_operation &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) , чтобы задать интервал опроса для целевых серверов.</span><span class="sxs-lookup"><span data-stu-id="a2e2c-129">In the query window, use the [sp_post_msx_operation &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) system stored procedure to set the polling interval for target servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2e2c-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="a2e2c-130">See Also</span></span>  
 [<span data-ttu-id="a2e2c-131">dbo.sysдовнлоадлист &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a2e2c-131">dbo.sysdownloadlist &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-sysdownloadlist-transact-sql)  
  
  
