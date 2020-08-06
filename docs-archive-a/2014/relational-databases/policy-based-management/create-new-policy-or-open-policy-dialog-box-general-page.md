---
title: Диалоговое окно "Создание новой политики" или "Открытие политики", страница "Общие" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.newgroup.f1
- sql12.swb.dmf.policy.f1
- sql12.swb.dmf.policy.filter.f1
ms.assetid: c00bebd0-d04b-4c64-840e-8b7a2c603436
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4b67cb8faf18001b841824b806e7befc0683d457
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657732"
---
# <a name="create-new-policy-or-open-policy-dialog-box-general-page"></a><span data-ttu-id="46140-102">Диалоговое окно «Создание новой политики» или «Открытие политики», страница «Общие»</span><span class="sxs-lookup"><span data-stu-id="46140-102">Create New Policy or Open Policy Dialog Box, General Page</span></span>
  <span data-ttu-id="46140-103">С помощью этого диалогового окна можно создать новую или изменить существующую политику управления на основе политик.</span><span class="sxs-lookup"><span data-stu-id="46140-103">Use this dialog box to create a new Policy-Based Management policy or modify an existing policy.</span></span> <span data-ttu-id="46140-104">Используя области **Применить к** и **Ограничение сервера** в качестве фильтра можно ограничить действие политик определенным подмножеством всех возможных целей.</span><span class="sxs-lookup"><span data-stu-id="46140-104">Use the **Against targets** and **Server restriction** areas as a filter to limit policies to a subset of all possible targets.</span></span> <span data-ttu-id="46140-105">Условия, которые будут использованы в качестве фильтров целей, должны быть определены для физического аспекта и не должны содержать функций и оператор LIKE.</span><span class="sxs-lookup"><span data-stu-id="46140-105">For conditions to be used as target filters, they must be defined on a physical facet, must not contain functions, and must not contain the LIKE operator.</span></span> <span data-ttu-id="46140-106">Когда система вычисляет набор объектов для политики, системные объекты исключаются из него по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="46140-106">When the system computes the object set for a policy, by default the system objects are excluded.</span></span>  <span data-ttu-id="46140-107">Например, если набор объектов для политики относится ко всем таблицам, политика будет неприменима к системным таблицам.</span><span class="sxs-lookup"><span data-stu-id="46140-107">For example, if the object set of the policy refers to all tables, the policy will not apply to system tables.</span></span> <span data-ttu-id="46140-108">Если пользователям требуется оценить политику, используя системные объекты, их можно явно добавить в набор объектов.</span><span class="sxs-lookup"><span data-stu-id="46140-108">If users want to evaluate a policy against system objects, they can explicitly add system objects to the object set.</span></span> <span data-ttu-id="46140-109">Однако несмотря на то, что все политики поддерживаются режимом оценки **проверка по расписанию** , в режиме **проверка при внесении изменений** по соображениям производительности поддерживаются не все политики с обязательными наборами объектов.</span><span class="sxs-lookup"><span data-stu-id="46140-109">However, though all policies are supported for **check on schedule** evaluation mode, for performance reason, not all policies with arbitrary object sets are supported for **check on change** evaluation mode.</span></span> <span data-ttu-id="46140-110">Дополнительные сведения см. в разделе [https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx](https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx)</span><span class="sxs-lookup"><span data-stu-id="46140-110">For more information, see [https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx](https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx)</span></span>  
  
