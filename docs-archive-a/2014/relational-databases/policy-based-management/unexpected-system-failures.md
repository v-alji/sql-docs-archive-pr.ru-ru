---
title: Непредвиденные сбои системы | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 1679bf9e-a2ef-4f90-8907-a002f7341a7d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b791ba0e3f709288a4e2c5b6add4e74e15d56dee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657702"
---
# <a name="unexpected-system-failures"></a><span data-ttu-id="fe417-102">Непредвиденные сбои системы</span><span class="sxs-lookup"><span data-stu-id="fe417-102">Unexpected System Failures</span></span>
  <span data-ttu-id="fe417-103">Это правило проверяет журнал событий компьютера на событие SYSTEM Event 6008.</span><span class="sxs-lookup"><span data-stu-id="fe417-103">This rule checks for SYSTEM Event 6008 in the computer event log.</span></span> <span data-ttu-id="fe417-104">Это событие указывает на непредвиденное завершение работы системы.</span><span class="sxs-lookup"><span data-stu-id="fe417-104">This event indicates an unexpected system shutdown.</span></span> <span data-ttu-id="fe417-105">Система может быть нестабильна и тем самым не обеспечивать устойчивость и целостность, необходимые для размещения экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe417-105">The system might be unstable and might not provide the stability and integrity that is required to host an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="fe417-106">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="fe417-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="fe417-107">Немедленно устраните причину непредвиденных перезагрузок сервера или переместите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на другой компьютер.</span><span class="sxs-lookup"><span data-stu-id="fe417-107">Immediately address the cause of the unexpected server restarts, or move the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to another computer.</span></span>  
  
  
