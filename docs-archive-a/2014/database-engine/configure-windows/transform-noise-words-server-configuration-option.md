---
title: Параметр конфигурации сервера "transform noise words" | Документы Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- full-text queries [SQL Server], performance
- transform noise words option
- noise words [full-text search]
- full-text search [SQL Server], stopwords
- stopwords [full-text search]
ms.assetid: 69bd388e-a86c-4de4-b5d5-d093424d9c57
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 49de4a381de3e998073a73c284e3e3e5960f4921
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738693"
---
# <a name="transform-noise-words-server-configuration-option"></a><span data-ttu-id="6b897-102">Параметр конфигурации сервера «transform noise words»</span><span class="sxs-lookup"><span data-stu-id="6b897-102">transform noise words Server Configuration Option</span></span>
  <span data-ttu-id="6b897-103">`transform noise words`Параметр конфигурации сервера используется для подавления сообщения об ошибке, если пропускаемые слова, [стоп-слова](../../relational-databases/search/full-text-search.md), приводят к тому, что логическая операция над полнотекстовым запросом возвращает нулевые строки.</span><span class="sxs-lookup"><span data-stu-id="6b897-103">Use the `transform noise words` server configuration option to suppress an error message if noise words, that is [stopwords](../../relational-databases/search/full-text-search.md), cause a Boolean operation on a full-text query to return zero rows.</span></span> <span data-ttu-id="6b897-104">Этот параметр удобно использовать в полнотекстовых запросах с предикатом CONTAINS, в котором логические операции или операции NEAR содержат пропускаемые слова.</span><span class="sxs-lookup"><span data-stu-id="6b897-104">This option is useful for full-text queries that use the CONTAINS predicate in which Boolean operations or NEAR operations include noise words.</span></span> <span data-ttu-id="6b897-105">Возможные значения описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="6b897-105">The possible values are described in the following table.</span></span>  
  
|<span data-ttu-id="6b897-106">Значение</span><span class="sxs-lookup"><span data-stu-id="6b897-106">Value</span></span>|<span data-ttu-id="6b897-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6b897-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6b897-108">0</span><span class="sxs-lookup"><span data-stu-id="6b897-108">0</span></span>|<span data-ttu-id="6b897-109">Пропускаемые слова (или стоп-слова) не преобразуются.</span><span class="sxs-lookup"><span data-stu-id="6b897-109">Noise words (or stopwords) are not transformed.</span></span> <span data-ttu-id="6b897-110">Если полнотекстовый запрос содержит стоп-слова, то запрос возвращает 0 строк, а [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="6b897-110">When a full-text query contains noise words, the query returns zero rows, and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] raises a warning.</span></span> <span data-ttu-id="6b897-111">Это поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6b897-111">This is the default behavior.</span></span><br /><br /> <span data-ttu-id="6b897-112">Обратите внимание, что предупреждение является предупреждением во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="6b897-112">Note that the warning is a run-time warning.</span></span> <span data-ttu-id="6b897-113">поэтому, если полнотекстовое предложение в запросе не выполняется, предупреждение не выдается.</span><span class="sxs-lookup"><span data-stu-id="6b897-113">Therefore, if the full-text clause in the query is not executed, the warning is not raised.</span></span> <span data-ttu-id="6b897-114">Для локального запроса предупреждение возвращается только при наличии в нем нескольких полнотекстовых предложений.</span><span class="sxs-lookup"><span data-stu-id="6b897-114">For a local query, only one warning is raised, even when there are multiple full-text query clauses.</span></span> <span data-ttu-id="6b897-115">Для удаленного запроса связанный сервер может не передать ошибку, поэтому сообщение может не отобразиться.</span><span class="sxs-lookup"><span data-stu-id="6b897-115">For a remote query, the linked server might not relay the error; therefore, the warning might not be raised.</span></span>|  
|<span data-ttu-id="6b897-116">1</span><span class="sxs-lookup"><span data-stu-id="6b897-116">1</span></span>|<span data-ttu-id="6b897-117">Пропускаемые слова (или стоп-слова) преобразуются.</span><span class="sxs-lookup"><span data-stu-id="6b897-117">Noise words (or stopwords) are transformed.</span></span> <span data-ttu-id="6b897-118">Они пропускаются, а остальная часть запроса обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="6b897-118">They are ignored, and the rest of the query is evaluated.</span></span><br /><br /> <span data-ttu-id="6b897-119">Если пропускаемые слова встречаются в предложениях, обозначающих расстояние, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] удаляет их.</span><span class="sxs-lookup"><span data-stu-id="6b897-119">If noise words are specified in a proximity term, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] removes them.</span></span> <span data-ttu-id="6b897-120">Например, пропускаемое слово `is` удаляется из фразы `CONTAINS(<column_name>, 'NEAR (hello,is,goodbye)')`, в результате чего поисковый запрос преобразуется в `CONTAINS(<column_name>, 'NEAR(hello,goodbye)')`.</span><span class="sxs-lookup"><span data-stu-id="6b897-120">For example, the noise word `is` is removed from `CONTAINS(<column_name>, 'NEAR (hello,is,goodbye)')`, transforming the search query into `CONTAINS(<column_name>, 'NEAR(hello,goodbye)')`.</span></span> <span data-ttu-id="6b897-121">Обратите внимание, что запрос `CONTAINS(<column_name>, 'NEAR(hello,is)')` будет преобразован просто в `CONTAINS(<column_name>, hello)` , поскольку там всего одно допустимое слово поиска.</span><span class="sxs-lookup"><span data-stu-id="6b897-121">Notice that `CONTAINS(<column_name>, 'NEAR(hello,is)')` would be transformed into simply `CONTAINS(<column_name>, hello)` because there is only one valid search term.</span></span>|  
  
