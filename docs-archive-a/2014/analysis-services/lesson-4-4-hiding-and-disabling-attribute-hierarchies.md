---
title: Скрытие и отключение иерархий атрибутов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 095039c2-7104-414c-a9a6-327b03ce79df
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc043c68d2a83424a14707799fd90bf893abc12d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751531"
---
# <a name="hiding-and-disabling-attribute-hierarchies"></a><span data-ttu-id="9033c-102">Скрытие и отключение иерархий атрибутов</span><span class="sxs-lookup"><span data-stu-id="9033c-102">Hiding and Disabling Attribute Hierarchies</span></span>
  <span data-ttu-id="9033c-103">По умолчанию иерархия атрибута создается для каждого атрибута в измерении и каждая иерархия доступна для разделения данных фактов по измерениям.</span><span class="sxs-lookup"><span data-stu-id="9033c-103">By default, an attribute hierarchy is created for every attribute in a dimension, and each hierarchy is available for dimensioning fact data.</span></span> <span data-ttu-id="9033c-104">Эта иерархия состоит из уровня «Все» и уровня подробностей, содержащего все элементы иерархии.</span><span class="sxs-lookup"><span data-stu-id="9033c-104">This hierarchy consists of an "All" level and a detail level containing all members of the hierarchy.</span></span> <span data-ttu-id="9033c-105">Ранее рассматривался вопрос о том, что атрибуты можно организовывать в пользовательские иерархии для предоставления путей перемещения в кубе.</span><span class="sxs-lookup"><span data-stu-id="9033c-105">As you have already learned, you can organize attributes into user-defined hierarchies to provide navigation paths in a cube.</span></span> <span data-ttu-id="9033c-106">В определенных случаях может потребоваться отключить или скрыть некоторые атрибуты и их иерархии.</span><span class="sxs-lookup"><span data-stu-id="9033c-106">Under certain circumstances, you may want to disable or hide some attributes and their hierarchies.</span></span> <span data-ttu-id="9033c-107">Например, определенные атрибуты, такие как номера социального страхования или номера национальной принадлежности, ставки заработной платы, даты рождения и имена входа в систему не являются атрибутами, по которым пользователь будет организовывать измерения куба.</span><span class="sxs-lookup"><span data-stu-id="9033c-107">For example, certain attributes such as social security numbers or national identification numbers, pay rates, birth dates, and login information are not attributes by which users will dimension cube information.</span></span> <span data-ttu-id="9033c-108">Эти сведения обычно просматриваются только для справки по конкретному члену атрибута.</span><span class="sxs-lookup"><span data-stu-id="9033c-108">Instead, this information is generally only viewed as details of a particular attribute member.</span></span> <span data-ttu-id="9033c-109">Данные иерархии атрибутов может потребоваться скрыть, оставляя видимыми только сами атрибуты как свойства члена конкретного атрибута.</span><span class="sxs-lookup"><span data-stu-id="9033c-109">You may want to hide these attribute hierarchies, leaving the attributes visible only as member properties of a specific attribute.</span></span> <span data-ttu-id="9033c-110">Кроме того, может возникнуть необходимость сделать элементы других атрибутов, такие как имена заказчиков или почтовые индексы, видимыми только при просмотре через пользовательскую иерархию, а не независимо через иерархию атрибута.</span><span class="sxs-lookup"><span data-stu-id="9033c-110">You may also want to make members of other attributes, such as customer names or postal codes, visible only when they are viewed through a user hierarchy instead of independently through an attribute hierarchy.</span></span> <span data-ttu-id="9033c-111">Одной из причин для этого может быть большое число различающихся элементов в иерархии атрибута.</span><span class="sxs-lookup"><span data-stu-id="9033c-111">One reason to do so may be the sheer number of distinct members in the attribute hierarchy.</span></span> <span data-ttu-id="9033c-112">Наконец, чтобы увеличить производительность обработки, следует выключить иерархии атрибутов, которыми не будут пользоваться пользователи.</span><span class="sxs-lookup"><span data-stu-id="9033c-112">Finally, to improve processing performance, you should disable attribute hierarchies that users will not use for browsing.</span></span>

 <span data-ttu-id="9033c-113">Значение свойства **AttributeHierarchyEnabled** определяет, создана ли иерархия атрибута.</span><span class="sxs-lookup"><span data-stu-id="9033c-113">The value of the **AttributeHierarchyEnabled** property determines whether an attribute hierarchy is created.</span></span> <span data-ttu-id="9033c-114">Если значением свойства является **False**, иерархия атрибутов не создана и атрибут нельзя использовать в качестве уровня пользовательской иерархии, то есть иерархия атрибутов существует только как свойство элемента.</span><span class="sxs-lookup"><span data-stu-id="9033c-114">If this property is set to **False**, the attribute hierarchy is not created and the attribute cannot be used as a level in a user hierarchy; the attribute hierarchy exists as a member property only.</span></span> <span data-ttu-id="9033c-115">Однако отключенную иерархию атрибута можно использовать для сортировки элементов другого атрибута.</span><span class="sxs-lookup"><span data-stu-id="9033c-115">However, a disabled attribute hierarchy can still be used to order the members of another attribute.</span></span> <span data-ttu-id="9033c-116">Если значением свойства **AttributeHierarchyEnabled** является **True**, значение свойства **AttributeHierarchyVisible** определяет, является ли иерархия атрибута видимой независимо от пользовательской иерархии.</span><span class="sxs-lookup"><span data-stu-id="9033c-116">If the value of the **AttributeHierarchyEnabled** property is set to **True**, the value of the **AttributeHierarchyVisible** property determines whether the attribute hierarchy is visible independent of its use in a user-defined hierarchy.</span></span>

 <span data-ttu-id="9033c-117">Если иерархия атрибута включена, может возникнуть необходимость указать значения следующих трех дополнительных свойств.</span><span class="sxs-lookup"><span data-stu-id="9033c-117">When an attribute hierarchy is enabled, you may want to specify values for the following three additional properties:</span></span>

