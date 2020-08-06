---
title: Инициирование действия на основе изменений значения атрибута (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], tracking attribute changes
- change tracking groups [Master Data Services], initiating actions
ms.assetid: 5e4402ce-31db-4774-a2a1-552335f87693
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 50931b9f9c4bd5d08596d485ba695143b9c6594e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729553"
---
# <a name="initiate-actions-based-on-attribute-value-changes-master-data-services"></a><span data-ttu-id="92315-102">Инициирование действия на основе значения атрибута (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="92315-102">Initiate Actions Based on Attribute Value Changes (Master Data Services)</span></span>
  <span data-ttu-id="92315-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]для инициации действий на основе значения атрибута создаются бизнес-правила.</span><span class="sxs-lookup"><span data-stu-id="92315-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a business rule to initiate actions based on changes to attribute values.</span></span> <span data-ttu-id="92315-104">Например, когда значение определенного атрибута изменяется, может потребоваться изменить значение, отправить уведомление или запустить внешний рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="92315-104">For example, when a specific attribute value changes, you may want to change a value, send a notification, or start an external workflow.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="92315-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="92315-105">Prerequisites</span></span>  
 <span data-ttu-id="92315-106">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="92315-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="92315-107">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="92315-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="92315-108">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="92315-108">You must be a model administrator.</span></span> <span data-ttu-id="92315-109">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="92315-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="92315-110">Атрибуты должны быть в группе отслеживания изменений.</span><span class="sxs-lookup"><span data-stu-id="92315-110">Your attributes must be in a change tracking group.</span></span> <span data-ttu-id="92315-111">Дополнительные сведения см. в разделе [Добавление атрибутов в группу отслеживания изменений (службы Master Data Services)](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) .</span><span class="sxs-lookup"><span data-stu-id="92315-111">See [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) for more information.</span></span>  
  
### <a name="to-create-a-business-rule-to-initiate-actions-based-on-attribute-value-changes"></a><span data-ttu-id="92315-112">Создание бизнес-правила для инициации действий на основе значения атрибута</span><span class="sxs-lookup"><span data-stu-id="92315-112">To create a business rule to initiate actions based on attribute value changes</span></span>  
  
1.  <span data-ttu-id="92315-113">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="92315-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="92315-114">В строке меню выберите **Управление** и щелкните **Бизнес-правила**.</span><span class="sxs-lookup"><span data-stu-id="92315-114">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="92315-115">На странице **Обслуживание бизнес-правил** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="92315-115">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="92315-116">Выберите сущность из списка **Сущность** .</span><span class="sxs-lookup"><span data-stu-id="92315-116">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="92315-117">В списке **Тип элемента** выберите тип элемента, к которому будет применяться бизнес-правило.</span><span class="sxs-lookup"><span data-stu-id="92315-117">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="92315-118">Выберите из списка **Атрибут** атрибут или оставьте **Все**по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="92315-118">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="92315-119">Нажмите **Добавить бизнес-правило**.</span><span class="sxs-lookup"><span data-stu-id="92315-119">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="92315-120">Нажмите **Изменить выбранное бизнес-правило**.</span><span class="sxs-lookup"><span data-stu-id="92315-120">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="92315-121">На панели **Компоненты** разверните узел **Условия** .</span><span class="sxs-lookup"><span data-stu-id="92315-121">In the **Components** pane, expand the **Conditions** node.</span></span>  
  
10. <span data-ttu-id="92315-122">В узле **Сравнение значений** перетащите **изменено** на значок **Условия** панели **IF** .</span><span class="sxs-lookup"><span data-stu-id="92315-122">Under the **Value comparison** node, drag **has changed** to the **IF** pane's **Conditions** label.</span></span>  
  
11. <span data-ttu-id="92315-123">На панели **атрибуты** щелкните атрибут и перетащите его на значок **Выбор атрибута** в области **изменить условие** .</span><span class="sxs-lookup"><span data-stu-id="92315-123">In the **Attributes** pane, click an attribute and drag it to the **Edit Condition** pane's **Select attribute** label.</span></span> <span data-ttu-id="92315-124">Атрибут не влияет на правило, так что можно выбрать любой из доступных атрибутов.</span><span class="sxs-lookup"><span data-stu-id="92315-124">This attribute has no effect on the rule, so select any available attribute.</span></span>  
  
