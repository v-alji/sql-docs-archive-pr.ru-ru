---
title: осуществлять поиск в документах в интерактивном режиме
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- interactive searches [SQL Server Management Studio]
- searches [SQL Server Management Studio], interactive
- Query Editor [SQL Server Management Studio], interactive search
ms.assetid: dae65ac5-67af-45c6-a6e0-952fea26d680
author: rothja
ms.author: jroth
ms.openlocfilehash: 5603db77ea4f58d4bb036635a23ec3cfa400a818
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668228"
---
# <a name="search-documents-interactively"></a><span data-ttu-id="e8edc-102">осуществлять поиск в документах в интерактивном режиме</span><span class="sxs-lookup"><span data-stu-id="e8edc-102">Search Documents Interactively</span></span>
  <span data-ttu-id="e8edc-103">С помощью диалогового окна **Найти и заменить** можно производить поиск в одном или нескольких открытых файлах или окнах и последовательно перемещаться по найденным совпадениям.</span><span class="sxs-lookup"><span data-stu-id="e8edc-103">Using the **Find and Replace** dialog box, you can search one or more open files or windows and move through the search matches one by one.</span></span> <span data-ttu-id="e8edc-104">Этот метод позволяет просматривать каждое отдельное найденное совпадение в контексте окружающего текста.</span><span class="sxs-lookup"><span data-stu-id="e8edc-104">This technique allows you to review each individual search match in the context of the text around the match.</span></span> <span data-ttu-id="e8edc-105">Кроме того, с помощью диалогового окна **Найти и заменить** можно выполнять операции группового поиска и просматривать найденные совпадения в виде отчета.</span><span class="sxs-lookup"><span data-stu-id="e8edc-105">You also have the option of performing bulk find operations and reviewing search matches in report format using the **Find and Replace** dialog box.</span></span>  
  
### <a name="to-search-all-open-documents"></a><span data-ttu-id="e8edc-106">Поиск во всех открытых документах</span><span class="sxs-lookup"><span data-stu-id="e8edc-106">To search all open documents</span></span>  
  
1.  <span data-ttu-id="e8edc-107">Откройте элементы, в которых надо произвести поиск.</span><span class="sxs-lookup"><span data-stu-id="e8edc-107">Open the items you wish to search.</span></span>  
  
2.  <span data-ttu-id="e8edc-108">В меню **Правка** наведите указатель на пункт **Найти и заменить** , а затем выберите **Быстрый поиск**.</span><span class="sxs-lookup"><span data-stu-id="e8edc-108">On the **Edit** menu, point to **Find and Replace,** and then click **QuickFind**.</span></span>  
  
3.  <span data-ttu-id="e8edc-109">В текстовом поле **Найти и заменить** введите текст, который необходимо найти.</span><span class="sxs-lookup"><span data-stu-id="e8edc-109">In the **Find and Replace** text box, enter the text to search for.</span></span>  
  
4.  <span data-ttu-id="e8edc-110">В списке **Искать в** выберите **Все открытые документы**.</span><span class="sxs-lookup"><span data-stu-id="e8edc-110">In the **Look in** list, select **All Open Documents**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e8edc-111">При выборе параметра **Все открытые документы** некоторые открытые файлы, возможно, не будут включены в поиск.</span><span class="sxs-lookup"><span data-stu-id="e8edc-111">Certain open files might not be searched when **All Open Documents** is selected.</span></span> <span data-ttu-id="e8edc-112">В поиске участвуют только файлы, открытые в данный момент в текстовом режиме, например в представлении кода.</span><span class="sxs-lookup"><span data-stu-id="e8edc-112">Only files currently open in a textual view, such as Code view, are included in searches.</span></span> <span data-ttu-id="e8edc-113">Файлы в режиме конструктора не участвуют в поиске.</span><span class="sxs-lookup"><span data-stu-id="e8edc-113">Files in Designer view are not included in searches.</span></span>  
  
5.  <span data-ttu-id="e8edc-114">Выберите дополнительные параметры поиска для повышения его точности.</span><span class="sxs-lookup"><span data-stu-id="e8edc-114">Select additional search options to increase the accuracy of the search.</span></span>  
  
6.  <span data-ttu-id="e8edc-115">Нажмите кнопку **Найти далее** , чтобы начать поиск; продолжайте нажимать **Найти далее** , пока не будет завершен поиск в последнем файле.</span><span class="sxs-lookup"><span data-stu-id="e8edc-115">Click **Find Next** to start the search, and continue clicking **Find Next** until the last file has been searched.</span></span>  
  
 <span data-ttu-id="e8edc-116">Когда поиск проходит через начало или конец документа, в строке состояния появляется соответствующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="e8edc-116">When the search passes the beginning or end of the document, a message is displayed in the status bar.</span></span> <span data-ttu-id="e8edc-117">Когда поиск достигает своей начальной точки, также появится сообщение.</span><span class="sxs-lookup"><span data-stu-id="e8edc-117">A message box appears when the search reaches the starting point of the search.</span></span>  
  
