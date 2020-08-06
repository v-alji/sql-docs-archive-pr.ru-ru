---
title: MSSQLSERVER_1101 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1101 (Database Engine error)
ms.assetid: d63b67d5-59f5-4f77-904e-5ba67f2dd850
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 631b0ab1466815cbacfd71b4f9fd714fabd0f7b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667186"
---
# <a name="mssqlserver_1101"></a>MSSQLSERVER_1101
    
## <a name="details"></a>Сведения  
  
|||  
|-|-|  
|Название продукта|SQL Server|  
|Идентификатор события|1101|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|NOALLOCPG|  
|Текст сообщения|Не удалось выделить новую страницу для базы данных "%.*ls" вследствие нехватки места на диске в файловой группе "%.\*ls". Предоставьте необходимое место на диске, удалив объекты в файловой группе, добавив дополнительные файлы в файловую группу или указав параметр автоматического увеличения размера для существующих файлов в файловой группе.|  
  
## <a name="explanation"></a>Объяснение  
 Нет свободного места на диске в файловой группе.  
  
## <a name="user-action"></a>Действие пользователя  
 Место в файловой группе можно освободить следующим образом.  
  
-   Включить автоматическое расширение.  
  
-   Добавить файлы в файловую группу.  
  
-   Освободить место на диске, удалив ненужные индексы или таблицы из файловой группы.  
  
  
