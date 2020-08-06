---
title: Проверка структур плана после обновления | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- plan guides [SQL Server], validating after upgrade
ms.assetid: a55ebd88-6f58-454d-b1c4-991b88add522
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 18cc0f93ddec46025f659bcb9489bfff3ca846ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732582"
---
# <a name="validate-plan-guides-after-upgrade"></a>Проверка структур плана после обновления
  Рекомендуется переоценить и протестировать определения структур планов при обновлении приложения для работы с новым выпуском [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Требования к настройке производительности и поведение сопоставления структур планов могут меняться. Хотя недопустимая структура плана не приведет к сбою при выполнении запроса, план будет скомпилирован без использования структуры, что не рекомендуется. После обновления базы данных до версии [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]рекомендуется выполнить следующие действия.  
  
-   Проверьте существующие структуры планов с помощью функции [sys.fn_validate_plan_guide](/sql/relational-databases/system-functions/sys-fn-validate-plan-guide-transact-sql) .  
  
-   Используйте расширенные события, чтобы проверить наличие планов без структуры за определенное время с помощью события [Plan Guide Unsuccessful](../event-classes/plan-guide-unsuccessful-event-class.md) .  
  
  
