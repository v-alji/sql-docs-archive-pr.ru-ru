---
title: Редактор диспетчера MSMQ Connection Manager | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msmqconnectionmanager.f1
helpviewer_keywords:
- MSMQ Connection Manager Editor
ms.assetid: ef842cb4-82da-4550-85fe-9bedbc1e77c7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 41d4231ce121d596c8d818485eccf5ddf6127470
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655822"
---
# <a name="msmq-connection-manager-editor"></a><span data-ttu-id="1b02c-102">редактор диспетчера MSMQ-сеансов</span><span class="sxs-lookup"><span data-stu-id="1b02c-102">MSMQ Connection Manager Editor</span></span>
  <span data-ttu-id="1b02c-103">Диалоговое окно **Диспетчер MSMQ-сеансов** используется для указания пути к очереди сообщений MSMQ.</span><span class="sxs-lookup"><span data-stu-id="1b02c-103">Use the **MSMQ Connection Manager** dialog box to specify the path to a Message Queuing (also known as MSMQ) message queue.</span></span>  
  
 <span data-ttu-id="1b02c-104">Дополнительные сведения о диспетчере MSMQ-сеансов см. в разделе [MSMQ Connection Manager](connection-manager/msmq-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="1b02c-104">To learn more about the MSMQ connection manager, see [MSMQ Connection Manager](connection-manager/msmq-connection-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1b02c-105">Диспетчер соединений MSMQ поддерживает локальные частные и общие очереди, а также удаленные общие очереди.</span><span class="sxs-lookup"><span data-stu-id="1b02c-105">The MSMQ connection manager supports local public and private queues and remote public queues.</span></span> <span data-ttu-id="1b02c-106">Он не поддерживает удаленные частные очереди.</span><span class="sxs-lookup"><span data-stu-id="1b02c-106">It does not support remote private queues.</span></span> <span data-ttu-id="1b02c-107">Метод, обходящий это ограничение, использует задачу «Скрипт». Дополнительные сведения см. в разделе [Отправка в удаленную закрытую очередь сообщений в задаче «Скрипт»](control-flow/script-task.md).</span><span class="sxs-lookup"><span data-stu-id="1b02c-107">For a workaround that uses the Script Task, see [Sending to a Remote Private Message Queue with the Script Task](control-flow/script-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1b02c-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="1b02c-108">Options</span></span>  
 <span data-ttu-id="1b02c-109">**Название**</span><span class="sxs-lookup"><span data-stu-id="1b02c-109">**Name**</span></span>  
 <span data-ttu-id="1b02c-110">Задайте уникальное имя для диспетчера MSMQ-сеансов в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="1b02c-110">Provide a unique name for the MSMQ connection manager in the workflow.</span></span> <span data-ttu-id="1b02c-111">Выбранное имя будет отображаться в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1b02c-111">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="1b02c-112">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1b02c-112">**Description**</span></span>  
 <span data-ttu-id="1b02c-113">Задайте описание диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="1b02c-113">Describe the connection manager.</span></span> <span data-ttu-id="1b02c-114">Рекомендуется описать назначение диспетчера соединений, чтобы сделать пакеты самодокументируемыми и более простыми в использовании.</span><span class="sxs-lookup"><span data-stu-id="1b02c-114">As a best practice, describe the connection manager in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="1b02c-115">**Путь**</span><span class="sxs-lookup"><span data-stu-id="1b02c-115">**Path**</span></span>  
 <span data-ttu-id="1b02c-116">Введите полный путь очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="1b02c-116">Type the complete path of the message queue.</span></span> <span data-ttu-id="1b02c-117">Формат пути зависит от типа очереди.</span><span class="sxs-lookup"><span data-stu-id="1b02c-117">The format of the path depends on the type of queue.</span></span>  
  
|<span data-ttu-id="1b02c-118">Тип очереди</span><span class="sxs-lookup"><span data-stu-id="1b02c-118">Queue type</span></span>|<span data-ttu-id="1b02c-119">Образец пути</span><span class="sxs-lookup"><span data-stu-id="1b02c-119">Sample path</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="1b02c-120">Общедоступные</span><span class="sxs-lookup"><span data-stu-id="1b02c-120">Public</span></span>|<span data-ttu-id="1b02c-121">\<computer name>\\<имя очереди\></span><span class="sxs-lookup"><span data-stu-id="1b02c-121">\<computer name>\\<queue name\></span></span>|  
|<span data-ttu-id="1b02c-122">Private</span><span class="sxs-lookup"><span data-stu-id="1b02c-122">Private</span></span>|<span data-ttu-id="1b02c-123">\<computer name>\Private$\\<имя очереди\></span><span class="sxs-lookup"><span data-stu-id="1b02c-123">\<computer name>\Private$\\<queue name\></span></span>|  
  
 <span data-ttu-id="1b02c-124">Для представления локального компьютера можно использовать знак точки «.».</span><span class="sxs-lookup"><span data-stu-id="1b02c-124">You can use "." to represent the local computer.</span></span>  
  
 <span data-ttu-id="1b02c-125">**Тест**</span><span class="sxs-lookup"><span data-stu-id="1b02c-125">**Test**</span></span>  
 <span data-ttu-id="1b02c-126">После настройки диспетчера MSMQ-сеансов убедитесь, что соединение работоспособно, нажав кнопку **Проверка**.</span><span class="sxs-lookup"><span data-stu-id="1b02c-126">After configuring the MSMQ connection manager, confirm that the connection is viable by clicking **Test**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b02c-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="1b02c-127">See Also</span></span>  
 [<span data-ttu-id="1b02c-128">Справочник по сообщениям об ошибках служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="1b02c-128">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
