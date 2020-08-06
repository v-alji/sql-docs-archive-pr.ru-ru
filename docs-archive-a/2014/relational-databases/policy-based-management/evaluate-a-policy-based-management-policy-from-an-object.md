---
title: Вычисление политики управления на основе политик в контексте объекта | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, evaluate policy
ms.assetid: b9e9d646-4894-4dee-a02a-0c71a8dc020e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f0de02092c87a727b723a5940805f34a75052e5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665992"
---
# <a name="evaluate-a-policy-based-management-policy-from-an-object"></a><span data-ttu-id="822e7-102">Вычисление политики управления на основе политик на основе объекта</span><span class="sxs-lookup"><span data-stu-id="822e7-102">Evaluate a Policy-Based Management Policy from an Object</span></span>
  <span data-ttu-id="822e7-103">В этом разделе описывается, как вычислить политику на основе экземпляра сервера, базы данных или объекта базы данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="822e7-103">This topic describes how to evaluate a policy from a server instance, database, or database object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="822e7-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="822e7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="822e7-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="822e7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="822e7-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="822e7-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="822e7-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="822e7-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="822e7-108">**Вычисление политики на основе объекта с помощью:**</span><span class="sxs-lookup"><span data-stu-id="822e7-108">**To evaluate a policy from an object, using:**</span></span>  
  
     [<span data-ttu-id="822e7-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="822e7-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="822e7-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="822e7-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="822e7-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="822e7-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="822e7-112">Режим выполнения определяется как часть политики и не может быть изменен в диалоговом окне **Вычисление политик** .</span><span class="sxs-lookup"><span data-stu-id="822e7-112">The execution mode is defined as part of the policy and cannot be changed in the **Evaluate Policies** dialog box.</span></span>  
  
-   <span data-ttu-id="822e7-113">Диалоговое окно **Вычисление политик** показывает только политики, соответствующие объекту базы данных.</span><span class="sxs-lookup"><span data-stu-id="822e7-113">The **Evaluate Policies** dialog box only shows policies appropriate for the database object.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="822e7-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="822e7-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="822e7-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="822e7-115">Permissions</span></span>  
 <span data-ttu-id="822e7-116">Требуется членство в роли PolicyAdministratorRole базы данных msdb.</span><span class="sxs-lookup"><span data-stu-id="822e7-116">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="822e7-117">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="822e7-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-evaluate-a-policy-from-an-object"></a><span data-ttu-id="822e7-118">Вычисление политики на основе объекта</span><span class="sxs-lookup"><span data-stu-id="822e7-118">To evaluate a policy from an object</span></span>  
  
1.  <span data-ttu-id="822e7-119">В обозревателе объектов щелкните правой кнопкой мыши экземпляр сервера, базу данных или объект базы данных, укажите **Политики**и выберите пункт **Вычислить**.</span><span class="sxs-lookup"><span data-stu-id="822e7-119">In Object Explorer, right-click a server instance, a database, or a database object, point to **Policies**, and select **Evaluate**.</span></span>  
  
2.  <span data-ttu-id="822e7-120">В диалоговом окне **Вычисление политик** выберите одну или несколько политик, затем нажмите кнопку **Вычислить** для запуска политики в режиме вычисления.</span><span class="sxs-lookup"><span data-stu-id="822e7-120">In the **Evaluate Policies** dialog box, select one or more policies and click **Evaluate** to run the policy in evaluation mode.</span></span> <span data-ttu-id="822e7-121">Создает отчет о соответствии политике для набора целей, но не изменяет конфигурацию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и не обеспечивает соблюдение политики в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="822e7-121">This generates a compliance report for the target set but does not reconfigure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or enforce future compliance.</span></span> <span data-ttu-id="822e7-122">Для целевых объектов, не соответствующих выбранным политикам и имеющих свойства, которые можно перенастроить с помощью управления на основе политик, соответствие политике можно включить принудительно, нажав кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="822e7-122">For targets that do not comply with the selected policies and have properties that can be reconfigured by Policy-Based Management, you can enforce policy compliance by clicking **Apply**.</span></span> <span data-ttu-id="822e7-123">Дополнительные сведения о параметрах, доступных в диалоговом окне **Вычисление политик** , см. в разделах [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md), [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md)и [Results Detailed View Dialog Box](results-detailed-view-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="822e7-123">For more information on the available options in the **Evaluate Policies** dialog box, see [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md), [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md), and [Results Detailed View Dialog Box](results-detailed-view-dialog-box.md).</span></span>  
  
3.  <span data-ttu-id="822e7-124">После завершения нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="822e7-124">When finished, click **Close**.</span></span>  
  
  
