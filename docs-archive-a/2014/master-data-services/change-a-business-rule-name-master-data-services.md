---
title: Изменение имени бизнес-правила (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], changing name
ms.assetid: cffcae43-a208-443f-9f43-a0ec9e05f79c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0e99047ffe27332aaed4514394ca2357942a1297
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668982"
---
# <a name="change-a-business-rule-name-master-data-services"></a><span data-ttu-id="ae338-102">Изменение имени бизнес-правила (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ae338-102">Change a Business Rule Name (Master Data Services)</span></span>
  <span data-ttu-id="ae338-103">В службах [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]изменение имени бизнес-правила может потребоваться в том случае, если заданное имя не соответствует потребностям предприятия.</span><span class="sxs-lookup"><span data-stu-id="ae338-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], change a business rule name when the name assigned does not meet your business needs.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ae338-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="ae338-104">Prerequisites</span></span>  
 <span data-ttu-id="ae338-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="ae338-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="ae338-106">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="ae338-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="ae338-107">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="ae338-107">You must be a model administrator.</span></span> <span data-ttu-id="ae338-108">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ae338-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="ae338-109">Должно существовать бизнес-правило.</span><span class="sxs-lookup"><span data-stu-id="ae338-109">A business rule must exist.</span></span> <span data-ttu-id="ae338-110">Дополнительные сведения см. в разделе [Создание и публикация бизнес-правила (службы Master Data Services)](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ae338-110">For more information, see [Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span></span>  
  
### <a name="to-change-the-name-of-a-business-rule"></a><span data-ttu-id="ae338-111">Изменение имени бизнес-правила</span><span class="sxs-lookup"><span data-stu-id="ae338-111">To change the name of a business rule</span></span>  
  
1.  <span data-ttu-id="ae338-112">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="ae338-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="ae338-113">В строке меню выберите **Управление** и щелкните **Бизнес-правила**.</span><span class="sxs-lookup"><span data-stu-id="ae338-113">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="ae338-114">На странице **Обслуживание бизнес-правил** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="ae338-114">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="ae338-115">Выберите сущность из списка **Сущность** .</span><span class="sxs-lookup"><span data-stu-id="ae338-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="ae338-116">В списке **тип члена** выберите тип члена.</span><span class="sxs-lookup"><span data-stu-id="ae338-116">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="ae338-117">Выберите из списка **Атрибут** атрибут или оставьте **Все**по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ae338-117">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="ae338-118">В сетке в строке для бизнес-правила дважды щелкните поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="ae338-118">In the grid, in the row for the business rule, double-click the **Name** field.</span></span>  
  
8.  <span data-ttu-id="ae338-119">Введите имя бизнес-правила.</span><span class="sxs-lookup"><span data-stu-id="ae338-119">Type a name for the business rule.</span></span>  
  
9. <span data-ttu-id="ae338-120">Нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="ae338-120">Press ENTER.</span></span>  
  
10. <span data-ttu-id="ae338-121">Нажмите кнопку **Опубликовать бизнес-правила**.</span><span class="sxs-lookup"><span data-stu-id="ae338-121">Click **Publish business rules**.</span></span>  
  
11. <span data-ttu-id="ae338-122">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ae338-122">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="ae338-123">Состояние правила изменится на **Активно**.</span><span class="sxs-lookup"><span data-stu-id="ae338-123">The rule's status changes to **Active**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae338-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="ae338-124">See Also</span></span>  
 [<span data-ttu-id="ae338-125">Бизнес-правила (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ae338-125">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
