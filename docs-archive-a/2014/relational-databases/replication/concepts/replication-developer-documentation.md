---
title: Пошаговое руководством для разработчиков&#39;(репликация) | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
helpviewer_keywords:
- developer's guide [SQL Server replication]
- programming [SQL Server replication]
- replication [SQL Server], development
ms.assetid: 7ee134ae-1cab-4a35-8017-8ac6d8fc64b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d9651aec1f02d19ea3494abf242f75049a4f33f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736242"
---
# <a name="developer39s-guide-replication"></a>Руководством разработчика&#39;(репликация)
  Возможность настраивать, сопровождать и осуществлять программным путем наблюдение за топологией репликации позволяет упростить повторное выполнение задачи репликации и повысить удобство работы пользователей с приложениями на основе репликации. Благодаря программной реализации средств репликации конечные пользователи получают возможность применять настраиваемые функциональные средства репликации, не будучи вынужденными изучать хранимые процедуры репликации и знакомиться с исполняемыми файлами агентов репликации или прибегать к использованию пользовательского интерфейса репликации, реализованного в среде [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].  
  
 Ниже описаны ситуации, в которых можно было бы усовершенствовать приложения путем предоставления программного доступа к службам репликации.  
  
-   Добавление к существующему приложению конечного пользователя таких функциональных средств репликации, как синхронизация подписки по запросу, осуществляемая после нажатия кнопки пользователем.   
-   Создание пользовательского веб-интерфейса для дистанционного управления репликацией.    
-   Создание настраиваемого пользовательского интерфейса, который предоставляет доступ только к определенному подмножеству функциональных средств администрирования и может использоваться для дистанционного управления несколькими топологиями репликации из одного места или сочетает в себе функциональные возможности администрирования и синхронизации.    
-   Усовершенствование одного из существующих инструментальных средств наблюдения путем добавления возможности наблюдения за состоянием публикации, подписки или распространителя.    
-   Создание пользовательского приложения для управления или синхронизации подписок на издателе Oracle.    
-   Написание настраиваемых бизнес-правил, выполняемых при синхронизации подписки на публикацию слиянием.    
-   Формирование скриптов [!INCLUDE[tsql](../../../includes/tsql-md.md)], которые могут выполняться повторно при настройке новых подписчиков.  
  
 В [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] предусмотрена возможность управлять программным путем агентами репликации, а также осуществлять программное управление и текущее наблюдение за топологией репликации. Дополнительные сведения о программировании репликации см. в статье [Основные понятия программирования репликации](replication-programming-concepts.md).  
  
## <a name="in-this-section"></a>в этом разделе  
 [Основные понятия программирования репликации](replication-programming-concepts.md)  
 Описывает шаги планирования, связанные с разработкой приложения, в котором используется репликация.  
  
 [Replication System Stored Procedures Concepts](replication-system-stored-procedures-concepts.md)  
 Описывает способы использования системных хранимых процедур для предоставления программного доступа в топологии репликации.  
  
 [Основные понятия объектов RMO](replication-management-objects-concepts.md)  
 Содержит основные понятия, связанные с использованием объектов RMO. Это — сборка управляемого кода, которая инкапсулирует функциональные возможности репликации для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
 [Replication Agent Executables Concepts](replication-agent-executables-concepts.md)  
 Описывает использование исполняемых файлов агента репликации.  

  
  