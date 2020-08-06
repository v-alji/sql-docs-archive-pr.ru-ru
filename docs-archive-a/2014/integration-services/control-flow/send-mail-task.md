---
title: Задача "Отправка почты" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sendmailtask.f1
helpviewer_keywords:
- mail [Integration Services]
- Send Mail task
- e-mail [Integration Services]
- messages [Integration Services]
- sending messages
ms.assetid: fe0b7cbc-fe8e-4fe2-95b4-2953efff5869
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c93723f3c443705acc14226ce07f456da4d5a884
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656513"
---
# <a name="send-mail-task"></a><span data-ttu-id="1666c-102">Задача «Отправка почты»</span><span class="sxs-lookup"><span data-stu-id="1666c-102">Send Mail Task</span></span>
  <span data-ttu-id="1666c-103">Задача «Отправка почты» производит отправку сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1666c-103">The Send Mail task sends an e-mail message.</span></span> <span data-ttu-id="1666c-104">Эта задача позволяет пакету отправлять сообщения при успешном или неуспешном завершении задач в рабочем процессе пакета либо в ответ на события, инициируемые при выполнении пакета.</span><span class="sxs-lookup"><span data-stu-id="1666c-104">By using the Send Mail task, a package can send messages if tasks in the package workflow succeed or fail, or send messages in response to an event that the package raises at run time.</span></span> <span data-ttu-id="1666c-105">Например, задача может уведомить администратора базы данных об успешном или неуспешном завершении задачи резервного копирования базы данных.</span><span class="sxs-lookup"><span data-stu-id="1666c-105">For example, the task can notify a database administrator about the success or failure of the Backup Database task.</span></span>  
  
 <span data-ttu-id="1666c-106">Задачу «Отправка почты» можно настроить следующими способами:</span><span class="sxs-lookup"><span data-stu-id="1666c-106">You can configure the Send Mail task in the following ways:</span></span>  
  
-   <span data-ttu-id="1666c-107">Укажите текст сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1666c-107">Provide the message text for the e-mail message.</span></span>  
  
-   <span data-ttu-id="1666c-108">Укажите строку темы сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1666c-108">Provide a subject line for the e-mail message.</span></span>  
  
-   <span data-ttu-id="1666c-109">Установите уровень приоритета сообщения.</span><span class="sxs-lookup"><span data-stu-id="1666c-109">Set the priority level of the message.</span></span> <span data-ttu-id="1666c-110">Задача поддерживает три уровня приоритета: обычный, низкий и высокий.</span><span class="sxs-lookup"><span data-stu-id="1666c-110">The task supports three priority levels: normal, low, and high.</span></span>  
  
-   <span data-ttu-id="1666c-111">Укажите получателей в строках «Кому», «Копия» и «Резервная копия».</span><span class="sxs-lookup"><span data-stu-id="1666c-111">Specify the recipients on the To, Cc, and Bcc lines.</span></span> <span data-ttu-id="1666c-112">Если указываются несколько получателей, они должны быть разделены точками с запятой.</span><span class="sxs-lookup"><span data-stu-id="1666c-112">If the task specifies multiple recipients, they are separated by semicolons.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1666c-113">Строки «Кому», «Копия» и «СК» ограничены длиной в 256 символов в соответствии со стандартами Интернета.</span><span class="sxs-lookup"><span data-stu-id="1666c-113">The To, Cc, and Bcc lines are limited to 256 characters each in accordance with Internet standards.</span></span>  
  
-   <span data-ttu-id="1666c-114">Добавьте вложения.</span><span class="sxs-lookup"><span data-stu-id="1666c-114">Include attachments.</span></span> <span data-ttu-id="1666c-115">Если указываются несколько вложений, они должны быть разделены вертикальной чертой (|).</span><span class="sxs-lookup"><span data-stu-id="1666c-115">If the task specifies multiple attachments, they are separated by the pipe (|) character.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1666c-116">Если файл вложения на момент выполнения пакета отсутствует, произойдет ошибка.</span><span class="sxs-lookup"><span data-stu-id="1666c-116">If an attachment file does not exist when the package runs, an error occurs.</span></span>  
  
