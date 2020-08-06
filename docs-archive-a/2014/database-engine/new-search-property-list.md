---
title: Новый список свойств поиска | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.spl.newsearchpropertylist.f1
ms.assetid: ffca78e9-8608-4b15-bd38-b2d78da4247a
author: rothja
ms.author: jroth
ms.openlocfilehash: 48c9e475b380d5f0c7310e33717f261c38acbbd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667872"
---
# <a name="new-search-property-list"></a><span data-ttu-id="efae1-102">Новый список свойств поиска</span><span class="sxs-lookup"><span data-stu-id="efae1-102">New Search Property List</span></span>
  <span data-ttu-id="efae1-103">Это диалоговое окно используется для создания списка свойств поиска.</span><span class="sxs-lookup"><span data-stu-id="efae1-103">Use this dialog box to create a search property list.</span></span>  
  
## <a name="options"></a><span data-ttu-id="efae1-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="efae1-104">Options</span></span>  
 <span data-ttu-id="efae1-105">**Имя списка свойств поиска**</span><span class="sxs-lookup"><span data-stu-id="efae1-105">**Search property list name**</span></span>  
 <span data-ttu-id="efae1-106">Введите имя списка свойств поиска.</span><span class="sxs-lookup"><span data-stu-id="efae1-106">Enter the name of the search property list.</span></span>  
  
 <span data-ttu-id="efae1-107">**Владелец**</span><span class="sxs-lookup"><span data-stu-id="efae1-107">**Owner**</span></span>  
 <span data-ttu-id="efae1-108">Укажите владельца списка свойств поиска.</span><span class="sxs-lookup"><span data-stu-id="efae1-108">Specify the owner of the search property list.</span></span> <span data-ttu-id="efae1-109">Чтобы сделать владельцем текущего пользователя, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="efae1-109">If you want ownership to be assigned to yourself, that is, to the current user, leave this field empty.</span></span> <span data-ttu-id="efae1-110">Чтобы указать другого пользователя, нажмите кнопку обзора.</span><span class="sxs-lookup"><span data-stu-id="efae1-110">To specify a different user, click the browse button.</span></span>  
  
### <a name="create-search-property-list-options"></a><span data-ttu-id="efae1-111">Параметры создания списка свойств поиска</span><span class="sxs-lookup"><span data-stu-id="efae1-111">Create Search Property List Options</span></span>  
 <span data-ttu-id="efae1-112">Выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="efae1-112">Click one of the following options:</span></span>  
  
 <span data-ttu-id="efae1-113">**Создание пустого списка свойств поиска**</span><span class="sxs-lookup"><span data-stu-id="efae1-113">**Create an empty search property list**</span></span>  
 <span data-ttu-id="efae1-114">Создает список свойств поиска без свойств.</span><span class="sxs-lookup"><span data-stu-id="efae1-114">Creates a search property list without any properties.</span></span>  
  
 <span data-ttu-id="efae1-115">**Создание на основе существующего списка свойств поиска**</span><span class="sxs-lookup"><span data-stu-id="efae1-115">**Create from an existing search property list**</span></span>  
 <span data-ttu-id="efae1-116">Копирует свойства существующего списка свойств поиска в новый список свойств.</span><span class="sxs-lookup"><span data-stu-id="efae1-116">Copies the properties of an existing search property list into the new property list.</span></span> <span data-ttu-id="efae1-117">Списки свойств поиска — это защищаемые объекты базы данных, поэтому необходимо указать базу данных, содержащую список свойств, который нужно копировать.</span><span class="sxs-lookup"><span data-stu-id="efae1-117">Search property lists are database objects, so you must specify the database that contains the property list that you want to copy.</span></span>  
  
 <span data-ttu-id="efae1-118">**База данных источника**</span><span class="sxs-lookup"><span data-stu-id="efae1-118">**Source database**</span></span>  
 <span data-ttu-id="efae1-119">Укажите имя базы данных, которой принадлежит существующий список свойств поиска.</span><span class="sxs-lookup"><span data-stu-id="efae1-119">Specify the name of the database to which the existing search property list belongs.</span></span> <span data-ttu-id="efae1-120">По умолчанию выбрана текущая база данных.</span><span class="sxs-lookup"><span data-stu-id="efae1-120">The current database is selected by default.</span></span> <span data-ttu-id="efae1-121">При необходимости можно использовать список для выбора другой базы данных, если текущее соединение связано с идентификатором пользователя в базе данных.</span><span class="sxs-lookup"><span data-stu-id="efae1-121">Optionally, you can use the list box to select another database, if your current connection is associated with a user ID in that database.</span></span>  
  
 <span data-ttu-id="efae1-122">**Исходный список свойств поиска**</span><span class="sxs-lookup"><span data-stu-id="efae1-122">**Source search property list**</span></span>  
 <span data-ttu-id="efae1-123">Выберите имя существующего списка свойств поиска из тех, которые принадлежат выбранной базе данных.</span><span class="sxs-lookup"><span data-stu-id="efae1-123">Select the name of an existing search property list from those belonging to the selected database.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="efae1-124">Разрешения</span><span class="sxs-lookup"><span data-stu-id="efae1-124">Permissions</span></span>  
 <span data-ttu-id="efae1-125">См. раздел [Создание списка свойств поиска &#40;&#41;Transact-SQL ](/sql/t-sql/statements/create-search-property-list-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="efae1-125">See [CREATE SEARCH PROPERTY LIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-search-property-list-transact-sql).</span></span>  
  
## <a name="to-use-sql-server-management-studio-to-manage-search-property-lists"></a><span data-ttu-id="efae1-126">Управление списками свойств поиска в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="efae1-126">To Use SQL Server Management Studio to Manage Search Property Lists</span></span>  
 <span data-ttu-id="efae1-127">Сведения о создании, просмотре, изменении или удалении списка свойств поиска, а также о настройке полнотекстового индекса для поиска свойств см. в разделе [Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span><span class="sxs-lookup"><span data-stu-id="efae1-127">For information about how to create, view, change, or delete a search property list, and about how to configure a full-text index for property searching, see [Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efae1-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="efae1-128">See Also</span></span>  
 <span data-ttu-id="efae1-129">[Создание списка свойств поиска &#40;&#41;Transact-SQL](/sql/t-sql/statements/create-search-property-list-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="efae1-129">[CREATE SEARCH PROPERTY LIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-search-property-list-transact-sql) </span></span>  
 <span data-ttu-id="efae1-130">[Поиск свойств документа с помощью списков свойств поиска](../relational-databases/search/search-document-properties-with-search-property-lists.md) </span><span class="sxs-lookup"><span data-stu-id="efae1-130">[Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md) </span></span>  
 [<span data-ttu-id="efae1-131">sys.registered_search_property_lists (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="efae1-131">sys.registered_search_property_lists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-registered-search-property-lists-transact-sql)  
  
  
