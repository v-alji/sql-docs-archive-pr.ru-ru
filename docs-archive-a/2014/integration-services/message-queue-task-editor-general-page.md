---
title: Редактор задачи «очередь сообщений» (страница «Общие») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msgqueuetask.general.f1
helpviewer_keywords:
- Message Queue Task Editor
ms.assetid: 09368b18-37a5-4321-a173-7cfe5d42d2a2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dcec75f3a4dd85efb7c97226c592d6b1e1bb26ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668996"
---
# <a name="message-queue-task-editor-general-page"></a><span data-ttu-id="5ad0f-102">Редактор задачи «Очередь сообщений» (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="5ad0f-102">Message Queue Task Editor (General Page)</span></span>
  <span data-ttu-id="5ad0f-103">**Страница «Общие»** диалогового окна **Редактор задачи «Очередь сообщений»** позволяет задавать имя и описывать задачу «Очередь сообщений», определять формат сообщений, а также указывать, будет ли задача отправлять или получать сообщения.</span><span class="sxs-lookup"><span data-stu-id="5ad0f-103">Use the **General page** of the **Message Queue Task Editor** dialog box to name and describe the Message Queue task, to specify the message format, and to indicate whether the task sends or receives messages.</span></span>  
  
 <span data-ttu-id="5ad0f-104">Дополнительные сведения об этой задаче см. в разделе [Message Queue Task](control-flow/message-queue-task.md).</span><span class="sxs-lookup"><span data-stu-id="5ad0f-104">To learn about this task, see [Message Queue Task](control-flow/message-queue-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5ad0f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5ad0f-105">Options</span></span>  
 <span data-ttu-id="5ad0f-106">**имя**;</span><span class="sxs-lookup"><span data-stu-id="5ad0f-106">**Name**</span></span>  
 <span data-ttu-id="5ad0f-107">Задайте уникальное имя задаче «Очередь сообщений».</span><span class="sxs-lookup"><span data-stu-id="5ad0f-107">Provide a unique name for the Message Queue task.</span></span> <span data-ttu-id="5ad0f-108">Это имя используется в качестве метки для значка задачи.</span><span class="sxs-lookup"><span data-stu-id="5ad0f-108">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5ad0f-109">Имена задач в пределах пакета должны быть уникальными.</span><span class="sxs-lookup"><span data-stu-id="5ad0f-109">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="5ad0f-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5ad0f-110">**Description**</span></span>  
 <span data-ttu-id="5ad0f-111">Введите описание задачи «Очередь сообщений».</span><span class="sxs-lookup"><span data-stu-id="5ad0f-111">Type a description of the Message Queue task.</span></span>  
  
 <span data-ttu-id="5ad0f-112">**Use2000Format**</span><span class="sxs-lookup"><span data-stu-id="5ad0f-112">**Use2000Format**</span></span>  
 <span data-ttu-id="5ad0f-113">Укажите, нужно ли использовать формат 2000 службы очередей сообщений (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="5ad0f-113">Indicate whether to use the 2000 format of Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="5ad0f-114">Значение по умолчанию — `False`.</span><span class="sxs-lookup"><span data-stu-id="5ad0f-114">The default is `False`.</span></span>  
  
 <span data-ttu-id="5ad0f-115">**MSMQConnection**</span><span class="sxs-lookup"><span data-stu-id="5ad0f-115">**MSMQConnection**</span></span>  
 <span data-ttu-id="5ad0f-116">Выберите существующий диспетчер подключений MSMQ или создайте новый, щелкнув пункт \<**New connection...**>.</span><span class="sxs-lookup"><span data-stu-id="5ad0f-116">Select an existing MSMQ connection manager or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="5ad0f-117">**См. также**: [Диспетчер FTP-соединений](connection-manager/msmq-connection-manager.md), [Редактор диспетчера FTP-соединений](../../2014/integration-services/msmq-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="5ad0f-117">**Related Topics**: [MSMQ Connection Manager](connection-manager/msmq-connection-manager.md), [MSMQ Connection Manager Editor](../../2014/integration-services/msmq-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="5ad0f-118">**Сообщение**</span><span class="sxs-lookup"><span data-stu-id="5ad0f-118">**Message**</span></span>  
 <span data-ttu-id="5ad0f-119">Указывает, будет ли задача «Очередь сообщений» отправлять или получать сообщения.</span><span class="sxs-lookup"><span data-stu-id="5ad0f-119">Specify whether the Message Queue task sends or receive messages.</span></span> <span data-ttu-id="5ad0f-120">При выборе режима **Отправить сообщение**на левой панели диалогового окна появляется страница «Отправка», при выборе режима **Получить сообщение**появляется страница «Получение».</span><span class="sxs-lookup"><span data-stu-id="5ad0f-120">If you select **Send message**, the Send page is listed in the left pane of the dialog box; if you select **Receive message**, the Receive page is listed.</span></span> <span data-ttu-id="5ad0f-121">По умолчанию, устанавливается режим **Отправить сообщение**.</span><span class="sxs-lookup"><span data-stu-id="5ad0f-121">By default, this value is set to **Send message**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ad0f-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="5ad0f-122">See Also</span></span>  
 <span data-ttu-id="5ad0f-123">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="5ad0f-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="5ad0f-124">[Редактор задачи "очередь сообщений" &#40;"получить страницу"&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span><span class="sxs-lookup"><span data-stu-id="5ad0f-124">[Message Queue Task Editor &#40;Receive Page&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span></span>  
 <span data-ttu-id="5ad0f-125">[Редактор задачи "очередь сообщений" &#40;"Отправить страницу"&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span><span class="sxs-lookup"><span data-stu-id="5ad0f-125">[Message Queue Task Editor &#40;Send Page&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span></span>  
 [<span data-ttu-id="5ad0f-126">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="5ad0f-126">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
