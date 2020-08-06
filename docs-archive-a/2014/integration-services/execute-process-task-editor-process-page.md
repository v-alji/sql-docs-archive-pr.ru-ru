---
title: Редактор задачи «Выполнение процесса» (страница «процесс») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executeprocesstask.process.f1
helpviewer_keywords:
- Execute Process Task Editor
ms.assetid: 0fc22406-e79b-47a4-a7e4-108d4ce6202f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ce8629be2c07ae4caac4586b266936a908e71499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727302"
---
# <a name="execute-process-task-editor-process-page"></a><span data-ttu-id="89a46-102">Редактор задачи «Выполнение процесса» (страница «Процесс»)</span><span class="sxs-lookup"><span data-stu-id="89a46-102">Execute Process Task Editor (Process Page)</span></span>
  <span data-ttu-id="89a46-103">Страница **Процесс** диалогового окна **Редактор задачи «Выполнение процесса»** позволяет настраивать параметры выполнения процесса.</span><span class="sxs-lookup"><span data-stu-id="89a46-103">Use the **Process** page of the **Execute Process Task Editor** dialog box to configure the options that execute the process.</span></span> <span data-ttu-id="89a46-104">Эти параметры включают исполняемый объект, его расположение, аргументы командной строки и переменные для входных и выходных данных.</span><span class="sxs-lookup"><span data-stu-id="89a46-104">These options include the executable to run, its location, command prompt arguments, and the variables that provide input and capture output.</span></span>  
  
 <span data-ttu-id="89a46-105">Дополнительные сведения об этой задаче см. в разделе [Execute Process Task](control-flow/execute-process-task.md).</span><span class="sxs-lookup"><span data-stu-id="89a46-105">To learn about this task, see [Execute Process Task](control-flow/execute-process-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="89a46-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="89a46-106">Options</span></span>  
 <span data-ttu-id="89a46-107">**Требуется полное имя файла**</span><span class="sxs-lookup"><span data-stu-id="89a46-107">**RequireFullFileName**</span></span>  
 <span data-ttu-id="89a46-108">Указывает, закончится ли задача ошибкой, если исполняемый объект не найден в указанном месте.</span><span class="sxs-lookup"><span data-stu-id="89a46-108">Indicate whether the task should fail if the executable is not found at the specified location.</span></span>  
  
 <span data-ttu-id="89a46-109">**Исполняемый объект**</span><span class="sxs-lookup"><span data-stu-id="89a46-109">**Executable**</span></span>  
 <span data-ttu-id="89a46-110">Введите имя исполняемого модуля.</span><span class="sxs-lookup"><span data-stu-id="89a46-110">Type the name of the executable to run.</span></span>  
  
 <span data-ttu-id="89a46-111">**Аргументы**</span><span class="sxs-lookup"><span data-stu-id="89a46-111">**Arguments**</span></span>  
 <span data-ttu-id="89a46-112">Введите аргументы командной строки.</span><span class="sxs-lookup"><span data-stu-id="89a46-112">Provide command prompt arguments.</span></span>  
  
 <span data-ttu-id="89a46-113">**WorkingDirectory**</span><span class="sxs-lookup"><span data-stu-id="89a46-113">**WorkingDirectory**</span></span>  
 <span data-ttu-id="89a46-114">Введите путь к папке, содержащей исполняемый объект, или нажмите кнопку обзора **(...)** и укажите эту папку.</span><span class="sxs-lookup"><span data-stu-id="89a46-114">Type the path of the folder that contains the executable, or click the browse button **(...)** and locate the folder.</span></span>  
  
 <span data-ttu-id="89a46-115">**StandardInputVariable**</span><span class="sxs-lookup"><span data-stu-id="89a46-115">**StandardInputVariable**</span></span>  
 <span data-ttu-id="89a46-116">Выберите переменную для ввода данных для этого процесса или щелкните пункт \<**New variable...**> для создания новой переменной:</span><span class="sxs-lookup"><span data-stu-id="89a46-116">Select a variable to provide the input to the process, or click \<**New variable...**> to create a new variable:</span></span>  
  
 <span data-ttu-id="89a46-117">**См. также:**  [Добавление переменной](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="89a46-117">**Related Topics:**  [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
 <span data-ttu-id="89a46-118">**StandardOutputVariable**</span><span class="sxs-lookup"><span data-stu-id="89a46-118">**StandardOutputVariable**</span></span>  
 <span data-ttu-id="89a46-119">Выберите переменную для вывода данных из этого процесса или щелкните пункт \<**New variable...**> для создания новой переменной.</span><span class="sxs-lookup"><span data-stu-id="89a46-119">Select a variable to capture the output of the process, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="89a46-120">**StandardErrorVariable**</span><span class="sxs-lookup"><span data-stu-id="89a46-120">**StandardErrorVariable**</span></span>  
 <span data-ttu-id="89a46-121">Выберите переменную для получения сведений об ошибках этого процессора или щелкните пункт \<**New variable...**> для создания новой переменной.</span><span class="sxs-lookup"><span data-stu-id="89a46-121">Select a variable to capture the error output of the processor, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="89a46-122">**FailTaskIfReturnCodeIsNotSuccessValue**</span><span class="sxs-lookup"><span data-stu-id="89a46-122">**FailTaskIfReturnCodeIsNotSuccessValue**</span></span>  
 <span data-ttu-id="89a46-123">Укажите, должна ли задача завершаться с ошибкой, если код завершения отличен от кода, указанного в параметре **SuccessValue**.</span><span class="sxs-lookup"><span data-stu-id="89a46-123">Indicate whether the task fails if the process exit code is different from the value specified in **SuccessValue**.</span></span>  
  
 <span data-ttu-id="89a46-124">**SuccessValue**</span><span class="sxs-lookup"><span data-stu-id="89a46-124">**SuccessValue**</span></span>  
 <span data-ttu-id="89a46-125">Укажите значение, возвращаемое исполняемым объектом при успешном завершении задачи.</span><span class="sxs-lookup"><span data-stu-id="89a46-125">Specify the value returned by the executable to indicate success.</span></span> <span data-ttu-id="89a46-126">По умолчанию, устанавливается значение **0**.</span><span class="sxs-lookup"><span data-stu-id="89a46-126">By default this value is set to **0**.</span></span>  
  
 <span data-ttu-id="89a46-127">**Время ожидания**</span><span class="sxs-lookup"><span data-stu-id="89a46-127">**TimeOut**</span></span>  
 <span data-ttu-id="89a46-128">Указывает число секунд, в течение которых может выполняться данный процесс.</span><span class="sxs-lookup"><span data-stu-id="89a46-128">Specify the number of seconds that the process can run.</span></span> <span data-ttu-id="89a46-129">Значение **0** показывает, что значение времени ожидания не используется и процесс выполняется до завершения или сбоя.</span><span class="sxs-lookup"><span data-stu-id="89a46-129">A value of **0** indicates that no time-out value is used, and the process runs until it is completed or until an error occurs.</span></span>  
  
 <span data-ttu-id="89a46-130">**TerminateProcessAfterTimeOut**</span><span class="sxs-lookup"><span data-stu-id="89a46-130">**TerminateProcessAfterTimeOut**</span></span>  
 <span data-ttu-id="89a46-131">Указывает, должен ли процесс быть принудительно остановлен по истечении времени, обозначенного в параметре **TimeOut** .</span><span class="sxs-lookup"><span data-stu-id="89a46-131">Indicate whether the process is forced to end after the time-out period specified by the **TimeOut** option.</span></span> <span data-ttu-id="89a46-132">Этот параметр доступен только при значении параметра **Время ожидания** , отличном от **0**.</span><span class="sxs-lookup"><span data-stu-id="89a46-132">This option is available only if **TimeOut** is not **0**.</span></span>  
  
 <span data-ttu-id="89a46-133">**WindowStyle**</span><span class="sxs-lookup"><span data-stu-id="89a46-133">**WindowStyle**</span></span>  
 <span data-ttu-id="89a46-134">Указывает стиль окна, в котором выполняется процесс.</span><span class="sxs-lookup"><span data-stu-id="89a46-134">Specify the window style in which to run the process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a46-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="89a46-135">See Also</span></span>  
 <span data-ttu-id="89a46-136">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="89a46-136">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="89a46-137">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="89a46-137">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