## <a name="effects-of-the-transform-noise-words-setting"></a><span data-ttu-id="6b897-122">Действие настройки transform noise words</span><span class="sxs-lookup"><span data-stu-id="6b897-122">Effects of the transform noise words Setting</span></span>  
 <span data-ttu-id="6b897-123">В этом разделе проиллюстрировано поведение запросов с пропускаемым словом «`the`» при другой настройке параметра `transform noise words`.</span><span class="sxs-lookup"><span data-stu-id="6b897-123">This section illustrates the behavior of queries containing a noise word, "`the`", under the alternate settings of `transform noise words`.</span></span>  <span data-ttu-id="6b897-124">Предполагается обработка образцов строк полнотекстовых запросов по строке таблицы со следующими данными: `[1, "The black cat"]`.</span><span class="sxs-lookup"><span data-stu-id="6b897-124">The sample full-text query strings are assumed to be run against a table row containing the following data: `[1, "The black cat"]`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b897-125">Все подобные сценарии могут выдавать предупреждение о пропускаемых словах.</span><span class="sxs-lookup"><span data-stu-id="6b897-125">All such scenarios can generate a noise word warning.</span></span>  
  
-   <span data-ttu-id="6b897-126">Если значение параметра transform noise words — 0:</span><span class="sxs-lookup"><span data-stu-id="6b897-126">With transform noise words set to 0:</span></span>  
  
    |<span data-ttu-id="6b897-127">Строка запроса</span><span class="sxs-lookup"><span data-stu-id="6b897-127">Query string</span></span>|<span data-ttu-id="6b897-128">Результат</span><span class="sxs-lookup"><span data-stu-id="6b897-128">Result</span></span>|  
    |------------------|------------|  
    |<span data-ttu-id="6b897-129">«`cat`» AND «`the`»</span><span class="sxs-lookup"><span data-stu-id="6b897-129">"`cat`" AND "`the`"</span></span>|<span data-ttu-id="6b897-130">Нет результатов (поведение аналогично «"`the`" AND "`cat`"».)</span><span class="sxs-lookup"><span data-stu-id="6b897-130">No results (The behavior is the same for "`the`" AND "`cat`".)</span></span>|  
    |<span data-ttu-id="6b897-131">«`cat`» NEAR «`the`»</span><span class="sxs-lookup"><span data-stu-id="6b897-131">"`cat`" NEAR "`the`"</span></span>|<span data-ttu-id="6b897-132">Нет результатов (поведение аналогично «"`the`" NEAR "`cat`"».)</span><span class="sxs-lookup"><span data-stu-id="6b897-132">No results (The behavior is the same for "`the`" NEAR "`cat`".)</span></span>|  
    |<span data-ttu-id="6b897-133">«`the`» AND NOT «`black`»</span><span class="sxs-lookup"><span data-stu-id="6b897-133">"`the`" AND NOT "`black`"</span></span>|<span data-ttu-id="6b897-134">Нет результатов</span><span class="sxs-lookup"><span data-stu-id="6b897-134">No results</span></span>|  
    |<span data-ttu-id="6b897-135">«`black`» AND NOT «`the`»</span><span class="sxs-lookup"><span data-stu-id="6b897-135">"`black`" AND NOT "`the`"</span></span>|<span data-ttu-id="6b897-136">Нет результатов</span><span class="sxs-lookup"><span data-stu-id="6b897-136">No results</span></span>|  
  
