---
title: MSSQLSERVER_2574 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2574 (Database Engine error)
ms.assetid: efba507a-b5ad-4f1d-b0c8-f73b663a0562
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44fd103f8c651ca968ae997ae9c3d544b41cbf3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729510"
---
# <a name="mssqlserver_2574"></a>MSSQLSERVER_2574
    
## <a name="details"></a>Сведения  
  
|||  
|-|-|  
|Название продукта|SQL Server|  
|Идентификатор события|2574|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|DBCC_EMPTY_INDEX_TREE_LEVEL_PAGE|  
|Текст сообщения|Ошибка таблицы: страница P_ID пуста в объекте с идентификатором O_ID, идентификатором индекса I_ID, идентификатором секции PN_ID, идентификатором единицы распределения A_ID (тип TYPE). Это недопустимо на LEVEL уровне сбалансированного дерева.|  
  
## <a name="explanation"></a>Объяснение  
 Страница сбалансированного дерева над конечным уровнем указанного индекса пуста, следовательно, не содержит строк. В [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] такое поведение возможно для страниц конечного уровня, но невозможно на уровнях дерева.  
  
## <a name="user-action"></a>Действие пользователя  
  
### <a name="look-for-hardware-failure"></a>Поиск сбоев оборудования  
 Выполните диагностику оборудования и исправьте все найденные проблемы. Кроме того, просмотрите журнал системы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows и журнал приложений, а также журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], чтобы определить, была ли ошибка вызвана сбоем оборудования. Исправьте все неполадки оборудования, обнаруженные в журналах.  
  
 Если постоянно возникают проблемы с повреждением данных, попробуйте изменить некоторые компоненты оборудования, чтобы локализовать проблему. Убедитесь, что в системе не включено кэширование записи для контроллера дисков. Если есть подозрение, что неполадки вызваны кэшированием записи, обратитесь к поставщику оборудования.  
  
 В конце концов можно попробовать сменить оборудование. Это может включать форматирование дисков и переустановку операционной системы.  
  
### <a name="restore-from-backup"></a>Восстановление из резервной копии  
 Если неполадка не связана с оборудованием и есть безошибочная резервная копия, восстановите базу данных из этой копии.  
  
### <a name="run-dbcc-checkdb"></a>Запуск DBCC CHECKDB  
 Если безошибочной резервной копии нет, выполните инструкцию DBCC CHECKDB без предложения REPAIR, чтобы определить степень повреждения. Инструкция DBCC CHECKDB выдаст рекомендацию по тому, какое предложение REPAIR следует использовать. После этого выполните инструкцию DBCC CHECKDB с соответствующим предложением REPAIR, чтобы устранить повреждение.  
  
> [!CAUTION]  
>  Если достоверно неизвестно, к каким последствиям приведет выполнение инструкции DBCC CHECKDB с выбранным предложением REPAIR, перед выполнением этой инструкции обратитесь к вашему основному поставщику услуг технической поддержки.  
  
 Если в результате выполнения инструкции DBCC CHECKDB с одним из предложений REPAIR неполадка устранена не была, обратитесь к вашему основному поставщику услуг технической поддержки.  
  
### <a name="results-of-running-repair-options"></a>Результаты выполнения инструкции REPAIR  
 Инструкция DBCC перестроит индекс.  
  
  