-   <span data-ttu-id="9033c-118">**IsAggregatable**</span><span class="sxs-lookup"><span data-stu-id="9033c-118">**IsAggregatable**</span></span>

     <span data-ttu-id="9033c-119">По умолчанию для всех иерархий атрибутов задается уровень «(Все)».</span><span class="sxs-lookup"><span data-stu-id="9033c-119">By default, an (All) level is defined for all attribute hierarchies.</span></span> <span data-ttu-id="9033c-120">Чтобы отключить уровень "(Все)" для включенной иерархии атрибутов, задайте для этого свойства значение **False**.</span><span class="sxs-lookup"><span data-stu-id="9033c-120">To disable the (All) level for an enabled attribute hierarchy, set the value for this property to **False**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="9033c-121">Атрибут, свойство **IsAggregatable** которого установлено в значение false, может использоваться только в качестве корневого элемента многоуровневой иерархии, и для него должен быть указан элемент по умолчанию (в противном случае элемент по умолчанию будет выбран ядром служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="9033c-121">An attribute that has its **IsAggregatable** property set to false can only be used as the root of a user-defined hierarchy and must have a default member specified (otherwise, one will be chosen for you by the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] engine).</span></span>

-   <span data-ttu-id="9033c-122">**AttributeHierarchyOrdered**</span><span class="sxs-lookup"><span data-stu-id="9033c-122">**AttributeHierarchyOrdered**</span></span>

     <span data-ttu-id="9033c-123">По умолчанию в службах [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] элементы включенных иерархий атрибутов сортируются при обработке, а затем сохраняются в зависимости от значения свойства **OrderBy** , например «Имя» или «Ключ».</span><span class="sxs-lookup"><span data-stu-id="9033c-123">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] orders the members of enabled attribute hierarchies during processing, and then stores the members by the value of the **OrderBy** property, such as by Name or Key.</span></span> <span data-ttu-id="9033c-124">Если сортировка не важна, производительность обработки можно повысить, указав для этого свойства значение **False**.</span><span class="sxs-lookup"><span data-stu-id="9033c-124">If you do not care about ordering, you can increase processing performance by setting the value of this property to **False**.</span></span>

