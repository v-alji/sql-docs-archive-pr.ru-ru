---
title: Свойства полнотекстового каталога (страница «Общие») | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftcatalogproperties.general.f1
ms.assetid: d1f66762-2d40-4f24-b635-a417d22ee79a
author: rothja
ms.author: jroth
ms.openlocfilehash: 483601c53db6c8a806ea8c53f771fd4f2608293b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740301"
---
# <a name="full-text-catalog-properties-general-page"></a><span data-ttu-id="5ca7c-102">Свойства полнотекстового каталога (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="5ca7c-102">Full-Text Catalog Properties (General Page)</span></span>
  <span data-ttu-id="5ca7c-103">В этом разделе показаны параметры и функции, доступные на странице **Общие** диалогового окна **Свойства полнотекстового каталога** .</span><span class="sxs-lookup"><span data-stu-id="5ca7c-103">This section shows the options and functions available on the **General** page of the **Full-Text Catalog Properties** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5ca7c-104">Полнотекстовый каталог в базах данных [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] — это логическое понятие, обозначающее группу полнотекстовых индексов.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-104">For [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] databases, a full-text catalog is a logical concept that refers to a group of full-text indexes.</span></span> <span data-ttu-id="5ca7c-105">Полнотекстовый каталог является виртуальным объектом и не входит в какую-либо файловую группу.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-105">The full-text catalog is a virtual object that does not belong to any filegroup.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5ca7c-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="5ca7c-106">Options</span></span>  
  
### <a name="properties"></a><span data-ttu-id="5ca7c-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="5ca7c-107">Properties</span></span>  
 <span data-ttu-id="5ca7c-108">**Каталог по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-108">**Default Catalog**</span></span>  
 <span data-ttu-id="5ca7c-109">Указывает, является ли каталог каталогом по умолчанию для базы данных.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-109">Displays whether the catalog is the default catalog for the database.</span></span>  
  
 <span data-ttu-id="5ca7c-110">**Состояние заполнения**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-110">**Population Status**</span></span>  
 <span data-ttu-id="5ca7c-111">Указывает состояние каталога.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-111">Indicates the status of the catalog.</span></span> <span data-ttu-id="5ca7c-112">Возможны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="5ca7c-112">Possible values are:</span></span>  
  
-   <span data-ttu-id="5ca7c-113">**Бездействие**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-113">**Idle**</span></span>  
  
-   <span data-ttu-id="5ca7c-114">**Выполняется сканирование**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-114">**Crawl in Progress**</span></span>  
  
-   <span data-ttu-id="5ca7c-115">**Приостановлено**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-115">**Paused**</span></span>  
  
-   <span data-ttu-id="5ca7c-116">**Ожидает повтора**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-116">**Throttled**</span></span>  
  
-   <span data-ttu-id="5ca7c-117">**Механизм**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-117">**Recovering**</span></span>  
  
-   <span data-ttu-id="5ca7c-118">**Завершение работы**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-118">**Shutdown**</span></span>  
  
-   <span data-ttu-id="5ca7c-119">**Выполняется добавочное заполнение**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-119">**Incremental population in progress**</span></span>  
  
-   <span data-ttu-id="5ca7c-120">**Построение индекса**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-120">**Building index**</span></span>  
  
-   <span data-ttu-id="5ca7c-121">**Диск полностью приостановлен**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-121">**Disk is full-Paused**</span></span>  
  
-   <span data-ttu-id="5ca7c-122">**Change tracking**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-122">**Change tracking**</span></span>  
  
 <span data-ttu-id="5ca7c-123">**Число элементов**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-123">**Item Count**</span></span>  
 <span data-ttu-id="5ca7c-124">Отображается количество полнотекстовых элементов в каталоге.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-124">Displays the number of full-text items in the catalog.</span></span>  
  
 <span data-ttu-id="5ca7c-125">**Размер каталога**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-125">**Catalog Size**</span></span>  
 <span data-ttu-id="5ca7c-126">Отображается размер полнотекстового каталога в мегабайтах.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-126">Displays the size, in megabytes, of the full-text catalog.</span></span>  
  
 <span data-ttu-id="5ca7c-127">**имя**;</span><span class="sxs-lookup"><span data-stu-id="5ca7c-127">**Name**</span></span>  
 <span data-ttu-id="5ca7c-128">Имя полнотекстового каталога.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-128">The name of the full-text catalog.</span></span>  
  
 <span data-ttu-id="5ca7c-129">**С учетом диакритических знаков**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-129">**Accent Sensitive**</span></span>  
 <span data-ttu-id="5ca7c-130">Просмотр или изменение того, учитывается ли каталог диакритическими знаками, такими как тильда ( **~** ), острая диакритические знаки (**ґ**) или умляут (**ё**).</span><span class="sxs-lookup"><span data-stu-id="5ca7c-130">View or modify whether the catalog is sensitive to diacritical marks, such as a tilde (**~**), acute accent mark (**´**), or umlaut (**¨**).</span></span> <span data-ttu-id="5ca7c-131">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="5ca7c-131">Valid values are:</span></span>  
  
