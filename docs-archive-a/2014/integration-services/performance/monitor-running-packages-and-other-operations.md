---
title: Мониторинг выполнения пакетов и других операций | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: cbbcd79f-ab9b-46ec-84cb-4821c1d16b99
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 628b62d9c8e01d0dc0bf641551de67c3838a4504
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668994"
---
# <a name="monitoring-for-package-executions-and-other-operations"></a><span data-ttu-id="64beb-102">Наблюдение за выполнением пакетов и других операций</span><span class="sxs-lookup"><span data-stu-id="64beb-102">Monitoring for Package Executions and Other Operations</span></span>
  <span data-ttu-id="64beb-103">Вы можете отслеживать выполнения пакета [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , проверки проекта и другие операции с помощью одного или нескольких из следующих средств.</span><span class="sxs-lookup"><span data-stu-id="64beb-103">You can monitor [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package executions, project validations, and other operations by using one of more of the following tools.</span></span> <span data-ttu-id="64beb-104">Такие средства, как отводы данных, доступны только для проектов, которые развертываются на сервере [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64beb-104">Certain tools such as data taps are available only for projects that are deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
-   <span data-ttu-id="64beb-105">Журналы</span><span class="sxs-lookup"><span data-stu-id="64beb-105">Logs</span></span>  
  
     <span data-ttu-id="64beb-106">Дополнительные сведения см. в разделе [Ведение журналов в службах Integration Services (SSIS)](integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="64beb-106">For more information, see [Integration Services &#40;SSIS&#41; Logging](integration-services-ssis-logging.md).</span></span>  
  
-   <span data-ttu-id="64beb-107">Отчеты</span><span class="sxs-lookup"><span data-stu-id="64beb-107">Reports</span></span>  
  
     <span data-ttu-id="64beb-108">Дополнительные сведения см. в статье [Reports for the Integration Services Server](../reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="64beb-108">For more information, see [Reports for the Integration Services Server](../reports-for-the-integration-services-server.md).</span></span>  
  
-   <span data-ttu-id="64beb-109">Представления</span><span class="sxs-lookup"><span data-stu-id="64beb-109">Views</span></span>  
  
     <span data-ttu-id="64beb-110">Дополнительные сведения см. в статье [Представления (каталог служб Integration Services)](/sql/integration-services/system-views/views-integration-services-catalog).</span><span class="sxs-lookup"><span data-stu-id="64beb-110">For more information, see [Views &#40;Integration Services Catalog&#41;](/sql/integration-services/system-views/views-integration-services-catalog).</span></span>  
  
-   <span data-ttu-id="64beb-111">Счетчики производительности</span><span class="sxs-lookup"><span data-stu-id="64beb-111">Performance counters</span></span>  
  
     <span data-ttu-id="64beb-112">Дополнительные сведения см. в статье [Performance Counters](performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="64beb-112">For more information, see [Performance Counters](performance-counters.md).</span></span>  
  
-   <span data-ttu-id="64beb-113">Отводы данных</span><span class="sxs-lookup"><span data-stu-id="64beb-113">Data taps</span></span>  
  
## <a name="operation-types"></a><span data-ttu-id="64beb-114">Типы операций</span><span class="sxs-lookup"><span data-stu-id="64beb-114">Operation Types</span></span>  
 <span data-ttu-id="64beb-115">В каталоге `SSISDB` на сервере [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] отслеживаются операции нескольких разных типов.</span><span class="sxs-lookup"><span data-stu-id="64beb-115">Several different types of operations are monitored in the `SSISDB` catalog, on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="64beb-116">Каждая операция может иметь несколько связанных с ней сообщений.</span><span class="sxs-lookup"><span data-stu-id="64beb-116">Each operation can have multiple messages associated with it.</span></span> <span data-ttu-id="64beb-117">Каждое сообщение можно отнести к одному из нескольких разных типов.</span><span class="sxs-lookup"><span data-stu-id="64beb-117">Each message can be classified into one of several different types.</span></span> <span data-ttu-id="64beb-118">Например, сообщение может иметь тип «информация», «предупреждение» или «ошибка».</span><span class="sxs-lookup"><span data-stu-id="64beb-118">For example, a message can be of type Information, Warning, or Error.</span></span> <span data-ttu-id="64beb-119">Полный список типов сообщений см. в документации по представлению Transact-SQL [catalog.operation_messages (база данных SSISDB)](/sql/integration-services/system-views/catalog-operation-messages-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="64beb-119">For the full list of message types, see the documentation for the Transact-SQL [catalog.operation_messages &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operation-messages-ssisdb-database) view.</span></span> <span data-ttu-id="64beb-120">Полный список типов операций см. в статье [catalog.operations (база данных SSISDB)](/sql/integration-services/system-views/catalog-operations-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="64beb-120">For a full list of the operations types, see [catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database).</span></span>  
  
 <span data-ttu-id="64beb-121">Для указания состояния операции используются девять различных типов состояний.</span><span class="sxs-lookup"><span data-stu-id="64beb-121">Nine different status types are used to indicate the status of an operation.</span></span> <span data-ttu-id="64beb-122">Полный список типов состояний см. в представлении [catalog.operations (база данных SSISDB)](/sql/integration-services/system-views/catalog-operations-ssisdb-database)</span><span class="sxs-lookup"><span data-stu-id="64beb-122">For a full list of the status types, see the [catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database) view.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="64beb-123">См. также</span><span class="sxs-lookup"><span data-stu-id="64beb-123">Related Content</span></span>  
 <span data-ttu-id="64beb-124">Запись в блоге [Общие сведения о T-SQL API служб SSIS](https://go.microsoft.com/fwlink/?LinkId=249051)на сайте blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="64beb-124">Blog entry, [SSIS T-SQL API Overview](https://go.microsoft.com/fwlink/?LinkId=249051), on blogs.msdn.com.</span></span>  
  
  
