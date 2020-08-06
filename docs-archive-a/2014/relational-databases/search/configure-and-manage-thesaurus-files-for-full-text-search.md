---
title: Настройка файлов тезауруса для полнотекстового поиска и управление ими | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes [SQL Server], thesaurus files
- thesaurus [full-text search], configuring
- thesaurus [full-text search]
ms.assetid: 3ef96a63-8a52-45be-9a1f-265bff400e54
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67f0a5af7be4f41ce33692e5f28ad5adf676980c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752080"
---
# <a name="configure-and-manage-thesaurus-files-for-full-text-search"></a><span data-ttu-id="966ae-102">Настройка и управление файлами тезауруса для полнотекстового поиска</span><span class="sxs-lookup"><span data-stu-id="966ae-102">Configure and Manage Thesaurus Files for Full-Text Search</span></span>
  <span data-ttu-id="966ae-103">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]полнотекстовые запросы могут выполнять поиск синонимов для заданных пользователем терминов с помощью тезауруса.</span><span class="sxs-lookup"><span data-stu-id="966ae-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], full-text queries can search for synonyms of user-specified terms through the use of a thesaurus.</span></span> <span data-ttu-id="966ae-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \*\* определяет набор синонимов для указанного языка.</span><span class="sxs-lookup"><span data-stu-id="966ae-104">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] *thesaurus* defines a set of synonyms for a specific language.</span></span> <span data-ttu-id="966ae-105">Системные администраторы могут определить две формы синонимов: расширяющие наборы и заменяющие наборы.</span><span class="sxs-lookup"><span data-stu-id="966ae-105">System administrators can define two forms of synonyms: expansion sets and replacement sets.</span></span> <span data-ttu-id="966ae-106">Подготовив тезаурус, ориентированный на пользовательские полнотекстовые данные, можно эффективно расширить область полнотекстовых запросов к этим данным.</span><span class="sxs-lookup"><span data-stu-id="966ae-106">By developing a thesaurus tailored to your full-text data, you can effectively broaden the scope of full-text queries on that data.</span></span> <span data-ttu-id="966ae-107">Сопоставление с тезаурусом выполняется для всех запросов [FREETEXT](/sql/t-sql/queries/freetext-transact-sql) и [FREETEXTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) и для любых запросов [CONTAINS](/sql/t-sql/queries/contains-transact-sql) и [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) , которые указывают предложение FORMSOF THESAURUS.</span><span class="sxs-lookup"><span data-stu-id="966ae-107">Thesaurus matching occurs for all [FREETEXT](/sql/t-sql/queries/freetext-transact-sql) and [FREETEXTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) queries and for any [CONTAINS](/sql/t-sql/queries/contains-transact-sql) and [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) queries that specify the FORMSOF THESAURUS clause.</span></span>  
  
##  <a name="basic-tasks-for-setting-up-a-thesaurus-file"></a><a name="tasks"></a><span data-ttu-id="966ae-108">Основные задачи по настройке файла тезауруса</span><span class="sxs-lookup"><span data-stu-id="966ae-108">Basic Tasks for Setting Up a Thesaurus File</span></span>  
 <span data-ttu-id="966ae-109">Прежде чем запросы полнотекстового поиска экземпляра сервера смогут найти синонимы на данном языке, необходимо определить сопоставления тезауруса (синонимы) для этого языка.</span><span class="sxs-lookup"><span data-stu-id="966ae-109">Before full-text search queries on your server instance can look for synonyms in a given language, you must define thesaurus mappings (synonyms) for that language.</span></span> <span data-ttu-id="966ae-110">В каждом тезаурусе необходимо вручную определить следующее.</span><span class="sxs-lookup"><span data-stu-id="966ae-110">Each thesaurus must be manually configured to define the following:</span></span>  
  
