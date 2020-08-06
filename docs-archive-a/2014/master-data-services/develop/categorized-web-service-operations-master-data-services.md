---
title: Операции веб-службы по категориям (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: e3f346b5-7e26-481d-9821-1846e2e91289
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0f7dd682f55c16c6dcbff9f0f669593a10486da6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666715"
---
# <a name="categorized-web-service-operations-master-data-services"></a><span data-ttu-id="8fd8c-102">Операции веб-службы по категориям (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="8fd8c-102">Categorized Web Service Operations (Master Data Services)</span></span>
  <span data-ttu-id="8fd8c-103">Веб-служба [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] содержит полный набор операций, позволяющих писать код для управления всеми функциями веб-приложения [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] через его пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8fd8c-103">The [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web service contains a complete set of operations that let you write code to control all of the features that [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] does through its user interface.</span></span> <span data-ttu-id="8fd8c-104">Операции веб-службы определяются интерфейсом <xref:Microsoft.MasterDataServices.IService> и реализуются в виде методов класса <xref:Microsoft.MasterDataServices.ServiceClient>.</span><span class="sxs-lookup"><span data-stu-id="8fd8c-104">The web service operations are defined by the <xref:Microsoft.MasterDataServices.IService> interface and are implemented as methods in the <xref:Microsoft.MasterDataServices.ServiceClient> class.</span></span> <span data-ttu-id="8fd8c-105">В этом разделе операции веб-службы сгруппированы по основным категориям для того, чтобы было проще понять, как пользоваться API-интерфейсом веб-службы.</span><span class="sxs-lookup"><span data-stu-id="8fd8c-105">This topic groups the web service operations into conceptual categories to help you understand how to use the web service API.</span></span>  
  
## <a name="model-operations"></a><span data-ttu-id="8fd8c-106">Операции с моделью</span><span class="sxs-lookup"><span data-stu-id="8fd8c-106">Model Operations</span></span>  
 <span data-ttu-id="8fd8c-107">С помощью этих операций выполняется создание, обновление или удаление моделей, а также управление всем содержимым модели, например сущностями, иерархиями и версиями.</span><span class="sxs-lookup"><span data-stu-id="8fd8c-107">These operations are used to create, update, and delete models, as well as to operate on all the contents of a model, such as entities, hierarchies, and versions.</span></span> <span data-ttu-id="8fd8c-108">Дополнительные сведения см. в разделе [Модели (службы Master Data Services)](../models-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8fd8c-108">For more information, see [Models &#40;Master Data Services&#41;](../models-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataUpdate%2A>|  
  
## <a name="entity-operations"></a><span data-ttu-id="8fd8c-109">Операции с сущностями</span><span class="sxs-lookup"><span data-stu-id="8fd8c-109">Entity Operations</span></span>  
 <span data-ttu-id="8fd8c-110">Эти операции служат для создания, обновления и удаления элементов одной сущности.</span><span class="sxs-lookup"><span data-stu-id="8fd8c-110">These operations are used to create, update, and delete the members of a single entity.</span></span> <span data-ttu-id="8fd8c-111">Дополнительные сведения см. в разделах [Сущности (службы Master Data Services)](../entities-master-data-services.md) и [Элементы (службы Master Data Services)](../members-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8fd8c-111">For more information, see [Entities &#40;Master Data Services&#41;](../entities-master-data-services.md) and [Members &#40;Master Data Services&#41;](../members-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberKeyLookup%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersCopy%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersMerge%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersUpdate%2A>|  
  
## <a name="member-operations"></a><span data-ttu-id="8fd8c-112">Операции с элементами</span><span class="sxs-lookup"><span data-stu-id="8fd8c-112">Member Operations</span></span>  
 <span data-ttu-id="8fd8c-113">Эти операции служат для получения, обновления и удаления элементов.</span><span class="sxs-lookup"><span data-stu-id="8fd8c-113">These operations are used to get, update, and delete members.</span></span> <span data-ttu-id="8fd8c-114">Набор элементов, с которыми выполняется операция, может содержать элементы из нескольких сущностей.</span><span class="sxs-lookup"><span data-stu-id="8fd8c-114">The set of members operated on can contain members from multiple entities.</span></span> <span data-ttu-id="8fd8c-115">Дополнительные сведения см. в разделе [Элементы (службы Master Data Services)](../members-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8fd8c-115">For more information, see [Members &#40;Master Data Services&#41;](../members-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersBulkDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersBulkMerge%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersBulkUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersGet%2A>|  
  
## <a name="attribute-and-hierarchy-operations"></a><span data-ttu-id="8fd8c-116">Операции с атрибутами и иерархиями</span><span class="sxs-lookup"><span data-stu-id="8fd8c-116">Attribute and Hierarchy Operations</span></span>  
 <span data-ttu-id="8fd8c-117">Эти операции служат для получения сведений об атрибутах и иерархиях.</span><span class="sxs-lookup"><span data-stu-id="8fd8c-117">These operations are used to get attribute and hierarchy information.</span></span> <span data-ttu-id="8fd8c-118">Атрибуты и иерархии также можно изменять с помощью операций с моделями, например <xref:Microsoft.MasterDataServices.ServiceClient.MetadataUpdate%2A>.</span><span class="sxs-lookup"><span data-stu-id="8fd8c-118">Attributes and hierarchies can also be modified by using the model operations, such as <xref:Microsoft.MasterDataServices.ServiceClient.MetadataUpdate%2A>.</span></span> <span data-ttu-id="8fd8c-119">Дополнительные сведения см. в разделах [Атрибуты (службы Master Data Services)](../attributes-master-data-services.md) и [Иерархии (службы Master Data Services)](../hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8fd8c-119">For more information, see [Attributes &#40;Master Data Services&#41;](../attributes-master-data-services.md) and [Hierarchies &#40;Master Data Services&#41;](../hierarchies-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberAttributesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.HierarchyMembersGet%2A>|  
  
## <a name="business-rule-operations"></a><span data-ttu-id="8fd8c-120">Операции с бизнес-правилами</span><span class="sxs-lookup"><span data-stu-id="8fd8c-120">Business Rule Operations</span></span>  
 <span data-ttu-id="8fd8c-121">Эти операции используются для создания, обновления, удаления и публикации бизнес-правил.</span><span class="sxs-lookup"><span data-stu-id="8fd8c-121">These operations are used to create, update, delete, and publish business rules.</span></span> <span data-ttu-id="8fd8c-122">Дополнительные сведения см. в статье [Бизнес-правила (службы Master Data Services)](../business-rules-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8fd8c-122">For more information, see [Business Rules &#40;Master Data Services&#41;](../business-rules-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesPaletteGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesPublish%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesUpdate%2A>|  
  
## <a name="annotation-operations"></a><span data-ttu-id="8fd8c-123">Операции с заметками</span><span class="sxs-lookup"><span data-stu-id="8fd8c-123">Annotation Operations</span></span>  
 <span data-ttu-id="8fd8c-124">Эти операции служат для создания, обновления и удаления заметок.</span><span class="sxs-lookup"><span data-stu-id="8fd8c-124">These operations are used to create, update, and delete annotations.</span></span> <span data-ttu-id="8fd8c-125">Дополнительные сведения см. в разделе [Заметки (службы Master Data Services)](../annotations-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8fd8c-125">For more information, see [Annotations &#40;Master Data Services&#41;](../annotations-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.AnnotationsDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.AnnotationsUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberAnnotationsCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberAnnotationsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionAnnotationsCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionAnnotationsGet%2A>|  
  
## <a name="transaction-operations"></a><span data-ttu-id="8fd8c-126">Операции с транзакциями</span><span class="sxs-lookup"><span data-stu-id="8fd8c-126">Transaction Operations</span></span>  
 <span data-ttu-id="8fd8c-127">Эти операции служат для получения и отмены транзакций.</span><span class="sxs-lookup"><span data-stu-id="8fd8c-127">These operations are used to get and reverse transactions.</span></span> <span data-ttu-id="8fd8c-128">Дополнительные сведения см. в разделе [Транзакции (службы Master Data Services)](../transactions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8fd8c-128">For more information, see [Transactions &#40;Master Data Services&#41;](../transactions-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionsReverse%2A>|  
  
## <a name="version-and-validation-operations"></a><span data-ttu-id="8fd8c-129">Операции проверки и операции с версиями</span><span class="sxs-lookup"><span data-stu-id="8fd8c-129">Version and Validation Operations</span></span>  
 <span data-ttu-id="8fd8c-130">Эти операции используются для копирования и проверки версий.</span><span class="sxs-lookup"><span data-stu-id="8fd8c-130">These operations are used to copy and validate versions.</span></span> <span data-ttu-id="8fd8c-131">Дополнительные сведения см. в разделах [Версии (службы Master Data Services)](../versions-master-data-services.md) и [Проверка (службы Master Data Services)](../validation-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8fd8c-131">For more information, see [Versions &#40;Master Data Services&#41;](../versions-master-data-services.md) and [Validation &#40;Master Data Services&#41;](../validation-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.VersionCopy%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ValidationGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ValidationProcess%2A>|  
  
## <a name="data-quality-operations"></a><span data-ttu-id="8fd8c-132">Операции по обеспечению качества данных</span><span class="sxs-lookup"><span data-stu-id="8fd8c-132">Data Quality Operations</span></span>  
 <span data-ttu-id="8fd8c-133">С помощью этих операций выполняются задачи по обеспечению качества данных, а также оценка результатов.</span><span class="sxs-lookup"><span data-stu-id="8fd8c-133">These operations are used to perform data quality tasks and to examine their results.</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityCleansingOperationCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityMatchingOperationCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityOperationStart%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityInstalledState%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityKnowledgeBasesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityOperationResultsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityOperationStatus%2A>|  
  
## <a name="data-import-operations"></a><span data-ttu-id="8fd8c-134">Операции импорта данных</span><span class="sxs-lookup"><span data-stu-id="8fd8c-134">Data Import Operations</span></span>  
 <span data-ttu-id="8fd8c-135">Эти операции используются для импорта данных в базу данных [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8fd8c-135">These operations are used to import data into a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="8fd8c-136">Дополнительные сведения см. в разделе [Импорт данных (службы Master Data Services)](../overview-importing-data-from-tables-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8fd8c-136">For more information, see [Data Import &#40;Master Data Services&#41;](../overview-importing-data-from-tables-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingClear%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingLoad%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingProcess%2A>|  
  
 <span data-ttu-id="8fd8c-137">Следующие операции используются для импорта данных с помощью промежуточного процесса в [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8fd8c-137">The following operations are used to import data by using the staging process included in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="8fd8c-138">Эти операции следует использовать только для поддержки существующих баз данных.</span><span class="sxs-lookup"><span data-stu-id="8fd8c-138">These operations should be used only to support existing databases.</span></span> <span data-ttu-id="8fd8c-139">Для новых разработок используйте приведенные ранее операции.</span><span class="sxs-lookup"><span data-stu-id="8fd8c-139">For new development, use the previously listed operations.</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingClear%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingNameCheck%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingProcess%2A>|  
  
## <a name="data-export-operations"></a><span data-ttu-id="8fd8c-140">Операции экспорта данных</span><span class="sxs-lookup"><span data-stu-id="8fd8c-140">Data Export Operations</span></span>  
 <span data-ttu-id="8fd8c-141">Эти операции используются для экспорта данных посредством использования представлений подписки.</span><span class="sxs-lookup"><span data-stu-id="8fd8c-141">These operations are used to export data through the use of subscription views.</span></span> <span data-ttu-id="8fd8c-142">Дополнительные сведения см. в разделе [Экспорт данных &#40;Master Data Services&#41;](../overview-exporting-data-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8fd8c-142">For more information, see [Exporting Data &#40;Master Data Services&#41;](../overview-exporting-data-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewListGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewUpdate%2A>|  
  
## <a name="security-operations"></a><span data-ttu-id="8fd8c-143">Операции безопасности</span><span class="sxs-lookup"><span data-stu-id="8fd8c-143">Security Operations</span></span>  
 <span data-ttu-id="8fd8c-144">С помощью этих операций выполняется изменение параметров безопасности, управляющих доступом к базе данных [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8fd8c-144">These operations are used to modify the security settings that control access to the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="8fd8c-145">Дополнительные сведения см. в разделе [Безопасность (службы Master Data Services)](../security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8fd8c-145">For more information, see [Security &#40;Master Data Services&#41;](../security-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesUpdate%2A>|  
  
## <a name="system-operations"></a><span data-ttu-id="8fd8c-146">Системные операции</span><span class="sxs-lookup"><span data-stu-id="8fd8c-146">System Operations</span></span>  
 <span data-ttu-id="8fd8c-147">Эти операции используются для определения и обновления параметров системы и персональных настроек пользователя.</span><span class="sxs-lookup"><span data-stu-id="8fd8c-147">These operations are used to get and update system settings and user preferences.</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ServiceCheck%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ServiceVersionGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemDomainListGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemPropertiesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemSettingsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemSettingsUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.UserPreferencesDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.UserPreferencesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.UserPreferencesUpdate%2A>|  
  
  
