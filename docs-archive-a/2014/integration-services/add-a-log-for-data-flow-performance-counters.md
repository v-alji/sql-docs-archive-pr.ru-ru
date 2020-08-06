---
title: Добавление журнала для счетчиков производительности потока данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- performance counters [Integration Services]
- counters [Integration Services]
- logs [Integration Services], data flow counters
ms.assetid: b500d166-33ba-4b82-a92d-b0a333924e8d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 489bde1b0e5769f05d1063eb0af2376b659574de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736677"
---
# <a name="add-a-log-for-data-flow-performance-counters"></a><span data-ttu-id="2f97a-102">Добавление журнала для счетчиков производительности потока данных</span><span class="sxs-lookup"><span data-stu-id="2f97a-102">Add a Log for Data Flow Performance Counters</span></span>
  <span data-ttu-id="2f97a-103">В этой процедуре описывается добавление журнала для счетчиков производительности, поставляемых подсистемой обработки потока данных.</span><span class="sxs-lookup"><span data-stu-id="2f97a-103">This procedure describes how to add a log for the performance counters that the data flow engine provides.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f97a-104">Если установить службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на компьютер, где запущена ОС [!INCLUDE[winxpsvr](../includes/winxpsvr-md.md)], а затем обновить ОС до [!INCLUDE[firstref_longhorn](../includes/firstref-longhorn-md.md)], то в процессе обновления из компьютера будут удалены счетчики производительности [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f97a-104">If you install [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] on a computer that is running [!INCLUDE[winxpsvr](../includes/winxpsvr-md.md)], and then upgrade that computer to [!INCLUDE[firstref_longhorn](../includes/firstref-longhorn-md.md)], the upgrade process removes the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] performance counters from the computer.</span></span> <span data-ttu-id="2f97a-105">Чтобы восстановить счетчики производительности служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на компьютере, запустите средство установки [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] в режиме исправлений.</span><span class="sxs-lookup"><span data-stu-id="2f97a-105">To restore the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] performance counters on the computer, run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Setup in repair mode.</span></span>  
  
### <a name="to-add-logging-of-performance-counters"></a><span data-ttu-id="2f97a-106">Добавление ведения журнала счетчиков производительности</span><span class="sxs-lookup"><span data-stu-id="2f97a-106">To add logging of performance counters</span></span>  
  
1.  <span data-ttu-id="2f97a-107">Если используется классический вид **панели управления**, выберите **Администрирование**.</span><span class="sxs-lookup"><span data-stu-id="2f97a-107">In **Control Panel**, if you are using Classic view, click **Administrative Tools**.</span></span> <span data-ttu-id="2f97a-108">Если используется вид по категориям, выберите вначале **Производительность и обслуживание** , затем **Администрирование**.</span><span class="sxs-lookup"><span data-stu-id="2f97a-108">If you are using Category view, click **Performance and Maintenance** and then click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="2f97a-109">Выберите **Производительность**.</span><span class="sxs-lookup"><span data-stu-id="2f97a-109">Click **Performance**.</span></span>  
  
3.  <span data-ttu-id="2f97a-110">В диалоговом окне **Производительность** разверните **Оповещения и журналы производительности**, щелкните правой кнопкой мыши **Журналы счетчиков**и выберите **Новые параметры журнала**.</span><span class="sxs-lookup"><span data-stu-id="2f97a-110">In the **Performance** dialog box, expand **Performance Logs and Alerts**, right-click **Counter Logs**, and then click **New Log Settings**.</span></span> <span data-ttu-id="2f97a-111">Введите имя журнала.</span><span class="sxs-lookup"><span data-stu-id="2f97a-111">Type the name of the log.</span></span> <span data-ttu-id="2f97a-112">Например, введите **Мой_журнал**.</span><span class="sxs-lookup"><span data-stu-id="2f97a-112">For example, type **MyLog**.</span></span>  
  
4.  <span data-ttu-id="2f97a-113">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2f97a-113">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="2f97a-114">В диалоговом окне **Мой_журнал** нажмите кнопку **Добавить счетчики**.</span><span class="sxs-lookup"><span data-stu-id="2f97a-114">In the **MyLog** dialog box, click **Add Counters**.</span></span>  
  
6.  <span data-ttu-id="2f97a-115">Щелкните **Использовать локальные счетчики** , чтобы вести журнал счетчиков производительности на локальном компьютере, или **Выбрать счетчики с компьютера** и выберите из списка компьютер, на котором требуется вести журнал счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="2f97a-115">Click **Use local computer counters** to log performance counters on the local computer, or click **Select counters from computer** and then select a computer from the list to log performance counters on the specified computer.</span></span>  
  
7.  <span data-ttu-id="2f97a-116">В диалоговом окне **Добавить счетчики** из списка **Объект:** выберите **SQL Server:SSIS Pipeline** .</span><span class="sxs-lookup"><span data-stu-id="2f97a-116">In the **Add Counters** dialog box, select **SQL Server:SSIS Pipeline** in the **Performance object** list.</span></span>  
  
8.  <span data-ttu-id="2f97a-117">Чтобы выбрать счетчики производительности, выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="2f97a-117">To select performance counters, do one of the following:</span></span>  
  
    -   <span data-ttu-id="2f97a-118">Выберите **Все счетчики** , чтобы вести журналы всех счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="2f97a-118">Select **All Counters** to log all performance counters.</span></span>  
  
    -   <span data-ttu-id="2f97a-119">Выберите **Выбрать счетчики из списка** , чтобы выбрать нужные счетчики производительности.</span><span class="sxs-lookup"><span data-stu-id="2f97a-119">Select **Select counters in list** and select the performance counters to use.</span></span>  
  
9. <span data-ttu-id="2f97a-120">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2f97a-120">Click **Add**.</span></span>  
  
10. <span data-ttu-id="2f97a-121">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="2f97a-121">Click **Close**.</span></span>  
  
11. <span data-ttu-id="2f97a-122">В диалоговом окне **Мой_журнал** проверьте список счетчиков производительности в списке **Счетчики** .</span><span class="sxs-lookup"><span data-stu-id="2f97a-122">In the **MyLog** dialog box, review the list of logging performance counters in the **Counters** list.</span></span>  
  
12. <span data-ttu-id="2f97a-123">Чтобы ввести дополнительные счетчики, повторите шаги с 5 по 10.</span><span class="sxs-lookup"><span data-stu-id="2f97a-123">To add additional counters, repeat steps 5 through 10.</span></span>  
  
13. <span data-ttu-id="2f97a-124">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2f97a-124">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2f97a-125">Необходимо запустить службу «Журналы и оповещения производительности» с помощью локальной учетной записи или учетной записи домена, входящей в группу «Администраторы».</span><span class="sxs-lookup"><span data-stu-id="2f97a-125">You must start the Performance Logs and Alerts service using a local account or a domain account that is a member of the Administrators group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f97a-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="2f97a-126">See Also</span></span>  
 <span data-ttu-id="2f97a-127">[Счетчики производительности](performance/performance-counters.md) </span><span class="sxs-lookup"><span data-stu-id="2f97a-127">[Performance Counters](performance/performance-counters.md) </span></span>  
 [<span data-ttu-id="2f97a-128">Просмотр записей журнала в окне "Регистрация событий"</span><span class="sxs-lookup"><span data-stu-id="2f97a-128">View Log Entries in the Log Events Window</span></span>](../../2014/integration-services/view-log-entries-in-the-log-events-window.md)  
  
  