-   <span data-ttu-id="9033c-125">**AttributeHierarchyOptimizedState**</span><span class="sxs-lookup"><span data-stu-id="9033c-125">**AttributeHierarchyOptimizedState**</span></span>

     <span data-ttu-id="9033c-126">По умолчанию в службах [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] создается индекс для каждой включенной иерархии атрибута при обработке, чтобы повысить производительность выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="9033c-126">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] creates an index for each enabled attribute hierarchy during processing, to improve query performance.</span></span> <span data-ttu-id="9033c-127">Если не планируется использовать иерархию атрибута для просмотра, можно повысить производительность обработки, задав в качестве значения этого свойства **NotOptimized**.</span><span class="sxs-lookup"><span data-stu-id="9033c-127">If you do not plan to use an attribute hierarchy for browsing, you can increase processing performance by setting the value of this property to **NotOptimized**.</span></span> <span data-ttu-id="9033c-128">Тем не менее, если скрытая иерархия используется в качестве ключевого атрибута измерения, создание индекса элементов атрибута позволит повысить производительность.</span><span class="sxs-lookup"><span data-stu-id="9033c-128">However, if you use a hidden hierarchy as the key attribute for the dimension, creating an index of the attribute members will still improve performance.</span></span>

 <span data-ttu-id="9033c-129">Эти свойства неприменимы, если иерархия атрибута отключена.</span><span class="sxs-lookup"><span data-stu-id="9033c-129">These properties do not apply if an attribute hierarchy is disabled.</span></span>

 <span data-ttu-id="9033c-130">В задачах этого раздела необходимо отключить номера социального страхования и другие атрибуты в измерении «Сотрудники», которые не будут использоваться для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9033c-130">In the tasks in this topic, you will disable social security numbers and other attributes in the Employee dimension that will not be used for browsing.</span></span> <span data-ttu-id="9033c-131">Затем предстоит скрыть иерархии атрибутов имени заказчика и почтового кода в измерении «Заказчик».</span><span class="sxs-lookup"><span data-stu-id="9033c-131">You will then hide the customer name and postal code attribute hierarchies in the Customer dimension.</span></span> <span data-ttu-id="9033c-132">Если у этих иерархий много элементов атрибутов, их просмотр будет достаточно медленным вне зависимости от пользовательской иерархии.</span><span class="sxs-lookup"><span data-stu-id="9033c-132">The large number of attribute members in these hierarchies will make browsing these hierarchies very slow independent of a user hierarchy.</span></span>

## <a name="setting-attribute-hierarchy-properties-in-the-employee-dimension"></a><span data-ttu-id="9033c-133">Определение свойств иерархии атрибута в измерении «Сотрудники»</span><span class="sxs-lookup"><span data-stu-id="9033c-133">Setting Attribute Hierarchy Properties in the Employee Dimension</span></span>

1.  <span data-ttu-id="9033c-134">Перейдите в конструктор измерений на измерение «Сотрудники» и откройте вкладку **Обозреватель** .</span><span class="sxs-lookup"><span data-stu-id="9033c-134">Switch to Dimension Designer for the Employee dimension, and then click the **Browser** tab.</span></span>

