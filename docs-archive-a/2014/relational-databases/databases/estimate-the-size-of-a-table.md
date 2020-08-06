---
title: Оценка размера таблицы | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- pages [SQL Server], space
- space [SQL Server], tables
- row size [SQL Server]
- size [SQL Server], tables
- column size [SQL Server]
- predicting table size [SQL Server]
- table size [SQL Server]
- estimating table size
- clustered indexes, table size
- disk space [SQL Server], tables
- space allocation [SQL Server], table size
- designing databases [SQL Server], estimating size
- reserved free rows per page [SQL Server]
- calculating table size
ms.assetid: 15c17c92-616f-402e-894b-907a296efe5f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a16d439d3b2bc59479866b7bb36295ec4fc8950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736374"
---
# <a name="estimate-the-size-of-a-table"></a>Оценка размера таблицы
  Оценить пространство, необходимое для хранения данных в таблице, можно с помощью следующих шагов:  
  
1.  Рассчитайте пространство, необходимое для кучи или кластеризованного индекса, с помощью инструкций в статьях [Оценка размера кучи](estimate-the-size-of-a-heap.md) и [Оценка размера кластеризованного индекса](estimate-the-size-of-a-clustered-index.md).  
  
2.  Вычислите необходимое пространство для каждого некластеризованного индекса с помощью инструкций в статье [Оценка размера некластеризованного индекса](estimate-the-size-of-a-nonclustered-index.md).  
  
3.  Сложите значения, рассчитанные на шаге 1 и 2.  
  
## <a name="see-also"></a>См. также:  
 [Оценка размера базы данных](estimate-the-size-of-a-database.md)   
 [Оценка размера кучи](estimate-the-size-of-a-heap.md)   
 [Оценка размера кластеризованного индекса](estimate-the-size-of-a-clustered-index.md)   
 [Оценка размера некластеризованного индекса](estimate-the-size-of-a-nonclustered-index.md)  
  
  