-   <span data-ttu-id="966ae-111">Настройка диакритических знаков</span><span class="sxs-lookup"><span data-stu-id="966ae-111">Diacritics setting</span></span>  
  
     <span data-ttu-id="966ae-112">Для данного тезауруса все шаблоны поиска являются конфиденциальными или не чувствительны к диакритическим знакам, таким как тильда ( **~** ), знак ударения (**??**) или умляут (**??).** (т. е. с *учетом диакритических* знаков или *без учета диакритических*знаков).</span><span class="sxs-lookup"><span data-stu-id="966ae-112">For a given thesaurus, all search patterns are either sensitive or insensitive to diacritical marks such as a tilde (**~**), acute accent mark (**??**), or umlaut (**??**) (that is, *accent sensitive* or *accent insensitive*).</span></span> <span data-ttu-id="966ae-113">Например, предположим, что вы указали шаблон «каф??».</span><span class="sxs-lookup"><span data-stu-id="966ae-113">For example, suppose you specify the pattern "caf??"</span></span> <span data-ttu-id="966ae-114">другими шаблонами.</span><span class="sxs-lookup"><span data-stu-id="966ae-114">to be replaced by other patterns in a full-text query.</span></span> <span data-ttu-id="966ae-115">Если тезаурус не учитывает диакритические знаки, полнотекстовый поиск заменит шаблоны "КАФ??"</span><span class="sxs-lookup"><span data-stu-id="966ae-115">If the thesaurus is accent-insensitive, full-text search replaces the patterns "caf??"</span></span> <span data-ttu-id="966ae-116">и "cafe".</span><span class="sxs-lookup"><span data-stu-id="966ae-116">and "cafe".</span></span> <span data-ttu-id="966ae-117">Если тезаурус учитывает диакритические знаки, полнотекстовый поиск заменяет только шаблон "КАФ??".</span><span class="sxs-lookup"><span data-stu-id="966ae-117">If the thesaurus is accent-sensitive, full-text search replaces only the pattern "caf??".</span></span> <span data-ttu-id="966ae-118">По умолчанию тезаурус не учитывает диакритические знаки.</span><span class="sxs-lookup"><span data-stu-id="966ae-118">By default, a thesaurus is accent-insensitive.</span></span>  
  
-   <span data-ttu-id="966ae-119">Расширяющий набор</span><span class="sxs-lookup"><span data-stu-id="966ae-119">Expansion set</span></span>  
  
     <span data-ttu-id="966ae-120">Расширяющий набор содержит группу синонимов, таких как «писатель», «автор» и «журналист», которые заменяют друг друга в полнотекстовом поиске.</span><span class="sxs-lookup"><span data-stu-id="966ae-120">An expansion set contains a group of synonyms such as "writer", "author", and "journalist" that are substituted for one another by a full-text query.</span></span> <span data-ttu-id="966ae-121">Запросы, содержащие слова, которые совпадают с одним из синонимов в расширяющем наборе, расширяются таким образом, чтобы включать в себя все другие синонимы в этом расширяющем наборе.</span><span class="sxs-lookup"><span data-stu-id="966ae-121">Queries that contain a match for any synonym in an expansion set are expanded to include every other synonym in the expansion set.</span></span>  
  
     <span data-ttu-id="966ae-122">Дополнительные сведения см. в подразделе «XML-структура расширяющего набора» далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="966ae-122">For more information, see "XML Structure of an Expansion Set," later in this topic.</span></span>  
  
-   <span data-ttu-id="966ae-123">Заменяющий набор</span><span class="sxs-lookup"><span data-stu-id="966ae-123">Replacement set</span></span>  
  
     <span data-ttu-id="966ae-124">Заменяющий набор содержит текстовый шаблон, заменяемый подстановочным набором.</span><span class="sxs-lookup"><span data-stu-id="966ae-124">A replacement set contains a text pattern to be replaced by a substitution set.</span></span> <span data-ttu-id="966ae-125">Пример см. в подразделе «XML-структура заменяющего набора» далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="966ae-125">For an example, see the section "XML Structure of a Replacement Set" later in this topic.</span></span>  
  
  
##  <a name="initial-content-of-the-thesaurus-files"></a><a name="initial_thesaurus_files"></a><span data-ttu-id="966ae-126">Первоначальное содержимое файлов тезауруса</span><span class="sxs-lookup"><span data-stu-id="966ae-126">Initial Content of the Thesaurus Files</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="966ae-127">предоставляет набор XML-файлов тезауруса, по одному для каждого поддерживаемого языка.</span><span class="sxs-lookup"><span data-stu-id="966ae-127">provides a set of XML thesaurus files, one for each supported language.</span></span> <span data-ttu-id="966ae-128">Эти файлы в основном пустые.</span><span class="sxs-lookup"><span data-stu-id="966ae-128">These files are essentially empty.</span></span> <span data-ttu-id="966ae-129">Они содержат только XML-структуру верхнего уровня, общую для всех тезаурусов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , и заключенный в комментарии образец тезауруса.</span><span class="sxs-lookup"><span data-stu-id="966ae-129">They contain only the top-level XML structure that is common to all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] thesauruses and a commented-out sample thesaurus.</span></span>  
  
 <span data-ttu-id="966ae-130">Все файлы тезауруса, поставляемые с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], содержат следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="966ae-130">The thesaurus files that are released with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] all contain the following XML code:</span></span>  
  
