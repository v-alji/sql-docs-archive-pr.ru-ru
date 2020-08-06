---
title: MSSQLSERVER_8689 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8689 (Database Engine error)
ms.assetid: 99467a32-6576-4272-a076-b16c06933f2a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2cdca0a3cd9ce47ccb39ebeaf8fd1cd260aafbd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730689"
---
# <a name="mssqlserver_8689"></a>MSSQLSERVER_8689
    
## <a name="details"></a>Сведения  
  
|||  
|-|-|  
|Название продукта|SQL Server|  
|Идентификатор события|8689|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|USEPLAN_ERR_NO_DB|  
|Текст сообщения|База данных "%.*ls", заданная в указании USE PLAN, не существует. Укажите существующую базу данных.|  
  
## <a name="explanation"></a>Объяснение  
 База данных, которая задана в указании USE PLAN, не существует.  
  
## <a name="user-action"></a>Действие пользователя  
 Убедитесь в том, что существуют все базы данных, которые заданы в указании USE PLAN.  
  
## <a name="see-also"></a>См. также:  
 [Указания запросов (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query)   
 [Руководства планов](../performance/plan-guides.md)  
  
  
