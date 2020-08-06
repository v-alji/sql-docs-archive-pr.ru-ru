---
title: Приостановка трассировки (SQL Server Profiler) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- pausing traces
- temporarily stopping traces
- traces [SQL Server], pausing
- stopping traces
ms.assetid: 432b9b0c-b5e7-47f3-a71b-310fb3bf2445
author: stevestein
ms.author: sstein
ms.openlocfilehash: cdc9dbbd01099b1d33787a72b0bd59b65cea722e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727569"
---
# <a name="pause-a-trace-sql-server-profiler"></a>приостановить трассировки (приложение SQL Server Profiler)
  При приостановке трассировки дальнейший захват событий прекращается до ее возобновления.  
  
 Приостановка трассировки приводит к тому, что сбор данных о событиях прекращается до ее перезапуска. Перезапуск трассировки позволяет возобновить сбор данных. При перезапуске трассировки уже зарегистрированные данные не утрачиваются. После перезапуска трассировки сбор данных возобновляется, начиная с текущей точки. Приостановив трассировку, можно изменить ее имя, события, столбцы и фильтры. Однако изменить места назначения, в которые отправляются данные трассировки, и соединение с сервером нельзя.  
  
### <a name="to-pause-a-trace"></a>Приостановка трассировки  
  
1.  Выберите окно, содержащее выполняющуюся трассировку.  
  
2.  В меню **Файл** выберите пункт **Приостановить трассировку**.  
  
## <a name="see-also"></a>См. также:  
 [Приложение SQL Server Profiler](sql-server-profiler.md)  
  
  
