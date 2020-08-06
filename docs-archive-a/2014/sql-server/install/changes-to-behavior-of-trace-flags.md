---
title: Изменения в поведении флагов трассировки | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- trace flags [SQL Server], behavior changes
ms.assetid: d739df96-2659-4383-8e10-194657632526
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 11d71e8401f6b870aaeb3f64f4145b509e3a3fe0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659228"
---
# <a name="changes-to-behavior-of-trace-flags"></a><span data-ttu-id="2201e-102">Изменения в поведении флагов трассировки</span><span class="sxs-lookup"><span data-stu-id="2201e-102">Changes to behavior of trace flags</span></span>
  <span data-ttu-id="2201e-103">Глобальные флаги трассировки, установленные сеансом, немедленно учитываются в других сеансах.</span><span class="sxs-lookup"><span data-stu-id="2201e-103">Global trace flags set by a session take effect in other sessions immediately.</span></span> <span data-ttu-id="2201e-104">Некоторые флаги трассировки [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] отсутствуют в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2201e-104">Some trace flags from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] do not exist in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="2201e-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="2201e-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="2201e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="2201e-106">Description</span></span>  
 <span data-ttu-id="2201e-107">Рекомендуется отключить все флаги трассировки перед началом обновления.</span><span class="sxs-lookup"><span data-stu-id="2201e-107">We recommend that you disable all trace flags before you upgrade.</span></span> <span data-ttu-id="2201e-108">Флаги трассировки, которые изменяют режимы доступности базы данных или восстановления, могут препятствовать [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] успешному обновлению экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2201e-108">Trace flags that modify the database availability or recovery modes might prevent the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] from successfully upgrading your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2201e-109">Включить эти флаги трассировки можно будет после проверки того, что они необходимы и по-прежнему допустимы в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2201e-109">You can enable the trace flags after you verify that the trace flags are required and are still valid in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="2201e-110">Если необходимо повторно включить флаги трассировки, то нужно выполнить дополнительную проверку экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2201e-110">If you must re-enable trace flags, you should perform additional tests on your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="2201e-111">поддерживает флаги трассировки на глобальном уровне и уровне сеанса.</span><span class="sxs-lookup"><span data-stu-id="2201e-111">supports global and session level trace flags.</span></span> <span data-ttu-id="2201e-112">В [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] флаги трассировки могут быть объявлены как локальные либо глобальные при помощи дополнительного аргумента (-1) команды DBCC TRACEON.</span><span class="sxs-lookup"><span data-stu-id="2201e-112">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], trace flags can be specified as either local or global by using an additional argument (-1) in the DBCC TRACEON command.</span></span> <span data-ttu-id="2201e-113">Если этот аргумент не указан, по умолчанию флаги объявляются как локальные.</span><span class="sxs-lookup"><span data-stu-id="2201e-113">If this argument is not specified, the default value is local.</span></span>  
  
 <span data-ttu-id="2201e-114">Кроме того, в [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] флаг трассировки, установленный в сеансе А, не будет автоматически воздействовать на уже существующий сеанс Б. Вместо этого данный флаг трассировки вступит в силу только после первой установки любого флага трассировки в сеансе Б. Такое поведение является недетерминированным в [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] и детерминированным в [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и более поздних версиях, в которых глобальные флаги трассировки, установленные в сеансе А, немедленно устанавливаются во всех параллельных сеансах.</span><span class="sxs-lookup"><span data-stu-id="2201e-114">Also, in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], a trace flag set in session A does not automatically take effect in an already existing session B. Instead, this trace flag takes effect only after the first time any trace flag is set in session B. This behavior is nondeterministic in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] and is deterministic in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions, where global trace flags set in session A are set immediately in other concurrent sessions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2201e-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="2201e-115">See Also</span></span>  
 <span data-ttu-id="2201e-116">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="2201e-116">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="2201e-117">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="2201e-117">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
