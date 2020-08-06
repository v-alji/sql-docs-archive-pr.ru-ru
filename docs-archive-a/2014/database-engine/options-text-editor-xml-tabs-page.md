---
title: 'Параметры (текстовый редактор: XML: Страница «Табуляция») | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.XML.Tabs
ms.assetid: 13bf5f8c-aba3-4c05-b8bb-eb475797c9bd
author: rothja
ms.author: jroth
ms.openlocfilehash: 3047d6c05ffb88d07a4bf2e5b1d4143412046c04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727321"
---
# <a name="options-text-editorxmltabs-page"></a><span data-ttu-id="b0793-102">Параметры (текстовый редактор: XML: страница "Табуляция")</span><span class="sxs-lookup"><span data-stu-id="b0793-102">Options (Text Editor:XML:Tabs Page)</span></span>
  <span data-ttu-id="b0793-103">Это диалоговое окно используется для изменения режима табуляции в редакторе XML, который используется для изменения XML-документов.</span><span class="sxs-lookup"><span data-stu-id="b0793-103">This dialog box lets you change the tabbing behavior of the XML Editor, which is used to edit XML documents.</span></span> <span data-ttu-id="b0793-104">Для вывода этих параметров выберите пункт **Параметры** в меню **Сервис** , раскройте узел **Текстовый редактор** , раскройте узел **XML** и щелкните **Табуляции**.</span><span class="sxs-lookup"><span data-stu-id="b0793-104">To display these settings, click **Options** on the **Tools** menu, expand the **Text Editor** folder, expand the **XML** subfolder and then click **Tabs**.</span></span>  
  
## <a name="setting-options-in-multiple-locations"></a><span data-ttu-id="b0793-105">Настройка параметров в нескольких местах</span><span class="sxs-lookup"><span data-stu-id="b0793-105">Setting Options in Multiple Locations</span></span>  
 <span data-ttu-id="b0793-106">Параметры редактора XML можно также задать в диалоговом окне **Все языки/Общие** .</span><span class="sxs-lookup"><span data-stu-id="b0793-106">Options for the XML Editor can also be set in the **All Languages General** dialog.</span></span> <span data-ttu-id="b0793-107">Если диалоговое окно **Все языки** используется для задания различных параметров для других редакторов среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , таких как DMX или MDX, необходимо сбросить параметры редактора XML с помощью этого окна.</span><span class="sxs-lookup"><span data-stu-id="b0793-107">If you use the **All Languages** dialogs to set different options for the other [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] editors, such as the DMX or MDX editors, you must reset the XML Editor options using this dialog.</span></span>  
  
## <a name="indenting"></a><span data-ttu-id="b0793-108">Отступы</span><span class="sxs-lookup"><span data-stu-id="b0793-108">Indenting</span></span>  
 <span data-ttu-id="b0793-109">**None**</span><span class="sxs-lookup"><span data-stu-id="b0793-109">**None**</span></span>  
 <span data-ttu-id="b0793-110">Если данный параметр выбран, при нажатии клавиши ВВОД отступ у новой строки создаваться не будет.</span><span class="sxs-lookup"><span data-stu-id="b0793-110">When this option is selected, the new line created when you press ENTER is not indented.</span></span> <span data-ttu-id="b0793-111">Курсор помещается в первый столбец новой строки.</span><span class="sxs-lookup"><span data-stu-id="b0793-111">The cursor is placed at the first column of the new line.</span></span>  
  
 <span data-ttu-id="b0793-112">**Заблокировать**</span><span class="sxs-lookup"><span data-stu-id="b0793-112">**Block**</span></span>  
 <span data-ttu-id="b0793-113">Если выбран данный режим, то новая строка, создаваемая при нажатии клавиши ВВОД, будет автоматически перемещена на такое же расстояние, что и предыдущая.</span><span class="sxs-lookup"><span data-stu-id="b0793-113">When this option is selected, the new line created when you press ENTER is automatically indented the same distance as the previous line.</span></span>  
  
 <span data-ttu-id="b0793-114">**Структура**</span><span class="sxs-lookup"><span data-stu-id="b0793-114">**Smart**</span></span>  
 <span data-ttu-id="b0793-115">Если выбран этот параметр, после нажатия клавиши ВВОД новая строка располагается в соответствии с контекстом.</span><span class="sxs-lookup"><span data-stu-id="b0793-115">When this option is selected, the new line created when you press ENTER is positioned according to the context.</span></span> <span data-ttu-id="b0793-116">Например при вводе открывающейся скобки ({) соответствующие строки автоматически сдвигаются на дополнительную позицию табулятора.</span><span class="sxs-lookup"><span data-stu-id="b0793-116">For example, after an opening brace ({), the included lines are automatically indented an extra tab stop.</span></span> <span data-ttu-id="b0793-117">Соответствующая закрывающаяся скобка (}) выравнивается с открывающейся.</span><span class="sxs-lookup"><span data-stu-id="b0793-117">The matching closing brace (}) is realigned with its opening brace.</span></span>  
  
