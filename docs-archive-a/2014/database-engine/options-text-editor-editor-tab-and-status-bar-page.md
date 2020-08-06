---
title: 'Параметры (текстовый редактор: вкладка редактора и страница строки состояния) | Документация Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqleditors.editorcontextsettings
- VS.ToolsOptionsPages.Text_Editor.EditorTabAndStatusBar
ms.assetid: e4815678-7885-4631-878f-c6a2b857ee05
author: rothja
ms.author: jroth
ms.openlocfilehash: 920b7d48b5f7a2472a521af21c8217b1adba486a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667392"
---
# <a name="options-text-editor-editor-tab-and-status-bar-page"></a><span data-ttu-id="b5482-102">Параметры (страница "Текстовый редактор" — "Вкладка редактора и строка состояния")</span><span class="sxs-lookup"><span data-stu-id="b5482-102">Options (Text Editor: Editor Tab and Status Bar Page)</span></span>
  <span data-ttu-id="b5482-103">На странице **Вкладка редактора и строка состояния** можно настроить сведения, которые показываются в редакторах запросов [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b5482-103">The **Editor Tab and Status Bar Page** lets you customize the information displayed by the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] Query Editors.</span></span> <span data-ttu-id="b5482-104">Можно указать уровень сведений, отображаемых на вкладке и в строке состояния редактора запросов, а также место расположения строки состояния: вверху или внизу окна редактора.</span><span class="sxs-lookup"><span data-stu-id="b5482-104">You can specify the level of information displayed in the tab and status bar of the Query Editor window, and whether the status bar appears at the top or bottom of the editor window.</span></span>  
  
## <a name="option-settings-by-editor"></a><span data-ttu-id="b5482-105">Параметры, задаваемые с помощью редактора</span><span class="sxs-lookup"><span data-stu-id="b5482-105">Option Settings by Editor</span></span>  
 <span data-ttu-id="b5482-106">Вкладка редактора и строка состояния доступны во всех редакторах среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , однако они отличаются разным уровнем функциональности.</span><span class="sxs-lookup"><span data-stu-id="b5482-106">The editor tab and the status bar are available in all of the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] editors, but have different levels of functionality.</span></span>  
  
 <span data-ttu-id="b5482-107">Редактор запросов Database Engine может подключаться к группе серверов, в этом случае он открывает соединения со всеми экземплярами в группе серверов и может одновременно запускать один и тот же запрос для каждого соединения.</span><span class="sxs-lookup"><span data-stu-id="b5482-107">The Database Engine Query Editor can connect to a server group, in which case it opens connections to all the instances in the Server Group and can simultaneously run the same query on each connection.</span></span> <span data-ttu-id="b5482-108">В этом диалоговом окне можно указать, что строка состояния будет иметь другой цвет при подключении к нескольким экземплярам вместо одного. Изменить параметры результатов для нескольких серверов можно на странице [Параметры (результаты запроса/SQL Server/многосерверные)](../../2014/database-engine/options-query-results-sql-server-multi-server.md).</span><span class="sxs-lookup"><span data-stu-id="b5482-108">You can use this dialog to specify that the status bar has different colors when connected to multiple instances rather than one instance.To change the multi-server results options, use the [Options (Query Results/SQL Server/Multi-Server)](../../2014/database-engine/options-query-results-sql-server-multi-server.md) page.</span></span>  
  
