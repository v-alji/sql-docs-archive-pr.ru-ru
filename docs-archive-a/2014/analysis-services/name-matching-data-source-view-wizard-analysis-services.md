---
title: Сопоставление имен (мастер представлений источников данных) (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.datasourceviewwizard.namematchingcriteria.f1
ms.assetid: 7f811e02-0fe6-45c9-a7b7-29c61032d96b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 50cc46db7f582e0aea1570dadc956336ef8be074
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664562"
---
# <a name="name-matching-data-source-view-wizard-analysis-services"></a><span data-ttu-id="c0779-102">Совпадение имен (мастер представлений источников данных) (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="c0779-102">Name Matching (Data Source View Wizard) (Analysis Services)</span></span>
  <span data-ttu-id="c0779-103">Страница **Совпадение имен** используется для выбора критерия для определения возможных связей между таблицами, выбранными для представления источников данных, и другими таблицами схемы.</span><span class="sxs-lookup"><span data-stu-id="c0779-103">Use the **Name Matching** page to select the criterion to use for detecting possible relationships between the tables that you select for the data source view and the other tables in the schema.</span></span> <span data-ttu-id="c0779-104">Если между этими таблицами не существует никаких связей внешних ключей, этот критерий помогает идентифицировать и добавить все связанные таблицы в представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="c0779-104">If no physical foreign key relationships exist between the tables, this criterion helps you identify and add related tables to the data source view.</span></span> <span data-ttu-id="c0779-105">Логические связи, идентифицируемые совпадением имен, также добавляются в представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="c0779-105">The logical relationships that are identified by name matching are also added to the data source view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c0779-106">Данная страница отображается только в случае выбора источника данных, содержащего несколько таблиц без связей внешних ключей между какими-либо из них.</span><span class="sxs-lookup"><span data-stu-id="c0779-106">This page appears only if you select a data source that has multiple tables but no foreign key relationships between any one of the tables.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c0779-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="c0779-107">Options</span></span>  
 <span data-ttu-id="c0779-108">**Создать логические связи по совпадающим столбцам**</span><span class="sxs-lookup"><span data-stu-id="c0779-108">**Create logical relationships by matching columns**</span></span>  
 <span data-ttu-id="c0779-109">Выберите, чтобы использовать критерий совпадения имен для определения возможных логических зависимостей и связей между таблицами, выбранными для включения в представление источника данных, и какими-либо другими таблицами схемы.</span><span class="sxs-lookup"><span data-stu-id="c0779-109">Select to use a name-matching criterion to detect possible logical dependencies and relationships between the tables that you select to include in the data source view and the other tables in the schema.</span></span> <span data-ttu-id="c0779-110">Если этот флажок снят, для идентификации логических связей между таблицами в этом источнике данных не используется никакого критерия совпадения имен.</span><span class="sxs-lookup"><span data-stu-id="c0779-110">If you clear this check box, no name-matching criterion is used to identify logical relationships between tables in the data source.</span></span>  
  
 <span data-ttu-id="c0779-111">**Совпадения внешнего ключа**</span><span class="sxs-lookup"><span data-stu-id="c0779-111">**Foreign key matches**</span></span>  
 <span data-ttu-id="c0779-112">Выберите критерий для использования при создании логических связей между таблицами и представлениями в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="c0779-112">Select the criterion to use for creating logical relationships between tables and views in the data source.</span></span> <span data-ttu-id="c0779-113">Символы, отличные от алфавитно-цифровых, в сравниваемых строках игнорируются.</span><span class="sxs-lookup"><span data-stu-id="c0779-113">Non-alphanumeric characters are ignored in matching strings.</span></span> <span data-ttu-id="c0779-114">Например, «Идентификатор заказчика», «Идентификатор_заказчика», «ИдентификаторЗаказчика» считаются совпадающими.</span><span class="sxs-lookup"><span data-stu-id="c0779-114">For example, "Customer ID", "Customer_ID", "CustomerID" all match.</span></span> <span data-ttu-id="c0779-115">Выберите один из параметров из следующей таблицы для создания связей с определенными условиями.</span><span class="sxs-lookup"><span data-stu-id="c0779-115">Select one of the options in the following table to create relationships under the specified conditions.</span></span>  
  
|<span data-ttu-id="c0779-116">Выберите пункт</span><span class="sxs-lookup"><span data-stu-id="c0779-116">Select</span></span>|<span data-ttu-id="c0779-117">Чтобы создать</span><span class="sxs-lookup"><span data-stu-id="c0779-117">To create</span></span>|  
|------------|---------------|  
|<span data-ttu-id="c0779-118">**То же имя, что и у первичного ключа**</span><span class="sxs-lookup"><span data-stu-id="c0779-118">**Same name as primary key**</span></span>|<span data-ttu-id="c0779-119">Логическая связь с какой-либо таблицей с именем столбца, совпадающим с именем первичного ключевого столбца в выбранной таблице.</span><span class="sxs-lookup"><span data-stu-id="c0779-119">A logical relationship to any table with a column name that matches the name of the primary key column in a selected table.</span></span>|  
|<span data-ttu-id="c0779-120">**То же имя, что и у целевой таблицы**</span><span class="sxs-lookup"><span data-stu-id="c0779-120">**Same name as destination table name**</span></span>|<span data-ttu-id="c0779-121">Логическая связь с какой-либо таблицей с именем столбца, совпадающим с именем выбранной таблицы.</span><span class="sxs-lookup"><span data-stu-id="c0779-121">A logical relationship to any table with a column name that matches the name of a selected table.</span></span>|  
|<span data-ttu-id="c0779-122">**Имя целевой таблицы + имя первичного ключа**</span><span class="sxs-lookup"><span data-stu-id="c0779-122">**Destination table name + primary key name**</span></span>|<span data-ttu-id="c0779-123">Логическая связь с какой-либо таблицей, в которой имя столбца совпадает с результатом сцепления имени выбранной таблицы и имени первичного ключевого столбца выбранной таблицы, именно в таком порядке.</span><span class="sxs-lookup"><span data-stu-id="c0779-123">A logical relationship to any table in which a column name matches the selected table name concatenated with the name of the primary key column for the selected table, in that order.</span></span> <span data-ttu-id="c0779-124">Символы, отличные от алфавитно-цифровых, в пределах объединения не учитываются (например, «Идентификатор продукта», «Идентификатор_продукта» и «Идентификаторпродукта» считаются совпадающими).</span><span class="sxs-lookup"><span data-stu-id="c0779-124">Non-alphanumeric characters within the concatenation are ignored (for example, "Product ID", "Product_ID" and "ProductID" all match).</span></span>|  
  
 <span data-ttu-id="c0779-125">**Описание и пример**</span><span class="sxs-lookup"><span data-stu-id="c0779-125">**Description and sample**</span></span>  
 <span data-ttu-id="c0779-126">Позволяет просмотреть описание и пример выбранного критерия.</span><span class="sxs-lookup"><span data-stu-id="c0779-126">View a description and a sample of the selected criterion.</span></span>  
  
  
