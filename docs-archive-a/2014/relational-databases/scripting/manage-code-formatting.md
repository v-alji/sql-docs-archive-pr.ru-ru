---
title: управлять форматированием кода
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- indenting code [SQL Server]
- displaying URLs
- code formatting [SQL Server Management Studio]
- collapsing text
- formats [SQL Server], code formatting in SQL Server Management Studio
- hiding text
- formats [SQL Server]
- text [SQL Server], code formats
- automatic indentation
- converting text to lower case
- Query Editor [SQL Server Management Studio], managing code formats
- URL displayed in code [SQL Server Management Studio]
- converting text to upper case
- text [SQL Server]
- unindenting code
ms.assetid: ddbac4d2-6bdc-4467-a352-e869ec880eed
author: rothja
ms.author: jroth
ms.openlocfilehash: 873848c8aee575b47f7a3d8c31d8392cba5ed12e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668742"
---
# <a name="manage-code-formatting"></a><span data-ttu-id="a7b9c-102">управлять форматированием кода</span><span class="sxs-lookup"><span data-stu-id="a7b9c-102">Manage Code Formatting</span></span>
  <span data-ttu-id="a7b9c-103">В редакторе можно форматировать код отступами, скрывать текст, вводить URL-адреса и т. д.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-103">With the Editor you can format your code with indenting, hidden text, URLs, and so forth.</span></span> <span data-ttu-id="a7b9c-104">Можно также выполнять автоматическое форматирование кода с помощью интеллектуальных отступов.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-104">You can also auto-format your code as you type by using Smart Indenting.</span></span>  
  
## <a name="indenting"></a><span data-ttu-id="a7b9c-105">Отступы</span><span class="sxs-lookup"><span data-stu-id="a7b9c-105">Indenting</span></span>  
 <span data-ttu-id="a7b9c-106">Возможны три разных стиля расстановки отступов.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-106">You can choose three different styles of text indenting.</span></span> <span data-ttu-id="a7b9c-107">Можно указать, сколько пробелов должно входить в один отступ или табуляцию, а также какие символы редактор будет использовать при расстановке отступов: табуляции или пробелы.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-107">You can also specify how many spaces compose a single indentation or tab, and whether the Editor uses tabs or space characters when indenting.</span></span>  
  
#### <a name="to-choose-an-indenting-style"></a><span data-ttu-id="a7b9c-108">Выбор стиля расстановки отступов</span><span class="sxs-lookup"><span data-stu-id="a7b9c-108">To choose an indenting style</span></span>  
  
1.  <span data-ttu-id="a7b9c-109">В меню **Сервис** выберите команду **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-109">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="a7b9c-110">Щелкните **Текстовый редактор**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-110">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="a7b9c-111">Щелкните папку и выберите **Все языки** , чтобы задать расстановку отступов для всех языков.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-111">Click the folder, and select **All Languages** to set indenting for all languages.</span></span>  
  
4.  <span data-ttu-id="a7b9c-112">Щелкните **Вкладки**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-112">Click **Tabs**.</span></span>  
  
