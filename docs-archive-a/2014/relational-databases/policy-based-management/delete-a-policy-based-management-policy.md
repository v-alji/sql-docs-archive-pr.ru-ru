---
title: Удаление политики управления на основе политик | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, delete policies
ms.assetid: 488f0305-190c-4223-aa5c-e9bd43b520eb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c43bc3cdf4a7a5b5d9268bbd7e68506616d1f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728210"
---
# <a name="delete-a-policy-based-management-policy"></a><span data-ttu-id="2df73-102">Удаление политики управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="2df73-102">Delete a Policy-Based Management Policy</span></span>
  <span data-ttu-id="2df73-103">В этом разделе описывается удаление политики управления на основе политик в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2df73-103">This topic describes how to delete a Policy-Based Management policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2df73-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="2df73-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2df73-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="2df73-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2df73-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="2df73-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2df73-107">**Удаление политики с помощью:**</span><span class="sxs-lookup"><span data-stu-id="2df73-107">**To delete a policy, using:**</span></span>  
  
     [<span data-ttu-id="2df73-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2df73-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2df73-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="2df73-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2df73-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="2df73-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2df73-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="2df73-111">Permissions</span></span>  
 <span data-ttu-id="2df73-112">Требуется членство в роли PolicyAdministratorRole базы данных msdb.</span><span class="sxs-lookup"><span data-stu-id="2df73-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2df73-113">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2df73-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-policy"></a><span data-ttu-id="2df73-114">Удаление политики</span><span class="sxs-lookup"><span data-stu-id="2df73-114">To delete a policy</span></span>  
  
1.  <span data-ttu-id="2df73-115">В обозревателе объектов щелкните знак «плюс», чтобы развернуть сервер, содержащий политику управления на основе политик, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="2df73-115">In Object Explorer, click the plus sign to expand the server that contains the Policy-Based Management policy that you want to delete.</span></span>  
  
2.  <span data-ttu-id="2df73-116">Щелкните знак «плюс», чтобы развернуть папку **Управление** .</span><span class="sxs-lookup"><span data-stu-id="2df73-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="2df73-117">Щелкните знак «плюс», чтобы развернуть папку **Управление политиками**.</span><span class="sxs-lookup"><span data-stu-id="2df73-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="2df73-118">Щелкните знак «плюс», чтобы развернуть папку **Политики** .</span><span class="sxs-lookup"><span data-stu-id="2df73-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="2df73-119">Щелкните правой кнопкой мыши политику, которую необходимо удалить, и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="2df73-119">Right-click the policy that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="2df73-120">В диалоговом окне **Удаление объекта** убедитесь, что выбрано верное условие, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2df73-120">In the **Delete Object** dialog box, ensure that the correct condition is selected and then click **OK**.</span></span>  
  
  
