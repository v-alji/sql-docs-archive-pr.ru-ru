---
title: Изменение типа атрибута (надстройка MDS для Excel) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 9d3001d9-8d0f-4e4a-8e04-4f666bf0df69
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a55ca53fcf6923957e2196840aea2fb5914e1746
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730801"
---
# <a name="change-the-attribute-type-mds-add-in-for-excel"></a><span data-ttu-id="05e04-102">Изменение типа атрибута (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="05e04-102">Change the Attribute Type (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="05e04-103">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]администраторы могут изменить тип атрибута, если тип данных или количество допустимых символов являются неверными.</span><span class="sxs-lookup"><span data-stu-id="05e04-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], administrators can change the attribute type when the data type or number of allowed characters is incorrect.</span></span>  
  
 <span data-ttu-id="05e04-104">Если необходимо изменить тип атрибута для создания ограниченного списка (атрибут на основе домена), см. раздел [Создание атрибута на основе домена (надстройка MDS для Excel)](create-a-domain-based-attribute-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="05e04-104">If you want to change the attribute type to create a constrained list (domain-based attribute), see [Create a Domain-based Attribute &#40;MDS Add-in for Excel&#41;](create-a-domain-based-attribute-mds-add-in-for-excel.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="05e04-105">Нельзя изменить тип или длину столбцов **Имя** или **Код**.</span><span class="sxs-lookup"><span data-stu-id="05e04-105">You cannot update the type or length of the **Name** or **Code** columns.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="05e04-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="05e04-106">Prerequisites</span></span>  
 <span data-ttu-id="05e04-107">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="05e04-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="05e04-108">необходимо иметь разрешение на доступ к функциональным областям **Администрирование системы** и **Обозреватель** ;</span><span class="sxs-lookup"><span data-stu-id="05e04-108">You must have permission to access the **System Administration** and **Explorer** functional areas.</span></span>  
  
-   <span data-ttu-id="05e04-109">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="05e04-109">You must be a model administrator.</span></span> <span data-ttu-id="05e04-110">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="05e04-110">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="05e04-111">должны быть существующие модель, сущность и атрибут.</span><span class="sxs-lookup"><span data-stu-id="05e04-111">There must be an existing model, entity, and attribute.</span></span>  
  
### <a name="to-change-the-attribute-type"></a><span data-ttu-id="05e04-112">Изменение типа атрибута</span><span class="sxs-lookup"><span data-stu-id="05e04-112">To change the attribute type</span></span>  
  
1.  <span data-ttu-id="05e04-113">В Excel загрузите сущность, содержащую столбец (атрибут), который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="05e04-113">In Excel, load the entity that contains the column (attribute) you want to change.</span></span> <span data-ttu-id="05e04-114">Дополнительные сведения см. [в статье Загрузка данных из MDS в Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="05e04-114">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
2.  <span data-ttu-id="05e04-115">Щелкните любую ячейку в столбце, который подлежит изменению.</span><span class="sxs-lookup"><span data-stu-id="05e04-115">Click any cell in the column you want to change.</span></span>  
  
3.  <span data-ttu-id="05e04-116">В группе **Построить модель** нажмите кнопку **Свойства атрибута**.</span><span class="sxs-lookup"><span data-stu-id="05e04-116">In the **Build Model** group, click **Attribute Properties**.</span></span>  
  
4.  <span data-ttu-id="05e04-117">В диалоговом окне **Свойства атрибута** при необходимости обновите параметры.</span><span class="sxs-lookup"><span data-stu-id="05e04-117">In the **Attribute Properties** dialog box, update settings as needed.</span></span>  
  
5.  <span data-ttu-id="05e04-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="05e04-118">Click **OK**.</span></span>  
  
## <a name="what-happens-when-you-change-the-attribute-type"></a><span data-ttu-id="05e04-119">Что происходит при изменении типа атрибута</span><span class="sxs-lookup"><span data-stu-id="05e04-119">What happens when you change the attribute type?</span></span>  
 <span data-ttu-id="05e04-120">Если есть какая-либо зависимость от атрибута, например на атрибут ссылается бизнес-правило MDS или он включен в представление подписки, то MDS при изменении типа данных атрибута выполняет следующие операции.</span><span class="sxs-lookup"><span data-stu-id="05e04-120">If there is any dependency on the attribute, such as the attribute is referenced by any MDS business rule or the attribute is included in a subscription view, and you change the data type of an attribute, MDS will:</span></span>  
  
-   <span data-ttu-id="05e04-121">Изменение типа данных атрибута.</span><span class="sxs-lookup"><span data-stu-id="05e04-121">Change the data type of the attribute.</span></span>  
  
-   <span data-ttu-id="05e04-122">Создать копию атрибута с суффиксом "_old", который не содержит значения.</span><span class="sxs-lookup"><span data-stu-id="05e04-122">Generate a copy of the attribute with the suffix "_old" that does not contain any value.</span></span> <span data-ttu-id="05e04-123">Это называется **устаревшим** атрибутом.</span><span class="sxs-lookup"><span data-stu-id="05e04-123">This is called a **deprecated** attribute.</span></span>  
  
 <span data-ttu-id="05e04-124">Однако все существующие элементы, которые зависят от исходного атрибута, будут указывать на устаревший атрибут, а не на измененный.</span><span class="sxs-lookup"><span data-stu-id="05e04-124">However, all the existing dependencies on the original attribute will point to the deprecated attribute, and not to the changed one.</span></span>  
  
 <span data-ttu-id="05e04-125">Это означает следующее.</span><span class="sxs-lookup"><span data-stu-id="05e04-125">This implies that:</span></span>  
  
-   <span data-ttu-id="05e04-126">Необходимо обновить бизнес-правила так, чтобы они указывали на измененный атрибут, поскольку логика может измениться с учетом того, что у атрибута теперь новый тип данных.</span><span class="sxs-lookup"><span data-stu-id="05e04-126">You must refresh the business rules to point to the changed attribute because the logic may not be the same given the new data type of the attribute.</span></span> <span data-ttu-id="05e04-127">Необходимо изменить все затронутые правила, а затем переработать выражения, чтобы удалить ссылки на устаревший атрибут (_old) и установить ссылки на обновленный атрибут.</span><span class="sxs-lookup"><span data-stu-id="05e04-127">You will have to edit each affected rule, and then rework the expressions to point to remove references from the deprecated attribute (_old) to point to the updated attribute.</span></span>  
  
-   <span data-ttu-id="05e04-128">Необходимо открыть все представления подписки в разделе Управление интеграцией, выбрать строку представления, открыть ее для редактирования, щелкнув значок карандаша, а затем щелкнув значок **сохранить диск** , чтобы обновить определение представления.</span><span class="sxs-lookup"><span data-stu-id="05e04-128">You must open any subscription views under the Integration Management selection, select the view row, open it for editing by clicking the pencil icon, and then click the **Save disk** icon to refresh the view definition.</span></span> <span data-ttu-id="05e04-129">Для повторного формирования синтаксиса представления больше никаких изменений не требуется.</span><span class="sxs-lookup"><span data-stu-id="05e04-129">No other change is needed to regenerate the view syntax.</span></span>  
  
-   <span data-ttu-id="05e04-130">К промежуточным таблицам, в которых есть этот атрибут, будет добавлен столбец с устаревшим атрибутом, а это означает, что промежуточный код также будет затронут.</span><span class="sxs-lookup"><span data-stu-id="05e04-130">Staging tables that include the attribute will have a deprecated attribute column added to them, which means that your staging code will be affected.</span></span> <span data-ttu-id="05e04-131">Устаревший атрибут после обновления бизнес-правил и представлений подписки можно удалить.</span><span class="sxs-lookup"><span data-stu-id="05e04-131">To get rid of the deprecated attribute, you can delete it after you have updated the business rules and subscription views.</span></span>  
  
 <span data-ttu-id="05e04-132">**Удаление устаревшего атрибута**</span><span class="sxs-lookup"><span data-stu-id="05e04-132">**Deleting the deprecated attribute**</span></span>  
  
 <span data-ttu-id="05e04-133">Прежде чем удалить какой-либо устаревший атрибут, необходимо удалить все ссылки на этот атрибут, например зафиксировать бизнес-правила и повторно сформировать представления подписки, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="05e04-133">Before you delete any deprecated attribute, you must remove any references to the attribute such as fixing the business rules and regenerating subscription views as described earlier.</span></span> <span data-ttu-id="05e04-134">В противном случае при попытке удалить устаревший атрибут на веб-странице «Системное администрирование» возникнет ошибка, указывающая, что атрибут нельзя удалить, так как на него ссылается объект.</span><span class="sxs-lookup"><span data-stu-id="05e04-134">Otherwise, you will get an error in the System Administration web page when you attempt to delete the deprecated attribute stating that the attribute cannot be deleted because it is referenced by an object.</span></span>  
  
 <span data-ttu-id="05e04-135">Чтобы удалить атрибут, см. раздел [Delete a attribute &#40;Master Data Services&#41;](../delete-an-attribute-master-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="05e04-135">To delete an attribute, see [Delete an Attribute &#40;Master Data Services&#41;](../delete-an-attribute-master-data-services.md)</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="05e04-136">Изменять тип данных атрибутов MDS, которые имеют данные и связанные сущности, неудобно, особенно если объявлено бизнес-правило или представление подписки, которое ссылается на сущность.</span><span class="sxs-lookup"><span data-stu-id="05e04-136">It is cumbersome to change data types for MDS attributes that have existing data and related entities, especially if there is a business rule or subscription view declared which depends on the entity.</span></span> <span data-ttu-id="05e04-137">Рекомендуется для начала выбрать тип данных, который достаточно гибок и позволяет указывать все необходимые значения.</span><span class="sxs-lookup"><span data-stu-id="05e04-137">The best practice is to start with a data type that is flexible enough to hold the necessary values.</span></span> <span data-ttu-id="05e04-138">Например, вначале строки могут быть небольшими, но со временем становиться все длиннее, поэтому следует исходить из самого худшего варианта развития событий.</span><span class="sxs-lookup"><span data-stu-id="05e04-138">For example, strings may start small, but may need to be lengthened over time, so consider the worst case scenarios.</span></span> <span data-ttu-id="05e04-139">Очень длинные текстовые строки могут быть неудобными в работе (например, широкие текстовые поля для пользовательского интерфейса сложно уместить на экране), поэтому следует избегать слишком длинных строк.</span><span class="sxs-lookup"><span data-stu-id="05e04-139">Extra text string length can be burdensome (for example, wide GUI text boxes are hard to fit on the screen), so avoid too long string length.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05e04-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="05e04-140">See Also</span></span>  
 <span data-ttu-id="05e04-141">[Master Data Services &#40;атрибутов&#41;](../attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="05e04-141">[Attributes &#40;Master Data Services&#41;](../attributes-master-data-services.md) </span></span>  
 [<span data-ttu-id="05e04-142">Построение модели (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="05e04-142">Building a Model &#40;MDS Add-in for Excel&#41;</span></span>](building-a-model-mds-add-in-for-excel.md)  
  
  
