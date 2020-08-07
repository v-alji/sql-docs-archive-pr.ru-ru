---
title: Внешние инструменты | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- External Tools dialog box
ms.assetid: d7dae88f-0781-4162-96cd-d3a3a4d82035
author: stevestein
ms.author: sstein
ms.openlocfilehash: a39cd0d139e81c02a7d2a58fae4e74221be7f78e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732253"
---
# <a name="external-tools"></a><span data-ttu-id="2ba27-102">Внешние инструменты</span><span class="sxs-lookup"><span data-stu-id="2ba27-102">External Tools</span></span>
  <span data-ttu-id="2ba27-103">С помощью этого диалогового окна можно добавить в меню **Сервис** внешние инструменты, такие как диспетчер конфигурации SQL Server или "Блокнот".</span><span class="sxs-lookup"><span data-stu-id="2ba27-103">Use this dialog box to add external tools, such as SQL Server Configuration Manager or Notepad, to the **Tools** menu.</span></span> <span data-ttu-id="2ba27-104">Добавление внешних средств позволяет легко запускать другие приложения во время работы в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ba27-104">Adding external tools allows you to easily launch other applications while working in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2ba27-105">При запуске средств можно указать аргументы и рабочий каталог.</span><span class="sxs-lookup"><span data-stu-id="2ba27-105">You can specify arguments and a working directory when launching the tool.</span></span> <span data-ttu-id="2ba27-106">Кроме того, выходные данные некоторых средств могут отображаться в окне «Вывод».</span><span class="sxs-lookup"><span data-stu-id="2ba27-106">In addition, the outputs from some tools can be displayed in the Output window.</span></span> <span data-ttu-id="2ba27-107">Диалоговое окно **Внешние инструменты** доступно в меню **Сервис** .</span><span class="sxs-lookup"><span data-stu-id="2ba27-107">The **External Tools** dialog box is available on the **Tools** menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2ba27-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="2ba27-108">Options</span></span>  
 <span data-ttu-id="2ba27-109">**Содержимое меню**</span><span class="sxs-lookup"><span data-stu-id="2ba27-109">**Menu Contents**</span></span>  
 <span data-ttu-id="2ba27-110">Перечисляются заголовки элементов, добавляемых в настоящий момент в меню **Сервис** .</span><span class="sxs-lookup"><span data-stu-id="2ba27-110">Lists the titles of the items currently added to the **Tools** menu.</span></span> <span data-ttu-id="2ba27-111">Для изменения порядка элементов в меню используйте кнопки со стрелками **вверх** и **вниз** .</span><span class="sxs-lookup"><span data-stu-id="2ba27-111">Use the **Move Up** and **Move Down** arrows to change the order the items that appear on the menu.</span></span> <span data-ttu-id="2ba27-112">Для удаления элемента из меню используйте кнопку **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="2ba27-112">Use the **Delete** button to remove an item from the menu.</span></span>  
  
 <span data-ttu-id="2ba27-113">**Вверх**</span><span class="sxs-lookup"><span data-stu-id="2ba27-113">**Move Up**</span></span>  
 <span data-ttu-id="2ba27-114">Перемещает выбранный инструмент вверх по списку, отображаемому в меню **Сервис** .</span><span class="sxs-lookup"><span data-stu-id="2ba27-114">Move the selected tool higher in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="2ba27-115">**Вниз**</span><span class="sxs-lookup"><span data-stu-id="2ba27-115">**Move Down**</span></span>  
 <span data-ttu-id="2ba27-116">Перемещает выбранный инструмент вниз по списку, отображаемому в меню **Сервис** .</span><span class="sxs-lookup"><span data-stu-id="2ba27-116">Move the selected tool lower in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="2ba27-117">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="2ba27-117">**Add**</span></span>  
 <span data-ttu-id="2ba27-118">Текстовые поля очищаются, чтобы можно было указать новое средство.</span><span class="sxs-lookup"><span data-stu-id="2ba27-118">Clear the text boxes so you can specify a new tool.</span></span>  
  
 <span data-ttu-id="2ba27-119">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="2ba27-119">**Delete**</span></span>  
 <span data-ttu-id="2ba27-120">Удаляет инструмент или команду из списка **Содержимое меню** , а также из меню **Сервис** .</span><span class="sxs-lookup"><span data-stu-id="2ba27-120">Remove the tool or command from the **Menu Contents** list as well as from the **Tools** menu.</span></span>  
  
 <span data-ttu-id="2ba27-121">**Title**</span><span class="sxs-lookup"><span data-stu-id="2ba27-121">**Title**</span></span>  
 <span data-ttu-id="2ba27-122">Имя инструмента или команды, появляющихся во вложенном меню **Внешние инструменты** меню **Сервис** .</span><span class="sxs-lookup"><span data-stu-id="2ba27-122">The name of the tool or command that will appear on the **External Tools** submenu of the **Tools** menu.</span></span> <span data-ttu-id="2ba27-123">Поместите символ амперсанд перед буквой в имени средства, чтобы использовать эту букву в качестве клавиши быстрого вызова для этого средства.</span><span class="sxs-lookup"><span data-stu-id="2ba27-123">Place an ampersand before a letter in the name of the tool to use that letter as an accelerator key for the tool.</span></span> <span data-ttu-id="2ba27-124">Например: указание `&Spy++` приводит к отображению пункта **Spy++** в меню **Сервис** .</span><span class="sxs-lookup"><span data-stu-id="2ba27-124">For example, `&Spy++` would display **Spy++** on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="2ba27-125">**Command**</span><span class="sxs-lookup"><span data-stu-id="2ba27-125">**Command**</span></span>  
 <span data-ttu-id="2ba27-126">Указывает путь к файлам с расширениями EXE, COM, PIF, BAT, CMD или к другим файлам, которые планируется запускать.</span><span class="sxs-lookup"><span data-stu-id="2ba27-126">Specify the path to the .exe, .com, .pif, .bat, .cmd, or other file that you intend to launch.</span></span> <span data-ttu-id="2ba27-127">Если установлен флажок `.bat`Использовать окно вывода `.com`, можно просмотреть вывод из файлов типа **,** и других файлов в окне "Вывод".</span><span class="sxs-lookup"><span data-stu-id="2ba27-127">The output from `.bat`, `.com`, and other files can be viewed in the Output window if you select the **Use output window** check box.</span></span>  
  
 <span data-ttu-id="2ba27-128">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="2ba27-128">**Arguments**</span></span>  
 <span data-ttu-id="2ba27-129">Указываются переменные, которые передаются средству при выборе соответствующего пункта в меню.</span><span class="sxs-lookup"><span data-stu-id="2ba27-129">Specify the variables that are passed to the tool when the tool is selected on the menu.</span></span> <span data-ttu-id="2ba27-130">Аргументы могут задавать значения, передаваемые средству или команде при их запуске.</span><span class="sxs-lookup"><span data-stu-id="2ba27-130">Arguments can specify values that are passed to the tool or command when it is launched.</span></span> <span data-ttu-id="2ba27-131">Например: значение может определять имя файла или каталога.</span><span class="sxs-lookup"><span data-stu-id="2ba27-131">For example, a value can specify a file name or directory.</span></span> <span data-ttu-id="2ba27-132">Используйте **кнопку со стрелкой** , чтобы сделать выбор из списка стандартных аргументов.</span><span class="sxs-lookup"><span data-stu-id="2ba27-132">Use the **Arrow** button to select from a list of predefined arguments.</span></span> <span data-ttu-id="2ba27-133">Можно добавить несколько аргументов.</span><span class="sxs-lookup"><span data-stu-id="2ba27-133">You can add more than one.</span></span> <span data-ttu-id="2ba27-134">Полный список стандартных аргументов и их определений см. в разделе [Arguments for External Tools](external-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2ba27-134">For a complete list of predefined arguments and their definitions, see [Arguments for External Tools](external-tools.md).</span></span> <span data-ttu-id="2ba27-135">В зависимости от того, какая команда или средство используется, можно также ввести специальные аргументы, например ключи командной строки.</span><span class="sxs-lookup"><span data-stu-id="2ba27-135">You can also enter custom arguments (command-prompt switches, for example), depending on the command or tool you use.</span></span>  
  
 <span data-ttu-id="2ba27-136">**Исходный каталог**</span><span class="sxs-lookup"><span data-stu-id="2ba27-136">**Initial directory**</span></span>  
 <span data-ttu-id="2ba27-137">Указывает рабочий каталог средства.</span><span class="sxs-lookup"><span data-stu-id="2ba27-137">Specify the working directory of the tool.</span></span> <span data-ttu-id="2ba27-138">Чтобы выбрать каталоги, используйте кнопку со **стрелкой** .</span><span class="sxs-lookup"><span data-stu-id="2ba27-138">Use the **Arrow** button to select directories.</span></span> <span data-ttu-id="2ba27-139">Можно выбрать несколько каталогов.</span><span class="sxs-lookup"><span data-stu-id="2ba27-139">You can select more than one.</span></span>  
  
 <span data-ttu-id="2ba27-140">**Use output Window**</span><span class="sxs-lookup"><span data-stu-id="2ba27-140">**Use output Window**</span></span>  
 <span data-ttu-id="2ba27-141">Указывает, отображать ли результаты работы средств в окне «Выход».</span><span class="sxs-lookup"><span data-stu-id="2ba27-141">Specify whether or not results from the tool are displayed in the Output window.</span></span> <span data-ttu-id="2ba27-142">Этот параметр доступен только для таких файлов, как BAT и COM, которые обычно выводят данные в окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="2ba27-142">This option is only available for files, such as .bat and .com files, that normally display output in the command prompt window.</span></span> <span data-ttu-id="2ba27-143">Если этот параметр включен, при работе со средством облегчается управление окнами.</span><span class="sxs-lookup"><span data-stu-id="2ba27-143">When enabled, this option eases window management when you are following the progress of a tool.</span></span>  
  
 <span data-ttu-id="2ba27-144">**Запрос аргументов**</span><span class="sxs-lookup"><span data-stu-id="2ba27-144">**Prompt for arguments**</span></span>  
 <span data-ttu-id="2ba27-145">Отображается диалоговое окно **Аргументы** , позволяющее пользователю вводить или редактировать значения аргументов при каждом запуске внешнего инструмента.</span><span class="sxs-lookup"><span data-stu-id="2ba27-145">Display the **Arguments** dialog box to enable you to enter or edit values for the arguments each time you launch the external tool.</span></span>  
  
 <span data-ttu-id="2ba27-146">**Рассматривать вывод как данные в формате Юникод**</span><span class="sxs-lookup"><span data-stu-id="2ba27-146">**Treat output as Unicode**</span></span>  
 <span data-ttu-id="2ba27-147">Позволяет отображать данные в формате Юникода в окне «Вывод».</span><span class="sxs-lookup"><span data-stu-id="2ba27-147">Allow the Output window to accept Unicode.</span></span>  
  
 <span data-ttu-id="2ba27-148">**Закрыть при выходе**</span><span class="sxs-lookup"><span data-stu-id="2ba27-148">**Close On Exit**</span></span>  
 <span data-ttu-id="2ba27-149">При закрытии средства закрывается открытое средством окно.</span><span class="sxs-lookup"><span data-stu-id="2ba27-149">Close the window opened by the tool when the tool is closed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ba27-150">Пример</span><span class="sxs-lookup"><span data-stu-id="2ba27-150">Example</span></span>  
  
#### <a name="to-add-sql-server-configuration-manager-to-the-tools-menu"></a><span data-ttu-id="2ba27-151">Добавление диспетчера конфигурации SQL Server в меню "Сервис"</span><span class="sxs-lookup"><span data-stu-id="2ba27-151">To add SQL Server Configuration Manager to the Tools menu</span></span>  
  
1.  <span data-ttu-id="2ba27-152">В меню **Сервис** выберите пункт **Внешние инструменты**.</span><span class="sxs-lookup"><span data-stu-id="2ba27-152">On the **Tools** menu, click **External Tools**.</span></span>  
  
2.  <span data-ttu-id="2ba27-153">В поле **Заголовок** введите **Диспетчер конфигурации SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="2ba27-153">In the **Title** box, type **SQL Server Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="2ba27-154">В поле **команда** введите путь к [!INCLUDE[msCoName](../../includes/msconame-md.md)] исполняемому файлу консоли управления, например`C:\WINNT\system32\mmc.exe`</span><span class="sxs-lookup"><span data-stu-id="2ba27-154">In the **Command** box, type the path to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console executable, such as `C:\WINNT\system32\mmc.exe`</span></span>  
  
4.  <span data-ttu-id="2ba27-155">В поле **аргументы** введите путь к файлу. msc, например`"C:\WINNT\system32\SQLServerManager.msc"`</span><span class="sxs-lookup"><span data-stu-id="2ba27-155">In the **Arguments** box, type the path to the .msc file, such as `"C:\WINNT\system32\SQLServerManager.msc"`</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2ba27-156">Чтобы проверить расположение соответствующих файлов на компьютере, просмотрите свойства ярлыка среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] в меню **Пуск** .</span><span class="sxs-lookup"><span data-stu-id="2ba27-156">View the properties of the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] shortcut on the **Start** menu to confirm the location of the files on your computer.</span></span>  
