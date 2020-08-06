---
title: Настройка бизнес-правил для отправки уведомлений (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], configuring notifications
- e-mail [Master Data Services], configuring business rules
- notifications [Master Data Services], configuring business rules
ms.assetid: b24f7b11-ab53-4642-999c-e17b543b3558
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cb1a12167dffe123e55760f031e21499fe22a945
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669460"
---
# <a name="configure-business-rules-to-send-notifications-master-data-services"></a><span data-ttu-id="c64f7-102">Настройка в бизнес-правилах отправки уведомлений (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c64f7-102">Configure Business Rules to Send Notifications (Master Data Services)</span></span>
  <span data-ttu-id="c64f7-103">Бизнес-правила для отправки уведомлений в службах [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]настраивают в том случае, если нужно уведомлять пользователей об изменениях значений атрибутов.</span><span class="sxs-lookup"><span data-stu-id="c64f7-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], configure business rules to send notifications when you want to notify users about attribute value changes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c64f7-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c64f7-104">Prerequisites</span></span>  
 <span data-ttu-id="c64f7-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="c64f7-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c64f7-106">Необходимо иметь разрешение на доступ к функциональным областям **Администрирование системы** и **Разрешения пользователей и групп** .</span><span class="sxs-lookup"><span data-stu-id="c64f7-106">You must have permission to access the **System Administration** and **User and Group Permissions** functional areas.</span></span> <span data-ttu-id="c64f7-107">Если отсутствуют разрешения для функциональной области **Разрешения пользователей и групп** , то пользователь не сможет просмотреть список пользователей и групп, которым необходимо отправить уведомления.</span><span class="sxs-lookup"><span data-stu-id="c64f7-107">If you do not have permission to the **User and Group Permissions** functional area, you cannot view the list of users and groups to send notifications to.</span></span>  
  
-   <span data-ttu-id="c64f7-108">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="c64f7-108">You must be a model administrator.</span></span> <span data-ttu-id="c64f7-109">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c64f7-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="c64f7-110">Уже должно существовать бизнес-правило, использующее действие по проверке.</span><span class="sxs-lookup"><span data-stu-id="c64f7-110">A business rule that uses a validation action must already exist.</span></span> <span data-ttu-id="c64f7-111">Дополнительные сведения см. в разделе [Создание и публикация бизнес-правила (службы Master Data Services)](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c64f7-111">For more information, see [Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="c64f7-112">Пользователь или группа, получающие уведомления, должны иметь разрешения не ниже **Только для чтения** для атрибута, проверка которого завершилась ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c64f7-112">The user or group that receives the notification must have at least **Read-only** permission to the attribute that fails validation.</span></span> <span data-ttu-id="c64f7-113">Пользователи или группы, которым явно или неявно отказано в разрешении на атрибут, получат по электронной почте соответствующее сообщение, но не смогут получить доступ к атрибуту в службах [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c64f7-113">Users or groups that are explicitly or implicitly denied permission to the attribute will receive the email but will not be able to access the attribute in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="c64f7-114">Если сообщение электронной почты отправляется группе, то это сообщение получат только те члены группы, которые имеют доступ к службам [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c64f7-114">If mail is sent to a group, only members of the group that have accessed [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] will get the email.</span></span>  
  
### <a name="to-configure-business-rules-to-send-notifications"></a><span data-ttu-id="c64f7-115">Настройка бизнес-правил для отправки уведомлений</span><span class="sxs-lookup"><span data-stu-id="c64f7-115">To configure business rules to send notifications</span></span>  
  
1.  <span data-ttu-id="c64f7-116">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="c64f7-116">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="c64f7-117">В строке меню выберите **Управление** и щелкните **Бизнес-правила**.</span><span class="sxs-lookup"><span data-stu-id="c64f7-117">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="c64f7-118">На странице **Обслуживание бизнес-правил** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="c64f7-118">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="c64f7-119">Выберите сущность из списка **Сущность** .</span><span class="sxs-lookup"><span data-stu-id="c64f7-119">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="c64f7-120">В списке **тип члена** выберите тип члена.</span><span class="sxs-lookup"><span data-stu-id="c64f7-120">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="c64f7-121">Выберите из списка **Атрибут** атрибут или оставьте **Все**по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c64f7-121">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="c64f7-122">В сетке в строке для бизнес-правила дважды щелкните поле **уведомления** .</span><span class="sxs-lookup"><span data-stu-id="c64f7-122">In the grid, in the row for the business rule, double-click the **Notification** field.</span></span>  
  
8.  <span data-ttu-id="c64f7-123">Во вложенном меню выберите пользователя или группу, куда необходимо отправлять уведомление.</span><span class="sxs-lookup"><span data-stu-id="c64f7-123">From the sub-menu, click a user or group to send the email notification to.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c64f7-124">Next Steps</span><span class="sxs-lookup"><span data-stu-id="c64f7-124">Next Steps</span></span>  
  
-   <span data-ttu-id="c64f7-125">Примените бизнес-правила к данным с помощью одной из следующих процедур:</span><span class="sxs-lookup"><span data-stu-id="c64f7-125">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="c64f7-126">Подтверждение конкретных членов, обнаруженных при проверке на соответствие бизнес-правилам (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c64f7-126">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="c64f7-127">Подтверждение исправления проблемы, обнаруженной при проверке на соответствие бизнес-правилам (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c64f7-127">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
-   <span data-ttu-id="c64f7-128">Настройте протокол электронной почты следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c64f7-128">Configure the email protocol as follows:</span></span>  
  
    -   [<span data-ttu-id="c64f7-129">Настройка уведомления электронной почты (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c64f7-129">Configure Email Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-email-notifications-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="c64f7-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="c64f7-130">See Also</span></span>  
 <span data-ttu-id="c64f7-131">[Master Data Services &#40;уведомлений&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c64f7-131">[Notifications &#40;Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span></span>  
 [<span data-ttu-id="c64f7-132">Настройка уведомления электронной почты (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c64f7-132">Configure Email Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-email-notifications-master-data-services.md)  
  
  