2.  <span data-ttu-id="9033c-135">Проверьте, включены ли в список **Иерархия** следующие иерархии атрибутов:</span><span class="sxs-lookup"><span data-stu-id="9033c-135">Verify that the following attribute hierarchies appear in the **Hierarchy** list:</span></span>

    -   <span data-ttu-id="9033c-136">**Базовая ставка**</span><span class="sxs-lookup"><span data-stu-id="9033c-136">**Base Rate**</span></span>

    -   <span data-ttu-id="9033c-137">**Дата рождения**</span><span class="sxs-lookup"><span data-stu-id="9033c-137">**Birth Date**</span></span>

    -   <span data-ttu-id="9033c-138">**Идентификатор входа**</span><span class="sxs-lookup"><span data-stu-id="9033c-138">**Login ID**</span></span>

    -   <span data-ttu-id="9033c-139">**ИНН менеджера**</span><span class="sxs-lookup"><span data-stu-id="9033c-139">**Manager SSN**</span></span>

    -   <span data-ttu-id="9033c-140">**SSN**</span><span class="sxs-lookup"><span data-stu-id="9033c-140">**SSN**</span></span>

3.  <span data-ttu-id="9033c-141">Перейдите на вкладку **Структура измерения** , а затем выберите следующие атрибуты на панели **Атрибуты** .</span><span class="sxs-lookup"><span data-stu-id="9033c-141">Switch to the **Dimension Structure** tab, and then select the following attributes in the **Attributes** pane.</span></span> <span data-ttu-id="9033c-142">Можно выбрать несколько мер. Для этого щелкните каждую из них, удерживая нажатой клавишу CTRL.</span><span class="sxs-lookup"><span data-stu-id="9033c-142">You can select multiple measures by clicking each while holding down the CTRL key:</span></span>

    -   <span data-ttu-id="9033c-143">**Базовая ставка**</span><span class="sxs-lookup"><span data-stu-id="9033c-143">**Base Rate**</span></span>

    -   <span data-ttu-id="9033c-144">**Дата рождения**</span><span class="sxs-lookup"><span data-stu-id="9033c-144">**Birth Date**</span></span>

    -   <span data-ttu-id="9033c-145">**Идентификатор входа**</span><span class="sxs-lookup"><span data-stu-id="9033c-145">**Login ID**</span></span>

    -   <span data-ttu-id="9033c-146">**ИНН менеджера**</span><span class="sxs-lookup"><span data-stu-id="9033c-146">**Manager SSN**</span></span>

    -   <span data-ttu-id="9033c-147">**SSN**</span><span class="sxs-lookup"><span data-stu-id="9033c-147">**SSN**</span></span>

4.  <span data-ttu-id="9033c-148">В окне свойств установите для свойства **AttributeHierarchyEnabled** выбранных атрибутов значение **False** .</span><span class="sxs-lookup"><span data-stu-id="9033c-148">In the Properties window, set the value of the **AttributeHierarchyEnabled** property to **False** for the selected attributes.</span></span>

     <span data-ttu-id="9033c-149">Обратите внимание, что на панели **Атрибуты** значок каждого из атрибута изменился и указывает, что этот атрибут отключен.</span><span class="sxs-lookup"><span data-stu-id="9033c-149">Notice in the **Attributes** pane that the icon for each attribute has changed to indicate that the attribute is not enabled.</span></span>

     <span data-ttu-id="9033c-150">На рисунке ниже показано, что для свойства **AttributeHierarchyEnabled** выбранных атрибутов установлено значение False.</span><span class="sxs-lookup"><span data-stu-id="9033c-150">The following image shows the **AttributeHierarchyEnabled** property set to False for the selected attributes.</span></span>

     <span data-ttu-id="9033c-151">![Значение False свойства AttributeHierarchyEnabled](../../2014/tutorials/media/l4-hierarchyenabled-1.gif "Значение False свойства AttributeHierarchyEnabled")</span><span class="sxs-lookup"><span data-stu-id="9033c-151">![AttributeHierarchyEnabled property set to False](../../2014/tutorials/media/l4-hierarchyenabled-1.gif "AttributeHierarchyEnabled property set to False")</span></span>

5.  <span data-ttu-id="9033c-152">В меню **Сборка** выберите команду **Развернуть Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="9033c-152">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>

