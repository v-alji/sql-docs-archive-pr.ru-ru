---
title: Запрос значений атрибута (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], requiring attribute values
- attributes [Master Data Services], requiring values
ms.assetid: a360ef13-0c34-43b8-a87e-2f5d8732d30e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 42b412fc42138c5e186c6c7ad42373f20e35f3cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657134"
---
# <a name="require-attribute-values-master-data-services"></a><span data-ttu-id="c051a-102">Запрос значений атрибута (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c051a-102">Require Attribute Values (Master Data Services)</span></span>
  <span data-ttu-id="c051a-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]значения атрибута запрашиваются для гарантии завершенности основных данных.</span><span class="sxs-lookup"><span data-stu-id="c051a-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], require attribute values when you want to ensure your master data is complete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c051a-104">Если у элемента не хватает значения атрибута на основе домена, то этот элемент не отображается в производной иерархии, основанной на этих связях.</span><span class="sxs-lookup"><span data-stu-id="c051a-104">Members that are missing domain-based attribute values are not displayed in derived hierarchies that are based on those relationships.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c051a-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c051a-105">Prerequisites</span></span>  
 <span data-ttu-id="c051a-106">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="c051a-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c051a-107">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="c051a-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="c051a-108">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="c051a-108">You must be a model administrator.</span></span> <span data-ttu-id="c051a-109">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c051a-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-require-attribute-values"></a><span data-ttu-id="c051a-110">Запрос значения атрибута</span><span class="sxs-lookup"><span data-stu-id="c051a-110">To require attribute values</span></span>  
  
1.  <span data-ttu-id="c051a-111">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="c051a-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="c051a-112">В строке меню выберите **Управление** и щелкните **Бизнес-правила**.</span><span class="sxs-lookup"><span data-stu-id="c051a-112">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="c051a-113">На странице **Обслуживание бизнес-правил** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="c051a-113">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="c051a-114">Выберите сущность из списка **Сущность** .</span><span class="sxs-lookup"><span data-stu-id="c051a-114">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="c051a-115">В списке **Тип элемента** выберите тип элемента, к которому будет применяться бизнес-правило.</span><span class="sxs-lookup"><span data-stu-id="c051a-115">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="c051a-116">Выберите из списка **Атрибут** атрибут или оставьте **Все**по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c051a-116">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="c051a-117">Нажмите **Добавить бизнес-правило**.</span><span class="sxs-lookup"><span data-stu-id="c051a-117">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="c051a-118">Нажмите **Изменить выбранное бизнес-правило**.</span><span class="sxs-lookup"><span data-stu-id="c051a-118">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="c051a-119">На панели **Компоненты** разверните узел **Действия** .</span><span class="sxs-lookup"><span data-stu-id="c051a-119">In the **Components** pane, expand the **Actions** node.</span></span>  
  
10. <span data-ttu-id="c051a-120">Щелкните **обязательно** и перетащите его на значок **действия** панели **then** .</span><span class="sxs-lookup"><span data-stu-id="c051a-120">Click **is required** and drag it to the **THEN** pane's **Action** label.</span></span>  
  
11. <span data-ttu-id="c051a-121">На панели **Атрибуты** щелкните атрибут и перетащите его на значок **Выбор атрибута** панели **Изменение действия** .</span><span class="sxs-lookup"><span data-stu-id="c051a-121">In the **Attributes** pane, click an attribute and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
12. <span data-ttu-id="c051a-122">На панели **Изменение действия** нажмите кнопку **Сохранить элемент**.</span><span class="sxs-lookup"><span data-stu-id="c051a-122">In the **Edit Action** pane, click **Save item**.</span></span>  
  
13. <span data-ttu-id="c051a-123">Нажмите кнопку **Назад**.</span><span class="sxs-lookup"><span data-stu-id="c051a-123">Click **Back**.</span></span>  
  
14. <span data-ttu-id="c051a-124">По желанию на странице **Обслуживание бизнес-правил** дважды щелкните ячейку столбца **Имя**, **Описание**или **Уведомление** , чтобы обновить значение.</span><span class="sxs-lookup"><span data-stu-id="c051a-124">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
15. <span data-ttu-id="c051a-125">Нажмите кнопку **Опубликовать бизнес-правила**.</span><span class="sxs-lookup"><span data-stu-id="c051a-125">Click **Publish business rules**.</span></span>  
  
16. <span data-ttu-id="c051a-126">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c051a-126">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="c051a-127">Состояние правила изменится на **Активно**.</span><span class="sxs-lookup"><span data-stu-id="c051a-127">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c051a-128">Next Steps</span><span class="sxs-lookup"><span data-stu-id="c051a-128">Next Steps</span></span>  
  
-   <span data-ttu-id="c051a-129">Примените бизнес-правила к данным с помощью одной из следующих процедур:</span><span class="sxs-lookup"><span data-stu-id="c051a-129">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="c051a-130">Подтверждение конкретных членов, обнаруженных при проверке на соответствие бизнес-правилам (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c051a-130">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="c051a-131">Подтверждение исправления проблемы, обнаруженной при проверке на соответствие бизнес-правилам (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c051a-131">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="c051a-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="c051a-132">See Also</span></span>  
 <span data-ttu-id="c051a-133">[Бизнес-правила &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c051a-133">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="c051a-134">Производные иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c051a-134">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)  
  
  
