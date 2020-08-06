---
title: Архитектура интеграции со средой CLR | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], architecture
- architecture [CLR integration]
ms.assetid: 05e4b872-3d21-46de-b4d5-739b5f2a0cf9
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: bb32e2c7f5eb2079146a2fee64af2e2dbc1d3356
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657260"
---
# <a name="architecture-of-clr-integration"></a><span data-ttu-id="c1b65-102">Архитектура интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="c1b65-102">Architecture of CLR Integration</span></span>
  <span data-ttu-id="c1b65-103">Интеграция [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] со средой CLR платформы .NET Framework позволяет программистам работать с базами данных, используя такие языки, как Visual C#, Visual Basic .NET, Visual C++.</span><span class="sxs-lookup"><span data-stu-id="c1b65-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integration with the .NET Framework common language runtime (CLR) enables database programmers to use languages such as Visual C#, Visual Basic .NET, and Visual C++.</span></span> <span data-ttu-id="c1b65-104">С помощью этих языков программисты могут создавать различные объекты бизнес-логики, например: функции, хранимые процедуры, триггеры, типы данных и агрегаты.</span><span class="sxs-lookup"><span data-stu-id="c1b65-104">Functions, stored procedures, triggers, data types, and aggregates are among the kinds of business logic that programmers can write with these languages.</span></span>  
  
 <span data-ttu-id="c1b65-105">В данном разделе описывается архитектура интеграции со средой CLR внутри [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], а также рассказывается, каким образом эта архитектура создает безопасную, масштабируемую, защищенную и эффективную среду для выполнения пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="c1b65-105">This section describes the architecture of CLR integration inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and how this architecture provides a safe, scalable, secure, and efficient environment to run user code.</span></span>  
  
 <span data-ttu-id="c1b65-106">В следующей таблице приводится список подразделов данного раздела.</span><span class="sxs-lookup"><span data-stu-id="c1b65-106">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="c1b65-107">Среда размещения CLR</span><span class="sxs-lookup"><span data-stu-id="c1b65-107">CLR Hosted Environment</span></span>](../../relational-databases/clr-integration/clr-integration-architecture-clr-hosted-environment.md)  
 <span data-ttu-id="c1b65-108">Обсуждаются цели, преследуемые при создании архитектуры, различные механизмы и преимущества интеграции со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="c1b65-108">Discusses architectural design goals, mechanisms, and benefits of CLR integration.</span></span>  
  
 [<span data-ttu-id="c1b65-109">Производительность интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="c1b65-109">Performance of CLR Integration</span></span>](../../relational-databases/clr-integration/clr-integration-architecture-performance.md)  
 <span data-ttu-id="c1b65-110">Рассказывает о различных аспектах, влияющих на производительность архитектуры интеграции со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="c1b65-110">Covers performance considerations of the CLR integration architecture.</span></span>  
  
  
