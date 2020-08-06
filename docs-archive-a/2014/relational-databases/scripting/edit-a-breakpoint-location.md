---
title: Изменение положения точки останова
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint location
ms.assetid: 5c28e411-0377-4210-a7ce-2a5c13dcdf74
author: rothja
ms.author: jroth
ms.openlocfilehash: 919e62d53d5c9e8898bf1d49c4b5e5aa4c0ed107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654128"
---
# <a name="edit-a-breakpoint-location"></a><span data-ttu-id="4573f-102">Изменение положения точки останова</span><span class="sxs-lookup"><span data-stu-id="4573f-102">Edit a Breakpoint Location</span></span>
  <span data-ttu-id="4573f-103">Положение точки останова задает строку и символ, где находится точка останова в файле скрипта [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4573f-103">The breakpoint location specifies the line and character where the breakpoint resides in a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="4573f-104">Положение точки останова можно изменить и перенести точку останова в другое место в скрипте или в другой скрипт.</span><span class="sxs-lookup"><span data-stu-id="4573f-104">You can edit the breakpoint location to move the breakpoint to another location in the script, or to a different script.</span></span>  
  
## <a name="editing-a-location"></a><span data-ttu-id="4573f-105">Изменение положения</span><span class="sxs-lookup"><span data-stu-id="4573f-105">Editing a Location</span></span>  
 <span data-ttu-id="4573f-106">При изменении положения точки останова она перемещается в новое место вместе со всеми существующими свойствами, такими как число попаданий или условие.</span><span class="sxs-lookup"><span data-stu-id="4573f-106">When you edit a breakpoint location, the breakpoint moves to the new location, carrying with it all of the existing properties, such as a hit count or condition.</span></span>  
  
#### <a name="to-edit-a-breakpoint-location"></a><span data-ttu-id="4573f-107">Изменение положения точки останова</span><span class="sxs-lookup"><span data-stu-id="4573f-107">To Edit a Breakpoint Location</span></span>  
  
1.  <span data-ttu-id="4573f-108">В окне редактора щелкните метку точки останова правой кнопкой мыши и выберите в контекстном меню пункт **Положение** .</span><span class="sxs-lookup"><span data-stu-id="4573f-108">In the editor window, right-click the breakpoint glyph, and then click **Location** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="4573f-109">-или-</span><span class="sxs-lookup"><span data-stu-id="4573f-109">-or-</span></span>  
  
     <span data-ttu-id="4573f-110">В окне **Точки останова** щелкните метку точки останова правой кнопкой мыши и выберите в контекстном меню пункт **Положение** .</span><span class="sxs-lookup"><span data-stu-id="4573f-110">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Location** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="4573f-111">В диалоговом окне **Точка останова в файле** в поле **Файл** укажите новый файл, в поле **Строка** укажите новую строку, а в поле **Символ** укажите новое расположение в строке.</span><span class="sxs-lookup"><span data-stu-id="4573f-111">In the **File Breakpoint** dialog box, edit **File** to specify a new file, **Line** to specify a new line, or **Character** to specify a new location within the line.</span></span> <span data-ttu-id="4573f-112">Если новый указанный файл уже открыт в окне редактора запросов, точка останова перемещается в это окно редактора.</span><span class="sxs-lookup"><span data-stu-id="4573f-112">If the new file you specify is already open in a query editor window, the breakpoint is moved to that editor window.</span></span> <span data-ttu-id="4573f-113">Если файл не открыт, открывается новое окно редактора, в него загружается указанный файл и точка останова перемещается в новое расположение.</span><span class="sxs-lookup"><span data-stu-id="4573f-113">If the file is not opened, a new editor window is opened, the file is loaded in, and the breakpoint moved to the new location.</span></span>  
  
     <span data-ttu-id="4573f-114">При отладке **параметр** Разрешить наличие отличий в исходном коде от первоначальной версии [!INCLUDE[tsql](../../includes/tsql-md.md)]не учитывается.</span><span class="sxs-lookup"><span data-stu-id="4573f-114">The **Allow the source code to be different from the original version** option has no effect when debugging [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4573f-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="4573f-115">See Also</span></span>  
 <span data-ttu-id="4573f-116">[Укажите число попаданий](specify-a-hit-count.md) </span><span class="sxs-lookup"><span data-stu-id="4573f-116">[Specify a Hit Count](specify-a-hit-count.md) </span></span>  
 <span data-ttu-id="4573f-117">[Указание действия точки останова](specify-a-breakpoint-action.md) </span><span class="sxs-lookup"><span data-stu-id="4573f-117">[Specify a Breakpoint Action](specify-a-breakpoint-action.md) </span></span>  
 <span data-ttu-id="4573f-118">[Указание условия для точки останова](specify-a-breakpoint-condition.md) </span><span class="sxs-lookup"><span data-stu-id="4573f-118">[Specify a Breakpoint Condition](specify-a-breakpoint-condition.md) </span></span>  
 [<span data-ttu-id="4573f-119">Задание фильтра точек останова</span><span class="sxs-lookup"><span data-stu-id="4573f-119">Specify a Breakpoint Filter</span></span>](specify-a-breakpoint-filter.md)  
