---
title: Создание и публикация бизнес-правила (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], creating
- creating business rules [Master Data Services]
ms.assetid: 6961d636-4d69-468e-81f7-8d0be6a4a039
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4dfca5613a1f328e02b3fd2c7337885a23889207
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667259"
---
# <a name="create-and-publish-a-business-rule-master-data-services"></a><span data-ttu-id="61eb8-102">Создание и публикация бизнес-правила (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="61eb8-102">Create and Publish a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="61eb8-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]бизнес-правило создается для гарантии точности основных данных.</span><span class="sxs-lookup"><span data-stu-id="61eb8-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a business rule to ensure the accuracy of your master data.</span></span> <span data-ttu-id="61eb8-104">Чтобы применить к данным созданное правило, его необходимо опубликовать.</span><span class="sxs-lookup"><span data-stu-id="61eb8-104">After you create a rule, you must publish it before you can apply it to data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="61eb8-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="61eb8-105">Prerequisites</span></span>  
 <span data-ttu-id="61eb8-106">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="61eb8-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="61eb8-107">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="61eb8-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="61eb8-108">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="61eb8-108">You must be a model administrator.</span></span> <span data-ttu-id="61eb8-109">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="61eb8-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-and-publish-a-business-rule"></a><span data-ttu-id="61eb8-110">Создание и публикация бизнес-правила</span><span class="sxs-lookup"><span data-stu-id="61eb8-110">To create and publish a business rule</span></span>  
  
1.  <span data-ttu-id="61eb8-111">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="61eb8-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="61eb8-112">В строке меню выберите **Управление** и щелкните **Бизнес-правила**.</span><span class="sxs-lookup"><span data-stu-id="61eb8-112">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="61eb8-113">На странице **Обслуживание бизнес-правил** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="61eb8-113">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="61eb8-114">Выберите сущность из списка **Сущность** .</span><span class="sxs-lookup"><span data-stu-id="61eb8-114">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="61eb8-115">В списке **Тип элемента** выберите тип элемента, к которому будет применяться бизнес-правило.</span><span class="sxs-lookup"><span data-stu-id="61eb8-115">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="61eb8-116">Выберите из списка **Атрибут** атрибут или оставьте **Все**по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="61eb8-116">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="61eb8-117">Нажмите **Добавить бизнес-правило**.</span><span class="sxs-lookup"><span data-stu-id="61eb8-117">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="61eb8-118">Нажмите **Изменить выбранное бизнес-правило**.</span><span class="sxs-lookup"><span data-stu-id="61eb8-118">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="61eb8-119">На панели **Компоненты** разверните узел **Условия** .</span><span class="sxs-lookup"><span data-stu-id="61eb8-119">In the **Components** pane, expand the **Conditions** node.</span></span>  
  
10. <span data-ttu-id="61eb8-120">Щелкните условие и перетащите его на метку **условия** области **If** .</span><span class="sxs-lookup"><span data-stu-id="61eb8-120">Click a condition and drag it to the **IF** pane's **Conditions** label.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="61eb8-121">Чтобы удалить элементы из бизнес-правила, щелкните правой кнопкой мыши и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="61eb8-121">You can delete items from your business rule by right-clicking and choosing **Delete**.</span></span>  
  
11. <span data-ttu-id="61eb8-122">На панели **атрибуты** щелкните атрибут и перетащите его на значок **Выбор атрибута** в области **изменить условие** .</span><span class="sxs-lookup"><span data-stu-id="61eb8-122">In the **Attributes** pane, click an attribute and drag it to the **Edit Condition** pane's **Select attribute** label.</span></span>  
  
12. <span data-ttu-id="61eb8-123">На панели **Изменение условия** заполните все обязательные поля.</span><span class="sxs-lookup"><span data-stu-id="61eb8-123">In the **Edit Condition** pane, complete any required fields.</span></span>  
  
13. <span data-ttu-id="61eb8-124">На панели **Изменение условия** нажмите кнопку **Сохранить элемент**.</span><span class="sxs-lookup"><span data-stu-id="61eb8-124">In the **Edit Condition** pane, click **Save item**.</span></span>  
  
14. <span data-ttu-id="61eb8-125">На панели **Компоненты** разверните узел **Действия** .</span><span class="sxs-lookup"><span data-stu-id="61eb8-125">In the **Components** pane, expand the **Actions** node.</span></span>  
  
