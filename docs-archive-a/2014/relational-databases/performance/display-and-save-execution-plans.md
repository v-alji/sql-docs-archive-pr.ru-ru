---
title: Отображение и сохранение планов выполнения | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Showplan results
- execution plans [SQL Server]
- queries [SQL Server], tuning
- execution plans [SQL Server], how-to topics
- SQL Server Management Studio [SQL Server], execution plans
- tuning queries [SQL Server]
ms.assetid: bcd6f094-c613-4835-ae19-4caaadb4bb17
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e236ed2a298bc8fc9a829948a864f6f5c27a2ba2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730550"
---
# <a name="display-and-save-execution-plans"></a><span data-ttu-id="1cd56-102">Отображение и сохранение планов выполнения</span><span class="sxs-lookup"><span data-stu-id="1cd56-102">Display and Save Execution Plans</span></span>
  <span data-ttu-id="1cd56-103">В этом разделе объясняется, как отображать планы выполнения и как сохранять их в файл формата XML в среде Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cd56-103">This section explains how to display execution plans and how to save execution plans to a file in XML format by using Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="1cd56-104">Планы выполнения графически отображают методы получения данных, выбранные оптимизатором запросов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1cd56-104">Execution plans graphically display the data retrieval methods chosen by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] query optimizer.</span></span> <span data-ttu-id="1cd56-105">Планы выполнения представляют стоимость выполнения в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] определенных инструкций и запросов в виде значков, а не таблиц, создаваемых инструкциями SET SHOWPLAN_ALL или SET SHOWPLAN_TEXT.</span><span class="sxs-lookup"><span data-stu-id="1cd56-105">Execution plans represent the execution cost of specific statements and queries in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using icons rather than the tabular representation produced by the SET SHOWPLAN_ALL or SET SHOWPLAN_TEXT statements.</span></span> <span data-ttu-id="1cd56-106">Графический подход очень полезен для понимания характеристик производительности запроса.</span><span class="sxs-lookup"><span data-stu-id="1cd56-106">This graphical approach is very useful for understanding the performance characteristics of a query.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1cd56-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="1cd56-107">In This Section</span></span>  
  
-   [<span data-ttu-id="1cd56-108">Отображение предполагаемого плана выполнения</span><span class="sxs-lookup"><span data-stu-id="1cd56-108">Display the Estimated Execution Plan</span></span>](display-the-estimated-execution-plan.md)  
  
-   [<span data-ttu-id="1cd56-109">Отображение действительного плана выполнения</span><span class="sxs-lookup"><span data-stu-id="1cd56-109">Display an Actual Execution Plan</span></span>](display-an-actual-execution-plan.md)  
  
-   [<span data-ttu-id="1cd56-110">Сохранение плана выполнения в формате XML</span><span class="sxs-lookup"><span data-stu-id="1cd56-110">Save an Execution Plan in XML Format</span></span>](save-an-execution-plan-in-xml-format.md)  
  
  
