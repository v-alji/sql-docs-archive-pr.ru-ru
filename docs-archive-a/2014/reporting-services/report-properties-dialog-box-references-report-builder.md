---
title: Диалоговое окно «Свойства отчета», ссылки (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10082"
ms.assetid: 3414c857-8ea6-4fc4-a6d5-b4883c039efa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2c28e9053a1c13f8d0e0b7b44f3b1a037976c318
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733570"
---
# <a name="report-properties-dialog-box-references-report-builder"></a><span data-ttu-id="cdcee-102">Диалоговое окно «Свойства отчета» — «Ссылки» (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="cdcee-102">Report Properties Dialog Box, References (Report Builder)</span></span>
  <span data-ttu-id="cdcee-103">На вкладке **Ссылки** диалогового окна **Свойства отчета** можно удалить или добавить ссылки на пользовательские или другие внешние сборки и экземпляры пользовательских классов, используемые выражениями в определении отчета.</span><span class="sxs-lookup"><span data-stu-id="cdcee-103">Select **References** on the **Report Properties** dialog box to add or remove references to custom or other external assemblies and custom class instances that are used by expressions in the report definition.</span></span> <span data-ttu-id="cdcee-104">Пользовательские сборки не поддерживаются в локальном режиме построителя отчетов.</span><span class="sxs-lookup"><span data-stu-id="cdcee-104">Custom assemblies are not supported in local mode in Report Builder.</span></span> <span data-ttu-id="cdcee-105">Для создания отчетов, использующих пользовательские сборки, используйте конструктор отчетов в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cdcee-105">To author reports that use custom assemblies, use Report Designer in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="cdcee-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="cdcee-106">Options</span></span>  
 <span data-ttu-id="cdcee-107">**Добавить или удалить сборки**</span><span class="sxs-lookup"><span data-stu-id="cdcee-107">**Add or remove assemblies**</span></span>  
 <span data-ttu-id="cdcee-108">Отображает список сборок, на которые имеются ссылки в отчете.</span><span class="sxs-lookup"><span data-stu-id="cdcee-108">Lists the assemblies that the report references.</span></span> <span data-ttu-id="cdcee-109">Сборка должна быть доступна на компьютере, на котором установлено средство для создания отчетов, и на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="cdcee-109">The assembly must be available on the computer on which the tool you are using to design the report is installed and on the report server.</span></span> <span data-ttu-id="cdcee-110">Имя ссылки должно точно совпадать с содержимым **\<CodeModule>** тегов в файле языка определения отчетов (RDL).</span><span class="sxs-lookup"><span data-stu-id="cdcee-110">The name of the reference must match the contents of **\<CodeModule>** tags in the Report Definition Language (.rdl) file exactly.</span></span>  
  
 <span data-ttu-id="cdcee-111">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="cdcee-111">**Add**</span></span>  
 <span data-ttu-id="cdcee-112">Нажмите, чтобы добавить сборку.</span><span class="sxs-lookup"><span data-stu-id="cdcee-112">Click to add an assembly.</span></span> <span data-ttu-id="cdcee-113">Нажмите кнопку с многоточием (...), чтобы открыть диалоговое окно **Открыть** , и выберите сборки, необходимые для завершения обработки отчета и оценки выражений.</span><span class="sxs-lookup"><span data-stu-id="cdcee-113">Click the ellipsis (...) button to open the **Open** dialog box and select the assemblies necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="cdcee-114">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="cdcee-114">**Remove**</span></span>  
 <span data-ttu-id="cdcee-115">Чтобы удалить ссылку на сборку из списка, выделите имя сборки, а затем нажмите кнопку **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="cdcee-115">To remove an assembly reference from the list, select the assembly name and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="cdcee-116">**Добавить или удалить классы**</span><span class="sxs-lookup"><span data-stu-id="cdcee-116">**Add or remove classes**</span></span>  
 <span data-ttu-id="cdcee-117">Отображает список экземпляров классов, которые используются в отчете.</span><span class="sxs-lookup"><span data-stu-id="cdcee-117">Lists the class instances that are used by the report.</span></span> <span data-ttu-id="cdcee-118">Список классов используется только элементами на основе экземпляров, но не статическими элементами.</span><span class="sxs-lookup"><span data-stu-id="cdcee-118">The class list is used only by instance-based members, not static members.</span></span>  
  
 <span data-ttu-id="cdcee-119">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="cdcee-119">**Add**</span></span>  
 <span data-ttu-id="cdcee-120">Нажмите, чтобы добавить ссылку на класс.</span><span class="sxs-lookup"><span data-stu-id="cdcee-120">Click to add a class reference.</span></span> <span data-ttu-id="cdcee-121">Нажмите кнопку с многоточием (...), чтобы открыть диалоговое окно **Открыть** , и выберите классы, необходимые для завершения обработки отчета и оценки выражений.</span><span class="sxs-lookup"><span data-stu-id="cdcee-121">Click the ellipsis (...) button to open the **Open** dialog box and select the classes necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="cdcee-122">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="cdcee-122">**Remove**</span></span>  
 <span data-ttu-id="cdcee-123">Чтобы удалить экземпляр класса, выберите его и нажмите кнопку **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="cdcee-123">To delete the class instance, select it and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="cdcee-124">**Крывающемся**</span><span class="sxs-lookup"><span data-stu-id="cdcee-124">**Up**</span></span>  
 <span data-ttu-id="cdcee-125">Применительно к классам, характеризующимся наличием зависимостей, допускается перемещение этой ссылки в более высокую позицию списка.</span><span class="sxs-lookup"><span data-stu-id="cdcee-125">For classes that have dependencies, you can move this reference higher in the list.</span></span>  
  
 <span data-ttu-id="cdcee-126">**Down**</span><span class="sxs-lookup"><span data-stu-id="cdcee-126">**Down**</span></span>  
 <span data-ttu-id="cdcee-127">Применительно к классам, характеризующимся наличием зависимостей, допускается перемещение этой ссылки в более низкую позицию списка.</span><span class="sxs-lookup"><span data-stu-id="cdcee-127">For classes that have dependencies, you can move this reference lower in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdcee-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="cdcee-128">See Also</span></span>  
 <span data-ttu-id="cdcee-129">[Построитель отчетов справки по диалоговым окнам, панелям и мастерам](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="cdcee-129">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 [<span data-ttu-id="cdcee-130">Выражения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="cdcee-130">Expressions &#40;Report Builder and SSRS&#41;</span></span>](report-design/expressions-report-builder-and-ssrs.md)  
  
  