-   <span data-ttu-id="1666c-117">Укажите используемый диспетчер соединений SMTP.</span><span class="sxs-lookup"><span data-stu-id="1666c-117">Specify the SMTP connection manager to use.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="1666c-118">Диспетчер SMTP-соединений поддерживает только анонимную проверку подлинности и проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="1666c-118">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="1666c-119">Обычная проверка подлинности не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1666c-119">It does not support basic authentication.</span></span>  
  
 <span data-ttu-id="1666c-120">В качестве текста сообщения может быть указана строка, соединение с файлом, содержащим текст, либо имя переменной, в которой содержится текст.</span><span class="sxs-lookup"><span data-stu-id="1666c-120">The message text can be a string that you provide, a connection to a file that contains the text, or the name of a variable that contains the text.</span></span> <span data-ttu-id="1666c-121">Подключение к файлу производится задачей при помощи диспетчера подключения файлов.</span><span class="sxs-lookup"><span data-stu-id="1666c-121">The task uses a File connection manager to connect to a file.</span></span> <span data-ttu-id="1666c-122">Дополнительные сведения см. в статье [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="1666c-122">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="1666c-123">Задача производит подключение к почтовому серверу при помощи диспетчера соединений SMTP.</span><span class="sxs-lookup"><span data-stu-id="1666c-123">The task uses an SMTP connection manager to connect to a mail server.</span></span> <span data-ttu-id="1666c-124">Дополнительные сведения см. в статье [SMTP Connection Manager](../connection-manager/smtp-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="1666c-124">For more information, see [SMTP Connection Manager](../connection-manager/smtp-connection-manager.md).</span></span>  
  
## <a name="custom-logging-messages-available-on-the-send-mail-task"></a><span data-ttu-id="1666c-125">Пользовательские сообщения для ведения журнала, доступные в задаче «Отправка почты»</span><span class="sxs-lookup"><span data-stu-id="1666c-125">Custom Logging Messages Available on the Send Mail Task</span></span>  
 <span data-ttu-id="1666c-126">В следующей таблице перечислены пользовательские записи в журнале для задачи «Отправка почты».</span><span class="sxs-lookup"><span data-stu-id="1666c-126">The following table lists the custom log entries for the Send Mail task.</span></span> <span data-ttu-id="1666c-127">Дополнительные сведения см. в разделах [Ведение журналов в службах Integration Services (SSIS)](../performance/integration-services-ssis-logging.md) и [Пользовательские сообщения для ведения журнала](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="1666c-127">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="1666c-128">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="1666c-128">Log entry</span></span>|<span data-ttu-id="1666c-129">Описание</span><span class="sxs-lookup"><span data-stu-id="1666c-129">Description</span></span>|  
|---------------|-----------------|  
|`SendMailTaskBegin`|<span data-ttu-id="1666c-130">Указывает, что задача приступила к отправке сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1666c-130">Indicates that the task began to send an e-mail message.</span></span>|  
|`SendMailTaskEnd`|<span data-ttu-id="1666c-131">Указывает, что задача завершила отправку сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1666c-131">Indicates that the task finished sending an e-mail message.</span></span>|  
|`SendMailTaskInfo`|<span data-ttu-id="1666c-132">Выводит описательные сведения об этой задаче.</span><span class="sxs-lookup"><span data-stu-id="1666c-132">Provides descriptive information about the task.</span></span>|  
  
## <a name="configuring-the-send-mail-task"></a><span data-ttu-id="1666c-133">Настройка задачи «Отправка почты»</span><span class="sxs-lookup"><span data-stu-id="1666c-133">Configuring the Send Mail Task</span></span>  
 <span data-ttu-id="1666c-134">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="1666c-134">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="1666c-135">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="1666c-135">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="1666c-136">Редактор задачи "Отправка почты" (страница "Общие")</span><span class="sxs-lookup"><span data-stu-id="1666c-136">Send Mail Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="1666c-137">Редактор задачи "Отправка почты" (страница "Почта")</span><span class="sxs-lookup"><span data-stu-id="1666c-137">Send Mail Task Editor &#40;Mail Page&#41;</span></span>](../send-mail-task-editor-mail-page.md)  
  
-   [<span data-ttu-id="1666c-138">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="1666c-138">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="1666c-139">Сведения о задании этих свойств программными средствами см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="1666c-139">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.SendMailTask.SendMailTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="1666c-140">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="1666c-140">Related Tasks</span></span>  
 <span data-ttu-id="1666c-141">Дополнительные сведения о настройке свойств этих свойств в конструкторе [!INCLUDE[ssIS](../../includes/ssis-md.md)] см. в разделе [Задание свойств задач или контейнеров](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="1666c-141">For information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="1666c-142">См. также</span><span class="sxs-lookup"><span data-stu-id="1666c-142">Related Content</span></span>  
  
-   <span data-ttu-id="1666c-143">Техническая статья [oтправка электронной почты с уведомлением доставки в C#](https://go.microsoft.com/fwlink/?LinkId=237625)на сайте shareourideas.com</span><span class="sxs-lookup"><span data-stu-id="1666c-143">Technical article, [How to send email with delivery notification in C#](https://go.microsoft.com/fwlink/?LinkId=237625), on shareourideas.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1666c-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="1666c-144">See Also</span></span>  
 <span data-ttu-id="1666c-145">[Задачи служб Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="1666c-145">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="1666c-146">Поток управления</span><span class="sxs-lookup"><span data-stu-id="1666c-146">Control Flow</span></span>](control-flow.md)  
  
  
