---
title: Редактор преобразования "Нечеткий уточняющий запрос" (вкладка "ссылочная таблица") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzylookuptransformation.referencetable.f1
helpviewer_keywords:
- Fuzzy Lookup Transformation Editor
ms.assetid: 451f4e7d-1c8e-4784-b540-df0806509bf1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9ce51dd64c9c5807ab23ac645694cfec29a36d52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655844"
---
# <a name="fuzzy-lookup-transformation-editor-reference-table-tab"></a><span data-ttu-id="46e35-102">Редактор преобразования «Нечеткий уточняющий запрос» (вкладка «Ссылочная таблица»)</span><span class="sxs-lookup"><span data-stu-id="46e35-102">Fuzzy Lookup Transformation Editor (Reference Table Tab)</span></span>
  <span data-ttu-id="46e35-103">Вкладка **Ссылочная таблица** в диалоговом окне **Редактор преобразования «Нечеткий уточняющий запрос»** позволяет указать исходную таблицу и индекс поиска.</span><span class="sxs-lookup"><span data-stu-id="46e35-103">Use the **Reference Table** tab of the **Fuzzy Lookup Transformation Editor** dialog box to specify the source table and the index to use for the lookup.</span></span> <span data-ttu-id="46e35-104">Эталонный источник данных должен быть таблицей в базе данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="46e35-104">The reference data source must be a table in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="46e35-105">Преобразование «Нечеткий уточняющий запрос» создает рабочую копию ссылочной таблицы.</span><span class="sxs-lookup"><span data-stu-id="46e35-105">The Fuzzy Lookup transformation creates a working copy of the reference table.</span></span> <span data-ttu-id="46e35-106">В этой рабочей таблице описанные ниже индексы создаются с помощью специальной таблицы, а не обычных индексов [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="46e35-106">The indexes described below are created on this working table by using a special table, not an ordinary [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] index.</span></span> <span data-ttu-id="46e35-107">Преобразование не изменяет существующие исходные таблицы, если не выбран параметр **Поддерживать хранимый индекс**.</span><span class="sxs-lookup"><span data-stu-id="46e35-107">The transformation does not modify the existing source tables unless you select **Maintain stored index**.</span></span> <span data-ttu-id="46e35-108">Если параметр выбран, в таблице ссылок создается триггер, который обновляет рабочую таблицу и таблицу индекса уточняющего запроса при изменениях в ссылочной таблице.</span><span class="sxs-lookup"><span data-stu-id="46e35-108">In this case, it creates a trigger on the reference table that updates the working table and the lookup index table based on changes to the reference table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="46e35-109">`Exhaustive` `MaxMemoryUsage` Свойства и преобразования «Нечеткий уточняющий запрос» недоступны в **редакторе преобразования «Нечеткий уточняющий запрос**», но могут быть установлены с помощью **Расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="46e35-109">The `Exhaustive` and the `MaxMemoryUsage` properties of the Fuzzy Lookup transformation are not available in the **Fuzzy Lookup Transformation Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="46e35-110">Кроме того, значение, превышающее 100, `MaxOutputMatchesPerInput` может быть указано только в **Расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="46e35-110">In addition, a value greater than 100 for `MaxOutputMatchesPerInput` can be specified only in the **Advanced Editor**.</span></span> <span data-ttu-id="46e35-111">Дополнительные сведения об этих свойствах см. в подразделе «Преобразование "Нечеткий уточняющий запрос"» раздела [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="46e35-111">For more information on these properties, see the Fuzzy Lookup Transformation section of [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="46e35-112">Дополнительные сведения о преобразовании «Нечеткий уточняющий запрос» см. в разделе [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="46e35-112">To learn more about the Fuzzy Lookup transformation, see [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="46e35-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="46e35-113">Options</span></span>  
 <span data-ttu-id="46e35-114">**Диспетчер соединений OLE DB**</span><span class="sxs-lookup"><span data-stu-id="46e35-114">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="46e35-115">Выберите существующий диспетчер соединений OLE DB из списка или создайте новое подключение, выбрав пункт **Создать**.</span><span class="sxs-lookup"><span data-stu-id="46e35-115">Select an existing OLE DB connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="46e35-116">**Создать**</span><span class="sxs-lookup"><span data-stu-id="46e35-116">**New**</span></span>  
 <span data-ttu-id="46e35-117">Создайте новое соединение с помощью диалогового окна **Настройка диспетчера соединений OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="46e35-117">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="46e35-118">**Сформировать новый индекс**</span><span class="sxs-lookup"><span data-stu-id="46e35-118">**Generate new index**</span></span>  
 <span data-ttu-id="46e35-119">Укажите в том случае, если преобразование должно создавать новый индекс уточняющего запроса.</span><span class="sxs-lookup"><span data-stu-id="46e35-119">Specify that the transformation should create a new index to use for the lookup.</span></span>  
  
 <span data-ttu-id="46e35-120">**Имя ссылочной таблицы**</span><span class="sxs-lookup"><span data-stu-id="46e35-120">**Reference table name**</span></span>  
 <span data-ttu-id="46e35-121">Выберите таблицу, которая будет использоваться в качестве таблицы ссылок (уточняющего запроса).</span><span class="sxs-lookup"><span data-stu-id="46e35-121">Select the existing table to use as the reference (lookup) table.</span></span>  
  
 <span data-ttu-id="46e35-122">**Сохранить новый индекс**</span><span class="sxs-lookup"><span data-stu-id="46e35-122">**Store new index**</span></span>  
 <span data-ttu-id="46e35-123">Выберите этот параметр, если требуется сохранить новый индекс уточняющего запроса.</span><span class="sxs-lookup"><span data-stu-id="46e35-123">Select this option if you want to save the new lookup index.</span></span>  
  
 <span data-ttu-id="46e35-124">**Имя нового индекса**</span><span class="sxs-lookup"><span data-stu-id="46e35-124">**New index name**</span></span>  
 <span data-ttu-id="46e35-125">Если выбран параметр сохранения нового индекса уточняющего запроса, введите описательное имя индекса.</span><span class="sxs-lookup"><span data-stu-id="46e35-125">If you have chosen to save the new lookup index, type a descriptive name for the index.</span></span>  
  
 <span data-ttu-id="46e35-126">**Поддерживать хранимый индекс**</span><span class="sxs-lookup"><span data-stu-id="46e35-126">**Maintain stored index**</span></span>  
 <span data-ttu-id="46e35-127">Если выбран параметр сохранения нового индекса уточняющего запроса, укажите, должен ли [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] поддерживать этот индекс.</span><span class="sxs-lookup"><span data-stu-id="46e35-127">If you have chosen to save the new lookup index, specify whether you also want [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to maintain the index.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="46e35-128">Если выбрать параметр **Поддерживать хранимый индекс** в **редакторе преобразования «Нечеткий уточняющий запрос»** на вкладке **Ссылочная таблица**, представление будет поддерживать хранимый индекс с помощью управляемых хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="46e35-128">When you select **Maintain stored index** on the **Reference Table** tab of the **Fuzzy Lookup Transformation Editor**, the transformation uses managed stored procedures to maintain the index.</span></span> <span data-ttu-id="46e35-129">Эти управляемые хранимые процедуры используют функцию интеграции со средой CLR, доступную в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46e35-129">These managed stored procedures use the common language runtime (CLR) integration feature in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="46e35-130">По умолчанию в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] отключена интеграция со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="46e35-130">By default, CLR integration in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is not enabled.</span></span> <span data-ttu-id="46e35-131">Чтобы использовать функцию **Поддерживать хранимый индекс** , необходимо включить интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="46e35-131">To use the **Maintain stored index** functionality, you must enable CLR integration.</span></span> <span data-ttu-id="46e35-132">Дополнительные сведения см. в статье [Enabling CLR Integration](../relational-databases/clr-integration/clr-integration-enabling.md).</span><span class="sxs-lookup"><span data-stu-id="46e35-132">For more information, see [Enabling CLR Integration](../relational-databases/clr-integration/clr-integration-enabling.md).</span></span>  
>   
>  <span data-ttu-id="46e35-133">Поскольку для параметра **Поддерживать хранимый индекс** необходима интеграция со средой CLR, эта функция работает, только если ссылочная таблица выбрана на экземпляре [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , на котором включена интеграция со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="46e35-133">Because the **Maintain stored index** option requires CLR integration, this feature works only when you select a reference table on an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] where CLR integration is enabled.</span></span>  
  
 <span data-ttu-id="46e35-134">**Использовать существующий индекс**</span><span class="sxs-lookup"><span data-stu-id="46e35-134">**Use existing index**</span></span>  
 <span data-ttu-id="46e35-135">Выберите, если преобразование будет использовать для уточняющего запроса существующий индекс.</span><span class="sxs-lookup"><span data-stu-id="46e35-135">Specify that the transformation should use an existing index for the lookup.</span></span>  
  
 <span data-ttu-id="46e35-136">**Имя существующего индекса**</span><span class="sxs-lookup"><span data-stu-id="46e35-136">**Name of an existing index**</span></span>  
 <span data-ttu-id="46e35-137">Выберите из списка ранее созданный индекс уточняющего запроса.</span><span class="sxs-lookup"><span data-stu-id="46e35-137">Select a previously created lookup index from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46e35-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="46e35-138">See Also</span></span>  
 <span data-ttu-id="46e35-139">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="46e35-139">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="46e35-140">[Редактор преобразования "Нечеткий уточняющий запрос" &#40;вкладка "столбцы"&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-columns-tab.md) </span><span class="sxs-lookup"><span data-stu-id="46e35-140">[Fuzzy Lookup Transformation Editor &#40;Columns Tab&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-columns-tab.md) </span></span>  
 [<span data-ttu-id="46e35-141">Редактор преобразования "Нечеткий уточняющий запрос" (вкладка "Дополнительно")</span><span class="sxs-lookup"><span data-stu-id="46e35-141">Fuzzy Lookup Transformation Editor &#40;Advanced Tab&#41;</span></span>](../../2014/integration-services/fuzzy-lookup-transformation-editor-advanced-tab.md)  
  
  
