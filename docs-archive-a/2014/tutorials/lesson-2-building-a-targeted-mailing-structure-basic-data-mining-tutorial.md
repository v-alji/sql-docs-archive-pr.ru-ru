---
title: Занятие 2. Создание структуры целевой рассылки (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 9d0d6ceb-49b5-47c7-9ee6-464da43cc1f6
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 005baa09e802a9ffe98f87239070401f170ddfa9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654678"
---
# <a name="lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial"></a><span data-ttu-id="42a83-102">Занятие 2. Создание структуры целевой рассылки (учебник по интеллектуальному анализу данных — базовый)</span><span class="sxs-lookup"><span data-stu-id="42a83-102">Lesson 2: Building a Targeted Mailing Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="42a83-103">Отдел маркетинга компании [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] получил задачу увеличить объемы продаж за счет привлечения индивидуальных заказчиков с помощью прямой почтовой рассылки.</span><span class="sxs-lookup"><span data-stu-id="42a83-103">The Marketing department of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] wants to increase sales by targeting specific customers for a mailing campaign.</span></span> <span data-ttu-id="42a83-104">База данных компании содержит список прошлых клиентов и список потенциальных новых клиентов.</span><span class="sxs-lookup"><span data-stu-id="42a83-104">The company's database contains a list of past customers and a list of potential new customers.</span></span> <span data-ttu-id="42a83-105">Изучая атрибуты предыдущих клиентов, компания надеетсяся на обнаружение шаблонов, которые затем могут быть применены к потенциальным клиентам.</span><span class="sxs-lookup"><span data-stu-id="42a83-105">By investigating the attributes of previous customers, the company hopes to discover patterns that they can then apply to potential customers.</span></span> <span data-ttu-id="42a83-106">Например, они могут использовать прошлые тенденции для прогнозирования того, какие потенциальные клиенты чаще всего приобретают велосипед [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] , или создавать сегменты клиентов для будущих маркетинговых кампаний.</span><span class="sxs-lookup"><span data-stu-id="42a83-106">For example, they might use past trends to predict which potential customers are most likely to purchase a bike from [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], or create customer segments for future marketing campaigns.</span></span>  
  
 <span data-ttu-id="42a83-107">На этом занятии будет использоваться **Мастер интеллектуального анализа данных** для создания структуры целевой рассылки.</span><span class="sxs-lookup"><span data-stu-id="42a83-107">In this lesson you will use the **Data Mining Wizard** to create the targeted mailing structure.</span></span> <span data-ttu-id="42a83-108">В результате выполнения задач этого занятия будет получена структура интеллектуального анализа данных с одной моделью.</span><span class="sxs-lookup"><span data-stu-id="42a83-108">After you complete the tasks in this lesson, you will have a mining structure with a single model.</span></span> <span data-ttu-id="42a83-109">Поскольку создание структуры включает множество шагов и важных концепций, этот процесс был разделен на следующие три задачи:</span><span class="sxs-lookup"><span data-stu-id="42a83-109">Because there are many steps and important concepts involved in creating a structure, we have separated this process into the following three tasks:</span></span>  
  
 [<span data-ttu-id="42a83-110">Создание структуры модели интеллектуального анализа данных с целевой корреспонденцией &#40;учебник по основам интеллектуального анализа&#41;</span><span class="sxs-lookup"><span data-stu-id="42a83-110">Creating a Targeted Mailing Mining Model Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="42a83-111">Выбор типа данных и типа содержимого &#40;учебник по базовому интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="42a83-111">Specifying the Data Type and Content Type &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-the-data-type-and-content-type-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="42a83-112">Указание набора проверочных данных для &#40;учебника по интеллектуальному анализу данных Basic&#41;</span><span class="sxs-lookup"><span data-stu-id="42a83-112">Specifying a Testing Data Set for the Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-a-testing-data-set-for-the-structure-basic-data-mining-tutorial.md)  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="42a83-113">Первая задача занятия</span><span class="sxs-lookup"><span data-stu-id="42a83-113">First Task in Lesson</span></span>  
 [<span data-ttu-id="42a83-114">Создание структуры модели интеллектуального анализа данных с целевой корреспонденцией &#40;учебник по основам интеллектуального анализа&#41;</span><span class="sxs-lookup"><span data-stu-id="42a83-114">Creating a Targeted Mailing Mining Model Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="42a83-115">Предыдущее занятие</span><span class="sxs-lookup"><span data-stu-id="42a83-115">Previous Lesson</span></span>  
 [<span data-ttu-id="42a83-116">Занятие 1. Подготовка Analysis Services базы данных &#40;базовое руководство по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="42a83-116">Lesson 1: Preparing the Analysis Services Database &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-preparing-the-analysis-services-database-basic-data-mining-tutorial.md)  
  
## <a name="next--lesson"></a><span data-ttu-id="42a83-117">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="42a83-117">Next  Lesson</span></span>  
 [<span data-ttu-id="42a83-118">Урок 3. Добавление и обработка моделей</span><span class="sxs-lookup"><span data-stu-id="42a83-118">Lesson 3: Adding and Processing Models</span></span>](../../2014/tutorials/lesson-3-adding-and-processing-models.md)  
  
## <a name="see-also"></a><span data-ttu-id="42a83-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="42a83-119">See Also</span></span>  
 <span data-ttu-id="42a83-120">[Создание структуры интеллектуального анализа данных &#40;мастер интеллектуального анализа данных&#41;](../../2014/analysis-services/create-the-data-mining-structure-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="42a83-120">[Create the Data Mining Structure &#40;Data Mining Wizard&#41;](../../2014/analysis-services/create-the-data-mining-structure-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="42a83-121">Создание реляционной структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="42a83-121">Create a Relational Mining Structure</span></span>](../../2014/analysis-services/data-mining/create-a-relational-mining-structure.md)  
  
  