6.  <span data-ttu-id="9033c-153">После успешного окончания обработки перейдите на вкладку **Обзор** , нажмите кнопку **Повторное соединение**и затем попытайтесь просмотреть измененные иерархии атрибутов.</span><span class="sxs-lookup"><span data-stu-id="9033c-153">When processing has successfully completed, switch to the **Browser** tab, click **Reconnect**, and then try to browse the modified attribute hierarchies.</span></span>

     <span data-ttu-id="9033c-154">Обратите внимание, что элементы измененных атрибутов недоступны для просмотра в качестве иерархий атрибутов в списке **Иерархия** .</span><span class="sxs-lookup"><span data-stu-id="9033c-154">Notice that the members of the modified attributes are not available for browsing as attribute hierarchies in the **Hierarchy** list.</span></span> <span data-ttu-id="9033c-155">При попытке добавления отключенной иерархии атрибута в качестве уровня пользовательской иерархии будет выведено сообщение об ошибке, уведомляющее о том, что для включения в пользовательскую иерархию необходимо активировать иерархию атрибута.</span><span class="sxs-lookup"><span data-stu-id="9033c-155">If you try to add one of the disabled attribute hierarchies as a level in a user hierarchy, you will receive an error notifying you that the attribute hierarchy must be enabled to participate in a user-defined hierarchy.</span></span>

## <a name="setting-attribute-hierarchy-properties-in-the-customer-dimension"></a><span data-ttu-id="9033c-156">Настройка свойств иерархии атрибута в измерении «Заказчик»</span><span class="sxs-lookup"><span data-stu-id="9033c-156">Setting Attribute Hierarchy Properties in the Customer Dimension</span></span>

1.  <span data-ttu-id="9033c-157">Перейдите в конструктор измерений на измерение «Заказчик» и откройте вкладку **Обозреватель** .</span><span class="sxs-lookup"><span data-stu-id="9033c-157">Switch to Dimension Designer for the Customer dimension, and then click the **Browser** tab.</span></span>

2.  <span data-ttu-id="9033c-158">Проверьте, включены ли в список **Иерархия** следующие иерархии атрибутов:</span><span class="sxs-lookup"><span data-stu-id="9033c-158">Verify that the following attribute hierarchies appear in the **Hierarchy** list:</span></span>

    -   <span data-ttu-id="9033c-159">**Полное имя**</span><span class="sxs-lookup"><span data-stu-id="9033c-159">**Full Name**</span></span>

    -   <span data-ttu-id="9033c-160">**Почтовый индекс**</span><span class="sxs-lookup"><span data-stu-id="9033c-160">**Postal Code**</span></span>

3.  <span data-ttu-id="9033c-161">Перейдите на вкладку **Структура измерения** и выберите следующие атрибуты на панели **Атрибуты** , удерживая нажатой клавишу CTRL, чтобы выделить несколько атрибутов одновременно:</span><span class="sxs-lookup"><span data-stu-id="9033c-161">Switch to the **Dimension Structure** tab, and then select the following attributes in the **Attributes** pane by using the CTRL key to select multiple attributes at the same time:</span></span>

    -   <span data-ttu-id="9033c-162">**Полное имя**</span><span class="sxs-lookup"><span data-stu-id="9033c-162">**Full Name**</span></span>

    -   <span data-ttu-id="9033c-163">**Почтовый индекс**</span><span class="sxs-lookup"><span data-stu-id="9033c-163">**Postal Code**</span></span>

