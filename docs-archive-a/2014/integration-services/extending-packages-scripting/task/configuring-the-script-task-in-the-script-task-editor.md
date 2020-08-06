---
title: Настройка задачи "Скрипт" в редакторе задачи "Скрипт" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], configuring
- Script Task Editor
- SSIS Script task, configuring
ms.assetid: 232de0c9-b24d-4c38-861d-6c1f4a75bdf3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b75b4a030e6c5baa2e26c610b0e8216843c8cca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657162"
---
# <a name="configuring-the-script-task-in-the-script-task-editor"></a><span data-ttu-id="b03b1-102">Настройка задачи «Скрипт» в редакторе задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b03b1-102">Configuring the Script Task in the Script Task Editor</span></span>
  <span data-ttu-id="b03b1-103">Прежде чем писать пользовательский код задачи "Скрипт", настройте ее основные свойства на трех страницах окна **Редактор задачи "Скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="b03b1-103">Before you write custom code in the Script task, you configure its principal properties in the three pages of the **Script Task Editor**.</span></span> <span data-ttu-id="b03b1-104">Дополнительные свойства задачи, не уникальные для задачи «Скрипт», можно настроить в окне «Свойства».</span><span class="sxs-lookup"><span data-stu-id="b03b1-104">You can configure additional task properties that are not unique to the Script task by using the Properties window.</span></span>

> [!NOTE]
>  <span data-ttu-id="b03b1-105">В отличие от предыдущих версий, где можно было указать, являются ли скрипты предварительно скомпилированными, начиная с версии [!INCLUDE[ssISversion10](../../../includes/ssisversion10-md.md)] все скрипты компилируются заранее.</span><span class="sxs-lookup"><span data-stu-id="b03b1-105">Unlike earlier versions where you could indicate whether scripts were precompiled, all scripts are precompiled beginning in [!INCLUDE[ssISversion10](../../../includes/ssisversion10-md.md)].</span></span>

## <a name="general-page-of-the-script-task-editor"></a><span data-ttu-id="b03b1-106">Страница «Общие свойства» окна «Редактор задачи "Скрипт"»</span><span class="sxs-lookup"><span data-stu-id="b03b1-106">General Page of the Script Task Editor</span></span>
 <span data-ttu-id="b03b1-107">На странице **Общие** окна **Редактор задачи "Скрипт"** назначается уникальное имя и вводится описание задачи "Скрипт".</span><span class="sxs-lookup"><span data-stu-id="b03b1-107">On the **General** page of the **Script Task Editor**, you assign a unique name and a description for the Script task.</span></span>

## <a name="script-page-of-the-script-task-editor"></a><span data-ttu-id="b03b1-108">Страница «Скрипт» окна «Редактор задачи "Скрипт"»</span><span class="sxs-lookup"><span data-stu-id="b03b1-108">Script Page of the Script Task Editor</span></span>
 <span data-ttu-id="b03b1-109">Страница **Скрипт** окна **Редактор задачи "Скрипт"** отображает пользовательские свойства задачи "Скрипт".</span><span class="sxs-lookup"><span data-stu-id="b03b1-109">The **Script** page of the **Script Task Editor** displays the custom properties of the Script task.</span></span>

