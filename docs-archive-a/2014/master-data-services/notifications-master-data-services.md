---
title: Уведомления (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- notifications [Master Data Services]
- notifications [Master Data Services], about notifications
- e-mail [Master Data Services]
- e-mail [Master Data Services], about e-mail notifications
ms.assetid: d7ad32d5-9fe5-48fd-8c61-0b00c0aff082
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a61825f9450dd5b708aff8c3fc72f0f12732337b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668390"
---
# <a name="notifications-master-data-services"></a><span data-ttu-id="38340-102">Уведомления (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="38340-102">Notifications (Master Data Services)</span></span>
  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]<span data-ttu-id="38340-103">можно настроить для отправки уведомлений по электронной почте при сбое проверки бизнес-правил или изменении состояния версии модели.</span><span class="sxs-lookup"><span data-stu-id="38340-103">can be configured to send an email notification when business rule validation fails or the status of a model version changes.</span></span>  
  
## <a name="how-notifications-are-sent"></a><span data-ttu-id="38340-104">Способ отправки уведомлений</span><span class="sxs-lookup"><span data-stu-id="38340-104">How Notifications Are Sent</span></span>  
 <span data-ttu-id="38340-105">Уведомления настраиваются в [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38340-105">You configure notifications in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span> <span data-ttu-id="38340-106">Уведомления отправляют сообщения электронной почты с помощью Database Mail на экземпляре [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] , где размещается [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] база данных.</span><span class="sxs-lookup"><span data-stu-id="38340-106">Notifications send email messages by using Database Mail on the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] that hosts the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="38340-107">Дополнительные сведения о компоненте Database Mail см. в разделе [Объекты конфигурации компонента Database Mail](../relational-databases/database-mail/database-mail-configuration-objects.md) электронной документации по [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38340-107">For more information about Database Mail, see [Database Mail Configuration Objects](../relational-databases/database-mail/database-mail-configuration-objects.md) in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="when-notifications-are-sent"></a><span data-ttu-id="38340-108">Время отправки уведомлений</span><span class="sxs-lookup"><span data-stu-id="38340-108">When Notifications Are Sent</span></span>  
 <span data-ttu-id="38340-109">После настройки уведомлений автоматические уведомления могут отправляться по электронной почте в следующие экземпляры.</span><span class="sxs-lookup"><span data-stu-id="38340-109">After notifications are configured, automated email notifications can be sent in the following instances.</span></span>  
  
|<span data-ttu-id="38340-110">Экземпляр</span><span class="sxs-lookup"><span data-stu-id="38340-110">Instance</span></span>|<span data-ttu-id="38340-111">Описание</span><span class="sxs-lookup"><span data-stu-id="38340-111">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="38340-112">Проверка данных на соответствие бизнес-правилам завершилась с ошибкой</span><span class="sxs-lookup"><span data-stu-id="38340-112">Data fails business rule validation</span></span>|<span data-ttu-id="38340-113">Если значение атрибута не прошло проверку на соответствие бизнес-правилам, то для отправки почтовых сообщений потребуется настроить бизнес-правила по отдельности.</span><span class="sxs-lookup"><span data-stu-id="38340-113">Individual business rules must be configured to send email when an attribute value fails business rule validation.</span></span> <span data-ttu-id="38340-114">Дополнительные сведения см. в разделе [Настройка в бизнес-правилах отправки уведомлений (службы Master Data Services)](configure-business-rules-to-send-notifications-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="38340-114">For more information, see [Configure Business Rules to Send Notifications &#40;Master Data Services&#41;](configure-business-rules-to-send-notifications-master-data-services.md).</span></span>|  
|<span data-ttu-id="38340-115">Изменения состояния версии модели</span><span class="sxs-lookup"><span data-stu-id="38340-115">Model version status changes</span></span>|<span data-ttu-id="38340-116">Пользователи, являющиеся администраторами модели, автоматически получают уведомления о каждом изменении состояния версии модели.</span><span class="sxs-lookup"><span data-stu-id="38340-116">Each time a model version's status changes, users that are model administrators receive notifications automatically.</span></span> <span data-ttu-id="38340-117">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="38340-117">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>|  
  
## <a name="system-settings"></a><span data-ttu-id="38340-118">Системные настройки</span><span class="sxs-lookup"><span data-stu-id="38340-118">System Settings</span></span>  
 <span data-ttu-id="38340-119">В [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] есть параметры, влияющие на рассылку уведомлений.</span><span class="sxs-lookup"><span data-stu-id="38340-119">There are settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] that affect notifications.</span></span> <span data-ttu-id="38340-120">Эти параметры можно настроить в программе [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] или непосредственно в таблице системных параметров в базе данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38340-120">You can adjust these settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] or directly in the System Settings table in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="38340-121">Дополнительные сведения см. в разделе [Системные параметры (службы Master Data Services)](../../2014/master-data-services/system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="38340-121">For more information, see [System Settings &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="38340-122">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="38340-122">Related Tasks</span></span>  
  
|<span data-ttu-id="38340-123">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="38340-123">Task Description</span></span>|<span data-ttu-id="38340-124">Раздел</span><span class="sxs-lookup"><span data-stu-id="38340-124">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="38340-125">Настройка [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] для отправки уведомлений.</span><span class="sxs-lookup"><span data-stu-id="38340-125">Configure [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] to send email notifications.</span></span>|[<span data-ttu-id="38340-126">Настройка уведомления электронной почты (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="38340-126">Configure Email Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-email-notifications-master-data-services.md)|  
|<span data-ttu-id="38340-127">Настройка [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] для отправки уведомлений при изменении значений атрибутов.</span><span class="sxs-lookup"><span data-stu-id="38340-127">Configure [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to send notifications when attribute values change.</span></span>|[<span data-ttu-id="38340-128">Настройка в бизнес-правилах отправки уведомлений (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="38340-128">Configure Business Rules to Send Notifications &#40;Master Data Services&#41;</span></span>](configure-business-rules-to-send-notifications-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="38340-129">См. также</span><span class="sxs-lookup"><span data-stu-id="38340-129">Related Content</span></span>  
  
-   [<span data-ttu-id="38340-130">Бизнес-правила (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="38340-130">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="38340-131">Версии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="38340-131">Versions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/versions-master-data-services.md)  
  
-   [<span data-ttu-id="38340-132">Устранение неполадок в уведомлениях по электронной почте (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="38340-132">Troubleshooting Email Notifications (Master Data Services)</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-email-notifications-master-data-services.aspx)  
  
  