12. <span data-ttu-id="92315-125">На панели **Изменение условия** в поле **Группа отслеживания изменений** введите номер группы отслеживания изменений, назначенный в рамках предварительных условий.</span><span class="sxs-lookup"><span data-stu-id="92315-125">In the **Edit Condition** pane, in the **Change tracking group** box, type the number of the change tracking group that you assigned as part of the prerequisites.</span></span>  
  
13. <span data-ttu-id="92315-126">На панели **Изменение условия** нажмите кнопку **Сохранить элемент**.</span><span class="sxs-lookup"><span data-stu-id="92315-126">In the **Edit Condition** pane, click **Save item**.</span></span>  
  
14. <span data-ttu-id="92315-127">На панели **Компоненты** разверните узел **Действия** .</span><span class="sxs-lookup"><span data-stu-id="92315-127">In the **Components** pane, expand the **Actions** node.</span></span>  
  
15. <span data-ttu-id="92315-128">Перетащите действие на значок **Действие** панели **THEN** .</span><span class="sxs-lookup"><span data-stu-id="92315-128">Click an action and drag it to the **THEN** pane's **Action** label.</span></span>  
  
16. <span data-ttu-id="92315-129">На панели **Атрибуты** щелкните атрибут и перетащите его на значок **Выбор атрибута** панели **Изменение действия** .</span><span class="sxs-lookup"><span data-stu-id="92315-129">In the **Attributes** pane, click an attribute and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
17. <span data-ttu-id="92315-130">На панели **Изменение действия** заполните все необходимые поля.</span><span class="sxs-lookup"><span data-stu-id="92315-130">In the **Edit Action** pane, complete any required fields.</span></span>  
  
18. <span data-ttu-id="92315-131">На панели **Изменение действия** нажмите кнопку **Сохранить элемент**.</span><span class="sxs-lookup"><span data-stu-id="92315-131">In the **Edit Action** pane, click **Save item**.</span></span>  
  
19. <span data-ttu-id="92315-132">Нажмите кнопку **Назад**.</span><span class="sxs-lookup"><span data-stu-id="92315-132">Click **Back**.</span></span>  
  
20. <span data-ttu-id="92315-133">По желанию на странице **Обслуживание бизнес-правил** дважды щелкните ячейку столбца **Имя**, **Описание**или **Уведомление** , чтобы обновить значение.</span><span class="sxs-lookup"><span data-stu-id="92315-133">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="92315-134">Уведомления отправляются только для правил, включающих действие по проверке.</span><span class="sxs-lookup"><span data-stu-id="92315-134">Notifications are sent only for rules that include a validation action.</span></span>  
  
21. <span data-ttu-id="92315-135">Нажмите кнопку **Опубликовать бизнес-правила**.</span><span class="sxs-lookup"><span data-stu-id="92315-135">Click **Publish business rules**.</span></span>  
  
22. <span data-ttu-id="92315-136">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="92315-136">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="92315-137">Состояние правила изменится на **Активно**.</span><span class="sxs-lookup"><span data-stu-id="92315-137">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="92315-138">Next Steps</span><span class="sxs-lookup"><span data-stu-id="92315-138">Next Steps</span></span>  
  
-   <span data-ttu-id="92315-139">Примените бизнес-правила к данным с помощью одной из следующих процедур:</span><span class="sxs-lookup"><span data-stu-id="92315-139">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="92315-140">Подтверждение конкретных членов, обнаруженных при проверке на соответствие бизнес-правилам (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="92315-140">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="92315-141">Подтверждение исправления проблемы, обнаруженной при проверке на соответствие бизнес-правилам (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="92315-141">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="92315-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="92315-142">See Also</span></span>  
 <span data-ttu-id="92315-143">[Добавление атрибутов в группу Отслеживание изменений &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="92315-143">[Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) </span></span>  
 [<span data-ttu-id="92315-144">Бизнес-правила (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="92315-144">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
