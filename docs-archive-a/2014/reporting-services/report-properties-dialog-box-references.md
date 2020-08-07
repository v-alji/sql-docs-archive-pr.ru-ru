---
title: Диалоговое окно "Свойства отчета", ссылки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10530"
- sql12.rtp.rptdesigner.reportproperties.references.f1
ms.assetid: 4639d368-9918-4bb1-9953-7a724ca78dea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4b28ea0865d37bdc56054d6b23dc8c82d9279b08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733565"
---
# <a name="report-properties-dialog-box-references"></a><span data-ttu-id="09495-102">Диалоговое окно «Свойства отчета» — «Ссылки»</span><span class="sxs-lookup"><span data-stu-id="09495-102">Report Properties Dialog Box, References</span></span>
  <span data-ttu-id="09495-103">На вкладке **Ссылки** диалогового окна **Свойства отчета** можно удалить или добавить ссылки на пользовательские или другие внешние сборки и экземпляры пользовательских классов, используемые выражениями в определении отчета.</span><span class="sxs-lookup"><span data-stu-id="09495-103">Select **References** on the **Report Properties** dialog box to add or remove references to custom or other external assemblies and custom class instances that are used by expressions in the report definition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="09495-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="09495-104">Options</span></span>  
 <span data-ttu-id="09495-105">**Добавить или удалить сборки**</span><span class="sxs-lookup"><span data-stu-id="09495-105">**Add or remove assemblies**</span></span>  
 <span data-ttu-id="09495-106">Отображает список сборок, на которые имеются ссылки в отчете.</span><span class="sxs-lookup"><span data-stu-id="09495-106">Lists the assemblies that the report references.</span></span> <span data-ttu-id="09495-107">Сборка должна быть доступна на компьютере, на котором установлено средство для создания отчетов, и на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="09495-107">The assembly must be available on the computer on which the tool you are using to design the report is installed and on the report server.</span></span> <span data-ttu-id="09495-108">Имя ссылки должно точно совпадать с содержимым **\<CodeModule>** тегов в файле языка определения отчетов (RDL).</span><span class="sxs-lookup"><span data-stu-id="09495-108">The name of the reference must match the contents of **\<CodeModule>** tags in the Report Definition Language (.rdl) file exactly.</span></span>  
  
 <span data-ttu-id="09495-109">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="09495-109">**Add**</span></span>  
 <span data-ttu-id="09495-110">Нажмите, чтобы добавить сборку.</span><span class="sxs-lookup"><span data-stu-id="09495-110">Click to add an assembly.</span></span> <span data-ttu-id="09495-111">Нажмите кнопку с многоточием (...), чтобы открыть диалоговое окно **Открыть** , и выберите сборки, необходимые для завершения обработки отчета и оценки выражений.</span><span class="sxs-lookup"><span data-stu-id="09495-111">Click the ellipsis (...) button to open the **Open** dialog box and select the assemblies necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="09495-112">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="09495-112">**Delete**</span></span>  
 <span data-ttu-id="09495-113">Чтобы удалить ссылку на сборку из списка, выделите имя сборки, а затем нажмите кнопку **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="09495-113">To remove an assembly reference from the list, select the assembly name and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="09495-114">**Добавить или удалить классы**</span><span class="sxs-lookup"><span data-stu-id="09495-114">**Add or remove classes**</span></span>  
 <span data-ttu-id="09495-115">Отображает список экземпляров классов, которые используются в отчете.</span><span class="sxs-lookup"><span data-stu-id="09495-115">Lists the class instances that are used by the report.</span></span> <span data-ttu-id="09495-116">Список классов используется только элементами на основе экземпляров, но не статическими элементами.</span><span class="sxs-lookup"><span data-stu-id="09495-116">The class list is used only by instance-based members, not static members.</span></span>  
  
 <span data-ttu-id="09495-117">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="09495-117">**Add**</span></span>  
 <span data-ttu-id="09495-118">Нажмите, чтобы добавить ссылку на класс.</span><span class="sxs-lookup"><span data-stu-id="09495-118">Click to add a class reference.</span></span> <span data-ttu-id="09495-119">Нажмите кнопку с многоточием (...), чтобы открыть диалоговое окно **Открыть** , и выберите классы, необходимые для завершения обработки отчета и оценки выражений.</span><span class="sxs-lookup"><span data-stu-id="09495-119">Click the ellipsis (...) button to open the **Open** dialog box and select the classes necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="09495-120">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="09495-120">**Delete**</span></span>  
 <span data-ttu-id="09495-121">Чтобы удалить экземпляр класса, выберите его и нажмите кнопку **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="09495-121">To delete the class instance, select it and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="09495-122">**Крывающемся**</span><span class="sxs-lookup"><span data-stu-id="09495-122">**Up**</span></span>  
 <span data-ttu-id="09495-123">Применительно к классам, характеризующимся наличием зависимостей, допускается перемещение этой ссылки в более высокую позицию списка.</span><span class="sxs-lookup"><span data-stu-id="09495-123">For classes that have dependencies, you can move this reference higher in the list.</span></span>  
  
 <span data-ttu-id="09495-124">**Down**</span><span class="sxs-lookup"><span data-stu-id="09495-124">**Down**</span></span>  
 <span data-ttu-id="09495-125">Применительно к классам, характеризующимся наличием зависимостей, допускается перемещение этой ссылки в более низкую позицию списка.</span><span class="sxs-lookup"><span data-stu-id="09495-125">For classes that have dependencies, you can move this reference lower in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09495-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="09495-126">See Also</span></span>  
 <span data-ttu-id="09495-127">[Пользовательский код и ссылки на сборки в выражениях в конструкторе отчетов (службы SSRS)](report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="09495-127">[Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md) </span></span>  
 <span data-ttu-id="09495-128">[Коллекции переменных отчета и группы ссылаются на &#40;построитель отчетов и службы SSRS&#41;](report-design/built-in-collections-report-and-group-variables-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="09495-128">[Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;](report-design/built-in-collections-report-and-group-variables-references-report-builder.md) </span></span>  
 [<span data-ttu-id="09495-129">Примеры выражений (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="09495-129">Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](report-design/expression-examples-report-builder-and-ssrs.md)  
  
  
