---
title: Редактор задачи «очередь сообщений» (страница «получение») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msgqueuetask.receive.f1
helpviewer_keywords:
- Message Queue Task Editor
ms.assetid: 7028756d-1dcc-480c-bbcd-e9654f0772a0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f45aa579d37d1fdd3a3124eea972014ce839fdc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752255"
---
# <a name="message-queue-task-editor-receive-page"></a><span data-ttu-id="b3b31-102">Редактор задачи «Очередь сообщений» (страница «Получение»)</span><span class="sxs-lookup"><span data-stu-id="b3b31-102">Message Queue Task Editor (Receive Page)</span></span>
  <span data-ttu-id="b3b31-103">Используйте страницу **Получение** диалогового окна **Редактор задачи "Очередь сообщений"** , чтобы настроить задачу "Очередь сообщений" для получения сообщений [!INCLUDE[msCoName](../includes/msconame-md.md)] Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="b3b31-103">Use the **Receive** page of the **Message Queue Task Editor** dialog box to configure a Message Queue task to receive [!INCLUDE[msCoName](../includes/msconame-md.md)] Message Queuing (MSMQ) messages.</span></span>  
  
 <span data-ttu-id="b3b31-104">Дополнительные сведения об этой задаче см. в разделе [Message Queue Task](control-flow/message-queue-task.md).</span><span class="sxs-lookup"><span data-stu-id="b3b31-104">To learn about this task, see [Message Queue Task](control-flow/message-queue-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b3b31-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3b31-105">Options</span></span>  
 <span data-ttu-id="b3b31-106">**RemoveFromMessageQueue**</span><span class="sxs-lookup"><span data-stu-id="b3b31-106">**RemoveFromMessageQueue**</span></span>  
 <span data-ttu-id="b3b31-107">Указывает, следует ли удалять сообщение из очереди после того, как оно было получено.</span><span class="sxs-lookup"><span data-stu-id="b3b31-107">Indicate whether to remove the message from the queue after it is received.</span></span> <span data-ttu-id="b3b31-108">По умолчанию, этому параметру присваивается значение `False`.</span><span class="sxs-lookup"><span data-stu-id="b3b31-108">By default, this value is set to `False`.</span></span>  
  
 <span data-ttu-id="b3b31-109">**ErrorIfMessageTimeOut**</span><span class="sxs-lookup"><span data-stu-id="b3b31-109">**ErrorIfMessageTimeOut**</span></span>  
 <span data-ttu-id="b3b31-110">Указывает, следует ли считать выполнение задачи завершенным неудачно по истечении лимита времени и отображать сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="b3b31-110">Indicate whether the task fails when the message times out, displaying an error message.</span></span> <span data-ttu-id="b3b31-111">Значение по умолчанию — `False`.</span><span class="sxs-lookup"><span data-stu-id="b3b31-111">The default is `False`.</span></span>  
  
 <span data-ttu-id="b3b31-112">**TimeoutAfter**</span><span class="sxs-lookup"><span data-stu-id="b3b31-112">**TimeoutAfter**</span></span>  
 <span data-ttu-id="b3b31-113">Если будет выбрано отображение сообщения об ошибке в случае неудачного завершения задачи, то следует указать количество секунд для ожидания перед отображением сообщения об истечении лимита времени.</span><span class="sxs-lookup"><span data-stu-id="b3b31-113">If you choose to display an error message on task failure, specify the number of seconds to wait before displaying the time-out message.</span></span>  
  
 <span data-ttu-id="b3b31-114">**MessageType**</span><span class="sxs-lookup"><span data-stu-id="b3b31-114">**MessageType**</span></span>  
 <span data-ttu-id="b3b31-115">Выбор типа сообщения.</span><span class="sxs-lookup"><span data-stu-id="b3b31-115">Select the message type.</span></span> <span data-ttu-id="b3b31-116">Это свойство имеет параметры, указанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="b3b31-116">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="b3b31-117">Значение</span><span class="sxs-lookup"><span data-stu-id="b3b31-117">Value</span></span>|<span data-ttu-id="b3b31-118">Описание</span><span class="sxs-lookup"><span data-stu-id="b3b31-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b3b31-119">**Сообщение файла данных**</span><span class="sxs-lookup"><span data-stu-id="b3b31-119">**Data file message**</span></span>|<span data-ttu-id="b3b31-120">Сообщение хранится в файле.</span><span class="sxs-lookup"><span data-stu-id="b3b31-120">The message is stored in a file.</span></span> <span data-ttu-id="b3b31-121">При выборе этого значения отображается динамический параметр **DataFileMessage**.</span><span class="sxs-lookup"><span data-stu-id="b3b31-121">Selecting the value displays the dynamic option, **DataFileMessage**.</span></span>|  
|<span data-ttu-id="b3b31-122">**Сообщение переменной**</span><span class="sxs-lookup"><span data-stu-id="b3b31-122">**Variable message**</span></span>|<span data-ttu-id="b3b31-123">Сообщение хранится в переменной.</span><span class="sxs-lookup"><span data-stu-id="b3b31-123">The message is stored in a variable.</span></span> <span data-ttu-id="b3b31-124">При выборе этого значения отображается динамический параметр **VariableMessage**.</span><span class="sxs-lookup"><span data-stu-id="b3b31-124">Selecting the value displays the dynamic option, **VariableMessage**.</span></span>|  
|<span data-ttu-id="b3b31-125">**Строковое сообщение**</span><span class="sxs-lookup"><span data-stu-id="b3b31-125">**String message**</span></span>|<span data-ttu-id="b3b31-126">Сообщение сохраняется в задаче «Очередь сообщений».</span><span class="sxs-lookup"><span data-stu-id="b3b31-126">The message is stored in the Message Queue task.</span></span> <span data-ttu-id="b3b31-127">При выборе этого значения отображается динамический параметр **StringMessage**.</span><span class="sxs-lookup"><span data-stu-id="b3b31-127">Selecting the value displays the dynamic option, **StringMessage**.</span></span>|  
|<span data-ttu-id="b3b31-128">**Строковое сообщение в переменную**</span><span class="sxs-lookup"><span data-stu-id="b3b31-128">**String message to variable**</span></span>|<span data-ttu-id="b3b31-129">Сообщение</span><span class="sxs-lookup"><span data-stu-id="b3b31-129">The message</span></span><br /><br /> <span data-ttu-id="b3b31-130">При выборе этого значения отображается динамический параметр **StringMessage**.</span><span class="sxs-lookup"><span data-stu-id="b3b31-130">Selecting the value displays the dynamic option, **StringMessage**.</span></span>|  
  
## <a name="messagetype-dynamic-options"></a><span data-ttu-id="b3b31-131">Динамические параметры MessageType</span><span class="sxs-lookup"><span data-stu-id="b3b31-131">MessageType Dynamic Options</span></span>  
  
### <a name="messagetype--data-file-message"></a><span data-ttu-id="b3b31-132">MessageType = Сообщение файла данных</span><span class="sxs-lookup"><span data-stu-id="b3b31-132">MessageType = Data file message</span></span>  
 <span data-ttu-id="b3b31-133">**SaveFileAs**</span><span class="sxs-lookup"><span data-stu-id="b3b31-133">**SaveFileAs**</span></span>  
 <span data-ttu-id="b3b31-134">Введите путь к используемому файлу или нажмите кнопку с многоточием **(…)** , а затем найдите файл.</span><span class="sxs-lookup"><span data-stu-id="b3b31-134">Type the path of the file to use, or click the ellipsis button **(...)** and then locate the file.</span></span>  
  
 <span data-ttu-id="b3b31-135">**Overwrite**</span><span class="sxs-lookup"><span data-stu-id="b3b31-135">**Overwrite**</span></span>  
 <span data-ttu-id="b3b31-136">Укажите, необходимо ли перезаписать данные в существующем файле при сохранении содержимого сообщения файлов данных.</span><span class="sxs-lookup"><span data-stu-id="b3b31-136">Indicate whether to overwrite the data in an existing file when saving the contents of a data file message.</span></span> <span data-ttu-id="b3b31-137">Значение по умолчанию — `False`.</span><span class="sxs-lookup"><span data-stu-id="b3b31-137">The default is `False`.</span></span>  
  
 <span data-ttu-id="b3b31-138">**Filter**</span><span class="sxs-lookup"><span data-stu-id="b3b31-138">**Filter**</span></span>  
 <span data-ttu-id="b3b31-139">Укажите, следует ли применять фильтр к сообщениям.</span><span class="sxs-lookup"><span data-stu-id="b3b31-139">Specify whether to apply a filter to the message.</span></span> <span data-ttu-id="b3b31-140">Это свойство имеет параметры, указанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="b3b31-140">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="b3b31-141">Значение</span><span class="sxs-lookup"><span data-stu-id="b3b31-141">Value</span></span>|<span data-ttu-id="b3b31-142">Описание</span><span class="sxs-lookup"><span data-stu-id="b3b31-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b3b31-143">**Нет фильтра**</span><span class="sxs-lookup"><span data-stu-id="b3b31-143">**No filter**</span></span>|<span data-ttu-id="b3b31-144">Эта задача не фильтрует сообщения.</span><span class="sxs-lookup"><span data-stu-id="b3b31-144">The task does not filter messages.</span></span> <span data-ttu-id="b3b31-145">Выбор этого значения отображает динамический параметр **IdentifierReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="b3b31-145">Selecting the value displays the dynamic option, **IdentifierReadOnly**.</span></span>|  
|<span data-ttu-id="b3b31-146">**Из пакета**</span><span class="sxs-lookup"><span data-stu-id="b3b31-146">**From package**</span></span>|<span data-ttu-id="b3b31-147">Сообщение получает только сообщения из указанного пакета.</span><span class="sxs-lookup"><span data-stu-id="b3b31-147">The message receives only messages from the specified package.</span></span> <span data-ttu-id="b3b31-148">Выбор этого значения отображает динамический параметр **Идентификатор**.</span><span class="sxs-lookup"><span data-stu-id="b3b31-148">Selecting the value displays the dynamic option, **Identifier**.</span></span>|  
  
### <a name="filter-dynamic-options"></a><span data-ttu-id="b3b31-149">Динамические параметры фильтра</span><span class="sxs-lookup"><span data-stu-id="b3b31-149">Filter Dynamic Options</span></span>  
  
#### <a name="filter--no-filter"></a><span data-ttu-id="b3b31-150">Filter = Не фильтровать</span><span class="sxs-lookup"><span data-stu-id="b3b31-150">Filter = No filter</span></span>  
 <span data-ttu-id="b3b31-151">**IdentifierReadOnly**</span><span class="sxs-lookup"><span data-stu-id="b3b31-151">**IdentifierReadOnly**</span></span>  
 <span data-ttu-id="b3b31-152">Этот параметр доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b3b31-152">This option is read-only.</span></span> <span data-ttu-id="b3b31-153">Он может быть пустым или содержать идентификатор GUID пакета в случае, если свойство «Фильтр» было установлено ранее.</span><span class="sxs-lookup"><span data-stu-id="b3b31-153">It may be blank or contain the GUID of a package when the Filter property was previously set.</span></span>  
  
#### <a name="filter--from-package"></a><span data-ttu-id="b3b31-154">Filter = Из пакета</span><span class="sxs-lookup"><span data-stu-id="b3b31-154">Filter = From package</span></span>  
 <span data-ttu-id="b3b31-155">**Идентификатор**</span><span class="sxs-lookup"><span data-stu-id="b3b31-155">**Identifier**</span></span>  
 <span data-ttu-id="b3b31-156">Если выбрано применение фильтра, следует ввести уникальный идентификатор пакета, из которого могут быть получены сообщения, или нажать кнопку с многоточием **(…)** и указать пакет.</span><span class="sxs-lookup"><span data-stu-id="b3b31-156">If you choose to apply a filter, type the unique identifier of the package from which messages can be received, or click the ellipsis button **(...)** and then specify the package.</span></span>  
  
 <span data-ttu-id="b3b31-157">**См. также:** [Выбор пакета](control-flow/select-a-package.md)</span><span class="sxs-lookup"><span data-stu-id="b3b31-157">**Related Topics:** [Select a Package](control-flow/select-a-package.md)</span></span>  
  
### <a name="messagetype--variable-message"></a><span data-ttu-id="b3b31-158">MessageType = Сообщение с переменными</span><span class="sxs-lookup"><span data-stu-id="b3b31-158">MessageType = Variable message</span></span>  
 <span data-ttu-id="b3b31-159">**Filter**</span><span class="sxs-lookup"><span data-stu-id="b3b31-159">**Filter**</span></span>  
 <span data-ttu-id="b3b31-160">Укажите, следует ли применять фильтр к сообщениям.</span><span class="sxs-lookup"><span data-stu-id="b3b31-160">Specify whether to apply a filter to messages.</span></span> <span data-ttu-id="b3b31-161">Это свойство имеет параметры, указанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="b3b31-161">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="b3b31-162">Значение</span><span class="sxs-lookup"><span data-stu-id="b3b31-162">Value</span></span>|<span data-ttu-id="b3b31-163">Описание</span><span class="sxs-lookup"><span data-stu-id="b3b31-163">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b3b31-164">**Нет фильтра**</span><span class="sxs-lookup"><span data-stu-id="b3b31-164">**No filter**</span></span>|<span data-ttu-id="b3b31-165">Эта задача не фильтрует сообщения.</span><span class="sxs-lookup"><span data-stu-id="b3b31-165">The task does not filter messages.</span></span> <span data-ttu-id="b3b31-166">Выбор этого значения отображает динамический параметр **IdentifierReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="b3b31-166">Selecting the value displays the dynamic option, **IdentifierReadOnly**.</span></span>|  
|<span data-ttu-id="b3b31-167">**Из пакета**</span><span class="sxs-lookup"><span data-stu-id="b3b31-167">**From package**</span></span>|<span data-ttu-id="b3b31-168">Сообщение получает только сообщения из указанного пакета.</span><span class="sxs-lookup"><span data-stu-id="b3b31-168">The message receives only messages from the specified package.</span></span> <span data-ttu-id="b3b31-169">Выбор этого значения отображает динамический параметр **Идентификатор**.</span><span class="sxs-lookup"><span data-stu-id="b3b31-169">Selecting the value displays the dynamic option, **Identifier**.</span></span>|  
  
 <span data-ttu-id="b3b31-170">**Переменная**</span><span class="sxs-lookup"><span data-stu-id="b3b31-170">**Variable**</span></span>  
 <span data-ttu-id="b3b31-171">Введите имя переменной либо выберите пункт \<**New variable...**> и затем настройте новую переменную.</span><span class="sxs-lookup"><span data-stu-id="b3b31-171">Type the variable name, or click \<**New variable...**> and then configure a new variable.</span></span>  
  
 <span data-ttu-id="b3b31-172">**См. также:** [Добавить переменную](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="b3b31-172">**Related Topics:** [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
### <a name="filter-dynamic-options"></a><span data-ttu-id="b3b31-173">Динамические параметры фильтра</span><span class="sxs-lookup"><span data-stu-id="b3b31-173">Filter Dynamic Options</span></span>  
  
#### <a name="filter--no-filter"></a><span data-ttu-id="b3b31-174">Filter = Не фильтровать</span><span class="sxs-lookup"><span data-stu-id="b3b31-174">Filter = No filter</span></span>  
 <span data-ttu-id="b3b31-175">**IdentifierReadOnly**</span><span class="sxs-lookup"><span data-stu-id="b3b31-175">**IdentifierReadOnly**</span></span>  
 <span data-ttu-id="b3b31-176">Этот параметр пуст.</span><span class="sxs-lookup"><span data-stu-id="b3b31-176">This option is blank.</span></span>  
  
#### <a name="filter--from-package"></a><span data-ttu-id="b3b31-177">Filter = Из пакета</span><span class="sxs-lookup"><span data-stu-id="b3b31-177">Filter = From package</span></span>  
 <span data-ttu-id="b3b31-178">**Идентификатор**</span><span class="sxs-lookup"><span data-stu-id="b3b31-178">**Identifier**</span></span>  
 <span data-ttu-id="b3b31-179">Если выбрано применение фильтра, следует ввести уникальный идентификатор пакета, из которого могут быть получены сообщения, или нажать кнопку с многоточием **(…)** и указать пакет.</span><span class="sxs-lookup"><span data-stu-id="b3b31-179">If you choose to apply a filter, type the unique identifier of the package from which messages can be received, or click the ellipsis button **(...)** and then specify the package.</span></span>  
  
 <span data-ttu-id="b3b31-180">**См. также:** [Выбор пакета](control-flow/select-a-package.md)</span><span class="sxs-lookup"><span data-stu-id="b3b31-180">**Related Topics:** [Select a Package](control-flow/select-a-package.md)</span></span>  
  
### <a name="messagetype--string-message"></a><span data-ttu-id="b3b31-181">MessageType = Строковое сообщение</span><span class="sxs-lookup"><span data-stu-id="b3b31-181">MessageType = String message</span></span>  
 <span data-ttu-id="b3b31-182">**Сравнить**</span><span class="sxs-lookup"><span data-stu-id="b3b31-182">**Compare**</span></span>  
 <span data-ttu-id="b3b31-183">Укажите, следует ли применять фильтр к сообщениям.</span><span class="sxs-lookup"><span data-stu-id="b3b31-183">Specify whether to apply a filter to messages.</span></span> <span data-ttu-id="b3b31-184">Это свойство имеет параметры, указанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="b3b31-184">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="b3b31-185">Значение</span><span class="sxs-lookup"><span data-stu-id="b3b31-185">Value</span></span>|<span data-ttu-id="b3b31-186">Описание</span><span class="sxs-lookup"><span data-stu-id="b3b31-186">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b3b31-187">**None**</span><span class="sxs-lookup"><span data-stu-id="b3b31-187">**None**</span></span>|<span data-ttu-id="b3b31-188">Сообщения не сравниваются.</span><span class="sxs-lookup"><span data-stu-id="b3b31-188">Messages are not compared.</span></span>|  
|<span data-ttu-id="b3b31-189">**Точное совпадение**</span><span class="sxs-lookup"><span data-stu-id="b3b31-189">**Exact match**</span></span>|<span data-ttu-id="b3b31-190">Сообщения должны точно совпадать со строкой, указанной в параметре **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="b3b31-190">Messages must match exactly the string in the **CompareString** option.</span></span>|  
|<span data-ttu-id="b3b31-191">**Игнорировать регистр**</span><span class="sxs-lookup"><span data-stu-id="b3b31-191">**Ignore case**</span></span>|<span data-ttu-id="b3b31-192">Сообщение должно совпадать со строкой, указанной в параметре **CompareString** , но регистр при этом не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="b3b31-192">Message must match the string in the **CompareString** option, but the comparison is not case sensitive.</span></span>|  
|<span data-ttu-id="b3b31-193">**Содержит**</span><span class="sxs-lookup"><span data-stu-id="b3b31-193">**Containing**</span></span>|<span data-ttu-id="b3b31-194">Сообщения должны содержать строку, указанную в параметре **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="b3b31-194">Message must contain the string in the **CompareString** option.</span></span>|  
  
 <span data-ttu-id="b3b31-195">**CompareString**</span><span class="sxs-lookup"><span data-stu-id="b3b31-195">**CompareString**</span></span>  
 <span data-ttu-id="b3b31-196">Если в качестве значения параметра **Сравнить** установлено **Нет**, укажите строку, с которой должно сравниваться сообщение.</span><span class="sxs-lookup"><span data-stu-id="b3b31-196">Unless the **Compare** option is set to **None**, provide the string to which the message is compared.</span></span>  
  
### <a name="messagetype--string-message-to-variable"></a><span data-ttu-id="b3b31-197">MessageType = String message to variable</span><span class="sxs-lookup"><span data-stu-id="b3b31-197">MessageType = String message to variable</span></span>  
 <span data-ttu-id="b3b31-198">**Сравнить**</span><span class="sxs-lookup"><span data-stu-id="b3b31-198">**Compare**</span></span>  
 <span data-ttu-id="b3b31-199">Укажите, следует ли применять фильтр к сообщениям.</span><span class="sxs-lookup"><span data-stu-id="b3b31-199">Specify whether to apply a filter to messages.</span></span> <span data-ttu-id="b3b31-200">Это свойство имеет параметры, указанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="b3b31-200">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="b3b31-201">Значение</span><span class="sxs-lookup"><span data-stu-id="b3b31-201">Value</span></span>|<span data-ttu-id="b3b31-202">Описание</span><span class="sxs-lookup"><span data-stu-id="b3b31-202">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b3b31-203">**None**</span><span class="sxs-lookup"><span data-stu-id="b3b31-203">**None**</span></span>|<span data-ttu-id="b3b31-204">Сообщения не сравниваются.</span><span class="sxs-lookup"><span data-stu-id="b3b31-204">Messages are not compared.</span></span>|  
|<span data-ttu-id="b3b31-205">**Точное совпадение**</span><span class="sxs-lookup"><span data-stu-id="b3b31-205">**Exact match**</span></span>|<span data-ttu-id="b3b31-206">Сообщения должны точно совпадать со строкой, указанной в параметре **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="b3b31-206">The message must match exactly the string in the **CompareString** option.</span></span>|  
|<span data-ttu-id="b3b31-207">**Игнорировать регистр**</span><span class="sxs-lookup"><span data-stu-id="b3b31-207">**Ignore case**</span></span>|<span data-ttu-id="b3b31-208">Сообщение должно совпадать со строкой, указанной в параметре **CompareString** , но регистр при этом не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="b3b31-208">The message must match the string in the **CompareString** option but the comparison is not case sensitive.</span></span>|  
|<span data-ttu-id="b3b31-209">**Содержит**</span><span class="sxs-lookup"><span data-stu-id="b3b31-209">**Containing**</span></span>|<span data-ttu-id="b3b31-210">Сообщение должно содержать строку, указанную в параметре **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="b3b31-210">The message must contain the string in the **CompareString** option.</span></span>|  
  
 <span data-ttu-id="b3b31-211">**CompareString**</span><span class="sxs-lookup"><span data-stu-id="b3b31-211">**CompareString**</span></span>  
 <span data-ttu-id="b3b31-212">Если в качестве значения параметра **Сравнить** установлено **Нет**, укажите строку, с которой должно сравниваться сообщение.</span><span class="sxs-lookup"><span data-stu-id="b3b31-212">Unless the **Compare** option is set to **None**, provide the string to which the message is compared.</span></span>  
  
 <span data-ttu-id="b3b31-213">**Переменная**</span><span class="sxs-lookup"><span data-stu-id="b3b31-213">**Variable**</span></span>  
 <span data-ttu-id="b3b31-214">Введите имя переменной, в которой должно храниться полученное сообщение, либо выберите пункт \<**New variable...**> и затем настройте новую переменную.</span><span class="sxs-lookup"><span data-stu-id="b3b31-214">Type the name of the variable to hold the received message, or click \<**New variable...**> and then configure a new variable.</span></span>  
  
 <span data-ttu-id="b3b31-215">**См. также:** [Добавить переменную](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="b3b31-215">**Related Topics:** [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3b31-216">См. также:</span><span class="sxs-lookup"><span data-stu-id="b3b31-216">See Also</span></span>  
 <span data-ttu-id="b3b31-217">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="b3b31-217">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="b3b31-218">[Редактор задачи "очередь сообщений" &#40;страница "Общие"&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="b3b31-218">[Message Queue Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="b3b31-219">[Редактор задачи "очередь сообщений" &#40;"Отправить страницу"&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span><span class="sxs-lookup"><span data-stu-id="b3b31-219">[Message Queue Task Editor &#40;Send Page&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span></span>  
 <span data-ttu-id="b3b31-220">[Страница «Выражения»](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="b3b31-220">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="b3b31-221">Задача «Очередь сообщений»</span><span class="sxs-lookup"><span data-stu-id="b3b31-221">Message Queue Task</span></span>](control-flow/message-queue-task.md)  
  
  
