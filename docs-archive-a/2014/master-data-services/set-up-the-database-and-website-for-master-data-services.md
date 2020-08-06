---
title: Настройка базы данных и веб-сайта для Master Data Services | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
f1_keywords:
- sql12.mds.configmanager.general.f1
ms.assetid: d50863e7-50d9-4ab8-aabb-fd68e2d132a1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: da797bc6f9838a2baab6cc440cc7d778a7a6e186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668968"
---
# <a name="set-up-the-database-and-website-for-master-data-services"></a><span data-ttu-id="edadd-102">Настройка базы данных и веб-сайта для служб Master Data Services</span><span class="sxs-lookup"><span data-stu-id="edadd-102">Set up the Database and Website for Master Data Services</span></span>
  <span data-ttu-id="edadd-103">Использование [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] для настройки базы данных и веб-сайта для [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (MDS)</span><span class="sxs-lookup"><span data-stu-id="edadd-103">Use the [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] to set up the database and website for [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (MDS)</span></span>  
  
 <span data-ttu-id="edadd-104">Чтобы настроить базу данных и веб-сайт, выполните следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="edadd-104">To set up the database and website, complete the following tasks.</span></span>  
  
1.  <span data-ttu-id="edadd-105">Создайте базу данных с помощью страницы **Конфигурация базы данных** в среде [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="edadd-105">Create a database using the **Database Configuration** page in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span>  
  
     <span data-ttu-id="edadd-106">Дополнительные сведения см. в разделе [&#40;страницы конфигурации базы данных диспетчер конфигурации Master Data Services&#41;](../../2014/master-data-services/database-configuration-page-master-data-services-configuration-manager.md) и [Мастер создания базы данных &#40;Диспетчер конфигурации Master Data Services&#41;](../../2014/master-data-services/create-database-wizard-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="edadd-106">For information, see [Database Configuration Page &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/database-configuration-page-master-data-services-configuration-manager.md) and [Create Database Wizard &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/create-database-wizard-master-data-services-configuration-manager.md).</span></span>  
  
2.  <span data-ttu-id="edadd-107">Создайте новый веб-сайт, выберите веб-сайт по умолчанию или выберите другой существующий веб-сайт с помощью страницы **веб-конфигурация** в [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="edadd-107">Create a new website, select the default website, or select another existing website, using the **Web Configuration** page in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span> <span data-ttu-id="edadd-108">Затем свяжите базу данных MDS с создаваемым или выбранным веб-приложением.</span><span class="sxs-lookup"><span data-stu-id="edadd-108">Then associate the MDS database with the web application you select or create.</span></span>  
  
     <span data-ttu-id="edadd-109">Дополнительные сведения см. в разделе [веб-страница конфигурации &#40;диспетчер конфигурации Master Data Services&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) и [Создание веб-сайта &#40;Диспетчер конфигурации Master Data Services&#41;](../../2014/master-data-services/create-website-dialog-box-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="edadd-109">For information, see [Web Configuration Page &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) and [Create Website Dialog Box &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/create-website-dialog-box-master-data-services-configuration-manager.md).</span></span>  
  
3.  <span data-ttu-id="edadd-110">Используемых Включите интеграцию со службами Data Quality Services с помощью страницы **веб-конфигурация** в [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="edadd-110">(Optional) Enable integration with Data Quality Services using the **Web Configuration** page in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span>  
  
     <span data-ttu-id="edadd-111">Дополнительные сведения см. в разделе [Web Configuration Page &#40;диспетчер конфигурации Master Data Services&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) и [Включение интеграции служб Data Quality Services с Master Data Services](install-windows/enable-data-quality-services-integration-with-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="edadd-111">For more information, see [Web Configuration Page &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) and [Enable Data Quality Services Integration with Master Data Services](install-windows/enable-data-quality-services-integration-with-master-data-services.md).</span></span>  
  
 <span data-ttu-id="edadd-112">Также можно использовать [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] для указания параметров веб-приложений и служб, связанных с базой данных MDS.</span><span class="sxs-lookup"><span data-stu-id="edadd-112">You can also use [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] to specify settings for the web applications and services associated with the MDS database.</span></span> <span data-ttu-id="edadd-113">К примеру, можно указать, как часто загружаются данные или как часто отправляются сообщения проверки.</span><span class="sxs-lookup"><span data-stu-id="edadd-113">For example, you can specify how frequently data is loaded or how often validation emails are sent.</span></span> <span data-ttu-id="edadd-114">Дополнительные сведения см. в разделе [Системные параметры (службы Master Data Services)](../../2014/master-data-services/system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="edadd-114">For more information, see [System Settings &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edadd-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="edadd-115">See Also</span></span>  
 <span data-ttu-id="edadd-116">[База данных Master Data Services](../../2014/master-data-services/master-data-services-database.md) </span><span class="sxs-lookup"><span data-stu-id="edadd-116">[Master Data Services Database](../../2014/master-data-services/master-data-services-database.md) </span></span>  
 [<span data-ttu-id="edadd-117">Веб-приложение диспетчера основных данных</span><span class="sxs-lookup"><span data-stu-id="edadd-117">Master Data Manager Web Application</span></span>](../../2014/master-data-services/master-data-manager-web-application.md)  
  
  
