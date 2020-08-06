---
title: Преобразование "Очистка DQS" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data correction
- correct data
ms.assetid: d2ec1b1a-c745-4741-b57c-6fdb524a154c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e980497905b8fa96a73516916af17f934221992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655279"
---
# <a name="dqs-cleansing-transformation"></a><span data-ttu-id="d97b2-102">Преобразование «Очистка DQS»</span><span class="sxs-lookup"><span data-stu-id="d97b2-102">DQS Cleansing Transformation</span></span>
  <span data-ttu-id="d97b2-103">Преобразование «Очистка DQS» используется службы Data Quality Services (DQS) для исправления данных из подключенного источника данных путем применения утвержденных правил, созданных для подключенного или аналогичного источника данных.</span><span class="sxs-lookup"><span data-stu-id="d97b2-103">The DQS Cleansing transformation uses Data Quality Services (DQS) to correct data from a connected data source, by applying approved rules that were created for the connected data source or a similar data source.</span></span> <span data-ttu-id="d97b2-104">Дополнительные сведения о правилах исправления данных см. в разделе [DQS Knowledge Bases and Domains](../../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="d97b2-104">For more information about data correction rules, see [DQS Knowledge Bases and Domains](../../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span> <span data-ttu-id="d97b2-105">Дополнительные сведения о службах DQS см. в разделе [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="d97b2-105">For more information DQS, see [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span></span>  
  
 <span data-ttu-id="d97b2-106">Чтобы определить, требуется ли исправление данных, преобразование «Очистка DQS» обрабатывает данные из входного столбца, когда выполняются следующие условия.</span><span class="sxs-lookup"><span data-stu-id="d97b2-106">To determine whether the data has to be corrected, the DQS Cleansing transformation processes data from an input column when the following conditions are true:</span></span>  
  
-   <span data-ttu-id="d97b2-107">Столбец выбран для корректировки данных.</span><span class="sxs-lookup"><span data-stu-id="d97b2-107">The column is selected for data correction.</span></span>  
  
-   <span data-ttu-id="d97b2-108">Данные столбца относятся к типу, пригодному для корректировки данных.</span><span class="sxs-lookup"><span data-stu-id="d97b2-108">The column data type is supported for data correction.</span></span>  
  
-   <span data-ttu-id="d97b2-109">Столбец сопоставлен с доменом, имеющим совместимый тип данных.</span><span class="sxs-lookup"><span data-stu-id="d97b2-109">The column is mapped a domain that has a compatible data type.</span></span>  
  
 <span data-ttu-id="d97b2-110">Преобразование также включает вывод ошибок, настроенный пользователем для обработки ошибок на уровне строк.</span><span class="sxs-lookup"><span data-stu-id="d97b2-110">The transformation also includes an error output that you configure to handle row-level errors.</span></span> <span data-ttu-id="d97b2-111">Чтобы настроить вывод ошибок, запустите **Редактор преобразования «Очистка DQS»** .</span><span class="sxs-lookup"><span data-stu-id="d97b2-111">To configure the error output, use the **DQS Cleansing Transformation Editor**.</span></span>  
  
 <span data-ttu-id="d97b2-112">В поток данных можно включить [Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) для определения строк данных, которые, вероятнее всего, будут повторяться.</span><span class="sxs-lookup"><span data-stu-id="d97b2-112">You can include the [Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) in the data flow to identify rows of data that are likely to be duplicates.</span></span>  
  
## <a name="data-quality-projects-and-values"></a><span data-ttu-id="d97b2-113">Проекты и значения служб DQS</span><span class="sxs-lookup"><span data-stu-id="d97b2-113">Data Quality Projects and Values</span></span>  
 <span data-ttu-id="d97b2-114">При обработке данных с помощью преобразования «Очистка DQS» на сервере DQS создается проект очистки.</span><span class="sxs-lookup"><span data-stu-id="d97b2-114">When you process data with the DQS Cleansing transformation, a cleansing project is created on the Data Quality Server.</span></span> <span data-ttu-id="d97b2-115">Для управления проектом используется клиент DQS.</span><span class="sxs-lookup"><span data-stu-id="d97b2-115">You use the Data Quality Client to manage the project.</span></span> <span data-ttu-id="d97b2-116">Кроме того, можно использовать клиент DQS для импорта значений проекта в домен базы знаний служб DQS.</span><span class="sxs-lookup"><span data-stu-id="d97b2-116">In addition, you can use the Data Quality Client to import the project values into a DQS knowledge base domain.</span></span> <span data-ttu-id="d97b2-117">Можно импортировать значения только в домен (или связанный домен), использование которого было настроено в преобразовании «Очистка DQS».</span><span class="sxs-lookup"><span data-stu-id="d97b2-117">You can import the values only to a domain (or linked domain) that the DQS Cleansing transformation was configured to use.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d97b2-118">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="d97b2-118">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d97b2-119">Открытие проектов служб Integration Services в клиенте DQS</span><span class="sxs-lookup"><span data-stu-id="d97b2-119">Open Integration Services Projects in Data Quality Client</span></span>](../../../data-quality-services/open-integration-services-projects-in-data-quality-client.md)  
  
-   [<span data-ttu-id="d97b2-120">Импорт значений проекта очистки в домен</span><span class="sxs-lookup"><span data-stu-id="d97b2-120">Import Cleansing Project Values into a Domain</span></span>](../../../data-quality-services/import-cleansing-project-values-into-a-domain.md)  
  
-   [<span data-ttu-id="d97b2-121">Применение правил качества данных к источнику данных</span><span class="sxs-lookup"><span data-stu-id="d97b2-121">Apply Data Quality Rules to Data Source</span></span>](apply-data-quality-rules-to-data-source.md)  
  
## <a name="related-content"></a><span data-ttu-id="d97b2-122">См. также</span><span class="sxs-lookup"><span data-stu-id="d97b2-122">Related Content</span></span>  
  
-   [<span data-ttu-id="d97b2-123">Управление &#40;открытие, разблокировка, переименование и удаление&#41; проекта качества данных</span><span class="sxs-lookup"><span data-stu-id="d97b2-123">Manage &#40;Open, Unlock, Rename, and Delete&#41; a Data Quality Project</span></span>](../../../data-quality-services/manage-open-unlock-rename-and-delete-a-data-quality-project.md)  
  
-   <span data-ttu-id="d97b2-124">Статья [Очистка сложных данных с использованием составных доменов](https://social.technet.microsoft.com/wiki/contents/articles/13324.using-dqs-cleansing-complex-data-using-composite-domains.aspx)на сайте social.technet.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d97b2-124">Article, [Cleansing complex data using composite domains](https://social.technet.microsoft.com/wiki/contents/articles/13324.using-dqs-cleansing-complex-data-using-composite-domains.aspx), on social.technet.microsoft.com.</span></span>  
  
  
