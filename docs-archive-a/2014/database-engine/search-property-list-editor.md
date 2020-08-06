---
title: Редактор списка свойств поиска | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.spl.searchpropertylisteditor.f1
ms.assetid: 0f3ced6e-0dfd-49fc-b175-82378c3d668e
author: rothja
ms.author: jroth
ms.openlocfilehash: 6c68ec986e2c6f4f53dfec7f188ba2a120532ae4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658383"
---
# <a name="search-property-list-editor"></a><span data-ttu-id="b540c-102">Редактор списка свойств поиска</span><span class="sxs-lookup"><span data-stu-id="b540c-102">Search Property List Editor</span></span>
  <span data-ttu-id="b540c-103">Используйте это диалоговое окно, чтобы добавлять или удалять свойства поиска в списке свойств поиска.</span><span class="sxs-lookup"><span data-stu-id="b540c-103">Use this dialog box to add or delete search properties in a search property list.</span></span>  
  
## <a name="to-use-sql-server-management-studio-to-manage-search-property-lists"></a><span data-ttu-id="b540c-104">Управление списками свойств поиска в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b540c-104">To Use SQL Server Management Studio to Manage Search Property Lists</span></span>  
 <span data-ttu-id="b540c-105">Сведения о создании, просмотре и удалении списка свойств поиска, а также о настройке полнотекстового индекса для поиска свойств см. в разделе [Поиск свойств документа с помощью списков свойств поиска](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span><span class="sxs-lookup"><span data-stu-id="b540c-105">For information about how to create, view, or delete a search property list, and about how to configure a full-text index for property searching, see [Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b540c-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="b540c-106">Options</span></span>  
 <span data-ttu-id="b540c-107">**Имя свойства**</span><span class="sxs-lookup"><span data-stu-id="b540c-107">**Property Name**</span></span>  
 <span data-ttu-id="b540c-108">Укажите имя, которое будет использоваться для обозначения свойства в полнотекстовых запросах.</span><span class="sxs-lookup"><span data-stu-id="b540c-108">Specify the name to be used to identify the property in full-text queries.</span></span> <span data-ttu-id="b540c-109">Имя свойства может содержать внутренние пробелы.</span><span class="sxs-lookup"><span data-stu-id="b540c-109">A property name can contain internal spaces.</span></span> <span data-ttu-id="b540c-110">Длина **имени свойства** не должна превышать 256 символов.</span><span class="sxs-lookup"><span data-stu-id="b540c-110">The maximum length of **Property Name** is 256 characters.</span></span> <span data-ttu-id="b540c-111">Это имя должно быть описательным, таким как «Автор» или «Домашний адрес», или каноническим именем Windows свойства, например `System.Author` или `System.Contact.HomeAddress`.</span><span class="sxs-lookup"><span data-stu-id="b540c-111">This name can be a user-friendly name, such as "Author" or "Home Address", or it can be the Windows canonical name of the property, such as `System.Author` or `System.Contact.HomeAddress`.</span></span> <span data-ttu-id="b540c-112">**Имя свойства** должно уникально определять свойство в наборе свойств.</span><span class="sxs-lookup"><span data-stu-id="b540c-112">**Property Name** must uniquely identify the property within the property set.</span></span>  
  
 <span data-ttu-id="b540c-113">Разработчики используют имя свойства, чтобы определить свойство в предикате [CONTAINS](/sql/t-sql/queries/contains-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="b540c-113">Developers use the property name to identify the property in the [CONTAINS](/sql/t-sql/queries/contains-transact-sql) predicate.</span></span> <span data-ttu-id="b540c-114">Поэтому при добавлении свойства важно указать значение, которое значимо представляет свойство.</span><span class="sxs-lookup"><span data-stu-id="b540c-114">Therefore, when adding a property it is important to specify a value that meaningfully represents the property.</span></span>  
  
 <span data-ttu-id="b540c-115">**Идентификатор GUID набора свойств**</span><span class="sxs-lookup"><span data-stu-id="b540c-115">**Property Set GUID**</span></span>  
 <span data-ttu-id="b540c-116">Указывает идентификатор набора свойств, к которому принадлежит свойство.</span><span class="sxs-lookup"><span data-stu-id="b540c-116">Specify the identifier of the property set to which the property belongs.</span></span> <span data-ttu-id="b540c-117">Это глобальный уникальный идентификатор GUID.</span><span class="sxs-lookup"><span data-stu-id="b540c-117">This is a globally unique identifier (GUID).</span></span> <span data-ttu-id="b540c-118">Набор свойств — группа логически связанных свойств.</span><span class="sxs-lookup"><span data-stu-id="b540c-118">A property set is a group of logically related properties.</span></span> <span data-ttu-id="b540c-119">Дополнительные сведения о получении этого значения см. в подразделе «Замечания» далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b540c-119">For information about obtaining this value, see "Remarks," later in this topic.</span></span>  
  
 <span data-ttu-id="b540c-120">**Идентификатор Int свойства**</span><span class="sxs-lookup"><span data-stu-id="b540c-120">**Property Int ID**</span></span>  
 <span data-ttu-id="b540c-121">Указывает целочисленный идентификатор свойства.</span><span class="sxs-lookup"><span data-stu-id="b540c-121">Specify the property integer identifier of the property.</span></span> <span data-ttu-id="b540c-122">Это предопределенное значение представляет собой целое число, уникальное внутри набора свойств.</span><span class="sxs-lookup"><span data-stu-id="b540c-122">This pre-assigned value is a positive integer that is unique within the property set.</span></span> <span data-ttu-id="b540c-123">Дополнительные сведения о получении этого значения см. в подразделе «Замечания» далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b540c-123">For information about obtaining this value, see "Remarks," later in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b540c-124">Свойства документа, использующие идентификаторы, не поддерживаются полнотекстовым поиском.</span><span class="sxs-lookup"><span data-stu-id="b540c-124">Document properties that use string identifiers are not supported by full-text search.</span></span>  
  
 <span data-ttu-id="b540c-125">**Описание свойства**</span><span class="sxs-lookup"><span data-stu-id="b540c-125">**Property Description**</span></span>  
 <span data-ttu-id="b540c-126">Дополнительно можно указать описание свойства.</span><span class="sxs-lookup"><span data-stu-id="b540c-126">Optionally, specify a description of the property.</span></span> <span data-ttu-id="b540c-127">Это строка длиной не более 512 символов.</span><span class="sxs-lookup"><span data-stu-id="b540c-127">This is a string of up to 512 characters.</span></span> <span data-ttu-id="b540c-128">Например, описание может содержать сведения о наборе свойств свойства или сведения о свойстве, которые не очевидны из его имени.</span><span class="sxs-lookup"><span data-stu-id="b540c-128">For example, a description could contain information about the property set of the property or information about a property that is not evident from its name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b540c-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="b540c-129">Remarks</span></span>  
 <span data-ttu-id="b540c-130">Чтобы добавить свойство поиска к списку свойств поиска, необходимо указать глобальный уникальный идентификатор (GUID) набора свойств, к которому принадлежит свойство, и целочисленный идентификатор свойства.</span><span class="sxs-lookup"><span data-stu-id="b540c-130">To add a search property to a search property list, you must specify the globally unique identifier (GUID) of the property set to which the property belongs and the property integer identifier of the property.</span></span> <span data-ttu-id="b540c-131">Сочетание этих значений должно быть уникальным в данном списке свойств поиска.</span><span class="sxs-lookup"><span data-stu-id="b540c-131">A given combination of these must be unique in a given search property list.</span></span> <span data-ttu-id="b540c-132">При попытке добавить существующее сочетание операция завершается неудачей и выдается ошибка.</span><span class="sxs-lookup"><span data-stu-id="b540c-132">If you try to add an existing combination, the operation fails and issues an error.</span></span> <span data-ttu-id="b540c-133">Это означает, что можно назначить только одно имя для данного свойства.</span><span class="sxs-lookup"><span data-stu-id="b540c-133">This means that you can configure only one name for a given property.</span></span>  
  
 <span data-ttu-id="b540c-134">Описание свойства является необязательным.</span><span class="sxs-lookup"><span data-stu-id="b540c-134">The property description is optional.</span></span>  
  
 <span data-ttu-id="b540c-135">**Настройка списка свойств поиска для полнотекстового индекса**</span><span class="sxs-lookup"><span data-stu-id="b540c-135">**To configure a search property list for a full-text index**</span></span>  
  
-   [<span data-ttu-id="b540c-136">Поиск свойств документа с помощью списков свойств поиска</span><span class="sxs-lookup"><span data-stu-id="b540c-136">Search Document Properties with Search Property Lists</span></span>](../relational-databases/search/search-document-properties-with-search-property-lists.md)  
  
## <a name="permissions"></a><span data-ttu-id="b540c-137">Разрешения</span><span class="sxs-lookup"><span data-stu-id="b540c-137">Permissions</span></span>  
 <span data-ttu-id="b540c-138">См. раздел [ALTER Search Property LIST &#40;&#41;Transact-SQL ](/sql/t-sql/statements/alter-search-property-list-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b540c-138">See [ALTER SEARCH PROPERTY LIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-search-property-list-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b540c-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="b540c-139">See Also</span></span>  
 <span data-ttu-id="b540c-140">[ИЗМЕНЕНИЕ списка свойств поиска &#40;&#41;Transact-SQL](/sql/t-sql/statements/alter-search-property-list-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b540c-140">[ALTER SEARCH PROPERTY LIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-search-property-list-transact-sql) </span></span>  
 <span data-ttu-id="b540c-141">[Поиск свойств документа с помощью списков свойств поиска](../relational-databases/search/search-document-properties-with-search-property-lists.md) </span><span class="sxs-lookup"><span data-stu-id="b540c-141">[Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md) </span></span>  
 [<span data-ttu-id="b540c-142">sys.registered_search_property_lists (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b540c-142">sys.registered_search_property_lists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-registered-search-property-lists-transact-sql)  
  
  
