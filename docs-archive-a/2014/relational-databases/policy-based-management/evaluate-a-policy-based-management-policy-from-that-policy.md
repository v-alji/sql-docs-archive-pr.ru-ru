---
title: Вычисление политики управления на основе политик в контексте этой политики | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, evaluate policy
ms.assetid: 0b3214bd-d0ab-45ab-9281-3d95507abe54
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 207c86f1465c49238fc9b50ee75489b43d956caf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665994"
---
# <a name="evaluate-a-policy-based-management-policy-from-that-policy"></a><span data-ttu-id="4e971-102">Вычисление политики управления на основе политик по этой политике</span><span class="sxs-lookup"><span data-stu-id="4e971-102">Evaluate a Policy-Based Management Policy from That Policy</span></span>
  <span data-ttu-id="4e971-103">В этом разделе описано вычисление политики в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e971-103">This topic describes how to evaluate a policy using that policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="4e971-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="4e971-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4e971-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="4e971-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4e971-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="4e971-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4e971-107">**Для вычисления политики используется:**</span><span class="sxs-lookup"><span data-stu-id="4e971-107">**To evaluate a policy, using:**</span></span>  
  
     [<span data-ttu-id="4e971-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4e971-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4e971-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="4e971-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4e971-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="4e971-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4e971-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="4e971-111">Permissions</span></span>  
 <span data-ttu-id="4e971-112">Требуется членство в роли PolicyAdministratorRole базы данных msdb.</span><span class="sxs-lookup"><span data-stu-id="4e971-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4e971-113">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4e971-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-evaluate-a-policy"></a><span data-ttu-id="4e971-114">Вычисление политики</span><span class="sxs-lookup"><span data-stu-id="4e971-114">To evaluate a policy</span></span>  
  
1.  <span data-ttu-id="4e971-115">В **обозревателе объектов**щелкните знак «плюс», чтобы развернуть сервер, содержащий политику, которую нужно вычислить.</span><span class="sxs-lookup"><span data-stu-id="4e971-115">In **Object Explorer**, click the plus sign to expand the server that contains the policy that you want to evaluate.</span></span>  
  
2.  <span data-ttu-id="4e971-116">Щелкните знак «плюс», чтобы развернуть папку **Управление** .</span><span class="sxs-lookup"><span data-stu-id="4e971-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="4e971-117">Щелкните знак «плюс», чтобы развернуть папку **Управление политиками**.</span><span class="sxs-lookup"><span data-stu-id="4e971-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="4e971-118">Щелкните знак «плюс», чтобы развернуть папку **Политики** .</span><span class="sxs-lookup"><span data-stu-id="4e971-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="4e971-119">Щелкните правой кнопкой мыши политику, которую необходимо вычислить, и выберите пункт **Вычислить**.</span><span class="sxs-lookup"><span data-stu-id="4e971-119">Right-click the policy that you want to evaluate and select **Evaluate**.</span></span>  
  
6.  <span data-ttu-id="4e971-120">В диалоговом окне **Анализ результатов**  показаны результаты вычисления политики.</span><span class="sxs-lookup"><span data-stu-id="4e971-120">In the **Evaluate Results**  dialog box, you see the results of the policy evaluation.</span></span> <span data-ttu-id="4e971-121">Для целевых объектов, не соответствующих политике и имеющих свойства, которые можно перенастроить с помощью управления на основе политик, соответствие политике можно включить принудительно, нажав кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="4e971-121">For targets that do not comply with the policy and have properties that can be reconfigured by Policy-Based Management, you can enforce compliance by clicking **Apply**.</span></span> <span data-ttu-id="4e971-122">Дополнительные сведения о параметрах, доступных в диалоговом окне **Вычисление политик** , см. в разделах [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md) и [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md).</span><span class="sxs-lookup"><span data-stu-id="4e971-122">For more information on the available options in the **Evaluate Policies** dialog box, see [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md) and [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md).</span></span>  
  
7.  <span data-ttu-id="4e971-123">После завершения нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="4e971-123">When finished, click **Close**.</span></span>  
  
  
