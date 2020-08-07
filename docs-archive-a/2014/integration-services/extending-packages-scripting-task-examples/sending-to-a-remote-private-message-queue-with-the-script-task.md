---
title: Отправка в удаленную закрытую очередь сообщений в задаче "Скрипт" | Документы Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], remote private message queues
- Message Queue task [Integration Services]
- Script task [Integration Services], examples
ms.assetid: 636314fd-d099-45cd-8bb4-f730d0a06739
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 308815293dfc41f0a0ac60c21ce7f561a5e7f660
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732737"
---
# <a name="sending-to-a-remote-private-message-queue-with-the-script-task"></a><span data-ttu-id="dda4f-102">Отправка в удаленную закрытую очередь сообщений в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="dda4f-102">Sending to a Remote Private Message Queue with the Script Task</span></span>
  <span data-ttu-id="dda4f-103">Служба очередей сообщений (называемая также MSMQ) облегчает разработчикам обеспечение быстрой и надежной связи с прикладными программами при помощи отправки и получения сообщений.</span><span class="sxs-lookup"><span data-stu-id="dda4f-103">Message Queuing (also known as MSMQ) makes it easy for developers to communicate with application programs quickly and reliably by sending and receiving messages.</span></span> <span data-ttu-id="dda4f-104">Очередь сообщений может находиться в локальном или в удаленном компьютере и может быть открытой или закрытой.</span><span class="sxs-lookup"><span data-stu-id="dda4f-104">A message queue may be located on the local computer or a remote computer, and may be public or private.</span></span> <span data-ttu-id="dda4f-105">В службах [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] диспетчер соединений MSMQ и задача «Очередь сообщений» не поддерживают отправку в закрытую очередь на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="dda4f-105">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], the MSMQ connection manager and Message Queue task do not support sending to a private queue on a remote computer.</span></span> <span data-ttu-id="dda4f-106">Но при использовании задачи «Скрипт» можно легко отправить сообщение в удаленную закрытую очередь.</span><span class="sxs-lookup"><span data-stu-id="dda4f-106">However, by using the Script task, it is easy to send a message to a remote private queue.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dda4f-107">Если нужно создать задачу, которую будет удобно использовать в нескольких пакетах, рекомендуется начать разработку пользовательской задачи с этого образца задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="dda4f-107">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="dda4f-108">Дополнительные сведения см. в разделе [Разработка пользовательской задачи](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="dda4f-108">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="dda4f-109">Description</span><span class="sxs-lookup"><span data-stu-id="dda4f-109">Description</span></span>  
 <span data-ttu-id="dda4f-110">В следующем примере для отправки текста (содержащегося в переменной пакета) в удаленную закрытую очередь сообщений используется существующий диспетчер соединений MSMQ вместе с объектами и методами из пространства имен System.Messaging.</span><span class="sxs-lookup"><span data-stu-id="dda4f-110">The following example uses an existing MSMQ connection manager, together with objects and methods from the System.Messaging namespace, to send the text contained in a package variable to a remote private message queue.</span></span> <span data-ttu-id="dda4f-111">Вызов метода М:Микрософт.склсервер.ДТС.манажедконнектионс.мсмкконн.аккуиреконнектион (System. Object) диспетчера соединений MSMQ возвращает объект **MessageQueue** , метод которого выполняет `Send` эту задачу.</span><span class="sxs-lookup"><span data-stu-id="dda4f-111">The call to the M:Microsoft.SqlServer.Dts.ManagedConnections.MSMQConn.AcquireConnection(System.Object) method of the MSMQ connection manager returns a **MessageQueue** object whose `Send` method accomplishes this task.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="dda4f-112">Настройка этого образца задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="dda4f-112">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="dda4f-113">Создайте диспетчер соединений MSMQ с именем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dda4f-113">Create an MSMQ connection manager with the default name.</span></span> <span data-ttu-id="dda4f-114">Установите путь к допустимой удаленной закрытой очереди в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="dda4f-114">Set the path of a valid remote private queue, in the following format:</span></span>  
  
    ```  
    FORMATNAME:DIRECT=OS:<computername>\private$\<queuename>  
    ```  
  
