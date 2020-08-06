---
title: Найти в файлах
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Find in Files dialog box
ms.assetid: bf92770a-33df-43ef-85ad-5a9223649b98
author: rothja
ms.author: jroth
ms.openlocfilehash: a7bd3051817198fb22e2bf7e96393ddf2023b703
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668241"
---
# <a name="find-in-files"></a><span data-ttu-id="862d1-102">Найти в файлах</span><span class="sxs-lookup"><span data-stu-id="862d1-102">Find in Files</span></span>
  <span data-ttu-id="862d1-103">Вкладка **Найти в файлах** окна «Найти и заменить» позволяет найти код, содержащий определенную строку или выражение, в заданном наборе файлов.</span><span class="sxs-lookup"><span data-stu-id="862d1-103">The **Find in Files** tab of the Find and Replace window enables you to search the code of a specified set of files for a string or expression.</span></span> <span data-ttu-id="862d1-104">Обнаруженные совпадения и предпринятые действия перечисляются в окне «Результаты поиска», выбранном в диалоговом окне **Параметры результата**.</span><span class="sxs-lookup"><span data-stu-id="862d1-104">The matches found and actions taken are listed in the Find Results window selected in **Result Options**.</span></span>  
  
 <span data-ttu-id="862d1-105">Кнопки панели инструментов и сочетания клавиш также могут использоваться для открытия диалогового окна **Найти и заменить** .</span><span class="sxs-lookup"><span data-stu-id="862d1-105">Toolbar buttons and shortcut keys are also available to open the **Find and Replace** dialog box.</span></span>  
  
 <span data-ttu-id="862d1-106">В следующих разделах перечисляются списки, доступные на вкладке **Найти в файлах** .</span><span class="sxs-lookup"><span data-stu-id="862d1-106">The sections that follow list controls available on the **Find in Files** tab.</span></span>  
  
## <a name="find-what"></a><span data-ttu-id="862d1-107">Найти</span><span class="sxs-lookup"><span data-stu-id="862d1-107">Find What</span></span>  
 <span data-ttu-id="862d1-108">Эти элементы управления на вкладке **Найти в файлах** позволяют задать строку или выражение для поиска.</span><span class="sxs-lookup"><span data-stu-id="862d1-108">These controls on the **Find in Files** tab enable you to specify the string or expression that will be matched.</span></span>  
  
 <span data-ttu-id="862d1-109">**Найти**</span><span class="sxs-lookup"><span data-stu-id="862d1-109">**Find what**</span></span>  
 <span data-ttu-id="862d1-110">Введите текст для поиска.</span><span class="sxs-lookup"><span data-stu-id="862d1-110">Type the text to search for.</span></span> <span data-ttu-id="862d1-111">Диалоговое окно попытается ввести в поле поиска возможный текст поиска, используя либо текст, который был выделен курсором перед открытием диалогового окна, либо соседний текст, либо текст предыдущего поиска.</span><span class="sxs-lookup"><span data-stu-id="862d1-111">The dialog box attempts to fill in a probable search text, using text selected with the cursor before opening the dialog box, or nearby text, or previously searched-for text.</span></span> <span data-ttu-id="862d1-112">Можно повторно использовать одну из 20 последних строк поиска, выбрав необходимую из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="862d1-112">You can reuse one of the last 20 search strings by selecting it from this drop-down list.</span></span>  
  
 <span data-ttu-id="862d1-113">**[строка с символами-шаблонами]**</span><span class="sxs-lookup"><span data-stu-id="862d1-113">**[string with wildcards]**</span></span>  
 <span data-ttu-id="862d1-114">Если необходимо использовать символы шаблонов, например звездочки (`*`) и вопросительные знаки (`?`) в строке поиска, то следует установить флажок **Использовать** в разделе **Параметры поиска** , а затем выбрать **Шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="862d1-114">If you want to use wildcards such as asterisks (`*`) and question marks (`?`) in your search string, select the **Use** check box under **Find Options** and then click **Wildcards**.</span></span>  
  
 <span data-ttu-id="862d1-115">**[регулярное выражение]**</span><span class="sxs-lookup"><span data-stu-id="862d1-115">**[regular expression]**</span></span>  
 <span data-ttu-id="862d1-116">Чтобы средство поиска воспринимало текст в строке поиска как регулярное выражение, следует установить флажок **Использовать** в разделе **Параметры поиска** , а затем выбрать **Регулярные выражения**.</span><span class="sxs-lookup"><span data-stu-id="862d1-116">To cause the search engine to interpret your search string as a regular expression, select the **Use** check box under **Find Options** and then click **Regular expressions**.</span></span>  
  
 <span data-ttu-id="862d1-117">**Построитель выражений**</span><span class="sxs-lookup"><span data-stu-id="862d1-117">**Expression Builder**</span></span>  
 <span data-ttu-id="862d1-118">Эта треугольная кнопка рядом со строкой **Найти** становится доступной в том случае, если установлен флажок **Использовать** в разделе **Параметры поиска**.</span><span class="sxs-lookup"><span data-stu-id="862d1-118">This triangular button next to the **Find what** box becomes available when the **Use** check box is selected in **Find Options**.</span></span> <span data-ttu-id="862d1-119">Нажмите эту кнопку для отображения списка шаблонов или регулярных выражений в зависимости от выбранных параметров **Использовать** .</span><span class="sxs-lookup"><span data-stu-id="862d1-119">Click this button to display a list of wildcards or regular expressions, depending upon the **Use** option selected.</span></span> <span data-ttu-id="862d1-120">Выбор любого из элементов этого списка добавляет его в строку поиска в поле **Найти** .</span><span class="sxs-lookup"><span data-stu-id="862d1-120">Choosing any item from this list adds it to the **Find what** string.</span></span>  
  
