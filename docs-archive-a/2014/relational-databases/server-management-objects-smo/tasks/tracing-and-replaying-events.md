---
title: Трассировка и воспроизведение событий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- replaying events
- traces [SMO]
- events [SMO], replaying
- events [SMO], tracing
ms.assetid: f41b3f85-2f6c-4c3e-9776-8c73d2cc7a53
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7f0d570c70ef1cba080217e6c3a0f9b6055a4d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732497"
---
# <a name="tracing-and-replaying-events"></a><span data-ttu-id="ce8d7-102">Трассировка и воспроизведение событий</span><span class="sxs-lookup"><span data-stu-id="ce8d7-102">Tracing and Replaying Events</span></span>
  <span data-ttu-id="ce8d7-103">В SMO объекты `Trace` и `Replay` в пространстве имен <xref:Microsoft.SqlServer.Management.Trace> обеспечивают программный доступ к функциональности приложения [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)], которая используется для наблюдения за экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] или служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce8d7-103">In SMO, the `Trace` and `Replay` objects in the <xref:Microsoft.SqlServer.Management.Trace> namespace provide programmatic access to the [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] functionality, which is used for monitoring an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="ce8d7-104">Приложение позволяет собирать и сохранять данные о каждом событии в файле или в таблице для последующего анализа.</span><span class="sxs-lookup"><span data-stu-id="ce8d7-104">You can capture and save data about each event to a file or table to analyze later.</span></span> <span data-ttu-id="ce8d7-105">Например, с помощью приложения можно наблюдать за рабочей средой, чтобы определить, какие процедуры сказываются на производительности из-за того, что выполняются слишком медленно.</span><span class="sxs-lookup"><span data-stu-id="ce8d7-105">For example, you can monitor a production environment to see which procedures are impeding performance by executing too slowly.</span></span>  
  
 <span data-ttu-id="ce8d7-106">Объекты `Trace` и `Replay` предоставляют набор объектов, которые можно использовать для создания трассировок экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce8d7-106">The `Trace` and `Replay` objects provide a set of objects that can be used to create traces on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ce8d7-107">Эти объекты можно использовать из пользовательских приложений для создания вручную трассировок для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] или служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce8d7-107">These objects can be used from within your own applications to create traces manually for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="ce8d7-108">Кроме того, объекты `Trace` SMO можно использовать для чтения файлов трассировок SQL и таблиц, которые были созданы при наблюдении за [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], службами [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] и операциями с журналом DTS.</span><span class="sxs-lookup"><span data-stu-id="ce8d7-108">Additionally, SMO `Trace` objects can be used to read SQL Trace files and tables that were created by monitoring [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], or DTS logging.</span></span>  
  
 <span data-ttu-id="ce8d7-109">Объекты `Trace` SMO позволяют выполнять следующие функции:</span><span class="sxs-lookup"><span data-stu-id="ce8d7-109">SMO `Trace` objects let you perform the following functions:</span></span>  
  
-   <span data-ttu-id="ce8d7-110">создать трассировку;</span><span class="sxs-lookup"><span data-stu-id="ce8d7-110">Create a trace.</span></span>  
  
-   <span data-ttu-id="ce8d7-111">назначить фильтры для трассировки;</span><span class="sxs-lookup"><span data-stu-id="ce8d7-111">Set filters on the trace.</span></span>  
  
-   <span data-ttu-id="ce8d7-112">назначить отслеживаемые события;</span><span class="sxs-lookup"><span data-stu-id="ce8d7-112">Set the events that are being traced.</span></span>  
  
-   <span data-ttu-id="ce8d7-113">остановить и запустить трассировку;</span><span class="sxs-lookup"><span data-stu-id="ce8d7-113">Stop or start a trace.</span></span>  
  
-   <span data-ttu-id="ce8d7-114">прочитать файлы трассировки и таблицы трассировки;</span><span class="sxs-lookup"><span data-stu-id="ce8d7-114">Read trace files, and trace tables.</span></span>  
  
