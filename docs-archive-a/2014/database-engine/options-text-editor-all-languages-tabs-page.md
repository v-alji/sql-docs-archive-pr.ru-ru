---
title: Параметры (текстовый редактор — все языки — страница вкладок) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: bd715d6b-f873-41d4-aa10-57b7098b61cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 13f791e34b2099e8c0492c25886ee6b37ef1a1a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667390"
---
# <a name="options-text-editor---all-languages--tabs-page"></a><span data-ttu-id="beeaf-102">Параметры ("Текстовый редактор" — "Все языки" — страница "Вкладки")</span><span class="sxs-lookup"><span data-stu-id="beeaf-102">Options (Text Editor - All Languages -Tabs Page)</span></span>
  <span data-ttu-id="beeaf-103">Это диалоговое окно используется для задания действий во всех пяти редакторах в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]при использовании клавиши TAB.</span><span class="sxs-lookup"><span data-stu-id="beeaf-103">Use this dialog box to set the tabbing behavior in all five of the editors in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="beeaf-104">Для отображения этих параметров в меню **Сервис** выберите **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="beeaf-104">To display these options, click **Options** on the **Tools** menu.</span></span> <span data-ttu-id="beeaf-105">Выберите папку **Текстовый редактор** , откройте папку **Все языки** и выберите **Вкладки**.</span><span class="sxs-lookup"><span data-stu-id="beeaf-105">Select the **Text Editor** folder, expand the **All Languages** folder and then click **Tabs**.</span></span>  
  
## <a name="tabbing-options-by-editor"></a><span data-ttu-id="beeaf-106">Параметры табуляции, задаваемые с помощью редактора</span><span class="sxs-lookup"><span data-stu-id="beeaf-106">Tabbing Options by Editor</span></span>  
 <span data-ttu-id="beeaf-107">Параметры редакторов DMX, MDX и SQL Server Compact задаются в диалоговом окне **Все языки** .</span><span class="sxs-lookup"><span data-stu-id="beeaf-107">You must use the **All Languages** dialogs to set options for the DMX, MDX, and SQL Server Compact editors.</span></span> <span data-ttu-id="beeaf-108">Задаваемые здесь параметры также применимы для редакторов простого текста, Transact-SQL и XML, однако для этих редакторов можно задать параметры отдельно, развернув вложенные папки для соответствующих языков и выбрав нужные страницы параметров.</span><span class="sxs-lookup"><span data-stu-id="beeaf-108">Options set here are also applied to the Plain Text, Transact-SQL, and XML editors, but you can set options separately for those editors by expanding the subfolders for those languages and selecting their option pages.</span></span> <span data-ttu-id="beeaf-109">В некоторых языках поддерживаются не все параметры табуляции.</span><span class="sxs-lookup"><span data-stu-id="beeaf-109">Some languages do not support all of the tabbing options.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="beeaf-110">Если для задания параметра используется данное диалоговое окно, но при этом нужно задать другие параметры для редакторов простого текста, Transact-SQL и XML, это следует делать после применения изменений в диалоговом окне **Все языки**.</span><span class="sxs-lookup"><span data-stu-id="beeaf-110">If you set an option using this dialog, but want a different setting for the Plain Text, Transact-SQL, or XML editors, you must set the options for those editors after applying your selections in the **All Languages** dialog.</span></span>  
  
 <span data-ttu-id="beeaf-111">Сообщение «Конфликт между параметрами отступа (или табуляции) для отдельных текстовых форматов» отображается, если для определенных редакторов выбраны разные параметры.</span><span class="sxs-lookup"><span data-stu-id="beeaf-111">The message "The indentation (or tab) settings for individual text formats conflict with each other" is displayed when different settings have been selected for particular editors.</span></span> <span data-ttu-id="beeaf-112">Например, это напоминание выводится, если для параметра **Обычный текст** выбран параметр **Отступ блока**, но для **XML** выбрано **Нет**.</span><span class="sxs-lookup"><span data-stu-id="beeaf-112">For example, this reminder is displayed if the **Block indenting** option is selected for **Plain Text**, but **None** is selected for **XML**.</span></span>  
  