4.  <span data-ttu-id="9033c-164">В окне свойств установите для свойства **AttributeHierarchyEnabled** выбранных атрибутов значение **False** .</span><span class="sxs-lookup"><span data-stu-id="9033c-164">In the Properties window, set the value of the **AttributeHierarchyVisible** property to **False** for the selected attributes.</span></span>

     <span data-ttu-id="9033c-165">Поскольку элементы этих иерархий атрибутов будут использоваться для разделения данных фактов по измерениям, их сортировка и оптимизация повысит производительность.</span><span class="sxs-lookup"><span data-stu-id="9033c-165">Because the members of these attribute hierarchies will be used for dimensioning fact data, ordering and optimizing the members of these attribute hierarchies will improve performance.</span></span> <span data-ttu-id="9033c-166">Таким образом, свойства этих атрибутов изменять не следует.</span><span class="sxs-lookup"><span data-stu-id="9033c-166">Therefore, the properties of these attributes should not be changed.</span></span>

     <span data-ttu-id="9033c-167">На рисунке ниже показано свойство **AttributeHierarchyVisible** , для которого установлено значение False.</span><span class="sxs-lookup"><span data-stu-id="9033c-167">The following image shows the **AttributeHierarchyVisible** property set to False.</span></span>

     <span data-ttu-id="9033c-168">![Значение False свойства AttributeHierarchyVisible](../../2014/tutorials/media/l4-hierarchyvisible-1.gif "Значение False свойства AttributeHierarchyVisible")</span><span class="sxs-lookup"><span data-stu-id="9033c-168">![AttributeHierarchyVisible property set to False](../../2014/tutorials/media/l4-hierarchyvisible-1.gif "AttributeHierarchyVisible property set to False")</span></span>

5.  <span data-ttu-id="9033c-169">Перетащите атрибут **Почтовый индекс** с панели **Атрибуты** в пользовательскую иерархию **География заказчика** панели **Иерархии и уровни** непосредственно под уровень **Город** .</span><span class="sxs-lookup"><span data-stu-id="9033c-169">Drag the **Postal Code** attribute from the **Attributes** pane into the **Customer Geography** user hierarchy in the **Hierarchies and Levels** pane, immediately under the **City** level.</span></span>

     <span data-ttu-id="9033c-170">Обратите внимание, что скрытый атрибут по-прежнему может быть уровнем пользовательской иерархии.</span><span class="sxs-lookup"><span data-stu-id="9033c-170">Notice that a hidden attribute can still become a level in a user hierarchy.</span></span>

6.  <span data-ttu-id="9033c-171">В меню **Сборка** выберите команду **Развернуть Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="9033c-171">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>

7.  <span data-ttu-id="9033c-172">После успешного окончания развертывания перейдите на вкладку **Браузер** измерения «Заказчик» и нажмите кнопку **Повторное соединение**.</span><span class="sxs-lookup"><span data-stu-id="9033c-172">When deployment has successfully completed, switch to the **Browser** tab for the Customer dimension, and then click **Reconnect**.</span></span>

8.  <span data-ttu-id="9033c-173">Попробуйте выбрать одну из измененных иерархий атрибутов в списке **Иерархия** .</span><span class="sxs-lookup"><span data-stu-id="9033c-173">Try to select either of the modified attribute hierarchies from the **Hierarchy** list.</span></span>

     <span data-ttu-id="9033c-174">Обратите внимание, что ни одна из измененных иерархий атрибутов не отображается в списке **Иерархия** .</span><span class="sxs-lookup"><span data-stu-id="9033c-174">Notice that neither of the modified attribute hierarchies appears in the **Hierarchy** list.</span></span>

9. <span data-ttu-id="9033c-175">В списке **Иерархия** выберите значение **География заказчика**и просмотрите каждый из уровней на панели браузера.</span><span class="sxs-lookup"><span data-stu-id="9033c-175">In the **Hierarchy** list, select **Customer Geography**, and then browse each level in the browser pane.</span></span>

     <span data-ttu-id="9033c-176">Обратите внимание на то, что скрытые уровни **Почтовый индекс** и **Полное имя**видны в пользовательской иерархии.</span><span class="sxs-lookup"><span data-stu-id="9033c-176">Notice that the hidden levels, **Postal Code** and **Full Name**, are visible in the user-defined hierarchy.</span></span>

## <a name="next-task-in-lesson"></a><span data-ttu-id="9033c-177">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="9033c-177">Next Task in Lesson</span></span>
 [<span data-ttu-id="9033c-178">Сортировка элементов атрибута по вторичному атрибуту</span><span class="sxs-lookup"><span data-stu-id="9033c-178">Sorting Attribute Members Based on a Secondary Attribute</span></span>](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md)