```  
<XML ID="Microsoft Search Thesaurus">  
  
<!--  Commented out  
  
    <thesaurus xmlns="x-schema:tsSchema.xml">  
<diacritics_sensitive>0</diacritics_sensitive>  
        <expansion>  
            <sub>Internet Explorer</sub>  
            <sub>IE</sub>  
            <sub>IE5</sub>  
        </expansion>  
        <replacement>  
            <pat>NT5</pat>  
            <pat>W2K</pat>  
            <sub>Windows 2012</sub>  
        </replacement>  
        <expansion>  
            <sub>run</sub>  
            <sub>jog</sub>  
        </expansion>  
    </thesaurus>  
-->  
</XML>  
```  
  
  
##  <a name="location-of-the-thesaurus-files"></a><a name="location"></a><span data-ttu-id="966ae-131">Расположение файлов тезауруса</span><span class="sxs-lookup"><span data-stu-id="966ae-131">Location of the Thesaurus Files</span></span>  
 <span data-ttu-id="966ae-132">Местоположение файлов тезауруса по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="966ae-132">The default location of the thesaurus files is:</span></span>  
  
 <span data-ttu-id="966ae-133">*<SQL_Server_data_files_path>* \MSSQL12. мссклсервер\мсскл\фтдата</span><span class="sxs-lookup"><span data-stu-id="966ae-133">*<SQL_Server_data_files_path>* \MSSQL12.MSSQLSERVER\MSSQL\FTDATA</span></span>\  
  
 <span data-ttu-id="966ae-134">В местоположении по умолчанию содержатся следующие файлы.</span><span class="sxs-lookup"><span data-stu-id="966ae-134">This default location contains the following files:</span></span>  
  
-   <span data-ttu-id="966ae-135">Зависящие от языка файлы тезауруса</span><span class="sxs-lookup"><span data-stu-id="966ae-135">Language-specific thesaurus files</span></span>  
  
     <span data-ttu-id="966ae-136">При установке в указанном выше месте устанавливаются пустые файлы тезауруса.</span><span class="sxs-lookup"><span data-stu-id="966ae-136">During setup, empty thesaurus files are installed in the above location.</span></span> <span data-ttu-id="966ae-137">Для каждого поддерживаемого языка предоставляется отдельный файл.</span><span class="sxs-lookup"><span data-stu-id="966ae-137">A separate file is provided for each supported language.</span></span> <span data-ttu-id="966ae-138">Системный администратор может настроить эти файлы.</span><span class="sxs-lookup"><span data-stu-id="966ae-138">A system administrator can customize these files.</span></span>  
  
     <span data-ttu-id="966ae-139">Имена файлов по умолчанию для файлов тезауруса имеют следующий формат:</span><span class="sxs-lookup"><span data-stu-id="966ae-139">The default file names of the thesaurus files use following format:</span></span>  
  
     <span data-ttu-id="966ae-140">"TS" + \<three-letter language-abbreviation> + ". XML"</span><span class="sxs-lookup"><span data-stu-id="966ae-140">'ts' + \<three-letter language-abbreviation> + '.xml'</span></span>  
  
     <span data-ttu-id="966ae-141">Имя файла тезауруса для данного языка указывается в следующем параметре реестра: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<имя-экземпляра>\MSSearch\\<аббревиатура-языка>.</span><span class="sxs-lookup"><span data-stu-id="966ae-141">The name of the thesaurus file for a given language is specified in the registry in the following value HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<instance-name>\MSSearch\\<language-abbrev>.</span></span>  
  
-   <span data-ttu-id="966ae-142">Файл глобального тезауруса</span><span class="sxs-lookup"><span data-stu-id="966ae-142">The global thesaurus file</span></span>  
  
     <span data-ttu-id="966ae-143">Пустой файл глобального тезауруса, tsGlobal.xml.</span><span class="sxs-lookup"><span data-stu-id="966ae-143">An empty global thesaurus file, tsGlobal.xml.</span></span>  
  
 <span data-ttu-id="966ae-144">Можно менять местонахождение и имена файлов тезауруса, изменяя соответствующий раздел реестра.</span><span class="sxs-lookup"><span data-stu-id="966ae-144">You can change the location and names of a thesaurus file by changing its registry key.</span></span> <span data-ttu-id="966ae-145">Для каждого языка местонахождение файла тезауруса указывается в следующем параметре реестра:</span><span class="sxs-lookup"><span data-stu-id="966ae-145">For each language, the location of the thesaurus file is specified in the following value in the registry:</span></span>  
  
 <span data-ttu-id="966ae-146">HKLM/SOFTWARE/Microsoft/Microsoft SQL Server/ \<instance name> /Мссеарч/лангуаже/ \<language-abbreviation> /тсаурусфиле</span><span class="sxs-lookup"><span data-stu-id="966ae-146">HKLM/SOFTWARE/Microsoft/Microsoft SQL Server/\<instance name>/MSSearch/Language/\<language-abbreviation>/TsaurusFile</span></span>  
  
 <span data-ttu-id="966ae-147">Файл глобального тезауруса соответствует языку «Нейтральный» с кодом языка (LCID) 0.</span><span class="sxs-lookup"><span data-stu-id="966ae-147">The global thesaurus file corresponds to the Neutral language with LCID 0.</span></span> <span data-ttu-id="966ae-148">Это значение может быть изменено только администратором.</span><span class="sxs-lookup"><span data-stu-id="966ae-148">This value can be changed by administrators only.</span></span>  
  
  
