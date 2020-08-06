---
title: Поиск и замена
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- match case [SQL Server]
- undo operations
- searches [SQL Server Management Studio]
- replacing text
- quick search and replaces [SQL Server Management Studio]
- Query Editor [SQL Server Management Studio], undo
- Query Editor [SQL Server Management Studio], searching
- regular expressions [SQL Server Management Studio]
- finding text [SQL Server Management Studio]
- text [SQL Server], search and replace operations
- finding [SQL Server Management Studio]
- locating text
- Query Editor [SQL Server Management Studio], replacing text
- Find and Replace dialog box
- wildcard options [SQL Server Management Studio]
- match whole word [SQL Server]
- searches [SQL Server Management Studio], replacing
ms.assetid: 3641c7b3-3e3e-4ddd-af82-c15b50004f94
author: rothja
ms.author: jroth
ms.openlocfilehash: 55422fa7201213477426c7bc25c45ff05acf8945
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656305"
---
# <a name="search-and-replace"></a><span data-ttu-id="1892d-102">Поиск и замена</span><span class="sxs-lookup"><span data-stu-id="1892d-102">Search and Replace</span></span>
  <span data-ttu-id="1892d-103">Существует несколько способов поиска и замены текста.</span><span class="sxs-lookup"><span data-stu-id="1892d-103">There are several different ways to find and replace text.</span></span> <span data-ttu-id="1892d-104">В меню **Правка** пункт **Найти и заменить** содержит четыре команды: **Быстрый поиск**, **Быстрая замена**, **Найти в файлах**или **Заменить в файлах**.</span><span class="sxs-lookup"><span data-stu-id="1892d-104">On the **Edit** menu, **Find and Replace** offers four choices: **Quick Find**, **Quick Replace**, **Find in Files**, or **Replace in Files**.</span></span> <span data-ttu-id="1892d-105">Каждая из этих команд открывает диалоговое окно **Найти и заменить** .</span><span class="sxs-lookup"><span data-stu-id="1892d-105">Each of these opens versions of the **Find and Replace** dialog box.</span></span> <span data-ttu-id="1892d-106">Можно выполнить поиск и без диалогового окна с помощью сочетаний клавиш добавочного поиска.</span><span class="sxs-lookup"><span data-stu-id="1892d-106">You can also search without a dialog box by using incremental search keyboard shortcut keys.</span></span> <span data-ttu-id="1892d-107">Эти методы позволяют управлять областью поиска и замены, а также выбирать способ просмотра совпадений при поиске и замене.</span><span class="sxs-lookup"><span data-stu-id="1892d-107">These techniques allow you to control the scope of find and replace, and choose the method of reviewing search matches and replacements.</span></span>  
  
 <span data-ttu-id="1892d-108">Выполняя поиск и замену текста, необходимо учитывать следующее.</span><span class="sxs-lookup"><span data-stu-id="1892d-108">You should consider the following when you search and replace text:</span></span>  
  
-   <span data-ttu-id="1892d-109">Параметры, установленные в диалоговом окне **Найти и заменить** , влияют на все поиски.</span><span class="sxs-lookup"><span data-stu-id="1892d-109">Options set in the **Find and Replace** dialog box affect all the searches.</span></span> <span data-ttu-id="1892d-110">В числе этих параметров такие, как **Учитывать регистр**, **Слово целиком**, **Искать вверх**, **Искать скрытый текст**, **Подстановочные знаки**, **Регулярные выражения**, **Искать во всех открытых документах**и **Искать в текущем проекте**.</span><span class="sxs-lookup"><span data-stu-id="1892d-110">These options include **Match case**, **Match whole word**, **Search up**, **Search hidden text**, **Wildcards**, **Regular Expressions**, **Look in All Open Documents**, and **Look in Current Project**.</span></span> <span data-ttu-id="1892d-111">Не все эти параметры доступны во всех версиях диалогового окна **Найти и заменить** ;</span><span class="sxs-lookup"><span data-stu-id="1892d-111">All options are not available in all versions of the **Find and Replace** dialog box.</span></span>  
  
-   <span data-ttu-id="1892d-112">Кнопка**Отмена** доступна только для документов, оставшихся открытыми после операции замены.</span><span class="sxs-lookup"><span data-stu-id="1892d-112">**Undo** is available only for documents left open after a replace operation.</span></span>  
  
-   <span data-ttu-id="1892d-113">Команда**Отменить** для операции **Заменить все** , выполняемой над несколькими файлами, рассматривается как единичное массовое действие над всеми затронутыми файлами.</span><span class="sxs-lookup"><span data-stu-id="1892d-113">**Undo** for a **Replace All** operation that spans more than one file is considered a single, bulk action across all the affected files.</span></span> <span data-ttu-id="1892d-114">При этом нельзя отменить изменения в одних файлах, сохранив их в других.</span><span class="sxs-lookup"><span data-stu-id="1892d-114">That is, you cannot undo the change in some files while retaining the change in other files.</span></span>  
  
 <span data-ttu-id="1892d-115">Обычно нельзя выполнять поиск в элементах с графическим отображением.</span><span class="sxs-lookup"><span data-stu-id="1892d-115">Generally, you cannot search items with graphical views.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1892d-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="1892d-116">See Also</span></span>  
 <span data-ttu-id="1892d-117">[Выполнение добавочного поиска в активном документе](search-an-active-document-incrementally.md) </span><span class="sxs-lookup"><span data-stu-id="1892d-117">[Search an Active Document Incrementally](search-an-active-document-incrementally.md) </span></span>  
 <span data-ttu-id="1892d-118">[осуществлять поиск в документах в интерактивном режиме](search-documents-interactively.md) </span><span class="sxs-lookup"><span data-stu-id="1892d-118">[Search Documents Interactively](search-documents-interactively.md) </span></span>  
 <span data-ttu-id="1892d-119">[Поиск документов с помощью списков результатов](search-documents-using-results-lists.md) </span><span class="sxs-lookup"><span data-stu-id="1892d-119">[Search Documents Using Results Lists](search-documents-using-results-lists.md) </span></span>  
 <span data-ttu-id="1892d-120">[Поиск текста с символами-шаблонами](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="1892d-120">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="1892d-121">Поиск текста с помощью регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="1892d-121">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
