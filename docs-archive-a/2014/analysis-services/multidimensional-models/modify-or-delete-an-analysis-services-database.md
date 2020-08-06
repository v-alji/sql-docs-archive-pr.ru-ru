---
title: Изменение или удаление базы данных Analysis Services | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- databases [Analysis Services], modifying
- removing databases
- deleting databases
- dropping databases
- databases [Analysis Services], deleting
- modifying databases
ms.assetid: e48e3988-c091-4379-aabc-4da62f709a7e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6182e91bd95754fe639e8a48548b5cab1835bdc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740553"
---
# <a name="modify-or-delete-an-analysis-services-database"></a><span data-ttu-id="5cfa2-102">Изменение или удаление базы данных служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="5cfa2-102">Modify or Delete an Analysis Services Database</span></span>
  <span data-ttu-id="5cfa2-103">Имя и описание базы данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] перед развертыванием можно изменить в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , а после развертывания — в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5cfa2-103">You can change the name and description of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database before deployment in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and after deployment in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="5cfa2-104">Можно также изменять дополнительные настройки в базе данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в зависимости от среды.</span><span class="sxs-lookup"><span data-stu-id="5cfa2-104">You can also adjust additional settings on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, depending on the environment.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5cfa2-105">Нельзя изменять свойства базы данных, используя среду [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="5cfa2-105">You cannot change database properties using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in online mode.</span></span>  
  
## <a name="modifying-databases-using-sql-server-management-studio"></a><span data-ttu-id="5cfa2-106">Изменение баз данных с помощью среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5cfa2-106">Modifying Databases Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="5cfa2-107">После развертывания базы данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] можно использовать среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , чтобы изменить режим олицетворения, используемый службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] при подключении к источникам данных, содержащимся в этой базе данных.</span><span class="sxs-lookup"><span data-stu-id="5cfa2-107">Once an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database is deployed, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to change the impersonation mode used by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] when connecting to data sources contained by the database.</span></span> <span data-ttu-id="5cfa2-108">Режим олицетворения позволяет задать контекст безопасности, используемый службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] при попытке подключения к источнику данных для обработки, просмотра или детализации.</span><span class="sxs-lookup"><span data-stu-id="5cfa2-108">The impersonation mode allows you to specify the security context used by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] when attempting to connect to a data source for processing, browsing, or drillthrough purposes.</span></span>  
  
## <a name="modifying-databases-using-sql-server-data-tools"></a><span data-ttu-id="5cfa2-109">Изменение баз данных с помощью средств SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="5cfa2-109">Modifying Databases Using SQL Server Data Tools</span></span>  
 <span data-ttu-id="5cfa2-110">Можно использовать среду [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] в режиме проекта, чтобы изменить переводы для заголовка и описания проекта служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , используемого для определения базы данных.</span><span class="sxs-lookup"><span data-stu-id="5cfa2-110">You can use [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in project mode to modify the translations for the caption and description of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project used to define a database.</span></span> <span data-ttu-id="5cfa2-111">Дополнительные сведения об использовании переводов в [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] базе данных см. в разделе [сценарии глобализации для Analysis Services многомерных](../globalization-scenarios-for-analysis-services-multiidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="5cfa2-111">For more information about using translations in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, see [Globalization scenarios for Analysis Services Multiidimensional](../globalization-scenarios-for-analysis-services-multiidimensional.md).</span></span>  
  
 <span data-ttu-id="5cfa2-112">Можно также установить псевдонимы и статистические функции, связанные с типами счетов, используемыми атрибутами счетов в измерениях, содержащихся в базе данных.</span><span class="sxs-lookup"><span data-stu-id="5cfa2-112">You can also set the aliases and aggregation functions associated with account types used by account attributes in dimensions contained by the database.</span></span> <span data-ttu-id="5cfa2-113">Псевдонимы позволяют выбрать специфическую терминологию, используемую в организации для типов счетов в плане счетов.</span><span class="sxs-lookup"><span data-stu-id="5cfa2-113">Aliases allow you to select the business-specific terminology used by your organization for the account types in a chart of accounts.</span></span> <span data-ttu-id="5cfa2-114">Типы счетов используются элементами атрибута счетов для указания способов статистической обработки мер по каждому элементу с использованием статистических функций, указанных для каждого типа счета, содержащегося в базе данных.</span><span class="sxs-lookup"><span data-stu-id="5cfa2-114">The account types are used by members of an account attribute to indicate how to aggregate measures over each member by using the aggregation functions specified for each account type contained in the database.</span></span> <span data-ttu-id="5cfa2-115">Дополнительные сведения об атрибутах учетной записи см. в статье [Атрибуты и иерархии атрибутов](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="5cfa2-115">For more information about account attributes, see [Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md).</span></span>  
  
## <a name="deleting-databases"></a><span data-ttu-id="5cfa2-116">удаление баз данных</span><span class="sxs-lookup"><span data-stu-id="5cfa2-116">Deleting Databases</span></span>  
 <span data-ttu-id="5cfa2-117">При удалении существующей базы данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] удаляются база данных и все кубы, измерения и модели интеллектуального анализа данных, содержащиеся в этой базе данных.</span><span class="sxs-lookup"><span data-stu-id="5cfa2-117">Deleting an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database deletes the database and all cubes, dimensions, and mining models in the database.</span></span> <span data-ttu-id="5cfa2-118">Удалить существующую базу данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] можно только в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5cfa2-118">You can only delete an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-delete-an-analysis-services-database"></a><span data-ttu-id="5cfa2-119">Удаление базы данных служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="5cfa2-119">To delete an Analysis Services database</span></span>  
  
1.  <span data-ttu-id="5cfa2-120">Подключитесь к экземпляру служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5cfa2-120">Connect to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
2.  <span data-ttu-id="5cfa2-121">В окне **Обозреватель объектов**разверните узел для подключенного экземпляра служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] и убедитесь, что объект, который требуется удалить, видимый.</span><span class="sxs-lookup"><span data-stu-id="5cfa2-121">In **Object Explorer**, expand the node for the connected [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and ensure that the object to be deleted is visible.</span></span>  
  
3.  <span data-ttu-id="5cfa2-122">Щелкните правой кнопкой мыши объект, который требуется удалить, и выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="5cfa2-122">Right-click the object to be deleted and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="5cfa2-123">В диалоговом окне **Удаление объекта** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5cfa2-123">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cfa2-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="5cfa2-124">See Also</span></span>  
 [<span data-ttu-id="5cfa2-125">Документирование и работа со скриптами в базе данных служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="5cfa2-125">Document and Script an Analysis Services Database</span></span>](document-and-script-an-analysis-services-database.md)  
  
  
