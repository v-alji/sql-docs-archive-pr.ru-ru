---
title: Создание условия управления на основе политик | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, creating policy conditions
ms.assetid: 8a612f7e-6c70-49db-a4de-48431e097cc5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e4fe206c9a82b69101508f6f0a760ca9c1bc423d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664893"
---
# <a name="create-a-new-policy-based-management-condition"></a><span data-ttu-id="40349-102">Создание нового условия управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="40349-102">Create a New Policy-Based Management Condition</span></span>
  <span data-ttu-id="40349-103">В этом разделе описывается создание условия управления на основе политик в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40349-103">This topic describes how to create a Policy-based Management condition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="40349-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="40349-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="40349-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="40349-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="40349-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="40349-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="40349-107">**Для создания условия используется:**</span><span class="sxs-lookup"><span data-stu-id="40349-107">**To create a condition, using:**</span></span>  
  
     [<span data-ttu-id="40349-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="40349-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="40349-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="40349-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="40349-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="40349-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="40349-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="40349-111">Permissions</span></span>  
 <span data-ttu-id="40349-112">Требуется членство в роли PolicyAdministratorRole базы данных msdb.</span><span class="sxs-lookup"><span data-stu-id="40349-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="40349-113">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="40349-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-condition"></a><span data-ttu-id="40349-114">Создание условия</span><span class="sxs-lookup"><span data-stu-id="40349-114">To create a condition</span></span>  
  
1.  <span data-ttu-id="40349-115">В **обозревателе объектов**щелкните знак "плюс", чтобы развернуть сервер, на котором необходимо создать условие управления на основе политик.</span><span class="sxs-lookup"><span data-stu-id="40349-115">In **Object Explorer**, click the plus sign to expand the server where you want to create a Policy-based Management condition.</span></span>  
  
2.  <span data-ttu-id="40349-116">Щелкните знак «плюс», чтобы развернуть папку **Управление** .</span><span class="sxs-lookup"><span data-stu-id="40349-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="40349-117">Щелкните знак «плюс», чтобы развернуть папку **Управление политиками**.</span><span class="sxs-lookup"><span data-stu-id="40349-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="40349-118">Чтобы развернуть папку **Аспекты** , щелкните знак «плюс».</span><span class="sxs-lookup"><span data-stu-id="40349-118">Click the plus sign to expand the **Facets** folder.</span></span>  
  
5.  <span data-ttu-id="40349-119">Щелкните правой кнопкой мыши аспект, в котором требуется создать новое условие, и выберите команду **Создать условие**.</span><span class="sxs-lookup"><span data-stu-id="40349-119">Right-click the facet in which you want to create a new condition and select **New Condition**.</span></span>  
  
6.  <span data-ttu-id="40349-120">В диалоговом окне **Создание нового условия** в поле **Имя** введите имя нового условия.</span><span class="sxs-lookup"><span data-stu-id="40349-120">In the **Create New Condition** dialog box, in the **Name** box, type the name of the new condition.</span></span>  
  
7.  <span data-ttu-id="40349-121">Подтвердите правильность аспекта в списке **Аспект** или выберите другой аспект.</span><span class="sxs-lookup"><span data-stu-id="40349-121">Confirm the correct facet in the **Facet** list, or select a different facet.</span></span>  
  
8.  <span data-ttu-id="40349-122">Создайте выражения условия в разделе **Выражение**, выбрав свойство аспекта в окне **Поле** , связанный оператор и значение.</span><span class="sxs-lookup"><span data-stu-id="40349-122">Under **Expression**, construct condition expressions by selecting a facet property in the **Field** box, together with its associated operator and value.</span></span> <span data-ttu-id="40349-123">При добавлении нескольких выражений их можно объединить с помощью операторов **And** или **Or**.</span><span class="sxs-lookup"><span data-stu-id="40349-123">When you add multiple expressions, the expressions can be joined by using **And** or **Or**.</span></span> <span data-ttu-id="40349-124">Дополнительные сведения о доступных параметрах данного диалогового окна см. в разделах [Диалоговое окно "Создание нового условия" или "Открытие условия", страница "Общие"](../../integration-services/general-page-of-integration-services-designers-options.md), [Диалоговое окно "Создание нового условия" или "Открытие условия", страница "Описание"](create-new-condition-or-open-condition-dialog-box-description-page.md) и [Диалоговое окно "Расширенное редактирование" (условие)](advanced-edit-condition-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="40349-124">For more information on the available options in this dialog box, see [Create New Condition or Open Condition Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md), [Create New Condition or Open Condition Dialog Box, Description Page](create-new-condition-or-open-condition-dialog-box-description-page.md), and [Advanced Edit &#40;Condition&#41; Dialog Box](advanced-edit-condition-dialog-box.md).</span></span>  
  
9. <span data-ttu-id="40349-125">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="40349-125">When finished, click **OK**.</span></span>  
  
  