##  <a name="how-queries-use-thesaurus-files"></a><a name="how_queries_use_tf"></a><span data-ttu-id="966ae-149">Использование файлов тезауруса в запросах</span><span class="sxs-lookup"><span data-stu-id="966ae-149">How Queries Use Thesaurus Files</span></span>  
 <span data-ttu-id="966ae-150">В каждом запросе тезауруса используется как языковой тезаурус, так и глобальный.</span><span class="sxs-lookup"><span data-stu-id="966ae-150">A thesaurus query uses both a language-specific thesaurus and the global thesaurus.</span></span> <span data-ttu-id="966ae-151">Вначале запрос ищет файл, относящийся к конкретному языку, и загружает его для обработки (если он не загружен).</span><span class="sxs-lookup"><span data-stu-id="966ae-151">First, the query looks up the language-specific file and loads it for processing (unless it is already loaded).</span></span> <span data-ttu-id="966ae-152">Запрос расширяется с целью включить в файл тезауруса синонимы конкретного языка, заданные правилами расширяющего и заменяющего наборов.</span><span class="sxs-lookup"><span data-stu-id="966ae-152">The query is expanded to include the language-specific synonyms specified by the expansion set and replacement set rules in the thesaurus file.</span></span> <span data-ttu-id="966ae-153">Затем эти шаги повторяются для глобального тезауруса.</span><span class="sxs-lookup"><span data-stu-id="966ae-153">These steps are then repeated for the global thesaurus.</span></span> <span data-ttu-id="966ae-154">Но если термин уже входит в состав соответствий в файле конкретного языка, он используется в глобальном тезаурусе.</span><span class="sxs-lookup"><span data-stu-id="966ae-154">However, if a term is already part of a match in the language specific thesaurus file, the term is ineligible for matching in the global thesaurus.</span></span>  
  
  
##  <a name="understanding-the-structure-of-a-thesaurus-file"></a><a name="structure"></a><span data-ttu-id="966ae-155">Основные сведения о структуре файла тезауруса</span><span class="sxs-lookup"><span data-stu-id="966ae-155">Understanding the Structure of a Thesaurus File</span></span>  
 <span data-ttu-id="966ae-156">Каждый файл тезауруса определяет XML-контейнер, идентификатор которого — `Microsoft Search Thesaurus`, и комментарий, `<!--` ... `-->`, который содержит образец тезауруса.</span><span class="sxs-lookup"><span data-stu-id="966ae-156">Each thesaurus file defines an XML container whose ID is `Microsoft Search Thesaurus`, and a comment, `<!--` ... `-->`, that contains a sample thesaurus.</span></span> <span data-ttu-id="966ae-157">Тезаурус определяется в \<thesaurus> элементе, содержащем образцы дочерних элементов, которые определяют параметры диакритических знаков, расширяющие наборы и заменяющие наборы следующим образом.</span><span class="sxs-lookup"><span data-stu-id="966ae-157">The thesaurus is defined in a \<thesaurus> element that contains samples of the child elements that define the diacritics setting, expansion sets, and replacement sets, as follows:</span></span>  
  
-   <span data-ttu-id="966ae-158">XML-структура настройки диакритических знаков</span><span class="sxs-lookup"><span data-stu-id="966ae-158">XML Structure of the Diacritical Setting</span></span>  
  
     <span data-ttu-id="966ae-159">Настройка диакритических знаков определяется в отдельном элементе <diacritics_sensitive>.</span><span class="sxs-lookup"><span data-stu-id="966ae-159">The diacritics setting of a thesaurus is specified in a single <diacritics_sensitive> element.</span></span> <span data-ttu-id="966ae-160">Этот элемент содержит целое значение, которое управляет поведением диакритических знаков, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="966ae-160">This element contains an integer value that controls accent sensitivity, as follows:</span></span>  
  
    |<span data-ttu-id="966ae-161">Настройка диакритических знаков</span><span class="sxs-lookup"><span data-stu-id="966ae-161">Diacritics Setting</span></span>|<span data-ttu-id="966ae-162">Значение</span><span class="sxs-lookup"><span data-stu-id="966ae-162">Value</span></span>|<span data-ttu-id="966ae-163">XML</span><span class="sxs-lookup"><span data-stu-id="966ae-163">XML</span></span>|  
    |------------------------|-----------|---------|  
    |<span data-ttu-id="966ae-164">без учета диакритических знаков</span><span class="sxs-lookup"><span data-stu-id="966ae-164">Accent insensitive</span></span>|<span data-ttu-id="966ae-165">0</span><span class="sxs-lookup"><span data-stu-id="966ae-165">0</span></span>|`<diacritics_sensitive>0</diacritics_sensitive>`|  
    |<span data-ttu-id="966ae-166">с учетом диакритических знаков</span><span class="sxs-lookup"><span data-stu-id="966ae-166">Accent sensitive</span></span>|<span data-ttu-id="966ae-167">1</span><span class="sxs-lookup"><span data-stu-id="966ae-167">1</span></span>|`<diacritics_sensitive>1</diacritics_sensitive>`|  
  
    > [!NOTE]  
    >  <span data-ttu-id="966ae-168">Эту настройку можно применить для файла только единожды, и она применяется для всех шаблонов поиска в файле.</span><span class="sxs-lookup"><span data-stu-id="966ae-168">This setting can only be applied one time in the file, and it applies to all search patterns in the file.</span></span> <span data-ttu-id="966ae-169">Этот параметр невозможно указать для отдельных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="966ae-169">This setting cannot be specified for individual patterns.</span></span>  
  