-   <span data-ttu-id="6b897-137">Если значение параметра transform noise words — 1:</span><span class="sxs-lookup"><span data-stu-id="6b897-137">With transform noise words set to 1:</span></span>  
  
    |<span data-ttu-id="6b897-138">Строка запроса</span><span class="sxs-lookup"><span data-stu-id="6b897-138">Query string</span></span>|<span data-ttu-id="6b897-139">Результат</span><span class="sxs-lookup"><span data-stu-id="6b897-139">Result</span></span>|  
    |------------------|------------|  
    |<span data-ttu-id="6b897-140">«`cat`» AND «`the`»</span><span class="sxs-lookup"><span data-stu-id="6b897-140">"`cat`" AND "`the`"</span></span>|<span data-ttu-id="6b897-141">Попадание для строки с идентификатором 1</span><span class="sxs-lookup"><span data-stu-id="6b897-141">Hit for row with ID 1</span></span>|  
    |<span data-ttu-id="6b897-142">«`cat`» NEAR «`the`»</span><span class="sxs-lookup"><span data-stu-id="6b897-142">"`cat`" NEAR "`the`"</span></span>|<span data-ttu-id="6b897-143">Попадание для строки с идентификатором 1</span><span class="sxs-lookup"><span data-stu-id="6b897-143">Hit for row with ID 1</span></span>|  
    |<span data-ttu-id="6b897-144">«`the`» AND NOT «`black`»</span><span class="sxs-lookup"><span data-stu-id="6b897-144">"`the`" AND NOT "`black`"</span></span>|<span data-ttu-id="6b897-145">Нет результатов</span><span class="sxs-lookup"><span data-stu-id="6b897-145">No results</span></span>|  
    |<span data-ttu-id="6b897-146">«`black`» AND NOT «`the`»</span><span class="sxs-lookup"><span data-stu-id="6b897-146">"`black`" AND NOT "`the`"</span></span>|<span data-ttu-id="6b897-147">Попадание для строки с идентификатором 1</span><span class="sxs-lookup"><span data-stu-id="6b897-147">Hit for row with ID 1</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6b897-148">Пример</span><span class="sxs-lookup"><span data-stu-id="6b897-148">Example</span></span>  
 <span data-ttu-id="6b897-149">В данном примере параметр `transform noise words` имеет значение `1`.</span><span class="sxs-lookup"><span data-stu-id="6b897-149">The following example sets `transform noise words` to `1`.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
RECONFIGURE;  
GO  
sp_configure 'transform noise words', 1;  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="6b897-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="6b897-150">See Also</span></span>  
 <span data-ttu-id="6b897-151">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6b897-151">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="6b897-152">CONTAINS (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6b897-152">CONTAINS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/contains-transact-sql)  
  
  