#### <a name="to-replace-in-all-active-files-interactively"></a><span data-ttu-id="e8edc-118">Замена во всех активных файлах в интерактивном режиме</span><span class="sxs-lookup"><span data-stu-id="e8edc-118">To replace in all active files interactively</span></span>  
  
1.  <span data-ttu-id="e8edc-119">В меню **Правка** наведите указатель на пункт **Найти и заменить**, а затем выберите **Быстрая замена**.</span><span class="sxs-lookup"><span data-stu-id="e8edc-119">On the **Edit** menu, point to **Find and Replace**, and then click **QuickReplace**.</span></span>  
  
2.  <span data-ttu-id="e8edc-120">В текстовом поле **Найти** введите текст, который необходимо найти.</span><span class="sxs-lookup"><span data-stu-id="e8edc-120">In the **Find what** box, enter the text to search for.</span></span>  
  
3.  <span data-ttu-id="e8edc-121">В поле **Заменить на** введите текст, на который следует заменить найденный текст.</span><span class="sxs-lookup"><span data-stu-id="e8edc-121">In the **Replace with** box, enter the text to replace the search text.</span></span>  
  
4.  <span data-ttu-id="e8edc-122">В списке **Искать в** выберите **Все открытые документы**.</span><span class="sxs-lookup"><span data-stu-id="e8edc-122">In the **Look in** list, select **All Open Documents**.</span></span>  
  
5.  <span data-ttu-id="e8edc-123">Нажмите кнопку **Заменить**; продолжайте нажимать кнопку **Заменить** , пока не будет заменено последнее найденное совпадение в последнем файле.</span><span class="sxs-lookup"><span data-stu-id="e8edc-123">Click **Replace**, and continue clicking **Replace** until the last match in the last file has been replaced.</span></span> <span data-ttu-id="e8edc-124">Нажмите кнопку **Найти далее** , чтобы пропустить совпадение, заменять которое не нужно.</span><span class="sxs-lookup"><span data-stu-id="e8edc-124">Click **Find Next** to skip a match you do not want to replace.</span></span>  
  
     <span data-ttu-id="e8edc-125">-или-</span><span class="sxs-lookup"><span data-stu-id="e8edc-125">-or-</span></span>  
  
     <span data-ttu-id="e8edc-126">Нажмите **Заменить все** , чтобы заменить все найденные совпадения.</span><span class="sxs-lookup"><span data-stu-id="e8edc-126">Choose **Replace All** to replace all matches.</span></span> <span data-ttu-id="e8edc-127">Появится сообщение, в котором будет указано общее количество произведенных замен.</span><span class="sxs-lookup"><span data-stu-id="e8edc-127">A message box appears, listing the total number of replacements.</span></span>  
  
 <span data-ttu-id="e8edc-128">Команда **Заменить все** заменяет все найденные совпадения, включая и те, которые были пропущены нажатием кнопки **Найти далее** .</span><span class="sxs-lookup"><span data-stu-id="e8edc-128">The **Replace All** command replaces all search matches, including those you have skipped with the **Find Next** button.</span></span> <span data-ttu-id="e8edc-129">Чтобы отменить команду **Заменить все**, перед тем как закрыть какой-либо файл в меню **Правка** выберите пункт **Отменить** .</span><span class="sxs-lookup"><span data-stu-id="e8edc-129">To cancel **Replace All**, click **Undo** from the **Edit** menu before closing any of the files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8edc-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="e8edc-130">See Also</span></span>  
 <span data-ttu-id="e8edc-131">[Выполнение добавочного поиска в активном документе](search-an-active-document-incrementally.md) </span><span class="sxs-lookup"><span data-stu-id="e8edc-131">[Search an Active Document Incrementally](search-an-active-document-incrementally.md) </span></span>  
 <span data-ttu-id="e8edc-132">[Поиск и замена](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="e8edc-132">[Search and Replace](search-and-replace.md) </span></span>  
 <span data-ttu-id="e8edc-133">[Поиск документов с помощью списков результатов](search-documents-using-results-lists.md) </span><span class="sxs-lookup"><span data-stu-id="e8edc-133">[Search Documents Using Results Lists](search-documents-using-results-lists.md) </span></span>  
 <span data-ttu-id="e8edc-134">[Поиск текста с символами-шаблонами](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="e8edc-134">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="e8edc-135">Поиск текста с помощью регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="e8edc-135">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
