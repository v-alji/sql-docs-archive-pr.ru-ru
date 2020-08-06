---
title: MSSQLSERVER_2501 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2501 (Database Engine error)
ms.assetid: 895aafe3-a4e7-4ed8-acc5-93be76ef3664
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 200997dcfe7bf8a5933b9fce492daabd5baffd04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734098"
---
# <a name="mssqlserver_2501"></a><span data-ttu-id="1a027-102">MSSQLSERVER_2501</span><span class="sxs-lookup"><span data-stu-id="1a027-102">MSSQLSERVER_2501</span></span>
    
## <a name="details"></a><span data-ttu-id="1a027-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="1a027-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1a027-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="1a027-104">Product Name</span></span>|<span data-ttu-id="1a027-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1a027-105">SQL Server</span></span>|  
|<span data-ttu-id="1a027-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="1a027-106">Event ID</span></span>|<span data-ttu-id="1a027-107">2501</span><span class="sxs-lookup"><span data-stu-id="1a027-107">2501</span></span>|  
|<span data-ttu-id="1a027-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="1a027-108">Event Source</span></span>|<span data-ttu-id="1a027-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1a027-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1a027-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="1a027-110">Component</span></span>|<span data-ttu-id="1a027-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1a027-111">SQLEngine</span></span>|  
|<span data-ttu-id="1a027-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="1a027-112">Symbolic Name</span></span>|<span data-ttu-id="1a027-113">DBCC_NO_SUCH_TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1a027-113">DBCC_NO_SUCH_TABLE_NAME</span></span>|  
|<span data-ttu-id="1a027-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="1a027-114">Message Text</span></span>|<span data-ttu-id="1a027-115">Невозможно найти таблицу или объект с именем «NAME».</span><span class="sxs-lookup"><span data-stu-id="1a027-115">Cannot find a table or object with the name 'NAME'.</span></span> <span data-ttu-id="1a027-116">Проверьте системный каталог.</span><span class="sxs-lookup"><span data-stu-id="1a027-116">Check the system catalog.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1a027-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="1a027-117">Explanation</span></span>  
 <span data-ttu-id="1a027-118">Не удается найти указанный объект.</span><span class="sxs-lookup"><span data-stu-id="1a027-118">The specified object cannot be found.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="1a027-119">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="1a027-119">Possible Causes</span></span>  
 <span data-ttu-id="1a027-120">Возможны следующие причины возникновения этой ошибки.</span><span class="sxs-lookup"><span data-stu-id="1a027-120">This error can be caused by one of the following problems:</span></span>  
  
-   <span data-ttu-id="1a027-121">Объект указан неверно.</span><span class="sxs-lookup"><span data-stu-id="1a027-121">The object is not specified correctly.</span></span>  
  
-   <span data-ttu-id="1a027-122">Объект не существует или был удален до того, как инструкция к нему обратилась.</span><span class="sxs-lookup"><span data-stu-id="1a027-122">The object does not exist, or the object was dropped before a statement tried to use it.</span></span>  
  
-   <span data-ttu-id="1a027-123">Объект может существовать, но быть недоступным пользователю.</span><span class="sxs-lookup"><span data-stu-id="1a027-123">The object might exist, but could not be exposed to the user.</span></span> <span data-ttu-id="1a027-124">Например, у пользователя могут отсутствовать необходимые разрешения для данного объекта, либо объект является внутренней таблицей, которую пользователь просматривать не может.</span><span class="sxs-lookup"><span data-stu-id="1a027-124">For example, the user might not have permissions on the object, or the object is an internal table that could not be seen by a user.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1a027-125">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="1a027-125">User Action</span></span>  
  
-   <span data-ttu-id="1a027-126">Проверьте правильность контекста текущей базы данных.</span><span class="sxs-lookup"><span data-stu-id="1a027-126">Verify the current database context is correct.</span></span> <span data-ttu-id="1a027-127">Дополнительные сведения см. в статье [USE (Transact-SQL)](/sql/t-sql/language-elements/use-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1a027-127">For more information, see [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span></span>  
  
-   <span data-ttu-id="1a027-128">Проверьте правильность имени таблицы или объекта.</span><span class="sxs-lookup"><span data-stu-id="1a027-128">Verify that the table or object name is spelled correctly.</span></span>  
  
-   <span data-ttu-id="1a027-129">Проверьте имя схемы, содержащей объект.</span><span class="sxs-lookup"><span data-stu-id="1a027-129">Verify the schema name that contains the object.</span></span> <span data-ttu-id="1a027-130">Если объект принадлежит к схеме, отличной от схемы по умолчанию (**dbo**), имя таблицы или объекта необходимо указывать в двухкомпонентном формате *имя_схемы.имя_объекта*.</span><span class="sxs-lookup"><span data-stu-id="1a027-130">If the object belongs to a schema other than the default (**dbo**) schema, you must specify the table or object name by using the two-part format *schema_name.object_name*.</span></span>  
  
-   <span data-ttu-id="1a027-131">Проверьте наличие объекта в системных таблицах.</span><span class="sxs-lookup"><span data-stu-id="1a027-131">Verify that the object exists in the system tables.</span></span> <span data-ttu-id="1a027-132">Чтобы проверить существование таблицы или другого объекта на уровне схемы, отправьте запрос к представлению каталога [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1a027-132">To verify whether a table or other schema-scoped object exists, query the [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) catalog view.</span></span> <span data-ttu-id="1a027-133">Если объект отсутствует в системных таблицах, значит он был удален или у пользователя отсутствуют разрешения на просмотр метаданных объекта.</span><span class="sxs-lookup"><span data-stu-id="1a027-133">If the object is not in the system tables, the object has been deleted, or the user does not have permissions to view the object metadata.</span></span> <span data-ttu-id="1a027-134">Дополнительные сведения о просмотре метаданных объекта см. в статье [Настройка видимости метаданных](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="1a027-134">For more information about how to view object metadata, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a027-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="1a027-135">See Also</span></span>  
 [<span data-ttu-id="1a027-136">Представления каталога (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1a027-136">Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql)  
  
  
