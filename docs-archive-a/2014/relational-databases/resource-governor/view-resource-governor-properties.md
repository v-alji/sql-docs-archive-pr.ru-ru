---
title: Просмотр свойств регулятора ресурсов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.rg.properties.f1
helpviewer_keywords:
- Resource Governor, properties
ms.assetid: de3510df-f792-4a9d-80fa-f198fd36cdc8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3cd7af8f4f8eb3cd0531bc907011846f73f94f6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658182"
---
# <a name="view-resource-governor-properties"></a><span data-ttu-id="ae9b3-102">Просмотр свойств регулятора ресурсов</span><span class="sxs-lookup"><span data-stu-id="ae9b3-102">View Resource Governor Properties</span></span>
  <span data-ttu-id="ae9b3-103">На странице свойств регулятора ресурсов в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]предусмотрена возможность создания и настройки сущности регуляторов ресурсов — пулов ресурсов и групп рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-103">You can create or configure Resource Governor entities, such as resource pools and workload groups, by using the Resource Governor Properties page in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
1.  <span data-ttu-id="ae9b3-104">**Перед началом работы**  [Разрешения](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="ae9b3-104">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
2.  <span data-ttu-id="ae9b3-105">**Просмотр свойств регулятора ресурсов с использованием следующих средств:**  [Страница «Свойства регулятора ресурсов»](#ViewRGProp)</span><span class="sxs-lookup"><span data-stu-id="ae9b3-105">**To view Resource Governor properties, using:**  [Resource Governor Properties page](#ViewRGProp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ae9b3-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="ae9b3-106">Before You Begin</span></span>  
 <span data-ttu-id="ae9b3-107">Кроме просмотра свойств сущностей регулятора ресурсов, на странице **Свойства регулятора ресурсов** можно выполнить некоторые задачи настройки.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-107">In addition to viewing the properties of Resource Governor entities, you can perform several configuration tasks using the **Resource Governor Properties** page.</span></span> <span data-ttu-id="ae9b3-108">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="ae9b3-108">For more information, see these topics:</span></span>  
  
-   [<span data-ttu-id="ae9b3-109">Включение регулятора ресурсов</span><span class="sxs-lookup"><span data-stu-id="ae9b3-109">Enable Resource Governor</span></span>](enable-resource-governor.md)  
  
-   [<span data-ttu-id="ae9b3-110">Отключение регулятора ресурсов</span><span class="sxs-lookup"><span data-stu-id="ae9b3-110">Disable Resource Governor</span></span>](disable-resource-governor.md)  
  
-   [<span data-ttu-id="ae9b3-111">Создание пула ресурсов</span><span class="sxs-lookup"><span data-stu-id="ae9b3-111">Create a Resource Pool</span></span>](create-a-resource-pool.md)  
  
-   [<span data-ttu-id="ae9b3-112">Создание группы рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="ae9b3-112">Create a Workload Group</span></span>](create-a-workload-group.md)  
  
-   [<span data-ttu-id="ae9b3-113">Изменение параметров пула ресурсов</span><span class="sxs-lookup"><span data-stu-id="ae9b3-113">Change Resource Pool Settings</span></span>](change-resource-pool-settings.md)  
  
-   [<span data-ttu-id="ae9b3-114">Изменение параметров группы рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="ae9b3-114">Change Workload Group Settings</span></span>](change-workload-group-settings.md)  
  
-   [<span data-ttu-id="ae9b3-115">Перемещение группы рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="ae9b3-115">Move a Workload Group</span></span>](move-a-workload-group.md)  
  
 <span data-ttu-id="ae9b3-116">При нажатии кнопки **ОК** после добавления, удаления или перемещения группы рабочей нагрузки или пула ресурсов выполняется инструкция ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-116">When you click **OK** after adding, deleting, or moving a workload group or resource pool, the ALTER RESOURCE GOVERNOR RECONFIGURE statement is executed.</span></span>  
  
 <span data-ttu-id="ae9b3-117">Если операция создания или изменения конфигурации пула ресурсов или группы рабочей нагрузки завершилась неуспешно, под заголовком страницы свойств будет отображено сводное сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-117">If the create or reconfigure operation for the resource pool or workload group fails, a summary error message appears below the title of the property page.</span></span> <span data-ttu-id="ae9b3-118">Чтобы просмотреть подробное сообщение об ошибке, щелкните стрелку вниз рядом с ним.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-118">To see a detailed error message, click the down arrow on the error message.</span></span>  
  
 <span data-ttu-id="ae9b3-119">Чтобы выяснить, находится ли конфигурация в состоянии ожидания, выполните запрос к динамическому административному представлению [sys.dm_resource_governor_configuration](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) , получив текущее состояние is_configuration_pending.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-119">You can determine whether there is a configuration pending by querying the [sys.dm_resource_governor_configuration](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) dynamic management view to get the current status of is_configuration_pending.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ae9b3-120">Permissions</span><span class="sxs-lookup"><span data-stu-id="ae9b3-120">Permissions</span></span>  
 <span data-ttu-id="ae9b3-121">Для просмотра свойств регулятора ресурсов требуется разрешение VIEW SERVER STATER.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-121">Viewing resource governor properties requires VIEW SERVER STATER permission.</span></span> <span data-ttu-id="ae9b3-122">Для задач настройки конфигурации регулятора ресурсов требуется разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-122">The resource governor configuration tasks require CONTROL SERVER permission.</span></span>  
  
##  <a name="view-the-resource-governor-properties-page"></a><a name="ViewRGProp"></a><span data-ttu-id="ae9b3-123">Просмотр страницы свойств Resource Governor</span><span class="sxs-lookup"><span data-stu-id="ae9b3-123">View the Resource Governor Properties Page</span></span>  
 <span data-ttu-id="ae9b3-124">**Просмотр свойств регулятора ресурсов на странице "Свойства регулятора ресурсов" в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="ae9b3-124">**To view resource governor properties by using the Resource Governor Properties page in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="ae9b3-125">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]откройте обозреватель объектов и рекурсивно разверните узел **Управление** вплоть до узла **Регулятор ресурсов**.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-125">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="ae9b3-126">Щелкните правой кнопкой мыши **Регулятор ресурсов** и выберите пункт **Свойства**, после чего откроется страница **Свойства регулятора ресурсов** .</span><span class="sxs-lookup"><span data-stu-id="ae9b3-126">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="ae9b3-127">Описания полей этой страницы см. в разделе [Свойства регулятора ресурсов](#RGProp).</span><span class="sxs-lookup"><span data-stu-id="ae9b3-127">For descriptions of the fields in the page, see [Resource Governor Properties](#RGProp).</span></span>  
  
4.  <span data-ttu-id="ae9b3-128">Чтобы сохранить изменения, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-128">To save any changes, click **OK**.</span></span>  
  
##  <a name="resource-governor-properties"></a><a name="RGProp"></a><span data-ttu-id="ae9b3-129">Свойства Resource Governor</span><span class="sxs-lookup"><span data-stu-id="ae9b3-129">Resource Governor Properties</span></span>  
 <span data-ttu-id="ae9b3-130">**Имя функции-классификатора**</span><span class="sxs-lookup"><span data-stu-id="ae9b3-130">**Classifier function name**</span></span>  
 <span data-ttu-id="ae9b3-131">Укажите функцию-классификатор, выбрав ее из списка.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-131">Specify the classifier function by selecting from the list.</span></span>  
  
 <span data-ttu-id="ae9b3-132">**Включение регулятора ресурсов**</span><span class="sxs-lookup"><span data-stu-id="ae9b3-132">**Enable Resource Governor**</span></span>  
 <span data-ttu-id="ae9b3-133">Включите или отключите регулятор ресурсов путем установки или снятия флажка.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-133">Enable or disable Resource Governor by selecting or clearing the check box.</span></span>  
  
 <span data-ttu-id="ae9b3-134">**Пулы ресурсов**</span><span class="sxs-lookup"><span data-stu-id="ae9b3-134">**Resource pools**</span></span>  
 <span data-ttu-id="ae9b3-135">Создайте или измените конфигурацию пула ресурсов в этой сетке.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-135">Create or change resource pool configuration by using the grid that is provided.</span></span> <span data-ttu-id="ae9b3-136">Сетка заполнена сведениями о стандартных внутренних пулах и пулах по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-136">This grid is populated with information for the predefined internal and default pools.</span></span> <span data-ttu-id="ae9b3-137">Выберите пул для работы, щелкнув первый столбец строки, содержащей имя пула.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-137">Select a pool to work with by clicking the first column in the row for the pool.</span></span> <span data-ttu-id="ae9b3-138">Чтобы создать пул ресурсов, щелкните строку, отмеченную символом "звездочка" ( **&#42;** ).</span><span class="sxs-lookup"><span data-stu-id="ae9b3-138">To create a new resource pool, click the row that is prefixed by the asterisk (**&#42;**).</span></span>  
  
 <span data-ttu-id="ae9b3-139">**имя**;</span><span class="sxs-lookup"><span data-stu-id="ae9b3-139">**Name**</span></span>  
 <span data-ttu-id="ae9b3-140">Укажите имя пула ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-140">Specify the name of the resource pool.</span></span>  
  
 <span data-ttu-id="ae9b3-141">**Минимальная пропускная способность ЦП, %**</span><span class="sxs-lookup"><span data-stu-id="ae9b3-141">**Minimum CPU %**</span></span>  
 <span data-ttu-id="ae9b3-142">Укажите гарантированную среднюю пропускную способность ЦП для всех запросов в пуле ресурсов при возникновении состязания использования ЦП.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-142">Specify the guaranteed average CPU bandwidth for all requests in the resource pool when there is CPU contention.</span></span> <span data-ttu-id="ae9b3-143">Диапазон от 0 до 100.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-143">Range is 0 to 100.</span></span>  
  
 <span data-ttu-id="ae9b3-144">**Максимальная пропускная способность ЦП, %**</span><span class="sxs-lookup"><span data-stu-id="ae9b3-144">**Maximum CPU %**</span></span>  
 <span data-ttu-id="ae9b3-145">Укажите максимальную среднюю пропускную способность ЦП для всех запросов в пуле ресурсов при возникновении состязания использования ЦП.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-145">Specify the maximum average CPU bandwidth that all requests in this resource pool will receive when there is CPU contention.</span></span> <span data-ttu-id="ae9b3-146">Диапазон от 0 до 100.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-146">Range is 0 to 100.</span></span> <span data-ttu-id="ae9b3-147">Значение по умолчанию — 100.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-147">The default setting is 100.</span></span>  
  
 <span data-ttu-id="ae9b3-148">**Минимальный объем памяти, %**</span><span class="sxs-lookup"><span data-stu-id="ae9b3-148">**Minimum Memory %**</span></span>  
 <span data-ttu-id="ae9b3-149">Укажите минимальный объем памяти, резервируемый для данного пула ресурсов, который не подлежит использованию совместно с другими пулами ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-149">Specify the minimum amount of memory reserved for this resource pool that can not be shared with other resource pools.</span></span> <span data-ttu-id="ae9b3-150">Диапазон от 0 до 100.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-150">Range is 0 to 100.</span></span>  
  
 <span data-ttu-id="ae9b3-151">**Максимальный объем памяти, %**</span><span class="sxs-lookup"><span data-stu-id="ae9b3-151">**Maximum Memory %**</span></span>  
 <span data-ttu-id="ae9b3-152">Укажите общий объем памяти сервера, который может использоваться для запросов в данном пуле ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-152">Specify the total server memory that can be used by requests in this resource pool.</span></span> <span data-ttu-id="ae9b3-153">Диапазон от 0 до 100.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-153">Range is 0 to 100.</span></span> <span data-ttu-id="ae9b3-154">Значение по умолчанию — 100.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-154">The default setting is 100.</span></span>  
  
 <span data-ttu-id="ae9b3-155">Дополнительные сведения см. в статье [Создание пула ресурсов &#40;&#41;Transact-SQL ](/sql/t-sql/statements/create-resource-pool-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ae9b3-155">For more information, see [CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql).</span></span>  
  
 <span data-ttu-id="ae9b3-156">**Группы рабочей нагрузки для пула ресурсов**</span><span class="sxs-lookup"><span data-stu-id="ae9b3-156">**Workload groups for resource pool**</span></span>  
 <span data-ttu-id="ae9b3-157">Создайте или измените конфигурацию группы рабочей нагрузки в этой сетке.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-157">Create or change the workload group configuration by using the grid that is provided.</span></span> <span data-ttu-id="ae9b3-158">Сетка заполнена сведениями о стандартных внутренних группах и группах по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-158">This grid is populated with information for the predefined internal and default groups.</span></span> <span data-ttu-id="ae9b3-159">Выберите группу для работы, щелкнув первый столбец строки, содержащей имя пула.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-159">Select a group to work with by clicking the first column in the row for the pool.</span></span> <span data-ttu-id="ae9b3-160">Чтобы создать группу рабочей нагрузки, щелкните строку, отмеченную символом "звездочка" ( **&#42;** ).</span><span class="sxs-lookup"><span data-stu-id="ae9b3-160">To create a new workload group, click the row that is prefixed by the asterisk (**&#42;**).</span></span>  
  
 <span data-ttu-id="ae9b3-161">**имя**;</span><span class="sxs-lookup"><span data-stu-id="ae9b3-161">**Name**</span></span>  
 <span data-ttu-id="ae9b3-162">Укажите имя группы рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-162">Specify the name of the workload group.</span></span>  
  
 <span data-ttu-id="ae9b3-163">**Важность**</span><span class="sxs-lookup"><span data-stu-id="ae9b3-163">**Importance**</span></span>  
 <span data-ttu-id="ae9b3-164">Укажите относительную важность запроса в группе рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-164">Specify the relative importance of a request in the workload group.</span></span> <span data-ttu-id="ae9b3-165">Доступны следующие значения: «Низкая», «Средняя» и «Высокая».</span><span class="sxs-lookup"><span data-stu-id="ae9b3-165">Available settings are Low, Medium, and High.</span></span>  
  
 <span data-ttu-id="ae9b3-166">**Максимальное число запросов**</span><span class="sxs-lookup"><span data-stu-id="ae9b3-166">**Maximum Requests**</span></span>  
 <span data-ttu-id="ae9b3-167">Укажите максимальное число запросов, одновременное выполнение которых разрешено в группе рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-167">Specify the maximum number of simultaneous requests that are allowed to execute in the workload group.</span></span> <span data-ttu-id="ae9b3-168">Должно быть 0 или положительным целым числом.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-168">Must be 0 or a positive integer.</span></span>  
  
 <span data-ttu-id="ae9b3-169">**Время ЦП (с)**</span><span class="sxs-lookup"><span data-stu-id="ae9b3-169">**CPU Time (sec)**</span></span>  
 <span data-ttu-id="ae9b3-170">Укажите максимальное время ЦП, которое может быть использовано запросом.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-170">Specify the maximum amount of CPU time that a request can use.</span></span> <span data-ttu-id="ae9b3-171">Должно быть 0 или положительным целым числом.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-171">Must be 0 or a positive integer.</span></span> <span data-ttu-id="ae9b3-172">Если задано значение 0, то время не ограничено.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-172">If 0, the time is unlimited.</span></span>  
  
 <span data-ttu-id="ae9b3-173">**Предоставление памяти, %**</span><span class="sxs-lookup"><span data-stu-id="ae9b3-173">**Memory Grant %**</span></span>  
 <span data-ttu-id="ae9b3-174">Укажите максимальный объем памяти, который может использоваться одним запросом из пула.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-174">Specify the maximum amount of memory that a single request can take from the pool.</span></span> <span data-ttu-id="ae9b3-175">Диапазон от 0 до 100.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-175">Range is 0 to 100.</span></span>  
  
 <span data-ttu-id="ae9b3-176">**Время ожидания предоставления (секунды)**</span><span class="sxs-lookup"><span data-stu-id="ae9b3-176">**Grant Time-out (sec)**</span></span>  
 <span data-ttu-id="ae9b3-177">Укажите максимальное количество времени, в течение которого запрос может ожидать освобождения ресурса, прежде чем завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-177">Specify the maximum time that a query can wait for a resource to become available before the query fails.</span></span> <span data-ttu-id="ae9b3-178">Должно быть 0 или положительным целым числом.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-178">Must be 0 or a positive integer.</span></span>  
  
 <span data-ttu-id="ae9b3-179">**Степень параллелизма**</span><span class="sxs-lookup"><span data-stu-id="ae9b3-179">**Degree of Parallelism**</span></span>  
 <span data-ttu-id="ae9b3-180">Укажите максимальную степень параллелизма (DOP) для параллельных запросов.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-180">Specify the maximum degree of parallelism (DOP) for parallel requests.</span></span> <span data-ttu-id="ae9b3-181">Диапазон от 0 до 64.</span><span class="sxs-lookup"><span data-stu-id="ae9b3-181">Range is 0 to 64.</span></span>  
  
 <span data-ttu-id="ae9b3-182">Дополнительные сведения см. в разделе [CREATE WORKLOAD GROUP (Transact-SQL)](/sql/t-sql/statements/create-workload-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ae9b3-182">For more information, see [CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql).</span></span>  
  
## <a name="view-resource-governor-properties-by-using-transact-sql"></a><span data-ttu-id="ae9b3-183">Просмотр свойств регулятора ресурсов с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ae9b3-183">View Resource Governor Properties by Using Transact-SQL</span></span>  
 <span data-ttu-id="ae9b3-184">**Просмотр свойств регулятора ресурсов с помощью Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ae9b3-184">**View resource governor properties by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="ae9b3-185">Для просмотра определений сущностей регулятора ресурсов используются [представления каталога регулятора ресурсов (Transact-SQL)](/sql/relational-databases/system-catalog-views/resource-governor-catalog-views-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ae9b3-185">To view the definitions of resource governor entities, use the [Resource Governor Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/resource-governor-catalog-views-transact-sql).</span></span>  
  
2.  <span data-ttu-id="ae9b3-186">Для просмотра текущей конфигурации сущностей регулятора ресурсов используются [динамические административные представления регулятора ресурсов (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/resource-governor-related-dynamic-management-views-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ae9b3-186">To view the current configuration of resource governor entities, use the [Resource Governor Related Dynamic Management Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/resource-governor-related-dynamic-management-views-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9b3-187">См. также:</span><span class="sxs-lookup"><span data-stu-id="ae9b3-187">See Also</span></span>  
 <span data-ttu-id="ae9b3-188">[регулятор ресурсов](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="ae9b3-188">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="ae9b3-189">[Активация регулятора ресурсов](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="ae9b3-189">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="ae9b3-190">[Пул ресурсов регулятора ресурсов](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="ae9b3-190">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="ae9b3-191">[Группа рабочей нагрузки регулятора ресурсов](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="ae9b3-191">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 [<span data-ttu-id="ae9b3-192">Функция-классификатор регулятора ресурсов</span><span class="sxs-lookup"><span data-stu-id="ae9b3-192">Resource Governor Classifier Function</span></span>](resource-governor-classifier-function.md)  
  
  
