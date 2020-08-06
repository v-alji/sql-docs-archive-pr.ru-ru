---
title: Диспетчер подключений MSMQ | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], message queues
- connection managers [Integration Services], MSMQ
- MSMQ connection manager
- message queue connections [Integration Services]
ms.assetid: a86900e2-450e-479f-b207-e1b02361d395
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0c51866eeef281f6587bf281461e4faa2278308d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667356"
---
# <a name="msmq-connection-manager"></a><span data-ttu-id="3e177-102">диспетчер соединений MSMQ</span><span class="sxs-lookup"><span data-stu-id="3e177-102">MSMQ Connection Manager</span></span>
  <span data-ttu-id="3e177-103">Диспетчер соединений MSMQ позволяет пакетам соединяться с очередями сообщений, которые используют службу очередей сообщений (также называемую MSMQ).</span><span class="sxs-lookup"><span data-stu-id="3e177-103">An MSMQ connection manager enables a package to connect to a message queue that uses Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="3e177-104">Задача "Очередь сообщений", содержащаяся в службах [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], использует диспетчер соединений MSMQ.</span><span class="sxs-lookup"><span data-stu-id="3e177-104">The Message Queue task that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses an MSMQ connection manager.</span></span>  
  
 <span data-ttu-id="3e177-105">При добавлении к пакету диспетчера MSMQ-сеансов службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] создают диспетчер соединений, который будет решать задачи MSMQ-сеансов во время работы, устанавливает свойства диспетчера соединений и добавляет его к коллекции пакета `Connections`.</span><span class="sxs-lookup"><span data-stu-id="3e177-105">When you add an MSMQ connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an MSMQ connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="3e177-106">Свойству `ConnectionManagerType` диспетчера соединений присваивается значение `MSMQ`.</span><span class="sxs-lookup"><span data-stu-id="3e177-106">The `ConnectionManagerType` property of the connection manager is set to `MSMQ`.</span></span>  
  
 <span data-ttu-id="3e177-107">Настроить диспетчер соединений MSMQ можно следующими способами.</span><span class="sxs-lookup"><span data-stu-id="3e177-107">You can configure an MSMQ connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="3e177-108">Указать строку соединения.</span><span class="sxs-lookup"><span data-stu-id="3e177-108">Provide a connection string.</span></span>  
  
-   <span data-ttu-id="3e177-109">Указать путь к очереди сообщений для подключения.</span><span class="sxs-lookup"><span data-stu-id="3e177-109">Provide the path of the message queue to connect to.</span></span>  
  
 <span data-ttu-id="3e177-110">Формат пути зависит от типа очереди, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="3e177-110">The format of the path depends on the type of queue, as shown in the following table.</span></span>  
  
|<span data-ttu-id="3e177-111">Тип очереди</span><span class="sxs-lookup"><span data-stu-id="3e177-111">Queue type</span></span>|<span data-ttu-id="3e177-112">Образец пути</span><span class="sxs-lookup"><span data-stu-id="3e177-112">Sample path</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="3e177-113">Общедоступные</span><span class="sxs-lookup"><span data-stu-id="3e177-113">Public</span></span>|<span data-ttu-id="3e177-114">\<computer name>\\<имя очереди\></span><span class="sxs-lookup"><span data-stu-id="3e177-114">\<computer name>\\<queue name\></span></span>|  
|<span data-ttu-id="3e177-115">Private</span><span class="sxs-lookup"><span data-stu-id="3e177-115">Private</span></span>|<span data-ttu-id="3e177-116">\<computer name>\Private$\\<имя очереди\></span><span class="sxs-lookup"><span data-stu-id="3e177-116">\<computer name>\Private$\\<queue name\></span></span>|  
  
 <span data-ttu-id="3e177-117">Для представления локального компьютера можно использовать знак точки («.»).</span><span class="sxs-lookup"><span data-stu-id="3e177-117">You can use a period (.) to represent the local computer.</span></span>  
  
## <a name="configuration-of-the-msmq-connection-manager"></a><span data-ttu-id="3e177-118">Настройка диспетчера соединений MSMQ</span><span class="sxs-lookup"><span data-stu-id="3e177-118">Configuration of the MSMQ Connection Manager</span></span>  
 <span data-ttu-id="3e177-119">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="3e177-119">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="3e177-120">Дополнительные сведения о свойствах, которые можно задавать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в статье [Редактор диспетчера MSMQ-сеансов](../msmq-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="3e177-120">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [MSMQ Connection Manager Editor](../msmq-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="3e177-121">Дополнительные сведения о программной настройке диспетчера подключений см. в разделах <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> и [Добавление соединений программным образом](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="3e177-121">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e177-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="3e177-122">See Also</span></span>  
 <span data-ttu-id="3e177-123">[Задача «Очередь сообщений»](../control-flow/message-queue-task.md) </span><span class="sxs-lookup"><span data-stu-id="3e177-123">[Message Queue Task](../control-flow/message-queue-task.md) </span></span>  
 [<span data-ttu-id="3e177-124">Соединения в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="3e177-124">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
