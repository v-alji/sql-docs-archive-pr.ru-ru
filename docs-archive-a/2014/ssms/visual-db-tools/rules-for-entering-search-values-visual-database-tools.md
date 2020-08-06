---
title: Правила ввода значений для поиска (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- time [SQL Server], searches
- date searches
- dates [SQL Server], searches
- embedding apostrophes [SQL Server]
- logical value searches [SQL Server]
- case-sensitive search matches
- search criteria [SQL Server], rules
- text value searches [SQL Server]
- numeric value searches [SQL Server]
ms.assetid: 3c8134b7-83f4-41b4-99c8-e3949a685ff5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 907bcac93863bc5660993e910b37e25e25a129b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655512"
---
# <a name="rules-for-entering-search-values-visual-database-tools"></a><span data-ttu-id="6da94-102">Правила ввода значений для поиска (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="6da94-102">Rules for Entering Search Values (Visual Database Tools)</span></span>
  <span data-ttu-id="6da94-103">В этом подразделе содержатся соглашения, которых следует придерживаться при вводе следующих типов литеральных значений в условиях поиска:</span><span class="sxs-lookup"><span data-stu-id="6da94-103">This topic discusses the conventions you must use when entering the following types of literal values for a search condition:</span></span>  
  
-   <span data-ttu-id="6da94-104">текстовых значений;</span><span class="sxs-lookup"><span data-stu-id="6da94-104">Text values</span></span>  
  
-   <span data-ttu-id="6da94-105">числовых значений;</span><span class="sxs-lookup"><span data-stu-id="6da94-105">Numeric values</span></span>  
  
-   <span data-ttu-id="6da94-106">даты.</span><span class="sxs-lookup"><span data-stu-id="6da94-106">Dates</span></span>  
  
-   <span data-ttu-id="6da94-107">логических значений.</span><span class="sxs-lookup"><span data-stu-id="6da94-107">Logical values</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6da94-108">Сведения в этом подразделе базируются на правилах, определенных стандартом SQL-92.</span><span class="sxs-lookup"><span data-stu-id="6da94-108">The information in this topic is derived from the rules for standard SQL-92.</span></span> <span data-ttu-id="6da94-109">Но реализовывать SQL в каждой базе данных можно по-своему.</span><span class="sxs-lookup"><span data-stu-id="6da94-109">However, each database can implement SQL in its own way.</span></span> <span data-ttu-id="6da94-110">Поэтому правила, описанные здесь, могут быть применимы не во всех случаях.</span><span class="sxs-lookup"><span data-stu-id="6da94-110">Therefore, the guidelines provided here might not apply in every case.</span></span> <span data-ttu-id="6da94-111">При возникновении вопросов по вводу значений поиска для конкретной базы данных обращайтесь к документации по используемой базе данных.</span><span class="sxs-lookup"><span data-stu-id="6da94-111">If you have questions about how to enter search values for a particular database, refer to the documentation for the database that you are using.</span></span>  
  
## <a name="searching-on-text-values"></a><span data-ttu-id="6da94-112">Поиск по текстовым значениям</span><span class="sxs-lookup"><span data-stu-id="6da94-112">Searching on Text Values</span></span>  
 <span data-ttu-id="6da94-113">Следующие правила применяются при вводе в условие поиска текстовых значений:</span><span class="sxs-lookup"><span data-stu-id="6da94-113">The following guidelines apply when you enter text values in search conditions:</span></span>  
  
-   <span data-ttu-id="6da94-114">**Кавычки** . Заключайте текстовые значения в одинарные кавычки (например, при указании фамилии):</span><span class="sxs-lookup"><span data-stu-id="6da94-114">**Quotation marks** Enclose text values in single quotation marks, as in this example for a last name:</span></span>  
  
    ```  
    'Smith'  
    ```  
  
     <span data-ttu-id="6da94-115">При вводе условия поиска на [панели критериев](visual-database-tools.md)можно просто ввести текстовое значение, и конструктор запросов и представлений автоматически заключит его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="6da94-115">If you are entering a search condition in the [Criteria Pane](visual-database-tools.md), you can simply type the text value and the Query and View Designer will automatically put single quotation marks around it.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6da94-116">В некоторых базах данных элементы в одинарных кавычках интерпретируются как значения литералов, тогда как элементы, заключенные в двойные кавычки, — как объекты базы данных (например имена столбцов и таблиц).</span><span class="sxs-lookup"><span data-stu-id="6da94-116">In some databases, terms in single quotation marks are interpreted as literal values, whereas terms in double quotation marks are interpreted as database objects such as column or table references.</span></span> <span data-ttu-id="6da94-117">Таким образом, даже если конструктор запросов и представлений воспримет элементы, заключенные в двойные кавычки, они могут быть интерпретированы не так, как ожидается.</span><span class="sxs-lookup"><span data-stu-id="6da94-117">Therefore, even though the Query and View Designer can accept terms in double quotation marks, it might interpret them differently than you expect.</span></span>  
  
-   <span data-ttu-id="6da94-118">**Использование апострофов** . Если искомые данные содержат одинарную кавычку (апостроф), введите вместо него две одинарные кавычки, чтобы указать, что апостроф входит в значение литерала, а не завершает его.</span><span class="sxs-lookup"><span data-stu-id="6da94-118">**Embedding apostrophes** If the data you are searching for contains a single quotation mark (an apostrophe), you can enter two single quotation marks to indicate that you mean the single quotation mark as a literal value and not a delimiter.</span></span> <span data-ttu-id="6da94-119">Например, при поиске значения «Swann's Way» введите:</span><span class="sxs-lookup"><span data-stu-id="6da94-119">For example, the following condition searches for the value "Swann's Way:"</span></span>  
  
    ```  
    ='Swann''s Way'  
    ```  
  
-   <span data-ttu-id="6da94-120">**Максимальный размер** . Не превышайте при вводе длинных строк максимальную длину инструкции SQL для базы данных.</span><span class="sxs-lookup"><span data-stu-id="6da94-120">**Length limits** Do not exceed the maximum length of the SQL statement for your database when entering long strings.</span></span>  
  
-   <span data-ttu-id="6da94-121">**Учет регистра символов** . Соблюдайте регистр символов, если используемая база данных его учитывает.</span><span class="sxs-lookup"><span data-stu-id="6da94-121">**Case sensitivity** Follow the case sensitivity rules for the database you are using.</span></span> <span data-ttu-id="6da94-122">Чувствительность поиска текста к регистру символов определяется базой данных.</span><span class="sxs-lookup"><span data-stu-id="6da94-122">The database you are using determines whether text searches are case sensitive.</span></span> <span data-ttu-id="6da94-123">Например, некоторые базы данных трактуют оператор «=» как точное совпадение с учетом регистра символов, а другие допускают любые комбинации прописных и строчных букв.</span><span class="sxs-lookup"><span data-stu-id="6da94-123">For example, some databases interpret the operator "=" to mean an exact case-sensitive match, but others will allow matches on any combination of uppercase and lowercase characters.</span></span>  
  
     <span data-ttu-id="6da94-124">Если нет уверенности в том, что поиск в базе данных учитывает регистр символов, пользуйтесь для преобразования регистра в условии поиска функциями UPPER и LOWER, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6da94-124">If you are unsure about whether the database uses a case-sensitive search, you can use the UPPER or LOWER functions in the search condition to convert the case of the search data, as illustrated in the following example:</span></span>  
  
    ```  
    WHERE UPPER(lname) = 'SMITH'  
    ```  
  
## <a name="searching-on-numeric-values"></a><span data-ttu-id="6da94-125">Поиск по числовым значениям</span><span class="sxs-lookup"><span data-stu-id="6da94-125">Searching on Numeric Values</span></span>  
 <span data-ttu-id="6da94-126">При вводе в условие поиска числовых значений должны применяться следующие правила:</span><span class="sxs-lookup"><span data-stu-id="6da94-126">The following guidelines apply when you enter numeric values in search conditions:</span></span>  
  
-   <span data-ttu-id="6da94-127">**Кавычки** . Не заключайте числа в кавычки.</span><span class="sxs-lookup"><span data-stu-id="6da94-127">**Quotation marks** Do not enclose numbers in quotation marks.</span></span>  
  
-   <span data-ttu-id="6da94-128">**Нецифровые символы** . Не вводите нецифровые символы, за исключением десятичного разделителя (который определен в диалоговом окне **Язык и региональные стандарты** панели управления Windows) и знака минус (-).</span><span class="sxs-lookup"><span data-stu-id="6da94-128">**Non-numeric characters** Do not include non-numeric characters except the decimal separator (as defined in the **Regional Settings** dialog box of Windows Control Panel) and negative sign (-).</span></span> <span data-ttu-id="6da94-129">Не вводите разделители десятичных групп (пробел между тысячами) и символы обозначения валют.</span><span class="sxs-lookup"><span data-stu-id="6da94-129">Do not include digit grouping symbols (such as a comma between thousands) or currency symbols.</span></span>  
  
-   <span data-ttu-id="6da94-130">**Десятичный признак** . При вводе целых чисел можно указать признак десятичного числа, указывающий на то, производится ли поиск целого или действительного числа.</span><span class="sxs-lookup"><span data-stu-id="6da94-130">**Decimal marks** If you are entering whole numbers, you can include a decimal mark, whether the value you are searching for is an integer or a real number.</span></span>  
  
-   <span data-ttu-id="6da94-131">**Экспоненциальное представление** . Очень большие или очень малые числовые значения могут быть введены в экспоненциальном представлении, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6da94-131">**Scientific notation** You can enter very large or very small numbers using scientific notation, as in this example:</span></span>  
  
    ```  
    > 1.23456e-9  
    ```  
  
## <a name="searching-on-dates"></a><span data-ttu-id="6da94-132">Поиск по датам</span><span class="sxs-lookup"><span data-stu-id="6da94-132">Searching on Dates</span></span>  
 <span data-ttu-id="6da94-133">Формат ввода даты зависит от базы данных и от того, на какой панели конструктора запросов и представлений вводятся данные.</span><span class="sxs-lookup"><span data-stu-id="6da94-133">The format you use to enter dates depends on the database you are using and in what pane of the Query and View Designer you are entering the date.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6da94-134">Если формат даты, допустимый для источника данных, неизвестен, введите дату в столбце фильтра панели критериев в каком-нибудь известном формате.</span><span class="sxs-lookup"><span data-stu-id="6da94-134">If you don't know which format your data source uses, type a date into the filter column of the Criteria pane in any format familiar to you.</span></span> <span data-ttu-id="6da94-135">Конструктор преобразовывает большинство таких значений в нужный формат.</span><span class="sxs-lookup"><span data-stu-id="6da94-135">The designer will convert most of such entries into the appropriate format.</span></span>  
  
 <span data-ttu-id="6da94-136">Конструктор запросов и представлений может работать со следующими форматами даты:</span><span class="sxs-lookup"><span data-stu-id="6da94-136">The Query and View Designer can work with the following date formats:</span></span>  
  
-   <span data-ttu-id="6da94-137">**Определяется локалем** . Формат даты, указанный в диалоговом окне **Свойства языка и стандартов Windows** .</span><span class="sxs-lookup"><span data-stu-id="6da94-137">**Locale-specific** The format specified for dates in the **Windows Regional Settings Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="6da94-138">**Определяется базой данных** . Любой формат, воспринимаемый базой данных.</span><span class="sxs-lookup"><span data-stu-id="6da94-138">**Database-specific** Any format understood by the database.</span></span>  
  
-   <span data-ttu-id="6da94-139">**По стандарту ANSI** . Формат, в котором используются фигурные скобки, маркер "d" для обозначения даты и дата в символьном виде, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6da94-139">**ANSI standard date** A format that uses braces, the marker 'd' to designate the date, and a date string, as in the following example:</span></span>  
  
    ```  
    { d '1990-12-31' }  
    ```  
  
-   <span data-ttu-id="6da94-140">**Дата и время по стандарту ANSI** . Аналогично дате по стандарту ANSI, но с указанием маркера "ts" вместо "d" и с добавлением к дате часов, минут и секунд (в 24-часовом формате), как в следующем примере (для 31 декабря 1990 года):</span><span class="sxs-lookup"><span data-stu-id="6da94-140">**ANSI standard datetime** Similar to ANSI-standard date, but uses 'ts' instead of 'd' and adds hours, minutes, and seconds to the date (using a 24-hour clock), as in this example for December 31, 1990:</span></span>  
  
    ```  
    { ts '1990-12-31 00:00:00' }  
    ```  
  
     <span data-ttu-id="6da94-141">В общем случае форматы даты по стандарту ANSI применяются в базах данных, в которых для представления даты используется подлинный формат даты,</span><span class="sxs-lookup"><span data-stu-id="6da94-141">In general, the ANSI standard date format is used with databases that represent dates using a true date data type.</span></span> <span data-ttu-id="6da94-142">а формат datetime — в базах данных, поддерживающих тип данных datetime.</span><span class="sxs-lookup"><span data-stu-id="6da94-142">In contrast, the datetime format is used with databases that support a datetime data type.</span></span>  
  
 <span data-ttu-id="6da94-143">В следующей таблице приведены все форматы даты, которые могут быть указаны на различных панелях конструктора запросов и представлений.</span><span class="sxs-lookup"><span data-stu-id="6da94-143">The following table summarizes the date format that you can use in different panes of the Query and View Designer.</span></span>  
  
|<span data-ttu-id="6da94-144">**Панель**</span><span class="sxs-lookup"><span data-stu-id="6da94-144">**Pane**</span></span>|<span data-ttu-id="6da94-145">**Формат даты**</span><span class="sxs-lookup"><span data-stu-id="6da94-145">**Date format**</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="6da94-146">Критерии</span><span class="sxs-lookup"><span data-stu-id="6da94-146">Criteria</span></span>|<span data-ttu-id="6da94-147">Определяется локалем, базой данных, стандартом ANSI</span><span class="sxs-lookup"><span data-stu-id="6da94-147">Locale-specific Database-specific ANSI standard</span></span><br /><br /> <span data-ttu-id="6da94-148">Дата, введенная на [панели критериев](visual-database-tools.md) , на панели "SQL" преобразуется в формат, совместимый с базой данных.</span><span class="sxs-lookup"><span data-stu-id="6da94-148">Dates entered in the [Criteria Pane](visual-database-tools.md) are converted to a database-compatible format in the SQL pane.</span></span>|  
|<span data-ttu-id="6da94-149">SQL</span><span class="sxs-lookup"><span data-stu-id="6da94-149">SQL</span></span>|<span data-ttu-id="6da94-150">Определяется базой данных, стандартом ANSI</span><span class="sxs-lookup"><span data-stu-id="6da94-150">Database-specific ANSI standard</span></span>|  
|<span data-ttu-id="6da94-151">Результаты</span><span class="sxs-lookup"><span data-stu-id="6da94-151">Results</span></span>|<span data-ttu-id="6da94-152">Определяется локалем</span><span class="sxs-lookup"><span data-stu-id="6da94-152">Locale-specific</span></span>|  
  
## <a name="searching-on-logical-values"></a><span data-ttu-id="6da94-153">Поиск по логическим значениям</span><span class="sxs-lookup"><span data-stu-id="6da94-153">Searching on Logical Values</span></span>  
 <span data-ttu-id="6da94-154">Форматы логических значений различаются для разных баз данных.</span><span class="sxs-lookup"><span data-stu-id="6da94-154">The format of logical data varies from database to database.</span></span> <span data-ttu-id="6da94-155">Чаще всего значение False хранится в виде нуля (0).</span><span class="sxs-lookup"><span data-stu-id="6da94-155">Very frequently, a value of False is stored as zero (0).</span></span> <span data-ttu-id="6da94-156">Чаще всего значение True хранится в виде 1, а иногда в виде -1.</span><span class="sxs-lookup"><span data-stu-id="6da94-156">A value of True is most frequently stored as 1 and occasionally as -1.</span></span> <span data-ttu-id="6da94-157">При вводе в условие поиска логических значений должны применяться следующие правила.</span><span class="sxs-lookup"><span data-stu-id="6da94-157">The following guidelines apply when you enter logical values in search conditions:</span></span>  
  
-   <span data-ttu-id="6da94-158">Для поиска значения False указывайте нуль, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6da94-158">To search for a value of False, use a zero, as in the following example:</span></span>  
  
    ```  
    SELECT * FROM authors  
    WHERE contract = 0  
    ```  
  
-   <span data-ttu-id="6da94-159">Если неизвестно, какое значение указывать для поиска True, попробуйте указать 1, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6da94-159">If you are not sure what format to use when searching for a True value, try using 1, as in the following example:</span></span>  
  
    ```  
    SELECT * FROM authors  
    WHERE contract = 1  
    ```  
  
-   <span data-ttu-id="6da94-160">В качестве альтернативного решения можно ограничить область поиска указанием ненулевого значения, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6da94-160">Alternatively, you can broaden the scope of the search by searching for any non-zero value, as in the following example:</span></span>  
  
    ```  
    SELECT * FROM authors  
    WHERE contract <> 0  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6da94-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="6da94-161">See Also</span></span>  
 [<span data-ttu-id="6da94-162">Определение критериев поиска (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="6da94-162">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
