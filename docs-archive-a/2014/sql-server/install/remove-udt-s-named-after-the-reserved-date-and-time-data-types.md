---
title: Удаление определяемого пользователем типа&#39;s с именем, зарезервированным типами данных даты и времени | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- time data type [SQL Server], UDTs
- date data type [SQL Server], UDTs
ms.assetid: 48f109af-b1d1-4f03-a7e3-8a0b05ed94e8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 827f060b309a7a620fd448554b074f45d78d3cb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666363"
---
# <a name="remove-udt39s-named-after-the-reserved-date-and-time-data-types"></a><span data-ttu-id="e6517-102">Удалить определяемый пользователем тип&#39;s с именем, зарезервированным типом данных даты и времени</span><span class="sxs-lookup"><span data-stu-id="e6517-102">Remove UDT&#39;s named after the reserved DATE and TIME data types</span></span>
  <span data-ttu-id="e6517-103">Помощник по обновлению обнаружил определяемый пользователем тип, имя которого совпадает с именем, зарезервированным для типа данных `date` или `time`.</span><span class="sxs-lookup"><span data-stu-id="e6517-103">Upgrade Advisor detected a user-defined type (UDT) that is named after a term reserved for either the `date` or the `time` data types.</span></span>  
  
## <a name="component"></a><span data-ttu-id="e6517-104">Компонент</span><span class="sxs-lookup"><span data-stu-id="e6517-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="e6517-105">Описание</span><span class="sxs-lookup"><span data-stu-id="e6517-105">Description</span></span>  
 <span data-ttu-id="e6517-106">Имена терминов, используемых для типов данных, не должны использоваться в качестве имен определяемых пользователем типов среды CLR или их псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="e6517-106">The terms used for data types should not be used as names for either common language runtime (CLR) or alias UDTs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="e6517-107">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="e6517-107">Corrective Action</span></span>  
 <span data-ttu-id="e6517-108">Удалите определяемый пользователем тип и создайте его повторно с именем, отличным от зарезервированного.</span><span class="sxs-lookup"><span data-stu-id="e6517-108">Remove the UDT that is named after the data type and recreate the UDT with an unreserved name.</span></span>  
  
  
