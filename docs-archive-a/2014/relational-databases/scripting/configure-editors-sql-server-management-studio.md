---
title: Настройка редакторов
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: e7c7a8ef-f561-4258-a7b6-c445dba69f87
author: rothja
ms.author: jroth
ms.openlocfilehash: 7e94cdbcd310814081e146e3fd0dbe75260d1240
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732542"
---
# <a name="configure-editors-sql-server-management-studio"></a><span data-ttu-id="934e6-102">Настройка редакторов (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="934e6-102">Configure Editors (SQL Server Management Studio)</span></span>
  <span data-ttu-id="934e6-103">Параметры работы редакторов [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] настраиваются для каждого редактора отдельно.</span><span class="sxs-lookup"><span data-stu-id="934e6-103">You can customize the operation of the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] editors by configuring the options for each editor.</span></span>  
  
## <a name="settng-editor-options"></a><span data-ttu-id="934e6-104">Настройка параметров редактора</span><span class="sxs-lookup"><span data-stu-id="934e6-104">Settng Editor Options</span></span>  
 <span data-ttu-id="934e6-105">Большинство параметров редакторов задаются в диалоговом окне **Параметры**. Чтобы открыть это окно, выберите в меню **Сервис** пункт **Параметры…** .</span><span class="sxs-lookup"><span data-stu-id="934e6-105">Most of the editor options are set by using the **Tools** menu and selecting **Options...** to display an **Options** dialog.</span></span> <span data-ttu-id="934e6-106">В диалоговом окне **Параметры** откройте узел **Текстовый редактор** в левой панели, чтобы задать параметры редактирования кода и текста.</span><span class="sxs-lookup"><span data-stu-id="934e6-106">In the **Options** dialog, open the **Text Editor** node in the left pane to set code and text editing options.</span></span> <span data-ttu-id="934e6-107">Вложенные узлы в узле «Текстовый редактор» относятся к определенным редакторам:</span><span class="sxs-lookup"><span data-stu-id="934e6-107">The nodes under Text Editor apply to specific editors:</span></span>  
  
1.  <span data-ttu-id="934e6-108">**Все языки** — параметры, заданные с помощью этого узла, относятся ко всем редакторам [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="934e6-108">**All Languages** - options set using this node apply to all of the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] editors.</span></span> <span data-ttu-id="934e6-109">Можно переопределить эти настройки с помощью других узлов, задав другие параметры для определенного редактора.</span><span class="sxs-lookup"><span data-stu-id="934e6-109">You can override these settings by using the other nodes to set different options for a specific editor.</span></span>  
  
2.  <span data-ttu-id="934e6-110">**Простой текст** — параметры, заданные с помощью этого узла, относятся к редакторам MDX, DMX и текстовым редакторам.</span><span class="sxs-lookup"><span data-stu-id="934e6-110">**Plain Text** - options set using this node apply to the MDX, DMX, and text editors.</span></span>  
  
3.  <span data-ttu-id="934e6-111">**Transact-SQL** — параметры, заданные с помощью этого узла, относятся к редактору запросов ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="934e6-111">**Transact-SQL** - options set using this node apply to the Database Engine Query Editor.</span></span>  
  
4.  <span data-ttu-id="934e6-112">**XML** — параметры, заданные с помощью этого узла, относятся к редактору XML для аналитики.</span><span class="sxs-lookup"><span data-stu-id="934e6-112">**XML** - options set using this node apply to the XML for Analysis editor.</span></span>  
  
 <span data-ttu-id="934e6-113">Откройте узел **Выполнение запросов** или **Результаты запросов** , чтобы настроить выполнение запросов и способ отображения результатов.</span><span class="sxs-lookup"><span data-stu-id="934e6-113">Open the **Query Execution** or **Query Results** nodes to customize the execution of queries and how the results are displayed.</span></span>  
  
## <a name="editor-configuration-tasks"></a><span data-ttu-id="934e6-114">Задачи конфигурации редакторов</span><span class="sxs-lookup"><span data-stu-id="934e6-114">Editor Configuration Tasks</span></span>  
  
|<span data-ttu-id="934e6-115">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="934e6-115">Task Description</span></span>|<span data-ttu-id="934e6-116">Раздел</span><span class="sxs-lookup"><span data-stu-id="934e6-116">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="934e6-117">Описывается, каким образом можно настроить открытие редактора двойным щелчком файла с указанным расширением в проводнике Windows.</span><span class="sxs-lookup"><span data-stu-id="934e6-117">Describes how to specify that an editor be opened by double-clicking on a file with a specified extension in Windows Explorer.</span></span>|[<span data-ttu-id="934e6-118">Связывание расширения файла с редактором кода</span><span class="sxs-lookup"><span data-stu-id="934e6-118">Associate File Extensions to a Code Editor</span></span>](associate-file-extensions-to-a-code-editor.md)|  
|<span data-ttu-id="934e6-119">Описывается настройка шрифтов для улучшения отображения кода и текста.</span><span class="sxs-lookup"><span data-stu-id="934e6-119">Describes how to customize fonts to make code and text more readable.</span></span>|[<span data-ttu-id="934e6-120">Изменение цвета, размера и стиля шрифта</span><span class="sxs-lookup"><span data-stu-id="934e6-120">Change Font Color, Size, and Style</span></span>](change-font-color-size-and-style.md)|  
|<span data-ttu-id="934e6-121">Описывается способ просмотра свойств.</span><span class="sxs-lookup"><span data-stu-id="934e6-121">Describes how to view properties.</span></span>|[<span data-ttu-id="934e6-122">Использование окна «Свойства» в среде Management Studio</span><span class="sxs-lookup"><span data-stu-id="934e6-122">Use the Properties Window in Management Studio</span></span>](use-the-properties-window-in-management-studio.md)|  
|<span data-ttu-id="934e6-123">Расположение страниц справки F1 в диалоговых окнах параметров редактора.</span><span class="sxs-lookup"><span data-stu-id="934e6-123">Location of the F1 help pages for the editor options dialogs.</span></span>|[<span data-ttu-id="934e6-124">Справка F1 страниц параметров запросов</span><span class="sxs-lookup"><span data-stu-id="934e6-124">Query Options Pages F1 Help</span></span>](../../database-engine/query-options-pages-f1-help.md)|  
  
  
