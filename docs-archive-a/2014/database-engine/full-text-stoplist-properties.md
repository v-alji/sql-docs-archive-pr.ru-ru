---
title: Свойства полнотекстового списка стоп-слов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftstoplistproperties.general.f1
- sql12.swb.fulltextsearch.ftstoplistproperties.schedule.f1
ms.assetid: 2e907f5b-0cf9-484a-afcf-a4e7f1e2f87f
author: rothja
ms.author: jroth
ms.openlocfilehash: 4ff27a1258d5164e3e93d34b6ff757993d6f6363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669051"
---
# <a name="full-text-stoplist-properties"></a><span data-ttu-id="8b9ee-102">Свойства полнотекстового списка стоп-слов</span><span class="sxs-lookup"><span data-stu-id="8b9ee-102">Full-Text Stoplist Properties</span></span>
  <span data-ttu-id="8b9ee-103">Это диалоговое окно используется для добавления и удаления отдельных стоп-слов, удаления всех стоп-слов указанного языка, а также для очистки текущего списка стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="8b9ee-103">Use this dialog box to add or delete individual stopwords, delete all stopwords for a specific language, or clear the current stoplist.</span></span> <span data-ttu-id="8b9ee-104">Стоп-слово — это часто употребляемое слово, включенное в список стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="8b9ee-104">A stopword is a commonly used word that is included in a stoplist.</span></span> <span data-ttu-id="8b9ee-105">Стоп-слова из этого списка исключаются при полнотекстовом индексировании таблиц, в которых используется список стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="8b9ee-105">The stopwords in a stoplist are omitted from full-text indexing for tables that use the stoplist.</span></span> <span data-ttu-id="8b9ee-106">Дополнительные сведения см. в разделе [Настройка стоп-слов и списков стоп-слов для полнотекстового поиска и управление ими](../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="8b9ee-106">For more information, see [Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="8b9ee-107">**Изменение свойств списка стоп-слов в среде SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="8b9ee-107">**To use SQL Server Management Studio to change stoplist properties**</span></span>  
  
-   [<span data-ttu-id="8b9ee-108">Настройка и управление стоп-словами и списками стоп-слов для полнотекстового поиска</span><span class="sxs-lookup"><span data-stu-id="8b9ee-108">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>](../relational-databases/search/full-text-search.md)  
  
## <a name="options"></a><span data-ttu-id="8b9ee-109">Варианты</span><span class="sxs-lookup"><span data-stu-id="8b9ee-109">Options</span></span>  
 <span data-ttu-id="8b9ee-110">**Действие**</span><span class="sxs-lookup"><span data-stu-id="8b9ee-110">**Action**</span></span>  
 <span data-ttu-id="8b9ee-111">Указывает действие, которое необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="8b9ee-111">Specifies the action that you want to perform.</span></span>  
  
 <span data-ttu-id="8b9ee-112">**Добавить стоп-слово**</span><span class="sxs-lookup"><span data-stu-id="8b9ee-112">**Add stopword**</span></span>  
 <span data-ttu-id="8b9ee-113">Добавление в список стоп-слов часто употребляемого слова.</span><span class="sxs-lookup"><span data-stu-id="8b9ee-113">Add a commonly used word to the stoplist.</span></span>  
  
 <span data-ttu-id="8b9ee-114">**Удалить стоп-слово**</span><span class="sxs-lookup"><span data-stu-id="8b9ee-114">**Delete stopword**</span></span>  
 <span data-ttu-id="8b9ee-115">Удаление стоп-слова из списка.</span><span class="sxs-lookup"><span data-stu-id="8b9ee-115">Delete a stopword from the stoplist.</span></span>  
  
 <span data-ttu-id="8b9ee-116">**Удалить все стоп-слова**</span><span class="sxs-lookup"><span data-stu-id="8b9ee-116">**Delete all stopwords**</span></span>  
 <span data-ttu-id="8b9ee-117">Удаление всех стоп-слов определенного языка.</span><span class="sxs-lookup"><span data-stu-id="8b9ee-117">Delete all the stopwords for a specific language.</span></span>  
  
 <span data-ttu-id="8b9ee-118">**Очистить список стоп-слов**</span><span class="sxs-lookup"><span data-stu-id="8b9ee-118">**Clear stoplist**</span></span>  
 <span data-ttu-id="8b9ee-119">Очистка списка путем удаления всех стоп-слов всех языков.</span><span class="sxs-lookup"><span data-stu-id="8b9ee-119">Clear the stoplist by deleting all the stopwords for all languages.</span></span>  
  
 <span data-ttu-id="8b9ee-120">**Стоп-слово**</span><span class="sxs-lookup"><span data-stu-id="8b9ee-120">**Stopword**</span></span>  
 <span data-ttu-id="8b9ee-121">Если выбрана команда **Добавить стоп-слово** или **Удалить стоп-слово**, введите это слово в поле **Стоп-слово** .</span><span class="sxs-lookup"><span data-stu-id="8b9ee-121">If you selected **Add stopword** or **Delete stopword**, enter the stopword in the **Stopword** field.</span></span> <span data-ttu-id="8b9ee-122">Новое стоп-слово должно быть уникальным, то есть отсутствовать в списке стоп-слов для выбранного языка.</span><span class="sxs-lookup"><span data-stu-id="8b9ee-122">A new stopword must be unique; that is, not yet in this stoplist for the language that you select.</span></span>  
  
 <span data-ttu-id="8b9ee-123">**Язык полнотекстового поиска**</span><span class="sxs-lookup"><span data-stu-id="8b9ee-123">**Full-text language**</span></span>  
 <span data-ttu-id="8b9ee-124">Если выбрана команда **Добавить стоп-слово**, **Удалить стоп-слово**или **Удалить все стоп-слова**, выберите язык стоп-слов из списка.</span><span class="sxs-lookup"><span data-stu-id="8b9ee-124">If you selected **Add stopword**, **Delete stopword**, or **Delete all stopwords**, select the language of the stopword or stopwords from the list box.</span></span> <span data-ttu-id="8b9ee-125">Список содержит все языки полнотекстового поиска, поддерживаемые экземпляром сервера.</span><span class="sxs-lookup"><span data-stu-id="8b9ee-125">This lists all the full-text languages that are supported by the server instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b9ee-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="8b9ee-126">See Also</span></span>  
 <span data-ttu-id="8b9ee-127">[sys. fulltext_stopwords &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8b9ee-127">[sys.fulltext_stopwords &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql) </span></span>  
 <span data-ttu-id="8b9ee-128">[sys. fulltext_stoplists &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8b9ee-128">[sys.fulltext_stoplists &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql) </span></span>  
 <span data-ttu-id="8b9ee-129">[Настройка стоп-слова и списков для полнотекстового поиска и управление ими](../relational-databases/search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="8b9ee-129">[Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md) </span></span>  
 <span data-ttu-id="8b9ee-130">[ALTER FULLTEXT стоп-слов &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8b9ee-130">[ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="8b9ee-131">[Создание ПОЛНОТЕКСТОВОГО списка стоп-слов &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8b9ee-131">[CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span></span>  
 [<span data-ttu-id="8b9ee-132">DROP FULLTEXT STOPLIST (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8b9ee-132">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql)  
  
  
