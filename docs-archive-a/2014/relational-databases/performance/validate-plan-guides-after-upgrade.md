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
# <a name="validate-plan-guides-after-upgrade"></a><span data-ttu-id="aa956-102">Проверка структур плана после обновления</span><span class="sxs-lookup"><span data-stu-id="aa956-102">Validate Plan Guides After Upgrade</span></span>
  <span data-ttu-id="aa956-103">Рекомендуется переоценить и протестировать определения структур планов при обновлении приложения для работы с новым выпуском [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa956-103">We recommend re-evaluating and testing plan guide definitions when you upgrade your application to a new release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="aa956-104">Требования к настройке производительности и поведение сопоставления структур планов могут меняться.</span><span class="sxs-lookup"><span data-stu-id="aa956-104">Performance tuning requirements and plan guide matching behavior may change.</span></span> <span data-ttu-id="aa956-105">Хотя недопустимая структура плана не приведет к сбою при выполнении запроса, план будет скомпилирован без использования структуры, что не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="aa956-105">Although an invalid plan guide will not cause a query to fail, the plan is compiled without using the plan guide and may not be the best choice.</span></span> <span data-ttu-id="aa956-106">После обновления базы данных до версии [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]рекомендуется выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="aa956-106">After upgrading a database to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], we recommend that you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="aa956-107">Проверьте существующие структуры планов с помощью функции [sys.fn_validate_plan_guide](/sql/relational-databases/system-functions/sys-fn-validate-plan-guide-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="aa956-107">Validate existing plan guides by using the [sys.fn_validate_plan_guide](/sql/relational-databases/system-functions/sys-fn-validate-plan-guide-transact-sql) function.</span></span>  
  
-   <span data-ttu-id="aa956-108">Используйте расширенные события, чтобы проверить наличие планов без структуры за определенное время с помощью события [Plan Guide Unsuccessful](../event-classes/plan-guide-unsuccessful-event-class.md) .</span><span class="sxs-lookup"><span data-stu-id="aa956-108">Use extended events to monitor for misguided plans for some period of time by using the [Plan Guide Unsuccessful](../event-classes/plan-guide-unsuccessful-event-class.md) event.</span></span>  
  
  
