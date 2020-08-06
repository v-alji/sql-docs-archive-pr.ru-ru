---
title: Связывание базы данных служб Master Data Services и веб-приложения | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: ccb25672-f71d-4135-b548-f50eb45d8fa5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 01afde6aea5065a51cb9e7ae5dc4151e9f1e9fc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729550"
---
# <a name="associate-a-master-data-services-database-and-web-application"></a><span data-ttu-id="9a574-102">Связывание базы данных служб Master Data Services и веб-приложения</span><span class="sxs-lookup"><span data-stu-id="9a574-102">Associate a Master Data Services Database and Web Application</span></span>
  <span data-ttu-id="9a574-103">Чтобы указать базу данных, используемую для веб-операций, нужно связать веб-приложение [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] с базой данных служб [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a574-103">Associate your [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application with a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database to specify the database to use for web operations.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9a574-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9a574-104">Prerequisites</span></span>  
  
-   [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] <span data-ttu-id="9a574-105">.</span><span class="sxs-lookup"><span data-stu-id="9a574-105">must be installed on the local computer.</span></span> <span data-ttu-id="9a574-106">Дополнительные сведения см. в статье [Установка служб Master Data Services](install-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9a574-106">For more information, see [Install Master Data Services](install-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="9a574-107">Должно существовать локальное веб-приложение [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a574-107">A local [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application must exist.</span></span> <span data-ttu-id="9a574-108">Дополнительные сведения см. в статье [Создание веб-приложения мастера основных данных (службы Master Data Services)](create-a-master-data-manager-web-application-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9a574-108">For more information, see [Create a Master Data Manager Web Application &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="9a574-109">Должна существовать локальная или удаленная база данных служб [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a574-109">Either a local or remote [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database must exist.</span></span> <span data-ttu-id="9a574-110">Дополнительные сведения см. в статье [Создание базы данных служб Master Data Services](create-a-master-data-services-database.md).</span><span class="sxs-lookup"><span data-stu-id="9a574-110">For more information, see [Create a Master Data Services Database](create-a-master-data-services-database.md).</span></span>  
  
### <a name="to-associate-a-master-data-services-database-and-web-application"></a><span data-ttu-id="9a574-111">Связывание базы данных служб Master Data Services и веб-приложения</span><span class="sxs-lookup"><span data-stu-id="9a574-111">To associate a Master Data Services database and web application</span></span>  
  
1.  <span data-ttu-id="9a574-112">Откройте среду [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a574-112">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="9a574-113">На панели слева щелкните элемент **Веб-конфигурация**.</span><span class="sxs-lookup"><span data-stu-id="9a574-113">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="9a574-114">В списке **Веб-сайт** раздела **Веб-приложение**страницы **Веб-конфигурация** выберите веб-сайт, на котором размещено веб-приложение [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a574-114">On the **Web Configuration** page, under **Web application**, from the **Website** list, select the website that contains your [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
4.  <span data-ttu-id="9a574-115">В поле **Веб-приложение** выберите веб-приложение, в котором размещается [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a574-115">In the **Web application** box, select the web application that hosts [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>  
  
5.  <span data-ttu-id="9a574-116">В разделе **Связь приложения с базой данных**щелкните элемент **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="9a574-116">Under **Associate Application with Database**, click **Select**.</span></span> <span data-ttu-id="9a574-117">Откроется диалоговое окно **Подключение к базе данных** .</span><span class="sxs-lookup"><span data-stu-id="9a574-117">The **Connect to Database** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="9a574-118">Укажите сведения о соединении для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , на котором размещена база данных [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] , и щелкните **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="9a574-118">Specify connection information for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database, and click **Connect**.</span></span>  
  
7.  <span data-ttu-id="9a574-119">В списке **База данных служб Master Data Services** выберите базу данных, которую нужно связать с веб-приложением, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9a574-119">From the **Master Data Services database** list, select the database you want to associate the web application with and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="9a574-120">В разделе **Связь приложения с базой данных**удостоверьтесь, что сведения об экземпляре и базе данных верны, а затем нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="9a574-120">Under **Associate Application with Database**, verify that the instance and database information are correct, and then click **Apply**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9a574-121">Next Steps</span><span class="sxs-lookup"><span data-stu-id="9a574-121">Next Steps</span></span>  
  
-   <span data-ttu-id="9a574-122">Программный доступ к веб-службам [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] автоматически включается после создания веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="9a574-122">Programmatic access to [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web services is automatically enabled when the web application is created.</span></span> <span data-ttu-id="9a574-123">Включите публикацию метаданных, чтобы разработчики могли обращаться к метаданным служб и легко создавать классы-посредники для программного доступа.</span><span class="sxs-lookup"><span data-stu-id="9a574-123">To let developers access the service metadata to easily generate proxy classes for programmatic access, enable metadata publishing.</span></span> <span data-ttu-id="9a574-124">Дополнительные сведения см. в статье [Create Master Data Manager Web Service Proxy Classes](../develop/create-master-data-manager-web-service-proxy-classes.md).</span><span class="sxs-lookup"><span data-stu-id="9a574-124">For more information, see [Create Master Data Manager Web Service Proxy Classes](../develop/create-master-data-manager-web-service-proxy-classes.md).</span></span>  
  
-   <span data-ttu-id="9a574-125">Добавьте пользователей и группы в [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a574-125">Add users and groups to [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span> <span data-ttu-id="9a574-126">Если ни одной группе или пользователю не предоставлен доступ к [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], необходимо открыть [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] , используя учетные данные системного администратора среды [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a574-126">If no users or groups have been granted access to [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], you must open [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] using the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] system administrator credentials.</span></span> <span data-ttu-id="9a574-127">Дополнительные сведения см. в статьях [Администраторы (службы Master Data Services)](../administrators-master-data-services.md) и [Пользователи и группы (службы Master Data Services)](../users-and-groups-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9a574-127">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md) and [Users and Groups &#40;Master Data Services&#41;](../users-and-groups-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a574-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="9a574-128">See Also</span></span>  
 <span data-ttu-id="9a574-129">[Установка Master Data Services](install-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9a574-129">[Install Master Data Services](install-master-data-services.md) </span></span>  
 [<span data-ttu-id="9a574-130">Страница "Веб-конфигурация" (диспетчер конфигурации Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9a574-130">Web Configuration Page &#40;Master Data Services Configuration Manager&#41;</span></span>](../web-configuration-page-master-data-services-configuration-manager.md)  
  
  