## <a name="indenting"></a><span data-ttu-id="beeaf-113">Отступы</span><span class="sxs-lookup"><span data-stu-id="beeaf-113">Indenting</span></span>  
 <span data-ttu-id="beeaf-114">**None**</span><span class="sxs-lookup"><span data-stu-id="beeaf-114">**None**</span></span>  
 <span data-ttu-id="beeaf-115">Если данный параметр выбран, при нажатии клавиши ВВОД отступ у новой строки создаваться не будет.</span><span class="sxs-lookup"><span data-stu-id="beeaf-115">When this option is selected, the new line created when you press ENTER is not indented.</span></span> <span data-ttu-id="beeaf-116">Курсор помещается в первый столбец новой строки.</span><span class="sxs-lookup"><span data-stu-id="beeaf-116">The cursor is placed at the first column of the new line.</span></span>  
  
 <span data-ttu-id="beeaf-117">**Заблокировать**</span><span class="sxs-lookup"><span data-stu-id="beeaf-117">**Block**</span></span>  
 <span data-ttu-id="beeaf-118">При выборе этого параметра во вновь созданной строке при нажатии пользователем клавиши ВВОД производится отступ на то же расстояние, что и в предыдущей строке.</span><span class="sxs-lookup"><span data-stu-id="beeaf-118">When this option is selected, the new line created when you press ENTER is automatically indented the same distance as the previous line was indented.</span></span>  
  
 <span data-ttu-id="beeaf-119">**Структура**</span><span class="sxs-lookup"><span data-stu-id="beeaf-119">**Smart**</span></span>  
 <span data-ttu-id="beeaf-120">Если выбран этот параметр, после нажатия клавиши ВВОД новая строка располагается в соответствии с контекстом.</span><span class="sxs-lookup"><span data-stu-id="beeaf-120">When this option is selected, the new line created when you press ENTER is positioned according to the context.</span></span>  
  
## <a name="tabs"></a><span data-ttu-id="beeaf-121">Вкладки</span><span class="sxs-lookup"><span data-stu-id="beeaf-121">Tabs</span></span>  
 <span data-ttu-id="beeaf-122">**Размер интервала табуляции**</span><span class="sxs-lookup"><span data-stu-id="beeaf-122">**Tab size**</span></span>  
 <span data-ttu-id="beeaf-123">Устанавливает расстояние в пробелах между табуляторами.</span><span class="sxs-lookup"><span data-stu-id="beeaf-123">Sets the distance in spaces between tab stops.</span></span> <span data-ttu-id="beeaf-124">По умолчанию этот параметр равен четырем пробелам.</span><span class="sxs-lookup"><span data-stu-id="beeaf-124">The default is four spaces.</span></span>  
  
 <span data-ttu-id="beeaf-125">**Размер отступа**</span><span class="sxs-lookup"><span data-stu-id="beeaf-125">**Indent size**</span></span>  
 <span data-ttu-id="beeaf-126">Устанавливается размер автоматического отступа в пробелах.</span><span class="sxs-lookup"><span data-stu-id="beeaf-126">Sets the size in spaces of an automatic indentation.</span></span> <span data-ttu-id="beeaf-127">По умолчанию этот параметр равен четырем пробелам.</span><span class="sxs-lookup"><span data-stu-id="beeaf-127">The default is four spaces.</span></span> <span data-ttu-id="beeaf-128">Для заполнения указанного размера вставляются символы табуляции, символы пробела или оба этих вида символов.</span><span class="sxs-lookup"><span data-stu-id="beeaf-128">Tab characters, space characters, or both will be inserted to fill the specified size.</span></span>  
  
 <span data-ttu-id="beeaf-129">**Вставлять пробелы**</span><span class="sxs-lookup"><span data-stu-id="beeaf-129">**Insert spaces**</span></span>  
 <span data-ttu-id="beeaf-130">При выборе этого параметра операции отступа вставляют только пробелы, а не символы табуляции.</span><span class="sxs-lookup"><span data-stu-id="beeaf-130">When this option is selected, indent operations insert only space characters, not tab characters.</span></span> <span data-ttu-id="beeaf-131">Например, если параметр **Ширина отступа** равен пяти, при нажатии клавиши TAB или кнопки **Увеличить отступ** на панели инструментов главного окна среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] вставляются пять символов пробела.</span><span class="sxs-lookup"><span data-stu-id="beeaf-131">If **Indent size** is set to 5, for example, then five space characters are inserted whenever you press the TAB key or click the **Increase Indent** button on the toolbar of the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] main window.</span></span>  
  
 <span data-ttu-id="beeaf-132">**Сохранять знаки табуляции**</span><span class="sxs-lookup"><span data-stu-id="beeaf-132">**Keep tabs**</span></span>  
 <span data-ttu-id="beeaf-133">При выборе этого параметра операции отступа вставляют максимально возможное количество символов табуляции.</span><span class="sxs-lookup"><span data-stu-id="beeaf-133">When this option is selected, indent operations insert as many tab characters as possible.</span></span> <span data-ttu-id="beeaf-134">Каждый символ табуляции включает количество пробелов, указанное в параметре **Размер интервала табуляции**.</span><span class="sxs-lookup"><span data-stu-id="beeaf-134">Each tab character fills the number of spaces specified in **Tab size**.</span></span> <span data-ttu-id="beeaf-135">Если параметр **Размер отступа** не кратен точно параметру **Размер интервала табуляции**, для заполнения остатка вставляются пробелы.</span><span class="sxs-lookup"><span data-stu-id="beeaf-135">If **Indent size** is not an even multiple of **Tab size**, space characters are added to fill in the difference.</span></span>  
  
  
