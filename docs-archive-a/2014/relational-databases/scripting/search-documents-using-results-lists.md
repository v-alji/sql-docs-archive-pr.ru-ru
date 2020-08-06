---
title: Поиск документов с помощью списков результатов
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- searches [SQL Server Management Studio], result lists
- result list searches [SQL Server Management Studio]
- searches [SQL Server Management Studio], multiple files
- Query Editor [SQL Server Management Studio], search multiple files
ms.assetid: 275e1b6c-fbd0-4408-af77-35903f90657c
author: rothja
ms.author: jroth
ms.openlocfilehash: 58ff3754bc1667de75426e52b3ddd855e7d1a348
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668223"
---
# <a name="search-documents-using-results-lists"></a><span data-ttu-id="e0be8-102">Поиск документов с помощью списков результатов</span><span class="sxs-lookup"><span data-stu-id="e0be8-102">Search Documents Using Results Lists</span></span>
  <span data-ttu-id="e0be8-103">С помощью диалогового окна **Найти и заменить** можно выполнять поиск и замену текста во всех файлах проекта или решения, или в папке файловой системы, даже если они не открыты в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0be8-103">Using the **Find and Replace** dialog box, you can search and replace text in all files in a project or solution or in a file system folder, even when they are not open in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="e0be8-104">Результаты поиска, выполненного в диалоговом окне **Найти и заменить** , появляются в окнах «Результаты поиска 1» и «Результаты поиска 2», что позволяет просмотреть точный текст строки, содержащей совпадение.</span><span class="sxs-lookup"><span data-stu-id="e0be8-104">Matches from searches that were performed with the **Find and Replace** dialog box appear in the Find Results 1 and Find Results 2 windows, which allows you to view the exact text from the line containing the match.</span></span>  
  
### <a name="to-search-in-multiple-files"></a><span data-ttu-id="e0be8-105">Выполнение поиска в группе файлов</span><span class="sxs-lookup"><span data-stu-id="e0be8-105">To search in multiple files</span></span>  
  
1.  <span data-ttu-id="e0be8-106">В меню **Правка** укажите **Найти и заменить** и далее **Найти в файлах**.</span><span class="sxs-lookup"><span data-stu-id="e0be8-106">On the **Edit** menu, point to **Find and Replace,** and then click **Find in Files**.</span></span>  
  
2.  <span data-ttu-id="e0be8-107">В текстовом поле **Найти** введите текст, который необходимо найти.</span><span class="sxs-lookup"><span data-stu-id="e0be8-107">In the **Find what** text box, enter the text to search for.</span></span>  
  
3.  <span data-ttu-id="e0be8-108">В списке **Искать в** выберите один из пунктов — **Все открытые документы**, **Текущий проект**, **Все решение**— или введите путь каталога.</span><span class="sxs-lookup"><span data-stu-id="e0be8-108">In the **Look in** list, click **All Open Documents**, **Current Project**, **Entire Solution**, or type a directory path.</span></span>  
  
4.  <span data-ttu-id="e0be8-109">В списке **Типы файлов** выберите один из указанных наборов расширений файлов или введите расширения, соответствующие типам файлов, в которых будет выполняться поиск, разделив их точками с запятой.</span><span class="sxs-lookup"><span data-stu-id="e0be8-109">In the **File types** list, select one of the listed sets of file extensions or enter the extensions for the types of files to be searched, separated by semicolons.</span></span> <span data-ttu-id="e0be8-110">Используйте \*.\* для поиска по всем файлам каталога, выбранного в раскрывающемся списке **Искать в** .</span><span class="sxs-lookup"><span data-stu-id="e0be8-110">Use \*.\* to search all files in the directory listed in the **Look in** drop-down list.</span></span>  
  
5.  <span data-ttu-id="e0be8-111">Установите остальные параметры поиска, чтобы повысить его точность.</span><span class="sxs-lookup"><span data-stu-id="e0be8-111">Select from the remaining search options to improve the accuracy of the search.</span></span>  
  
6.  <span data-ttu-id="e0be8-112">Чтобы начать поиск, нажмите кнопку **Найти** .</span><span class="sxs-lookup"><span data-stu-id="e0be8-112">Click **Find** to begin the search.</span></span>  
  
 <span data-ttu-id="e0be8-113">Совпадения при поиске отображаются по умолчанию в окне «Результаты поиска 1».</span><span class="sxs-lookup"><span data-stu-id="e0be8-113">The matches for the search appear in the Find Results 1 window by default.</span></span> <span data-ttu-id="e0be8-114">Совпадения можно просмотреть двойным щелчком на каждой записи в окне «Результаты поиска 1».</span><span class="sxs-lookup"><span data-stu-id="e0be8-114">You can browse the search matches by double-clicking each entry in the Find Results 1 window.</span></span> <span data-ttu-id="e0be8-115">Чтобы просмотреть результаты поиска в новом окне, выберите **Показывать в результатах 2**.</span><span class="sxs-lookup"><span data-stu-id="e0be8-115">To view the search results in a new window, select **Display in Find 2**.</span></span>  
  