-   <span data-ttu-id="966ae-170">XML-структура расширяющего набора</span><span class="sxs-lookup"><span data-stu-id="966ae-170">XML Structure of an Expansion Set</span></span>  
  
     <span data-ttu-id="966ae-171">Каждый расширяющий набор заключен в элемент \<expansion>.</span><span class="sxs-lookup"><span data-stu-id="966ae-171">Each expansion set is enclosed within an \<expansion> element.</span></span> <span data-ttu-id="966ae-172">Внутри этого элемента можно указать одну или несколько подстановок в элементе \<sub>.</span><span class="sxs-lookup"><span data-stu-id="966ae-172">Within this element, you specify one or more substitutions in a \<sub> element.</span></span> <span data-ttu-id="966ae-173">В расширяющем наборе можно указать группу подстановок, являющихся синонимами.</span><span class="sxs-lookup"><span data-stu-id="966ae-173">In the expansion set, you can specify a group of substitutions that are synonyms of each other.</span></span>  
  
     <span data-ttu-id="966ae-174">Например, можно изменить раздел расширения так, чтобы подстановки «писатель», «автор» и «журналист» считались синонимами.</span><span class="sxs-lookup"><span data-stu-id="966ae-174">For example, you can edit the expansion section to treat the substitutions "writer", "author", and "journalist" as synonyms.</span></span> <span data-ttu-id="966ae-175">Полнотекстовые запросы, содержащие слова, совпадающие с одним из подстановочных слов, расширяются таким образом, чтобы включать в себя другие подстановочные слова в этом расширяющем наборе.</span><span class="sxs-lookup"><span data-stu-id="966ae-175">full-text search queries that contain matches in one substitution are expanded to include all other substitutions specified in the expansion set.</span></span> <span data-ttu-id="966ae-176">Следовательно, в предыдущем примере при выполнении запроса FORMS OF THESAURUS или FREETEXT со словом «автор» после полнотекстового поиска будут также возвращены результаты, содержащие слова «писатель» и «журналист».</span><span class="sxs-lookup"><span data-stu-id="966ae-176">Therefore, in the preceding example, when you issue a FORMS OF THESAURUS or a FREETEXT query for the word "author", full-text search also returns search results containing the words "writer" and "journalist".</span></span>  
  
     <span data-ttu-id="966ae-177">Для этого примера раздел расширяющего набора должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="966ae-177">This is what the expansion set section would look like for the above example:</span></span>  
  
    ```  
    <expansion>  
            <sub>writer</sub>  
            <sub>author</sub>  
            <sub>journalist</sub>  
    </expansion>  
    ```  
  
