---
title: Действия в многомерных моделях | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- actions [Analysis Services], creating
- report actions [Analysis Services]
- drillthrough actions [Analysis Services]
- cubes [Analysis Services], actions
ms.assetid: b9fee2b9-05a5-4077-848d-d8457326dc27
author: minewiskan
ms.author: owend
ms.openlocfilehash: ce42907190363be085e8f4d8e9adfbab52a70590
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658473"
---
# <a name="actions-in-multidimensional-models"></a><span data-ttu-id="bb2c6-102">Действия в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="bb2c6-102">Actions in Multidimensional Models</span></span>
  <span data-ttu-id="bb2c6-103">Действие представляет собой инициированную пользователем операцию для выбранного куба или его части.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-103">An action is an end user-initiated operation upon a selected cube or portion of a cube.</span></span> <span data-ttu-id="bb2c6-104">Эта операция может запускать приложение, для которого в качестве параметра используется выбранный элемент, или получать сведения о выбранном элементе.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-104">The operation can start an application with the selected item as a parameter, or it can retrieve information about the selected item.</span></span> <span data-ttu-id="bb2c6-105">Дополнительные сведения о действиях см. в разделе [Действия (службы Analysis Services — многомерные данные)](actions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="bb2c6-105">For more information about actions, see [Actions &#40;Analysis Services - Multidimensional Data&#41;](actions-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="bb2c6-106">Для построения действий для куба используется вкладка **Действия** конструктора кубов.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-106">Use the **Actions** tab of Cube Designer to build actions for a cube.</span></span> <span data-ttu-id="bb2c6-107">Укажите следующее.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-107">Specify the following:</span></span>  
  
 <span data-ttu-id="bb2c6-108">**имя**;</span><span class="sxs-lookup"><span data-stu-id="bb2c6-108">**Name**</span></span>  
 <span data-ttu-id="bb2c6-109">Выберите имя для идентификации действия.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-109">Select a name that identifies the action.</span></span>  
  
 <span data-ttu-id="bb2c6-110">**Цель действия**</span><span class="sxs-lookup"><span data-stu-id="bb2c6-110">**Action Target**</span></span>  
 <span data-ttu-id="bb2c6-111">Выберите объект, с которым необходимо связать действие.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-111">Select the object to which the action is attached.</span></span> <span data-ttu-id="bb2c6-112">Обычно в клиентских приложениях действие отображается, когда конечные пользователи выбирают целевой объект. Однако клиентское приложение определяет, какая из операций конечного пользователя отображает действия.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-112">Generally, in client applications, the action is displayed when end users select the target object; however, the client application determines which end-user operation displays actions.</span></span> <span data-ttu-id="bb2c6-113">В качестве значения для параметра **Целевой тип**выберите следующие объекты:</span><span class="sxs-lookup"><span data-stu-id="bb2c6-113">For **Target type**, select from the following objects:</span></span>  
  
-   <span data-ttu-id="bb2c6-114">Элементы атрибута</span><span class="sxs-lookup"><span data-stu-id="bb2c6-114">Attribute members</span></span>  
  
-   <span data-ttu-id="bb2c6-115">Ячейки</span><span class="sxs-lookup"><span data-stu-id="bb2c6-115">Cells</span></span>  
  
-   <span data-ttu-id="bb2c6-116">Куб</span><span class="sxs-lookup"><span data-stu-id="bb2c6-116">Cube</span></span>  
  
-   <span data-ttu-id="bb2c6-117">Элементы измерения</span><span class="sxs-lookup"><span data-stu-id="bb2c6-117">Dimension members</span></span>  
  
-   <span data-ttu-id="bb2c6-118">Иерархия</span><span class="sxs-lookup"><span data-stu-id="bb2c6-118">Hierarchy</span></span>  
  
-   <span data-ttu-id="bb2c6-119">Элементы иерархии</span><span class="sxs-lookup"><span data-stu-id="bb2c6-119">Hierarchy members</span></span>  
  
-   <span data-ttu-id="bb2c6-120">Level</span><span class="sxs-lookup"><span data-stu-id="bb2c6-120">Level</span></span>  
  
-   <span data-ttu-id="bb2c6-121">Элементы уровня</span><span class="sxs-lookup"><span data-stu-id="bb2c6-121">Level members</span></span>  
  
 <span data-ttu-id="bb2c6-122">После выбора в разделе **Целевой объект**целевого типа объекта выберите объект куба назначенного типа.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-122">After you select the target object type, under **Target object**, select the cube object of the designated type.</span></span>  
  
 <span data-ttu-id="bb2c6-123">**Условие (необязательно)**</span><span class="sxs-lookup"><span data-stu-id="bb2c6-123">**Condition (Optional)**</span></span>  
 <span data-ttu-id="bb2c6-124">Укажите необязательное многомерное выражение, результатом которого является логическое значение.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-124">Specify an optional Multidimensional Expressions (MDX) expression that resolves to a Boolean value.</span></span> <span data-ttu-id="bb2c6-125">Если значение равно `True`, то действие выполняется на заданной цели.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-125">If the value is `True`, the action is performed on the specified target.</span></span> <span data-ttu-id="bb2c6-126">Если значение равно `False`, то действие не выполняется.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-126">If the value is `False`, the action is not performed.</span></span>  
  
 <span data-ttu-id="bb2c6-127">**Содержимое действия**</span><span class="sxs-lookup"><span data-stu-id="bb2c6-127">**Action Content**</span></span>  
 <span data-ttu-id="bb2c6-128">Выберите тип действия.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-128">Select the type of action.</span></span> <span data-ttu-id="bb2c6-129">Следующая таблица содержит сводку возможных типов.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-129">The following table summarizes the available types.</span></span>  
  
|<span data-ttu-id="bb2c6-130">Type</span><span class="sxs-lookup"><span data-stu-id="bb2c6-130">Type</span></span>|<span data-ttu-id="bb2c6-131">Описание</span><span class="sxs-lookup"><span data-stu-id="bb2c6-131">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="bb2c6-132">Набор данных</span><span class="sxs-lookup"><span data-stu-id="bb2c6-132">Data Set</span></span>|<span data-ttu-id="bb2c6-133">Извлекает набор данных.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-133">Retrieves a dataset.</span></span>|  
|<span data-ttu-id="bb2c6-134">Частный</span><span class="sxs-lookup"><span data-stu-id="bb2c6-134">Proprietary</span></span>|<span data-ttu-id="bb2c6-135">Выполняет операцию с использованием интерфейса, отличного от приведенных в данной таблице.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-135">Performs an operation by using an interface other than those listed in this table.</span></span>|  
|<span data-ttu-id="bb2c6-136">Набор строк</span><span class="sxs-lookup"><span data-stu-id="bb2c6-136">Row Set</span></span>|<span data-ttu-id="bb2c6-137">Извлекает набор строк.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-137">Retrieves a rowset.</span></span>|  
|<span data-ttu-id="bb2c6-138">Оператор</span><span class="sxs-lookup"><span data-stu-id="bb2c6-138">Statement</span></span>|<span data-ttu-id="bb2c6-139">Выполняет команду OLE DB.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-139">Runs an OLE DB command.</span></span>|  
|<span data-ttu-id="bb2c6-140">URL-адрес</span><span class="sxs-lookup"><span data-stu-id="bb2c6-140">URL</span></span>|<span data-ttu-id="bb2c6-141">Отображает страницу переменных в интернет-браузере.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-141">Displays a variable page in an Internet browser.</span></span>|  
  
 <span data-ttu-id="bb2c6-142">Для параметра **Выражение действия**задайте параметры, передаваемые во время выполнения действия.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-142">For **Action Expression**, specify the parameters that are passed when the action is run.</span></span> <span data-ttu-id="bb2c6-143">Синтаксис должен преобразовываться в строку и необходимо включить выражение, написанное на языке многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-143">The syntax must evaluate to a string, and you must include an expression written in MDX.</span></span> <span data-ttu-id="bb2c6-144">Например, выбранное многомерное выражение может указывать часть куба, включенную в синтаксис.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-144">For example, your MDX expression can indicate a part of the cube that is included in the syntax.</span></span> <span data-ttu-id="bb2c6-145">Многомерные выражения вычисляются до передачи параметров.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-145">MDX expressions are evaluated before the parameters are passed.</span></span> <span data-ttu-id="bb2c6-146">Также для построения многомерных выражений прилагается построитель многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-146">Also, MDX Builder is available to help you build MDX expressions.</span></span>  
  
 <span data-ttu-id="bb2c6-147">**Дополнительные свойства**</span><span class="sxs-lookup"><span data-stu-id="bb2c6-147">**Additional Properties**</span></span>  
 <span data-ttu-id="bb2c6-148">Выберите свойство.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-148">Select the property.</span></span> <span data-ttu-id="bb2c6-149">Следующая таблица содержит сводку возможных свойств.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-149">The following table summarizes the available properties.</span></span>  
  
|<span data-ttu-id="bb2c6-150">Свойство</span><span class="sxs-lookup"><span data-stu-id="bb2c6-150">Property</span></span>|<span data-ttu-id="bb2c6-151">Описание</span><span class="sxs-lookup"><span data-stu-id="bb2c6-151">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="bb2c6-152">**Вызов**</span><span class="sxs-lookup"><span data-stu-id="bb2c6-152">**Invocation**</span></span>|<span data-ttu-id="bb2c6-153">Указывает способ запуска действия.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-153">Specifies how the action is run.</span></span> <span data-ttu-id="bb2c6-154">Интерактивный способ, заданный по умолчанию, указывает на то, что действие будет запущено при открытии пользователем объекта.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-154">Interactive, the default, specifies that the action is run when a user accesses an object.</span></span> <span data-ttu-id="bb2c6-155">Допустимые параметры:</span><span class="sxs-lookup"><span data-stu-id="bb2c6-155">The possible settings are:</span></span><br /><br /> <span data-ttu-id="bb2c6-156">Пакетная служба</span><span class="sxs-lookup"><span data-stu-id="bb2c6-156">Batch</span></span><br /><br /> <span data-ttu-id="bb2c6-157">Интерактивно</span><span class="sxs-lookup"><span data-stu-id="bb2c6-157">Interactive</span></span><br /><br /> <span data-ttu-id="bb2c6-158">При открытии</span><span class="sxs-lookup"><span data-stu-id="bb2c6-158">On Open</span></span>|  
|<span data-ttu-id="bb2c6-159">**Приложение**</span><span class="sxs-lookup"><span data-stu-id="bb2c6-159">**Application**</span></span>|<span data-ttu-id="bb2c6-160">Описывает приложение действия.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-160">Describes the application of the action.</span></span>|  
|<span data-ttu-id="bb2c6-161">**Описание**</span><span class="sxs-lookup"><span data-stu-id="bb2c6-161">**Description**</span></span>|<span data-ttu-id="bb2c6-162">Описывает действие.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-162">Describes the action.</span></span>|  
|<span data-ttu-id="bb2c6-163">**Caption**</span><span class="sxs-lookup"><span data-stu-id="bb2c6-163">**Caption**</span></span>|<span data-ttu-id="bb2c6-164">Указывает заголовок, отображаемый для действия.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-164">Provides a caption that is displayed for the action.</span></span> <span data-ttu-id="bb2c6-165">Если заголовок является многомерным выражением, укажите `True` для **заголовка значение MDX**.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-165">If the caption is MDX, specify `True` for **Caption is MDX**.</span></span>|  
|<span data-ttu-id="bb2c6-166">**Заголовок является многомерным выражением**</span><span class="sxs-lookup"><span data-stu-id="bb2c6-166">**Caption is MDX**</span></span>|<span data-ttu-id="bb2c6-167">Укажите значение `True`, если заголовок является многомерным выражением, а в обратном случае — значение `False`.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-167">Specify `True` if the caption is MDX or `False` if it is not.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="bb2c6-168">Определение действий типов «HTML» и «Командная строка» производится на языке сценариев служб анализа данных (ASSL) или с помощью объектов AMO.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-168">You must use Analysis Services Scripting Language (ASSL) or Analysis Management Objects (AMO) to define HTML and Command Line action types.</span></span> <span data-ttu-id="bb2c6-169">Дополнительные сведения см. в разделах [Элемент Action (ASSL)](https://docs.microsoft.com/bi-reference/assl/objects/action-element-assl), [Элемент Type (Action) (ASSL)](https://docs.microsoft.com/bi-reference/assl/properties/type-element-action-assl) и [Программирование расширенных объектов AMO OLAP](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-advanced-objects).</span><span class="sxs-lookup"><span data-stu-id="bb2c6-169">For more information, see [Action Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/objects/action-element-assl), [Type Element &#40;Action&#41; &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/type-element-action-assl), and [Programming AMO OLAP Advanced Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-advanced-objects).</span></span>  
  
## <a name="creating-a-reporting-action"></a><span data-ttu-id="bb2c6-170">Создание действия «Построение отчета»</span><span class="sxs-lookup"><span data-stu-id="bb2c6-170">Creating a Reporting Action</span></span>  
 <span data-ttu-id="bb2c6-171">Сервер отчетов отвечает на запросы с URL-адресами для отчетов.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-171">The report server responds to URL-based requests for reports.</span></span> <span data-ttu-id="bb2c6-172">Чтобы создать действие построения отчета, выберите в меню **Куб** пункт **Создать действие с отчетами**.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-172">To create a reporting action, on the **Cube** menu, click **New Reporting Action**.</span></span> <span data-ttu-id="bb2c6-173">Для действия отчета доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-173">The following options are specific to a reporting action.</span></span>  
  
 <span data-ttu-id="bb2c6-174">**Сервер отчетов**</span><span class="sxs-lookup"><span data-stu-id="bb2c6-174">**Report Server**</span></span>  
 <span data-ttu-id="bb2c6-175">Свойства, описанные в следующей таблице, указываются для сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-175">The properties described in the following table are specified for the report server.</span></span>  
  
|<span data-ttu-id="bb2c6-176">Свойство</span><span class="sxs-lookup"><span data-stu-id="bb2c6-176">Property</span></span>|<span data-ttu-id="bb2c6-177">Описание</span><span class="sxs-lookup"><span data-stu-id="bb2c6-177">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="bb2c6-178">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="bb2c6-178">**Server name**</span></span>|<span data-ttu-id="bb2c6-179">Имя компьютера, на котором запущен сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-179">The name of the computer running report server.</span></span>|  
|<span data-ttu-id="bb2c6-180">**Путь сервера**</span><span class="sxs-lookup"><span data-stu-id="bb2c6-180">**Server path**</span></span>|<span data-ttu-id="bb2c6-181">Путь, предоставленный сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-181">The path exposed by report server.</span></span>|  
|<span data-ttu-id="bb2c6-182">**Формат отчета**</span><span class="sxs-lookup"><span data-stu-id="bb2c6-182">**Report format**</span></span>|<span data-ttu-id="bb2c6-183">HTML5, HTML3, Excel или PDF.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-183">HTML5, HTML3, Excel, or PDF.</span></span>|  
  
 <span data-ttu-id="bb2c6-184">**Параметры (необязательно)**</span><span class="sxs-lookup"><span data-stu-id="bb2c6-184">**Parameters (Optional)**</span></span>  
 <span data-ttu-id="bb2c6-185">Параметры отправляются на сервер в составе строки URL-адреса во время создания действия.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-185">The parameters are sent to the server as part of the URL string when the action is created.</span></span> <span data-ttu-id="bb2c6-186">В них включены **Имя параметра** и **Значение параметра**, представляющее собой многомерное выражение.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-186">They include **Parameter Name** and **Parameter Value**, which is an MDX expression.</span></span>  
  
 <span data-ttu-id="bb2c6-187">URL-адрес сервера отчетов формируется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bb2c6-187">The report server URL is constructed as follows:</span></span>  
  
```  
  
http://  
host  
/  
virtualdirectory  
/Path&  
parametername1  
=  
parametervalue1  
& ...  
```  
  
 <span data-ttu-id="bb2c6-188">Пример:</span><span class="sxs-lookup"><span data-stu-id="bb2c6-188">For example:</span></span>  
  
```  
http://localhost/ReportServer/Sales/YearlySalesByCategory?rs:Command=Render&Region=West  
```  
  
## <a name="creating-a-drillthrough-action"></a><span data-ttu-id="bb2c6-189">Создание действия детализации</span><span class="sxs-lookup"><span data-stu-id="bb2c6-189">Creating a Drillthrough Action</span></span>  
 <span data-ttu-id="bb2c6-190">Действие детализации задается действием набора строк, возвращаемым клиентскому приложению в виде инструкции детализации.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-190">A drillthrough action is defined by a rowset action, which is returned to the client application as a drillthrough statement.</span></span> <span data-ttu-id="bb2c6-191">Цель действия является элементом группы мер.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-191">The action target is a member of a measure group.</span></span> <span data-ttu-id="bb2c6-192">Чтобы создать действие детализации, выберите в меню **Куб** пункт **Создать действие детализации**.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-192">To create a new drillthrough action, on the **Cube** menu, click **New Drillthrough Action**.</span></span> <span data-ttu-id="bb2c6-193">Для действия детализации доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="bb2c6-193">The following options are specific to a drillthrough action:</span></span>  
  
 <span data-ttu-id="bb2c6-194">**Столбцы детализации**</span><span class="sxs-lookup"><span data-stu-id="bb2c6-194">**Drillthrough Columns**</span></span>  
 <span data-ttu-id="bb2c6-195">Выберите одно или несколько измерений и столбцы детализации для каждого измерения, возвращенные клиентскому приложению действием.</span><span class="sxs-lookup"><span data-stu-id="bb2c6-195">Select one or more dimensions and, for each dimension, the drillthrough columns returned to the client application by the action.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb2c6-196">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb2c6-196">See Also</span></span>  
 [<span data-ttu-id="bb2c6-197">Кубы в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="bb2c6-197">Cubes in Multidimensional Models</span></span>](cubes-in-multidimensional-models.md)  
  
  