## <a name="status-bar-content"></a><span data-ttu-id="b5482-109">Содержимое строки состояния</span><span class="sxs-lookup"><span data-stu-id="b5482-109">Status Bar Content</span></span>  
 <span data-ttu-id="b5482-110">Определяет сведения, которые отображаются в строке состояния редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="b5482-110">Specifies the information that appears in the Query Editor status bar.</span></span>  
  
 <span data-ttu-id="b5482-111">**Отображать время выполнения**</span><span class="sxs-lookup"><span data-stu-id="b5482-111">**Display execution time**</span></span>  
 <span data-ttu-id="b5482-112">Включает время выполнения скрипта.</span><span class="sxs-lookup"><span data-stu-id="b5482-112">Includes the script execution time.</span></span> <span data-ttu-id="b5482-113">Доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="b5482-113">The settings are as follows:</span></span>  
  
 <span data-ttu-id="b5482-114">**None**</span><span class="sxs-lookup"><span data-stu-id="b5482-114">**None**</span></span>  
 <span data-ttu-id="b5482-115">В строке состояния не отображаются сведения о времени.</span><span class="sxs-lookup"><span data-stu-id="b5482-115">The status bar displays no time information.</span></span>  
  
 <span data-ttu-id="b5482-116">**END**</span><span class="sxs-lookup"><span data-stu-id="b5482-116">**End**</span></span>  
 <span data-ttu-id="b5482-117">В строке состояния отображается текущее время, пока выполняется скрипт.</span><span class="sxs-lookup"><span data-stu-id="b5482-117">The status bar displays the current time of day while the script is running.</span></span> <span data-ttu-id="b5482-118">По завершении скрипта показывается время окончания скрипта.</span><span class="sxs-lookup"><span data-stu-id="b5482-118">When the script completes, the display shows the time of day that the script completed.</span></span>  
  
 <span data-ttu-id="b5482-119">**Затраченное**</span><span class="sxs-lookup"><span data-stu-id="b5482-119">**Elapsed**</span></span>  
 <span data-ttu-id="b5482-120">В строке состояния отображается продолжительность выполнения скрипта на данный момент.</span><span class="sxs-lookup"><span data-stu-id="b5482-120">The status bar displays the length of time that the script has been running.</span></span> <span data-ttu-id="b5482-121">По завершении скрипта показывается общая продолжительность выполнения скрипта.</span><span class="sxs-lookup"><span data-stu-id="b5482-121">When the script completes, the display shows how much time was taken to run the script.</span></span>  
  
 <span data-ttu-id="b5482-122">**Включить имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="b5482-122">**Include database name**</span></span>  
 <span data-ttu-id="b5482-123">Включает имя текущей базы данных для данного соединения.</span><span class="sxs-lookup"><span data-stu-id="b5482-123">Includes the name of the current database for the connection.</span></span> <span data-ttu-id="b5482-124">При первом открытии редактора запросов это база данных по умолчанию для имени входа.</span><span class="sxs-lookup"><span data-stu-id="b5482-124">When the query editor is first opened, this is the default database for the login.</span></span> <span data-ttu-id="b5482-125">Контекст базы данных можно сменить позже с помощью инструкции USE языка Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="b5482-125">The database context can later be changed by using the Transact-SQL USE statement.</span></span>  
  
 <span data-ttu-id="b5482-126">**Включить имя входа**</span><span class="sxs-lookup"><span data-stu-id="b5482-126">**Include login name**</span></span>  
 <span data-ttu-id="b5482-127">Включает имя входа.</span><span class="sxs-lookup"><span data-stu-id="b5482-127">Includes the login name.</span></span>  
  
 <span data-ttu-id="b5482-128">**Отображать количество строк**</span><span class="sxs-lookup"><span data-stu-id="b5482-128">**Include row count**</span></span>  
 <span data-ttu-id="b5482-129">Включает количество строк, которые были обработаны скриптом, выполняемым в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="b5482-129">Includes a count of the rows that have been processed by the script that is currently executing.</span></span>  
  
 <span data-ttu-id="b5482-130">**Включить имя сервера**</span><span class="sxs-lookup"><span data-stu-id="b5482-130">**Include server name**</span></span>  
 <span data-ttu-id="b5482-131">Включает имя сервера.</span><span class="sxs-lookup"><span data-stu-id="b5482-131">Includes the server name.</span></span> <span data-ttu-id="b5482-132">Для локальных соединений это имя экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b5482-132">For local connections, this is the instance name.</span></span> <span data-ttu-id="b5482-133">Для удаленных соединений это имя удаленного компьютера и имя экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b5482-133">For remote connections, this is the remote computer name and instance name.</span></span>  
  
## <a name="status-bar-layout-and-colors"></a><span data-ttu-id="b5482-134">Макет и цвета строки состояния</span><span class="sxs-lookup"><span data-stu-id="b5482-134">Status Bar Layout and Colors</span></span>  
 <span data-ttu-id="b5482-135">Указывает цвета для элементов в строке состояния редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="b5482-135">Specifies the colors for items in the Query Editor status bar.</span></span>  
  
 <span data-ttu-id="b5482-136">**Групповые соединения**</span><span class="sxs-lookup"><span data-stu-id="b5482-136">**Group connections**</span></span>  
 <span data-ttu-id="b5482-137">Установите цвет строки состояния, применяемый, если редактор запросов имеет больше одного соединения.</span><span class="sxs-lookup"><span data-stu-id="b5482-137">Set the color of the status bar when the Query Editor has more than one connection.</span></span>  
  
 <span data-ttu-id="b5482-138">**Соединения с одиночным сервером**</span><span class="sxs-lookup"><span data-stu-id="b5482-138">**Single server connections**</span></span>  
 <span data-ttu-id="b5482-139">Установите цвет строки состояния, применяемый, если редактор запросов имеет одно соединение.</span><span class="sxs-lookup"><span data-stu-id="b5482-139">Set the color of the status bar when the Query Editor has one connection.</span></span>  
  
 <span data-ttu-id="b5482-140">**Расположение строки состояния**</span><span class="sxs-lookup"><span data-stu-id="b5482-140">**Status bar location**</span></span>  
 <span data-ttu-id="b5482-141">Указывает расположение строки состояния.</span><span class="sxs-lookup"><span data-stu-id="b5482-141">Specifies the location of the status bar.</span></span> <span data-ttu-id="b5482-142">Доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="b5482-142">The settings are as follows:</span></span>  
  
 <span data-ttu-id="b5482-143">**Top**</span><span class="sxs-lookup"><span data-stu-id="b5482-143">**Top**</span></span>  
 <span data-ttu-id="b5482-144">Строка состояния появляется в верхней части окна редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="b5482-144">The status bar appears at the top of the Query Editor window.</span></span>  
  
 <span data-ttu-id="b5482-145">**Последние**</span><span class="sxs-lookup"><span data-stu-id="b5482-145">**Bottom**</span></span>  
 <span data-ttu-id="b5482-146">Строка состояния появляется в нижней части окна редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="b5482-146">The status bar appears at the bottom of the Query Editor window.</span></span>  
  
