---
title: Параметры (текстовый редактор — Transact-SQL-страница «Общие») | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.SQL.General
dev_langs:
- TSQL
ms.assetid: 7021ecb7-8fb5-4d8c-b984-3d34fcde8be2
author: rothja
ms.author: jroth
ms.openlocfilehash: f008d0d84a15cfbf0bfa988232015e6619f4f5c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666215"
---
# <a name="options-text-editor---transact-sql--general-page"></a><span data-ttu-id="e7d8b-102">Параметры (текстовый редактор — Transact-SQL-страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="e7d8b-102">Options (Text Editor - Transact-SQL- General Page)</span></span>
  <span data-ttu-id="e7d8b-103">Используйте диалоговое окно параметров **Общие** для изменения общего режима правок в редакторе запросов компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] , который используется для изменения скриптов [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e7d8b-103">Use the **General** options dialog box to change the general editing behavior of the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor, which is used to edit [!INCLUDE[tsql](../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="e7d8b-104">Чтобы отобразить эти параметры, выберите пункт **Параметры** в меню **Сервис**, откройте вложенную папку **Transact-SQL**, а затем откройте страницу **Общие**.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-104">To display these settings, click **Options** on the **Tools** menu, expand the **Transact-SQL** subfolder, and then click **General**.</span></span>  
  
## <a name="setting-options-in-multiple-locations"></a><span data-ttu-id="e7d8b-105">Настройка параметров в нескольких местах</span><span class="sxs-lookup"><span data-stu-id="e7d8b-105">Setting Options in Multiple Locations</span></span>  
 <span data-ttu-id="e7d8b-106">Параметры редактора запросов компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] можно также задать в диалоговом окне **Все языки/Общие** .</span><span class="sxs-lookup"><span data-stu-id="e7d8b-106">Options for the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor can also be set in the **All Languages General** dialog.</span></span> <span data-ttu-id="e7d8b-107">Если диалоговое окно **Все языки** используется для задания других параметров прочих редакторов среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , например DMX или MDX, то необходимо с помощью данного окна сбросить параметры редактора запросов компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e7d8b-107">If you use the **All Languages** dialogs to set different options for the other [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] editors, such as the DMX or MDX editors, you must reset the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor options using this dialog.</span></span>  
  
## <a name="statement-completion"></a><span data-ttu-id="e7d8b-108">Завершение операторов</span><span class="sxs-lookup"><span data-stu-id="e7d8b-108">Statement Completion</span></span>  
 <span data-ttu-id="e7d8b-109">**Автоматически отображать список членов**</span><span class="sxs-lookup"><span data-stu-id="e7d8b-109">**Auto list members**</span></span>  
 <span data-ttu-id="e7d8b-110">Если этот флажок установлен, то при вводе в редакторе отображаются списки доступных объектов базы данных и объектов схем, столбцов, функций с табличными значениями, или обычных функций.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-110">When this check box is selected, lists of available database and schema objects, columns, table-valued functions, or functions are displayed as you type in the editor.</span></span> <span data-ttu-id="e7d8b-111">Чтобы вставить в код элемент из всплывающего списка, выберите его.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-111">Choose any item from the pop-up list to insert it into your code.</span></span>  
  
 <span data-ttu-id="e7d8b-112">**Скрывать дополнительные члены**</span><span class="sxs-lookup"><span data-stu-id="e7d8b-112">**Hide advanced members**</span></span>  
 <span data-ttu-id="e7d8b-113">Этот флажок недоступен.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-113">This check box is unavailable.</span></span>  
  
 <span data-ttu-id="e7d8b-114">**Сведения о параметрах**</span><span class="sxs-lookup"><span data-stu-id="e7d8b-114">**Parameter information**</span></span>  
 <span data-ttu-id="e7d8b-115">Если установлен этот флажок, то отображаются сведения о параметрах для хранимой процедуры или функции, расположенной непосредственно слева от точки вставки (курсора).</span><span class="sxs-lookup"><span data-stu-id="e7d8b-115">When this check box is selected, parameter information is displayed for a stored procedure or function that is immediately to the left of the insertion point (cursor).</span></span> <span data-ttu-id="e7d8b-116">Эти сведения содержат список доступных параметров с их именами и типами данных.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-116">The information includes a list of the available parameters with their names and data types.</span></span>  
  