15. <span data-ttu-id="61eb8-126">Перетащите действие на значок **Действие** панели **THEN** .</span><span class="sxs-lookup"><span data-stu-id="61eb8-126">Click an action and drag it to the **THEN** pane's **Action** label.</span></span>  
  
16. <span data-ttu-id="61eb8-127">На панели **Атрибуты** щелкните атрибут и перетащите его на значок **Выбор атрибута** панели **Изменение действия** .</span><span class="sxs-lookup"><span data-stu-id="61eb8-127">In the **Attributes** pane, click an attribute and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
17. <span data-ttu-id="61eb8-128">На панели **Изменение действия** заполните все необходимые поля.</span><span class="sxs-lookup"><span data-stu-id="61eb8-128">In the **Edit Action** pane, complete any required fields.</span></span>  
  
18. <span data-ttu-id="61eb8-129">На панели **Изменение действия** нажмите кнопку **Сохранить элемент**.</span><span class="sxs-lookup"><span data-stu-id="61eb8-129">In the **Edit Action** pane, click **Save item**.</span></span>  
  
19. <span data-ttu-id="61eb8-130">В правило также можно добавлять по несколько условий.</span><span class="sxs-lookup"><span data-stu-id="61eb8-130">Optionally, add multiple conditions to the rule.</span></span> <span data-ttu-id="61eb8-131">Дополнительные сведения см. в статье [Добавление нескольких условий к бизнес-правилу (службы Master Data Services)](../../2014/master-data-services/add-multiple-conditions-to-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="61eb8-131">For more information, see [Add Multiple Conditions to a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/add-multiple-conditions-to-a-business-rule-master-data-services.md).</span></span>  
  
20. <span data-ttu-id="61eb8-132">Нажмите кнопку **Назад**.</span><span class="sxs-lookup"><span data-stu-id="61eb8-132">Click **Back**.</span></span>  
  
21. <span data-ttu-id="61eb8-133">По желанию на странице **Обслуживание бизнес-правил** дважды щелкните ячейку столбца **Имя**, **Описание**или **Уведомление** , чтобы обновить значение.</span><span class="sxs-lookup"><span data-stu-id="61eb8-133">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="61eb8-134">Уведомления отправляются только для правил, включающих действие по проверке.</span><span class="sxs-lookup"><span data-stu-id="61eb8-134">Notifications are sent only for rules that include a validation action.</span></span>  
  
22. <span data-ttu-id="61eb8-135">Нажмите кнопку **Опубликовать бизнес-правила**.</span><span class="sxs-lookup"><span data-stu-id="61eb8-135">Click **Publish business rules**.</span></span>  
  
23. <span data-ttu-id="61eb8-136">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="61eb8-136">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="61eb8-137">Состояние правила изменится на **Активно**.</span><span class="sxs-lookup"><span data-stu-id="61eb8-137">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="61eb8-138">Next Steps</span><span class="sxs-lookup"><span data-stu-id="61eb8-138">Next Steps</span></span>  
  
-   <span data-ttu-id="61eb8-139">Примените бизнес-правила к данным с помощью одной из следующих процедур:</span><span class="sxs-lookup"><span data-stu-id="61eb8-139">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="61eb8-140">Подтверждение конкретных членов, обнаруженных при проверке на соответствие бизнес-правилам (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="61eb8-140">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="61eb8-141">Подтверждение исправления проблемы, обнаруженной при проверке на соответствие бизнес-правилам (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="61eb8-141">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="61eb8-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="61eb8-142">See Also</span></span>  
 <span data-ttu-id="61eb8-143">[Настройка бизнес-правил для отправки уведомлений &#40;Master Data Services&#41;](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="61eb8-143">[Configure Business Rules to Send Notifications &#40;Master Data Services&#41;](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md) </span></span>  
 <span data-ttu-id="61eb8-144">[Измените имя бизнес-правила &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="61eb8-144">[Change a Business Rule Name &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span></span>  
 [<span data-ttu-id="61eb8-145">Добавление нескольких условий к бизнес-правилу (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="61eb8-145">Add Multiple Conditions to a Business Rule &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-multiple-conditions-to-a-business-rule-master-data-services.md)  
  
  
