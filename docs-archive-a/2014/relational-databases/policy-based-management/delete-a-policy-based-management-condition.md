---
title: Удаление условия управления на основе политик | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, delete policy conditions
ms.assetid: e04148b8-f6dd-4c50-a5ef-c650b71dbf4d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f02a5294ecb53db4d8baa4f3dae0a232d9551a13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655106"
---
# <a name="delete-a-policy-based-management-condition"></a><span data-ttu-id="a0986-102">Удаление условия управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="a0986-102">Delete a Policy-Based Management Condition</span></span>
  <span data-ttu-id="a0986-103">В этом разделе описывается удаление условия управления на основе политик в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0986-103">This topic describes how to delete a Policy-based Management condition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="a0986-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="a0986-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a0986-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="a0986-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a0986-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a0986-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a0986-107">**Удаление условия с помощью:**</span><span class="sxs-lookup"><span data-stu-id="a0986-107">**To delete a condition, using:**</span></span>  
  
     [<span data-ttu-id="a0986-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a0986-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a0986-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="a0986-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a0986-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="a0986-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a0986-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="a0986-111">Permissions</span></span>  
 <span data-ttu-id="a0986-112">Требуется членство в роли PolicyAdministratorRole базы данных msdb.</span><span class="sxs-lookup"><span data-stu-id="a0986-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a0986-113">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a0986-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-condition"></a><span data-ttu-id="a0986-114">Удаление условия</span><span class="sxs-lookup"><span data-stu-id="a0986-114">To delete a condition</span></span>  
  
1.  <span data-ttu-id="a0986-115">В **обозревателе объектов**щелкните знак «плюс», чтобы развернуть сервер, содержащий условие, которое нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="a0986-115">In **Object Explorer**, click the plus sign to expand the server that contains the condition that you want to delete.</span></span>  
  
2.  <span data-ttu-id="a0986-116">Щелкните знак «плюс», чтобы развернуть папку **Управление** .</span><span class="sxs-lookup"><span data-stu-id="a0986-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="a0986-117">Щелкните знак «плюс», чтобы развернуть папку **Управление политиками**.</span><span class="sxs-lookup"><span data-stu-id="a0986-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="a0986-118">Щелкните знак «плюс», чтобы развернуть папку **Условия** .</span><span class="sxs-lookup"><span data-stu-id="a0986-118">Click the plus sign to expand the **Conditions** folder.</span></span>  
  
5.  <span data-ttu-id="a0986-119">Щелкните правой кнопкой мыши условие, которое необходимо удалить, и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a0986-119">Right-click the condition that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="a0986-120">В диалоговом окне **Удаление объекта** убедитесь, что выбрано верное условие, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a0986-120">In the **Delete Object** dialog box, ensure that the correct condition is selected and then click **OK**.</span></span>  
  
  