## <a name="tabs"></a><span data-ttu-id="b0793-118">Вкладки</span><span class="sxs-lookup"><span data-stu-id="b0793-118">Tabs</span></span>  
 <span data-ttu-id="b0793-119">**Размер интервала табуляции**</span><span class="sxs-lookup"><span data-stu-id="b0793-119">**Tab size**</span></span>  
 <span data-ttu-id="b0793-120">Устанавливает расстояние в пробелах между табуляторами.</span><span class="sxs-lookup"><span data-stu-id="b0793-120">Sets the distance in spaces between tab stops.</span></span> <span data-ttu-id="b0793-121">По умолчанию этот параметр равен четырем пробелам.</span><span class="sxs-lookup"><span data-stu-id="b0793-121">The default is four spaces.</span></span>  
  
 <span data-ttu-id="b0793-122">**Размер отступа**</span><span class="sxs-lookup"><span data-stu-id="b0793-122">**Indent size**</span></span>  
 <span data-ttu-id="b0793-123">Устанавливается размер автоматического отступа в пробелах.</span><span class="sxs-lookup"><span data-stu-id="b0793-123">Sets the size in spaces of an automatic indentation.</span></span> <span data-ttu-id="b0793-124">По умолчанию этот параметр равен четырем пробелам.</span><span class="sxs-lookup"><span data-stu-id="b0793-124">The default is four spaces.</span></span> <span data-ttu-id="b0793-125">Символы табуляции, символы пробела или оба этих вида символов будут вставлены для заполнения указанного размера.</span><span class="sxs-lookup"><span data-stu-id="b0793-125">Tab characters, space characters, or both are inserted to fill the specified size.</span></span>  
  
 <span data-ttu-id="b0793-126">**Вставлять пробелы**</span><span class="sxs-lookup"><span data-stu-id="b0793-126">**Insert spaces**</span></span>  
 <span data-ttu-id="b0793-127">При выборе этого параметра операции отступа вставляют только пробелы, а не символы табуляции.</span><span class="sxs-lookup"><span data-stu-id="b0793-127">When this option is selected, indent operations insert only space characters, not tab characters.</span></span> <span data-ttu-id="b0793-128">Например, если для параметра **Размер отступа** задано значение 5, то при каждом нажатии клавиши TAB или нажатии кнопки **увеличить отступ** на панели инструментов в главном окне вставляются пять символов пробела [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b0793-128">If **Indent size** is set to 5, for example, then five space characters are inserted whenever you press the TAB key or click the **Increase Indent** button on the toolbar in the main [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] window.</span></span>  
  
 <span data-ttu-id="b0793-129">**Сохранять знаки табуляции**</span><span class="sxs-lookup"><span data-stu-id="b0793-129">**Keep tabs**</span></span>  
 <span data-ttu-id="b0793-130">При выборе этого параметра операции отступа вставляют максимально возможное количество символов табуляции.</span><span class="sxs-lookup"><span data-stu-id="b0793-130">When this option is selected, indent operations insert as many tab characters as possible.</span></span> <span data-ttu-id="b0793-131">Каждый символ табуляции включает количество пробелов, указанное в параметре **Размер интервала табуляции**.</span><span class="sxs-lookup"><span data-stu-id="b0793-131">Each tab character fills the number of spaces specified in **Tab size**.</span></span> <span data-ttu-id="b0793-132">Если параметр **Размер отступа** не кратен точно параметру **Размер интервала табуляции**, для заполнения остатка вставляются пробелы.</span><span class="sxs-lookup"><span data-stu-id="b0793-132">If **Indent size** is not an even multiple of **Tab size**, space characters are added to fill in the difference.</span></span>  
  
  
