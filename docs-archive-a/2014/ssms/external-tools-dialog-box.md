---
title: Диалоговое окно "Внешние средства" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- adding external tools
- external tools [SQL Server Management Studio]
- SQL Server Management Studio [SQL Server], external tools
ms.assetid: ba797203-24d0-4922-9b97-8ab483f1db14
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5789dc150e45c1a0364b7acc0ea7fda443efcf17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733489"
---
# <a name="external-tools-dialog-box"></a><span data-ttu-id="824d4-102">Диалоговое окно «Внешние средства»</span><span class="sxs-lookup"><span data-stu-id="824d4-102">External Tools Dialog Box</span></span>
  <span data-ttu-id="824d4-103">Используйте диалоговое окно **Внешние инструменты** для добавления внешних инструментов, например SQLCMD или приложения "Блокнот", в меню **Сервис**.</span><span class="sxs-lookup"><span data-stu-id="824d4-103">Use the **External Tools** dialog box to add external tools such as SQLCMD or Notepad to the **Tools** menu.</span></span> <span data-ttu-id="824d4-104">Добавление внешних инструментов позволяет запускать другие приложения во время работы в среде [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="824d4-104">Adding external tools allows you to easily launch other applications while working in the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment.</span></span> <span data-ttu-id="824d4-105">При запуске средств можно указать аргументы и рабочий каталог.</span><span class="sxs-lookup"><span data-stu-id="824d4-105">You can specify arguments and a working directory when launching the tool.</span></span> <span data-ttu-id="824d4-106">Кроме того, результаты работы некоторых средств могут отображаться в окне **Вывод** .</span><span class="sxs-lookup"><span data-stu-id="824d4-106">In addition, the output from some tools can be displayed in the **Output** window.</span></span> <span data-ttu-id="824d4-107">Диалоговое окно **Внешние инструменты** доступно в меню **Сервис** .</span><span class="sxs-lookup"><span data-stu-id="824d4-107">The **External Tools** dialog box is available on the **Tools** menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="824d4-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="824d4-108">Options</span></span>  
 <span data-ttu-id="824d4-109">**Содержимое меню**</span><span class="sxs-lookup"><span data-stu-id="824d4-109">**Menu contents**</span></span>  
 <span data-ttu-id="824d4-110">Перечисляются заголовки элементов, добавляемых в настоящий момент в меню **Сервис** .</span><span class="sxs-lookup"><span data-stu-id="824d4-110">Lists the titles of the items currently added to the **Tools** menu.</span></span> <span data-ttu-id="824d4-111">Для изменения порядка элементов в меню используйте кнопки со стрелками **вверх** и **вниз** .</span><span class="sxs-lookup"><span data-stu-id="824d4-111">Use the **Move Up** and **Move Down** arrows to change the order the items that appear on the menu.</span></span> <span data-ttu-id="824d4-112">Для удаления элемента из меню используйте кнопку **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="824d4-112">Use the **Delete** button to remove an item from the menu.</span></span>  
  
 <span data-ttu-id="824d4-113">**Вверх**</span><span class="sxs-lookup"><span data-stu-id="824d4-113">**Move Up**</span></span>  
 <span data-ttu-id="824d4-114">Перемещает выбранный инструмент вверх по списку, отображаемому в меню **Сервис** .</span><span class="sxs-lookup"><span data-stu-id="824d4-114">Move the selected tool higher in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="824d4-115">**Вниз**</span><span class="sxs-lookup"><span data-stu-id="824d4-115">**Move Down**</span></span>  
 <span data-ttu-id="824d4-116">Перемещает выбранный инструмент вниз по списку, отображаемому в меню **Сервис** .</span><span class="sxs-lookup"><span data-stu-id="824d4-116">Move the selected tool lower in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="824d4-117">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="824d4-117">**Add**</span></span>  
 <span data-ttu-id="824d4-118">Текстовые поля очищаются, чтобы можно было указать новое средство.</span><span class="sxs-lookup"><span data-stu-id="824d4-118">Clear the text boxes so you can specify a new tool.</span></span>  
  
 <span data-ttu-id="824d4-119">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="824d4-119">**Delete**</span></span>  
 <span data-ttu-id="824d4-120">Удаляет инструмент или команду из списка **Содержимое меню** , а также из меню **Сервис** .</span><span class="sxs-lookup"><span data-stu-id="824d4-120">Remove the tool or command from the **Menu Contents** list as well as from the **Tools** menu.</span></span>  
  
 <span data-ttu-id="824d4-121">**Title**</span><span class="sxs-lookup"><span data-stu-id="824d4-121">**Title**</span></span>  
 <span data-ttu-id="824d4-122">Позволяет ввести имя инструмента или команды, появляющихся во вложенном меню **Внешние инструменты** меню **Сервис** .</span><span class="sxs-lookup"><span data-stu-id="824d4-122">Enter the name of the tool or command that will appear on the **External Tools** submenu of the **Tools** menu.</span></span> <span data-ttu-id="824d4-123">Поместите знак амперсанда (&) перед буквой в названии средства, чтобы задать эту букву в сочетании клавиш быстрого вызова.</span><span class="sxs-lookup"><span data-stu-id="824d4-123">Place an ampersand (&) before a letter in the name of the tool to specify that letter as a keyboard shortcut.</span></span> <span data-ttu-id="824d4-124">Например, строка "&SQLCMD" отобразит средство SQLCMD в меню **Сервис**.</span><span class="sxs-lookup"><span data-stu-id="824d4-124">For example, "&SQLCMD" would display SQLCMD on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="824d4-125">**Command**</span><span class="sxs-lookup"><span data-stu-id="824d4-125">**Command**</span></span>  
 <span data-ttu-id="824d4-126">Задается путь к файлу для запуска.</span><span class="sxs-lookup"><span data-stu-id="824d4-126">Specify the path to the file to launch.</span></span>  
  
 <span data-ttu-id="824d4-127">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="824d4-127">**Arguments**</span></span>  
 <span data-ttu-id="824d4-128">Указываются переменные, которые передаются средству при выборе соответствующего пункта в меню.</span><span class="sxs-lookup"><span data-stu-id="824d4-128">Specify the variables that are passed to the tool when the tool is selected on the menu.</span></span> <span data-ttu-id="824d4-129">Аргументы могут задавать значения, передаваемые средству или команде при их запуске.</span><span class="sxs-lookup"><span data-stu-id="824d4-129">Arguments can specify values that are passed to the tool or command when it is launched.</span></span> <span data-ttu-id="824d4-130">Например: значение может определять имя файла или каталога.</span><span class="sxs-lookup"><span data-stu-id="824d4-130">For example, a value can specify a file name or directory.</span></span> <span data-ttu-id="824d4-131">Для выбора аргумента из списка предопределенных аргументов используйте кнопки со стрелками.</span><span class="sxs-lookup"><span data-stu-id="824d4-131">Use the arrow button to select from a list of predefined arguments.</span></span> <span data-ttu-id="824d4-132">Можно добавить несколько аргументов.</span><span class="sxs-lookup"><span data-stu-id="824d4-132">You can add more than one.</span></span> <span data-ttu-id="824d4-133">Полный список стандартных аргументов и их определений см. в разделе [Arguments for External Tools](menu-help/external-tools.md).</span><span class="sxs-lookup"><span data-stu-id="824d4-133">For a complete list of predefined arguments and their definitions, see [Arguments for External Tools](menu-help/external-tools.md).</span></span> <span data-ttu-id="824d4-134">В зависимости от того, какая команда или средство используется, можно также вводить пользовательские аргументы, например переключатели командной строки.</span><span class="sxs-lookup"><span data-stu-id="824d4-134">You can also enter custom arguments (for example, command line switches), depending on the command or tool you use.</span></span>  
  
 <span data-ttu-id="824d4-135">**Использовать окно вывода**</span><span class="sxs-lookup"><span data-stu-id="824d4-135">**Use Output window**</span></span>  
 <span data-ttu-id="824d4-136">Открывает окно вывода среды [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] , чтобы отобразить выходные данные выполняемой команды.</span><span class="sxs-lookup"><span data-stu-id="824d4-136">Opens the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] Output window to display output of the command being run.</span></span> <span data-ttu-id="824d4-137">Не все средства представляют выходные данные в формате, который доступен для отображения в окне вывода.</span><span class="sxs-lookup"><span data-stu-id="824d4-137">Not all tools present output in a format that can be presented in the Output window.</span></span> <span data-ttu-id="824d4-138">Дополнительные сведения см. в разделе [Окно вывода](../relational-databases/scripting/transact-sql-debugger-output-window.md).</span><span class="sxs-lookup"><span data-stu-id="824d4-138">For more information, see [Output Window](../relational-databases/scripting/transact-sql-debugger-output-window.md).</span></span>  
  
 <span data-ttu-id="824d4-139">**Рассматривать вывод как данные в формате Юникод**</span><span class="sxs-lookup"><span data-stu-id="824d4-139">**Treat output as Unicode**</span></span>  
 <span data-ttu-id="824d4-140">Преобразует выходные данные в формат Юникод.</span><span class="sxs-lookup"><span data-stu-id="824d4-140">Interprets the output as Unicode.</span></span>  
  
 <span data-ttu-id="824d4-141">**Исходный каталог**</span><span class="sxs-lookup"><span data-stu-id="824d4-141">**Initial directory**</span></span>  
 <span data-ttu-id="824d4-142">Указывает рабочий каталог средства.</span><span class="sxs-lookup"><span data-stu-id="824d4-142">Specify the working directory of the tool.</span></span> <span data-ttu-id="824d4-143">Для выбора каталогов используйте кнопки со стрелками.</span><span class="sxs-lookup"><span data-stu-id="824d4-143">Use the arrow button to select directories.</span></span> <span data-ttu-id="824d4-144">Можно выбрать несколько каталогов.</span><span class="sxs-lookup"><span data-stu-id="824d4-144">You can select more than one.</span></span>  
  
 <span data-ttu-id="824d4-145">**Запрос аргументов**</span><span class="sxs-lookup"><span data-stu-id="824d4-145">**Prompt for arguments**</span></span>  
 <span data-ttu-id="824d4-146">Отображает диалоговое окно **Аргументы** , чтобы при каждом запуске внешнего инструмента можно было вводить или изменять значения аргументов.</span><span class="sxs-lookup"><span data-stu-id="824d4-146">Display the **Arguments** dialog box to allow you to enter or edit values for the arguments each time you launch the external tool.</span></span>  
  
 <span data-ttu-id="824d4-147">**Закрывать при выходе**</span><span class="sxs-lookup"><span data-stu-id="824d4-147">**Close on exit**</span></span>  
 <span data-ttu-id="824d4-148">При закрытии средства закрывается открытое средством окно.</span><span class="sxs-lookup"><span data-stu-id="824d4-148">Close the window opened by the tool when the tool is closed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="824d4-149">Пример</span><span class="sxs-lookup"><span data-stu-id="824d4-149">Example</span></span>  
 <span data-ttu-id="824d4-150">Ввод следующих значений в диалоговое окно **Внешние инструменты** приведет к созданию пункта меню с названием "DAC", при выборе которого открывается командная строка и выполняется программа **sqlcmd** , использующая выделенное административное соединение.</span><span class="sxs-lookup"><span data-stu-id="824d4-150">Entering the following values in the **External Tools** dialog box will create a menu item labeled "DAC" that when selected, opens a command prompt and runs the **sqlcmd** utility using the dedicated administrator connection.</span></span>  
  
