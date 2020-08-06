---
title: MSSQLSERVER_208 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 208 (Database Engine error)
ms.assetid: 4b1895f5-3197-4da1-af86-954c93507956
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 97ab3eb220c03c3de0c95251861f3b947890b090
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655244"
---
# <a name="mssqlserver_208"></a><span data-ttu-id="d5c66-102">MSSQLSERVER_208</span><span class="sxs-lookup"><span data-stu-id="d5c66-102">MSSQLSERVER_208</span></span>
    
## <a name="details"></a><span data-ttu-id="d5c66-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="d5c66-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d5c66-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="d5c66-104">Product Name</span></span>|<span data-ttu-id="d5c66-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d5c66-105">SQL Server</span></span>|  
|<span data-ttu-id="d5c66-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="d5c66-106">Event ID</span></span>|<span data-ttu-id="d5c66-107">208</span><span class="sxs-lookup"><span data-stu-id="d5c66-107">208</span></span>|  
|<span data-ttu-id="d5c66-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="d5c66-108">Event Source</span></span>|<span data-ttu-id="d5c66-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d5c66-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d5c66-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="d5c66-110">Component</span></span>|<span data-ttu-id="d5c66-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d5c66-111">SQLEngine</span></span>|  
|<span data-ttu-id="d5c66-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="d5c66-112">Symbolic Name</span></span>|<span data-ttu-id="d5c66-113">SQ_BADOBJECT</span><span class="sxs-lookup"><span data-stu-id="d5c66-113">SQ_BADOBJECT</span></span>|  
|<span data-ttu-id="d5c66-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="d5c66-114">Message Text</span></span>|<span data-ttu-id="d5c66-115">Недопустимое имя объекта «%.\*ls».</span><span class="sxs-lookup"><span data-stu-id="d5c66-115">Invalid object name '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d5c66-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="d5c66-116">Explanation</span></span>  
 <span data-ttu-id="d5c66-117">Не удается найти указанный объект.</span><span class="sxs-lookup"><span data-stu-id="d5c66-117">The specified object cannot be found.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="d5c66-118">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="d5c66-118">Possible Causes</span></span>  
 <span data-ttu-id="d5c66-119">Возможны следующие причины возникновения этой ошибки.</span><span class="sxs-lookup"><span data-stu-id="d5c66-119">This error can be caused by one of the following problems:</span></span>  
  
-   <span data-ttu-id="d5c66-120">Объект указан неверно.</span><span class="sxs-lookup"><span data-stu-id="d5c66-120">The object is not specified correctly.</span></span>  
  
-   <span data-ttu-id="d5c66-121">Объект не существует в текущей базе данных или в указанной базе данных.</span><span class="sxs-lookup"><span data-stu-id="d5c66-121">The object does not exist in the current database or in the specified database.</span></span>  
  
-   <span data-ttu-id="d5c66-122">Объект существует, но пользователю не может быть предоставлен к нему доступ.</span><span class="sxs-lookup"><span data-stu-id="d5c66-122">The object exists, but could not be exposed to the user.</span></span> <span data-ttu-id="d5c66-123">Например, может оказаться так, что пользователь не имеет разрешений для доступа к объекту или объект создан в инструкции EXECUTE, но доступ к нему осуществляется вне области действия инструкции EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="d5c66-123">For example, the user might not have permissions on the object or the object is created within an EXECUTE statement but accessed outside the scope of the EXECUTE statement.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d5c66-124">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="d5c66-124">User Action</span></span>  
 <span data-ttu-id="d5c66-125">Проверьте следующую информацию и исправьте инструкцию соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="d5c66-125">Verify the following information and correct the statement as appropriate.</span></span>  
  
-   <span data-ttu-id="d5c66-126">Имя объекта записано правильно.</span><span class="sxs-lookup"><span data-stu-id="d5c66-126">The object name is spelled correctly.</span></span>  
  
