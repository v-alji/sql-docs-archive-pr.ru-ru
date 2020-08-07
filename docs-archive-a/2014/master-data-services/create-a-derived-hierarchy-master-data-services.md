---
title: Создание производной иерархии (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- derived hierarchies, creating
- creating derived hierarchies [Master Data Services]
ms.assetid: fec653c4-11cc-46a2-8dd8-b605341ebb40
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 20469ad30222e43a3104503cc32187c2e6512743
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732713"
---
# <a name="create-a-derived-hierarchy-master-data-services"></a><span data-ttu-id="390d2-102">Создание производной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="390d2-102">Create a Derived Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="390d2-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]производные иерархии создаются, если необходима многоуровневая иерархия, гарантирующая, что элементы располагаются на правильном уровне.</span><span class="sxs-lookup"><span data-stu-id="390d2-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a derived hierarchy when you want a level-based hierarchy that ensures that members exist at the correct level.</span></span> <span data-ttu-id="390d2-104">Производные иерархии опираются на имеющиеся в модели связи атрибутов на основе домена.</span><span class="sxs-lookup"><span data-stu-id="390d2-104">Derived hierarchies are based on the domain-based attribute relationships that exist in a model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="390d2-105">Если значение атрибута на основе домена отсутствует для какого-либо элемента, он не включается в производную иерархию.</span><span class="sxs-lookup"><span data-stu-id="390d2-105">If a domain-based attribute value doesn't exist for a member, the member is not included in the derived hierarchy.</span></span> <span data-ttu-id="390d2-106">Сведения о том, как сделать значение атрибута на основе домена обязательным для всех элементов, см. в разделе [Запрос значений атрибута (службы Master Data Services)](require-attribute-values-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="390d2-106">See [Require Attribute Values &#40;Master Data Services&#41;](require-attribute-values-master-data-services.md) to require a domain-based attribute value for all members.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="390d2-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="390d2-107">Prerequisites</span></span>  
 <span data-ttu-id="390d2-108">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="390d2-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="390d2-109">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="390d2-109">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="390d2-110">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="390d2-110">You must be a model administrator.</span></span> <span data-ttu-id="390d2-111">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="390d2-111">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-derived-hierarchy"></a><span data-ttu-id="390d2-112">Создание производной иерархии</span><span class="sxs-lookup"><span data-stu-id="390d2-112">To create a derived hierarchy</span></span>  
  
1.  <span data-ttu-id="390d2-113">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="390d2-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="390d2-114">На странице **представление модели** в строке меню наведите указатель мыши на пункт **Управление** и щелкните **производные иерархии**.</span><span class="sxs-lookup"><span data-stu-id="390d2-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Derived Hierarchies**.</span></span>  
  
3.  <span data-ttu-id="390d2-115">На странице **Обслуживание производной иерархии** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="390d2-115">On the **Derived Hierarchy Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="390d2-116">Нажмите кнопку **Добавить производную иерархию**.</span><span class="sxs-lookup"><span data-stu-id="390d2-116">Click **Add derived hierarchy**.</span></span>  
  
5.  <span data-ttu-id="390d2-117">В поле **Имя производной иерархии** на странице **Добавление производной иерархии** введите имя иерархии.</span><span class="sxs-lookup"><span data-stu-id="390d2-117">On the **Add Derived Hierarchy** page, in the **Derived hierarchy name** box, type a name for the hierarchy.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="390d2-118"> Используйте имя, описывающее уровни иерархии, например **Продукт: от подкатегории к категории**.</span><span class="sxs-lookup"><span data-stu-id="390d2-118">Use a name that describes the levels in the hierarchy, for example **Product to Subcategory to Category**.</span></span>  
  
6.  <span data-ttu-id="390d2-119">Нажмите кнопку **Сохранить производную иерархию**.</span><span class="sxs-lookup"><span data-stu-id="390d2-119">Click **Save derived hierarchy**.</span></span>  
  
7.  <span data-ttu-id="390d2-120">На странице **изменение производной иерархии** на панели **Доступные сущности и иерархии** щелкните сущность или иерархию и перетащите ее на панель **текущие уровни** .</span><span class="sxs-lookup"><span data-stu-id="390d2-120">On the **Edit Derived Hierarchy** page, in the **Available Entities and Hierarchies** pane, click an entity or hierarchy and drag it to the **Current Levels** pane.</span></span>  
  
8.  <span data-ttu-id="390d2-121">Перетаскивайте сущности или иерархии, пока не завершите создание иерархии.</span><span class="sxs-lookup"><span data-stu-id="390d2-121">Continue dragging entities or hierarchies until your hierarchy is complete.</span></span>  
  
9. <span data-ttu-id="390d2-122">Нажмите кнопку **Назад**.</span><span class="sxs-lookup"><span data-stu-id="390d2-122">Click **Back**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="390d2-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="390d2-123">See Also</span></span>  
 <span data-ttu-id="390d2-124">[Производные иерархии &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="390d2-124">[Derived Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span></span>  
 <span data-ttu-id="390d2-125">[Производные иерархии с явно заданными ограничениями &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="390d2-125">[Derived Hierarchies with Explicit Caps &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span></span>  
 [<span data-ttu-id="390d2-126">Атрибуты на основе домена (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="390d2-126">Domain-Based Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/domain-based-attributes-master-data-services.md)  
  
  
