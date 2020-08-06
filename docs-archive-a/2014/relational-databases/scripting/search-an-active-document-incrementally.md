---
title: Выполнение добавочного поиска в активном документе
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- searches [SQL Server Management Studio], incremental
- Query Editor [SQL Server Management Studio], incremental search
- incremental searches [SQL Server Management Studio]
ms.assetid: 490bb36c-dd43-4219-9e2a-ff27046b9395
author: rothja
ms.author: jroth
ms.openlocfilehash: aefc2f0b7abff5992a8f4f7817e564ef1b72009d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656308"
---
# <a name="search-an-active-document-incrementally"></a><span data-ttu-id="9e37c-102">Выполнение добавочного поиска в активном документе</span><span class="sxs-lookup"><span data-stu-id="9e37c-102">Search an Active Document Incrementally</span></span>
  <span data-ttu-id="9e37c-103">В отдельном документе или окне можно осуществлять добавочный поиск с уточнением критериев путем ввода текста.</span><span class="sxs-lookup"><span data-stu-id="9e37c-103">You can search a single document or window incrementally by entering text.</span></span> <span data-ttu-id="9e37c-104">При операции поиска первый набор символов, соответствующий введенным в ходе добавочного поиска в документе или окне, выделяется цветом.</span><span class="sxs-lookup"><span data-stu-id="9e37c-104">The search operation highlights the first set of characters that matches the characters entered during the incremental search in the document or window.</span></span> <span data-ttu-id="9e37c-105">При добавочном поиске производится автоматический поиск во всем тексте документа или окна, кроме скрытого текста.</span><span class="sxs-lookup"><span data-stu-id="9e37c-105">Incremental search automatically searches all of the text within a document or window except for text that has been hidden.</span></span>  
  
 <span data-ttu-id="9e37c-106">Для параметра **Учитывать регистр** во время добавочного поиска используется значение, заданное при предыдущем поиске.</span><span class="sxs-lookup"><span data-stu-id="9e37c-106">For the **Match case** option, incremental search uses the criteria from your previous search.</span></span> <span data-ttu-id="9e37c-107">Например, если производился поиск в нескольких файлах с помощью диалогового окна **Поиск в файлах** при установленном флажке **Учитывать регистр**, а следующий поиск осуществляется добавочно, при этом поиске будет учитываться регистр.</span><span class="sxs-lookup"><span data-stu-id="9e37c-107">For example, if you searched across multiple files using the **Find in Files** dialog box and select **Match Case**, and you next search incrementally, the search will be case-sensitive.</span></span>  
  
### <a name="to-search-incrementally"></a><span data-ttu-id="9e37c-108">Выполнение добавочного поиска</span><span class="sxs-lookup"><span data-stu-id="9e37c-108">To search incrementally</span></span>  
  
1.  <span data-ttu-id="9e37c-109">Откройте файл или окно, в котором требуется произвести поиск.</span><span class="sxs-lookup"><span data-stu-id="9e37c-109">Open the file or window to you want to search.</span></span>  
  
2.  <span data-ttu-id="9e37c-110">В меню **Правка** укажите **Дополнительно**, а затем **Добавочный поиск**.</span><span class="sxs-lookup"><span data-stu-id="9e37c-110">On the **Edit** menu, point to **Advanced**, and then click **Incremental Search**.</span></span>  
  
     <span data-ttu-id="9e37c-111">Значок курсора примет форму бинокля со стрелкой, указывающей направление поиска, а в строке состояния появится надпись «Добавочный поиск».</span><span class="sxs-lookup"><span data-stu-id="9e37c-111">The cursor icon changes to a binocular with an arrow, indicating the search direction, and the status bar displays "Incremental Search."</span></span>  
  
3.  <span data-ttu-id="9e37c-112">Начинайте ввод строки текста.</span><span class="sxs-lookup"><span data-stu-id="9e37c-112">Begin typing the text string.</span></span>  
  
     <span data-ttu-id="9e37c-113">В строке состояния отображается введенный текст, в то время как в редакторе первое совпадение этого текста выделяется цветом.</span><span class="sxs-lookup"><span data-stu-id="9e37c-113">The status bar displays the text you are entering while the editor highlights the first occurrence that matches the text.</span></span> <span data-ttu-id="9e37c-114">По мере ввода редактор перемещается на следующее совпадение и выделяет его.</span><span class="sxs-lookup"><span data-stu-id="9e37c-114">As you continue typing, the editor moves to the next match and highlights it.</span></span> <span data-ttu-id="9e37c-115">Если совпадений текста не найдено, в строке состояния отображается следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="9e37c-115">If no matches are available, the status bar displays the following.</span></span>  
  
    ```  
    Incremental Search: <text> (not found)  
    ```  
  
 <span data-ttu-id="9e37c-116">Добавочный поиск выполняется с текущей позиции в направлении конца документа слева направо.</span><span class="sxs-lookup"><span data-stu-id="9e37c-116">Incremental searches are performed from the current location in the document downwards from left to right.</span></span> <span data-ttu-id="9e37c-117">Добавочный поиск может быть запущен с помощью сочетания клавиш.</span><span class="sxs-lookup"><span data-stu-id="9e37c-117">Incremental searches can be done using keyboard shortcut keys.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9e37c-118">Полный список сочетаний клавиш см. в статье [Сочетания клавиш среды SQL Server Management Studio](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="9e37c-118">For a complete list of keyboard shortcut keys, see [SQL Server Management Studio Keyboard Shortcuts](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e37c-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="9e37c-119">See Also</span></span>  
 <span data-ttu-id="9e37c-120">[Поиск и замена](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="9e37c-120">[Search and Replace](search-and-replace.md) </span></span>  
 <span data-ttu-id="9e37c-121">[осуществлять поиск в документах в интерактивном режиме](search-documents-interactively.md) </span><span class="sxs-lookup"><span data-stu-id="9e37c-121">[Search Documents Interactively](search-documents-interactively.md) </span></span>  
 <span data-ttu-id="9e37c-122">[Поиск документов с помощью списков результатов](search-documents-using-results-lists.md) </span><span class="sxs-lookup"><span data-stu-id="9e37c-122">[Search Documents Using Results Lists](search-documents-using-results-lists.md) </span></span>  
 <span data-ttu-id="9e37c-123">[Поиск текста с символами-шаблонами](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="9e37c-123">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="9e37c-124">Поиск текста с помощью регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="9e37c-124">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