-   <span data-ttu-id="966ae-178">XML-структура заменяющего набора</span><span class="sxs-lookup"><span data-stu-id="966ae-178">XML Structure of a Replacement Set</span></span>  
  
     <span data-ttu-id="966ae-179">Каждый заменяющий набор заключен в элемент \<replacement>.</span><span class="sxs-lookup"><span data-stu-id="966ae-179">Each replacement set is enclosed within a \<replacement> element.</span></span> <span data-ttu-id="966ae-180">Внутри этого элемента можно указать один или несколько шаблонов в элементе \<pat> и ноль или более подстановок в элементах \<sub>, по одному для синонима.</span><span class="sxs-lookup"><span data-stu-id="966ae-180">Within this element you can specify one or more patterns in a \<pat> element and zero or more substitutions in \<sub> elements, one per synonym.</span></span> <span data-ttu-id="966ae-181">Можно указать шаблон, заменяемый подстановочным набором.</span><span class="sxs-lookup"><span data-stu-id="966ae-181">You can specify a pattern to be replaced by a substitution set.</span></span> <span data-ttu-id="966ae-182">Шаблоны и подстановки могут содержать одно слово или последовательность слов.</span><span class="sxs-lookup"><span data-stu-id="966ae-182">Patterns and substitutions can contain a word, or a sequence of words.</span></span> <span data-ttu-id="966ae-183">Если для шаблона не указано подстановки, то шаблон удаляется из запроса пользователя.</span><span class="sxs-lookup"><span data-stu-id="966ae-183">If there is no substitution specified for a pattern, it has the effect of removing the pattern from the user query.</span></span>  
  
     <span data-ttu-id="966ae-184">Например, допустим, что необходимо заменить слово-шаблон «Win8» словами «Windows Server 2012» или «Windows 8.0».</span><span class="sxs-lookup"><span data-stu-id="966ae-184">For example, suppose you want queries for "Win8", the pattern, to be replaced by "Windows Server 2012" or "Windows 8.0", the substitutions.</span></span> <span data-ttu-id="966ae-185">При выполнении полнотекстового запроса со словом «Win8» полнотекстовый поиск возвращает только результаты, содержащие слова «Windows Server 2012» или «Windows 8.0».</span><span class="sxs-lookup"><span data-stu-id="966ae-185">If you run a full-text query for "Win8", full-text search only returns search results containing "Windows Server 2012" or "Windows 8.0".</span></span> <span data-ttu-id="966ae-186">Результаты, содержащие слово «Win8», не возвращаются.</span><span class="sxs-lookup"><span data-stu-id="966ae-186">It does not return results containing "Win8".</span></span> <span data-ttu-id="966ae-187">Это происходит потому, что шаблон «Win8» был заменен шаблонами «Windows Server 2012» и «Windows 8.0».</span><span class="sxs-lookup"><span data-stu-id="966ae-187">This is because the pattern "Win8" has been "replaced" by the patterns "Windows Server 2012" and "Windows 8.0".</span></span>  
  
     <span data-ttu-id="966ae-188">Для этого примера раздел заменяющего набора должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="966ae-188">This is what the replacement set section would look like for the above example:</span></span>  
  
    ```  
    <replacement>  
            <pat>Win8</pat>  
            <sub>Windows Server 2012</sub>  
            <sub>Windows 8.0</sub>  
    </replacement>  
    ```  
  
     <span data-ttu-id="966ae-189">Если имеются два заменяющих набора с одинаковыми сравниваемыми шаблонами, приоритет имеет самый длинный из них.</span><span class="sxs-lookup"><span data-stu-id="966ae-189">If you have two replacement sets with similar patterns being matched, the longer of the two takes precedence.</span></span> <span data-ttu-id="966ae-190">Например, если определены следующие заменяющие наборы, при выполнении запроса FORMS OF THESAURUS по фразе «сообщество Internet Explorer в сети», набор «Internet Explorer» имеет приоритет перед набором «Internet».</span><span class="sxs-lookup"><span data-stu-id="966ae-190">For example, if you run a FORMS OF THESAURUS query for "Internet Explorer online community" and you have the following replacement sets, the "Internet Explorer" replacement set takes precedence over the "Internet" replacement set.</span></span> <span data-ttu-id="966ae-191">Следовательно, запрос будет обрабатываться так, как будто он сформирован по фразам «сообщество IE в сети» или «сообщество IE 9 в сети».</span><span class="sxs-lookup"><span data-stu-id="966ae-191">The query will therefore be processed as "IE online community" or "IE 9 online community".</span></span>  
  
    ```  
    <replacement>  
             <pat>Internet</pat>  
             <sub>intranet</sub>  
    </replacement>  
    ```  
  
     <span data-ttu-id="966ae-192">и</span><span class="sxs-lookup"><span data-stu-id="966ae-192">and</span></span>  
  
    ```  
    <replacement>  
             <pat>Internet Explorer</pat>  
             <sub>IE</sub>  
             <sub>IE 9</sub>  
    </replacement>  
    ```  
  
  
##  <a name="working-with-thesaurus-files"></a><a name="working_with_thesaurus_files"></a><span data-ttu-id="966ae-193">Работа с файлами тезауруса</span><span class="sxs-lookup"><span data-stu-id="966ae-193">Working with Thesaurus Files</span></span>  
 <span data-ttu-id="966ae-194">**Изменение файла тезауруса**</span><span class="sxs-lookup"><span data-stu-id="966ae-194">**To edit a thesaurus file**</span></span>  
  
