---
title: Вычисление политики управления на основе политик по расписанию | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, evaluate policy
ms.assetid: bea09522-ff47-4037-ab55-a98ea7c10099
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f1c6b1a7d13d14c02f4b4e537c2dbdb2df39d02c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731514"
---
# <a name="evaluate-a-policy-based-management-policy-on-a-schedule"></a><span data-ttu-id="7eb67-102">Вычисление политики управления на основе политик по расписанию</span><span class="sxs-lookup"><span data-stu-id="7eb67-102">Evaluate a Policy-Based Management Policy on a Schedule</span></span>
  <span data-ttu-id="7eb67-103">В этом разделе описывается вычисление политики управления на основе политик по расписанию в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7eb67-103">This topic describes how to evaluate a Policy-Based Management policy on a schedule in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="7eb67-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="7eb67-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7eb67-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="7eb67-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7eb67-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="7eb67-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7eb67-107">**Вычисление политики по расписанию с помощью:**</span><span class="sxs-lookup"><span data-stu-id="7eb67-107">**To evaluate a policy on a schedule, using:**</span></span>  
  
     [<span data-ttu-id="7eb67-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7eb67-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7eb67-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="7eb67-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7eb67-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="7eb67-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7eb67-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="7eb67-111">Permissions</span></span>  
 <span data-ttu-id="7eb67-112">Требуется членство в роли PolicyAdministratorRole базы данных msdb.</span><span class="sxs-lookup"><span data-stu-id="7eb67-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7eb67-113">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7eb67-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-evaluate-a-policy-on-a-schedule"></a><span data-ttu-id="7eb67-114">Вычисление политики по расписанию</span><span class="sxs-lookup"><span data-stu-id="7eb67-114">To evaluate a policy on a schedule</span></span>  
  
1.  <span data-ttu-id="7eb67-115">В **обозревателе объектов**щелкните знак «плюс», чтобы развернуть сервер, содержащий расписание политики, которую нужно вычислить.</span><span class="sxs-lookup"><span data-stu-id="7eb67-115">In **Object Explorer**, click the plus sign to expand the server that contains the policy schedule that you want to evaluate.</span></span>  
  
2.  <span data-ttu-id="7eb67-116">Щелкните знак «плюс», чтобы развернуть папку **Управление** .</span><span class="sxs-lookup"><span data-stu-id="7eb67-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="7eb67-117">Щелкните знак «плюс», чтобы развернуть папку **Управление политиками**.</span><span class="sxs-lookup"><span data-stu-id="7eb67-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="7eb67-118">Щелкните знак «плюс», чтобы развернуть папку **Политики** .</span><span class="sxs-lookup"><span data-stu-id="7eb67-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="7eb67-119">Щелкните правой кнопкой мыши политику, расписание которой нужно вычислить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7eb67-119">Right-click the policy whose schedule you what to evaluate and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="7eb67-120">В диалоговом окне **Открытие политики —** _имя_политики_ в списке **Режим оценки** выберите значение **По расписанию**.</span><span class="sxs-lookup"><span data-stu-id="7eb67-120">On the **Open Policy -**_policy_name_ dialog box, in the **Evaluation Mode** list, select **On schedule**.</span></span>  
  
7.  <span data-ttu-id="7eb67-121">В разделе **Расписание**нажмите кнопку **Выбрать** , чтобы указать существующее расписание, или кнопку **Создать** , чтобы создать новое расписание.</span><span class="sxs-lookup"><span data-stu-id="7eb67-121">Under **Schedule**, click either **Pick** to specify an existing schedule or **New** to create a new schedule.</span></span>  
  
8.  <span data-ttu-id="7eb67-122">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7eb67-122">When finished, click **OK**.</span></span>  
  
  
