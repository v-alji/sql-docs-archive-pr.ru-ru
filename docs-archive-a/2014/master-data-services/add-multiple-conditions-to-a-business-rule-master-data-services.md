---
title: Добавление нескольких условий к бизнес-правилу (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], multiple conditions
ms.assetid: 5f0f6958-6cf2-444b-bdcd-05b887637a0b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c62b8dfa4f459958d12bd384b85aa74bef382b21
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666113"
---
# <a name="add-multiple-conditions-to-a-business-rule-master-data-services"></a><span data-ttu-id="48608-102">Добавление нескольких условий к бизнес-правилу (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="48608-102">Add Multiple Conditions to a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="48608-103">Чтобы в среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]создать более сложное бизнес-правило, к нему с помощью операторов **AND** и **OR** можно добавить несколько условий.</span><span class="sxs-lookup"><span data-stu-id="48608-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], add multiple **AND** or **OR** conditions to a business rule when you want a more complex rule.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48608-104">Если в создаваемом бизнес-правиле используется оператор **OR** , рассмотрите возможность создания отдельного правила для каждой из условных инструкций, которые можно применить независимо.</span><span class="sxs-lookup"><span data-stu-id="48608-104">If you create a business rule that uses the **OR** operator, consider creating a separate rule for each conditional statement that can be evaluated independently.</span></span> <span data-ttu-id="48608-105">При необходимости правила можно исключать, что повышает гибкость и упрощает устранение неполадок.</span><span class="sxs-lookup"><span data-stu-id="48608-105">You can then exclude rules as needed, providing more flexibility and easier troubleshooting.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="48608-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="48608-106">Prerequisites</span></span>  
 <span data-ttu-id="48608-107">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="48608-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="48608-108">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="48608-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="48608-109">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="48608-109">You must be a model administrator.</span></span> <span data-ttu-id="48608-110">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="48608-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="48608-111">Должно существовать бизнес-правило.</span><span class="sxs-lookup"><span data-stu-id="48608-111">A business rule must exist.</span></span> <span data-ttu-id="48608-112">Дополнительные сведения см. в разделе [Создание и публикация бизнес-правила (службы Master Data Services)](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="48608-112">For more information, see [Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span></span>  
  
### <a name="to-add-multiple-conditions-to-a-business-rule"></a><span data-ttu-id="48608-113">Добавление нескольких условий в бизнес-правило</span><span class="sxs-lookup"><span data-stu-id="48608-113">To add multiple conditions to a business rule</span></span>  
  
1.  <span data-ttu-id="48608-114">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="48608-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="48608-115">В строке меню выберите **Управление** и щелкните **Бизнес-правила**.</span><span class="sxs-lookup"><span data-stu-id="48608-115">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="48608-116">На странице **Обслуживание бизнес-правил** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="48608-116">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="48608-117">Выберите сущность из списка **Сущность** .</span><span class="sxs-lookup"><span data-stu-id="48608-117">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="48608-118">В списке **тип члена** выберите тип члена.</span><span class="sxs-lookup"><span data-stu-id="48608-118">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="48608-119">Выберите из списка **Атрибут** атрибут или оставьте **Все**по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="48608-119">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="48608-120">Щелкните строку, где указано бизнес-правило, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="48608-120">Click the row for the business rule you want to edit.</span></span>  
  
8.  <span data-ttu-id="48608-121">Нажмите **Изменить выбранное бизнес-правило**.</span><span class="sxs-lookup"><span data-stu-id="48608-121">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="48608-122">В области **компоненты** разверните узел **логические операторы** .</span><span class="sxs-lookup"><span data-stu-id="48608-122">In the **Components** pane, expand the **Logical Operators** node.</span></span>  
  
10. <span data-ttu-id="48608-123">Щелкните **и** или **или** и перетащите его в область **и** метку **If** .</span><span class="sxs-lookup"><span data-stu-id="48608-123">Click **AND** or **OR** and drag it to the **IF** pane's **AND** label.</span></span>  
  
11. <span data-ttu-id="48608-124">На панели **Компоненты** разверните узел **Условия** .</span><span class="sxs-lookup"><span data-stu-id="48608-124">In the **Components** pane, expand the **Conditions** node.</span></span>  
  
12. <span data-ttu-id="48608-125">Щелкните условие и перетащите его в область **If** , в метку **и** или **или** из шага 10.</span><span class="sxs-lookup"><span data-stu-id="48608-125">Click a condition and drag it to **IF** pane, to the **AND** or **OR** label from step 10.</span></span>  
  
13. <span data-ttu-id="48608-126">На панели **атрибуты** щелкните атрибут и перетащите его на значок **Выбор атрибута** в области **изменить условие** .</span><span class="sxs-lookup"><span data-stu-id="48608-126">In the **Attributes** pane, click an attribute and drag it to the **Edit Condition** pane's **Select attribute** label.</span></span>  
  
14. <span data-ttu-id="48608-127">На панели **Изменение условия** заполните все обязательные поля.</span><span class="sxs-lookup"><span data-stu-id="48608-127">In the **Edit Condition** pane, complete any required fields.</span></span>  
  
15. <span data-ttu-id="48608-128">На панели **Изменение условия** нажмите кнопку **Сохранить элемент**.</span><span class="sxs-lookup"><span data-stu-id="48608-128">In the **Edit Condition** pane, click **Save item**.</span></span>  
  
16. <span data-ttu-id="48608-129">При необходимости, чтобы добавить дополнительные условия, в области **компоненты** перетащите объект **и** или **или** в любой элемент **и** или **или в** область **If** .</span><span class="sxs-lookup"><span data-stu-id="48608-129">Optionally, to add more conditions, from the **Components** pane, drag **AND** or **OR** to any **AND** or **OR** in the **IF** pane.</span></span> <span data-ttu-id="48608-130">Затем выполните шаги 13–15.</span><span class="sxs-lookup"><span data-stu-id="48608-130">Then follow steps 13-15.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="48608-131">Чтобы удалить условие, щелкните имя условия и на панели **изменить условие** нажмите кнопку **удалить элемент**.</span><span class="sxs-lookup"><span data-stu-id="48608-131">To delete a condition, click the name of the condition and in the **Edit Condition** pane, click **Delete item**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48608-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="48608-132">See Also</span></span>  
 <span data-ttu-id="48608-133">[Бизнес-правила &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="48608-133">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 <span data-ttu-id="48608-134">[Измените имя бизнес-правила &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="48608-134">[Change a Business Rule Name &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span></span>  
 [<span data-ttu-id="48608-135">Настройка в бизнес-правилах отправки уведомлений (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="48608-135">Configure Business Rules to Send Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md)  
  
  
