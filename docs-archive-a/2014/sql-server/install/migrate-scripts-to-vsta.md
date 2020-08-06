---
title: Перенос скриптов в VSTA | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SSIS Script task, converting scripts
- Script component [Integration Services], converting scripts
- Script task [Integration Services], converting scripts
- SSIS Script component, converting scripts
ms.assetid: d685098b-86a1-46bf-939a-63d56951e009
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: afbc19c35f99a5abc5a6ebd92024e42baa6a9237
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749599"
---
# <a name="migrate-scripts-to-vsta"></a><span data-ttu-id="0fb45-102">Миграция скриптов в VSTA</span><span class="sxs-lookup"><span data-stu-id="0fb45-102">Migrate Scripts to VSTA</span></span>
  <span data-ttu-id="0fb45-103">При обновлении [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] пакетов до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] переносит скрипты в любой задаче или компонентах скриптов в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] средства для приложений (VSTA).</span><span class="sxs-lookup"><span data-stu-id="0fb45-103">When you upgrade [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] packages to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] migrates the scripts in any Script tasks or Script components to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span> <span data-ttu-id="0fb45-104">VSTA — среда выполнения сценариев, используемая службами [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0fb45-104">VSTA is the scripting environment that [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] uses.</span></span> <span data-ttu-id="0fb45-105">В [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] среде Среда скриптов для [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] предназначена [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] для приложений (VSA).</span><span class="sxs-lookup"><span data-stu-id="0fb45-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], the scripting environment for [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] for Applications (VSA).</span></span>  
  
 <span data-ttu-id="0fb45-106">Если скрипты в задачах или компонентах скрипта содержат ссылки на интерфейсы, то перед обновлением пакета эти ссылки, возможно, придется изменить.</span><span class="sxs-lookup"><span data-stu-id="0fb45-106">If the scripts in either the Script tasks or Script components reference interfaces, you might have to modify those references before you upgrade the package.</span></span> <span data-ttu-id="0fb45-107">В противном случае в зависимости от используемого метода обновления либо пакет не будет обновлен, либо не удастся подтвердить правильность скриптов.</span><span class="sxs-lookup"><span data-stu-id="0fb45-107">Otherwise, the package will not be upgraded or the scripts will not be validated, depending on the upgrade method that you use.</span></span> <span data-ttu-id="0fb45-108">Чтобы изменить эти ссылки, замените ссылки на интерфейсы IDTS*xxx*90 ссылками на соответствующие интерфейсы IDTS*xxx*100.</span><span class="sxs-lookup"><span data-stu-id="0fb45-108">To modify these references, replace references to IDTS*xxx*90 interfaces with references to the corresponding IDTS*xxx*100 interfaces.</span></span>  
  
 <span data-ttu-id="0fb45-109">Дополнительные сведения о переносе скриптов и обновлении пакетов см. в разделе [upgrade Integration Services Packages](../../integration-services/install-windows/upgrade-integration-services-packages.md).</span><span class="sxs-lookup"><span data-stu-id="0fb45-109">For more information about how to migrate scripts and upgrade packages, see [Upgrade Integration Services Packages](../../integration-services/install-windows/upgrade-integration-services-packages.md).</span></span>  
  
## <a name="understanding-migration-failures"></a><span data-ttu-id="0fb45-110">Основные сведения об ошибках миграции</span><span class="sxs-lookup"><span data-stu-id="0fb45-110">Understanding Migration Failures</span></span>  
 <span data-ttu-id="0fb45-111">При переносе скриптов миграция может завершиться ошибкой по одной из следующих причин.</span><span class="sxs-lookup"><span data-stu-id="0fb45-111">When you migrate the scripts, the migration can fail because of one of the following reasons:</span></span>  
  
-   <span data-ttu-id="0fb45-112">Точка входа для скрипта VSA была переименована.</span><span class="sxs-lookup"><span data-stu-id="0fb45-112">The entry point for the VSA script was renamed.</span></span>  
  
     <span data-ttu-id="0fb45-113">Точка входа указывает метод класса `ScriptMain` в проекте VSTA, который службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] вызывают во время выполнения как точку входа в код задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="0fb45-113">The entry point specifies the method in the `ScriptMain` class in the VSTA project that the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] runtime calls as the entry point into the Script task code.</span></span> <span data-ttu-id="0fb45-114">Класс `ScriptMain` является классом по умолчанию, создаваемым шаблонами скриптов.</span><span class="sxs-lookup"><span data-stu-id="0fb45-114">The `ScriptMain` class is the default class that the script templates generate.</span></span>  
  
-   <span data-ttu-id="0fb45-115">Не существует точки входа, или имеется несколько точек входа в скрипты VSA.</span><span class="sxs-lookup"><span data-stu-id="0fb45-115">There is no entry point or there are multiple entry points in the VSA script.</span></span>  
  
-   <span data-ttu-id="0fb45-116">Не удалось добавить ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="0fb45-116">Assembly references could not be added.</span></span>  
  
-   <span data-ttu-id="0fb45-117">Класс `ScriptMain` был изменен. В него была добавлена возможность наследования из других классов в дополнение к классу `ScriptObjectModelSSIS`.</span><span class="sxs-lookup"><span data-stu-id="0fb45-117">The `ScriptMain` class was modified to inherit from other classes in addition to the `ScriptObjectModelSSIS` class.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="0fb45-118">не [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] поддерживает множественное наследование.</span><span class="sxs-lookup"><span data-stu-id="0fb45-118">[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] does not support multiple inheritance.</span></span>  
  
 <span data-ttu-id="0fb45-119">Невозможно преобразовать скрипт VSA, который использует, [!INCLUDE[vbprvblong](../../includes/vbprvblong-md.md)] в скрипт VSTA, использующий [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0fb45-119">You cannot convert a VSA script that uses [!INCLUDE[vbprvblong](../../includes/vbprvblong-md.md)] to a VSTA script that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)].</span></span> <span data-ttu-id="0fb45-120">Однако можно создать новый скрипт VSTA, использующий [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0fb45-120">However, you can create a new VSTA script that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)].</span></span> <span data-ttu-id="0fb45-121">Дополнительные сведения см. в разделах [Кодирование и отладка задачи "Скрипт"](../../integration-services/control-flow/script-task.md) и [Кодирование и отладка компонента скрипта](../../integration-services/data-flow/transformations/script-component.md).</span><span class="sxs-lookup"><span data-stu-id="0fb45-121">For more information, see [Coding and Debugging the Script Task](../../integration-services/control-flow/script-task.md) and [Coding and Debugging the Script Component](../../integration-services/data-flow/transformations/script-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fb45-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="0fb45-122">See Also</span></span>  
 [<span data-ttu-id="0fb45-123">Расширение пакетов с помощью сценариев</span><span class="sxs-lookup"><span data-stu-id="0fb45-123">Extending Packages with Scripting</span></span>](../../relational-databases/server-management-objects-smo/tasks/scripting.md)  
  
  
