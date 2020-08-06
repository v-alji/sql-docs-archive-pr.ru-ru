---
title: Задание параметра максимальной степени параллелизма для оптимальной производительности | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: ec908006-67ae-4674-9a61-25ea741d6197
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3043a656cbe1ac1ec40f0d0a67b6eac057005af4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749747"
---
# <a name="set-the-max-degree-of-parallelism-option-for-optimal-performance"></a><span data-ttu-id="c1899-102">Задание параметра максимальной степени параллелизма для оптимальной производительности</span><span class="sxs-lookup"><span data-stu-id="c1899-102">Set the Max Degree of Parallelism Option for Optimal Performance</span></span>
  <span data-ttu-id="c1899-103">Это правило определяет, является ли значение параметра максимальной степени параллелизма (MAXDOP) больше 8.</span><span class="sxs-lookup"><span data-stu-id="c1899-103">This rule determines whether the max degree of parallelism (MAXDOP) option for a value greater than 8.</span></span> <span data-ttu-id="c1899-104">Установка большего значения часто приводит к неэффективному расходованию ресурсов и снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="c1899-104">Setting this option to a larger value often causes unwanted resource consumption and performance degradation.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="c1899-105">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="c1899-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="c1899-106">Установите значение параметра максимальной степени параллелизма равным 8 или меньше с помощью хранимой процедуры sp_configure.</span><span class="sxs-lookup"><span data-stu-id="c1899-106">Set the max degree of parallelism option to 8 or less by using sp_configure.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="c1899-107">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="c1899-107">For More Information</span></span>  
 [<span data-ttu-id="c1899-108">Статья 329204 базы знаний Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c1899-108">Microsoft Knowledge Base article 329204</span></span>](https://go.microsoft.com/fwlink/?linkid=117786)  
  
 [<span data-ttu-id="c1899-109">Настройка параметра конфигурации сервера max degree of parallelism</span><span class="sxs-lookup"><span data-stu-id="c1899-109">Configure the max degree of parallelism Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md)  
  
 [<span data-ttu-id="c1899-110">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c1899-110">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