-   [<span data-ttu-id="966ae-195">Изменение файла тезауруса</span><span class="sxs-lookup"><span data-stu-id="966ae-195">Editing a Thesaurus File</span></span>](#editing)  
  
 <span data-ttu-id="966ae-196">**Загрузка обновленного файла тезауруса**</span><span class="sxs-lookup"><span data-stu-id="966ae-196">**To load an updated thesaurus file**</span></span>  
  
-   [<span data-ttu-id="966ae-197">sp_fulltext_load_thesaurus_file (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="966ae-197">sp_fulltext_load_thesaurus_file &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql)  
  
 <span data-ttu-id="966ae-198">**Просмотр разметки, полученной в результате применения средства разбиения по словам, тезауруса и списка стоп-слов**</span><span class="sxs-lookup"><span data-stu-id="966ae-198">**To view the tokenization result of a word breaker, thesaurus, and stoplist combination**</span></span>  
  
-   [<span data-ttu-id="966ae-199">sys. dm_fts_parser &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="966ae-199">sys.dm_fts_parser &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-parser-transact-sql)  
  
  
##  <a name="editing-a-thesaurus-file"></a><a name="editing"></a><span data-ttu-id="966ae-200">Изменение файла тезауруса</span><span class="sxs-lookup"><span data-stu-id="966ae-200">Editing a Thesaurus File</span></span>  
 <span data-ttu-id="966ae-201">Тезаурус для данного языка может быть настроен путем изменения соответствующего файла тезауруса (XML-файла).</span><span class="sxs-lookup"><span data-stu-id="966ae-201">The thesaurus for a given language can be configured by editing its thesaurus file (an XML file).</span></span> <span data-ttu-id="966ae-202">Во время установки устанавливаются пустые файлы тезауруса, содержащие только \<xml> контейнер и образец элемента с комментарием \<thesaurus> .</span><span class="sxs-lookup"><span data-stu-id="966ae-202">During setup, empty thesaurus files that contain only the \<xml> container and a commented-out sample \<thesaurus> element are installed.</span></span> <span data-ttu-id="966ae-203">Чтобы запросы полнотекстового поиска, которые ищут синонимы, работали правильно, необходимо создать реальный \<thesaurus> элемент, определяющий набор синонимов.</span><span class="sxs-lookup"><span data-stu-id="966ae-203">In order for full-text search queries that look for synonyms to work properly, you must create an actual \<thesaurus> element that defines a set of synonyms.</span></span> <span data-ttu-id="966ae-204">Могут быть определены две формы синонимов — расширяющие наборы и заменяющие наборы.</span><span class="sxs-lookup"><span data-stu-id="966ae-204">You can define two forms of synonyms, expansion sets and replacement sets.</span></span>  
  
 <span data-ttu-id="966ae-205">**Ограничения для файлов тезауруса**</span><span class="sxs-lookup"><span data-stu-id="966ae-205">**Restrictions for thesaurus files**</span></span>  
  
 <span data-ttu-id="966ae-206">На изменения файла тезауруса налагаются следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="966ae-206">The following restrictions apply to editing a thesaurus file:</span></span>  
  
-   <span data-ttu-id="966ae-207">Только системные администраторы имеют право обновлять, изменять и удалять файлы тезауруса.</span><span class="sxs-lookup"><span data-stu-id="966ae-207">Only system administrators can update, modify, or delete thesaurus files.</span></span>  
  
-   <span data-ttu-id="966ae-208">При изменении файлов тезауруса с помощью текстовых редакторов эти файлы необходимо сохранять в Юникоде с указанием отметок порядка байтов.</span><span class="sxs-lookup"><span data-stu-id="966ae-208">When editing thesaurus files using text editor tools, the files must be saved in Unicode format, and Byte Order Marks must be specified.</span></span>  
  
-   <span data-ttu-id="966ae-209">Элементы тезауруса не могут быть пустыми или делиться на пустые строки.</span><span class="sxs-lookup"><span data-stu-id="966ae-209">Thesaurus entries cannot be empty or word break to an empty string.</span></span>  
  
-   <span data-ttu-id="966ae-210">Фразы в файле тезауруса не могут иметь длину более 512 символов.</span><span class="sxs-lookup"><span data-stu-id="966ae-210">Phrases in the thesaurus file must be no longer than 512 characters.</span></span>  
  
-   <span data-ttu-id="966ae-211">Тезаурус не должен содержать повторяющихся элементов среди элементов \<sub> расширяющих наборов и элементов \<pat> заменяющих наборов.</span><span class="sxs-lookup"><span data-stu-id="966ae-211">A thesaurus must not contain any duplicate entries among the \<sub> entries of expansion sets and the \<pat> elements of replacement sets.</span></span>  
  
 <span data-ttu-id="966ae-212">**Рекомендации для файлов тезауруса**</span><span class="sxs-lookup"><span data-stu-id="966ae-212">**Recommendations for thesaurus files**</span></span>  
  
 <span data-ttu-id="966ae-213">Рекомендуется, чтобы элементы в файле тезауруса не содержали специальных символов.</span><span class="sxs-lookup"><span data-stu-id="966ae-213">We recommend that entries in the thesaurus file contain no special characters.</span></span> <span data-ttu-id="966ae-214">Это объясняется особенностями поведения средств разбиения по словам в отношении специальных символов.</span><span class="sxs-lookup"><span data-stu-id="966ae-214">This is because word breakers have subtle behaviors with respect to special characters.</span></span> <span data-ttu-id="966ae-215">Если элемент тезауруса содержит какие-нибудь специальные символы, то средства разбиения по словам, использованные в сочетании с этим элементом, могут оказать малозаметное воздействие на поведение полнотекстового запроса.</span><span class="sxs-lookup"><span data-stu-id="966ae-215">If a thesaurus entry contains any special characters, word breakers used in combination with that entry can have subtle behavioral implications for a full-text query.</span></span>  
  
 <span data-ttu-id="966ae-216">Рекомендуется, чтобы элементы \<sub> не содержали стоп-слов, так как стоп-слова удаляются из полнотекстового индекса.</span><span class="sxs-lookup"><span data-stu-id="966ae-216">We recommend that \<sub> entries contain no stopwords since stopwords are omitted from the full-text index.</span></span> <span data-ttu-id="966ae-217">Запросы расширяются, чтобы охватить элементы \<sub> из файла тезауруса, и если элемент \<sub> содержит стоп-слова, то размер запроса излишне увеличивается.</span><span class="sxs-lookup"><span data-stu-id="966ae-217">Queries are expanded to include the \<sub> entries from a thesaurus file, and if a \<sub> entry contains stopwords, query size increases unnecessarily.</span></span>  
  
#### <a name="to-edit-a-thesaurus-file"></a><span data-ttu-id="966ae-218">Изменение файла тезауруса</span><span class="sxs-lookup"><span data-stu-id="966ae-218">To edit a thesaurus file</span></span>  
  
1.  <span data-ttu-id="966ae-219">Откройте файл тезауруса в Блокноте.</span><span class="sxs-lookup"><span data-stu-id="966ae-219">Open the thesaurus file in Notepad.</span></span>  
  
2.  <span data-ttu-id="966ae-220">При первом редактировании файла тезауруса удалите следующие строки комментариев, находящиеся, соответственно, в конце и в начале файла:</span><span class="sxs-lookup"><span data-stu-id="966ae-220">If you are editing the thesaurus file for the first time, remove the following comment lines at the beginning and end of the file, respectively:</span></span>  
  
    ```  
    <!--Commented out  
    -->  
    ```  
  
3.  <span data-ttu-id="966ae-221">Добавьте, измените или удалите заменяющий или расширяющий набор.</span><span class="sxs-lookup"><span data-stu-id="966ae-221">Add, modify, or delete a replacement set, or expansion set.</span></span>  
  
4.  <span data-ttu-id="966ae-222">Сохраните файл и закройте Блокнот.</span><span class="sxs-lookup"><span data-stu-id="966ae-222">Save the file and close Notepad.</span></span>  
  
5.  <span data-ttu-id="966ae-223">Используйте хранимую процедуру [sp_fulltext_load_thesaurus_file](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql) , чтобы загрузить содержимое файла тезауруса в базу данных tempdb, указав идентификатор языкового стандарта (LCID), соответствующий языку файла тезауруса.</span><span class="sxs-lookup"><span data-stu-id="966ae-223">Use [sp_fulltext_load_thesaurus_file](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql) to load the content of the thesaurus file into tempdb, specifying the local identifier (LCID) that corresponds to the language of the thesaurus file.</span></span> <span data-ttu-id="966ae-224">Например, файлу тезауруса английского языка, tsenu.xml, соответствует код языка 1033.</span><span class="sxs-lookup"><span data-stu-id="966ae-224">For example, for the English thesaurus file, tsenu.xml, the corresponding LCID is 1033.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    EXEC sys.sp_fulltext_load_thesaurus_file 1033;  
    GO  
    ```  
  
  
## <a name="see-also"></a><span data-ttu-id="966ae-225">См. также:</span><span class="sxs-lookup"><span data-stu-id="966ae-225">See Also</span></span>  
 <span data-ttu-id="966ae-226">[CONTAINS (Transact-SQL)](/sql/t-sql/queries/contains-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="966ae-226">[CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql) </span></span>  
 <span data-ttu-id="966ae-227">[CONTAINSTABLE (Transact-SQL)](/sql/relational-databases/system-functions/containstable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="966ae-227">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span></span>  
 <span data-ttu-id="966ae-228">[FREETEXT (Transact-SQL)](/sql/t-sql/queries/freetext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="966ae-228">[FREETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/freetext-transact-sql) </span></span>  
 <span data-ttu-id="966ae-229">[FREETEXTTABLE (Transact-SQL)](/sql/relational-databases/system-functions/freetexttable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="966ae-229">[FREETEXTTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/freetexttable-transact-sql) </span></span>  
 [<span data-ttu-id="966ae-230">Полнотекстовый поиск</span><span class="sxs-lookup"><span data-stu-id="966ae-230">Full-Text Search</span></span>](full-text-search.md)  
  
  