-   <span data-ttu-id="d5c66-127">Контекст текущей базы данных является правильным.</span><span class="sxs-lookup"><span data-stu-id="d5c66-127">The current database context is correct.</span></span> <span data-ttu-id="d5c66-128">Если не указано имя базы данных для объекта, то объект должен существовать в текущей базе данных.</span><span class="sxs-lookup"><span data-stu-id="d5c66-128">If a database name for the object is not specified, the object must exist in the current database.</span></span> <span data-ttu-id="d5c66-129">Дополнительные сведения об установке контекста базы данных см. в статье [USE (Transact-SQL)](/sql/t-sql/language-elements/use-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d5c66-129">For more information about setting the database context, see [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span></span>  
  
-   <span data-ttu-id="d5c66-130">Объект существует в системных таблицах.</span><span class="sxs-lookup"><span data-stu-id="d5c66-130">The object exists in the system tables.</span></span> <span data-ttu-id="d5c66-131">Чтобы проверить существование таблицы или другого объекта на уровне схемы, отправьте запрос к представлению каталога **sys.objects**.</span><span class="sxs-lookup"><span data-stu-id="d5c66-131">To verify whether a table or other schema-scoped object exists, query the **sys.objects** catalog view.</span></span> <span data-ttu-id="d5c66-132">Если объект отсутствует в системных таблицах, значит он был удален или у пользователя отсутствуют разрешения на просмотр метаданных объекта.</span><span class="sxs-lookup"><span data-stu-id="d5c66-132">If the object is not in the system tables, the object has been deleted, or the user does not have permissions to view the object metadata.</span></span> <span data-ttu-id="d5c66-133">Дополнительные сведения о разрешениях на просмотр метаданных объекта см. в статье [Настройка видимости метаданных](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="d5c66-133">For more information about permissions to view object metadata, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
-   <span data-ttu-id="d5c66-134">Объект содержится в применяемой по умолчанию схеме пользователя.</span><span class="sxs-lookup"><span data-stu-id="d5c66-134">The object is contained in the default schema of the user.</span></span> <span data-ttu-id="d5c66-135">Если его там нет, имя объекта нужно указывать в двухкомпонентном формате: *имя_схемы.имя_объекта*.</span><span class="sxs-lookup"><span data-stu-id="d5c66-135">If it is not, the object must be specified using the two-part format *schema_name.object_name*.</span></span> <span data-ttu-id="d5c66-136">Следует отметить, что скалярные функции должны всегда вызываться с использованием по меньшей мере двухкомпонентного имени.</span><span class="sxs-lookup"><span data-stu-id="d5c66-136">Note that scalar-valued functions must always be invoked by using at least a two-part name.</span></span>  
  
-   <span data-ttu-id="d5c66-137">Учет регистра в параметрах сортировки базы данных.</span><span class="sxs-lookup"><span data-stu-id="d5c66-137">The case sensitivity of the database collation.</span></span>  
  
     <span data-ttu-id="d5c66-138">Если в базе данных используются параметры сортировки с учетом регистра, то имя объекта должно согласовываться по регистру с именем объекта в базе данных.</span><span class="sxs-lookup"><span data-stu-id="d5c66-138">When a database uses a case-sensitive collation, the object name must match the case of the object in the database.</span></span> <span data-ttu-id="d5c66-139">Например, если определенный объект имеет имя **MyTable** в базе данных с параметрами сортировки с учетом регистра, запросы, в которых этот объект именуется как **mytable** или **Mytable**, будут возвращать ошибку 208, так как имена объектов не согласуются.</span><span class="sxs-lookup"><span data-stu-id="d5c66-139">For example, when an object is specified as **MyTable** in a database with a case sensitive collation, queries that refer to the object as **mytable** or **Mytable** will cause error 208 to return because the object names do not match.</span></span>  
  
     <span data-ttu-id="d5c66-140">Параметры сортировки базы данных можно проверить, введя следующую инструкцию.</span><span class="sxs-lookup"><span data-stu-id="d5c66-140">You can verify the database collation by running the following statement.</span></span>  
  
    ```  
    SELECT collation_name FROM sys.databases WHERE name = 'database_name';  
    ```  
  
     <span data-ttu-id="d5c66-141">Аббревиатура CS в имени параметров сортировки указывает, что учитывается регистр символов.</span><span class="sxs-lookup"><span data-stu-id="d5c66-141">The abbreviation CS in the collation name indicates the collation is case sensitive.</span></span> <span data-ttu-id="d5c66-142">Например, значение Latin1_General_CS_AS определяет параметры сортировки с учетом регистра и с учетом диакритических знаков.</span><span class="sxs-lookup"><span data-stu-id="d5c66-142">For example, Latin1_General_CS_AS is a case sensitive, accent sensitive collation.</span></span> <span data-ttu-id="d5c66-143">Значение CI указывает, что в параметрах сортировки не учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="d5c66-143">CI indicates a case insensitive collation.</span></span>  
  
-   <span data-ttu-id="d5c66-144">Пользователь имеет разрешение на получение доступа к объекту.</span><span class="sxs-lookup"><span data-stu-id="d5c66-144">The user has permission to access the object.</span></span> <span data-ttu-id="d5c66-145">Чтобы проверить, какие разрешения имеет пользователь для доступа к объекту, можно воспользоваться системной функцией **Has_Perms_By_Name**.</span><span class="sxs-lookup"><span data-stu-id="d5c66-145">To verify the permissions the user has on the object, use the **Has_Perms_By_Name** system function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5c66-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="d5c66-146">See Also</span></span>  
 <span data-ttu-id="d5c66-147">[Использование &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d5c66-147">[USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql) </span></span>  
 <span data-ttu-id="d5c66-148">[Настройка видимости метаданных](../security/metadata-visibility-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="d5c66-148">[Metadata Visibility Configuration](../security/metadata-visibility-configuration.md) </span></span>  
 [<span data-ttu-id="d5c66-149">HAS_PERMS_BY_NAME (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d5c66-149">HAS_PERMS_BY_NAME &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/has-perms-by-name-transact-sql)  
  
  
