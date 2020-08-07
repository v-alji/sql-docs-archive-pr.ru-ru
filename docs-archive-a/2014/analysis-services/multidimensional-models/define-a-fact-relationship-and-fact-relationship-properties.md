---
title: Определение связей фактов и свойств связей фактов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- fact dimensions [Analysis Services]
ms.assetid: d8e41724-da77-4ac1-bc42-956b5d91ea5d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 15f67a4bdf699bbc6443fc76ce54bcfb35831827
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730970"
---
# <a name="define-a-fact-relationship-and-fact-relationship-properties"></a><span data-ttu-id="98f39-102">Определение связей фактов и свойств связей фактов</span><span class="sxs-lookup"><span data-stu-id="98f39-102">Define a Fact Relationship and Fact Relationship Properties</span></span>
  <span data-ttu-id="98f39-103">При определении нового измерения куба или новой группы мер службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] попытаются определить, существует ли связь измерений фактов, и установить настройку использования измерения, равной `Fact`.</span><span class="sxs-lookup"><span data-stu-id="98f39-103">When you define a new cube dimension or a new measure group, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will try to detect if a fact dimension relationship exists and then set the dimension usage setting to `Fact`.</span></span> <span data-ttu-id="98f39-104">Связь измерений фактов можно просмотреть или отредактировать на вкладке **Использование измерений** конструктора кубов.</span><span class="sxs-lookup"><span data-stu-id="98f39-104">You can view or edit a fact dimension relationship on the **Dimension Usage** tab of Cube Designer.</span></span> <span data-ttu-id="98f39-105">Связь фактов между измерением и группой мер имеет следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="98f39-105">The fact relationship between a dimension and a measure group has the following constraints:</span></span>  
  
-   <span data-ttu-id="98f39-106">Измерение куба может иметь только одну связь фактов с конкретной группой мер.</span><span class="sxs-lookup"><span data-stu-id="98f39-106">A cube dimension can have only one fact relationship to a particular measure group.</span></span>  
  
-   <span data-ttu-id="98f39-107">Измерение куба может иметь отдельные связи фактов с несколькими группами мер.</span><span class="sxs-lookup"><span data-stu-id="98f39-107">A cube dimension can have separate fact relationships to multiple measure groups.</span></span>  
  
-   <span data-ttu-id="98f39-108">Атрибут гранулярности для связи должен быть ключевым атрибутом (таким как номер транзакции) для измерения.</span><span class="sxs-lookup"><span data-stu-id="98f39-108">The granularity attribute for the relationship must be the key attribute (such as Transaction Number) for the dimension.</span></span> <span data-ttu-id="98f39-109">Это создает связь «один к одному» между измерением и фактами в таблице фактов.</span><span class="sxs-lookup"><span data-stu-id="98f39-109">This creates a one-to-one relationship between the dimension and facts in the fact table.</span></span>  
  
  
