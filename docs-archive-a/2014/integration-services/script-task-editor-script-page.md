---
title: Редактор задачи «Скрипт» (страница «Скрипт») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.scripttask.script.f1
helpviewer_keywords:
- Script Task Editor
ms.assetid: 93da0e0d-83f5-406d-b144-4cce216571cb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4eec491cc689d7d5c616e0819075e1ee5159d4e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728474"
---
# <a name="script-task-editor-script-page"></a><span data-ttu-id="8a463-102">Редактор задачи «Скрипт» (страница «Скрипт»)</span><span class="sxs-lookup"><span data-stu-id="8a463-102">Script Task Editor (Script Page)</span></span>
  <span data-ttu-id="8a463-103">Используйте страницу **Скрипт** в диалоговом окне **Редактор задачи «Скрипт»** , чтобы задать свойства скрипта и указать переменные, к которым скрипт будет иметь доступ.</span><span class="sxs-lookup"><span data-stu-id="8a463-103">Use the **Script** page of the **Script Task Editor** dialog box to set script properties and specify variables that can be accessed by the script.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a463-104">В [!INCLUDE[ssISversion10](../includes/ssisversion10-md.md)] и более поздних версиях все скрипты предварительно скомпилированы.</span><span class="sxs-lookup"><span data-stu-id="8a463-104">In [!INCLUDE[ssISversion10](../includes/ssisversion10-md.md)] and later versions, all scripts are precompiled.</span></span> <span data-ttu-id="8a463-105">В предыдущих версиях для предварительной компиляции необходимо было установить свойство **PrecompileScriptIntoBinaryCode** .</span><span class="sxs-lookup"><span data-stu-id="8a463-105">In earlier versions, you set a **PrecompileScriptIntoBinaryCode** property to specify that the script was precompiled.</span></span>  
  
 <span data-ttu-id="8a463-106">Дополнительные сведения о задаче «Скрипт» см. в разделах [Script Task](control-flow/script-task.md) и [Настройка задачи «Скрипт» в редакторе задачи «Скрипт»](extending-packages-scripting/task/configuring-the-script-task-in-the-script-task-editor.md).</span><span class="sxs-lookup"><span data-stu-id="8a463-106">To learn more about the Script task, see [Script Task](control-flow/script-task.md) and [Configuring the Script Task in the Script Task Editor](extending-packages-scripting/task/configuring-the-script-task-in-the-script-task-editor.md).</span></span> <span data-ttu-id="8a463-107">Дополнительные сведения о программировании задачи «Скрипт» см. в разделе [Extending the Package with the Script Task](extending-packages-scripting/task/extending-the-package-with-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="8a463-107">To learn about programming the Script task, see [Extending the Package with the Script Task](extending-packages-scripting/task/extending-the-package-with-the-script-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8a463-108">Варианты</span><span class="sxs-lookup"><span data-stu-id="8a463-108">Options</span></span>  
 <span data-ttu-id="8a463-109">**ScriptLanguage**</span><span class="sxs-lookup"><span data-stu-id="8a463-109">**ScriptLanguage**</span></span>  
 <span data-ttu-id="8a463-110">Выберите используемый для задачи язык скрипта: [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual Basic или [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="8a463-110">Select the scripting language for the task, either [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual C#.</span></span>  
  
 <span data-ttu-id="8a463-111">Изменить значение свойства **ScriptLanguage** для задачи после создания скрипта нельзя.</span><span class="sxs-lookup"><span data-stu-id="8a463-111">After you have created a script for the task, you cannot change the value of the **ScriptLanguage** property.</span></span>  
  
 <span data-ttu-id="8a463-112">Чтобы установить значение по умолчанию языка скрипта для задачи «Скрипт», воспользуйтесь параметром **Язык скрипта** страницы **Общие** диалогового окна **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="8a463-112">To set the default scripting language for the Script task, use the **Scripting language** option on **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="8a463-113">Дополнительные сведения см. в разделе [General Page](general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="8a463-113">For more information, see [General Page](general-page-of-integration-services-designers-options.md).</span></span>  
  
 <span data-ttu-id="8a463-114">**EntryPoint**</span><span class="sxs-lookup"><span data-stu-id="8a463-114">**EntryPoint**</span></span>  
 <span data-ttu-id="8a463-115">Укажите метод, вызываемый средой выполнения служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , в качестве точки входа в код задачи "Скрипт".</span><span class="sxs-lookup"><span data-stu-id="8a463-115">Specify the method that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] runtime calls as the entry point into the code of the Script task.</span></span> <span data-ttu-id="8a463-116">Указанный метод должен находиться в классе ScriptMain [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] проекта Tools for Applications (VSTA). класс ScriptMain является классом по умолчанию, созданным шаблонами скриптов.</span><span class="sxs-lookup"><span data-stu-id="8a463-116">The specified method must be in the ScriptMain class of the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA) project The ScriptMain class is the default class generated by the script templates.</span></span>  
  
 <span data-ttu-id="8a463-117">Для изменения имени метода в проекте VSTA следует поменять значение свойства **EntryPoint** .</span><span class="sxs-lookup"><span data-stu-id="8a463-117">If you change the name of the method in the VSTA project, you must change the value of the **EntryPoint** property.</span></span>  
  
 <span data-ttu-id="8a463-118">**ReadOnlyVariables**</span><span class="sxs-lookup"><span data-stu-id="8a463-118">**ReadOnlyVariables**</span></span>  
 <span data-ttu-id="8a463-119">Введите через запятую список переменных "только для чтения", которые доступны для скрипта, или нажмите кнопку с многоточием (**...**) и выберите переменные в диалоговом окне **Выбор переменных**.</span><span class="sxs-lookup"><span data-stu-id="8a463-119">Type a comma-separated list of read-only variables that are available to the script, or click the ellipsis (**...**) button and select the variables in the **Select variables** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a463-120">В именах переменных учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="8a463-120">Variable names are case sensitive.</span></span>  
  
 <span data-ttu-id="8a463-121">**ReadWriteVariables**</span><span class="sxs-lookup"><span data-stu-id="8a463-121">**ReadWriteVariables**</span></span>  
 <span data-ttu-id="8a463-122">Введите через запятую список переменных "для чтения и записи", которые доступны для скрипта, или нажмите кнопку с многоточием (**...**) и выберите переменные в диалоговом окне **Выбор переменных**.</span><span class="sxs-lookup"><span data-stu-id="8a463-122">Type a comma-separated list of read/write variables that are available to the script, or click the ellipsis (**...**) button and select the variables in the **Select variables** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a463-123">В именах переменных учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="8a463-123">Variable names are case sensitive.</span></span>  
  
 <span data-ttu-id="8a463-124">**Изменение скрипта**</span><span class="sxs-lookup"><span data-stu-id="8a463-124">**Edit Script**</span></span>  
 <span data-ttu-id="8a463-125">Открывает среду VSTA IDE, в которой можно создать или изменить скрипт.</span><span class="sxs-lookup"><span data-stu-id="8a463-125">Opens the VSTA IDE where you can create or modify the script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a463-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="8a463-126">See Also</span></span>  
 <span data-ttu-id="8a463-127">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8a463-127">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="8a463-128">[Страница "Общие"](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="8a463-128">[General Page](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="8a463-129">[Редактор задачи "Скрипт" &#40;страница "Общие"&#41;](../../2014/integration-services/script-task-editor-general-page.md) </span><span class="sxs-lookup"><span data-stu-id="8a463-129">[Script Task Editor &#40;General Page&#41;](../../2014/integration-services/script-task-editor-general-page.md) </span></span>  
 <span data-ttu-id="8a463-130">[Страница «Выражения»](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="8a463-130">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="8a463-131">[Примеры задач "Скрипт"](extending-packages-scripting-task-examples/script-task-examples.md) </span><span class="sxs-lookup"><span data-stu-id="8a463-131">[Script Task Examples](extending-packages-scripting-task-examples/script-task-examples.md) </span></span>  
 <span data-ttu-id="8a463-132">[Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="8a463-132">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="8a463-133">Добавление, удаление и изменение области определяемой пользователем переменной в пакете</span><span class="sxs-lookup"><span data-stu-id="8a463-133">Add, Delete, Change Scope of User-Defined Variable in a Package</span></span>](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md)  
  
  