#### <a name="to-replace-across-multiple-files-or-folders"></a><span data-ttu-id="e0be8-116">Выполнение замены в нескольких файлах или папках</span><span class="sxs-lookup"><span data-stu-id="e0be8-116">To replace across multiple files or folders</span></span>  
  
1.  <span data-ttu-id="e0be8-117">В меню **Правка** укажите **Найти и заменить** и выберите пункт **Заменить в файлах**.</span><span class="sxs-lookup"><span data-stu-id="e0be8-117">On the **Edit** menu, point to **Find and Replace,** and then click **Replace in Files**.</span></span>  
  
2.  <span data-ttu-id="e0be8-118">В текстовом поле **Найти** введите текст, который необходимо найти.</span><span class="sxs-lookup"><span data-stu-id="e0be8-118">In the **Find what** text box, enter the text to search for.</span></span>  
  
3.  <span data-ttu-id="e0be8-119">В поле **Заменить на** введите текст, на который следует заменить найденный текст.</span><span class="sxs-lookup"><span data-stu-id="e0be8-119">In the **Replace with** box, enter the text to replace the search text.</span></span>  
  
4.  <span data-ttu-id="e0be8-120">В списке **Искать в** выберите один из пунктов — **Все открытые документы**, **Текущий проект**, **Все решение**— или введите путь каталога.</span><span class="sxs-lookup"><span data-stu-id="e0be8-120">In the **Look in** list, click **All Open Documents**, **Current Project**, **Entire Solution**, or type a directory path.</span></span>  
  
5.  <span data-ttu-id="e0be8-121">Нажмите кнопку **Заменить** , чтобы заменить текущее совпадение на текст, указанный в поле **Заменить на** .</span><span class="sxs-lookup"><span data-stu-id="e0be8-121">Click **Replace** to replace the current search match with the text in the **Replace with** box.</span></span> <span data-ttu-id="e0be8-122">Отдельные совпадения можно пропустить, нажав кнопку **Найти следующее** . Чтобы пропустить целый файл, нажмите кнопку **Пропустить файл**.</span><span class="sxs-lookup"><span data-stu-id="e0be8-122">You can skip a single match by clicking **Find Next** or skip an entire file clicking **Skip File**.</span></span>  
  
     <span data-ttu-id="e0be8-123">\- или -</span><span class="sxs-lookup"><span data-stu-id="e0be8-123">\- or -</span></span>  
  
     <span data-ttu-id="e0be8-124">Нажмите кнопку **Заменить все** , чтобы заменить все совпадения на текст, указанный в поле **Заменить на** .</span><span class="sxs-lookup"><span data-stu-id="e0be8-124">Choose **Replace all** to replace all search matches with the text in the **Replace with** box.</span></span> <span data-ttu-id="e0be8-125">Чтобы позже можно было отменить некоторые из замен, выберите **Оставить измененные файлы открытыми после замены** .</span><span class="sxs-lookup"><span data-stu-id="e0be8-125">Select **Keep modified files open after Replace All** if you want to undo some of the replacements at another time.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0be8-126">Команда**Заменить все** заменяет все совпадения при поиске, включая совпадения в файлах, пропущенных с помощью кнопок **Пропустить файл** или **Найти далее**.</span><span class="sxs-lookup"><span data-stu-id="e0be8-126">**Replace all** replaces all search matches, including those in files you have skipped with **Skip File** or **Find Next**.</span></span> <span data-ttu-id="e0be8-127">С помощью кнопки **Отменить** можно отменить замены только для тех файлов, которые остались открытыми после операции замены.</span><span class="sxs-lookup"><span data-stu-id="e0be8-127">You can only use **Undo** for replacements made in files that remain open after the replacement operation.</span></span>  
  
 <span data-ttu-id="e0be8-128">Сведения о заменах появляются по умолчанию в окне «Результаты поиска 1».</span><span class="sxs-lookup"><span data-stu-id="e0be8-128">Replacement information appears in the Find Results 1 window by default.</span></span> <span data-ttu-id="e0be8-129">Замены можно просмотреть двойным щелчком на каждой записи в окне «Результаты поиска 1».</span><span class="sxs-lookup"><span data-stu-id="e0be8-129">You can browse replacements by double-clicking each entry in the Find Results 1 window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0be8-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="e0be8-130">See Also</span></span>  
 <span data-ttu-id="e0be8-131">[Поиск и замена](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="e0be8-131">[Search and Replace](search-and-replace.md) </span></span>  
 <span data-ttu-id="e0be8-132">[осуществлять поиск в документах в интерактивном режиме](search-documents-interactively.md) </span><span class="sxs-lookup"><span data-stu-id="e0be8-132">[Search Documents Interactively](search-documents-interactively.md) </span></span>  
 <span data-ttu-id="e0be8-133">[Поиск текста с символами-шаблонами](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="e0be8-133">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="e0be8-134">Поиск текста с помощью регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="e0be8-134">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
