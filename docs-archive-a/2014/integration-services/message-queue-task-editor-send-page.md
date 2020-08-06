---
title: Редактор задачи «очередь сообщений» (страница «отправка») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msgqueuetask.send.f1
helpviewer_keywords:
- Message Queue Task Editor
ms.assetid: 565aa079-ac44-4407-8efc-cddab839de30
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3534e1a8b475f22064ef7f2283c2e70eb561294f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752252"
---
# <a name="message-queue-task-editor-send-page"></a><span data-ttu-id="6799f-102">Редактор задачи «Очередь сообщений» (страница «Отправка»)</span><span class="sxs-lookup"><span data-stu-id="6799f-102">Message Queue Task Editor (Send Page)</span></span>
  <span data-ttu-id="6799f-103">Используйте страницу **Отправить** диалогового окна **Редактор задачи "Очередь сообщений"** , чтобы настроить задачу "Очередь сообщений" для отправки сообщений от пакета служб [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6799f-103">Use the **Send** page of the **Message Queue Task Editor** dialog box to configure a Message Queue task to send messages from a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span>  
  
 <span data-ttu-id="6799f-104">Дополнительные сведения об этой задаче см. в разделе [Message Queue Task](control-flow/message-queue-task.md).</span><span class="sxs-lookup"><span data-stu-id="6799f-104">To learn about this task, see [Message Queue Task](control-flow/message-queue-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6799f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6799f-105">Options</span></span>  
 <span data-ttu-id="6799f-106">**UseEncryption**</span><span class="sxs-lookup"><span data-stu-id="6799f-106">**UseEncryption**</span></span>  
 <span data-ttu-id="6799f-107">Укажите, необходимо ли шифровать сообщение.</span><span class="sxs-lookup"><span data-stu-id="6799f-107">Indicate whether to encrypt the message.</span></span> <span data-ttu-id="6799f-108">Значение по умолчанию — `False`.</span><span class="sxs-lookup"><span data-stu-id="6799f-108">The default is `False`.</span></span>  
  
 <span data-ttu-id="6799f-109">**EncryptionAlgorithm**</span><span class="sxs-lookup"><span data-stu-id="6799f-109">**EncryptionAlgorithm**</span></span>  
 <span data-ttu-id="6799f-110">При выборе шифрования задайте имя алгоритма шифрования для использования.</span><span class="sxs-lookup"><span data-stu-id="6799f-110">If you choose to use encryption, specify the name of the encryption algorithm to use.</span></span> <span data-ttu-id="6799f-111">Задача «Очередь сообщений» поддерживает алгоритмы RC2 и RC4.</span><span class="sxs-lookup"><span data-stu-id="6799f-111">The Message Queue task can use the RC2 and RC4 algorithms.</span></span> <span data-ttu-id="6799f-112">По умолчанию, используется алгоритм **RC2**.</span><span class="sxs-lookup"><span data-stu-id="6799f-112">The default is **RC2**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6799f-113">Алгоритм RC4 поддерживается только в целях обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="6799f-113">The RC4 algorithm is only supported for backward compatibility.</span></span> <span data-ttu-id="6799f-114">Когда база данных имеет уровень совместимости 90 или 100, новые материалы могут шифроваться только с помощью алгоритмов RC4 или RC4_128.</span><span class="sxs-lookup"><span data-stu-id="6799f-114">New material can only be encrypted using RC4 or RC4_128 when the database is in compatibility level 90 or 100.</span></span> <span data-ttu-id="6799f-115">(Не рекомендуется.) Используйте вместо этого более новые алгоритмы, например AES.</span><span class="sxs-lookup"><span data-stu-id="6799f-115">(Not recommended.) Use a newer algorithm such as one of the AES algorithms instead.</span></span> <span data-ttu-id="6799f-116">В текущем выпуске [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] материалы, зашифрованные с помощью алгоритмов RC4 или RC4_128, могут быть расшифрованы на любом уровне совместимости.</span><span class="sxs-lookup"><span data-stu-id="6799f-116">In the current release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], material encrypted using RC4 or RC4_128 can be decrypted in any compatibility level.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6799f-117">Здесь приведены алгоритмы шифрования, поддерживаемые технологией очередей сообщений (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="6799f-117">These are the encryption algorithms that the Message Queuing (also known as MSMQ) technology supports.</span></span> <span data-ttu-id="6799f-118">Оба этих алгоритма шифрования считаются сегодня криптографически слабыми по сравнению с новыми алгоритмами, которые служба очередей сообщений еще не поддерживает.</span><span class="sxs-lookup"><span data-stu-id="6799f-118">Both of these encryption algorithms are now considered cryptographically weak compared to newer algorithms, which Message Queuing does not yet support.</span></span> <span data-ttu-id="6799f-119">Поэтому при отправке сообщений с помощью задачи «Очередь сообщений» необходимо тщательно учитывать требования криптографии.</span><span class="sxs-lookup"><span data-stu-id="6799f-119">Therefore, you should consider your cryptography needs carefully when sending messages using the Message Queue task.</span></span>  
  
 <span data-ttu-id="6799f-120">**MessageType**</span><span class="sxs-lookup"><span data-stu-id="6799f-120">**MessageType**</span></span>  
 <span data-ttu-id="6799f-121">Выбор типа сообщения.</span><span class="sxs-lookup"><span data-stu-id="6799f-121">Select the message type.</span></span> <span data-ttu-id="6799f-122">Это свойство имеет параметры, указанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="6799f-122">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="6799f-123">Значение</span><span class="sxs-lookup"><span data-stu-id="6799f-123">Value</span></span>|<span data-ttu-id="6799f-124">Описание</span><span class="sxs-lookup"><span data-stu-id="6799f-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6799f-125">**Сообщение файла данных**</span><span class="sxs-lookup"><span data-stu-id="6799f-125">**Data file message**</span></span>|<span data-ttu-id="6799f-126">Сообщение хранится в файле.</span><span class="sxs-lookup"><span data-stu-id="6799f-126">The message is stored in a file.</span></span> <span data-ttu-id="6799f-127">При выборе этого значения отображается динамический параметр **DataFileMessage**.</span><span class="sxs-lookup"><span data-stu-id="6799f-127">Selecting the value displays the dynamic option, **DataFileMessage**.</span></span>|  
|<span data-ttu-id="6799f-128">**Сообщение переменной**</span><span class="sxs-lookup"><span data-stu-id="6799f-128">**Variable message**</span></span>|<span data-ttu-id="6799f-129">Сообщение хранится в переменной.</span><span class="sxs-lookup"><span data-stu-id="6799f-129">The message is stored in a variable.</span></span> <span data-ttu-id="6799f-130">При выборе этого значения отображается динамический параметр **VariableMessage**.</span><span class="sxs-lookup"><span data-stu-id="6799f-130">Selecting the value displays the dynamic option, **VariableMessage**.</span></span>|  
|<span data-ttu-id="6799f-131">**Строковое сообщение**</span><span class="sxs-lookup"><span data-stu-id="6799f-131">**String message**</span></span>|<span data-ttu-id="6799f-132">Сообщение сохраняется в задаче «Очередь сообщений».</span><span class="sxs-lookup"><span data-stu-id="6799f-132">The message is stored in the Message Queue task.</span></span> <span data-ttu-id="6799f-133">При выборе этого значения отображается динамический параметр **StringMessage**.</span><span class="sxs-lookup"><span data-stu-id="6799f-133">Selecting the value displays the dynamic option, **StringMessage**.</span></span>|  
  
## <a name="messagetype-dynamic-options"></a><span data-ttu-id="6799f-134">Динамические параметры MessageType</span><span class="sxs-lookup"><span data-stu-id="6799f-134">MessageType Dynamic Options</span></span>  
  
### <a name="messagetype--data-file-message"></a><span data-ttu-id="6799f-135">MessageType = Сообщение файла данных</span><span class="sxs-lookup"><span data-stu-id="6799f-135">MessageType = Data file message</span></span>  
 <span data-ttu-id="6799f-136">**DataFileMessage**</span><span class="sxs-lookup"><span data-stu-id="6799f-136">**DataFileMessage**</span></span>  
 <span data-ttu-id="6799f-137">Введите путь к файлу данных или нажмите кнопку с многоточием **(…)** , а затем найдите файл.</span><span class="sxs-lookup"><span data-stu-id="6799f-137">Type the path of the data file, or click the ellipsis **(...)** and then locate the file.</span></span>  
  
### <a name="messagetype--variable-message"></a><span data-ttu-id="6799f-138">MessageType = Сообщение с переменными</span><span class="sxs-lookup"><span data-stu-id="6799f-138">MessageType = Variable message</span></span>  
 <span data-ttu-id="6799f-139">**VariableMessage**</span><span class="sxs-lookup"><span data-stu-id="6799f-139">**VariableMessage**</span></span>  
 <span data-ttu-id="6799f-140">Введите имена переменных или нажмите кнопку с многоточием **(…)** , а затем выберите переменные.</span><span class="sxs-lookup"><span data-stu-id="6799f-140">Type the variable names, or click the ellipsis **(...)** and then select the variables.</span></span> <span data-ttu-id="6799f-141">Переменные разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="6799f-141">Variables are separated by commas.</span></span>  
  
 <span data-ttu-id="6799f-142">**См. также:** Выбор переменных</span><span class="sxs-lookup"><span data-stu-id="6799f-142">**Related Topics:** Select Variables</span></span>  
  
### <a name="messagetype--string-message"></a><span data-ttu-id="6799f-143">MessageType = Строковое сообщение</span><span class="sxs-lookup"><span data-stu-id="6799f-143">MessageType = String message</span></span>  
 <span data-ttu-id="6799f-144">**StringMessage**</span><span class="sxs-lookup"><span data-stu-id="6799f-144">**StringMessage**</span></span>  
 <span data-ttu-id="6799f-145">Введите строковое сообщение или нажмите кнопку с многоточием **(…)** , а затем введите сообщение в диалоговом окне **Введите строковое сообщение**.</span><span class="sxs-lookup"><span data-stu-id="6799f-145">Type the string message, or click the ellipsis **(...)** and then type the message in the **Enter String Message** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6799f-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="6799f-146">See Also</span></span>  
 <span data-ttu-id="6799f-147">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6799f-147">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="6799f-148">[Редактор задачи "очередь сообщений" &#40;страница "Общие"&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="6799f-148">[Message Queue Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="6799f-149">[Редактор задачи "очередь сообщений" &#40;"получить страницу"&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span><span class="sxs-lookup"><span data-stu-id="6799f-149">[Message Queue Task Editor &#40;Receive Page&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span></span>  
 [<span data-ttu-id="6799f-150">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="6799f-150">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
