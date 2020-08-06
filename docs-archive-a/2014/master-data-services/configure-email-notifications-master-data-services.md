---
title: Настройка уведомлений электронной почты (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- e-mail [Master Data Services], configuring
- notifications [Master Data Services], configuring notifications
ms.assetid: 4241a6ab-7465-471b-9890-57c6b572037e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: baf60677435122af00f5ee5492e47bafaa45a3ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669459"
---
# <a name="configure-email-notifications-master-data-services"></a><span data-ttu-id="4b9a6-102">Настройка уведомления электронной почты (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="4b9a6-102">Configure Email Notifications (Master Data Services)</span></span>
  <span data-ttu-id="4b9a6-103">Настройка автоматической отправки уведомлений по электронной почте в [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b9a6-103">Configure notification emails when you want [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] to send email messages automatically.</span></span>  
  
### <a name="to-configure-notifications"></a><span data-ttu-id="4b9a6-104">Настройка уведомлений</span><span class="sxs-lookup"><span data-stu-id="4b9a6-104">To configure notifications</span></span>  
  
1.  <span data-ttu-id="4b9a6-105">Выберите свою базу данных [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)]на странице **База данных** в [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b9a6-105">In [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)], on the **Database** page, select your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="4b9a6-106">В разделе **Системные настройки** нажмите **Создать профиль**.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-106">In the **System Settings** section, click **Create Profile**.</span></span>  
  
3.  <span data-ttu-id="4b9a6-107">Заполните все необходимые поля.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-107">Complete all required fields.</span></span> <span data-ttu-id="4b9a6-108">Дополнительные сведения см. в разделе [Диалоговое окно "Создание профиля электронной почты и учетной записи базы данных" (диспетчер конфигурации служб Master Data Services)](../../2014/master-data-services/create-database-mail-profile-and-account-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="4b9a6-108">For more information, see [Create Database Mail Profile and Account Dialog Box &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/create-database-mail-profile-and-account-dialog-box.md).</span></span>  
  
4.  <span data-ttu-id="4b9a6-109">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-109">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4b9a6-110">После настройки уведомлений вносить изменения с помощью [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] нельзя.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-110">After you configure notifications, you cannot use [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] to make changes.</span></span> <span data-ttu-id="4b9a6-111">Это нужно делать непосредственно в базе данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b9a6-111">You must make changes directly in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="4b9a6-112">Дополнительные сведения см. в статье [Database Mail Configuration Objects](../relational-databases/database-mail/database-mail-configuration-objects.md).</span><span class="sxs-lookup"><span data-stu-id="4b9a6-112">For more information, see [Database Mail Configuration Objects](../relational-databases/database-mail/database-mail-configuration-objects.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4b9a6-113">Next Steps</span><span class="sxs-lookup"><span data-stu-id="4b9a6-113">Next Steps</span></span>  
  
-   <span data-ttu-id="4b9a6-114">В [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] есть параметры, влияющие на рассылку уведомлений.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-114">There are settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] that affect notifications.</span></span> <span data-ttu-id="4b9a6-115">Эти параметры можно настроить в программе [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] или непосредственно в таблице системных параметров в базе данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b9a6-115">You can adjust these settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] or directly in the System Settings table in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="4b9a6-116">Дополнительные сведения см. в разделе [Системные параметры (службы Master Data Services)](system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="4b9a6-116">For more information, see [System Settings &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b9a6-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="4b9a6-117">See Also</span></span>  
 <span data-ttu-id="4b9a6-118">[Master Data Services &#40;уведомлений&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4b9a6-118">[Notifications &#40;Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span></span>  
 <span data-ttu-id="4b9a6-119">[Устранение неполадок с уведомлениями по электронной почте (Master Data Services)](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-email-notifications-master-data-services.aspx) </span><span class="sxs-lookup"><span data-stu-id="4b9a6-119">[Troubleshooting Email Notifications (Master Data Services)](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-email-notifications-master-data-services.aspx) </span></span>  
 [<span data-ttu-id="4b9a6-120">Настройка в бизнес-правилах отправки уведомлений (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="4b9a6-120">Configure Business Rules to Send Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md)  
  
  
