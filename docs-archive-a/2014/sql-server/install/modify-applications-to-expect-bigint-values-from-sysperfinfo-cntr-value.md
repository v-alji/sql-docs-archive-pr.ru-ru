---
title: Изменение приложений для ожидания значений bigint из sysperfinfo. cntr_value | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sysperfinfo
- bigint values [SQL Server]
ms.assetid: b0345303-6e9a-4078-8148-6e1bce207b8c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 108a9b981debc95e182b16847c39a03d4b242088
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749595"
---
# <a name="modify-applications-to-expect-bigint-values-from-sysperfinfocntr_value"></a><span data-ttu-id="4ee50-102">Измените приложения, чтобы они использовали значения bigint из столбца sysperfinfo.cntr_value</span><span class="sxs-lookup"><span data-stu-id="4ee50-102">Modify applications to expect bigint values from sysperfinfo.cntr_value</span></span>
  <span data-ttu-id="4ee50-103">sysperfinfo возвращает `bigint` значение для столбца cntr_value.</span><span class="sxs-lookup"><span data-stu-id="4ee50-103">sysperfinfo returns a `bigint` value for the cntr_value column.</span></span>  
  
## <a name="component"></a><span data-ttu-id="4ee50-104">Компонент</span><span class="sxs-lookup"><span data-stu-id="4ee50-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="4ee50-105">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="4ee50-105">Corrective Action</span></span>  
 <span data-ttu-id="4ee50-106">Внесите изменения в приложения, использующие представление sysperfinfo, чтобы убедиться, что они могут обрабатывать значение типа `bigint` столбца cntr_value.</span><span class="sxs-lookup"><span data-stu-id="4ee50-106">Modify applications that use sysperfinfo to ensure that they can handle the `bigint` values of the cntr_value column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ee50-107">sysperfinfo является представлением совместимости.</span><span class="sxs-lookup"><span data-stu-id="4ee50-107">sysperfinfo is a compatibility view.</span></span> <span data-ttu-id="4ee50-108">Вместо него следует использовать динамическое административное представление sys.dm_os_performance_counters.</span><span class="sxs-lookup"><span data-stu-id="4ee50-108">You should use the sys.dm_os_performance_counter dynamic management view instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ee50-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="4ee50-109">See Also</span></span>  
 <span data-ttu-id="4ee50-110">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="4ee50-110">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="4ee50-111">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="4ee50-111">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
