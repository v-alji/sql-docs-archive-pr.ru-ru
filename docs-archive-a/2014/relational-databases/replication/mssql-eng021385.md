---
title: MSSQL_ENG021385 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021385 error
ms.assetid: a2c0444f-d97b-4760-8905-3574791c2e26
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b73d3216f07cb44d750a37149634258648f1bd48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730497"
---
# <a name="mssql_eng021385"></a>MSSQL_ENG021385
    
## <a name="message-details"></a>Сведения о сообщении  
  
|||  
|-|-|  
|Название продукта|SQL Server|  
|Идентификатор события|21385|  
|Источник события|MSSQLSERVER|  
|Компонент|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|Символическое имя||  
|Текст сообщения|Не удалось создать моментальный снимок для публикации "%s". Возможно, из-за изменений в схеме или из-за статей, добавленных во время создания снимка.|  
  
## <a name="explanation"></a>Объяснение  
 Данная ошибка возникает, если агент моментальных снимков начинает работу во время выполняющихся изменений в базе данных публикации, включающих добавление или удаление статей и внесение изменений схемы в опубликованные объекты.  
  
## <a name="user-action"></a>Действие пользователя  
 После завершения изменений в базе данных публикации перезапустите агент моментальных снимков. Дополнительные сведения см. в статьях и [Запуск и остановка агента репликации (среда SQL Server Management Studio)](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) и [Основные понятия исполняемых файлов агента репликации](concepts/replication-agent-executables-concepts.md).  
  
## <a name="see-also"></a>См. также:  
 [Справочник по ошибкам и событиям (репликация)](errors-and-events-reference-replication.md)  
  
  
