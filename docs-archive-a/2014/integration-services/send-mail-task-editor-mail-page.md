---
title: Редактор задачи «Отправка почты» (страница «почта») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sendmailtask.mail.f1
helpviewer_keywords:
- Send Mail Task Editor
ms.assetid: adb385d5-ef24-4d18-b9ea-b39e00a7075e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 52cab62f3c88ea248b76061664547fd8f1314099
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751304"
---
# <a name="send-mail-task-editor-mail-page"></a><span data-ttu-id="5af26-102">Редактор задачи «Отправка почты» (страница «Почта»)</span><span class="sxs-lookup"><span data-stu-id="5af26-102">Send Mail Task Editor (Mail Page)</span></span>
  <span data-ttu-id="5af26-103">Страница **Почта** диалогового окна **Редактор задачи «Отправка почты»** служит для определения получателей, типа и приоритета сообщения.</span><span class="sxs-lookup"><span data-stu-id="5af26-103">Use the **Mail** page of the **Send Mail Task Editor** dialog box to specify recipients, message type, and priority for a message.</span></span> <span data-ttu-id="5af26-104">К сообщению можно также прикрепить файлы.</span><span class="sxs-lookup"><span data-stu-id="5af26-104">You can also attach files to the message.</span></span> <span data-ttu-id="5af26-105">Текстом сообщения может быть введенная строка, соединение с файлом, содержащим текст, или имя переменной, содержащей текст.</span><span class="sxs-lookup"><span data-stu-id="5af26-105">The message text can be a string you provide, a file connection to a file that contains the text, or the name of a variable that contains the text.</span></span>  
  
 <span data-ttu-id="5af26-106">Дополнительные сведения об этой задаче см. в разделе [Send Mail Task](control-flow/send-mail-task.md).</span><span class="sxs-lookup"><span data-stu-id="5af26-106">To learn about this task, see [Send Mail Task](control-flow/send-mail-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5af26-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="5af26-107">Options</span></span>  
 <span data-ttu-id="5af26-108">**SMTPConnection**</span><span class="sxs-lookup"><span data-stu-id="5af26-108">**SMTPConnection**</span></span>  
 <span data-ttu-id="5af26-109">Выберите из списка диспетчер подключений SMTP или нажмите **\<New connection...>** для создания нового диспетчера подключений.</span><span class="sxs-lookup"><span data-stu-id="5af26-109">Select an SMTP connection manager in the list, or click **\<New connection...>** to create a new connection manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5af26-110">Диспетчер SMTP-соединений поддерживает только анонимную проверку подлинности и проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="5af26-110">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="5af26-111">Обычная проверка подлинности не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5af26-111">It does not support basic authentication.</span></span>  
  
 <span data-ttu-id="5af26-112">**См. также:** [Диспетчер SMTP-подключений](connection-manager/smtp-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="5af26-112">**Related Topics:** [SMTP Connection Manager](connection-manager/smtp-connection-manager.md)</span></span>  
  
 <span data-ttu-id="5af26-113">**От**</span><span class="sxs-lookup"><span data-stu-id="5af26-113">**From**</span></span>  
 <span data-ttu-id="5af26-114">Задайте адрес электронной почты отправителя.</span><span class="sxs-lookup"><span data-stu-id="5af26-114">Specify the e-mail address of the sender.</span></span>  
  
 <span data-ttu-id="5af26-115">**Чтобы**</span><span class="sxs-lookup"><span data-stu-id="5af26-115">**To**</span></span>  
 <span data-ttu-id="5af26-116">Укажите адреса электронной почты получателей, разделенные точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="5af26-116">Provide the e-mail addresses of the recipients, delimited by semicolons.</span></span>  
  
 <span data-ttu-id="5af26-117">**Копия**</span><span class="sxs-lookup"><span data-stu-id="5af26-117">**Cc**</span></span>  
 <span data-ttu-id="5af26-118">Задайте адреса электронной почты получателей, которые также получают копии сообщения. Разделяйте адреса точками с запятой.</span><span class="sxs-lookup"><span data-stu-id="5af26-118">Specify the e-mail addresses, delimited by semicolons, of individuals who also receive copies of the message.</span></span>  
  
 <span data-ttu-id="5af26-119">**Скрытая копия**</span><span class="sxs-lookup"><span data-stu-id="5af26-119">**Bcc**</span></span>  
 <span data-ttu-id="5af26-120">Задайте адреса электронной почты получателей, которые получают скрытые копии сообщения. Разделяйте адреса точками с запятой.</span><span class="sxs-lookup"><span data-stu-id="5af26-120">Specify the e-mail addresses, delimited by semicolons, of individuals who receive blind carbon copies (Bcc) copies of the message.</span></span>  
  
 <span data-ttu-id="5af26-121">**Тема**</span><span class="sxs-lookup"><span data-stu-id="5af26-121">**Subject**</span></span>  
 <span data-ttu-id="5af26-122">Укажите тему электронного сообщения.</span><span class="sxs-lookup"><span data-stu-id="5af26-122">Provide a subject for the e-mail message.</span></span>  
  
 <span data-ttu-id="5af26-123">**MessageSourceType**</span><span class="sxs-lookup"><span data-stu-id="5af26-123">**MessageSourceType**</span></span>  
 <span data-ttu-id="5af26-124">Выберите тип источника сообщения.</span><span class="sxs-lookup"><span data-stu-id="5af26-124">Select the source type of the message.</span></span> <span data-ttu-id="5af26-125">Это свойство имеет параметры, указанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="5af26-125">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="5af26-126">Значение</span><span class="sxs-lookup"><span data-stu-id="5af26-126">Value</span></span>|<span data-ttu-id="5af26-127">Описание</span><span class="sxs-lookup"><span data-stu-id="5af26-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5af26-128">**Прямой ввод**</span><span class="sxs-lookup"><span data-stu-id="5af26-128">**Direct input**</span></span>|<span data-ttu-id="5af26-129">Задание источника текста сообщения.</span><span class="sxs-lookup"><span data-stu-id="5af26-129">Set the source to the message text.</span></span> <span data-ttu-id="5af26-130">При выборе этого значения отображается динамический параметр **MessageSource**.</span><span class="sxs-lookup"><span data-stu-id="5af26-130">Selecting this value displays the dynamic option, **MessageSource**.</span></span>|  
|<span data-ttu-id="5af26-131">**Соединение с файлом**</span><span class="sxs-lookup"><span data-stu-id="5af26-131">**File connection**</span></span>|<span data-ttu-id="5af26-132">Задание в качестве источника файла, содержащего текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="5af26-132">Set the source to the file that contains the message text.</span></span> <span data-ttu-id="5af26-133">При выборе этого значения отображается динамический параметр **MessageSource**.</span><span class="sxs-lookup"><span data-stu-id="5af26-133">Selecting this value displays the dynamic option, **MessageSource**.</span></span>|  
|<span data-ttu-id="5af26-134">**Переменная**</span><span class="sxs-lookup"><span data-stu-id="5af26-134">**Variable**</span></span>|<span data-ttu-id="5af26-135">В качестве источника указывается переменная, содержащая текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="5af26-135">Set the source to a variable that contains the message text.</span></span> <span data-ttu-id="5af26-136">При выборе этого значения отображается динамический параметр **MessageSource**.</span><span class="sxs-lookup"><span data-stu-id="5af26-136">Selecting this value displays the dynamic option, **MessageSource**.</span></span>|  
  
 <span data-ttu-id="5af26-137">**Приоритет**</span><span class="sxs-lookup"><span data-stu-id="5af26-137">**Priority**</span></span>  
 <span data-ttu-id="5af26-138">Задается приоритет сообщения.</span><span class="sxs-lookup"><span data-stu-id="5af26-138">Set the priority of the message.</span></span>  
  
 <span data-ttu-id="5af26-139">**Вложения**</span><span class="sxs-lookup"><span data-stu-id="5af26-139">**Attachments**</span></span>  
 <span data-ttu-id="5af26-140">Укажите имена вложений для электронного сообщения, разделенные символом вертикальной черты (|).</span><span class="sxs-lookup"><span data-stu-id="5af26-140">Provide the file names of attachments to the e-mail message, delimited by the pipe (|) character.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5af26-141">Длина строк «Кому», «Копия» и «СК» ограничена 256 символами в соответствии со стандартами Интернета.</span><span class="sxs-lookup"><span data-stu-id="5af26-141">The To, Cc, and Bcc lines are limited to 256 characters in accordance with Internet standards.</span></span>  
  
## <a name="messagesourcetype-dynamic-options"></a><span data-ttu-id="5af26-142">Динамические параметры MessageSourceType</span><span class="sxs-lookup"><span data-stu-id="5af26-142">MessageSourceType Dynamic Options</span></span>  
  
### <a name="messagesourcetype--direct-input"></a><span data-ttu-id="5af26-143">MessageSourceType = Прямой ввод</span><span class="sxs-lookup"><span data-stu-id="5af26-143">MessageSourceType = Direct Input</span></span>  
 <span data-ttu-id="5af26-144">**MessageSource**</span><span class="sxs-lookup"><span data-stu-id="5af26-144">**MessageSource**</span></span>  
 <span data-ttu-id="5af26-145">Введите текст сообщения или нажмите кнопку обзора (...), а затем введите сообщение в диалоговом окне **Источник сообщения**.</span><span class="sxs-lookup"><span data-stu-id="5af26-145">Type the message text or click the browse button (...) and then type the message in the **Message source** dialog box.</span></span>  
  
### <a name="messagesourcetype--file-connection"></a><span data-ttu-id="5af26-146">MessageSourceType = Соединение с файлом</span><span class="sxs-lookup"><span data-stu-id="5af26-146">MessageSourceType = File connection</span></span>  
 <span data-ttu-id="5af26-147">**MessageSource**</span><span class="sxs-lookup"><span data-stu-id="5af26-147">**MessageSource**</span></span>  
 <span data-ttu-id="5af26-148">Выберите в списке диспетчер подключений файлов или щелкните \<**New connection...**>, чтобы создать диспетчер подключений.</span><span class="sxs-lookup"><span data-stu-id="5af26-148">Select a File connection manager in the list or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="5af26-149">**См. также:** подробные сведения о [диспетчере файловых подключений](connection-manager/file-connection-manager.md) и о [редакторе диспетчера файловых подключений](../../2014/integration-services/file-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="5af26-149">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="messagesourcetype--variable"></a><span data-ttu-id="5af26-150">MessageSourceType = Переменная</span><span class="sxs-lookup"><span data-stu-id="5af26-150">MessageSourceType = Variable</span></span>  
 <span data-ttu-id="5af26-151">**MessageSource**</span><span class="sxs-lookup"><span data-stu-id="5af26-151">**MessageSource**</span></span>  
 <span data-ttu-id="5af26-152">Выберите переменную в списке или щелкните \<**New variable...**> для создания переменной.</span><span class="sxs-lookup"><span data-stu-id="5af26-152">Select a variable in the list or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="5af26-153">**См. также:** подробные сведения о [переменных в службах Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) и о [добавлении переменной](../../2014/integration-services/add-variable.md).</span><span class="sxs-lookup"><span data-stu-id="5af26-153">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5af26-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="5af26-154">See Also</span></span>  
 <span data-ttu-id="5af26-155">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="5af26-155">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="5af26-156">[Редактор задачи «Отправка почты» &#40;страница «Общие»&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="5af26-156">[Send Mail Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="5af26-157">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="5af26-157">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
