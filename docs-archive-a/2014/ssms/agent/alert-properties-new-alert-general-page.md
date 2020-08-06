---
title: Свойства предупреждения — Создание предупреждения (страница "Общие") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.alert.general.f1
ms.assetid: f5c11610-62e3-44df-9800-a5dc35be4a09
author: stevestein
ms.author: sstein
ms.openlocfilehash: 471b0062ecc805e83020495e422f8914baec5f71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737499"
---
# <a name="alert-properties-new-alert-general-page"></a><span data-ttu-id="58da9-102">Свойства предупреждения — Создание предупреждения (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="58da9-102">Alert Properties-New Alert (General Page)</span></span>
  <span data-ttu-id="58da9-103">Эта страница используется для просмотра и изменения общих свойств [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предупреждений агента.</span><span class="sxs-lookup"><span data-stu-id="58da9-103">Use this page to view and modify the general properties of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span>  
  
## <a name="options"></a><span data-ttu-id="58da9-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="58da9-104">Options</span></span>  
 <span data-ttu-id="58da9-105">**имя**;</span><span class="sxs-lookup"><span data-stu-id="58da9-105">**Name**</span></span>  
 <span data-ttu-id="58da9-106">Изменить имя предупреждения.</span><span class="sxs-lookup"><span data-stu-id="58da9-106">Change the name of the alert.</span></span>  
  
 <span data-ttu-id="58da9-107">**Разрешить**</span><span class="sxs-lookup"><span data-stu-id="58da9-107">**Enable**</span></span>  
 <span data-ttu-id="58da9-108">Включить предупреждение.</span><span class="sxs-lookup"><span data-stu-id="58da9-108">Enable the alert.</span></span> <span data-ttu-id="58da9-109">Если предупреждение не активировано, действия, указанные в предупреждении, не совершаются.</span><span class="sxs-lookup"><span data-stu-id="58da9-109">When the alert is not enabled, the actions specified in the alert do not occur.</span></span>  
  
 <span data-ttu-id="58da9-110">**Тип**</span><span class="sxs-lookup"><span data-stu-id="58da9-110">**Type**</span></span>  
 <span data-ttu-id="58da9-111">Выбрать тип предупреждения:</span><span class="sxs-lookup"><span data-stu-id="58da9-111">Select the type of alert:</span></span>  
  
-   <span data-ttu-id="58da9-112">**Предупреждение о событии SQL Server** реагирует на сообщения в журнале событий [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="58da9-112">**SQL Server event alert** responds to messages in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows event log.</span></span>  
  
-   <span data-ttu-id="58da9-113">**Предупреждение о производительности SQL Server** реагирует на конкретные условия в счетчике производительности.</span><span class="sxs-lookup"><span data-stu-id="58da9-113">**SQL Server performance condition alert** responds to a specific condition in a performance counter.</span></span>  
  
-   <span data-ttu-id="58da9-114">**Предупреждение о событии WMI** реагирует на событие инструментария управления Windows.</span><span class="sxs-lookup"><span data-stu-id="58da9-114">**WMI event alert** responds to a Windows Management Instrumentation (WMI) event.</span></span>  
  
## <a name="sql-server-event-alert-options"></a><span data-ttu-id="58da9-115">Параметры предупреждений о событиях SQL Server</span><span class="sxs-lookup"><span data-stu-id="58da9-115">SQL Server Event Alert Options</span></span>  
 <span data-ttu-id="58da9-116">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="58da9-116">**Database name**</span></span>  
 <span data-ttu-id="58da9-117">Укажите базу данных для события или **Все базы данных** , чтобы реагировать на сообщение независимо от того, где происходит событие.</span><span class="sxs-lookup"><span data-stu-id="58da9-117">Specify a database for the event, or **all databases** to respond to a message regardless of the database where the event occurs.</span></span>  
  
 <span data-ttu-id="58da9-118">**Номер ошибки**</span><span class="sxs-lookup"><span data-stu-id="58da9-118">**Error number**</span></span>  
 <span data-ttu-id="58da9-119">Укажите, что это событие реагирует на ошибку, и укажите номер ошибки.</span><span class="sxs-lookup"><span data-stu-id="58da9-119">Specify that this event responds to an error, and specify the error number.</span></span>  
  
 <span data-ttu-id="58da9-120">**Уровень серьезности**</span><span class="sxs-lookup"><span data-stu-id="58da9-120">**Severity**</span></span>  
 <span data-ttu-id="58da9-121">Укажите, что это событие реагирует на любое сообщение с указанным уровнем серьезности, и укажите уровень серьезности.</span><span class="sxs-lookup"><span data-stu-id="58da9-121">Specify that this event responds to any message with a specific severity level, and specify the severity level.</span></span>  
  
 <span data-ttu-id="58da9-122">**Создать предупреждение, если сообщение содержит**</span><span class="sxs-lookup"><span data-stu-id="58da9-122">**Raise alert when message contains**</span></span>  
 <span data-ttu-id="58da9-123">Фильтровать события по указанной строке.</span><span class="sxs-lookup"><span data-stu-id="58da9-123">Filter events by a specific string.</span></span> <span data-ttu-id="58da9-124">Когда выбран этот параметр, предупреждение реагирует только на события, содержащие указанную строку.</span><span class="sxs-lookup"><span data-stu-id="58da9-124">When this option is selected, the alert only responds to events that contain a specific string.</span></span>  
  
 <span data-ttu-id="58da9-125">**Текст сообщения**</span><span class="sxs-lookup"><span data-stu-id="58da9-125">**Message text**</span></span>  
 <span data-ttu-id="58da9-126">Укажите строку, которую нужно использовать для фильтрации событий.</span><span class="sxs-lookup"><span data-stu-id="58da9-126">Specify the string to use to filter events.</span></span>  
  
## <a name="sql-server-performance-condition-alerts"></a><span data-ttu-id="58da9-127">Предупреждения о производительности SQL Server</span><span class="sxs-lookup"><span data-stu-id="58da9-127">SQL Server Performance Condition Alerts</span></span>  
 <span data-ttu-id="58da9-128">**Объект**</span><span class="sxs-lookup"><span data-stu-id="58da9-128">**Object**</span></span>  
 <span data-ttu-id="58da9-129">Укажите объект производительности для контроля.</span><span class="sxs-lookup"><span data-stu-id="58da9-129">Specify the performance object to monitor.</span></span>  
  
 <span data-ttu-id="58da9-130">**Счетчик**</span><span class="sxs-lookup"><span data-stu-id="58da9-130">**Counter**</span></span>  
 <span data-ttu-id="58da9-131">Укажите счетчик в объекте производительности для контроля.</span><span class="sxs-lookup"><span data-stu-id="58da9-131">Specify the counter within the performance object to monitor.</span></span>  
  
 <span data-ttu-id="58da9-132">**Экземпляр**</span><span class="sxs-lookup"><span data-stu-id="58da9-132">**Instance**</span></span>  
 <span data-ttu-id="58da9-133">Укажите экземпляр счетчика для контроля.</span><span class="sxs-lookup"><span data-stu-id="58da9-133">Specify the instance of the counter to monitor.</span></span>  
  
 <span data-ttu-id="58da9-134">**Создать предупреждение, если счетчик**</span><span class="sxs-lookup"><span data-stu-id="58da9-134">**Alert if counter**</span></span>  
 <span data-ttu-id="58da9-135">Укажите поведение счетчика, на которое должно реагировать предупреждение.</span><span class="sxs-lookup"><span data-stu-id="58da9-135">Specify the behavior of the counter that the alert responds to.</span></span> <span data-ttu-id="58da9-136">Например, нужно, чтобы предупреждение реагировало на условие, когда значение счетчика **Свободное пространство в tempdb (КБ)** падает ниже определенного значения, или чтобы оповещение реагировало на условие, когда число **Компиляций SQL в секунду** превышает определенное значение.</span><span class="sxs-lookup"><span data-stu-id="58da9-136">For example, you may want the alert to respond to a condition where the value of the **Free space in tempdb (KB)** counter falls below a certain value, or you may want the alert to respond to a condition where the **SQL Compilations/sec** rises above a certain value.</span></span>  
  
 <span data-ttu-id="58da9-137">**Значение**</span><span class="sxs-lookup"><span data-stu-id="58da9-137">**Value**</span></span>  
 <span data-ttu-id="58da9-138">Укажите значение счетчика.</span><span class="sxs-lookup"><span data-stu-id="58da9-138">Specify a value for the counter.</span></span>  
  
## <a name="wmi-event-alert-options"></a><span data-ttu-id="58da9-139">Параметры предупреждения о событии WMI</span><span class="sxs-lookup"><span data-stu-id="58da9-139">WMI Event Alert Options</span></span>  
 <span data-ttu-id="58da9-140">**Пространство имен**</span><span class="sxs-lookup"><span data-stu-id="58da9-140">**Namespace**</span></span>  
 <span data-ttu-id="58da9-141">Укажите пространство имен для использования в инструкции языка запросов инструментария WMI (WQL).</span><span class="sxs-lookup"><span data-stu-id="58da9-141">Specify the namespace to use for the WMI Query Language (WQL) statement.</span></span> <span data-ttu-id="58da9-142">Поддерживаются только пространства имен на компьютере, на котором запущен агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="58da9-142">Only namespaces on the computer that runs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent are supported.</span></span>  
  
 <span data-ttu-id="58da9-143">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="58da9-143">**Query**</span></span>  
 <span data-ttu-id="58da9-144">Укажите инструкцию WQL, определяющую событие, на которое реагирует предупреждение.</span><span class="sxs-lookup"><span data-stu-id="58da9-144">Specify the WQL statement that identifies the event that the alert responds to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58da9-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="58da9-145">See Also</span></span>  
 <span data-ttu-id="58da9-146">[Alerts](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="58da9-146">[Alerts](alerts.md) </span></span>  
 <span data-ttu-id="58da9-147">[Использование WQL с поставщиком WMI для событий сервера](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md) </span><span class="sxs-lookup"><span data-stu-id="58da9-147">[Using WQL with the WMI Provider for Server Events](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md) </span></span>  
 <span data-ttu-id="58da9-148">[Создание предупреждения по номеру ошибки](create-an-alert-using-an-error-number.md) </span><span class="sxs-lookup"><span data-stu-id="58da9-148">[Create an Alert Using an Error Number](create-an-alert-using-an-error-number.md) </span></span>  
 [<span data-ttu-id="58da9-149">Create an Alert Using Severity Level</span><span class="sxs-lookup"><span data-stu-id="58da9-149">Create an Alert Using Severity Level</span></span>](create-an-alert-using-severity-level.md)  
  
  
