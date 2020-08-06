---
title: MSSQLSERVER_8710 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8710 (Database Engine error)
ms.assetid: 78b9f9da-5489-4be0-94df-f065d86ed18c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 65fb6b3efb42c282347f560353a2b21edc337859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669426"
---
# <a name="mssqlserver_8710"></a>MSSQLSERVER_8710
    
## <a name="details"></a>Сведения  
  
|||  
|-|-|  
|Название продукта|MSSQLSERVER|  
|Идентификатор события|8710|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|QUERY2_CUBE_ILLEGAL_AGG_FUNC|  
|Текст сообщения|Агрегатные функции, используемые в запросах CUBE, ROLLUP или GROUPING SET, должны обеспечивать возможность слияния подытогов. Чтобы решить эту проблему, удалите агрегатную функцию или напишите запрос UNION ALL с предложениями GROUP BY.|  
  
## <a name="explanation"></a>Объяснение  
 В запросе CUBE, ROLLUP или GROUPING SETS была использована агрегатная функция, не предусматривающая метод для слияния подытогов.  
  
## <a name="user-action"></a>Действие пользователя  
 Чтобы решить эту проблему, удалите агрегатную функцию или напишите запрос UNION ALL с предложениями GROUP BY.  
  
  
