---
title: Получение сведений о представлении | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.viewproperties.general.f1
helpviewer_keywords:
- views [SQL Server], status information
- metadata [SQL Server], views
- dependencies [SQL Server], views
- displaying view information
- views [SQL Server], metadata
- viewing view information
- status information [SQL Server], views
- view dependencies
ms.assetid: 05a73e33-8f85-4fb6-80c1-1b659e753403
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4277aad4c1de0140606575c7ba437408518b3c8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654977"
---
# <a name="get-information-about-a-view"></a><span data-ttu-id="7212a-102">Получение сведений о представлении</span><span class="sxs-lookup"><span data-stu-id="7212a-102">Get Information About a View</span></span>
  <span data-ttu-id="7212a-103">Получить сведения об определении или свойствах представления в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7212a-103">You can gain information about a view's definition or properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7212a-104">Возможность просмотреть определение представления может понадобиться, чтобы понять, как его данные извлекаются из исходных таблиц, или чтобы увидеть данные, определенные представлением.</span><span class="sxs-lookup"><span data-stu-id="7212a-104">You may need to see the definition of the view to understand how its data is derived from the source tables or to see the data defined by the view.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7212a-105">Если имя объекта, на который ссылается представление, было изменено, необходимо изменить представление так, чтобы в его тексте использовалось новое имя.</span><span class="sxs-lookup"><span data-stu-id="7212a-105">If you change the name of an object referenced by a view, you must modify the view so that its text reflects the new name.</span></span> <span data-ttu-id="7212a-106">Следовательно, прежде чем переименовывать объект, следует отобразить зависимости объекта, чтобы определить, повлияет ли предполагаемое изменение на какие-либо представления.</span><span class="sxs-lookup"><span data-stu-id="7212a-106">Therefore, before renaming an object, display the dependencies of the object first to determine if any views are affected by the proposed change.</span></span>  
  
 <span data-ttu-id="7212a-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="7212a-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7212a-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="7212a-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7212a-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="7212a-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7212a-110">**Получение сведений о представлении с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="7212a-110">**To get information about a view, using:**</span></span>  
  
     [<span data-ttu-id="7212a-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7212a-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7212a-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7212a-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7212a-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="7212a-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7212a-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="7212a-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7212a-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="7212a-115">Permissions</span></span>  
 <span data-ttu-id="7212a-116">Для использования `sp_helptext` для получения определения представления требуется членство в роли **public** .</span><span class="sxs-lookup"><span data-stu-id="7212a-116">Using `sp_helptext` to return the definition of a view requires membership in the **public** role.</span></span> <span data-ttu-id="7212a-117">Для использования `sys.sql_expression_dependencies` для поиска всех зависимостей в представлении требуется разрешение VIEW DEFINITION в базе данных и разрешение SELECT в `sys.sql_expression_dependencies` для базы данных.</span><span class="sxs-lookup"><span data-stu-id="7212a-117">Using `sys.sql_expression_dependencies` to find all the dependencies on a view requires VIEW DEFINITION permission on the database and SELECT permission on `sys.sql_expression_dependencies` for the database.</span></span> <span data-ttu-id="7212a-118">Такие определения системных объектов, как полученные в SELECT OBJECT_DEFINITION, видимы для всех.</span><span class="sxs-lookup"><span data-stu-id="7212a-118">System object definitions, like the ones returned in SELECT OBJECT_DEFINITION, are publicly visible.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7212a-119">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7212a-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="get-view-properties-by-using-object-explorer"></a><span data-ttu-id="7212a-120">Получение свойств представления с помощью обозревателя объектов</span><span class="sxs-lookup"><span data-stu-id="7212a-120">Get view properties by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="7212a-121">В **обозревателе объектов**щелкните знак «плюс» рядом с базой данных, содержащей представление, свойства которого необходимо просмотреть, а затем щелкните знак «плюс», чтобы развернуть папку **Представления** .</span><span class="sxs-lookup"><span data-stu-id="7212a-121">In **Object Explorer**, click the plus sign next to the database that contains the view to which you want to view the properties, and then click the plus sign to expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="7212a-122">Щелкните правой кнопкой представление, свойства которого необходимо просмотреть, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7212a-122">Right-click the view of which you want to view the properties and select **Properties**.</span></span>  
  
     <span data-ttu-id="7212a-123">В диалоговом окне **Свойства представления** отображаются следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="7212a-123">The following properties show in the **View Properties** dialog box.</span></span>  
  
     <span data-ttu-id="7212a-124">**База данных**</span><span class="sxs-lookup"><span data-stu-id="7212a-124">**Database**</span></span>  
     <span data-ttu-id="7212a-125">Имя базы данных, содержащей это представление.</span><span class="sxs-lookup"><span data-stu-id="7212a-125">The name of the database containing this view.</span></span>  
  
     <span data-ttu-id="7212a-126">**Server**</span><span class="sxs-lookup"><span data-stu-id="7212a-126">**Server**</span></span>  
     <span data-ttu-id="7212a-127">Имя текущего экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="7212a-127">The name of the current server instance.</span></span>  
  
     <span data-ttu-id="7212a-128">**Пользователь**</span><span class="sxs-lookup"><span data-stu-id="7212a-128">**User**</span></span>  
     <span data-ttu-id="7212a-129">Имя пользователя этого соединения.</span><span class="sxs-lookup"><span data-stu-id="7212a-129">The name of the user of this connection.</span></span>  
  
     <span data-ttu-id="7212a-130">**Дата создания**</span><span class="sxs-lookup"><span data-stu-id="7212a-130">**Created date**</span></span>  
     <span data-ttu-id="7212a-131">Отображает дату создания представления.</span><span class="sxs-lookup"><span data-stu-id="7212a-131">Displays the date the view was created.</span></span>  
  
     <span data-ttu-id="7212a-132">**Название**</span><span class="sxs-lookup"><span data-stu-id="7212a-132">**Name**</span></span>  
     <span data-ttu-id="7212a-133">Имя текущего представления.</span><span class="sxs-lookup"><span data-stu-id="7212a-133">The name of the current view.</span></span>  
  
     <span data-ttu-id="7212a-134">**Схема**</span><span class="sxs-lookup"><span data-stu-id="7212a-134">**Schema**</span></span>  
     <span data-ttu-id="7212a-135">Схема, которой принадлежит представление.</span><span class="sxs-lookup"><span data-stu-id="7212a-135">Displays the schema that owns the view.</span></span>  
  
     <span data-ttu-id="7212a-136">**Системный объект**</span><span class="sxs-lookup"><span data-stu-id="7212a-136">**System object**</span></span>  
     <span data-ttu-id="7212a-137">Указывает, является ли представление системным объектом.</span><span class="sxs-lookup"><span data-stu-id="7212a-137">Indicates whether the view is a system object.</span></span> <span data-ttu-id="7212a-138">Возможные значения: True и False.</span><span class="sxs-lookup"><span data-stu-id="7212a-138">Values are True and False.</span></span>  
  
     <span data-ttu-id="7212a-139">**Значения NULL по стандарту ANSI**</span><span class="sxs-lookup"><span data-stu-id="7212a-139">**ANSI NULLs**</span></span>  
     <span data-ttu-id="7212a-140">Указывает, был ли объект создан с параметром ANSI NULL.</span><span class="sxs-lookup"><span data-stu-id="7212a-140">Indicates if the object was created with the ANSI NULLs option.</span></span>  
  
     <span data-ttu-id="7212a-141">**Зашифрована**</span><span class="sxs-lookup"><span data-stu-id="7212a-141">**Encrypted**</span></span>  
     <span data-ttu-id="7212a-142">Указывает, зашифровано ли представление.</span><span class="sxs-lookup"><span data-stu-id="7212a-142">Indicates whether the view is encrypted.</span></span> <span data-ttu-id="7212a-143">Возможные значения: True и False.</span><span class="sxs-lookup"><span data-stu-id="7212a-143">Values are True and False.</span></span>  
  
     <span data-ttu-id="7212a-144">**Заключенный в кавычки идентификатор**</span><span class="sxs-lookup"><span data-stu-id="7212a-144">**Quoted identifier**</span></span>  
     <span data-ttu-id="7212a-145">Показывает, был ли объект создан с параметром «заключенный в кавычки идентификатор».</span><span class="sxs-lookup"><span data-stu-id="7212a-145">Indicates if the object was created with the quoted identifier option.</span></span>  
  
     <span data-ttu-id="7212a-146">**Привязка к схеме**</span><span class="sxs-lookup"><span data-stu-id="7212a-146">**Schema bound**</span></span>  
     <span data-ttu-id="7212a-147">Указывает, является ли представление привязанным к схеме.</span><span class="sxs-lookup"><span data-stu-id="7212a-147">Indicates whether the view is schema-bound.</span></span> <span data-ttu-id="7212a-148">Возможные значения: True и False.</span><span class="sxs-lookup"><span data-stu-id="7212a-148">Values are True and False.</span></span> <span data-ttu-id="7212a-149">Сведения о представлениях, привязанных к схеме, см. в подразделе SCHEMABINDING раздела [CREATE VIEW (Transact-SQL)](/sql/t-sql/statements/create-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7212a-149">For information about schema-bound views, see the SCHEMABINDING portion of [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span></span>  
  
#### <a name="getting-view-properties-by-using-the-view-designer-tool"></a><span data-ttu-id="7212a-150">Получение свойств представления с помощью конструктора представлений</span><span class="sxs-lookup"><span data-stu-id="7212a-150">Getting view properties by using the View Designer tool</span></span>  
  
1.  <span data-ttu-id="7212a-151">В **обозревателе объектов**разверните базу данных, содержащую представление, свойства которого необходимо просмотреть, а затем разверните папку **Представления** .</span><span class="sxs-lookup"><span data-stu-id="7212a-151">In **Object Explorer**, expand the database that contains the view to which you want to view the properties, and then expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="7212a-152">Щелкните правой кнопкой мыши представление, свойства которого необходимо просмотреть, и выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="7212a-152">Right-click the view of which you want to view the properties and select **Design**.</span></span>  
  
3.  <span data-ttu-id="7212a-153">Щелкните правой кнопкой мыши пустое пространство на панели диаграммы и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7212a-153">Right-click in the blank space of the Diagram pane and click **Properties**.</span></span>  
  
     <span data-ttu-id="7212a-154">На панели **Свойства** отображаются следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="7212a-154">The following properties show in the **Properties** pane.</span></span>  
  
     <span data-ttu-id="7212a-155">**(Имя)**</span><span class="sxs-lookup"><span data-stu-id="7212a-155">**(Name)**</span></span>  
     <span data-ttu-id="7212a-156">Имя текущего представления.</span><span class="sxs-lookup"><span data-stu-id="7212a-156">The name of the current view.</span></span>  
  
     <span data-ttu-id="7212a-157">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="7212a-157">**Database Name**</span></span>  
     <span data-ttu-id="7212a-158">Имя базы данных, содержащей это представление.</span><span class="sxs-lookup"><span data-stu-id="7212a-158">The name of the database containing this view.</span></span>  
  
     <span data-ttu-id="7212a-159">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7212a-159">**Description**</span></span>  
     <span data-ttu-id="7212a-160">Краткое описание текущего представления.</span><span class="sxs-lookup"><span data-stu-id="7212a-160">A brief description of the current view.</span></span>  
  
     <span data-ttu-id="7212a-161">**Схема**</span><span class="sxs-lookup"><span data-stu-id="7212a-161">**Schema**</span></span>  
     <span data-ttu-id="7212a-162">Схема, которой принадлежит представление.</span><span class="sxs-lookup"><span data-stu-id="7212a-162">Displays the schema that owns the view.</span></span>  
  
     <span data-ttu-id="7212a-163">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="7212a-163">**Server Name**</span></span>  
     <span data-ttu-id="7212a-164">Имя текущего экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="7212a-164">The name of the current server instance.</span></span>  
  
     <span data-ttu-id="7212a-165">**Привязка к схеме**</span><span class="sxs-lookup"><span data-stu-id="7212a-165">**Bind to Schema**</span></span>  
     <span data-ttu-id="7212a-166">Предотвращает такие изменения пользователями базовых объектов, задействованных в представлении, в результате которых определение представления становится недействительным.</span><span class="sxs-lookup"><span data-stu-id="7212a-166">Prevents users from modifying the underlying objects that contribute to this view in any way that would invalidate the view definition.</span></span>  
  
     <span data-ttu-id="7212a-167">**Детерминированное**</span><span class="sxs-lookup"><span data-stu-id="7212a-167">**Deterministic**</span></span>  
     <span data-ttu-id="7212a-168">Указывает, может ли тип данных для выбранного столбца быть точно определен</span><span class="sxs-lookup"><span data-stu-id="7212a-168">Shows whether the data type of the selected column can be determined with certainty</span></span>  
  
     <span data-ttu-id="7212a-169">**Различные значения**</span><span class="sxs-lookup"><span data-stu-id="7212a-169">**Distinct Values**</span></span>  
     <span data-ttu-id="7212a-170">Указывает, что запрос будет отфильтровывать повторения в представлении.</span><span class="sxs-lookup"><span data-stu-id="7212a-170">Specifies that the query will filter out duplicates in the view.</span></span> <span data-ttu-id="7212a-171">Этот параметр полезен при использовании только некоторых столбцов из таблицы, притом что эти столбцы могут содержать повторяющиеся значения, или если обработка соединения двух или более таблиц приводит к появлению повторяющихся строк в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="7212a-171">This option is useful when you are using only some of the columns from a table and those columns might contain duplicate values, or when the process of joining two or more tables produces duplicate rows in the result set.</span></span> <span data-ttu-id="7212a-172">Выбор этого параметра эквивалентен вставке ключевого слова DISTINCT в инструкцию на панели SQL.</span><span class="sxs-lookup"><span data-stu-id="7212a-172">Choosing this option is equivalent to inserting the keyword DISTINCT into the statement in the SQL pane.</span></span>  
  
     <span data-ttu-id="7212a-173">**Расширение GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="7212a-173">**GROUP BY Extension**</span></span>  
     <span data-ttu-id="7212a-174">Указывает, что для представлений доступны дополнительные параметры, основанные на агрегатных запросах.</span><span class="sxs-lookup"><span data-stu-id="7212a-174">Specifies that additional options for views based on aggregate queries are available.</span></span>  
  
     <span data-ttu-id="7212a-175">**Выводить все столбцы**</span><span class="sxs-lookup"><span data-stu-id="7212a-175">**Output All Columns**</span></span>  
     <span data-ttu-id="7212a-176">Указывает, возвращаются ли в выбранном представлении все столбцы.</span><span class="sxs-lookup"><span data-stu-id="7212a-176">Shows whether all columns are returned by the selected view.</span></span> <span data-ttu-id="7212a-177">Этот параметр задается во время создания представления.</span><span class="sxs-lookup"><span data-stu-id="7212a-177">This is set at the time the view is created.</span></span>  
  
     <span data-ttu-id="7212a-178">**Комментарий SQL**</span><span class="sxs-lookup"><span data-stu-id="7212a-178">**SQL Comment**</span></span>  
     <span data-ttu-id="7212a-179">Показывает описание инструкций SQL.</span><span class="sxs-lookup"><span data-stu-id="7212a-179">Shows a description of the SQL statements.</span></span> <span data-ttu-id="7212a-180">Чтобы просмотреть или отредактировать описание целиком, щелкните его и затем нажмите кнопку с многоточием **(...)** справа от свойства.</span><span class="sxs-lookup"><span data-stu-id="7212a-180">To see the entire description, or to edit it, click the description and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="7212a-181">Комментарии могут содержать, например, сведения о том, кто использует это представление и когда оно используется.</span><span class="sxs-lookup"><span data-stu-id="7212a-181">Your comments might include information such as who uses the view and when they use it.</span></span>  
  
     <span data-ttu-id="7212a-182">**Спецификация TOP**</span><span class="sxs-lookup"><span data-stu-id="7212a-182">**Top Specification**</span></span>  
     <span data-ttu-id="7212a-183">Разворачивается для отображения свойств **Первые**, **Выражение**, **Процент**и **Со связями** .</span><span class="sxs-lookup"><span data-stu-id="7212a-183">Expands to show properties for the **Top**, **Expression**, **Percent**, and **With Ties** properties.</span></span>  
  
     <span data-ttu-id="7212a-184">**(Верх)**</span><span class="sxs-lookup"><span data-stu-id="7212a-184">**(Top)**</span></span>  
     <span data-ttu-id="7212a-185">Указывает, что представление будет иметь предложение TOP, возвращающее только первые n строк или первые n процентов строк из результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="7212a-185">Specifies that the view will include a TOP clause, which returns only the first n rows or first n percentage of rows in the result set.</span></span> <span data-ttu-id="7212a-186">По умолчанию представление возвращает первые 10 строк из результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="7212a-186">The default is that the view returns the first 10 rows in the result set.</span></span> <span data-ttu-id="7212a-187">Это поле позволяет изменить число возвращаемых строк или указать другой процент.</span><span class="sxs-lookup"><span data-stu-id="7212a-187">Use this to change the number of rows to return or to specify a different percentage</span></span>  
  
     <span data-ttu-id="7212a-188">**Выражение**</span><span class="sxs-lookup"><span data-stu-id="7212a-188">**Expression**</span></span>  
     <span data-ttu-id="7212a-189">Указывает, какой процент (если для параметра **Процент** выбрано значение **Да**) или какое количество записей (если для параметра **Процент** выбрано значение **Нет**) возвращает представление.</span><span class="sxs-lookup"><span data-stu-id="7212a-189">Shows what percent (if **Percent** is set to **Yes**) or records (if **Percent** is set to **No**) that the view will return.</span></span>  
  
     <span data-ttu-id="7212a-190">**Процент**</span><span class="sxs-lookup"><span data-stu-id="7212a-190">**Percent**</span></span>  
     <span data-ttu-id="7212a-191">Указывает, что запрос будет включать предложение **TOP** , возвращающее только первые n процентов строк из результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="7212a-191">Specifies that the query will include a **TOP** clause, returning only the first n percentage of rows in the result set</span></span>  
  
     <span data-ttu-id="7212a-192">**Со связями**</span><span class="sxs-lookup"><span data-stu-id="7212a-192">**With Ties**</span></span>  
     <span data-ttu-id="7212a-193">Указывает, что представление включает предложение **WITH TIES** .</span><span class="sxs-lookup"><span data-stu-id="7212a-193">Specifies that the view will include a **WITH TIES** clause.</span></span> <span data-ttu-id="7212a-194">**WITH TIES** полезно, если представление включает предложения **ORDER BY** и **TOP** , основанные на процентах.</span><span class="sxs-lookup"><span data-stu-id="7212a-194">**WITH TIES** is useful if a view includes an **ORDER BY** clause and a **TOP** clause based on percentage.</span></span> <span data-ttu-id="7212a-195">Если этот параметр установлен и пороговое значение процента приходится на середину набора строк с одинаковыми значениями в предложении **ORDER BY** , то данное представление будет расширено и будет включать все такие строки.</span><span class="sxs-lookup"><span data-stu-id="7212a-195">If this option is set, and if the percentage cutoff falls in the middle of a set of rows with identical values in the **ORDER BY** clause, the view is extended to include all such rows.</span></span>  
  
     <span data-ttu-id="7212a-196">**Спецификация Update**</span><span class="sxs-lookup"><span data-stu-id="7212a-196">**Update Specification**</span></span>  
     <span data-ttu-id="7212a-197">Разворачивается для отображения свойств **Правила обновления через представление** и **Параметр проверки** .</span><span class="sxs-lookup"><span data-stu-id="7212a-197">Expands to show properties for the **Update Using View Rules** and **Check Option** properties.</span></span>  
  
     <span data-ttu-id="7212a-198">**(Обновление с использованием правил представления.)**</span><span class="sxs-lookup"><span data-stu-id="7212a-198">**(Update Using View Rules)**</span></span>  
     <span data-ttu-id="7212a-199">Указывает, что все обновления и вставки в представлении будут преобразованы с помощью Microsoft Data Access Components (MDAC) в инструкции SQL, которые ссылаются на представление, а не в инструкции SQL, которые ссылаются непосредственно на базовые таблицы представления.</span><span class="sxs-lookup"><span data-stu-id="7212a-199">Indicates that all updates and insertions to the view will be translated by Microsoft Data Access Components (MDAC) into SQL statements that refer to the view, rather than into SQL statements that refer directly to the view's base tables.</span></span>  
  
     <span data-ttu-id="7212a-200">В некоторых случаях компоненты MDAC представляют операции обновления и вставки представления в виде операций обновления и вставки в базовых таблицах представления.</span><span class="sxs-lookup"><span data-stu-id="7212a-200">In some cases, MDAC manifests view update and view insert operations as updates and inserts against the view's underlying base tables.</span></span> <span data-ttu-id="7212a-201">Выбор **Обновление с использованием правил представления**позволяет гарантировать создание MDAC операций обновления и вставки для самого представления.</span><span class="sxs-lookup"><span data-stu-id="7212a-201">By selecting **Update Using View Rules**, you can ensure that MDAC generates update and insert operations against the view itself.</span></span>  
  
     <span data-ttu-id="7212a-202">**Параметр проверки**</span><span class="sxs-lookup"><span data-stu-id="7212a-202">**Check Option**</span></span>  
     <span data-ttu-id="7212a-203">Указывает, что при открытии этого представления и изменении панели **Результаты** источник данных проверяет соответствие добавленных или измененных данных предложению **WHERE** определения представления.</span><span class="sxs-lookup"><span data-stu-id="7212a-203">Indicates that when you open this view and modify the **Results** pane, the data source checks whether the added or modified data satisfies the **WHERE** clause of the view definition.</span></span> <span data-ttu-id="7212a-204">Если изменения не соответствуют предложению **WHERE** , будет отображено сообщение об ошибке с более подробными сведениями.</span><span class="sxs-lookup"><span data-stu-id="7212a-204">If your modification do not satisfy the **WHERE** clause, you will see an error with more information.</span></span>  
  
#### <a name="to-get-dependencies-on-the-view"></a><span data-ttu-id="7212a-205">Получение зависимостей представления</span><span class="sxs-lookup"><span data-stu-id="7212a-205">To get dependencies on the view</span></span>  
  
1.  <span data-ttu-id="7212a-206">В **обозревателе объектов**разверните базу данных, содержащую представление, свойства которого необходимо просмотреть, а затем разверните папку **Представления** .</span><span class="sxs-lookup"><span data-stu-id="7212a-206">In **Object Explorer**, expand the database that contains the view to which you want to view the properties, and then expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="7212a-207">Щелкните правой кнопкой мыши представление, свойства которого необходимо просмотреть, и выберите пункт **Просмотреть зависимости**.</span><span class="sxs-lookup"><span data-stu-id="7212a-207">Right-click the view of which you want to view the properties and select **View Dependencies**.</span></span>  
  
3.  <span data-ttu-id="7212a-208">Выберите **Объекты, зависящие от [имя_представления]** для отображения объектов, которые ссылаются на представление.</span><span class="sxs-lookup"><span data-stu-id="7212a-208">Select **Objects that depend on [view name]** to display the objects that refer to the view.</span></span>  
  
4.  <span data-ttu-id="7212a-209">Для отображения объектов, на которые ссылается представление, выберите **Объекты, от которых зависит [имя_представления]** .</span><span class="sxs-lookup"><span data-stu-id="7212a-209">Select **Objects on which [view name] depends** to display the objects that are referenced by the view.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7212a-210">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7212a-210">Using Transact-SQL</span></span>  
  
#### <a name="to-get-the-definition-and-properties-of-a-view"></a><span data-ttu-id="7212a-211">Получение определения и свойств представления</span><span class="sxs-lookup"><span data-stu-id="7212a-211">To get the definition and properties of a view</span></span>  
  
1.  <span data-ttu-id="7212a-212">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7212a-212">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7212a-213">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7212a-213">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7212a-214">Скопируйте и вставьте один из следующих примеров в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="7212a-214">Copy and paste one of the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT definition, uses_ansi_nulls, uses_quoted_identifier, is_schema_bound  
    FROM sys.sql_modules  
    WHERE object_id = OBJECT_ID('HumanResources.vEmployee');   
    GO  
    ```  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT OBJECT_DEFINITION (OBJECT_ID('HumanResources.vEmployee')) AS ObjectDefinition;   
    GO  
    ```  
  
    ```  
    EXEC sp_helptext 'HumanResources.vEmployee';  
    ```  
  
 <span data-ttu-id="7212a-215">Дополнительные сведения см. в разделах [sys.sql_modules (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql), [OBJECT_DEFINITION (Transact-SQL)](/sql/t-sql/functions/object-definition-transact-sql) и [sp_helptext (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7212a-215">For more information, see [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql), [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) and [sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql).</span></span>  
  
#### <a name="to-get-the-dependencies-of-a-view"></a><span data-ttu-id="7212a-216">Получение зависимостей представления</span><span class="sxs-lookup"><span data-stu-id="7212a-216">To get the dependencies of a view</span></span>  
  
1.  <span data-ttu-id="7212a-217">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7212a-217">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7212a-218">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7212a-218">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7212a-219">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="7212a-219">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_NAME(referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(referencing_id, referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        referencing_class_desc, referenced_class_desc,  
        referenced_server_name, referenced_database_name, referenced_schema_name,  
        referenced_entity_name,   
        COALESCE(COL_NAME(referenced_id, referenced_minor_id), '(n/a)') AS referenced_column_name,  
        is_caller_dependent, is_ambiguous  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    WHERE referencing_id = OBJECT_ID(N'Production.vProductAndDescription');  
    GO  
    ```  
  
 <span data-ttu-id="7212a-220">Дополнительные сведения см. в разделах [sys.sql_expression_dependencies (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) и [sys.objects (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7212a-220">For more information, see [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) and [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span></span>  
  
  
