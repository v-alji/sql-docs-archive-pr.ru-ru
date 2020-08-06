---
title: Параметры (текстовый редактор — Transact-SQL — страница «вкладки») | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.SQL.Tabs
dev_langs:
- TSQL
ms.assetid: a4499784-67f7-46ef-9f7c-2d0fdd117a52
author: rothja
ms.author: jroth
ms.openlocfilehash: 6caa659d13f8089fdd9f990a55e503657ef72a43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666209"
---
# <a name="options-text-editor---transact-sql---tabs-page"></a><span data-ttu-id="e4df9-102">Параметры (текстовый редактор — Transact-SQL — страница «вкладки»)</span><span class="sxs-lookup"><span data-stu-id="e4df9-102">Options (Text Editor - Transact-SQL - Tabs Page)</span></span>
  <span data-ttu-id="e4df9-103">Используйте это диалоговое окно, чтобы изменить действия редактора запросов компонента [!INCLUDE[ssDE](../includes/ssde-md.md)], который используется для скриптов программы [!INCLUDE[tsql](../includes/tsql-md.md)], при нажатии клавиши TAB.</span><span class="sxs-lookup"><span data-stu-id="e4df9-103">Use this dialog to change the tabbing behavior of the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor, which is used to program [!INCLUDE[tsql](../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="e4df9-104">Для вывода этих параметров выберите пункт **Параметры** в меню **Сервис**, раскройте узел **Текстовый редактор**, раскройте вложенную папку **Transact-SQL** и щелкните **Вкладки**.</span><span class="sxs-lookup"><span data-stu-id="e4df9-104">To display these settings, click **Options** on the **Tools** menu, expand the **Text Editor** folder, expand the **Transact-SQL** subfolder and then click **Tabs**.</span></span>  
  
## <a name="setting-options-in-multiple-locations"></a><span data-ttu-id="e4df9-105">Настройка параметров в нескольких местах</span><span class="sxs-lookup"><span data-stu-id="e4df9-105">Setting Options in Multiple Locations</span></span>  
 <span data-ttu-id="e4df9-106">Параметры для редактора запросов компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] можно также задать в диалоговом окне **Вкладки всех языков**.</span><span class="sxs-lookup"><span data-stu-id="e4df9-106">Options for the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor can also be set in the **All Languages Tabs** dialog.</span></span> <span data-ttu-id="e4df9-107">Если диалоговое окно **Все языки** используется для задания других параметров прочих редакторов среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , например DMX или MDX, то необходимо с помощью данного окна сбросить параметры редактора запросов компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e4df9-107">If you use the **All Languages** dialogs to set different options for the other [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] editors, such as the DMX or MDX editors, you must reset the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor options using this dialog.</span></span>  
  
## <a name="indenting"></a><span data-ttu-id="e4df9-108">Отступы</span><span class="sxs-lookup"><span data-stu-id="e4df9-108">Indenting</span></span>  
 <span data-ttu-id="e4df9-109">**None**</span><span class="sxs-lookup"><span data-stu-id="e4df9-109">**None**</span></span>  
 <span data-ttu-id="e4df9-110">Если данный параметр выбран, при нажатии клавиши ВВОД отступ у новой строки создаваться не будет.</span><span class="sxs-lookup"><span data-stu-id="e4df9-110">When this option is selected, the new line created when you press ENTER is not indented.</span></span> <span data-ttu-id="e4df9-111">Курсор помещается в первый столбец новой строки.</span><span class="sxs-lookup"><span data-stu-id="e4df9-111">The cursor is placed at the first column of the new line.</span></span>  
  
 <span data-ttu-id="e4df9-112">**Заблокировать**</span><span class="sxs-lookup"><span data-stu-id="e4df9-112">**Block**</span></span>  
 <span data-ttu-id="e4df9-113">Если выбран данный режим, то новая строка, создаваемая при нажатии клавиши ВВОД, будет автоматически перемещена на такое же расстояние, что и предыдущая.</span><span class="sxs-lookup"><span data-stu-id="e4df9-113">When this option is selected, the new line created when you press ENTER is automatically indented the same distance as the previous line.</span></span>  
  
 <span data-ttu-id="e4df9-114">**Структура**</span><span class="sxs-lookup"><span data-stu-id="e4df9-114">**Smart**</span></span>  
 <span data-ttu-id="e4df9-115">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="e4df9-115">This option is unavailable.</span></span>  
  
## <a name="tabs"></a><span data-ttu-id="e4df9-116">Вкладки</span><span class="sxs-lookup"><span data-stu-id="e4df9-116">Tabs</span></span>  
 <span data-ttu-id="e4df9-117">**Размер интервала табуляции**</span><span class="sxs-lookup"><span data-stu-id="e4df9-117">**Tab size**</span></span>  
 <span data-ttu-id="e4df9-118">Устанавливает расстояние в пробелах между табуляторами.</span><span class="sxs-lookup"><span data-stu-id="e4df9-118">Sets the distance in spaces between tab stops.</span></span> <span data-ttu-id="e4df9-119">По умолчанию этот параметр равен четырем пробелам.</span><span class="sxs-lookup"><span data-stu-id="e4df9-119">The default is four spaces.</span></span>  
  
 <span data-ttu-id="e4df9-120">**Размер отступа**</span><span class="sxs-lookup"><span data-stu-id="e4df9-120">**Indent size**</span></span>  
 <span data-ttu-id="e4df9-121">Устанавливается размер автоматического отступа в пробелах.</span><span class="sxs-lookup"><span data-stu-id="e4df9-121">Sets the size in spaces of an automatic indentation.</span></span> <span data-ttu-id="e4df9-122">По умолчанию этот параметр равен четырем пробелам.</span><span class="sxs-lookup"><span data-stu-id="e4df9-122">The default is four spaces.</span></span> <span data-ttu-id="e4df9-123">Символы табуляции, символы пробела или оба этих вида символов будут вставлены для заполнения указанного размера.</span><span class="sxs-lookup"><span data-stu-id="e4df9-123">Tab characters, space characters, or both are inserted to fill the specified size.</span></span>  
  
 <span data-ttu-id="e4df9-124">**Вставлять пробелы**</span><span class="sxs-lookup"><span data-stu-id="e4df9-124">**Insert spaces**</span></span>  
 <span data-ttu-id="e4df9-125">При выборе этого параметра операции отступа вставляют только пробелы, а не символы табуляции.</span><span class="sxs-lookup"><span data-stu-id="e4df9-125">When this option is selected, indent operations insert only space characters, not tab characters.</span></span> <span data-ttu-id="e4df9-126">Например, если для параметра **Размер отступа** задано значение 5, то при каждом нажатии клавиши TAB или нажатии кнопки **увеличить отступ** на панели инструментов в главном окне вставляются пять символов пробела [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e4df9-126">If **Indent size** is set to 5, for example, then five space characters are inserted whenever you press the TAB key or click the **Increase Indent** button on the toolbar in the main [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] window.</span></span>  
  
 <span data-ttu-id="e4df9-127">**Сохранять знаки табуляции**</span><span class="sxs-lookup"><span data-stu-id="e4df9-127">**Keep tabs**</span></span>  
 <span data-ttu-id="e4df9-128">При выборе этого параметра операции отступа вставляют максимально возможное количество символов табуляции.</span><span class="sxs-lookup"><span data-stu-id="e4df9-128">When this option is selected, indent operations insert as many tab characters as possible.</span></span> <span data-ttu-id="e4df9-129">Каждый символ табуляции включает количество пробелов, указанное в параметре **Размер интервала табуляции**.</span><span class="sxs-lookup"><span data-stu-id="e4df9-129">Each tab character fills the number of spaces specified in **Tab size**.</span></span> <span data-ttu-id="e4df9-130">Если параметр **Размер отступа** не кратен точно параметру **Размер интервала табуляции**, для заполнения остатка вставляются пробелы.</span><span class="sxs-lookup"><span data-stu-id="e4df9-130">If **Indent size** is not an even multiple of **Tab size**, space characters are added to fill in the difference.</span></span>  
  
  