-   <span data-ttu-id="5ca7c-132">**Нет**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-132">**No**</span></span>  
  
-   <span data-ttu-id="5ca7c-133">**Да**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-133">**Yes**</span></span>  
  
-   <span data-ttu-id="5ca7c-134">Дополнительные сведения о диакритических знаках см. в разделе [диакритические](https://www.merriam-webster.com/dictionary/diacritic) знаки в словаре Мерриам-толковом.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-134">For information about diacritical marks, see [Diacritic](https://www.merriam-webster.com/dictionary/diacritic) in the Merriam-Webster dictionary.</span></span>  
  
 <span data-ttu-id="5ca7c-135">**Дата последнего заполнения**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-135">**Last Population Date**</span></span>  
 <span data-ttu-id="5ca7c-136">Отображается дата последнего заполнения каталога.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-136">Displays the date the catalog was last populated.</span></span>  
  
 <span data-ttu-id="5ca7c-137">**Владелец**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-137">**Owner**</span></span>  
 <span data-ttu-id="5ca7c-138">Владелец полнотекстового каталога.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-138">The owner of the full-text catalog.</span></span>  
  
 <span data-ttu-id="5ca7c-139">**Число уникальных ключей**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-139">**Unique Key Count**</span></span>  
 <span data-ttu-id="5ca7c-140">Количество уникальных слов, образующих полнотекстовый индекс каталога.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-140">The number of unique words that make up the full-text index for the catalog.</span></span>  
  
### <a name="catalog-action"></a><span data-ttu-id="5ca7c-141">Операция с каталогом</span><span class="sxs-lookup"><span data-stu-id="5ca7c-141">Catalog Action</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5ca7c-142">**None**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-142">**None**</span></span>|<span data-ttu-id="5ca7c-143">Не выполняются операции **Оптимизировать каталог**, **Перестроить каталог**и **Повторить заполнение каталога** .</span><span class="sxs-lookup"><span data-stu-id="5ca7c-143">Does not perform **Optimize catalog**, **Rebuild catalog**, or **Repopulate catalog** operations.</span></span>|  
|<span data-ttu-id="5ca7c-144">**Оптимизировать каталог**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-144">**Optimize catalog**</span></span>|<span data-ttu-id="5ca7c-145">Оптимизируется использование пространства каталога и повышается производительность запросов.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-145">Optimizes the space utilization of the catalog and improves query performance.</span></span> <span data-ttu-id="5ca7c-146">Кроме того, повышается точность ранжирования релевантности результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-146">It also improves the accuracy of relevance ranking of search results.</span></span><br /><br /> <span data-ttu-id="5ca7c-147">Это действие выполняет инструкцию ALTER FULLTEXT CATALOG *catalog_name* с параметром REORGANIZE.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-147">This action executes ALTER FULLTEXT CATALOG *catalog_name* REORGANIZE.</span></span>|  
|<span data-ttu-id="5ca7c-148">**Перестроить каталог**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-148">**Rebuild catalog**</span></span>|<span data-ttu-id="5ca7c-149">Удаляется и перестраивается полнотекстовый каталог.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-149">Deletes and rebuilds the full-text catalog.</span></span> <span data-ttu-id="5ca7c-150">Эта операция должна выполняться после изменения основных свойств каталога, например учета диакритических знаков.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-150">This operation must be performed if a fundamental catalog property is changed, such as accent sensitivity.</span></span><br /><br /> <span data-ttu-id="5ca7c-151">Чтобы перестроить каталог, файловая группа, которая содержится в полнотекстовом каталоге, должна быть доступна в интерактивном режиме или доступна для чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-151">For the rebuild to succeed, the filegroup the full-text catalog resides in must be online or read-writeable.</span></span> <span data-ttu-id="5ca7c-152">После перестроения полнотекстовый индекс будет заполнен заново.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-152">After the rebuild, the full-text index will be repopulated.</span></span><br /><br /> <span data-ttu-id="5ca7c-153">Это действие выполняет инструкцию ALTER FULLTEXT CATALOG *catalog_name* с параметром REBUILD.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-153">This action executes ALTER FULLTEXT CATALOG *catalog_name* REBUILD.</span></span>|  
|<span data-ttu-id="5ca7c-154">**Повторить заполнение каталога**</span><span class="sxs-lookup"><span data-stu-id="5ca7c-154">**Repopulate catalog**</span></span>|<span data-ttu-id="5ca7c-155">Каталог обновляется последними изменениями данных.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-155">Updates the catalog with recent changes to the data.</span></span> <span data-ttu-id="5ca7c-156">Изменение этого параметра не требует остановки каталога.</span><span class="sxs-lookup"><span data-stu-id="5ca7c-156">This option does require catalog downtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ca7c-157">См. также:</span><span class="sxs-lookup"><span data-stu-id="5ca7c-157">See Also</span></span>  
 [<span data-ttu-id="5ca7c-158">Заполнение полнотекстовых индексов</span><span class="sxs-lookup"><span data-stu-id="5ca7c-158">Populate Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
  
