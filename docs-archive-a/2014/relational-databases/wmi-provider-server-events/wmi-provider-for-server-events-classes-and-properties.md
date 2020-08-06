---
title: Поставщик WMI для классов и свойств событий сервера | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- event classes [WMI]
- WMI Provider for Server Events, events listed
- classes [WMI]
ms.assetid: e2916cd7-a3ed-41e6-97b4-2ee060754cbe
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 471e77cb7afa4e6aed441dcbbc8b3b70064f6737
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739614"
---
# <a name="wmi-provider-for-server-events-classes-and-properties"></a><span data-ttu-id="81c0e-102">Поставщик инструментария WMI для классов событий и свойств сервера</span><span class="sxs-lookup"><span data-stu-id="81c0e-102">WMI Provider for Server Events Classes and Properties</span></span>
  <span data-ttu-id="81c0e-103">Следующие события сервера образуют программную модель поставщика WMI для событий сервера.</span><span class="sxs-lookup"><span data-stu-id="81c0e-103">The following server events make up the programming model for the WMI Provider for Server Events.</span></span> <span data-ttu-id="81c0e-104">Существует две основные категории событий, которые могут быть опрошены с помощью запросов WQL к поставщику.</span><span class="sxs-lookup"><span data-stu-id="81c0e-104">There are two main categories of events that can be queried by issuing WQL queries against the provider.</span></span> <span data-ttu-id="81c0e-105">Это события языка описания данных DDL и события трассировки.</span><span class="sxs-lookup"><span data-stu-id="81c0e-105">These are data definition language (DDL) events and trace events.</span></span> <span data-ttu-id="81c0e-106">Запрос также можно выполнять к событиям компонента Service Broker QUEUE_ACTIVATION и BROKER_QUEUE_DISABLED.</span><span class="sxs-lookup"><span data-stu-id="81c0e-106">The QUEUE_ACTIVATION and BROKER_QUEUE_DISABLED service broker events can also be queried.</span></span> <span data-ttu-id="81c0e-107">Обратите внимание на вложенную природу следующих диаграмм.</span><span class="sxs-lookup"><span data-stu-id="81c0e-107">Note the inclusive nature of the following tree diagrams.</span></span> <span data-ttu-id="81c0e-108">Например, событие DDL_ASSEMBLY_EVENTS включает любое из событий ALTER_ASSEMBLY, CREATE_ASSEMBLY и DROP_ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="81c0e-108">The DDL_ASSEMBLY_EVENTS event, for example, includes any ALTER_ASSEMBLY, CREATE_ASSEMBLY, and DROP_ASSEMBLY event.</span></span> <span data-ttu-id="81c0e-109">Аналогично, событие TRC_FULL_TEXT включает любое из событий FT_CRAWL_ABORTED, FT_CRAWL_STARTED и FT_CRAWL_STOPPED.</span><span class="sxs-lookup"><span data-stu-id="81c0e-109">Similarly, the TRC_FULL_TEXT event includes any FT_CRAWL_ABORTED, FT_CRAWL_STARTED, and FT_CRAWL_STOPPED event.</span></span> <span data-ttu-id="81c0e-110">Событие ALL_EVENTS охватывает все DDL-события, события трассировки, QUEUE_ACTIVATION и BROKER_QUEUE_DISABLED.</span><span class="sxs-lookup"><span data-stu-id="81c0e-110">ALL_EVENTS covers all DDL events, trace events, QUEUE_ACTIVATION, and BROKER_QUEUE_DISABLED.</span></span>  
  
 <span data-ttu-id="81c0e-111">Сведения о том, к каким свойствам может быть выполнен запрос из события или группы событий, см. в схеме события.</span><span class="sxs-lookup"><span data-stu-id="81c0e-111">To learn which properties can be queried from an event or event group, refer to the event schema.</span></span> <span data-ttu-id="81c0e-112">По умолчанию схема событий устанавливается в следующий каталог: [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)] Tools\Binn\schemas\sqlserver\2006\11\events\events.xsd.</span><span class="sxs-lookup"><span data-stu-id="81c0e-112">By default, the event schema is installed in the following directory: [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)]Tools\Binn\schemas\sqlserver\2006\11\events\events.xsd.</span></span>  
  
 <span data-ttu-id="81c0e-113">Кроме того, можно обратиться к схеме событий, опубликованной по адресу [https://schemas.microsoft.com/sqlserver](https://go.microsoft.com/fwlink/?linkid=43100) .</span><span class="sxs-lookup"><span data-stu-id="81c0e-113">Alternatively, you can refer to the event schema published at [https://schemas.microsoft.com/sqlserver](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>  
  
 <span data-ttu-id="81c0e-114">Например, при обращении к событию ALTER_DATABASE выясняется, что его родительским событием является DDL_SERVER_LEVEL_EVENTS, а свойствами — `TSQLCommand` и `DatabaseName`.</span><span class="sxs-lookup"><span data-stu-id="81c0e-114">For example, by referring to the ALTER_DATABASE event, you will learn that its parent event is DDL_SERVER_LEVEL_EVENTS and its properties are `TSQLCommand` and `DatabaseName`.</span></span> <span data-ttu-id="81c0e-115">Событие также наследует свойства `SQLInstance`, `PostTime`, `ComputerName`, `SPID` и `LoginName`.</span><span class="sxs-lookup"><span data-stu-id="81c0e-115">The event also inherits the properties `SQLInstance`, `PostTime`, `ComputerName`, `SPID`, and `LoginName`.</span></span> <span data-ttu-id="81c0e-116">Это событие не имеет дочерних событий.</span><span class="sxs-lookup"><span data-stu-id="81c0e-116">The event has no children events.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="81c0e-117">Системные хранимые процедуры, выполняющие DDL-подобные операции, также могут запускать уведомления о событиях.</span><span class="sxs-lookup"><span data-stu-id="81c0e-117">System stored procedures that perform DDL-like operations can also fire event notifications.</span></span> <span data-ttu-id="81c0e-118">Протестируйте свои уведомления о событиях, чтобы определить их реакцию на системные хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="81c0e-118">Test your event notifications to determine their responses to system stored procedures that are run.</span></span> <span data-ttu-id="81c0e-119">Например, инструкция CREATE TYPE и хранимая процедура **sp_addtype** будут вызывать уведомление о событии, созданное для события CREATE_TYPE.</span><span class="sxs-lookup"><span data-stu-id="81c0e-119">For example, the CREATE TYPE statement and **sp_addtype** stored procedure will both fire an event notification that is created on a CREATE_TYPE event.</span></span> <span data-ttu-id="81c0e-120">Дополнительные сведения см. в разделе[DDL Events](../../relational-databases/triggers/ddl-events.md).</span><span class="sxs-lookup"><span data-stu-id="81c0e-120">For more information, see[DDL Events](../../relational-databases/triggers/ddl-events.md).</span></span>  
  
 <span data-ttu-id="81c0e-121">**События и группы событий языка описания данных DDL**</span><span class="sxs-lookup"><span data-stu-id="81c0e-121">**Data Definition Language Events and Event Groups**</span></span>  
  
 <span data-ttu-id="81c0e-122">![Дерево событий поставщика WMI для событий сервера](../../../2014/database-engine/dev-guide/media/sql-wmi-ddl-events-ktm.gif "Дерево событий поставщика WMI для событий сервера")</span><span class="sxs-lookup"><span data-stu-id="81c0e-122">![WMI Provider for Server Events Event Tree](../../../2014/database-engine/dev-guide/media/sql-wmi-ddl-events-ktm.gif "WMI Provider for Server Events Event Tree")</span></span>  
  
 <span data-ttu-id="81c0e-123">**События трассировки и группы событий**</span><span class="sxs-lookup"><span data-stu-id="81c0e-123">**Trace Events and Event Groups**</span></span>  
  
 <span data-ttu-id="81c0e-124">![События трассировки и группы событий](../../../2014/database-engine/dev-guide/media/sql-wmi-trc-all-events.gif "События трассировки и их группы")</span><span class="sxs-lookup"><span data-stu-id="81c0e-124">![Trace events and event groups](../../../2014/database-engine/dev-guide/media/sql-wmi-trc-all-events.gif "Trace events and event groups")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c0e-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="81c0e-125">See Also</span></span>  
 <span data-ttu-id="81c0e-126">[Основные понятия о поставщике WMI для событий сервера](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="81c0e-126">[WMI Provider for Server Events Concepts](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md) </span></span>  
 [<span data-ttu-id="81c0e-127">Использование WQL с поставщиком WMI для событий сервера</span><span class="sxs-lookup"><span data-stu-id="81c0e-127">Using WQL with the WMI Provider for Server Events</span></span>](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md)  
  
  
