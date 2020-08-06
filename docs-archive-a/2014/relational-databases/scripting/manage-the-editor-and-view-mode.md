---
title: Управление режимами редактирования и просмотра
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Query Editor [SQL Server Management Studio], managing window behavior
- workbench view modes [SQL Server Management Studio]
- full screen mode [SQL Server Management Studio]
- fonts [SQL Server Management Studio]
- word wraps [SQL Server Management Studio]
- virtual space mode [SQL Server Management Studio]
- splitting document views
- displaying line numbers
- view modes [SQL Server Management Studio]
ms.assetid: 25c58a14-9f94-4296-9770-7d84c6bc3969
author: rothja
ms.author: jroth
ms.openlocfilehash: 36788b1fe831a6c15c4aa0668d1759c088fcaa73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667684"
---
# <a name="manage-the-editor-and-view-mode"></a><span data-ttu-id="e54fc-102">Управление режимами редактирования и просмотра</span><span class="sxs-lookup"><span data-stu-id="e54fc-102">Manage the Editor and View Mode</span></span>
  <span data-ttu-id="e54fc-103">Редактор позволяет управлять способами просмотра кода.</span><span class="sxs-lookup"><span data-stu-id="e54fc-103">The Editor gives you a number of ways to control the view of your code.</span></span>  
  
## <a name="changing-the-view-mode"></a><span data-ttu-id="e54fc-104">Изменение режима просмотра</span><span class="sxs-lookup"><span data-stu-id="e54fc-104">Changing the View Mode</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="e54fc-105">имеется режим просмотра **Документы с вкладками**, позволяющий открыть одновременно несколько редакторов и документов и переключаться между ними с помощью вкладок в верхней части окна редактора.</span><span class="sxs-lookup"><span data-stu-id="e54fc-105">features a view mode called **Tabbed Documents**, which allows you to open multiple editors and documents simultaneously and access them through tabs at the top of the Editor.</span></span> <span data-ttu-id="e54fc-106">Также можно открыть среду [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] в режиме интерфейса MDI (Multiple Document Interface), объединяющем окна без вкладок и позволяющем сворачивать окна, располагать их рядом и т. д.</span><span class="sxs-lookup"><span data-stu-id="e54fc-106">You can alternatively open the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] environment in Multiple Document Interface (MDI) mode, which joins windows without the tabs, and allows each window to be tiled, minimized, and so on.</span></span>  
  
#### <a name="to-switch-between-view-modes"></a><span data-ttu-id="e54fc-107">Переключение между режимами просмотра</span><span class="sxs-lookup"><span data-stu-id="e54fc-107">To switch between view modes</span></span>  
  
1.  <span data-ttu-id="e54fc-108">В меню **Сервис** выберите пункт **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="e54fc-108">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="e54fc-109">Перейдите на вкладку **Среда**,</span><span class="sxs-lookup"><span data-stu-id="e54fc-109">Click **Environment**.</span></span> <span data-ttu-id="e54fc-110">Выберите **Общие**.</span><span class="sxs-lookup"><span data-stu-id="e54fc-110">Click **General**.</span></span>  
  