## <a name="options"></a><span data-ttu-id="46140-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="46140-111">Options</span></span>  
 <span data-ttu-id="46140-112">**Название**</span><span class="sxs-lookup"><span data-stu-id="46140-112">**Name**</span></span>  
 <span data-ttu-id="46140-113">Введите имя для новой политики.</span><span class="sxs-lookup"><span data-stu-id="46140-113">For a new policy, type the new policy name.</span></span> <span data-ttu-id="46140-114">Если политика уже существует, отображается ее имя.</span><span class="sxs-lookup"><span data-stu-id="46140-114">For an existing policy, the name is displayed.</span></span>  
  
 <span data-ttu-id="46140-115">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="46140-115">**Enabled**</span></span>  
 <span data-ttu-id="46140-116">Установите флажок **Включено** , чтобы включить политику.</span><span class="sxs-lookup"><span data-stu-id="46140-116">Select the **Enabled** check box to enable the policy.</span></span> <span data-ttu-id="46140-117">Снимите флажок в поле **Включено** , чтобы отключить политику.</span><span class="sxs-lookup"><span data-stu-id="46140-117">Clear the **Enabled** check box to disable the policy.</span></span> <span data-ttu-id="46140-118">Флажок **Включено** применяется к автоматизации политики.</span><span class="sxs-lookup"><span data-stu-id="46140-118">The **Enabled** box applies to policy automation.</span></span> <span data-ttu-id="46140-119">Он создает или удаляет систему автоматизации для политики.</span><span class="sxs-lookup"><span data-stu-id="46140-119">It creates or removes the automation system for the policy.</span></span> <span data-ttu-id="46140-120">Автоматизация применяет следующие механизмы.</span><span class="sxs-lookup"><span data-stu-id="46140-120">Automation uses the following mechanisms:</span></span>  
  
 <span data-ttu-id="46140-121">**При изменении: запретить**</span><span class="sxs-lookup"><span data-stu-id="46140-121">**On change: prevent**</span></span>  
 <span data-ttu-id="46140-122">Триггер базы данных принудительно реализует соответствие.</span><span class="sxs-lookup"><span data-stu-id="46140-122">A database trigger enforces compliance.</span></span>  
  
 <span data-ttu-id="46140-123">**При изменении: только внесение в журнал**</span><span class="sxs-lookup"><span data-stu-id="46140-123">**On change: log only**</span></span>  
 <span data-ttu-id="46140-124">Событие служб Notification Services проверяет соответствие.</span><span class="sxs-lookup"><span data-stu-id="46140-124">A notification services event checks for compliance.</span></span>  
  
 <span data-ttu-id="46140-125">**По расписанию**</span><span class="sxs-lookup"><span data-stu-id="46140-125">**On schedule**</span></span>  
 <span data-ttu-id="46140-126">Создается задание агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , чтобы проверить соответствие по расписанию.</span><span class="sxs-lookup"><span data-stu-id="46140-126">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job is created to check for compliance on a schedule.</span></span>  
  
 <span data-ttu-id="46140-127">В политиках, работающих с режимом оценки **по запросу** , этот флажок не устанавливается.</span><span class="sxs-lookup"><span data-stu-id="46140-127">Policies that are run using **On demand** evaluation mode do not use this check box.</span></span>  
  
 <span data-ttu-id="46140-128">**Проверка условия**</span><span class="sxs-lookup"><span data-stu-id="46140-128">**Check condition**</span></span>  
 <span data-ttu-id="46140-129">Выберите условие управления на основе политик, которое использует данная политика.</span><span class="sxs-lookup"><span data-stu-id="46140-129">Select the Policy-Based Management condition that this policy uses.</span></span> <span data-ttu-id="46140-130">Перечисляются все условия на сервере для связанного аспекта управления на основе политик.</span><span class="sxs-lookup"><span data-stu-id="46140-130">All conditions on the server for the associated Policy-Based Management facet are listed.</span></span> <span data-ttu-id="46140-131">Нажмите кнопку **Создать условие** , чтобы создать новое условие.</span><span class="sxs-lookup"><span data-stu-id="46140-131">Click **New condition** to create a new condition.</span></span> <span data-ttu-id="46140-132">Нажмите кнопку с многоточием ( **...** ), чтобы изменить условие.</span><span class="sxs-lookup"><span data-stu-id="46140-132">Click the ellipsis (**...**) button to modify the condition.</span></span>  
  
 <span data-ttu-id="46140-133">**Применить к**</span><span class="sxs-lookup"><span data-stu-id="46140-133">**Against targets**</span></span>  
 <span data-ttu-id="46140-134">Чтобы завершить создание критерия фильтра, выберите типы целевого объекта, доступные для данного аспекта.</span><span class="sxs-lookup"><span data-stu-id="46140-134">Select the target types that are available for this facet to complete a filter expression.</span></span>  
  
 <span data-ttu-id="46140-135">**Режим оценки**</span><span class="sxs-lookup"><span data-stu-id="46140-135">**Evaluation Mode**</span></span>  
 <span data-ttu-id="46140-136">Выберите режим оценки для политики.</span><span class="sxs-lookup"><span data-stu-id="46140-136">Select the evaluation mode for the policy.</span></span> <span data-ttu-id="46140-137">Некоторые политики можно проверить, но нельзя принудительно применить.</span><span class="sxs-lookup"><span data-stu-id="46140-137">Some policies can be checked but not enforced.</span></span> <span data-ttu-id="46140-138">Существуют следующие режимы оценки.</span><span class="sxs-lookup"><span data-stu-id="46140-138">The evaluation modes are as follows:</span></span>  
  
 <span data-ttu-id="46140-139">**по запросу**</span><span class="sxs-lookup"><span data-stu-id="46140-139">**On demand**</span></span>  
 <span data-ttu-id="46140-140">Политика будет запускаться только пользователем из диалогового окна **Вычислить** .</span><span class="sxs-lookup"><span data-stu-id="46140-140">Policy will only be run when you run it from the **Evaluate** dialog box.</span></span>  
  
 <span data-ttu-id="46140-141">**По расписанию**</span><span class="sxs-lookup"><span data-stu-id="46140-141">**On schedule**</span></span>  
 <span data-ttu-id="46140-142">Периодически происходит оценка политики, создаются в журнале записи для политик, имеющих несоответствие, и формируется отчет.</span><span class="sxs-lookup"><span data-stu-id="46140-142">Periodically evaluates the policy, records a log entry for policies that have out-of-compliance, and creates a report.</span></span> <span data-ttu-id="46140-143">Включает поле **Расписание** .</span><span class="sxs-lookup"><span data-stu-id="46140-143">Enables the **Schedule** box.</span></span>  
  
 <span data-ttu-id="46140-144">**При изменении: только внесение в журнал**</span><span class="sxs-lookup"><span data-stu-id="46140-144">**On change: log only**</span></span>  
 <span data-ttu-id="46140-145">При попытке внесения изменений несоответствующие изменения не предотвращаются, но нарушения заносятся в журнал.</span><span class="sxs-lookup"><span data-stu-id="46140-145">When changes are tried, this option does not prevent out-of-compliance changes, but logs policy violations.</span></span>  
  
 <span data-ttu-id="46140-146">**При изменении: запретить**</span><span class="sxs-lookup"><span data-stu-id="46140-146">**On change: prevent**</span></span>  
 <span data-ttu-id="46140-147">В данном режиме запрещается внесение изменений, нарушающих политику.</span><span class="sxs-lookup"><span data-stu-id="46140-147">When changes are tried, this option prevents changes that would violate the policy.</span></span>  
  
 <span data-ttu-id="46140-148">**Расписание**</span><span class="sxs-lookup"><span data-stu-id="46140-148">**Schedule**</span></span>  
 <span data-ttu-id="46140-149">Этот параметр появляется, если выбран режим оценки **По расписанию** .</span><span class="sxs-lookup"><span data-stu-id="46140-149">This option appears when **On schedule** evaluation mode is selected.</span></span> <span data-ttu-id="46140-150">Введите имя расписания, нажмите кнопку **Выбрать** , чтобы выбрать из списка график, либо нажмите кнопку **Создать** , чтобы создать новый график.</span><span class="sxs-lookup"><span data-stu-id="46140-150">Type the name of the schedule, click **Pick** to select a schedule from a list, or click **New** to create a new schedule.</span></span> <span data-ttu-id="46140-151">Чтобы включить область расписаний, необходимо выбрать режим **По расписанию** .</span><span class="sxs-lookup"><span data-stu-id="46140-151">To enable the schedule area, **On schedule** must be selected.</span></span>  
  
 <span data-ttu-id="46140-152">**Ограничение сервера**</span><span class="sxs-lookup"><span data-stu-id="46140-152">**Server restriction**</span></span>  
 <span data-ttu-id="46140-153">Выберите типы серверов, подходящие для данной политики.</span><span class="sxs-lookup"><span data-stu-id="46140-153">Select the types of servers that are appropriate for this policy.</span></span> <span data-ttu-id="46140-154">Параметрами могут быть **Нет** или выбранное условие, выполняющее фильтрацию возможных серверов.</span><span class="sxs-lookup"><span data-stu-id="46140-154">Options are **None** or select a condition that filters the possible servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46140-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="46140-155">See Also</span></span>  
 [<span data-ttu-id="46140-156">Администрирование серверов с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="46140-156">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
