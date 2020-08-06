---
title: Использование расширенных событий SQL Server (XEvents) для отслеживания Analysis Services | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b57cc2fe-52dc-4fa9-8554-5a866e25c6d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9d12d9bc8d6a56702e1b44f8404b25681a1033f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666255"
---
# <a name="use-sql-server-extended-events-xevents-to-monitor-analysis-services"></a><span data-ttu-id="e1571-102">Использование расширенных событий SQL Server (XEvents) для мониторинга служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="e1571-102">Use SQL Server Extended Events (XEvents) to Monitor Analysis Services</span></span>
  <span data-ttu-id="e1571-103">Analysis Services предоставляет возможности трассировки за счет использования [расширенных событий](../../relational-databases/extended-events/extended-events.md).</span><span class="sxs-lookup"><span data-stu-id="e1571-103">Analysis Services provides tracing capabilities through the usage of [Extended Events](../../relational-databases/extended-events/extended-events.md).</span></span>  
  
 <span data-ttu-id="e1571-104">Расширенные события — это инфраструктура событий с высоким уровнем масштабирования и настройки для серверных систем.</span><span class="sxs-lookup"><span data-stu-id="e1571-104">Extended Events is an event infrastructure that is highly scalable and configurable for server systems.</span></span> <span data-ttu-id="e1571-105">Расширенные события — это упрощенная система мониторинга производительности, в которой применяется очень небольшой объем ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e1571-105">Extended Events is a light weight performance monitoring system that uses very few performance resources.</span></span>  
  
 <span data-ttu-id="e1571-106">Все события Analysis Services могут быть перехвачены и нацелены конкретным потребителям, как определено в [расширенных событиях](../../relational-databases/extended-events/extended-events.md), через XEvents.</span><span class="sxs-lookup"><span data-stu-id="e1571-106">All Analysis Services events can be captured and target to specific consumers, as defined in [Extended Events](../../relational-databases/extended-events/extended-events.md), through XEvents.</span></span>  
  
## <a name="initiating-extended-events-in-analysis-services"></a><span data-ttu-id="e1571-107">Запуск расширенных событий в службах Analysis Services</span><span class="sxs-lookup"><span data-stu-id="e1571-107">Initiating Extended Events in Analysis Services</span></span>  
 <span data-ttu-id="e1571-108">Расширенная трассировка событий включается с помощью команды скрипта создания объекта, аналогичной команде XML для аналитики, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="e1571-108">Extended Event tracing is enabled using a similar XMLA create object script command as shown below:</span></span>  
  
