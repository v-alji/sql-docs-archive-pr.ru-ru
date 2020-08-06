---
title: Переименование определяемых пользователем функций | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: c2695a5c-9cc5-4b18-8771-53027ca9a9af
author: rothja
ms.author: jroth
ms.openlocfilehash: ec923be64cf7819c4018ebda71a472f58b29cf8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669337"
---
# <a name="rename-user-defined-functions"></a><span data-ttu-id="ad7bf-102">Переименование определяемых пользователем функций</span><span class="sxs-lookup"><span data-stu-id="ad7bf-102">Rename User-defined Functions</span></span>
  <span data-ttu-id="ad7bf-103">Определяемые пользователем функции в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно переименовать с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad7bf-103">You can rename user-defined functions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ad7bf-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="ad7bf-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ad7bf-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="ad7bf-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ad7bf-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="ad7bf-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ad7bf-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="ad7bf-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ad7bf-108">**Для переименования определяемой пользователем функции используются.**</span><span class="sxs-lookup"><span data-stu-id="ad7bf-108">**To rename user-defined functions, using:**</span></span>  
  
     [<span data-ttu-id="ad7bf-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad7bf-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ad7bf-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ad7bf-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ad7bf-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="ad7bf-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ad7bf-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="ad7bf-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ad7bf-113">Имена функций должны соответствовать правилам для [идентификаторов](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="ad7bf-113">Function names must comply with the rules for [identifiers](../databases/database-identifiers.md).</span></span>  
  
-   <span data-ttu-id="ad7bf-114">При переименовании определяемой пользователем функции не изменяется имя соответствующего объекта в столбце определения представления каталога **sys.sql_modules** .</span><span class="sxs-lookup"><span data-stu-id="ad7bf-114">Renaming a user-defined function will not change the name of the corresponding object name in the definition column of the **sys.sql_modules** catalog view.</span></span> <span data-ttu-id="ad7bf-115">Поэтому не рекомендуется переименовывать объекты этого типа.</span><span class="sxs-lookup"><span data-stu-id="ad7bf-115">Therefore, we recommend that you do not rename this object type.</span></span> <span data-ttu-id="ad7bf-116">Лучше удалить хранимую процедуру и создать ее повторно с новым именем.</span><span class="sxs-lookup"><span data-stu-id="ad7bf-116">Instead, drop and re-create the stored procedure with its new name.</span></span>  
  
-   <span data-ttu-id="ad7bf-117">Изменение имени или определения определяемой пользователем функции может привести к тому, что все зависящие от нее объекты при выполнении будут возвращать ошибку, если они не будут обновлены в соответствии с внесенными в функцию изменениями.</span><span class="sxs-lookup"><span data-stu-id="ad7bf-117">Changing the name or definition of a user-defined function can cause dependent objects to fail when the objects are not updated to reflect the changes that have been made to the function.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ad7bf-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="ad7bf-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ad7bf-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="ad7bf-119">Permissions</span></span>  
 <span data-ttu-id="ad7bf-120">Для удаления функции у пользователя должно быть разрешение ALTER на схему, которой принадлежит функция, или разрешение CONTROL на функцию.</span><span class="sxs-lookup"><span data-stu-id="ad7bf-120">To drop the function, requires either ALTER permission on the schema to which the function belongs or CONTROL permission on the function.</span></span> <span data-ttu-id="ad7bf-121">Для повторного создания функции требуется разрешение CREATE FUNCTION на базу данных и разрешение ALTER на схему, в которой создается функция.</span><span class="sxs-lookup"><span data-stu-id="ad7bf-121">To re-create the function, requires CREATE FUNCTION permission in the database and ALTER permission on the schema in which the function is being created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ad7bf-122">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad7bf-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-user-defined-functions"></a><span data-ttu-id="ad7bf-123">Переименование определяемой пользователем функции</span><span class="sxs-lookup"><span data-stu-id="ad7bf-123">To rename user-defined functions</span></span>  
  
1.  <span data-ttu-id="ad7bf-124">В **обозревателе объектов**щелкните значок «плюс» рядом с базой данных, содержащей функцию, которую нужно переименовать.</span><span class="sxs-lookup"><span data-stu-id="ad7bf-124">In **Object Explorer**, click the plus sign next to the database that contains the function you wish to rename and then</span></span>  
  
2.  <span data-ttu-id="ad7bf-125">Щелкните значок «плюс» рядом с папкой **Программирование** .</span><span class="sxs-lookup"><span data-stu-id="ad7bf-125">Click the plus sign next to the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="ad7bf-126">Щелкните значок «плюс» рядом с папкой, содержащей функцию, которую надо переименовать.</span><span class="sxs-lookup"><span data-stu-id="ad7bf-126">Click the plus sign next to the folder that contains the function you wish to rename:</span></span>  
  
    -   <span data-ttu-id="ad7bf-127">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="ad7bf-127">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="ad7bf-128">Скалярная функция</span><span class="sxs-lookup"><span data-stu-id="ad7bf-128">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="ad7bf-129">Агрегатная функция</span><span class="sxs-lookup"><span data-stu-id="ad7bf-129">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="ad7bf-130">Щелкните правой кнопкой мыши функцию, которую нужно переименовать, и выберите пункт **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="ad7bf-130">Right-click the function you wish to rename and select **Rename**.</span></span>  
  
5.  <span data-ttu-id="ad7bf-131">Введите новое имя функции.</span><span class="sxs-lookup"><span data-stu-id="ad7bf-131">Enter the function's new name.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ad7bf-132">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ad7bf-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="ad7bf-133">**Переименование определяемой пользователем функции**</span><span class="sxs-lookup"><span data-stu-id="ad7bf-133">**To rename user-defined functions**</span></span>  
  
 <span data-ttu-id="ad7bf-134">Эту задачу нельзя выполнить с помощью инструкций Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="ad7bf-134">This task cannot be performed using Transact-SQL statements.</span></span> <span data-ttu-id="ad7bf-135">Чтобы переименовать определяемую пользователем функцию с помощью Transact-SQL, необходимо сначала удалить существующую функцию, а затем создать ее повторно с новым именем.</span><span class="sxs-lookup"><span data-stu-id="ad7bf-135">To rename a user-defined function using Transact-SQL, you must first delete the existing function and then re-create it with the new name.</span></span> <span data-ttu-id="ad7bf-136">Убедитесь, что весь код и приложения, ссылающиеся на старое имя функции, теперь используют новое имя.</span><span class="sxs-lookup"><span data-stu-id="ad7bf-136">Ensure that all code and applications that used the function's old name now use the new name.</span></span>  
  
 <span data-ttu-id="ad7bf-137">Дополнительные сведения см. в разделах [CREATE FUNCTION (Transact-SQL)](/sql/t-sql/statements/create-function-transact-sql) и [DROP FUNCTION (Transact-SQL)](/sql/t-sql/statements/drop-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ad7bf-137">For more information, see [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) and [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad7bf-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="ad7bf-138">See Also</span></span>  
 <span data-ttu-id="ad7bf-139">[sys.sql_expression_dependencies (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ad7bf-139">[sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) </span></span>  
 [<span data-ttu-id="ad7bf-140">Просмотр пользовательских функций</span><span class="sxs-lookup"><span data-stu-id="ad7bf-140">View User-defined Functions</span></span>](user-defined-functions.md)  
  
  
