---
title: Создание базы данных служб Master Data Services | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 8373bb35-f0f9-4c3c-a53c-dfaa2ce567ac
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9ee90ac5d02489da3b411b12389e949ff3136287
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656432"
---
# <a name="create-a-master-data-services-database"></a><span data-ttu-id="9fd4d-102">Создание базы данных служб Master Data Services</span><span class="sxs-lookup"><span data-stu-id="9fd4d-102">Create a Master Data Services Database</span></span>
  <span data-ttu-id="9fd4d-103">Создайте базу данных [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] , если для поддержки веб-приложения [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] и веб-службы [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] требуется новая база данных.</span><span class="sxs-lookup"><span data-stu-id="9fd4d-103">Create a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database when you need a new database to support the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application and [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web service.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9fd4d-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9fd4d-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="9fd4d-105">Дополнительные сведения о требованиях, предъявляемых к компьютеру, на котором размещается база данных, см. в разделе [Требования баз данных (службы Master Data Services)](database-requirements-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9fd4d-105">For information about the requirements for the computer that hosts the database, see [Database Requirements &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span></span>  
  
### <a name="to-create-a-master-data-services-database"></a><span data-ttu-id="9fd4d-106">Создание базы данных служб Master Data Services</span><span class="sxs-lookup"><span data-stu-id="9fd4d-106">To create a Master Data Services database</span></span>  
  
1.  <span data-ttu-id="9fd4d-107">Откройте среду [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9fd4d-107">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="9fd4d-108">На панели слева щелкните **Конфигурация базы данных**.</span><span class="sxs-lookup"><span data-stu-id="9fd4d-108">In the left pane, click **Database Configuration**.</span></span>  
  
3.  <span data-ttu-id="9fd4d-109">На странице **Конфигурация базы данных** выберите **Создать базу данных**.</span><span class="sxs-lookup"><span data-stu-id="9fd4d-109">On the **Database Configuration** page, click **Create Database**.</span></span>  
  
4.  <span data-ttu-id="9fd4d-110">Чтобы создать и настроить базу данных, выполните инструкции мастера **создания базы данных** .</span><span class="sxs-lookup"><span data-stu-id="9fd4d-110">Complete the **Create Database** wizard to create and configure the database.</span></span> <span data-ttu-id="9fd4d-111">Дополнительные сведения о параметрах пользовательского интерфейса в мастере см. в разделе [Создание мастера баз данных (диспетчер конфигураций Master Data Services)](../create-database-wizard-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="9fd4d-111">For information about the user interface (UI) options in the wizard, see [Create Database Wizard &#40;Master Data Services Configuration Manager&#41;](../create-database-wizard-master-data-services-configuration-manager.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9fd4d-112">Next Steps</span><span class="sxs-lookup"><span data-stu-id="9fd4d-112">Next Steps</span></span>  
  
-   <span data-ttu-id="9fd4d-113">Настройте системные параметры базы данных и веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="9fd4d-113">Configure system settings for the database and web application.</span></span> <span data-ttu-id="9fd4d-114">Дополнительные сведения см. в разделе [Системные параметры (службы Master Data Services)](../system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9fd4d-114">For more information, see [System Settings &#40;Master Data Services&#41;](../system-settings-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="9fd4d-115">Создайте веб-приложение [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] , которое будет связано с этой базой данных.</span><span class="sxs-lookup"><span data-stu-id="9fd4d-115">Create a [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application to associate with this database.</span></span> <span data-ttu-id="9fd4d-116">Дополнительные сведения см. в статье [Создание веб-приложения мастера основных данных (службы Master Data Services)](create-a-master-data-manager-web-application-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9fd4d-116">For more information, see [Create a Master Data Manager Web Application &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="9fd4d-117">Настройте план обслуживания для резервного копирования базы данных и журналов транзакций.</span><span class="sxs-lookup"><span data-stu-id="9fd4d-117">Configure a maintenance plan to back up the database and transaction logs.</span></span> <span data-ttu-id="9fd4d-118">Дополнительные сведения см. в разделе [Требования к базе данных (службы Master Data Services)](database-requirements-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9fd4d-118">For more information, see [Database Requirements &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fd4d-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="9fd4d-119">See Also</span></span>  
 [<span data-ttu-id="9fd4d-120">Установка служб Master Data Services</span><span class="sxs-lookup"><span data-stu-id="9fd4d-120">Install Master Data Services</span></span>](install-master-data-services.md)  
  
  