## <a name="settings"></a><span data-ttu-id="e7d8b-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="e7d8b-117">Settings</span></span>  
 <span data-ttu-id="e7d8b-118">**Разрешить виртуальные пробелы**</span><span class="sxs-lookup"><span data-stu-id="e7d8b-118">**Enable virtual space**</span></span>  
 <span data-ttu-id="e7d8b-119">Если установлен этот флажок, появляется возможность устанавливать курсор и печатать в любом месте строки кода.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-119">When this check box is selected, you can click anywhere beyond the end of a line of code and type.</span></span> <span data-ttu-id="e7d8b-120">Установите этот флажок для размещения комментариев в постоянной позиции относительно кода.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-120">Select this check box to position comments at a consistent point next to your code.</span></span> <span data-ttu-id="e7d8b-121">Установка этого флажка отключает параметр **Перенос по словам** .</span><span class="sxs-lookup"><span data-stu-id="e7d8b-121">Selecting this check box disables the **Word wrap** check box.</span></span>  
  
 <span data-ttu-id="e7d8b-122">**Перенос по словам**</span><span class="sxs-lookup"><span data-stu-id="e7d8b-122">**Word wrap**</span></span>  
 <span data-ttu-id="e7d8b-123">Если этот флажок установлен, любая часть строки, выступающая за пределы видимой области редактора по горизонтали, будет автоматически отображаться на следующей строке.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-123">When this check box is selected, any portion of a line that extends horizontally beyond the viewable editor area is automatically displayed on the next line.</span></span> <span data-ttu-id="e7d8b-124">При установке этого флажка включается параметр **Отображать символы переноса по словам** и отключается параметр **Разрешить виртуальные пробелы** .</span><span class="sxs-lookup"><span data-stu-id="e7d8b-124">Selecting this check box enables the **Show visual glyphs for word wrap** check box and disables the **Enable virtual space** check box.</span></span>  
  
 <span data-ttu-id="e7d8b-125">**Отображать символы переноса по словам**</span><span class="sxs-lookup"><span data-stu-id="e7d8b-125">**Show visual glyphs for word wrap**</span></span>  
 <span data-ttu-id="e7d8b-126">Если этот флажок установлен, в том месте, где длинная строка была перенесена на следующую строку, отображается индикатор в виде стрелки возврата.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-126">When this check box is selected, a return arrow indicator is displayed where a long line wraps to the next line.</span></span>  
  
 <span data-ttu-id="e7d8b-127">**Применять команды «Вырезать» или «Копировать» к пустым строкам, когда текст не выделен**</span><span class="sxs-lookup"><span data-stu-id="e7d8b-127">**Apply Cut/Copy commands to blank lines when there is no selection**</span></span>  
 <span data-ttu-id="e7d8b-128">Этот флажок задает поведение редактора в случае, когда точка ввода расположена на пустой строке, выбор пуст и запущена команда **Копировать** или **Вырезать**.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-128">This check box sets the behavior of the editor when you place the insertion point on a blank line, select nothing, and then click **Copy** or **Cut**.</span></span>  
  
 <span data-ttu-id="e7d8b-129">Если флажок установлен, то копируется или вырезается пустая строка.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-129">When this check box is selected, the blank line is copied or cut.</span></span> <span data-ttu-id="e7d8b-130">Если затем выбрать **Вставить**, то будет вставлена новая пустая строка.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-130">If you then click **Paste**, a new, blank line is inserted.</span></span>  
  
 <span data-ttu-id="e7d8b-131">Если флажок снят, ничего не копируется и не вырезается.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-131">When this check box is cleared, nothing is copied or cut.</span></span> <span data-ttu-id="e7d8b-132">Если затем выбрать команду **Вставить**, то будет вставлено то, что было скопировано в буфер обмена ранее.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-132">If you then click **Paste**, the content most recently copied is pasted.</span></span> <span data-ttu-id="e7d8b-133">Если ничего не было ранее скопировано, ничего не будет вставлено.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-133">If nothing has been copied previously, nothing is pasted.</span></span>  
  
 <span data-ttu-id="e7d8b-134">Эта установка не оказывает влияния на команды **Копировать** и **Вырезать** в случае, если строка не пуста.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-134">This setting has no effect on **Copy** or **Cut** when a line is not blank.</span></span> <span data-ttu-id="e7d8b-135">Если ничего не выделено, копируется или вырезается вся строка.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-135">If nothing is selected, the entire line is copied or cut.</span></span> <span data-ttu-id="e7d8b-136">Если затем выбрать команду **Вставить**, вставляется текст всей строки, включая символ конца строки.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-136">If you then click **Paste**, the text of the entire line and its end line character are pasted.</span></span>  
  
## <a name="display"></a><span data-ttu-id="e7d8b-137">Отображение</span><span class="sxs-lookup"><span data-stu-id="e7d8b-137">Display</span></span>  
 <span data-ttu-id="e7d8b-138">**Номера строк**</span><span class="sxs-lookup"><span data-stu-id="e7d8b-138">**Line numbers**</span></span>  
 <span data-ttu-id="e7d8b-139">Если установлен этот флажок, рядом с каждой строкой кода отображается номер строки.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-139">When this check box is selected, a line number appears next to each line of code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e7d8b-140">Номера строк не добавляются в код и не выводятся на печать.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-140">These line numbers are not added to your code, and they do not print.</span></span> <span data-ttu-id="e7d8b-141">Они предназначены только для уведомления.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-141">They are for reference only.</span></span>  
  
 <span data-ttu-id="e7d8b-142">**Открывать URL-адреса одним щелчком**</span><span class="sxs-lookup"><span data-stu-id="e7d8b-142">**Enable single-click URL navigation**</span></span>  
 <span data-ttu-id="e7d8b-143">Если этот флажок установлен, то при прохождении курсора над URL-адресом в редакторе указатель курсора принимает форму руки.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-143">When this check box is selected, the cursor changes to a pointing hand as it passes over a URL in the editor.</span></span> <span data-ttu-id="e7d8b-144">Можно щелкнуть URL-адрес для отображения указанной страницы в браузере.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-144">You can click the URL to display the indicated page in your Web browser.</span></span>  
  
 <span data-ttu-id="e7d8b-145">**Панель переходов**</span><span class="sxs-lookup"><span data-stu-id="e7d8b-145">**Navigation bar**</span></span>  
 <span data-ttu-id="e7d8b-146">Этот флажок недоступен.</span><span class="sxs-lookup"><span data-stu-id="e7d8b-146">This check box is unavailable.</span></span>  
  
  
