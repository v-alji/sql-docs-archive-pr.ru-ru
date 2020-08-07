---
title: Исключение бизнес-правила (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], excluding
ms.assetid: bdbc9df0-23f7-40b9-8aba-4445c1482580
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 317964dcbc7b2cbe212c415b3aa4f9f1a0743301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731838"
---
# <a name="exclude-a-business-rule-master-data-services"></a><span data-ttu-id="c7851-102">Исключение бизнес-правила (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c7851-102">Exclude a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="c7851-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]исключите бизнес-правило, если его не следует удалять без возможности восстановления и отсутствует необходимость проверки данных на соответствие этому бизнес-правилу.</span><span class="sxs-lookup"><span data-stu-id="c7851-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], exclude a business rule when you do not want to delete the rule permanently, but you do not want to validate data against it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c7851-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c7851-104">Prerequisites</span></span>  
 <span data-ttu-id="c7851-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="c7851-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c7851-106">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="c7851-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="c7851-107">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="c7851-107">You must be a model administrator.</span></span> <span data-ttu-id="c7851-108">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c7851-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-exclude-a-business-rule"></a><span data-ttu-id="c7851-109">Исключение бизнес-правила</span><span class="sxs-lookup"><span data-stu-id="c7851-109">To exclude a business rule</span></span>  
  
1.  <span data-ttu-id="c7851-110">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="c7851-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="c7851-111">В строке меню выберите **Управление** и щелкните **Бизнес-правила**.</span><span class="sxs-lookup"><span data-stu-id="c7851-111">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="c7851-112">На странице **Обслуживание бизнес-правил** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="c7851-112">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="c7851-113">Выберите сущность из списка **Сущность** .</span><span class="sxs-lookup"><span data-stu-id="c7851-113">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="c7851-114">В списке **тип члена** выберите тип члена.</span><span class="sxs-lookup"><span data-stu-id="c7851-114">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="c7851-115">Выберите из списка **Атрибут** атрибут или оставьте **Все**по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c7851-115">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="c7851-116">В сетке в строке для бизнес-правила установите флажок в столбце **исключить** .</span><span class="sxs-lookup"><span data-stu-id="c7851-116">In the grid, in the row for the business rule, select the check box in the **Exclude** column.</span></span> <span data-ttu-id="c7851-117">Значение в столбце **Status** является **ожидающим исключением**.</span><span class="sxs-lookup"><span data-stu-id="c7851-117">The value in the **Status** column is **Exclusion pending**.</span></span>  
  
8.  <span data-ttu-id="c7851-118">Нажмите кнопку **Опубликовать бизнес-правила**.</span><span class="sxs-lookup"><span data-stu-id="c7851-118">Click **Publish business rules**.</span></span>  
  
9. <span data-ttu-id="c7851-119">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c7851-119">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="c7851-120">Значение в столбце **состояние** **исключается**.</span><span class="sxs-lookup"><span data-stu-id="c7851-120">The value in the **Status** column is **Excluded**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7851-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="c7851-121">See Also</span></span>  
 <span data-ttu-id="c7851-122">[Удаление бизнес-правила &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c7851-122">[Delete a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-business-rule-master-data-services.md) </span></span>  
 <span data-ttu-id="c7851-123">[Создание и публикация бизнес-правила &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c7851-123">[Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span></span>  
 [<span data-ttu-id="c7851-124">Бизнес-правила (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c7851-124">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
