---
title: Устаревшие функции Master Data Services в SQL Server 2014 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: d8506bda-66dd-45a4-bfc9-3a10fa665acc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce532e9f407ec475f7e59c0d79659265a9e0bf3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728409"
---
# <a name="deprecated-master-data-services-features-in-sql-server-2014"></a><span data-ttu-id="ad652-102">Устаревшие функции Master Data Services в SQL Server «2014»</span><span class="sxs-lookup"><span data-stu-id="ad652-102">Deprecated Master Data Services Features in SQL Server 2014</span></span>
  <span data-ttu-id="ad652-103">В этом разделе описаны устаревшие функции компонента [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] , которые по-прежнему доступны в [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad652-103">This topic describes the deprecated [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] features that are still available in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="ad652-104">Эти функции будут удалены в следующем выпуске [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad652-104">These features are scheduled to be removed in a future release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ad652-105">Не следует использовать устаревшие функции в новых приложениях.</span><span class="sxs-lookup"><span data-stu-id="ad652-105">Deprecated features should not be used in new applications.</span></span>  
  
## <a name="staging-process"></a><span data-ttu-id="ad652-106">Промежуточный процесс</span><span class="sxs-lookup"><span data-stu-id="ad652-106">Staging Process</span></span>  
 <span data-ttu-id="ad652-107">Промежуточный процесс, который использовался в [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] , более недоступен в веб-приложении [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] ; но по-прежнему доступен в [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad652-107">The staging process that was used in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] is no longer available in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application; however it is still available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ad652-108">Промежуточные ошибки из промежуточного процесса [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] более не отображаются в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="ad652-108">Staging errors from the [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] staging process are no longer displayed in the UI.</span></span> <span data-ttu-id="ad652-109">Коды ошибок, заполняемые во время промежуточного процесса, по-прежнему доступны в промежуточных таблицах, и их можно найти здесь: [https://msdn.microsoft.com/library/ff487022.aspx](https://msdn.microsoft.com/library/ff487022.aspx) .</span><span class="sxs-lookup"><span data-stu-id="ad652-109">Error codes that are populated during the staging process are still available in the staging tables, and can be found here: [https://msdn.microsoft.com/library/ff487022.aspx](https://msdn.microsoft.com/library/ff487022.aspx).</span></span>  
  
 <span data-ttu-id="ad652-110">Промежуточные таблицы (tblStgMember, tblStgMemberAttribute и tblStgRelationship) по-прежнему доступны в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ad652-110">The staging tables (tblStgMember, tblStgMemberAttribute, and tblStgRelationship) are still available in the database.</span></span> <span data-ttu-id="ad652-111">Хранимая процедура, используемая для промежуточного процесса (mdm.udpStagingSweep), по-прежнему доступна в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ad652-111">The stored procedure used to initiate the staging process (mdm.udpStagingSweep) is still available in the database.</span></span>  
  
 <span data-ttu-id="ad652-112">Методы веб-службы, которые вызывают промежуточный процесс, по-прежнему доступны.</span><span class="sxs-lookup"><span data-stu-id="ad652-112">The web service methods that call the staging process are still available.</span></span>  
  
 <span data-ttu-id="ad652-113">Промежуточный интервал, заданный в [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] , применим к промежуточному процессу как в [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] , так и [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad652-113">The staging interval set in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] applies to the staging process in both [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] and [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="ad652-114">В [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]реализован новый, более производительный промежуточный процесс.</span><span class="sxs-lookup"><span data-stu-id="ad652-114">A new, higher performance staging process has been implemented in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="ad652-115">Дополнительные сведения см. в разделе [Импорт данных (службы Master Data Services)](overview-importing-data-from-tables-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ad652-115">For more information, see [Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span></span>  
  
## <a name="metadata"></a><span data-ttu-id="ad652-116">Метаданные</span><span class="sxs-lookup"><span data-stu-id="ad652-116">Metadata</span></span>  
 <span data-ttu-id="ad652-117">Хотя модель «Метаданные» все еще отображается в веб-приложении [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , использовать ее не следует.</span><span class="sxs-lookup"><span data-stu-id="ad652-117">Though the Metadata model is still displayed in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application, it should not be used.</span></span> <span data-ttu-id="ad652-118">В будущем выпуске она будет удалена.</span><span class="sxs-lookup"><span data-stu-id="ad652-118">It will be removed in a future release.</span></span> <span data-ttu-id="ad652-119">Теперь пользователи не могут просматривать метаданные в функциональной области **Обозреватель** и не могут создавать версии модели метаданных.</span><span class="sxs-lookup"><span data-stu-id="ad652-119">Users can also no longer view metadata in the **Explorer** functional area, and you can no longer create versions of the Metadata model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad652-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="ad652-120">See Also</span></span>  
 [<span data-ttu-id="ad652-121">Неподдерживаемые функции служб Master Data Services в SQL Server «2014»</span><span class="sxs-lookup"><span data-stu-id="ad652-121">Discontinued Master Data Services Features in SQL Server 2014</span></span>](discontinued-master-data-services-features.md)  
  
  