|<span data-ttu-id="824d4-151">Box</span><span class="sxs-lookup"><span data-stu-id="824d4-151">Box</span></span>|<span data-ttu-id="824d4-152">Значение</span><span class="sxs-lookup"><span data-stu-id="824d4-152">Value</span></span>|  
|---------|-----------|  
|<span data-ttu-id="824d4-153">**Title**</span><span class="sxs-lookup"><span data-stu-id="824d4-153">**Title**</span></span>|<span data-ttu-id="824d4-154">DAC</span><span class="sxs-lookup"><span data-stu-id="824d4-154">DAC</span></span>|  
|<span data-ttu-id="824d4-155">**Command**</span><span class="sxs-lookup"><span data-stu-id="824d4-155">**Command**</span></span>|[!INCLUDE[ssInstallPath](../includes/ssinstallpath-md.md)]<span data-ttu-id="824d4-156">Tools\Binn\SQLCMD.exe</span><span class="sxs-lookup"><span data-stu-id="824d4-156">Tools\Binn\SQLCMD.exe</span></span>|  
|<span data-ttu-id="824d4-157">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="824d4-157">**Arguments**</span></span>|<span data-ttu-id="824d4-158">-A</span><span class="sxs-lookup"><span data-stu-id="824d4-158">-A</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="824d4-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="824d4-159">See Also</span></span>  
 <span data-ttu-id="824d4-160">[Аргументы для внешних средств](menu-help/external-tools.md) </span><span class="sxs-lookup"><span data-stu-id="824d4-160">[Arguments for External Tools](menu-help/external-tools.md) </span></span>  
 [<span data-ttu-id="824d4-161">Общие элементы пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="824d4-161">General User Interface Elements</span></span>](general-user-interface-elements.md)  
  
  
