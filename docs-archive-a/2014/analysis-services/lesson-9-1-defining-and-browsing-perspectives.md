---
title: Определение и просмотр перспектив | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 766004b9-6578-4914-a445-6f44843a5fb0
author: minewiskan
ms.author: owend
ms.openlocfilehash: c9658098180618c2d5d6d6d9e00e7a7e4a6c4231
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734549"
---
# <a name="defining-and-browsing-perspectives"></a><span data-ttu-id="47603-102">Определение и поиск перспектив</span><span class="sxs-lookup"><span data-stu-id="47603-102">Defining and Browsing Perspectives</span></span>
  <span data-ttu-id="47603-103">Перспектива может упростить вид куба для определенных целей.</span><span class="sxs-lookup"><span data-stu-id="47603-103">A perspective can simplify the view of a cube for specific purposes.</span></span> <span data-ttu-id="47603-104">По умолчанию пользователям доступны для просмотра все элементы куба, на которые они имеют разрешения.</span><span class="sxs-lookup"><span data-stu-id="47603-104">By default, users can see all of the elements in a cube to which they have permissions.</span></span> <span data-ttu-id="47603-105">Все элементы, которые видит пользователь при просмотре всего куба служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , называются перспективой по умолчанию для куба.</span><span class="sxs-lookup"><span data-stu-id="47603-105">What users are viewing when they view an entire [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube is the default perspective for the cube.</span></span> <span data-ttu-id="47603-106">Представление полного куба может оказаться слишком сложным для перемещений, особенно для тех пользователей, которым для решения задач, связанных с бизнес-аналитикой и отчетностью, достаточно доступа лишь к малой его части.</span><span class="sxs-lookup"><span data-stu-id="47603-106">A view of the whole cube can be very complex for users to navigate, especially for users who only need to interact with a small part of the cube to satisfy their business intelligence and reporting requirements.</span></span>  
  
 <span data-ttu-id="47603-107">Чтобы упростить излишне сложный куб, можно создать его отображаемые подмножества, называемые *перспективами*, которые отражают лишь небольшую часть групп мер, мер, измерений, атрибутов, иерархий, ключевых показателей эффективности, операций и вычисляемых элементов этого куба.</span><span class="sxs-lookup"><span data-stu-id="47603-107">To reduce the apparent complexity of a cube, you can create viewable subsets of the cube, called *perspectives*, which show users only a part of the measure groups, measures, dimensions, attributes, hierarchies, Key Performance Indicators (KPIs), actions, and calculated members in the cube.</span></span> <span data-ttu-id="47603-108">Это может оказаться полезным для работы с клиентскими приложениями, написанных для предыдущей версии служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47603-108">This can be particularly useful for working with client applications that were written for a previous release of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="47603-109">Эти клиенты не имеют концепции, например папок отображения или перспектив, но перспектива рассматривается клиентами прошлых версий как куб.</span><span class="sxs-lookup"><span data-stu-id="47603-109">These clients have no concept of display folders or perspectives, for example, but a perspective appears to older clients as if it were a cube.</span></span> <span data-ttu-id="47603-110">Дополнительные сведения см. в разделах [Перспективы](multidimensional-models-olap-logical-cube-objects/perspectives.md)и [Перспективы в многомерных моделях](multidimensional-models/perspectives-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="47603-110">For more information, see [Perspectives](multidimensional-models-olap-logical-cube-objects/perspectives.md), and [Perspectives in Multidimensional Models](multidimensional-models/perspectives-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="47603-111">Перспектива не является механизмом безопасности, она призвана повысить удобство работы пользователя.</span><span class="sxs-lookup"><span data-stu-id="47603-111">A perspective is not a security mechanism, but instead is a tool for providing a better user experience.</span></span> <span data-ttu-id="47603-112">Все параметры безопасности перспективы наследуются из базового куба.</span><span class="sxs-lookup"><span data-stu-id="47603-112">All security for a perspective is inherited from the underlying cube.</span></span>  
  
 <span data-ttu-id="47603-113">В задачах этого раздела будет определено несколько разных перспектив, в которых затем будет просмотрен куб.</span><span class="sxs-lookup"><span data-stu-id="47603-113">In the tasks in this topic, you will define several different perspectives and then browse the cube through each of these new perspectives.</span></span>  
  
## <a name="defining-an-internet-sales-perspective"></a><span data-ttu-id="47603-114">Определение перспективы Internet Sales</span><span class="sxs-lookup"><span data-stu-id="47603-114">Defining an Internet Sales Perspective</span></span>  
  
1.  <span data-ttu-id="47603-115">Откройте конструктор кубов для куба "Учебник по службам [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] " и перейдите на вкладку **Перспективы** .</span><span class="sxs-lookup"><span data-stu-id="47603-115">Open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Perspectives** tab.</span></span>  
  
     <span data-ttu-id="47603-116">Все объекты и их типы отображаются на панели **Перспективы** , как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="47603-116">All the objects and their object types appear in the **Perspectives** pane, as shown in the following image.</span></span>  
  
     <span data-ttu-id="47603-117">![Панель «Перспективы» конструктора кубов](../../2014/tutorials/media/l9-perspectives-1.gif "Панель «Перспективы» конструктора кубов")</span><span class="sxs-lookup"><span data-stu-id="47603-117">![Perspectives pane of Cube Designer](../../2014/tutorials/media/l9-perspectives-1.gif "Perspectives pane of Cube Designer")</span></span>  
  
2.  <span data-ttu-id="47603-118">На панели инструментов вкладки **Перспективы** нажмите кнопку **Создать перспективу** .</span><span class="sxs-lookup"><span data-stu-id="47603-118">On the toolbar of the **Perspectives** tab, click the **New Perspective** button.</span></span>  
  
     <span data-ttu-id="47603-119">Новая перспектива появится в столбце **Имя перспективы** с заданным по умолчанию именем **Перспектива**, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="47603-119">A new perspective appears in the **Perspective Name** column with a default name of **Perspective**, as shown in the following image.</span></span> <span data-ttu-id="47603-120">Обратите внимание, что для каждого из объектов установлен флажок. Пока не снят флажок для одного из объектов, перспектива будет идентична заданной по умолчанию перспективе данного куба.</span><span class="sxs-lookup"><span data-stu-id="47603-120">Notice that the check box for every object is selected; until you clear the check box for an object, this perspective is identical to the default perspective of this cube.</span></span>  
  
     <span data-ttu-id="47603-121">![Новая перспектива в столбце «Имя перспективы»](../../2014/tutorials/media/l9-perspectives-2.gif "Новая перспектива в столбце «Имя перспективы»")</span><span class="sxs-lookup"><span data-stu-id="47603-121">![New perspective in Perspective Name column](../../2014/tutorials/media/l9-perspectives-2.gif "New perspective in Perspective Name column")</span></span>  
  
3.  <span data-ttu-id="47603-122">Измените имя перспективы на `Internet Sales` .</span><span class="sxs-lookup"><span data-stu-id="47603-122">Change the perspective name to `Internet Sales`.</span></span>  
  
4.  <span data-ttu-id="47603-123">В следующей строке задайте для свойства DefaultMeasure значение **Продажи через Интернет — объем продаж**.</span><span class="sxs-lookup"><span data-stu-id="47603-123">On the next row, set the DefaultMeasure to **Internet Sales-Sales Amount**.</span></span>  
  
     <span data-ttu-id="47603-124">При просмотре куба с помощью этой перспективы будет видна именно эта мера, если не будет выбрана другая.</span><span class="sxs-lookup"><span data-stu-id="47603-124">When users browse the cube by using this perspective, this will be the measure that the users see unless they specify some other measure.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="47603-125">В окне свойств на вкладке [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Структура куба **можно также указать меру по умолчанию для всего куба учебника по службам** .</span><span class="sxs-lookup"><span data-stu-id="47603-125">You can also set the default measure for the whole [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube in the Properties window on the **Cube Structure** tab for the cube.</span></span>  
  
5.  <span data-ttu-id="47603-126">Снимите флажки для следующих объектов:</span><span class="sxs-lookup"><span data-stu-id="47603-126">Clear the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="47603-127">`Reseller Sales`Группа мер</span><span class="sxs-lookup"><span data-stu-id="47603-127">`Reseller Sales` measure group</span></span>  
  
    -   <span data-ttu-id="47603-128">группа мер**Квоты продаж** ;</span><span class="sxs-lookup"><span data-stu-id="47603-128">**Sales Quotas** measure group</span></span>  
  
    -   <span data-ttu-id="47603-129">группа мер**Квоты продаж 1** ;</span><span class="sxs-lookup"><span data-stu-id="47603-129">**Sales Quotas 1** measure group</span></span>  
  
    -   <span data-ttu-id="47603-130">измерение куба**Торговый посредник** ;</span><span class="sxs-lookup"><span data-stu-id="47603-130">**Reseller** cube dimension</span></span>  
  
    -   <span data-ttu-id="47603-131">измерение куба**География торгового посредника** ;</span><span class="sxs-lookup"><span data-stu-id="47603-131">**Reseller Geography** cube dimension</span></span>  
  
    -   <span data-ttu-id="47603-132">измерение куба**Территория продаж** ;</span><span class="sxs-lookup"><span data-stu-id="47603-132">**Sales Territory** cube dimension</span></span>  
  
    -   <span data-ttu-id="47603-133">измерение куба**Сотрудник** ;</span><span class="sxs-lookup"><span data-stu-id="47603-133">**Employee** cube dimension</span></span>  
  
    -   <span data-ttu-id="47603-134">измерение куба**Продвижение** ;</span><span class="sxs-lookup"><span data-stu-id="47603-134">**Promotion** cube dimension</span></span>  
  
    -   <span data-ttu-id="47603-135">ключевой показатель эффективности**Доход от продаж через торгового посредника** ;</span><span class="sxs-lookup"><span data-stu-id="47603-135">**Reseller Revenue** KPI</span></span>  
  
    -   <span data-ttu-id="47603-136">именованный набор**Крупные торговые посредники** ;</span><span class="sxs-lookup"><span data-stu-id="47603-136">**Large Resellers** named set</span></span>  
  
    -   <span data-ttu-id="47603-137">вычисляемый элемент**Итоговая сумма продаж** ;</span><span class="sxs-lookup"><span data-stu-id="47603-137">**Total Sales Amount** calculated member</span></span>  
  
    -   <span data-ttu-id="47603-138">вычисляемый элемент**Общая стоимость товара** ;</span><span class="sxs-lookup"><span data-stu-id="47603-138">**Total Product Cost** calculated member</span></span>  
  
    -   <span data-ttu-id="47603-139">вычисляемый элемент**Коэффициент валовой прибыли торгового посредника** ;</span><span class="sxs-lookup"><span data-stu-id="47603-139">**Reseller GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="47603-140">вычисляемый элемент**Итоговый коэффициент валовой прибыли** ;</span><span class="sxs-lookup"><span data-stu-id="47603-140">**Total GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="47603-141">вычисляемый элемент**Доля продаж через торгового посредника по всей номенклатуре продукции** ;</span><span class="sxs-lookup"><span data-stu-id="47603-141">**Reseller Sales Ratio to All Products** calculated member</span></span>  
  
    -   <span data-ttu-id="47603-142">вычисляемый элемент**Общая доля продаж по всей номенклатуре продукции** .</span><span class="sxs-lookup"><span data-stu-id="47603-142">**Total Sales Ratio to All Products** calculated member</span></span>  
  
     <span data-ttu-id="47603-143">Эти объекты не связаны с продажами через Интернет.</span><span class="sxs-lookup"><span data-stu-id="47603-143">These objects do not relate to Internet sales.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="47603-144">В каждом из измерений отдельно можно выбрать пользовательские иерархии и атрибуты, которые должны отображаться в данной перспективе.</span><span class="sxs-lookup"><span data-stu-id="47603-144">Within each dimension, you can also individually select the user-defined hierarchies and attributes that you want to appear in a perspective.</span></span>  
  
## <a name="defining-a-reseller-sales-perspective"></a><span data-ttu-id="47603-145">Определение перспективы Reseller Sales</span><span class="sxs-lookup"><span data-stu-id="47603-145">Defining a Reseller Sales Perspective</span></span>  
  
1.  <span data-ttu-id="47603-146">На панели инструментов вкладки **Перспективы** нажмите кнопку **Создать перспективу** .</span><span class="sxs-lookup"><span data-stu-id="47603-146">On the toolbar of the **Perspectives** tab, click the **New Perspective** button.</span></span>  
  
2.  <span data-ttu-id="47603-147">Измените имя новой перспективы на `Reseller Sales` .</span><span class="sxs-lookup"><span data-stu-id="47603-147">Change the name of the new perspective to `Reseller Sales`.</span></span>  
  
3.  <span data-ttu-id="47603-148">Установите меру **Товарооборот посредников — объем продаж** в качестве меры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="47603-148">Set **Reseller Sales-Sales Amount** as the default measure.</span></span>  
  
     <span data-ttu-id="47603-149">Если пользователи выполняют просмотр куба при помощи этой перспективы, они будут видеть именно эту меру, если не выберут другую.</span><span class="sxs-lookup"><span data-stu-id="47603-149">When users browse the cube by using this perspective, this measure will be the measure that the users will see unless they specify some other measure.</span></span>  
  
4.  <span data-ttu-id="47603-150">Снимите флажки для следующих объектов:</span><span class="sxs-lookup"><span data-stu-id="47603-150">Clear the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="47603-151">`Internet Sales`Группа мер</span><span class="sxs-lookup"><span data-stu-id="47603-151">`Internet Sales` measure group</span></span>  
  
    -   <span data-ttu-id="47603-152">группа мер**Причина покупки через Интернет** ;</span><span class="sxs-lookup"><span data-stu-id="47603-152">**Internet Sales Reason** measure group</span></span>  
  
    -   <span data-ttu-id="47603-153">измерение куба**Заказчик** ;</span><span class="sxs-lookup"><span data-stu-id="47603-153">**Customer** cube dimension</span></span>  
  
    -   <span data-ttu-id="47603-154">измерение куба**Подробности заказа через Интернет** ;</span><span class="sxs-lookup"><span data-stu-id="47603-154">**Internet Sales Order Details** cube dimension</span></span>  
  
    -   <span data-ttu-id="47603-155">измерение куба**Причина покупки** ;</span><span class="sxs-lookup"><span data-stu-id="47603-155">**Sales Reason** cube dimension</span></span>  
  
    -   <span data-ttu-id="47603-156">действие детализации**Действие детализации продаж через Интернет** ;</span><span class="sxs-lookup"><span data-stu-id="47603-156">**Internet Sales Details Drillthrough Action** drillthrough action</span></span>  
  
    -   <span data-ttu-id="47603-157">вычисляемый элемент**Итоговая сумма продаж** ;</span><span class="sxs-lookup"><span data-stu-id="47603-157">**Total Sales Amount** calculated member</span></span>  
  
    -   <span data-ttu-id="47603-158">вычисляемый элемент**Общая стоимость товара** ;</span><span class="sxs-lookup"><span data-stu-id="47603-158">**Total Product Cost** calculated member</span></span>  
  
    -   <span data-ttu-id="47603-159">вычисляемый элемент**Коэффициент валовой прибыли от продаж через Интернет** ;</span><span class="sxs-lookup"><span data-stu-id="47603-159">**Internet GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="47603-160">вычисляемый элемент**Итоговый коэффициент валовой прибыли** ;</span><span class="sxs-lookup"><span data-stu-id="47603-160">**Total GPM** calculated member</span></span>  
  
    -   <span data-ttu-id="47603-161">вычисляемый элемент**Доля продаж через Интернет по всей номенклатуре продукции** ;</span><span class="sxs-lookup"><span data-stu-id="47603-161">**Internet Sales Ratio to All Products** calculated member</span></span>  
  
    -   <span data-ttu-id="47603-162">вычисляемый элемент**Общая доля продаж по всей номенклатуре продукции** .</span><span class="sxs-lookup"><span data-stu-id="47603-162">**Total Sales Ratio to All Products** calculated member</span></span>  
  
     <span data-ttu-id="47603-163">Эти объекты не связаны с продажами через торгового посредника.</span><span class="sxs-lookup"><span data-stu-id="47603-163">These objects do not relate to resellers sales.</span></span>  
  
## <a name="defining-a-sales-summary-perspective"></a><span data-ttu-id="47603-164">Определение перспективы сводки о продажах</span><span class="sxs-lookup"><span data-stu-id="47603-164">Defining a Sales Summary Perspective</span></span>  
  
1.  <span data-ttu-id="47603-165">На панели инструментов вкладки **Перспективы** нажмите кнопку **Создать перспективу** .</span><span class="sxs-lookup"><span data-stu-id="47603-165">On the toolbar of the **Perspectives** tab, click the **New Perspective** button.</span></span>  
  
2.  <span data-ttu-id="47603-166">Измените имя новой перспективы на `Sales Summary` .</span><span class="sxs-lookup"><span data-stu-id="47603-166">Change the name of the new perspective to `Sales Summary`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="47603-167">Нельзя указывать вычисляемую меру как меру по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="47603-167">You cannot specify a calculated measure as the default measure.</span></span>  
  
3.  <span data-ttu-id="47603-168">Снимите флажки для следующих объектов:</span><span class="sxs-lookup"><span data-stu-id="47603-168">Clear the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="47603-169">`Internet Sales`Группа мер</span><span class="sxs-lookup"><span data-stu-id="47603-169">`Internet Sales` measure group</span></span>  
  
    -   <span data-ttu-id="47603-170">`Reseller Sales`Группа мер</span><span class="sxs-lookup"><span data-stu-id="47603-170">`Reseller Sales` measure group</span></span>  
  
    -   <span data-ttu-id="47603-171">группа мер**Причина покупки через Интернет** ;</span><span class="sxs-lookup"><span data-stu-id="47603-171">**Internet Sales Reason** measure group</span></span>  
  
    -   <span data-ttu-id="47603-172">группа мер**Квоты продаж** ;</span><span class="sxs-lookup"><span data-stu-id="47603-172">**Sales Quotas** measure group</span></span>  
  
    -   <span data-ttu-id="47603-173">группа мер**Квоты продаж 1** ;</span><span class="sxs-lookup"><span data-stu-id="47603-173">**Sales Quotas1** measure group</span></span>  
  
    -   <span data-ttu-id="47603-174">измерение куба**Подробности заказа через Интернет** ;</span><span class="sxs-lookup"><span data-stu-id="47603-174">**Internet Sales Order Details** cube dimension</span></span>  
  
    -   <span data-ttu-id="47603-175">измерение куба**Причина покупки** ;</span><span class="sxs-lookup"><span data-stu-id="47603-175">**Sales Reason** cube dimension</span></span>  
  
    -   <span data-ttu-id="47603-176">действие детализации**Действие детализации продаж через Интернет** ;</span><span class="sxs-lookup"><span data-stu-id="47603-176">**Internet Sales Details Drillthrough Action** drillthrough action</span></span>  
  
4.  <span data-ttu-id="47603-177">Установите флажки для следующих объектов:</span><span class="sxs-lookup"><span data-stu-id="47603-177">Select the check box for the following objects:</span></span>  
  
    -   <span data-ttu-id="47603-178">мера**Число продаж через Интернет** ;</span><span class="sxs-lookup"><span data-stu-id="47603-178">**Internet Sales Count** measure</span></span>  
  
    -   <span data-ttu-id="47603-179">мера**Число продаж через торговых посредников** .</span><span class="sxs-lookup"><span data-stu-id="47603-179">**Reseller Sales Count** measure</span></span>  
  
## <a name="browsing-the-cube-through-each-perspective"></a><span data-ttu-id="47603-180">Просмотр куба в каждой из перспектив</span><span class="sxs-lookup"><span data-stu-id="47603-180">Browsing the Cube Through Each Perspective</span></span>  
  
1.  <span data-ttu-id="47603-181">В меню **Сборка** выберите команду **Развернуть Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="47603-181">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="47603-182">После успешного завершения развертывания перейдите на вкладку **Браузер** и нажмите кнопку **Повторное соединение** .</span><span class="sxs-lookup"><span data-stu-id="47603-182">When deployment has successfully completed, switch to the **Browser** tab, and then click the **Reconnect** button.</span></span>  
  
3.  <span data-ttu-id="47603-183">Запустите Excel.</span><span class="sxs-lookup"><span data-stu-id="47603-183">Start Excel.</span></span>  
  
4.  <span data-ttu-id="47603-184">При выполнении команды «Анализ в Excel» выводится запрос выбора перспективы, которая будет использоваться при просмотре модели в Excel, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="47603-184">Analyze in Excel prompts you to choose which perspective to use when browsing the model in Excel, as shown in the following image.</span></span>  
  
     <span data-ttu-id="47603-185">![Объекты перспективы «Продажи через Интернет»](../../2014/tutorials/media/l9-perspectives-3.gif "Объекты перспективы «Продажи через Интернет»")</span><span class="sxs-lookup"><span data-stu-id="47603-185">![Objects for the Internet Sales perspective](../../2014/tutorials/media/l9-perspectives-3.gif "Objects for the Internet Sales perspective")</span></span>  
  
5.  <span data-ttu-id="47603-186">Кроме того, можно запустить Excel из меню «Пуск» Windows, определить подключение к базе данных учебника по службам Analysis Services на узле localhost и выбрать перспективу в мастере подключения к данным, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="47603-186">Alternatively, you can start Excel from the Windows Start menu, define a connection to the Analysis Services Tutorial database on localhost, and choose a perspective in the Data Connection wizard, as shown in the following image.</span></span>  
  
     <span data-ttu-id="47603-187">![Мастер подключения к данным в Excel](../../2014/tutorials/media/l9-perspectives-3b.gif "Мастер подключения к данным в Excel")</span><span class="sxs-lookup"><span data-stu-id="47603-187">![Data Connection wizard in Excel](../../2014/tutorials/media/l9-perspectives-3b.gif "Data Connection wizard in Excel")</span></span>  
  
6.  <span data-ttu-id="47603-188">Выберите `Internet Sales` в списке **Перспектива** , а затем просмотрите меры и измерения на панели Метаданные.</span><span class="sxs-lookup"><span data-stu-id="47603-188">Select `Internet Sales` in the **Perspective** list and then review the measures and dimensions in the metadata pane.</span></span>  
  
     <span data-ttu-id="47603-189">Обратите внимание, что отображаются только те объекты, которые определены для перспективы «Internet Sales».</span><span class="sxs-lookup"><span data-stu-id="47603-189">Notice that only those objects that are specified for the Internet Sales perspective appear.</span></span>  
  
7.  <span data-ttu-id="47603-190">На панели "Метаданные" разверните узел **Меры**.</span><span class="sxs-lookup"><span data-stu-id="47603-190">In the metadata pane, expand **Measures**.</span></span>  
  
     <span data-ttu-id="47603-191">Обратите внимание, что `Internet Sales` отображается только группа мер, а также отношение **товарооборота через Интернет** и **продажи через Интернет ко всем** вычисляемым элементам продукты.</span><span class="sxs-lookup"><span data-stu-id="47603-191">Notice that only the `Internet Sales` measure group appears, together with the **Internet GPM** and **Internet Sales Ratio to All Products** calculated members.</span></span>  
  
8.  <span data-ttu-id="47603-192">В модели снова выберите Excel.</span><span class="sxs-lookup"><span data-stu-id="47603-192">In the model, select Excel again.</span></span> <span data-ttu-id="47603-193">Выберите `Sales Summary`.</span><span class="sxs-lookup"><span data-stu-id="47603-193">Select `Sales Summary`.</span></span>  
  
     <span data-ttu-id="47603-194">Обратите внимание, что в каждой из этих групп мер отображается лишь одна мера, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="47603-194">Notice that in each of these measure groups, only a single measure appears, as shown in the following image.</span></span>  
  
     <span data-ttu-id="47603-195">![Меры «Продажи через Интернет» и «Продажи через посредников»](../../2014/tutorials/media/l9-perspectives-4.gif "Меры «Продажи через Интернет» и «Продажи через посредников»")</span><span class="sxs-lookup"><span data-stu-id="47603-195">![Internet Sales and Reseller Sales measures](../../2014/tutorials/media/l9-perspectives-4.gif "Internet Sales and Reseller Sales measures")</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="47603-196">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="47603-196">Next Task in Lesson</span></span>  
 [<span data-ttu-id="47603-197">Определение и просмотр переводов</span><span class="sxs-lookup"><span data-stu-id="47603-197">Defining and Browsing Translations</span></span>](lesson-9-2-defining-and-browsing-translations.md)  
  
## <a name="see-also"></a><span data-ttu-id="47603-198">См. также:</span><span class="sxs-lookup"><span data-stu-id="47603-198">See Also</span></span>  
 <span data-ttu-id="47603-199">[Перспективы](multidimensional-models-olap-logical-cube-objects/perspectives.md) </span><span class="sxs-lookup"><span data-stu-id="47603-199">[Perspectives](multidimensional-models-olap-logical-cube-objects/perspectives.md) </span></span>  
 [<span data-ttu-id="47603-200">Перспективы в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="47603-200">Perspectives in Multidimensional Models</span></span>](multidimensional-models/perspectives-in-multidimensional-models.md)  
  
  