5.  <span data-ttu-id="a7b9c-113">Выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="a7b9c-113">Click one of the following options:</span></span>  
  
    -   <span data-ttu-id="a7b9c-114">**Нет**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-114">**None**.</span></span> <span data-ttu-id="a7b9c-115">Курсор переходит на начало следующей строки.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-115">The cursor goes to the beginning of the next line.</span></span>  
  
    -   <span data-ttu-id="a7b9c-116">**Заблокировать**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-116">**Block**.</span></span> <span data-ttu-id="a7b9c-117">Курсор выравнивает следующую строку с предыдущей.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-117">The cursor aligns the next line with the previous line.</span></span>  
  
    -   <span data-ttu-id="a7b9c-118">**Автоматически** (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="a7b9c-118">**Smart** (Default).</span></span> <span data-ttu-id="a7b9c-119">Подходящий стиль расстановки отступов определяет служба языков.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-119">The language service determines the appropriate indenting style to use.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a7b9c-120">В некоторых языках могут не поддерживаться все три параметра расстановки отступов.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-120">Some languages do not offer all three indenting options.</span></span>  
  
#### <a name="to-change-indent-tab-settings"></a><span data-ttu-id="a7b9c-121">Изменение параметров отступов табуляциями</span><span class="sxs-lookup"><span data-stu-id="a7b9c-121">To change indent tab settings</span></span>  
  
1.  <span data-ttu-id="a7b9c-122">В меню **Сервис** выберите команду **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-122">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="a7b9c-123">Щелкните **Текстовый редактор**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-123">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="a7b9c-124">Щелкните папку **Все языки** , чтобы задать расстановку отступов для всех языков.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-124">Select the folder for **All Languages** to set indenting for all languages.</span></span>  
  
4.  <span data-ttu-id="a7b9c-125">Щелкните **Вкладки**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-125">Click **Tabs**.</span></span>  
  
5.  <span data-ttu-id="a7b9c-126">Чтобы задать символы табуляции для операций расстановки табуляций и отступов, щелкните **Сохранить табуляции**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-126">To specify tab characters for tab and indent operations, click **Keep tabs**.</span></span> <span data-ttu-id="a7b9c-127">Чтобы указать символы пробелов, выберите **Вставлять пробелы**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-127">To specify space characters, select **Insert spaces**.</span></span>  
  
     <span data-ttu-id="a7b9c-128">Если выбрано **Вставлять пробелы**, введите количество пробелов в каждой табуляции или отступе в полях **Размер табуляции** или **Размер отступа**соответственно.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-128">If you select **Insert Spaces**, enter the number of space characters each tab or indent represents under **Tab Size** or **Indent Size**, respectively.</span></span>  
  
#### <a name="to-indent-code"></a><span data-ttu-id="a7b9c-129">Создание отступа в тексте кода</span><span class="sxs-lookup"><span data-stu-id="a7b9c-129">To indent code</span></span>  
  
1.  <span data-ttu-id="a7b9c-130">Выберите текст, в котором нужно применить отступы.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-130">Select the text you want to indent.</span></span>  
  
2.  <span data-ttu-id="a7b9c-131">Нажмите клавишу TAB или кнопку **Отступ** на панели инструментов «Стандартная».</span><span class="sxs-lookup"><span data-stu-id="a7b9c-131">Press TAB, or click the **Indent** button on the Standard toolbar.</span></span>  
  
#### <a name="to-unindent-code"></a><span data-ttu-id="a7b9c-132">Отмена отступа в коде</span><span class="sxs-lookup"><span data-stu-id="a7b9c-132">To unindent code</span></span>  
  
1.  <span data-ttu-id="a7b9c-133">Выберите текст, в котором нужно удалить отступы.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-133">Select the text you want to unindent.</span></span>  
  
2.  <span data-ttu-id="a7b9c-134">Нажмите SHIFT + TAB или кнопку **Удалить отступы** на панели инструментов "Стандартная".</span><span class="sxs-lookup"><span data-stu-id="a7b9c-134">Press SHIFT+TAB, or click the **Unindent** button on the Standard toolbar.</span></span>  
  
#### <a name="to-automatically-indent-all-of-your-code"></a><span data-ttu-id="a7b9c-135">Автоматическая расстановка отступов во всем коде</span><span class="sxs-lookup"><span data-stu-id="a7b9c-135">To automatically indent all of your code</span></span>  
  
1.  <span data-ttu-id="a7b9c-136">В меню **Сервис** выберите команду **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-136">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="a7b9c-137">Щелкните **Текстовый редактор**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-137">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="a7b9c-138">Щелкните **Все языки**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-138">Click **All Languages**.</span></span>  
  
4.  <span data-ttu-id="a7b9c-139">Щелкните **Вкладки**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-139">Click **Tabs**.</span></span>  
  
5.  <span data-ttu-id="a7b9c-140">Выберите **Автоматически**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-140">Click **Smart**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7b9c-141">Параметр **Автоматически** в некоторых языках недоступен.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-141">The **Smart** option is not available for some languages.</span></span>  
  
#### <a name="to-convert-white-space-to-tabs"></a><span data-ttu-id="a7b9c-142">Преобразование пробелов в табуляции</span><span class="sxs-lookup"><span data-stu-id="a7b9c-142">To convert white space to tabs</span></span>  
  
1.  <span data-ttu-id="a7b9c-143">Выберите текст, в котором нужно преобразовать пробелы в табуляции.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-143">Select the text whose white space you want to convert to tabs.</span></span>  
  
2.  <span data-ttu-id="a7b9c-144">В меню **Правка** укажите пункт **Дополнительно**и выберите **Установить табуляции в выделенном**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-144">On the **Edit** menu, point to **Advanced**, and click **Tabify Selection**.</span></span>  
  
#### <a name="to-convert-tabs-to-spaces"></a><span data-ttu-id="a7b9c-145">Преобразование табуляций в пробелы</span><span class="sxs-lookup"><span data-stu-id="a7b9c-145">To convert tabs to spaces</span></span>  
  
1.  <span data-ttu-id="a7b9c-146">Выберите текст, в котором нужно преобразовать табуляции в пробелы.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-146">Select the text whose tabs you want to convert to spaces.</span></span>  
  
2.  <span data-ttu-id="a7b9c-147">В меню **Правка** укажите пункт **Дополнительно**и выберите **Удалить табуляции в выделенном**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-147">On the **Edit** menu, point to **Advanced**, and click **Untabify Selection**.</span></span>  
  
 <span data-ttu-id="a7b9c-148">Действие этих команд зависит от настройки табуляции в диалоговом окне **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="a7b9c-148">The behavior of these commands depends on the tab settings in the **Options** dialog box.</span></span> <span data-ttu-id="a7b9c-149">Например, если параметр табуляции равен 4, **Установить табуляции в выделенном** заменяет табуляцией каждые 4 непрерывных пробела, а **Удалить табуляции в выделенном** создает 4 пробела для каждой табуляции.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-149">For example, if the tab setting is 4, **Tabify Selection** creates a tab for every 4 contiguous spaces, and **Untabify Selection** creates 4 spaces for every tab.</span></span>  
  
## <a name="converting-text-to-upper-and-lower-case"></a><span data-ttu-id="a7b9c-150">Преобразование текста в верхний и нижний регистр</span><span class="sxs-lookup"><span data-stu-id="a7b9c-150">Converting Text to Upper and Lower Case</span></span>  
 <span data-ttu-id="a7b9c-151">Для преобразования текста в верхний или нижний регистр имеются специальные команды.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-151">You can use commands to convert text to all uppercase or lower case.</span></span>  
  
#### <a name="to-switch-text-to-upper-or-lower-case"></a><span data-ttu-id="a7b9c-152">Преобразование текста в верхний и нижний регистр</span><span class="sxs-lookup"><span data-stu-id="a7b9c-152">To switch text to upper or lower case</span></span>  
  
1.  <span data-ttu-id="a7b9c-153">Выберите текст, который нужно преобразовать.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-153">Select the text you want to convert.</span></span>  
  
2.  <span data-ttu-id="a7b9c-154">Чтобы преобразовать текст в верхний регистр, нажмите CTRL + SHIFT + U или выберите **Верхний регистр** в подменю **Дополнительно** меню **Правка** .</span><span class="sxs-lookup"><span data-stu-id="a7b9c-154">To convert text to uppercase, press CTRL+SHIFT+U, or click **Make Uppercase** on the **Advanced** submenu of the **Edit** menu.</span></span>  
  
3.  <span data-ttu-id="a7b9c-155">Чтобы преобразовать текст в нижний регистр, нажмите CTRL + SHIFT + L или выберите **Нижний регистр** в подменю **Дополнительно** меню **Правка** .</span><span class="sxs-lookup"><span data-stu-id="a7b9c-155">To convert text to lowercase, press CTRL+SHIFT+L, or click **Make Lowercase** on the **Advanced** submenu of the **Edit** menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7b9c-156">Полный список сочетаний клавиш см. в статье [Сочетания клавиш среды SQL Server Management Studio](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="a7b9c-156">For a complete list of keyboard shortcut keys, see [SQL Server Management Studio Keyboard Shortcuts](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span></span>  
  
## <a name="displaying-and-linking-to-urls"></a><span data-ttu-id="a7b9c-157">Отображение URL-адресов и переход по ним</span><span class="sxs-lookup"><span data-stu-id="a7b9c-157">Displaying and Linking to URLs</span></span>  
 <span data-ttu-id="a7b9c-158">В программном коде можно создавать и отображать интерактивные URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-158">You can create and display clickable URLs in your code.</span></span> <span data-ttu-id="a7b9c-159">По умолчанию URL-адреса:</span><span class="sxs-lookup"><span data-stu-id="a7b9c-159">By default, the URLs:</span></span>  
  
-   <span data-ttu-id="a7b9c-160">подчеркнуты;</span><span class="sxs-lookup"><span data-stu-id="a7b9c-160">Are underlined.</span></span>  
  
-   <span data-ttu-id="a7b9c-161">при наведении указателя меняют его форму на изображение ладони;</span><span class="sxs-lookup"><span data-stu-id="a7b9c-161">Change the mouse pointer to a hand when you move over them.</span></span>  
  
-   <span data-ttu-id="a7b9c-162">открывают URL-адрес при щелчке на нем, если этот URL-адрес действителен.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-162">Open the URL when clicked, if the URL is valid.</span></span>  
  
#### <a name="to-display-a-clickable-url"></a><span data-ttu-id="a7b9c-163">Включение отображения интерактивных URL-адресов</span><span class="sxs-lookup"><span data-stu-id="a7b9c-163">To display a clickable URL</span></span>  
  
1.  <span data-ttu-id="a7b9c-164">В меню **Сервис** выберите команду **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-164">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="a7b9c-165">Щелкните **Текстовый редактор**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-165">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="a7b9c-166">Чтобы изменить параметр только для одного языка, щелкните папку этого языка и выберите **Общие**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-166">To change the option for only one language, click that language folder and then click **General**.</span></span> <span data-ttu-id="a7b9c-167">Чтобы изменить параметр для всех языков, щелкните **Все языки** и выберите **Общие**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-167">To change the option for all languages, click **All Languages** and then click **General**.</span></span>  
  
4.  <span data-ttu-id="a7b9c-168">Выберите **Переход по URL-адресам одним щелчком**.</span><span class="sxs-lookup"><span data-stu-id="a7b9c-168">Select **Enable single-click URL navigation**.</span></span>  
  
  