```  
<Execute ...>  
   <Command>  
      <Batch ...>  
         <Create ...>  
            <ObjectDefinition>  
               <Trace>  
                  <ID>trace_id</ID>  
                  <Name>trace_name</Name>  
                  <ddl300_300:XEvent>  
                     <event_session ...>  
                        <event package="AS" name="AS_event">  
                           <action package="PACKAGE0" .../>  
                        </event>  
                        <target package="PACKAGE0" name="asynchronous_file_target">  
                           <parameter name="filename" value="data_filename.xel"/>  
                           <parameter name="metadatafile" value="metadata_filename.xem"/>  
                        </target>  
                     </event_session>  
                  </ddl300_300:XEvent>  
               </Trace>  
            </ObjectDefinition>  
         </Create>  
      </Batch>  
   </Command>  
   <Properties></Properties>  
</Execute>  
  
```  
  
 <span data-ttu-id="e1571-109">Следующие элементы должны быть определены пользователем с учетом потребностей трассировки:</span><span class="sxs-lookup"><span data-stu-id="e1571-109">Where the following elements are to be defined by the user, depending on the tracing needs:</span></span>  
  
 <span data-ttu-id="e1571-110">*trace_id*</span><span class="sxs-lookup"><span data-stu-id="e1571-110">*trace_id*</span></span>  
 <span data-ttu-id="e1571-111">Определяет уникальный идентификатор для данной трассировки.</span><span class="sxs-lookup"><span data-stu-id="e1571-111">Defines the unique identifier for this trace.</span></span>  
  
 <span data-ttu-id="e1571-112">*trace_name*</span><span class="sxs-lookup"><span data-stu-id="e1571-112">*trace_name*</span></span>  
 <span data-ttu-id="e1571-113">Имя, присвоенное данной трассировке. Как правило, понятное определение трассировки.</span><span class="sxs-lookup"><span data-stu-id="e1571-113">The name given to this trace; usually a human readable definition of the trace.</span></span> <span data-ttu-id="e1571-114">Обычно принято использовать в качестве имени значение *trace_id* .</span><span class="sxs-lookup"><span data-stu-id="e1571-114">It is a common practice to use the *trace_id* value as the name.</span></span>  
  
 <span data-ttu-id="e1571-115">*AS_event*</span><span class="sxs-lookup"><span data-stu-id="e1571-115">*AS_event*</span></span>  
 <span data-ttu-id="e1571-116">Событие служб Analysis Services, к которому должен быть предоставлен доступ.</span><span class="sxs-lookup"><span data-stu-id="e1571-116">The Analysis Services event to be exposed.</span></span> <span data-ttu-id="e1571-117">Имена событий см. в разделе [События трассировки служб Analysis Services](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events) .</span><span class="sxs-lookup"><span data-stu-id="e1571-117">See [Analysis Services Trace Events](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events) for names of the events.</span></span>  
  
 <span data-ttu-id="e1571-118">*data_filename*</span><span class="sxs-lookup"><span data-stu-id="e1571-118">*data_filename*</span></span>  
 <span data-ttu-id="e1571-119">Имя файла данных, который содержит данные события.</span><span class="sxs-lookup"><span data-stu-id="e1571-119">The name of the file that contains the events data.</span></span> <span data-ttu-id="e1571-120">Это имя имеет в качестве суффикса отметку времени, что позволяет предотвратить перезапись данных, если одно и то же сообщение трассировки передается снова и снова.</span><span class="sxs-lookup"><span data-stu-id="e1571-120">This name is suffixed with a time stamp to avoid data overwriting if the trace is sent over and over.</span></span>  
  
 <span data-ttu-id="e1571-121">*metadata_filename*</span><span class="sxs-lookup"><span data-stu-id="e1571-121">*metadata_filename*</span></span>  
 <span data-ttu-id="e1571-122">Имя файла данных, который содержит метаданные события.</span><span class="sxs-lookup"><span data-stu-id="e1571-122">The name of the file that contains the events metadata.</span></span> <span data-ttu-id="e1571-123">Это имя имеет в качестве суффикса отметку времени, что позволяет предотвратить перезапись данных, если одно и то же сообщение трассировки передается снова и снова.</span><span class="sxs-lookup"><span data-stu-id="e1571-123">This name is suffixed with a time stamp to avoid data overwriting if the trace is sent over and over.</span></span>  
  
## <a name="stopping-extended-events-in-analysis-services"></a><span data-ttu-id="e1571-124">Останов расширенных событий в службах Analysis Services</span><span class="sxs-lookup"><span data-stu-id="e1571-124">Stopping Extended Events in Analysis Services</span></span>  
 <span data-ttu-id="e1571-125">Чтобы остановить объект расширенных событий трассировки, необходимо удалить этот объект с помощью команды скрипта удаления объекта, аналогичной применяемой в XML для аналитики, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="e1571-125">To stop the Extended Events tracing object you need to delete that object using a similar XMLA delete object script command as shown below:</span></span>  
  
```  
<Execute xmlns="urn:schemas-microsoft-com:xml-analysis">  
   <Command>  
      <Batch ...>  
         <Delete ...>  
            <Object>  
               <TraceID>trace_id</TraceID>  
            </Object>  
         </Delete>  
      </Batch>  
   </Command>  
   <Properties></Properties>  
</Execute>  
  
```  
  
 <span data-ttu-id="e1571-126">Следующие элементы должны быть определены пользователем с учетом потребностей трассировки:</span><span class="sxs-lookup"><span data-stu-id="e1571-126">Where the following elements are to be defined by the user, depending on the tracing needs:</span></span>  
  
 <span data-ttu-id="e1571-127">*trace_id*</span><span class="sxs-lookup"><span data-stu-id="e1571-127">*trace_id*</span></span>  
 <span data-ttu-id="e1571-128">Определяет уникальный идентификатор удаляемой трассировки.</span><span class="sxs-lookup"><span data-stu-id="e1571-128">Defines the unique identifier for the trace to be deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1571-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="e1571-129">See Also</span></span>  
 [<span data-ttu-id="e1571-130">Расширенные события</span><span class="sxs-lookup"><span data-stu-id="e1571-130">Extended Events</span></span>](../../relational-databases/extended-events/extended-events.md)  
  
  
