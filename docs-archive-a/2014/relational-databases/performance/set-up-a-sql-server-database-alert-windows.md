---
title: Настройка предупреждения базы данных SQL Server (Windows) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server], creating
ms.assetid: 65d2c5c1-921f-4eff-9ef7-149170ab61e8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 090eeda2c134857df18d083ce06d460214aa4dfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668823"
---
# <a name="set-up-a-sql-server-database-alert-windows"></a><span data-ttu-id="176d0-102">Настройка оповещения базы данных SQL Server (Windows)</span><span class="sxs-lookup"><span data-stu-id="176d0-102">Set Up a SQL Server Database Alert (Windows)</span></span>
  <span data-ttu-id="176d0-103">Используя системный монитор, можно создать предупреждение, которое будет выводиться при достижении порогового значения счетчика системного монитора.</span><span class="sxs-lookup"><span data-stu-id="176d0-103">Using System Monitor, you can create an alert to be raised when a threshold value for a System Monitor counter has been reached.</span></span> <span data-ttu-id="176d0-104">В ответ на оповещение системный монитор может запустить то или иное приложение — скажем, приложение, решающее связанную с оповещением проблему.</span><span class="sxs-lookup"><span data-stu-id="176d0-104">In response to the alert, System Monitor can launch an application, such as a custom application written to handle the alert condition.</span></span> <span data-ttu-id="176d0-105">Например, можно создать предупреждение, которое будет выводиться, когда число взаимоблокировок превысит заданное значение.</span><span class="sxs-lookup"><span data-stu-id="176d0-105">For example, you can create an alert that is raised when the number of deadlocks exceeds a specific value.</span></span>  
  
 <span data-ttu-id="176d0-106">Оповещения можно также определять при помощи среды Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] и агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="176d0-106">Alerts also can be defined using Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="176d0-107">Дополнительные сведения см. в статье [Оповещения](../../ssms/agent/alerts.md).</span><span class="sxs-lookup"><span data-stu-id="176d0-107">For more information, see [Alerts](../../ssms/agent/alerts.md).</span></span>  
  
### <a name="to-set-up-a-sql-server-database-alert"></a><span data-ttu-id="176d0-108">Настройка оповещения базы данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="176d0-108">To set up a SQL Server database alert</span></span>  
  
1.  <span data-ttu-id="176d0-109">В дереве навигации окна Производительность разверните узел **Журналы и оповещения производительности**.</span><span class="sxs-lookup"><span data-stu-id="176d0-109">On the navigation tree of the Performance window, expand **Performance Logs and Alerts**.</span></span>  
  
2.  <span data-ttu-id="176d0-110">Щелкните правой кнопкой мыши пункт **Оповещения**и выберите пункт **Новые параметры оповещений**.</span><span class="sxs-lookup"><span data-stu-id="176d0-110">Right-click **Alerts**, and then click **New Alert Settings**.</span></span>  
  
3.  <span data-ttu-id="176d0-111">В диалоговом окне **Новые параметры оповещений** введите имя нового оповещения и щелкните **OK**.</span><span class="sxs-lookup"><span data-stu-id="176d0-111">In the **New Alert Settings** dialog box, type a name for the new alert, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="176d0-112">На вкладке **Общие** диалогового окна нового оповещения введите **Комментарий**и нажмите кнопку **Добавить** , чтобы добавить к оповещению счетчик.</span><span class="sxs-lookup"><span data-stu-id="176d0-112">On the **General** tab of the dialog box for the new alert, add a **Comment**, and click **Add** to add a counter to the alert.</span></span>  
  
     <span data-ttu-id="176d0-113">Каждое оповещение должно быть связано хотя бы с одним счетчиком.</span><span class="sxs-lookup"><span data-stu-id="176d0-113">All alerts must have at least one counter.</span></span>  
  
5.  <span data-ttu-id="176d0-114">В диалоговом окне «Добавить счетчики» выберите объект SQL Server из списка **Объект** , после чего выберите нужный счетчик в поле **Выбрать счетчики из списка**.</span><span class="sxs-lookup"><span data-stu-id="176d0-114">In the Add Counters dialog box, select a SQL Server object from the **Performance Object** list, and then select a counter from the **Select counters from list**.</span></span>  
  
6.  <span data-ttu-id="176d0-115">Чтобы связать счетчик с оповещением, нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="176d0-115">To add the counter to the alert, click **Add**.</span></span> <span data-ttu-id="176d0-116">Далее можно продолжить добавление счетчиков или щелкнуть кнопку **Закрыть** , чтобы вернуться к диалоговому окну нового оповещения.</span><span class="sxs-lookup"><span data-stu-id="176d0-116">You can continue to add counters, or you can click **Close** to return to the dialog box for the new alert.</span></span>  
  
7.  <span data-ttu-id="176d0-117">В диалоговом окне нового предупреждения выберите в списке **Оповещать, когда значение** вариант **Меньше**in the **Меньше** и введите пороговое значение в поле **Предел**.</span><span class="sxs-lookup"><span data-stu-id="176d0-117">In the new alert dialog box, click either **Over** or **Under**in the **Alert when the value is** list, and then enter a threshold value in **Limit**.</span></span>  
  
     <span data-ttu-id="176d0-118">Предупреждение будет выводиться, когда значение счетчика станет больше или меньше порогового значения (это зависит от того, что было выбрано: **Больше** или **Меньше**).</span><span class="sxs-lookup"><span data-stu-id="176d0-118">The alert is generated when the value for the counter is more than or less than the threshold value (depending on whether you clicked **Over** or **Under**).</span></span>  
  
8.  <span data-ttu-id="176d0-119">В поле **Снимать показания каждые** укажите частоту считывания показаний счетчика.</span><span class="sxs-lookup"><span data-stu-id="176d0-119">In the **Sample data every** boxes, set the sampling frequency.</span></span>  
  
9. <span data-ttu-id="176d0-120">На вкладке **Действие** укажите действия, которые будут выполняться в ответ на оповещение.</span><span class="sxs-lookup"><span data-stu-id="176d0-120">On the **Action** tab, set actions to occur every time the alert is triggered.</span></span>  
  
10. <span data-ttu-id="176d0-121">На вкладке **Расписание** укажите время начала и прекращения наблюдения за оповещениями.</span><span class="sxs-lookup"><span data-stu-id="176d0-121">On the **Schedule** tab, set the start and stop schedule for the alert scan.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="176d0-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="176d0-122">See Also</span></span>  
 [<span data-ttu-id="176d0-123">Создание предупреждения для базы данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="176d0-123">Create a SQL Server Database Alert</span></span>](../performance-monitor/create-a-sql-server-database-alert.md)  
  
  
