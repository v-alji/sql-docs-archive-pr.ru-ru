---
title: Создание сущности (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- entities [Master Data Services], creating
- creating entities [Master Data Services]
ms.assetid: d9a6a51e-7b53-4785-a118-3baeb7ca2d48
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7cefdedd07ee248f12b3b17337878934a2b1aa84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668407"
---
# <a name="create-an-entity-master-data-services"></a><span data-ttu-id="027e3-102">Создание сущности (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="027e3-102">Create an Entity (Master Data Services)</span></span>
  <span data-ttu-id="027e3-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]сущности создаются, чтобы содержать элементы и их атрибуты.</span><span class="sxs-lookup"><span data-stu-id="027e3-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create an entity to contain members and their attributes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="027e3-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="027e3-104">Prerequisites</span></span>  
 <span data-ttu-id="027e3-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="027e3-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="027e3-106">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="027e3-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="027e3-107">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="027e3-107">You must be a model administrator.</span></span> <span data-ttu-id="027e3-108">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="027e3-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="027e3-109">Модель должна существовать.</span><span class="sxs-lookup"><span data-stu-id="027e3-109">A model must exist.</span></span> <span data-ttu-id="027e3-110">Дополнительные сведения см. в разделе [Создание модели (службы Master Data Services)](../../2014/master-data-services/create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="027e3-110">For more information, see [Create a Model &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-model-master-data-services.md).</span></span>  
  
### <a name="to-create-an-entity"></a><span data-ttu-id="027e3-111">Создание сущности</span><span class="sxs-lookup"><span data-stu-id="027e3-111">To create an entity</span></span>  
  
1.  <span data-ttu-id="027e3-112">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="027e3-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="027e3-113">На странице **Представление модели** в строке меню наведите курсор на **Управление** и щелкните **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="027e3-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="027e3-114">На странице **Обслуживание сущности** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="027e3-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="027e3-115">Нажмите кнопку **добавить сущность**.</span><span class="sxs-lookup"><span data-stu-id="027e3-115">Click **Add entity**.</span></span>  
  
5.  <span data-ttu-id="027e3-116">В поле **имя сущности** введите имя сущности.</span><span class="sxs-lookup"><span data-stu-id="027e3-116">In the **Entity name** box, type the name of the entity.</span></span>  
  
6.  <span data-ttu-id="027e3-117">В поле **имя для промежуточных таблиц** введите имя промежуточной таблицы.</span><span class="sxs-lookup"><span data-stu-id="027e3-117">In the **Name for staging tables** box, type a name for the staging table.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="027e3-118">Используйте имя модели как часть имени промежуточной таблицы, например *Modelname_Entityname*.</span><span class="sxs-lookup"><span data-stu-id="027e3-118">Use the model name as part of the staging table name, for example *Modelname_Entityname*.</span></span> <span data-ttu-id="027e3-119">Это облегчит поиск таблиц в базе данных.</span><span class="sxs-lookup"><span data-stu-id="027e3-119">This makes the tables easier to find in the database.</span></span> <span data-ttu-id="027e3-120">Дополнительные сведения о промежуточных таблицах см. в разделе [Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="027e3-120">For more information about the staging tables, see [Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span></span>  
  
7.  <span data-ttu-id="027e3-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="027e3-121">Optional.</span></span> <span data-ttu-id="027e3-122">Установите флажок в поле **Автоматически создавать значения кода** .</span><span class="sxs-lookup"><span data-stu-id="027e3-122">Select the **Create Code values automatically** check box.</span></span> <span data-ttu-id="027e3-123">Дополнительные сведения см. в разделе [Автоматическое создание кода &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="027e3-123">For more information, see [Automatic Code Creation &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md).</span></span>  
  
8.  <span data-ttu-id="027e3-124">В списке **включить явные иерархии и коллекции** выберите один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="027e3-124">From the **Enable explicit hierarchies and collections** list, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="027e3-125">**Нет**.</span><span class="sxs-lookup"><span data-stu-id="027e3-125">**No**.</span></span> <span data-ttu-id="027e3-126">Выберите этот параметр, если сущность не должна включать явные иерархии и коллекции.</span><span class="sxs-lookup"><span data-stu-id="027e3-126">Select this option if you do not need to enable the entity for explicit hierarchies and collections.</span></span> <span data-ttu-id="027e3-127">При необходимости это значение можно впоследствии изменить.</span><span class="sxs-lookup"><span data-stu-id="027e3-127">You can change this later if needed.</span></span>  
  
    -   <span data-ttu-id="027e3-128">**Да.**</span><span class="sxs-lookup"><span data-stu-id="027e3-128">**Yes**.</span></span> <span data-ttu-id="027e3-129">Выберите этот параметр, если необходимо включить использование явных иерархий и коллекций.</span><span class="sxs-lookup"><span data-stu-id="027e3-129">Select this option when you want to enable the entity for explicit hierarchies and collections.</span></span> <span data-ttu-id="027e3-130">В поле **имя явной иерархии** введите имя.</span><span class="sxs-lookup"><span data-stu-id="027e3-130">In the **Explicit hierarchy name** box, type a name.</span></span> <span data-ttu-id="027e3-131">При необходимости выберите **обязательная иерархия (все конечные элементы включены** , чтобы сделать явную иерархию обязательной иерархией.</span><span class="sxs-lookup"><span data-stu-id="027e3-131">Optionally, select **Mandatory hierarchy (all leaf members are included** to make the explicit hierarchy a mandatory hierarchy.</span></span>  
  
9. <span data-ttu-id="027e3-132">Нажмите кнопку **Сохранить сущность**.</span><span class="sxs-lookup"><span data-stu-id="027e3-132">Click **Save entity**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="027e3-133">Next Steps</span><span class="sxs-lookup"><span data-stu-id="027e3-133">Next Steps</span></span>  
  
-   [<span data-ttu-id="027e3-134">Создание текстового атрибута (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="027e3-134">Create a Text Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-text-attribute-master-data-services.md)  
  
-   [<span data-ttu-id="027e3-135">Создание атрибута на основе домена (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="027e3-135">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
-   [<span data-ttu-id="027e3-136">Создание файлового атрибута (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="027e3-136">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="027e3-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="027e3-137">See Also</span></span>  
 <span data-ttu-id="027e3-138">[Сущности &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="027e3-138">[Entities &#40;Master Data Services&#41;](../../2014/master-data-services/entities-master-data-services.md) </span></span>  
 <span data-ttu-id="027e3-139">[Явные иерархии &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="027e3-139">[Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) </span></span>  
 <span data-ttu-id="027e3-140">[Измените имя сущности &#40;Master Data Services&#41;](edit-an-entity-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="027e3-140">[Change an Entity Name &#40;Master Data Services&#41;](edit-an-entity-master-data-services.md) </span></span>  
 [<span data-ttu-id="027e3-141">Удаление сущности (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="027e3-141">Delete an Entity &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-entity-master-data-services.md)  
  
  