-   <span data-ttu-id="ce8d7-115">получить сведения о событиях трассировки;</span><span class="sxs-lookup"><span data-stu-id="ce8d7-115">Get information about events on a trace.</span></span>  
  
-   <span data-ttu-id="ce8d7-116">получить сведения о фильтрах трассировки;</span><span class="sxs-lookup"><span data-stu-id="ce8d7-116">Get information about filters on a trace.</span></span>  
  
-   <span data-ttu-id="ce8d7-117">программно управлять данными трассировки;</span><span class="sxs-lookup"><span data-stu-id="ce8d7-117">Manipulate trace data programmatically.</span></span>  
  
-   <span data-ttu-id="ce8d7-118">записать файлы и таблицы трассировки;</span><span class="sxs-lookup"><span data-stu-id="ce8d7-118">Write trace tables and trace files.</span></span>  
  
-   <span data-ttu-id="ce8d7-119">воспроизвести файлы и таблицы трассировки.</span><span class="sxs-lookup"><span data-stu-id="ce8d7-119">Replay trace files or trace tables.</span></span>  
  
 <span data-ttu-id="ce8d7-120">Данные трассировки из `Trace` `Replay` объектов и могут использоваться приложением SMO или могут быть проверены вручную с помощью [SQL Server Profiler](../../../tools/sql-server-profiler/sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="ce8d7-120">The trace data from the `Trace` and `Replay` objects can be used by the SMO application, or it can be examined manually by using [SQL Server Profiler](../../../tools/sql-server-profiler/sql-server-profiler.md).</span></span> <span data-ttu-id="ce8d7-121">Данные трассировки также совместимы с хранимыми процедурами [SQL Trace](../../sql-trace/sql-trace.md) , которые также обеспечивают возможности трассировки.</span><span class="sxs-lookup"><span data-stu-id="ce8d7-121">The trace data is also compatible with the [SQL Trace](../../sql-trace/sql-trace.md) stored procedures that also provide tracing capabilities.</span></span>  
  
 <span data-ttu-id="ce8d7-122">Объекты трассировки SMO находятся в пространстве имен <xref:Microsoft.SqlServer.Management.Trace>, для использования которого необходима ссылка на файл Microsoft.SQLServer.ConnectionInfo.dll.</span><span class="sxs-lookup"><span data-stu-id="ce8d7-122">The SMO trace objects reside in the <xref:Microsoft.SqlServer.Management.Trace> namespace, which requires a reference to the Microsoft.SQLServer.ConnectionInfo.dll file.</span></span>  
  
 <span data-ttu-id="ce8d7-123">Объекты `Trace` и `Replay` требуют наличия объекта <xref:Microsoft.SqlServer.Management.Common.ServerConnection><xref:Microsoft.SqlServer.Management.Smo.Server.%23ctor%2A> для установления соединения с экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce8d7-123">The `Trace` and `Replay` objects require a <xref:Microsoft.SqlServer.Management.Common.ServerConnection><xref:Microsoft.SqlServer.Management.Smo.Server.%23ctor%2A> object to establish a connection with the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ce8d7-124">Объект <xref:Microsoft.SqlServer.Management.Common.ServerConnection> находится в пространстве имен <xref:Microsoft.SqlServer.Management.Common>, для которого необходима ссылка на файл Microsoft.SQLServer.ConnectionInfo.dll.</span><span class="sxs-lookup"><span data-stu-id="ce8d7-124">The <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object resides in the <xref:Microsoft.SqlServer.Management.Common> namespace, which requires a reference to the Microsoft.SQLServer.ConnectionInfo.dll file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ce8d7-125">Объекты `Trace` и `Replay` не поддерживаются в 64-разрядной версии платформы.</span><span class="sxs-lookup"><span data-stu-id="ce8d7-125">The `Trace` and `Replay` objects are not supported on a 64-bit platform.</span></span>  
  
  