## <a name="look-in"></a><span data-ttu-id="862d1-121">Искать в</span><span class="sxs-lookup"><span data-stu-id="862d1-121">Look In</span></span>  
 <span data-ttu-id="862d1-122">Этот параметр выбирается из раскрывающегося списка **Искать в** и определяет, будут ли команды **Найти в файлах** выполнять поиск только в активных в данный момент файлах или во всех файлах, сохраненных в заданной папке.</span><span class="sxs-lookup"><span data-stu-id="862d1-122">The option chosen from the **Look in** drop-down list determines whether **Find in Files** searches only in currently active files or in all files stored within certain folders.</span></span> <span data-ttu-id="862d1-123">Выберите область поиска из списка, введите путь к папке или нажмите кнопку **Обзор** для открытия диалогового окна **Пользовательский набор каталогов** , которое поможет визуально указать папку с файлами для поиска.</span><span class="sxs-lookup"><span data-stu-id="862d1-123">Select a search scope from the list, type a folder path, or click the **Browse** button to display the **Custom Directory Set Dialog Box** and choose a set of folders to search.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="862d1-124">Если в результате выбора параметра **Искать в** найден файл, изъятый из системы управления исходным кодом, то поиск производится только в версии файла, загруженной на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="862d1-124">If the **Look in** option selected causes you to search a file that you have checked out from source code control, only the version of that file which has been downloaded to your local computer is searched.</span></span>  
  
 <span data-ttu-id="862d1-125">**Look in**</span><span class="sxs-lookup"><span data-stu-id="862d1-125">**Look in**</span></span>  
 <span data-ttu-id="862d1-126">Выберите в списке заранее определенную область поиска или используйте диалоговое окно **Пользовательский набор каталогов** для ввода собственного набора каталогов.</span><span class="sxs-lookup"><span data-stu-id="862d1-126">Select a predefined search scope from this list, or use the **Custom Directory Set** dialog box to enter your own set of directories.</span></span>  
  
 <span data-ttu-id="862d1-127">**Текущий документ**</span><span class="sxs-lookup"><span data-stu-id="862d1-127">**Current Document**</span></span>  
 <span data-ttu-id="862d1-128">Этот параметр доступен, если документ открыт в редакторе.</span><span class="sxs-lookup"><span data-stu-id="862d1-128">This option is available when a document is open in an editor.</span></span> <span data-ttu-id="862d1-129">Будет произведен поиск строки в поле **Найти**только в активном документе.</span><span class="sxs-lookup"><span data-stu-id="862d1-129">It searches only the active document for the string in **Find what**.</span></span>  
  
 <span data-ttu-id="862d1-130">**Все открытые документы**</span><span class="sxs-lookup"><span data-stu-id="862d1-130">**All Open Documents**</span></span>  
 <span data-ttu-id="862d1-131">Поиск производится во всех файлах, открытых в данный момент для редактирования.</span><span class="sxs-lookup"><span data-stu-id="862d1-131">Searches all files currently opened for editing.</span></span>  
  
 <span data-ttu-id="862d1-132">**Текущий проект**</span><span class="sxs-lookup"><span data-stu-id="862d1-132">**Current Project**</span></span>  
 <span data-ttu-id="862d1-133">Поиск производится во всех файлах активного проекта.</span><span class="sxs-lookup"><span data-stu-id="862d1-133">Searches all files in the active project.</span></span>  
  
 <span data-ttu-id="862d1-134">**Все решение**</span><span class="sxs-lookup"><span data-stu-id="862d1-134">**Entire Solution**</span></span>  
 <span data-ttu-id="862d1-135">Поиск производится во всех файлах активного решения.</span><span class="sxs-lookup"><span data-stu-id="862d1-135">Searches all files in the active solution.</span></span>  
  
 <span data-ttu-id="862d1-136">**Включая вложенные папки**</span><span class="sxs-lookup"><span data-stu-id="862d1-136">**Include subfolders**</span></span>  
 <span data-ttu-id="862d1-137">Указывает, что поиск будет произведен во вложенных папках, указанных в поле **Искать в** .</span><span class="sxs-lookup"><span data-stu-id="862d1-137">Specifies that subfolders of the folder specified in **Look in** will be searched.</span></span> <span data-ttu-id="862d1-138">Для этого необходимо задать пользовательский набор каталогов.</span><span class="sxs-lookup"><span data-stu-id="862d1-138">It requires a custom directory set.</span></span>  
  
 <span data-ttu-id="862d1-139">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="862d1-139">**Browse**</span></span>  
 <span data-ttu-id="862d1-140">Нажмите эту кнопку для вызова диалогового окна **Пользовательский набор каталогов** , где можно собрать, отредактировать, сохранить и выбрать именованные наборы каталогов для ввода в поле **Искать в** .</span><span class="sxs-lookup"><span data-stu-id="862d1-140">Click this button to display the **Custom Directory Set** dialog box, where you can assemble, edit, save, and select named sets of directories to enter in the **Look in** box.</span></span>  
  
