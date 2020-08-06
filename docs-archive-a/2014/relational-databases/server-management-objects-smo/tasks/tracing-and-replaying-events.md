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
# <a name="tracing-and-replaying-events"></a>Трассировка и воспроизведение событий
  В SMO объекты `Trace` и `Replay` в пространстве имен <xref:Microsoft.SqlServer.Management.Trace> обеспечивают программный доступ к функциональности приложения [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)], которая используется для наблюдения за экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] или служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]. Приложение позволяет собирать и сохранять данные о каждом событии в файле или в таблице для последующего анализа. Например, с помощью приложения можно наблюдать за рабочей средой, чтобы определить, какие процедуры сказываются на производительности из-за того, что выполняются слишком медленно.  
  
 Объекты `Trace` и `Replay` предоставляют набор объектов, которые можно использовать для создания трассировок экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Эти объекты можно использовать из пользовательских приложений для создания вручную трассировок для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] или служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]. Кроме того, объекты `Trace` SMO можно использовать для чтения файлов трассировок SQL и таблиц, которые были созданы при наблюдении за [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], службами [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] и операциями с журналом DTS.  
  
 Объекты `Trace` SMO позволяют выполнять следующие функции:  
  
-   создать трассировку;  
  
-   назначить фильтры для трассировки;  
  
-   назначить отслеживаемые события;  
  
-   остановить и запустить трассировку;  
  
-   прочитать файлы трассировки и таблицы трассировки;  
  
-   получить сведения о событиях трассировки;  
  
-   получить сведения о фильтрах трассировки;  
  
-   программно управлять данными трассировки;  
  
-   записать файлы и таблицы трассировки;  
  
-   воспроизвести файлы и таблицы трассировки.  
  
 Данные трассировки из `Trace` `Replay` объектов и могут использоваться приложением SMO или могут быть проверены вручную с помощью [SQL Server Profiler](../../../tools/sql-server-profiler/sql-server-profiler.md). Данные трассировки также совместимы с хранимыми процедурами [SQL Trace](../../sql-trace/sql-trace.md) , которые также обеспечивают возможности трассировки.  
  
 Объекты трассировки SMO находятся в пространстве имен <xref:Microsoft.SqlServer.Management.Trace>, для использования которого необходима ссылка на файл Microsoft.SQLServer.ConnectionInfo.dll.  
  
 Объекты `Trace` и `Replay` требуют наличия объекта <xref:Microsoft.SqlServer.Management.Common.ServerConnection><xref:Microsoft.SqlServer.Management.Smo.Server.%23ctor%2A> для установления соединения с экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Объект <xref:Microsoft.SqlServer.Management.Common.ServerConnection> находится в пространстве имен <xref:Microsoft.SqlServer.Management.Common>, для которого необходима ссылка на файл Microsoft.SQLServer.ConnectionInfo.dll.  
  
> [!NOTE]  
>  Объекты `Trace` и `Replay` не поддерживаются в 64-разрядной версии платформы.  
  
  
