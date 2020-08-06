---
title: Определяемые пользователем статистические функции CLR | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- aggregate functions [CLR integration]
- custom aggregates [CLR integration]
- calculations [CLR integration]
- user-defined functions [CLR integration]
ms.assetid: bad9b7e8-5967-4afa-8dc8-6d840faf9372
author: rothja
ms.author: jroth
ms.openlocfilehash: d1ef5d07fe082d0eeb2c3484d6e99572d8fc80e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664951"
---
# <a name="clr-user-defined-aggregates"></a><span data-ttu-id="913ec-102">Пользовательские агрегатные функции среды CLR</span><span class="sxs-lookup"><span data-stu-id="913ec-102">CLR User-Defined Aggregates</span></span>
  <span data-ttu-id="913ec-103">Агрегатные функции выполняют вычисление на наборе значений и возвращают одиночное значение.</span><span class="sxs-lookup"><span data-stu-id="913ec-103">Aggregate functions perform a calculation on a set of values and return a single value.</span></span> <span data-ttu-id="913ec-104">Традиционно [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживаются только встроенные агрегатные функции, такие как `SUM` или `MAX` , которые работают с набором входных скалярных значений и создают одно статистическое значение из этого набора.</span><span class="sxs-lookup"><span data-stu-id="913ec-104">Traditionally, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has supported only built-in aggregate functions, such as `SUM` or `MAX`, that operate on a set of input scalar values and generate a single aggregate value from that set.</span></span> <span data-ttu-id="913ec-105">Но теперь интеграция [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] со средой [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework CLR позволяет создавать в управляемом коде пользовательские агрегатные функции и предоставлять доступ к ним из [!INCLUDE[tsql](../../includes/tsql-md.md)] или другого управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="913ec-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integration with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework common language runtime (CLR) now allows developers to create custom aggregate functions in managed code, and to make these functions accessible to [!INCLUDE[tsql](../../includes/tsql-md.md)] or other managed code.</span></span>  
  
 <span data-ttu-id="913ec-106">В следующей таблице приводится список подразделов данного раздела.</span><span class="sxs-lookup"><span data-stu-id="913ec-106">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="913ec-107">Требования для определяемых пользователем статистических функций CLR</span><span class="sxs-lookup"><span data-stu-id="913ec-107">Requirements for CLR User-Defined Aggregates</span></span>](clr-user-defined-aggregates-requirements.md)  
 <span data-ttu-id="913ec-108">Содержит общие сведения о требованиях к реализации определяемых пользователем агрегатных функций среды CLR.</span><span class="sxs-lookup"><span data-stu-id="913ec-108">Provides an overview of the requirements for implementing CLR user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="913ec-109">Вызов определяемых пользователем агрегатных функций CLR</span><span class="sxs-lookup"><span data-stu-id="913ec-109">Invoking CLR User-Defined Aggregate Functions</span></span>](clr-user-defined-aggregate-invoking-functions.md)  
 <span data-ttu-id="913ec-110">Рассказывает о способах вызова определяемой пользователем статистической функции.</span><span class="sxs-lookup"><span data-stu-id="913ec-110">Explains how to invoke user-defined aggregates.</span></span>  
  
  
