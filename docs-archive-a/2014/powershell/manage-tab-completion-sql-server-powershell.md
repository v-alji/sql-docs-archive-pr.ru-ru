---
title: Управление завершением по нажатию клавиши Tab (SQL Server PowerShell) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 6296848a-890f-4ad3-8d9f-92ed6a79aa00
author: stevestein
ms.author: sstein
ms.openlocfilehash: 72bcf96245c536d6ea444bc1d7964b7579e793c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668956"
---
# <a name="manage-tab-completion-sql-server-powershell"></a><span data-ttu-id="2563a-102">Управление завершением по нажатию клавиши Tab (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="2563a-102">Manage Tab Completion (SQL Server PowerShell)</span></span>
  <span data-ttu-id="2563a-103">В [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell введены три системные переменные (`$SqlServerMaximumTabCompletion`, `$SqlServerMaximumChildItems` и `$SqlServerIncludeSystemObjects`) для управления функцией завершения Windows PowerShell по клавише TAB.</span><span class="sxs-lookup"><span data-stu-id="2563a-103">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins introduce three variables (`$SqlServerMaximumTabCompletion`, `$SqlServerMaximumChildItems`, and `$SqlServerIncludeSystemObjects`) to control Windows PowerShell tab completion.</span></span> <span data-ttu-id="2563a-104">Функция завершения по клавише TAB позволяет сократить объем вводимого текста, поскольку возвращает таблицы элементов, имена которых начинаются с набранной строки.</span><span class="sxs-lookup"><span data-stu-id="2563a-104">Tab completion reduces the amount of typing you must do by returning tables of items whose names start with the string you are typing.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="2563a-105">Перед началом</span><span class="sxs-lookup"><span data-stu-id="2563a-105">Before You Begin</span></span>  
 <span data-ttu-id="2563a-106">Функция завершения по клавише TAB среды Windows PowerShell дает возможность после ввода части имени пути или командлета нажать клавишу TAB, чтобы получить список элементов, имена которых согласуются с уже набранным текстом.</span><span class="sxs-lookup"><span data-stu-id="2563a-106">With Windows PowerShell tab-completion, when you have typed part of a path or cmdlet name, you can hit the Tab key to get a list of the items whose names match what you have already typed.</span></span> <span data-ttu-id="2563a-107">Затем можно выбрать нужный элемент из списка, не набирая остальную часть его имени.</span><span class="sxs-lookup"><span data-stu-id="2563a-107">You can then select the item you want from the list without having to type the rest of the name.</span></span>  
  
 <span data-ttu-id="2563a-108">При работе с базой данных, содержащей большое количество объектов, списки завершения по клавише TAB могут стать очень большими.</span><span class="sxs-lookup"><span data-stu-id="2563a-108">If you are working in a database that has a lot of objects, the tab-completion lists can become very large.</span></span> <span data-ttu-id="2563a-109">Кроме того, для некоторых типов объектов [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , например представлений, предусмотрено большое число системных объектов.</span><span class="sxs-lookup"><span data-stu-id="2563a-109">Some [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] object types, such as views, also have large numbers of system objects.</span></span>  
  
 <span data-ttu-id="2563a-110">В оснастках [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] впервые представлены три системные переменные, которые позволяют управлять объемом данных, выводимых функцией завершения по клавише TAB и командлетом **Get-ChildItem**.</span><span class="sxs-lookup"><span data-stu-id="2563a-110">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] snap-ins introduces three system variables that you can use to control the amount of information presented by tab-completion and **Get-ChildItem**.</span></span>  
  
 <span data-ttu-id="2563a-111">**$SqlServerMaximumTabCompletion =** *n*</span><span class="sxs-lookup"><span data-stu-id="2563a-111">**$SqlServerMaximumTabCompletion =** *n*</span></span>  
 <span data-ttu-id="2563a-112">Указывает максимальное число объектов, включаемых в список завершения по клавише TAB.</span><span class="sxs-lookup"><span data-stu-id="2563a-112">Specifies the maximum number of objects to include in a tab-completion list.</span></span> <span data-ttu-id="2563a-113">Если нажать клавишу TAB в узле пути, для которого существует более *n* подходящих объектов, выводимый список завершения будет усечен до *n*объектов.</span><span class="sxs-lookup"><span data-stu-id="2563a-113">If you select Tab at a path node having more than *n* objects, the tab-completion list is truncated at *n*.</span></span> <span data-ttu-id="2563a-114">*n* имеет тип integer.</span><span class="sxs-lookup"><span data-stu-id="2563a-114">*n* is an integer.</span></span> <span data-ttu-id="2563a-115">0 — значение по умолчанию, которое означает, что число перечисляемых объектов не ограничено.</span><span class="sxs-lookup"><span data-stu-id="2563a-115">0 is the default setting, and means there is no limit to the number of objects listed.</span></span>  
  
 <span data-ttu-id="2563a-116">**$SqlServerMaximumChildItems =** *n*</span><span class="sxs-lookup"><span data-stu-id="2563a-116">**$SqlServerMaximumChildItems =** *n*</span></span>  
 <span data-ttu-id="2563a-117">Указывает максимальное количество объектов, отображаемых командлетом **Get-ChildItem**.</span><span class="sxs-lookup"><span data-stu-id="2563a-117">Specifies the maximum number of objects displayed by **Get-ChildItem**.</span></span> <span data-ttu-id="2563a-118">Если командлет **Get-ChildItem** выполняется в узле пути, для которого существует более *n* объектов, список будет усечен до *n*объектов.</span><span class="sxs-lookup"><span data-stu-id="2563a-118">If **Get-ChildItem** is run at a path node having more than *n* objects, the list is truncated at *n*.</span></span> <span data-ttu-id="2563a-119">*n* имеет тип integer.</span><span class="sxs-lookup"><span data-stu-id="2563a-119">*n* is an integer.</span></span> <span data-ttu-id="2563a-120">0 — значение по умолчанию, которое означает, что число перечисляемых объектов не ограничено.</span><span class="sxs-lookup"><span data-stu-id="2563a-120">0 is the default setting, and means there is no limit to the number of objects listed.</span></span>  
  
 <span data-ttu-id="2563a-121">**$SqlServerIncludeSystemObjects =** { **$True** | **$False** }</span><span class="sxs-lookup"><span data-stu-id="2563a-121">**$SqlServerIncludeSystemObjects =** { **$True** | **$False** }</span></span>  
 <span data-ttu-id="2563a-122">Если указано значение **$True**, функция завершения по клавише TAB и командлет **Get-ChildItem**отображают системные объекты.</span><span class="sxs-lookup"><span data-stu-id="2563a-122">If **$True**, system objects are displayed by tab-completion and **Get-ChildItem**.</span></span> <span data-ttu-id="2563a-123">Если значение равно **$False**, системные объекты не отображаются.</span><span class="sxs-lookup"><span data-stu-id="2563a-123">If **$False**, no system objects are displayed.</span></span> <span data-ttu-id="2563a-124">Значение по умолчанию — **$False**.</span><span class="sxs-lookup"><span data-stu-id="2563a-124">The default setting is **$False**.</span></span>  
  
## <a name="set-the-sql-server-tab-completion-variables"></a><span data-ttu-id="2563a-125">Установка переменных функции завершения по клавише TAB для SQL Server</span><span class="sxs-lookup"><span data-stu-id="2563a-125">Set the SQL Server Tab Completion Variables</span></span>  
 <span data-ttu-id="2563a-126">Задайте новое значение для любой переменной, значение которой необходимо заменить на отличное от применяемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2563a-126">For any of the variables you want to change from the default value, set the variable to the new value.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="2563a-127">Пример (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="2563a-127">Example (PowerShell)</span></span>  
 <span data-ttu-id="2563a-128">В следующем примере задаются все три переменные и выводятся их значения:</span><span class="sxs-lookup"><span data-stu-id="2563a-128">The following example sets all three variables and lists their settings:</span></span>  
  
```powershell
$SqlServerMaximumTabCompletion = 20  
$SqlServerMaximumChildItems = 10  
$SqlServerIncludeSystemObjects = $False  
dir variable:sqlserver*  
```  
  
## <a name="see-also"></a><span data-ttu-id="2563a-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="2563a-129">See Also</span></span>  
 [<span data-ttu-id="2563a-130">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="2563a-130">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