2.  <span data-ttu-id="dda4f-115">Создайте [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] переменную с именем **MessageText** типа `String` , чтобы передать текст сообщения в скрипт.</span><span class="sxs-lookup"><span data-stu-id="dda4f-115">Create an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable named **MessageText** of type `String` to pass the message text into the script.</span></span> <span data-ttu-id="dda4f-116">Введите сообщение по умолчанию как значение переменной.</span><span class="sxs-lookup"><span data-stu-id="dda4f-116">Enter a default message as the value of the variable.</span></span>  
  
3.  <span data-ttu-id="dda4f-117">Добавьте задачу «Скрипт» в область конструктора и измените ее.</span><span class="sxs-lookup"><span data-stu-id="dda4f-117">Add a Script Task to the design surface and edit it.</span></span> <span data-ttu-id="dda4f-118">На вкладке **Скрипт** **редактора задачи "Скрипт"** добавьте переменную `MessageText` к свойству **ReadOnlyVariables**, чтобы сделать переменную доступной в скрипте.</span><span class="sxs-lookup"><span data-stu-id="dda4f-118">On the **Script** tab of the **Script Task Editor**, add the `MessageText` variable to the **ReadOnlyVariables** property to make the variable available inside the script.</span></span>  
  
4.  <span data-ttu-id="dda4f-119">Нажмите кнопку **Изменить скрипт**, чтобы открыть редактор скриптов средств [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] для приложений (VSTA).</span><span class="sxs-lookup"><span data-stu-id="dda4f-119">Click **Edit Script** to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) script editor.</span></span>  
  
5.  <span data-ttu-id="dda4f-120">В проект скрипта добавьте ссылку на пространство имен `System.Messaging`.</span><span class="sxs-lookup"><span data-stu-id="dda4f-120">Add a reference in the script project to the `System.Messaging` namespace.</span></span>  
  
6.  <span data-ttu-id="dda4f-121">Замените содержимое окна скрипта кодом из следующего раздела.</span><span class="sxs-lookup"><span data-stu-id="dda4f-121">Replace the contents of the script window with the code in the following section.</span></span>  
  
## <a name="code"></a><span data-ttu-id="dda4f-122">Код</span><span class="sxs-lookup"><span data-stu-id="dda4f-122">Code</span></span>  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports System.Messaging  
  
Public Class ScriptMain  
  
    Public Sub Main()  
  
        Dim remotePrivateQueue As MessageQueue  
        Dim messageText As String  
  
        remotePrivateQueue = _  
            DirectCast(Dts.Connections("Message Queue Connection Manager").AcquireConnection(Dts.Transaction), _  
            MessageQueue)  
        messageText = DirectCast(Dts.Variables("MessageText").Value, String)  
        remotePrivateQueue.Send(messageText)  
  
        Dts.TaskResult = ScriptResults.Success  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Messaging;  
  
public class ScriptMain  
{  
  
    public void Main()  
        {  
  
            MessageQueue remotePrivateQueue = new MessageQueue();  
            string messageText;  
  
            remotePrivateQueue = (MessageQueue)(Dts.Connections["Message Queue Connection Manager"].AcquireConnection(Dts.Transaction) as MessageQueue);  
            messageText = (string)(Dts.Variables["MessageText"].Value);  
            remotePrivateQueue.Send(messageText);  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
  
}  
```  
  
<span data-ttu-id="dda4f-123">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="dda4f-123">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="dda4f-124">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="dda4f-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="dda4f-125">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="dda4f-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="dda4f-126">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="dda4f-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dda4f-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="dda4f-127">See Also</span></span>  
 [<span data-ttu-id="dda4f-128">Задача «Очередь сообщений»</span><span class="sxs-lookup"><span data-stu-id="dda4f-128">Message Queue Task</span></span>](../control-flow/message-queue-task.md)  
  
  
