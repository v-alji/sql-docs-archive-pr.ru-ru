---
title: Автоматическое формирование значений атрибута, отличного от Code (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: b82f6f81-6e9c-4918-9ea9-4ab5f5d11b15
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8db6c89bdce2a11a5a54ed3a763a7bc41bd7f1be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667267"
---
# <a name="automatically-generate-attribute-values-other-than-code-master-data-services"></a><span data-ttu-id="4948a-102">Автоматическое формирование значений атрибута отличного от Code (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="4948a-102">Automatically Generate Attribute Values Other Than Code (Master Data Services)</span></span>
  <span data-ttu-id="4948a-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] значения для атрибутов сущности можно формировать автоматически, если каждый раз при применении бизнес-правил необходимо автоматически задавать целое число в качестве значения.</span><span class="sxs-lookup"><span data-stu-id="4948a-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], automatically generate values for an entity's attribute values when you want an integer to be automatically assigned as the value each time business rules are applied.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4948a-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="4948a-104">Prerequisites</span></span>  
 <span data-ttu-id="4948a-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="4948a-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="4948a-106">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="4948a-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="4948a-107">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="4948a-107">You must be a model administrator.</span></span> <span data-ttu-id="4948a-108">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4948a-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="4948a-109">Должен существовать числовой атрибут.</span><span class="sxs-lookup"><span data-stu-id="4948a-109">A numeric attribute must exist.</span></span> <span data-ttu-id="4948a-110">Дополнительные сведения см. в разделе [Создание числового атрибута (службы Master Data Services)](../../2014/master-data-services/create-a-numeric-attribute-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4948a-110">For more information, see [Create a Numeric Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-numeric-attribute-master-data-services.md).</span></span>  
  
### <a name="to-automatically-generate-an-attribute-value"></a><span data-ttu-id="4948a-111">Автоматическое формирование значений атрибута</span><span class="sxs-lookup"><span data-stu-id="4948a-111">To automatically generate an attribute value</span></span>  
  
1.  <span data-ttu-id="4948a-112">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="4948a-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="4948a-113">В строке меню выберите **Управление** и щелкните **Бизнес-правила**.</span><span class="sxs-lookup"><span data-stu-id="4948a-113">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="4948a-114">На странице **Обслуживание бизнес-правил** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="4948a-114">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="4948a-115">Выберите сущность из списка **Сущность** .</span><span class="sxs-lookup"><span data-stu-id="4948a-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="4948a-116">В списке **Тип элемента** выберите тип элемента, к которому будет применяться бизнес-правило.</span><span class="sxs-lookup"><span data-stu-id="4948a-116">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="4948a-117">В списке **Атрибут** оставьте **Все**по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4948a-117">From the **Attribute** list, leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="4948a-118">Нажмите **Добавить бизнес-правило**.</span><span class="sxs-lookup"><span data-stu-id="4948a-118">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="4948a-119">Нажмите **Изменить выбранное бизнес-правило**.</span><span class="sxs-lookup"><span data-stu-id="4948a-119">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="4948a-120">На панели **Компоненты** разверните узел **Действия** .</span><span class="sxs-lookup"><span data-stu-id="4948a-120">In the **Components** pane, expand the **Actions** node.</span></span>  
  
10. <span data-ttu-id="4948a-121">В узле "Значение по умолчанию" щелкните **По умолчанию имеет сформированное значение** и перетащите его на значок **Действия** панели **ТО**.</span><span class="sxs-lookup"><span data-stu-id="4948a-121">In the Default Value node, click **defaults to a generated value** and drag it to the **THEN** pane's **Actions** label.</span></span>  
  
11. <span data-ttu-id="4948a-122">На панели **Атрибуты** щелкните атрибут со значением, которое необходимо сформировать, и перетащите его на значок **Выбор атрибута** панели **Изменение действия** .</span><span class="sxs-lookup"><span data-stu-id="4948a-122">In the **Attributes** pane, click the attribute with the value you want to generated and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
12. <span data-ttu-id="4948a-123">Введите значения в поля **Начать с** и **Приращение** .</span><span class="sxs-lookup"><span data-stu-id="4948a-123">Type a value in the **Start with** and **Increment by** boxes.</span></span> <span data-ttu-id="4948a-124">Если элемент уже существует, то значение будет установлено, исходя из наибольшего существующего значения.</span><span class="sxs-lookup"><span data-stu-id="4948a-124">If members already exist, the value will be set based on the highest existing value.</span></span> <span data-ttu-id="4948a-125">Например, если наибольшее существующее значение равно 299, а в поле **Приращение** установлено значение **1**, то следующее значение элемента будет равно 300.</span><span class="sxs-lookup"><span data-stu-id="4948a-125">For example, if the highest existing value is 299 and you set **Increment by** to **1**, the next member's value will be set to 300.</span></span>  
  
13. <span data-ttu-id="4948a-126">На панели **Изменение действия** нажмите кнопку **Сохранить элемент**.</span><span class="sxs-lookup"><span data-stu-id="4948a-126">In the **Edit Action** pane, click **Save item**.</span></span>  
  
14. <span data-ttu-id="4948a-127">Нажмите кнопку **Назад**.</span><span class="sxs-lookup"><span data-stu-id="4948a-127">Click **Back**.</span></span>  
  
15. <span data-ttu-id="4948a-128">По желанию на странице **Обслуживание бизнес-правил** дважды щелкните ячейку столбца **Имя**, **Описание**или **Уведомление** , чтобы обновить значение.</span><span class="sxs-lookup"><span data-stu-id="4948a-128">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
16. <span data-ttu-id="4948a-129">Нажмите кнопку **Опубликовать бизнес-правила**.</span><span class="sxs-lookup"><span data-stu-id="4948a-129">Click **Publish business rules**.</span></span>  
  
17. <span data-ttu-id="4948a-130">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4948a-130">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="4948a-131">Состояние правила изменится на **Активно**.</span><span class="sxs-lookup"><span data-stu-id="4948a-131">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4948a-132">Next Steps</span><span class="sxs-lookup"><span data-stu-id="4948a-132">Next Steps</span></span>  
  
-   [<span data-ttu-id="4948a-133">Подтверждение конкретных членов, обнаруженных при проверке на соответствие бизнес-правилам (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="4948a-133">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="4948a-134">Подтверждение исправления проблемы, обнаруженной при проверке на соответствие бизнес-правилам (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="4948a-134">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="4948a-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="4948a-135">See Also</span></span>  
 <span data-ttu-id="4948a-136">[Автоматическое создание кода &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4948a-136">[Automatic Code Creation &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span></span>  
 <span data-ttu-id="4948a-137">[Бизнес-правила &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4948a-137">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="4948a-138">Проверка (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="4948a-138">Validation &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validation-master-data-services.md)  
  
  
