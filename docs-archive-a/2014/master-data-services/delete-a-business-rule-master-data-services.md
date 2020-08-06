---
title: Удаление бизнес-правила (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting business rules [Master Data Services]
- business rules [Master Data Services], deleting
ms.assetid: b97aa4f9-569f-451d-ad62-65b81f980299
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8e6db486f71634cf025c57eabbedeeb9efdbc437
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728414"
---
# <a name="delete-a-business-rule-master-data-services"></a><span data-ttu-id="523f3-102">Удаление бизнес-правила (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="523f3-102">Delete a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="523f3-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]можно удалить бизнес-правило, которое больше не нужно.</span><span class="sxs-lookup"><span data-stu-id="523f3-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete a business rule when it is no longer needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="523f3-104">Чтобы предотвратить выполнение проверки данных на соответствие бизнес-правилу, можно исключить эти данные, а не удалить их.</span><span class="sxs-lookup"><span data-stu-id="523f3-104">You can prevent data from being validated against a business rule by excluding it, rather than deleting it.</span></span> <span data-ttu-id="523f3-105">Дополнительные сведения см. в разделе [Исключение бизнес-правила (службы Master Data Services)](exclude-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="523f3-105">For more information, see [Exclude a Business Rule &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="523f3-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="523f3-106">Prerequisites</span></span>  
 <span data-ttu-id="523f3-107">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="523f3-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="523f3-108">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="523f3-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="523f3-109">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="523f3-109">You must be a model administrator.</span></span> <span data-ttu-id="523f3-110">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="523f3-110">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-a-business-rule"></a><span data-ttu-id="523f3-111">Удаление бизнес-правила</span><span class="sxs-lookup"><span data-stu-id="523f3-111">To delete a business rule</span></span>  
  
1.  <span data-ttu-id="523f3-112">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="523f3-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="523f3-113">В строке меню выберите **Управление** и щелкните **Бизнес-правила**.</span><span class="sxs-lookup"><span data-stu-id="523f3-113">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="523f3-114">На странице **Обслуживание бизнес-правил** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="523f3-114">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="523f3-115">Выберите сущность из списка **Сущность** .</span><span class="sxs-lookup"><span data-stu-id="523f3-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="523f3-116">В списке **Тип элемента** выберите тип элемента, к которому будет применяться бизнес-правило.</span><span class="sxs-lookup"><span data-stu-id="523f3-116">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="523f3-117">Выберите из списка **Атрибут** атрибут или оставьте **Все**по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="523f3-117">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="523f3-118">В сетке щелкните строку бизнес-правила, которое необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="523f3-118">In the grid, click the row for the business rule you want to delete.</span></span>  
  
8.  <span data-ttu-id="523f3-119">Щелкните **Удалить выбранное бизнес-правило**.</span><span class="sxs-lookup"><span data-stu-id="523f3-119">Click **Delete selected business rule**.</span></span>  
  
9. <span data-ttu-id="523f3-120">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="523f3-120">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="523f3-121">Значение в столбце **состояние** — **Ожидание удаления**.</span><span class="sxs-lookup"><span data-stu-id="523f3-121">The value in the **Status** column is **Deletion pending**.</span></span>  
  
10. <span data-ttu-id="523f3-122">Нажмите кнопку **Опубликовать бизнес-правила**.</span><span class="sxs-lookup"><span data-stu-id="523f3-122">Click **Publish business rules**.</span></span>  
  
11. <span data-ttu-id="523f3-123">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="523f3-123">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="523f3-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="523f3-124">See Also</span></span>  
 <span data-ttu-id="523f3-125">[Исключить &#40;бизнес-правила Master Data Services&#41;](exclude-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="523f3-125">[Exclude a Business Rule &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md) </span></span>  
 <span data-ttu-id="523f3-126">[Создание и публикация бизнес-правила &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="523f3-126">[Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span></span>  
 [<span data-ttu-id="523f3-127">Бизнес-правила (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="523f3-127">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