## <a name="tab-text"></a><span data-ttu-id="b5482-147">Текст вкладки</span><span class="sxs-lookup"><span data-stu-id="b5482-147">Tab Text</span></span>  
 <span data-ttu-id="b5482-148">Задает текст, который появляется на вкладке в верхней части окна «Редактор запросов».</span><span class="sxs-lookup"><span data-stu-id="b5482-148">Specifies the text that appears in the tab at the top of a Query Editor window.</span></span> <span data-ttu-id="b5482-149">Если текста слишком много, чтобы его отобразить, можно просмотреть полную строку во всплывающей подсказке, которая появляется при наведении указателя мыши на вкладку.</span><span class="sxs-lookup"><span data-stu-id="b5482-149">If the text is too long to display, you can view the full string in a tooltip that is displayed if you hover over the tab.</span></span>  
  
 <span data-ttu-id="b5482-150">**Включить имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="b5482-150">**Include database name**</span></span>  
 <span data-ttu-id="b5482-151">Включает имя текущей базы данных для данного соединения.</span><span class="sxs-lookup"><span data-stu-id="b5482-151">Includes the name of the current database for the connection.</span></span> <span data-ttu-id="b5482-152">При первом открытии редактора запросов это база данных по умолчанию для имени входа.</span><span class="sxs-lookup"><span data-stu-id="b5482-152">When the query editor is first opened, this is the default database for the login.</span></span> <span data-ttu-id="b5482-153">Контекст базы данных можно сменить позже с помощью инструкции USE языка Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="b5482-153">The database context can later be changed by using the Transact-SQL USE statement.</span></span>  
  
 <span data-ttu-id="b5482-154">**Включить имя файла**</span><span class="sxs-lookup"><span data-stu-id="b5482-154">**Include file name**</span></span>  
 <span data-ttu-id="b5482-155">Включает имя файла, в котором хранится скрипт.</span><span class="sxs-lookup"><span data-stu-id="b5482-155">Includes the name of the file where the script is stored.</span></span>  
  
 <span data-ttu-id="b5482-156">**Включить имя папки**</span><span class="sxs-lookup"><span data-stu-id="b5482-156">**Include folder name**</span></span>  
 <span data-ttu-id="b5482-157">Включает путь к папке, в которой хранится файл скрипта.</span><span class="sxs-lookup"><span data-stu-id="b5482-157">Includes the path of the folder where the script file is stored.</span></span>  
  
 <span data-ttu-id="b5482-158">**Включить имя входа**</span><span class="sxs-lookup"><span data-stu-id="b5482-158">**Include login name**</span></span>  
 <span data-ttu-id="b5482-159">Включает имя входа.</span><span class="sxs-lookup"><span data-stu-id="b5482-159">Includes the login name.</span></span>  
  
 <span data-ttu-id="b5482-160">**Включить имя сервера**</span><span class="sxs-lookup"><span data-stu-id="b5482-160">**Include server name**</span></span>  
 <span data-ttu-id="b5482-161">Включает имя сервера.</span><span class="sxs-lookup"><span data-stu-id="b5482-161">Includes the server name.</span></span> <span data-ttu-id="b5482-162">Для локальных соединений это имя экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b5482-162">For local connections, this is the instance name.</span></span> <span data-ttu-id="b5482-163">Для удаленных соединений это имя удаленного компьютера и имя экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b5482-163">For remote connections, this is the remote computer name and instance name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5482-164">См. также:</span><span class="sxs-lookup"><span data-stu-id="b5482-164">See Also</span></span>  
 <span data-ttu-id="b5482-165">[Параметры &#40;среда: страница "шрифты и цвета"&#41;](../ssms/menu-help/options-environment-fonts-and-colors-page.md) </span><span class="sxs-lookup"><span data-stu-id="b5482-165">[Options &#40;Environment: Fonts and Colors Page&#41;](../ssms/menu-help/options-environment-fonts-and-colors-page.md) </span></span>  
 [<span data-ttu-id="b5482-166">Выделение цветом в редакторах запросов</span><span class="sxs-lookup"><span data-stu-id="b5482-166">Color Coding in Query Editors</span></span>](../relational-databases/scripting/color-coding-in-query-editors.md)  
  
  