### <a name="scriptlanguage-property"></a><span data-ttu-id="b03b1-110">Свойство ScriptLanguage</span><span class="sxs-lookup"><span data-stu-id="b03b1-110">ScriptLanguage Property</span></span>
 <span data-ttu-id="b03b1-111">Среда набора средств [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools для работы с приложениями (VSTA) поддерживает языки программирования [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic и [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual С#.</span><span class="sxs-lookup"><span data-stu-id="b03b1-111">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA) supports the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C# programming languages.</span></span> <span data-ttu-id="b03b1-112">После создания скрипта в задаче "Скрипт" изменить значение свойства **ScriptLanguage** нельзя.</span><span class="sxs-lookup"><span data-stu-id="b03b1-112">After you create a script in the Script task, you cannot change value of the **ScriptLanguage** property.</span></span>

 <span data-ttu-id="b03b1-113">Чтобы задать язык скриптов по умолчанию для компонентов скрипта и задач "Скрипт", воспользуйтесь свойством **ScriptLanguage** на странице **Общие** диалогового окна **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="b03b1-113">To set the default script language for Script tasks and Script components, use the **ScriptLanguage** property on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="b03b1-114">Дополнительные сведения см. в разделе [General Page](../../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="b03b1-114">For more information, see [General Page](../../general-page-of-integration-services-designers-options.md).</span></span>

### <a name="entrypoint-property"></a><span data-ttu-id="b03b1-115">Свойство EntryPoint</span><span class="sxs-lookup"><span data-stu-id="b03b1-115">EntryPoint Property</span></span>
 <span data-ttu-id="b03b1-116">Свойство `EntryPoint` определяет метод класса `ScriptMain` в проекте VSTA, который вызывается средой выполнения служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] в качестве точки входа в код задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="b03b1-116">The `EntryPoint` property specifies the method on the `ScriptMain` class in the VSTA project that the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime calls as the entry point into the Script task code.</span></span> <span data-ttu-id="b03b1-117">`ScriptMain`Класс является классом по умолчанию, созданным шаблонами скриптов.</span><span class="sxs-lookup"><span data-stu-id="b03b1-117">The `ScriptMain` class is the default class generated by the script templates.</span></span>

 <span data-ttu-id="b03b1-118">При изменении имени метода в проекте VSTA следует поменять значение свойства `EntryPoint`.</span><span class="sxs-lookup"><span data-stu-id="b03b1-118">If you change the name of the method in the VSTA project, you must change the value of the `EntryPoint` property.</span></span>

### <a name="readonlyvariables-and-readwritevariables-properties"></a><span data-ttu-id="b03b1-119">Свойства ReadOnlyVariables и ReadWriteVariables</span><span class="sxs-lookup"><span data-stu-id="b03b1-119">ReadOnlyVariables and ReadWriteVariables Properties</span></span>
 <span data-ttu-id="b03b1-120">В качестве значений этих свойств можно ввести разделенные запятыми списки существующих переменных, чтобы обеспечить доступ к ним в коде задачи «Скрипт» в режиме только для чтения или чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="b03b1-120">You can enter comma-delimited lists of existing variables as the values of these properties to make the variables available for read-only or read/write access within the Script task code.</span></span> <span data-ttu-id="b03b1-121">Переменные обоих типов доступны в коде через свойство <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> объекта `Dts`.</span><span class="sxs-lookup"><span data-stu-id="b03b1-121">Variables of both types are accessed in code through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property of the `Dts` object.</span></span> <span data-ttu-id="b03b1-122">Дополнительные сведения см. в статье [Using Variables in the Script Task](../../extending-packages-scripting/task/using-variables-in-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="b03b1-122">For more information, see [Using Variables in the Script Task](../../extending-packages-scripting/task/using-variables-in-the-script-task.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="b03b1-123">В именах переменных учитывается регистр букв.</span><span class="sxs-lookup"><span data-stu-id="b03b1-123">Variable names are case-sensitive.</span></span>

 <span data-ttu-id="b03b1-124">Для выбора переменных нажмите кнопку с многоточием ( **…** ) рядом с полем свойства.</span><span class="sxs-lookup"><span data-stu-id="b03b1-124">To select the variables, click the ellipsis (**...**) button next to the property field.</span></span> <span data-ttu-id="b03b1-125">Дополнительные сведения см. в статье [Страница "Выбор переменных"](../../control-flow/select-variables-page.md).</span><span class="sxs-lookup"><span data-stu-id="b03b1-125">For more information, see [Select Variables Page](../../control-flow/select-variables-page.md).</span></span>

### <a name="edit-script-button"></a><span data-ttu-id="b03b1-126">Кнопка «Изменить скрипт»</span><span class="sxs-lookup"><span data-stu-id="b03b1-126">Edit Script Button</span></span>
 <span data-ttu-id="b03b1-127">Кнопка **Изменить скрипт** запускает среду разработки VSTA, в которой и создается пользовательский скрипт.</span><span class="sxs-lookup"><span data-stu-id="b03b1-127">The **Edit Script** button launches the VSTA development environment in which you write your custom script.</span></span> <span data-ttu-id="b03b1-128">Дополнительные сведения см. в разделе [Написание кода и отладка задачи "Скрипт"](coding-and-debugging-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="b03b1-128">For more information, see [Coding and Debugging the Script Task](coding-and-debugging-the-script-task.md).</span></span>

## <a name="expressions-page-of-the-script-task-editor"></a><span data-ttu-id="b03b1-129">Страница «Выражения» окна «Редактор задачи "Скрипт"»</span><span class="sxs-lookup"><span data-stu-id="b03b1-129">Expressions Page of the Script Task Editor</span></span>
 <span data-ttu-id="b03b1-130">На странице **Выражения** окна **Редактор задачи "Скрипт"** можно с помощью выражений указать значения свойств задачи "Скрипт", перечисленных выше, а также многих других свойств задач.</span><span class="sxs-lookup"><span data-stu-id="b03b1-130">On the **Expressions** page of the **Script Task Editor**, you can use expressions to provide values for the properties of the Script task listed above and for many other task properties.</span></span> <span data-ttu-id="b03b1-131">Дополнительные сведения см. в разделе [Выражения служб Integration Services (SSIS)](../../expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="b03b1-131">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md).</span></span>

<span data-ttu-id="b03b1-132">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="b03b1-132">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="b03b1-133">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы [!INCLUDE[msCoName](../../../includes/msconame-md.md)], а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="b03b1-133">For the latest downloads, articles, samples, and videos from [!INCLUDE[msCoName](../../../includes/msconame-md.md)], as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="b03b1-134">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="b03b1-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="b03b1-135">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="b03b1-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="b03b1-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="b03b1-136">See Also</span></span>
 [<span data-ttu-id="b03b1-137">Написание кода и отладка задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="b03b1-137">Coding and Debugging the Script Task</span></span>](coding-and-debugging-the-script-task.md)