3.  <span data-ttu-id="e54fc-111">Выберите **Документы с вкладками** или **Среда MDI**.</span><span class="sxs-lookup"><span data-stu-id="e54fc-111">Click **Tabbed documents** or **MDI environment**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e54fc-112">Изменения вступят в силу только после перезапуска [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e54fc-112">The changes will not take effect until [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is restarted.</span></span>  
  
## <a name="splitting-the-view"></a><span data-ttu-id="e54fc-113">Разделение представления</span><span class="sxs-lookup"><span data-stu-id="e54fc-113">Splitting the View</span></span>  
 <span data-ttu-id="e54fc-114">Окно редактора можно разбить на две части, чтобы облегчить изменение.</span><span class="sxs-lookup"><span data-stu-id="e54fc-114">An Editor window can be split into two separate parts for easier editing.</span></span>  
  
#### <a name="to-split-a-window"></a><span data-ttu-id="e54fc-115">Как разбить окно</span><span class="sxs-lookup"><span data-stu-id="e54fc-115">To split a window</span></span>  
  
1.  <span data-ttu-id="e54fc-116">Щелкните вешку разбивки, расположенную над вертикальной полосой прокрутки.</span><span class="sxs-lookup"><span data-stu-id="e54fc-116">Click the splitter bar (located above the scroll bar).</span></span>  
  
2.  <span data-ttu-id="e54fc-117">Перетащите вешку разбивки вниз.</span><span class="sxs-lookup"><span data-stu-id="e54fc-117">Drag the splitter bar downward.</span></span>  
  
3.  <span data-ttu-id="e54fc-118">Чтобы вернуться к отображению в одной панели, дважды щелкните линию разбивки, находящуюся между двумя областями.</span><span class="sxs-lookup"><span data-stu-id="e54fc-118">To go back to a single pane, double-click the splitter bar dividing the two panes.</span></span>  
  
 <span data-ttu-id="e54fc-119">Новая панель содержит тот же документ, и любые изменения, сделанные в одной из панелей, немедленно появляются и в другой панели, если она отображает ту же часть документа.</span><span class="sxs-lookup"><span data-stu-id="e54fc-119">The new pane contains the same document, and any changes made to one pane are reflected in the other pane as long as that pane displays the same place in the document.</span></span>  
  
## <a name="word-wrap"></a><span data-ttu-id="e54fc-120">Перенос по словам</span><span class="sxs-lookup"><span data-stu-id="e54fc-120">Word Wrap</span></span>  
 <span data-ttu-id="e54fc-121">Если включить перенос по словам, горизонтальная полоса прокрутки исчезает, а строки кода, длина которых превышает ширину окна редактора, вместо продолжения за пределы окна автоматически переносятся на следующую строку.</span><span class="sxs-lookup"><span data-stu-id="e54fc-121">When you activate Word Wrap, the horizontal scrollbar is removed and lines of code that exceed the width of the Editor's window size automatically wraps to the next displayed line rather than scrolling off the side of the window.</span></span>  
  
#### <a name="to-activate-word-wrap"></a><span data-ttu-id="e54fc-122">Включение переноса по словам</span><span class="sxs-lookup"><span data-stu-id="e54fc-122">To activate word wrap</span></span>  
  
1.  <span data-ttu-id="e54fc-123">В меню **Сервис** выберите пункт **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="e54fc-123">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="e54fc-124">Щелкните **Текстовый редактор**.</span><span class="sxs-lookup"><span data-stu-id="e54fc-124">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="e54fc-125">Откройте папку соответствующего языка (или папку **Все языки** , чтобы изменения затронули все языки).</span><span class="sxs-lookup"><span data-stu-id="e54fc-125">Open the appropriate language folder (or **All Languages** to affect all languages).</span></span>  
  
4.  <span data-ttu-id="e54fc-126">Выберите **Перенос по словам**.</span><span class="sxs-lookup"><span data-stu-id="e54fc-126">Select **Word wrap**.</span></span>  
  
## <a name="enabling-virtual-space-mode"></a><span data-ttu-id="e54fc-127">Включение режима виртуального пространства</span><span class="sxs-lookup"><span data-stu-id="e54fc-127">Enabling Virtual Space Mode</span></span>  
 <span data-ttu-id="e54fc-128">В режиме **Виртуальное пространство** редактор действует так, будто пространство после конца каждой строки заполнено бесконечным количеством пробелов, позволяя строкам кода продолжаться за край видимой области экрана.</span><span class="sxs-lookup"><span data-stu-id="e54fc-128">In **Virtual Space** mode, the Editor acts as if the space past the end of each line is filled with an infinite number of spaces, allowing code lines to continue off the side of the visible screen area.</span></span>  
  
#### <a name="to-enable-virtual-space-mode"></a><span data-ttu-id="e54fc-129">Включение режима виртуального пространства</span><span class="sxs-lookup"><span data-stu-id="e54fc-129">To enable Virtual Space mode</span></span>  
  
1.  <span data-ttu-id="e54fc-130">В меню **Сервис** выберите пункт **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="e54fc-130">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="e54fc-131">Щелкните **Текстовый редактор**.</span><span class="sxs-lookup"><span data-stu-id="e54fc-131">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="e54fc-132">Откройте папку соответствующего языка (или папку **Все языки** , чтобы изменения затронули все языки).</span><span class="sxs-lookup"><span data-stu-id="e54fc-132">Open the appropriate language folder (or **All Languages** to affect all languages).</span></span>  
  
4.  <span data-ttu-id="e54fc-133">Выберите **Разрешить виртуальное пространство**.</span><span class="sxs-lookup"><span data-stu-id="e54fc-133">Select **Enable virtual space**.</span></span>  
  
 <span data-ttu-id="e54fc-134">Когда режим виртуального пространства не включен, курсор переходит с конца одной строки на первый символ следующей строки и наоборот.</span><span class="sxs-lookup"><span data-stu-id="e54fc-134">When Virtual Space mode is not enabled, the cursor wraps from the end of one line to the first character of the next line and vice-versa.</span></span>  
  
## <a name="displaying-line-numbers"></a><span data-ttu-id="e54fc-135">отображение номеров строк</span><span class="sxs-lookup"><span data-stu-id="e54fc-135">Displaying Line Numbers</span></span>  
 <span data-ttu-id="e54fc-136">В редакторе можно включить нумерацию строк кода.</span><span class="sxs-lookup"><span data-stu-id="e54fc-136">You can turn on line numbering in your code.</span></span> <span data-ttu-id="e54fc-137">Номера строк полезны при перемещении по коду.</span><span class="sxs-lookup"><span data-stu-id="e54fc-137">Line numbers are useful for navigating code.</span></span> <span data-ttu-id="e54fc-138">Дополнительные сведения о группах и пользователях см. в разделе [Перемещение по коду и тексту](navigate-code-and-text.md).</span><span class="sxs-lookup"><span data-stu-id="e54fc-138">For more information, see [Navigate Code and Text](navigate-code-and-text.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e54fc-139">Включение нумерации строк не приводит к печати номеров строк при печати документа.</span><span class="sxs-lookup"><span data-stu-id="e54fc-139">Turning on line numbering does not mean that the document will print with line numbers.</span></span> <span data-ttu-id="e54fc-140">Чтобы номера строк печатались, необходимо установить флажок **Номера строк** в окне **Параметры страницы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="e54fc-140">For line numbers to print, you must select the **Line numbers** check box in the **Page Setup** command on the **File** menu.</span></span>  
  
#### <a name="to-display-line-numbers-in-code"></a><span data-ttu-id="e54fc-141">Отображение номеров строк кода</span><span class="sxs-lookup"><span data-stu-id="e54fc-141">To display line numbers in code</span></span>  
  
1.  <span data-ttu-id="e54fc-142">В меню **Сервис** выберите пункт **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="e54fc-142">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="e54fc-143">Щелкните **Текстовый редактор**.</span><span class="sxs-lookup"><span data-stu-id="e54fc-143">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="e54fc-144">Щелкните **Все языки**.</span><span class="sxs-lookup"><span data-stu-id="e54fc-144">Click **All Languages**.</span></span>  
  
4.  <span data-ttu-id="e54fc-145">Выберите **Общие**.</span><span class="sxs-lookup"><span data-stu-id="e54fc-145">Click **General**.</span></span>  
  
5.  <span data-ttu-id="e54fc-146">Выберите **Номера строк**.</span><span class="sxs-lookup"><span data-stu-id="e54fc-146">Select **Line numbers**.</span></span>  
  
 <span data-ttu-id="e54fc-147">Чтобы включить нумерацию строк только для некоторых языков программирования, выберите **Номера строк** в соответствующей папке.</span><span class="sxs-lookup"><span data-stu-id="e54fc-147">To specify line numbering for only some programming languages, select **Line Numbers** in the appropriate folder.</span></span>  
  
## <a name="enabling-full-screen-mode"></a><span data-ttu-id="e54fc-148">Включение полноэкранного режима</span><span class="sxs-lookup"><span data-stu-id="e54fc-148">Enabling Full Screen Mode</span></span>  
 <span data-ttu-id="e54fc-149">Включив полноэкранный режим, можно скрыть окна всех средств и просматривать лишь окна документов.</span><span class="sxs-lookup"><span data-stu-id="e54fc-149">You can choose to hide all tool windows and view only document windows by enabling Full Screen mode.</span></span>  
  
#### <a name="to-enable-full-screen-mode"></a><span data-ttu-id="e54fc-150">Включение полноэкранного режима</span><span class="sxs-lookup"><span data-stu-id="e54fc-150">To enable Full Screen mode</span></span>  
  
1.  <span data-ttu-id="e54fc-151">Нажмите клавиши ALT + SHIFT + ВВОД, чтобы включить или выключить полноэкранный режим.</span><span class="sxs-lookup"><span data-stu-id="e54fc-151">Press ALT+SHIFT+ENTER to toggle Full Screen mode.</span></span>  
  
## <a name="using-auto-hide-all"></a><span data-ttu-id="e54fc-152">Использование автоматического скрытия всех окон</span><span class="sxs-lookup"><span data-stu-id="e54fc-152">Using Auto Hide All</span></span>  
  
#### <a name="to-hide-all-the-tool-windows-at-once"></a><span data-ttu-id="e54fc-153">Как сразу скрыть окна всех средств</span><span class="sxs-lookup"><span data-stu-id="e54fc-153">To hide all the tool windows at once</span></span>  
  
1.  <span data-ttu-id="e54fc-154">В меню **Окно** выберите **Скрыть все автоматически** .</span><span class="sxs-lookup"><span data-stu-id="e54fc-154">Select **Auto Hide All** on the **Window** menu.</span></span>  
  
  
