---
title: База данных служб Master Data Services | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- database [Master Data Services], about the database
- database [Master Data Services]
ms.assetid: 5f590cc1-6ec2-4b8c-a598-03de0f6051a0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7e4bae180dfb7c9051d5445a689c44978ef73bfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665392"
---
# <a name="master-data-services-database"></a><span data-ttu-id="2eae2-102">База данных служб Master Data Services</span><span class="sxs-lookup"><span data-stu-id="2eae2-102">Master Data Services Database</span></span>
  <span data-ttu-id="2eae2-103">База данных содержит все сведения, необходимые для системы [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2eae2-103">The database contains all of the information for the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system.</span></span> <span data-ttu-id="2eae2-104">Она является основой для развертывания [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2eae2-104">It is central to a [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] deployment.</span></span> <span data-ttu-id="2eae2-105">База данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2eae2-105">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database:</span></span>  
  
-   <span data-ttu-id="2eae2-106">В ней хранятся параметры, объекты базы данных и данные, необходимые системе [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2eae2-106">Stores the settings, database objects, and data required by the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system.</span></span>  
  
-   <span data-ttu-id="2eae2-107">Содержит промежуточные таблицы, используемые для обработки данных из исходных систем.</span><span class="sxs-lookup"><span data-stu-id="2eae2-107">Contains staging tables that are used to process data from source systems.</span></span>  
  
-   <span data-ttu-id="2eae2-108">Предоставляет схему и объекты базы данных для хранения основных данных из исходных систем.</span><span class="sxs-lookup"><span data-stu-id="2eae2-108">Provides a schema and database objects to store master data from source systems.</span></span>  
  
-   <span data-ttu-id="2eae2-109">Поддерживает управление версиями, в том числе проверку бизнес-правил и уведомления по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="2eae2-109">Supports versioning functionality, including business rule validation and e-mail notifications.</span></span>  
  
-   <span data-ttu-id="2eae2-110">Предоставляет представления для систем-подписчиков, которым надо извлекать данные из базы данных.</span><span class="sxs-lookup"><span data-stu-id="2eae2-110">Provides views for subscribing systems that need to retrieve data from the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2eae2-111">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="2eae2-111">In This Section</span></span>  
  
-   [<span data-ttu-id="2eae2-112">Конечный элемент таблицы элементов (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2eae2-112">Leaf Member Staging Table &#40;Master Data Services&#41;</span></span>](leaf-member-staging-table-master-data-services.md)  
  
-   [<span data-ttu-id="2eae2-113">Промежуточная таблица консолидированных элементов (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2eae2-113">Consolidated Member Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-member-staging-table-master-data-services.md)  
  
-   [<span data-ttu-id="2eae2-114">Промежуточная таблица связей (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2eae2-114">Relationship Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/relationship-staging-table-master-data-services.md)  
  
-   [<span data-ttu-id="2eae2-115">Ошибки промежуточного процесса (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2eae2-115">Staging Process Errors &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/staging-process-errors-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="2eae2-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="2eae2-116">See Also</span></span>  
 <span data-ttu-id="2eae2-117">[Создание базы данных Master Data Services](install-windows/create-a-master-data-services-database.md) </span><span class="sxs-lookup"><span data-stu-id="2eae2-117">[Create a Master Data Services Database](install-windows/create-a-master-data-services-database.md) </span></span>  
 <span data-ttu-id="2eae2-118">[&#40;Master Data Services безопасности объектов базы данных&#41;](../../2014/master-data-services/database-object-security-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2eae2-118">[Database Object Security &#40;Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md) </span></span>  
 [<span data-ttu-id="2eae2-119">Имена входа, пользователи и роли базы данных (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2eae2-119">Database Logins, Users, and Roles &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/database-logins-users-and-roles-master-data-services.md)  
  
  