## <a name="find-options"></a><span data-ttu-id="862d1-141">Параметры поиска</span><span class="sxs-lookup"><span data-stu-id="862d1-141">Find Options</span></span>  
 <span data-ttu-id="862d1-142">Можно развернуть или свернуть раздел **Параметры поиска** .</span><span class="sxs-lookup"><span data-stu-id="862d1-142">You can expand or collapse the **Find Options** section.</span></span> <span data-ttu-id="862d1-143">Следующие параметры могут быть выбраны или отменены.</span><span class="sxs-lookup"><span data-stu-id="862d1-143">The following options can be selected or cleared.</span></span>  
  
 <span data-ttu-id="862d1-144">**Учитывать регистр**</span><span class="sxs-lookup"><span data-stu-id="862d1-144">**Match case**</span></span>  
 <span data-ttu-id="862d1-145">При установке этого флажка окно результатов поиска будет показывать только те строки, которые совпадают с искомой строкой, указанной в поле **Найти** , и которые совпадают по регистру.</span><span class="sxs-lookup"><span data-stu-id="862d1-145">When this check box is selected, the Find Results windows will only display instances of the string specified in **Find what** that are matched both by content and by case.</span></span> <span data-ttu-id="862d1-146">Например, поиск строки **MyObject** с установленным флажком **Учитывать регистр** вернет строки с «MyObject», но не с «myobject» или с «MYOBJECT».</span><span class="sxs-lookup"><span data-stu-id="862d1-146">For example, a search for **MyObject** with the **Match case** check box selected will return "MyObject" but not "myobject" or "MYOBJECT."</span></span>  
  
 <span data-ttu-id="862d1-147">**Слово целиком**</span><span class="sxs-lookup"><span data-stu-id="862d1-147">**Match whole word**</span></span>  
 <span data-ttu-id="862d1-148">Если этот флажок установлен, то окно результатов поиска будет содержать только те строки, которые содержат строку поля **Найти** и только в виде слова целиком.</span><span class="sxs-lookup"><span data-stu-id="862d1-148">When this check box is selected, the Find Results windows will only display instances of the string specified in **Find what** that are matched in complete words.</span></span> <span data-ttu-id="862d1-149">Например, поиск **MyObject** вернет «MyObject», а не «CMyObject» или «MyObjectC».</span><span class="sxs-lookup"><span data-stu-id="862d1-149">For example, a search for **MyObject** will return "MyObject" but not "CMyObject" or "MyObjectC."</span></span>  
  
 <span data-ttu-id="862d1-150">**Использование**</span><span class="sxs-lookup"><span data-stu-id="862d1-150">**Use**</span></span>  
 <span data-ttu-id="862d1-151">Указывает, как воспринимать специальные символы, введенные в текстовые поля **Найти** или **Заменить на** .</span><span class="sxs-lookup"><span data-stu-id="862d1-151">Indicates how to interpret special characters entered in the **Find what** or **Replace with** text boxes.</span></span> <span data-ttu-id="862d1-152">Параметры включают **Шаблоны** и **Регулярные выражения**.</span><span class="sxs-lookup"><span data-stu-id="862d1-152">The options include **Wildcards** and **Regular Expressions**.</span></span>  
  
 <span data-ttu-id="862d1-153">**Regular Expressions**</span><span class="sxs-lookup"><span data-stu-id="862d1-153">**Regular Expressions**</span></span>  
 <span data-ttu-id="862d1-154">Шаблон для поиска соответствия определяется специальными обозначениями.</span><span class="sxs-lookup"><span data-stu-id="862d1-154">Special notations define patterns of text to match.</span></span> <span data-ttu-id="862d1-155">Список см. в разделе [Поиск текста с помощью регулярных выражений](search-text-with-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="862d1-155">For a list, see [Search Text with Regular Expressions](search-text-with-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="862d1-156">**Подстановочные знаки**</span><span class="sxs-lookup"><span data-stu-id="862d1-156">**Wildcards**</span></span>  
 <span data-ttu-id="862d1-157">Такие специальные символы, как звездочки (`*`) и вопросительные знаки (`?`) представляют один или несколько символов.</span><span class="sxs-lookup"><span data-stu-id="862d1-157">Special characters such as asterisks (`*`) and question marks (`?`) represent one or more characters.</span></span> <span data-ttu-id="862d1-158">Список см. в разделе [Поиск текста с символами-шаблонами](search-text-with-wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="862d1-158">For a list, see [Search Text with Wildcards](search-text-with-wildcards.md).</span></span>  
  
 <span data-ttu-id="862d1-159">**Искать в файлах указанных типов**</span><span class="sxs-lookup"><span data-stu-id="862d1-159">**Look at these file types**</span></span>  
 <span data-ttu-id="862d1-160">В этом списке указываются типы файлов, которые будут просмотрены в папках, заданных параметром **Искать в**.</span><span class="sxs-lookup"><span data-stu-id="862d1-160">This list indicates the types of files to search through in the directories specified in **Look in**.</span></span> <span data-ttu-id="862d1-161">Если это поле оставлено пустым, то поиск будет выполнен по всем файлам каталога, заданного полем **Искать в** .</span><span class="sxs-lookup"><span data-stu-id="862d1-161">If this field is left blank, all of the files in the directories specified in **Look in** will be searched.</span></span>  
  
```  
*.[ext]; *.[ext] (manual)  
```  
  
 <span data-ttu-id="862d1-162">Для нахождения файлов конкретного типа введите шаблон «звездочка» (`*`) вместо имени файла, затем точку (`.`) и расширение файла.</span><span class="sxs-lookup"><span data-stu-id="862d1-162">To find files of a particular type, enter an asterisk wildcard (`*`) for the file name, followed by a period (`.`) and the file extension.</span></span> <span data-ttu-id="862d1-163">Для поиска нескольких типов файлов введите несколько строк для поиска, разделяя их точкой с запятой (`;`).</span><span class="sxs-lookup"><span data-stu-id="862d1-163">To find more than one file type, enter multiple search strings separated by a semicolon (`;`).</span></span>  
  
```  
*.[ext]; *.[ext] (from list)  
```  
  
 <span data-ttu-id="862d1-164">Выберите любой элемент списка для ввода заранее заданной строки поиска файлов определенных типов.</span><span class="sxs-lookup"><span data-stu-id="862d1-164">Select any item in the list to enter a preconfigured search string that will find files of particular types.</span></span>  
  
## <a name="result-options"></a><span data-ttu-id="862d1-165">Параметры результата</span><span class="sxs-lookup"><span data-stu-id="862d1-165">Result Options</span></span>  
 <span data-ttu-id="862d1-166">Определяет размещение результатов после нажатия на кнопку **Найти все**.</span><span class="sxs-lookup"><span data-stu-id="862d1-166">Determines the location of the results when you click **Find All**.</span></span> <span data-ttu-id="862d1-167">Раздел **Параметры результата** может быть свернут или развернут.</span><span class="sxs-lookup"><span data-stu-id="862d1-167">You can expand or collapse the **Result Options** section.</span></span> <span data-ttu-id="862d1-168">Следующие параметры могут быть выбраны или отменены.</span><span class="sxs-lookup"><span data-stu-id="862d1-168">The following options can be selected or cleared.</span></span>  
  
 <span data-ttu-id="862d1-169">**Окно "Результаты поиска 1"**</span><span class="sxs-lookup"><span data-stu-id="862d1-169">**Find Results 1 window**</span></span>  
 <span data-ttu-id="862d1-170">Если установлен этот флажок, результаты текущего поиска будут добавлены к содержимому окна «Результаты поиска».</span><span class="sxs-lookup"><span data-stu-id="862d1-170">When this check box is selected, the results of the current search will be appended to the content of the Find Results 1 window.</span></span> <span data-ttu-id="862d1-171">Это окно открывается автоматически и отображает результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="862d1-171">This window opens automatically to display your search results.</span></span> <span data-ttu-id="862d1-172">Чтобы открыть это окно вручную, выберите пункт **Другие окна** в меню **Вид** , а затем пункт **Результаты поиска 1**.</span><span class="sxs-lookup"><span data-stu-id="862d1-172">To open this window manually, click **Other Windows** on the **View** menu and then click **Find Results 1**.</span></span>  
  
 <span data-ttu-id="862d1-173">**Окно «Результаты поиска 2»**</span><span class="sxs-lookup"><span data-stu-id="862d1-173">**Find Results 2 window**</span></span>  
 <span data-ttu-id="862d1-174">Если установлен этот флажок, результаты текущего поиска будут добавлены к содержимому окна «Результаты поиска 2».</span><span class="sxs-lookup"><span data-stu-id="862d1-174">When this check box is selected, the results of the current search will be appended to the content of the Find Results 2 window.</span></span> <span data-ttu-id="862d1-175">Это окно открывается автоматически и отображает результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="862d1-175">This window opens automatically to display your search results.</span></span> <span data-ttu-id="862d1-176">Чтобы открыть это окно вручную, выберите пункт **Другие окна** в меню **Вид** , а затем пункт **Результаты поиска 2**.</span><span class="sxs-lookup"><span data-stu-id="862d1-176">To open this window manually, click **Other Windows** on the **View** menu and then click **Find Results 2**.</span></span>  
  
 <span data-ttu-id="862d1-177">**Отображать только имена файлов**</span><span class="sxs-lookup"><span data-stu-id="862d1-177">**Display file names only**</span></span>  
 <span data-ttu-id="862d1-178">Отображает в окнах «Результаты поиска 1» и «Результаты поиска 2» по одной записи для каждого файла, содержащего совпадения со строкой поиска, вместо одной записи на каждое совпадение.</span><span class="sxs-lookup"><span data-stu-id="862d1-178">Displays one entry per file containing a search match rather than one entry per search match in either the Find Results 1 or Find Results 2 window.</span></span> <span data-ttu-id="862d1-179">Этот параметр не доступен в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="862d1-179">This option is not available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="862d1-180">**Оставить измененные файлы открытыми после выполнения команды «Заменить все»**</span><span class="sxs-lookup"><span data-stu-id="862d1-180">**Keep modified files open after Replace All**</span></span>  
 <span data-ttu-id="862d1-181">Если этот флажок установлен, все файлы, в которых были произведены замены, останутся открытыми, так что изменения можно будет сохранить или отменить.</span><span class="sxs-lookup"><span data-stu-id="862d1-181">When selected, leaves open all files in which replacements have been made, so you can undo or save the changes.</span></span> <span data-ttu-id="862d1-182">Объем доступной памяти может ограничить число файлов, которые останутся открытыми после операции замены.</span><span class="sxs-lookup"><span data-stu-id="862d1-182">Memory constraints might limit the number of files that can remain open after a replace operation.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="862d1-183">Команда **Откат** может использоваться только для файлов, которые остались открытыми для редактирования.</span><span class="sxs-lookup"><span data-stu-id="862d1-183">You can use **Undo** only on files that remain open for editing.</span></span> <span data-ttu-id="862d1-184">Если этот параметр не установлен, файлы, которые не были до этого открыты для редактирования, останутся закрытыми, а команда **Откат** не будет для них доступна.</span><span class="sxs-lookup"><span data-stu-id="862d1-184">If this option is not selected, files that were not already open for editing will remain closed, and no **Undo** option will be available in those files.</span></span>  
  
## <a name="find-and-replace-views"></a><span data-ttu-id="862d1-185">Варианты представлений для поиска и замены</span><span class="sxs-lookup"><span data-stu-id="862d1-185">Find and Replace Views</span></span>  
 <span data-ttu-id="862d1-186">Вкладки сверху окна «Найти и заменить» включают меню **Вид** .</span><span class="sxs-lookup"><span data-stu-id="862d1-186">The tabs at the top of the Find and Replace window include **View** menus.</span></span> <span data-ttu-id="862d1-187">Эти меню позволяют выбрать набор полей для отображения в активной панели.</span><span class="sxs-lookup"><span data-stu-id="862d1-187">These menus enable you to choose a set of fields to display in the active pane.</span></span> <span data-ttu-id="862d1-188">Можно закрепить окно «Найти и заменить» в удобном месте, а затем переключаться между вкладками или между видами для выполнения любой операции поиска и замены.</span><span class="sxs-lookup"><span data-stu-id="862d1-188">You can leave the Find and Replace window docked in a convenient location and then change from tab to tab and view to view to perform any type of find or replace operation.</span></span>  
  
 <span data-ttu-id="862d1-189">**Переключение в режим быстрого поиска**</span><span class="sxs-lookup"><span data-stu-id="862d1-189">**Switch to Quick Find**</span></span>  
 <span data-ttu-id="862d1-190">Эта вкладка панели инструментов заменяет текущее диалоговое окно на диалоговое окно **Быстрый поиск** .</span><span class="sxs-lookup"><span data-stu-id="862d1-190">This toolbar tab changes the dialog box to a **Quick Find** dialog box.</span></span>  
  
 <span data-ttu-id="862d1-191">**Переключение на поиск в файлах**</span><span class="sxs-lookup"><span data-stu-id="862d1-191">**Switch to Find in Files**</span></span>  
 <span data-ttu-id="862d1-192">Эта вкладка панели инструментов заменяет текущее диалоговое окно на диалоговое окно **Поиск в файлах** .</span><span class="sxs-lookup"><span data-stu-id="862d1-192">This toolbar tab changes the dialog box to a **Find in Files** dialog box.</span></span>  
  
 <span data-ttu-id="862d1-193">**Переключение на поиск в символах**</span><span class="sxs-lookup"><span data-stu-id="862d1-193">**Switch to Find Symbols**</span></span>  
 <span data-ttu-id="862d1-194">Эта вкладка панели инструментов заменяет текущее диалоговое окно на диалоговое окно **Поиск в символах** .</span><span class="sxs-lookup"><span data-stu-id="862d1-194">This toolbar tab changes the dialog box to a **Find in Symbols** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="862d1-195">См. также:</span><span class="sxs-lookup"><span data-stu-id="862d1-195">See Also</span></span>  
 [<span data-ttu-id="862d1-196">Сочетания клавиш среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="862d1-196">SQL Server Management Studio Keyboard Shortcuts</span></span>](../../ssms/sql-server-management-studio-keyboard-shortcuts.md)  
