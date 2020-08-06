---
title: Импорт данных (Master Data Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- staging process [Master Data Services], about staging process
- importing data [Master Data Services]
- staging process [Master Data Services]
ms.assetid: 181d1e22-379c-45d1-b03c-e1e22ff14164
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 403eca212611397fb3ba30f8fe12a2aa8b5e83ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655267"
---
# <a name="data-import-master-data-services"></a><span data-ttu-id="5ff2b-102">Импорт данных (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5ff2b-102">Data Import (Master Data Services)</span></span>
  <span data-ttu-id="5ff2b-103">После создания модели для данных в [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]можно добавлять данные и вносить в них изменения в базе данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5ff2b-103">Once you've created a model for your data in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can start adding data and make changes to data in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>   <span data-ttu-id="5ff2b-104">Используются промежуточные таблицы [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] , хранимые процедуры и диспетчер основных данных.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-104">You use [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] staging tables, stored procedures and Master Data Manager .</span></span>

 <span data-ttu-id="5ff2b-105">Можно также использовать [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] для добавления данных в репозиторий MDS ( [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] база данных).</span><span class="sxs-lookup"><span data-stu-id="5ff2b-105">You can also use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)], to add data to the MDS repository ([!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database).</span></span> <span data-ttu-id="5ff2b-106">Дополнительные сведения см. в разделе [Publishing Data &#40;надстройка MDS для Excel&#41;](microsoft-excel-add-in/overview-importing-data-from-excel-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="5ff2b-106">For more information, see [Publishing Data &#40;MDS Add-in for Excel&#41;](microsoft-excel-add-in/overview-importing-data-from-excel-mds-add-in-for-excel.md).</span></span>

 <span data-ttu-id="5ff2b-107">При добавлении или обновлении данных можно выполнять следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-107">When you add and update data, you can do the following.</span></span>

-   <span data-ttu-id="5ff2b-108">Загружать и обновлять элементы и обновлять значения атрибутов</span><span class="sxs-lookup"><span data-stu-id="5ff2b-108">Load and update members, and update attribute values</span></span>

-   <span data-ttu-id="5ff2b-109">Деактивировать или удалять элементы</span><span class="sxs-lookup"><span data-stu-id="5ff2b-109">Deactivate and delete members</span></span>

-   <span data-ttu-id="5ff2b-110">Перемещать элементы явной иерархии</span><span class="sxs-lookup"><span data-stu-id="5ff2b-110">Move explicit hierarchy members</span></span>

 <span data-ttu-id="5ff2b-111">Добавление и обновление данных включает следующие основные задачи.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-111">Adding and updating data  includes the following main tasks.</span></span>

1.  <span data-ttu-id="5ff2b-112">Загрузка данных в промежуточные таблицы в базу данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5ff2b-112">Load data into the staging tables in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>

2.  <span data-ttu-id="5ff2b-113">Загрузка данных из промежуточных таблиц в соответствующие таблицы [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5ff2b-113">Load the data from the staging tables into the appropriate [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] tables.</span></span>

     <span data-ttu-id="5ff2b-114">Для загрузки данных используются промежуточные хранимые процедуры или [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5ff2b-114">You use staging stored procedures or [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to load the data.</span></span>

> [!NOTE]
>  <span data-ttu-id="5ff2b-115">В [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]прекращена поддержка промежуточных процедур [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5ff2b-115">In [!INCLUDE[ssSQL14](../includes/sssql14-md.md)], support for the [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] staging processes is deprecated.</span></span>

## <a name="deactivating-and-deleting-members"></a><span data-ttu-id="5ff2b-116">Деактивация и удаление элементов</span><span class="sxs-lookup"><span data-stu-id="5ff2b-116">Deactivating and Deleting Members</span></span>
 <span data-ttu-id="5ff2b-117">Отключение означает, что элемент может быть активирован повторно.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-117">Deactivating means the member can be reactivated.</span></span> <span data-ttu-id="5ff2b-118">Если элемент включен повторно, то его атрибуты и членство в иерархиях и коллекциях восстанавливаются.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-118">If you reactivate a member, its attributes and its membership in hierarchies and collections are restored.</span></span> <span data-ttu-id="5ff2b-119">Все предыдущие транзакции являются неизменными.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-119">All previous transactions are intact.</span></span> <span data-ttu-id="5ff2b-120">Транзакции отключения отслеживаются администраторами в функциональной области **Управление версиями** диспетчера основных данных.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-120">Deactivation transactions are visible to administrators in the **Version Management** functional area of the Master Data Manager.</span></span>

 <span data-ttu-id="5ff2b-121">Удаление означает окончательное удаление элемента из системы.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-121">Deleting means purging the member from the system permanently.</span></span> <span data-ttu-id="5ff2b-122">Все транзакции для элемента, все связи и все атрибуты будут окончательно удалены.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-122">All transactions for the member, all relationships, and all attributes are permanently deleted.</span></span>

> [!NOTE]
>  <span data-ttu-id="5ff2b-123">Использовать промежуточное хранение данных для повторной активации элементов невозможно.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-123">You cannot use staging to reactivate members.</span></span> <span data-ttu-id="5ff2b-124">Повторную активацию необходимо выполнять вручную в диспетчере основных данных.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-124">You must do it manually in the Master Data Manager.</span></span> <span data-ttu-id="5ff2b-125">Дополнительные сведения см. в разделе [Повторная активация элемента или коллекции (службы Master Data Services)](reactivate-a-member-or-collection-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5ff2b-125">For more information, see [Reactivate a Member or Collection &#40;Master Data Services&#41;](reactivate-a-member-or-collection-master-data-services.md).</span></span>
> 
>  <span data-ttu-id="5ff2b-126">Промежуточное хранение нельзя использовать для удаления или деактивации коллекций.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-126">You cannot use staging to delete or deactivate collections.</span></span> <span data-ttu-id="5ff2b-127">Дополнительные сведения о деактивации коллекций вручную см. в разделе [Удаление элемента или коллекции (службы Master Data Services)](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5ff2b-127">For more information on manually deactivating collections, see [Delete a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md).</span></span>

## <a name="moving-explicit-hierarchy-members"></a><span data-ttu-id="5ff2b-128">Перемещение элементов явной иерархии</span><span class="sxs-lookup"><span data-stu-id="5ff2b-128">Moving explicit hierarchy members</span></span>
 <span data-ttu-id="5ff2b-129">При массовом изменении местоположения элементов в явных иерархиях можно назначать элементы следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-129">When you move the location of members in explicit hierarchies in bulk, you can designate the following.</span></span>

-   <span data-ttu-id="5ff2b-130">Объединенный элемент в качестве родителя другого объединенного элемента.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-130">A consolidated member as a parent of a consolidated member.</span></span>

-   <span data-ttu-id="5ff2b-131">Объединенный элемент в качестве родителя конечного элемента.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-131">A consolidated member as a parent of a leaf member.</span></span>

-   <span data-ttu-id="5ff2b-132">Конечный элемент в качестве одноуровневого элемента для другого конечного или объединенного элемента.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-132">A leaf member as a sibling of a leaf or consolidated member.</span></span>

-   <span data-ttu-id="5ff2b-133">Объединенный элемент в качестве одноуровневого элемента для другого конечного или объединенного элемента.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-133">A consolidated member as a sibling of a leaf or consolidated member.</span></span>

## <a name="staging-tables-and-stored-procedures"></a><span data-ttu-id="5ff2b-134">Промежуточные таблицы и хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="5ff2b-134">Staging Tables and Stored Procedures</span></span>
 <span data-ttu-id="5ff2b-135">База данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] включает следующие типы промежуточных таблиц, которые можно заполнять данными.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-135">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database includes the following types of staging tables that you can populate with your  data.</span></span>

-   [<span data-ttu-id="5ff2b-136">Конечный элемент таблицы элементов (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5ff2b-136">Leaf Member Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/leaf-member-staging-table-master-data-services.md)

-   [<span data-ttu-id="5ff2b-137">Промежуточная таблица консолидированных элементов (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5ff2b-137">Consolidated Member Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-member-staging-table-master-data-services.md)

-   [<span data-ttu-id="5ff2b-138">Промежуточная таблица связей (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5ff2b-138">Relationship Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/relationship-staging-table-master-data-services.md)

 <span data-ttu-id="5ff2b-139">Для каждой сущности в модели есть промежуточная таблица.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-139">For each entity in the model, there is a staging table.</span></span> <span data-ttu-id="5ff2b-140">Имя таблицы обозначает соответствующую сущность и ее тип, например конечный элемент.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-140">The table name indicates the corresponding entity, and the entity type such as leaf member.</span></span> <span data-ttu-id="5ff2b-141">На этом изображении показаны промежуточные таблицы для сущностей валюты, клиента и продукта.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-141">The following image shows the staging tables for the currency, customer, and product entities.</span></span>

 <span data-ttu-id="5ff2b-142">![Промежуточные таблицы в базе данных MDS](../../2014/master-data-services/media/mds-stagingtables.png "Промежуточные таблицы в базе данных MDS")</span><span class="sxs-lookup"><span data-stu-id="5ff2b-142">![Staging Tables in MDS database](../../2014/master-data-services/media/mds-stagingtables.png "Staging Tables in MDS database")</span></span>

 <span data-ttu-id="5ff2b-143">Имя таблицы указывается при создании сущности и не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-143">The name of the  table is specified when an entity is created and cannot be changed.</span></span> <span data-ttu-id="5ff2b-144">Если имя промежуточной таблицы содержит _1 (или другое число), то на момент создания сущности уже существовала другая таблица с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-144">If the staging table name contains a _1 or other number, another table of that name already existed when the entity was created.</span></span>

 <span data-ttu-id="5ff2b-145">[!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] включает следующие типы промежуточных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-145">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] includes the following types of staging stored procedures.</span></span>

-   <span data-ttu-id="5ff2b-146">STG. udp_ \<name> _Leaf</span><span class="sxs-lookup"><span data-stu-id="5ff2b-146">stg.udp_\<name>_Leaf</span></span>

-   <span data-ttu-id="5ff2b-147">STG. udp_ \<name> _Consolidated</span><span class="sxs-lookup"><span data-stu-id="5ff2b-147">stg.udp_\<name>_Consolidated</span></span>

-   <span data-ttu-id="5ff2b-148">STG. udp_ \<name> _Relationship</span><span class="sxs-lookup"><span data-stu-id="5ff2b-148">stg.udp_\<name>_Relationship</span></span>

 <span data-ttu-id="5ff2b-149">Для каждой сущности в модели есть три хранимые процедуры, которые соответствуют конечному элементу, объединенному элементу и промежуточным таблицам связей.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-149">For each entity in the model, there are three stored procedures that correspond to the leaf member, consolidated member, and relationship staging tables.</span></span>  <span data-ttu-id="5ff2b-150">На следующем изображении показаны промежуточные хранимые процедуры для сущностей валюты, клиента и продукта.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-150">The following image shows the staging stored procedures for the currency, customer, and product entities.</span></span>

 <span data-ttu-id="5ff2b-151">![Промежуточные хранимые процедуры в базе данных MDS](../../2014/master-data-services/media/mds-stagingstoredprocedures.png "Промежуточные хранимые процедуры в базе данных MDS")</span><span class="sxs-lookup"><span data-stu-id="5ff2b-151">![Staging Stored Procedures in MDS database](../../2014/master-data-services/media/mds-stagingstoredprocedures.png "Staging Stored Procedures in MDS database")</span></span>

 <span data-ttu-id="5ff2b-152">Дополнительные сведения о хранимых процедурах см. в разделе [Промежуточная хранимая процедура (службы Master Data Services)](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5ff2b-152">For more information on the stored procedures, see [Staging Stored Procedure &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span></span>

## <a name="logging-transactions"></a><span data-ttu-id="5ff2b-153">Регистрация транзакций</span><span class="sxs-lookup"><span data-stu-id="5ff2b-153">Logging Transactions</span></span>
 <span data-ttu-id="5ff2b-154">Все транзакции, происходящие при импорте или обновлении данных или связей, можно регистрировать.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-154">All transactions that occur when data or relationships are imported or updated can be logged.</span></span> <span data-ttu-id="5ff2b-155">Параметр хранимой процедуры позволяет такую регистрацию.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-155">An option in the stored procedure allows this logging.</span></span> <span data-ttu-id="5ff2b-156">При запуске промежуточного процесса с помощью [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]регистрация не осуществляется.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-156">If you initiate the staging process using [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], no logging occurs.</span></span>

 <span data-ttu-id="5ff2b-157">В [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)]параметр **Регистрация промежуточных транзакций** не применяется к этому методу промежуточной обработки данных.</span><span class="sxs-lookup"><span data-stu-id="5ff2b-157">In [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)], the **Log staging transactions** setting does not apply to this method of staging data.</span></span>

## <a name="related-content"></a><span data-ttu-id="5ff2b-158">См. также</span><span class="sxs-lookup"><span data-stu-id="5ff2b-158">Related Content</span></span>

-   [<span data-ttu-id="5ff2b-159">Проверка (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5ff2b-159">Validation &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validation-master-data-services.md)

-   [<span data-ttu-id="5ff2b-160">Бизнес-правила (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5ff2b-160">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)


