---
title: Создание политики управления на основе политик | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, creating policies
ms.assetid: b28bf963-89f9-4941-b6c1-6004fec347f1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e76b4dce17e00bae5e8ca4fcf071868c0641c786
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664888"
---
# <a name="create-a-policy-based-management-policy"></a><span data-ttu-id="bceda-102">Создание политики управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="bceda-102">Create a Policy-Based Management Policy</span></span>
  <span data-ttu-id="bceda-103">В этом разделе описывается создание политики управления на основе политик в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bceda-103">This topic describes how to create a Policy-Based Management policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="bceda-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="bceda-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bceda-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="bceda-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bceda-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="bceda-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bceda-107">**Создание политики с помощью:**</span><span class="sxs-lookup"><span data-stu-id="bceda-107">**To create a policy, using:**</span></span>  
  
     [<span data-ttu-id="bceda-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bceda-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bceda-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="bceda-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bceda-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="bceda-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bceda-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="bceda-111">Permissions</span></span>  
 <span data-ttu-id="bceda-112">Требуется членство в роли PolicyAdministratorRole базы данных msdb.</span><span class="sxs-lookup"><span data-stu-id="bceda-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bceda-113">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bceda-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-policy"></a><span data-ttu-id="bceda-114">Создание политики</span><span class="sxs-lookup"><span data-stu-id="bceda-114">To create a policy</span></span>  
  
1.  <span data-ttu-id="bceda-115">В **обозревателе объектов**щелкните знак "плюс", чтобы развернуть сервер, на котором необходимо создать новую политику управления на основе политик.</span><span class="sxs-lookup"><span data-stu-id="bceda-115">In **Object Explorer**, click the plus sign to expand the server where you want to create a new a Policy-Based Management policy.</span></span>  
  
2.  <span data-ttu-id="bceda-116">Щелкните знак «плюс», чтобы развернуть папку **Управление** .</span><span class="sxs-lookup"><span data-stu-id="bceda-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="bceda-117">Щелкните знак «плюс», чтобы развернуть папку **Управление политиками**.</span><span class="sxs-lookup"><span data-stu-id="bceda-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="bceda-118">Щелкните правой кнопкой мыши папку **Политики** и выберите команду **Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="bceda-118">Right-click the **Policies** folder and select **New Policy**.</span></span>  
  
5.  <span data-ttu-id="bceda-119">В диалоговом окне **Создание новой политики** в поле **Имя** введите имя новой политики.</span><span class="sxs-lookup"><span data-stu-id="bceda-119">In the **Create New Policy** dialog box, in the **Name** box, type the name of the new policy.</span></span>  
  
6.  <span data-ttu-id="bceda-120">Установите флажок **Включено** , если требуется, чтобы политика была включена сразу после ее создания.</span><span class="sxs-lookup"><span data-stu-id="bceda-120">If you want the policy to be enabled as soon as it is created, select the **Enabled** check box.</span></span> <span data-ttu-id="bceda-121">Если режим вычисления имеет значение **По запросу**, флажок **Включено** недоступен.</span><span class="sxs-lookup"><span data-stu-id="bceda-121">If the evaluation mode is **On demand**, the **Enabled** check box is not available.</span></span>  
  
7.  <span data-ttu-id="bceda-122">В списке **Проверить условие** выберите одно из существующих условий или укажите пункт **Создать условие**.</span><span class="sxs-lookup"><span data-stu-id="bceda-122">In the **Check condition** list, select one of the existing conditions, or select **New Condition**.</span></span> <span data-ttu-id="bceda-123">Для изменения условия выберите его и нажмите кнопку с многоточием ( **...** ). Дополнительные сведения см. в статье [Создание нового условия управления на основе политик](create-a-new-policy-based-management-condition.md) или [Просмотр или изменение свойств условия управления на основе политик](view-or-modify-the-properties-of-a-policy-based-management-condition.md).</span><span class="sxs-lookup"><span data-stu-id="bceda-123">To edit a condition, select the condition and then click the ellipsis (**...**). For more information, see [Create a New Policy-Based Management Condition](create-a-new-policy-based-management-condition.md) or [View or Modify the Properties of a Policy-Based Management Condition](view-or-modify-the-properties-of-a-policy-based-management-condition.md).</span></span>  
  
8.  <span data-ttu-id="bceda-124">Выберите один или несколько типов целевого объекта для данной политики в окне **Применить к** .</span><span class="sxs-lookup"><span data-stu-id="bceda-124">In the **Against targets** box, select one or more target types for this policy.</span></span> <span data-ttu-id="bceda-125">Некоторые условия и аспекты можно применить только к определенным типам целей.</span><span class="sxs-lookup"><span data-stu-id="bceda-125">Some conditions and facets can only be applied to certain types of targets.</span></span> <span data-ttu-id="bceda-126">Доступные наборы целей появляются в соответствующем окне.</span><span class="sxs-lookup"><span data-stu-id="bceda-126">The available target sets appear in the associated box.</span></span> <span data-ttu-id="bceda-127">Чтобы выбрать условие фильтрации для некоторых типов целей, разверните **Каждый** .</span><span class="sxs-lookup"><span data-stu-id="bceda-127">Expand **Every** to select a filtering condition for some types of the targets.</span></span> <span data-ttu-id="bceda-128">Если в разделе не появляются целевые объекты, убедитесь, что условие ограничено уровнем сервера.</span><span class="sxs-lookup"><span data-stu-id="bceda-128">If no targets appear in this box, the check condition is scoped at the server level.</span></span>  
  
9. <span data-ttu-id="bceda-129">Выберите тип поведения данной политики в окне **Режим вычисления** .</span><span class="sxs-lookup"><span data-stu-id="bceda-129">In the **Evaluation Mode** box, select how this policy will behave.</span></span> <span data-ttu-id="bceda-130">Разные условия могут иметь разные допустимые режимы вычисления.</span><span class="sxs-lookup"><span data-stu-id="bceda-130">Different conditions can have different valid evaluation modes.</span></span> <span data-ttu-id="bceda-131">Дополнительные сведения о допустимых режимах вычисления см. в статье [Администрирование серверов с помощью управления на основе политик](administer-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="bceda-131">For more information about which evaluation modes are valid, see [Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md).</span></span>  
  
10. <span data-ttu-id="bceda-132">Если политика вычисляется по расписанию, установите режим вычисления в состояние **По запросу**и нажмите **Выбрать** для выбора расписания либо нажмите кнопку **Создать** для создания нового расписания.</span><span class="sxs-lookup"><span data-stu-id="bceda-132">If the policy will be evaluated on a schedule, set the evaluation mode to **On schedule**, and then click **Pick** to select a schedule, or click **New** to create a new schedule.</span></span>  
  
11. <span data-ttu-id="bceda-133">Чтобы ограничить политику поднабором типов целевого объекта, выберите условия в окне **Ограничение сервера** или создайте новое условие.</span><span class="sxs-lookup"><span data-stu-id="bceda-133">To limit the policy to subset of the target types, in the **Server restriction** box, select from limiting conditions or create a new condition.</span></span>  
  
     <span data-ttu-id="bceda-134">Дополнительные сведения о параметрах, доступных в диалоговом окне **Создание новой политики** , см. в разделах [Диалоговое окно «Создание новой политики» или «Открытие политики», страница «Общие»](../../integration-services/general-page-of-integration-services-designers-options.md) и [Диалоговое окно «Создание новой политики» или «Открытие политики», страница «Описание»](create-new-policy-or-open-policy-dialog-box-description-page.md).</span><span class="sxs-lookup"><span data-stu-id="bceda-134">For more information on the available options in the **Create New Policy** dialog box, see [Create New Policy or Open Policy Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md) or [Create New Policy or Open Policy Dialog Box, Description Page](create-new-policy-or-open-policy-dialog-box-description-page.md).</span></span>  
  
12. <span data-ttu-id="bceda-135">В завершение нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bceda-135">When finished click **OK**.</span></span>  
  
  
