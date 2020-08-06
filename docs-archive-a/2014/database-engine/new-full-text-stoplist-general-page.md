---
title: Создать полнотекстовый список стоп-слов (страница "Общие") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftstoplist.general.f1
ms.assetid: 97f8e82d-82ab-4525-91c9-1ee3ae217309
author: rothja
ms.author: jroth
ms.openlocfilehash: a6272fb570b85989f38c8187e29712966862710d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667886"
---
# <a name="new-full-text-stoplist-general-page"></a><span data-ttu-id="3b997-102">Создание списка полнотекстовых стоп-слов (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="3b997-102">New Full-Text Stoplist (General Page)</span></span>
  <span data-ttu-id="3b997-103">Используется для создания полнотекстового списка стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="3b997-103">Use this dialog box to create a full-text stoplist.</span></span> <span data-ttu-id="3b997-104">*Список стоп-слов* — это набор часто употребляемых слов, называемых *стоп-словами*, которые не включаются в полнотекстовый индекс для таблиц, использующих такой список.</span><span class="sxs-lookup"><span data-stu-id="3b997-104">A *stoplist* is a set of commonly used words, called *stopwords*, that are omitted from full-text indexing for tables that use the stoplist.</span></span> <span data-ttu-id="3b997-105">Дополнительные сведения см. в разделе [Настройка стоп-слов и списков стоп-слов для полнотекстового поиска и управление ими](../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="3b997-105">For more information, see [Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="3b997-106">**Создание списка стоп-слов в среде SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="3b997-106">**To use SQL Server Management Studio to create a stoplist**</span></span>  
  
-   [<span data-ttu-id="3b997-107">Настройка и управление стоп-словами и списками стоп-слов для полнотекстового поиска</span><span class="sxs-lookup"><span data-stu-id="3b997-107">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>](../relational-databases/search/full-text-search.md)  
  
## <a name="options"></a><span data-ttu-id="3b997-108">Варианты</span><span class="sxs-lookup"><span data-stu-id="3b997-108">Options</span></span>  
 <span data-ttu-id="3b997-109">**Имя полнотекстового списка стоп-слов**</span><span class="sxs-lookup"><span data-stu-id="3b997-109">**Full-text stoplist name**</span></span>  
 <span data-ttu-id="3b997-110">Введите имя полнотекстового списка стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="3b997-110">Enter the name of the full-text stoplist.</span></span>  
  
 <span data-ttu-id="3b997-111">**Владелец**</span><span class="sxs-lookup"><span data-stu-id="3b997-111">**Owner**</span></span>  
 <span data-ttu-id="3b997-112">Укажите владельца полнотекстового списка стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="3b997-112">Specify the owner of the full-text stoplist.</span></span> <span data-ttu-id="3b997-113">Чтобы сделать владельцем текущего пользователя, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="3b997-113">If you want ownership to be assigned to yourself, that is, to the current user, leave this field empty.</span></span>  
  
 <span data-ttu-id="3b997-114">Чтобы указать другого пользователя, нажмите кнопку обзора.</span><span class="sxs-lookup"><span data-stu-id="3b997-114">To specify a different user, click the browse button.</span></span>  
  
### <a name="create-stoplist-options"></a><span data-ttu-id="3b997-115">Параметры создания списка стоп-слов</span><span class="sxs-lookup"><span data-stu-id="3b997-115">Create stoplist options</span></span>  
 <span data-ttu-id="3b997-116">Выберите один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="3b997-116">Click one of the following create options:</span></span>  
  
 <span data-ttu-id="3b997-117">**Создать пустой список стоп-слов**</span><span class="sxs-lookup"><span data-stu-id="3b997-117">**Create an empty stoplist**</span></span>  
 <span data-ttu-id="3b997-118">Новый список не будет содержать стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="3b997-118">The new stoplist will not contain any stopwords.</span></span>  
  
 <span data-ttu-id="3b997-119">**Создать из системного списка стоп-слов**</span><span class="sxs-lookup"><span data-stu-id="3b997-119">**Create from the system stoplist**</span></span>  
 <span data-ttu-id="3b997-120">Новый список стоп-слов создается на основе списка, существующего в базе данных [Resource](../relational-databases/databases/resource-database.md)по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3b997-120">The new stoplist is created from the stoplist that exists by default in the [Resource database](../relational-databases/databases/resource-database.md).</span></span>  
  
 <span data-ttu-id="3b997-121">**Создать из существующего полнотекстового списка стоп-слов**</span><span class="sxs-lookup"><span data-stu-id="3b997-121">**Create from an existing full-text stoplist**</span></span>  
 <span data-ttu-id="3b997-122">Новый список стоп-слов создается путем копирования существующего.</span><span class="sxs-lookup"><span data-stu-id="3b997-122">The new stoplist is created by copying an existing stoplist.</span></span>  
  
 <span data-ttu-id="3b997-123">**База данных источника**</span><span class="sxs-lookup"><span data-stu-id="3b997-123">**Source database**</span></span>  
 <span data-ttu-id="3b997-124">Указывает имя базы данных, которой принадлежит существующий список стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="3b997-124">Specifies the name of the database to which the existing stoplist belongs.</span></span> <span data-ttu-id="3b997-125">По умолчанию выбрана текущая база данных.</span><span class="sxs-lookup"><span data-stu-id="3b997-125">The current database is selected by default.</span></span> <span data-ttu-id="3b997-126">При необходимости можно выбрать из списка другую базу данных.</span><span class="sxs-lookup"><span data-stu-id="3b997-126">Optionally, select a different database from the list box.</span></span>  
  
 <span data-ttu-id="3b997-127">**Источник списка стоп-слов**</span><span class="sxs-lookup"><span data-stu-id="3b997-127">**Source stoplist**</span></span>  
 <span data-ttu-id="3b997-128">Указывает имя существующего списка стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="3b997-128">Specifies the name of an existing stoplist.</span></span> <span data-ttu-id="3b997-129">Из перечня доступных списков выберите один, который будет использоваться в качестве источника.</span><span class="sxs-lookup"><span data-stu-id="3b997-129">From the list of available stoplists, select the one to use as the source.</span></span> <span data-ttu-id="3b997-130">Доступные списки стоп-слов перечисляются в порядке их отображения в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="3b997-130">The available stoplists are listed in the order in which they appear in Object Explorer.</span></span>  
  
 <span data-ttu-id="3b997-131">Если в текущей базе данных не зарегистрирован любой язык стоп-слов из исходного списка стоп-слов, инструкция CREATE FULLTEXT STOPLIST завершается успешно, но с предупреждениями, а соответствующие стоп-слова не добавляются.</span><span class="sxs-lookup"><span data-stu-id="3b997-131">If any languages specified in the stop words of the source stoplist are not registered in the current database, CREATE FULLTEXT STOPLIST succeeds, but warning(s) are returned and the corresponding stop words are not added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b997-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="3b997-132">See Also</span></span>  
 <span data-ttu-id="3b997-133">[ALTER FULLTEXT стоп-слов &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3b997-133">[ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="3b997-134">[Создание ПОЛНОТЕКСТОВОГО списка стоп-слов &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3b997-134">[CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="3b997-135">[УДАЛИТЬ ПОЛНОТЕКСТОВЫЙ список стоп-слов &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3b997-135">[DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="3b997-136">[Настройка стоп-слова и списков для полнотекстового поиска и управление ими](../relational-databases/search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="3b997-136">[Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md) </span></span>  
 [<span data-ttu-id="3b997-137">sys.fulltext_stoplists (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3b997-137">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql)  
  
  
