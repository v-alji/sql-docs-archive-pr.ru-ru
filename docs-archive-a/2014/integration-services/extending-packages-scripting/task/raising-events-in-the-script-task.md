---
title: Вызов событий в задаче "Скрипт" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- events [Integration Services], scripts
- warnings [Integration Services]
- SSIS events, scripts
- errors [Integration Services], events
- SSIS Script task, events
- Events property
- Script task [Integration Services], events
ms.assetid: 21ea07d1-e267-4fb1-a6cc-82c95a39beae
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e20a276b91e434b6915cfb218eba17c07acd6544
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731894"
---
# <a name="raising-events-in-the-script-task"></a><span data-ttu-id="939b3-102">Вызов событий в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="939b3-102">Raising Events in the Script Task</span></span>
  <span data-ttu-id="939b3-103">События позволяют сообщать об ошибках и предупреждениях, а также передавать другие сведения, например о ходе выполнения задачи или ее состоянии, в пакет, содержащий задачу.</span><span class="sxs-lookup"><span data-stu-id="939b3-103">Events provide a way to report errors, warnings, and other information, such as task progress or status, to the containing package.</span></span> <span data-ttu-id="939b3-104">Пакет предоставляет обработчики событий для управления уведомлениями о событиях.</span><span class="sxs-lookup"><span data-stu-id="939b3-104">The package provides event handlers for managing event notifications.</span></span> <span data-ttu-id="939b3-105">Задача «Скрипт» может создавать события, вызывая методы свойства <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> объекта `Dts`.</span><span class="sxs-lookup"><span data-stu-id="939b3-105">The Script task can raise events by calling methods on the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property of the `Dts` object.</span></span> <span data-ttu-id="939b3-106">Дополнительные сведения о том, как пакеты службы [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] обрабатывают события, см. в разделе [Обработчики событий в службах Integration Services (SSIS)](../../integration-services-ssis-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="939b3-106">For more information about how [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages handle events, see [Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md).</span></span>  
  
 <span data-ttu-id="939b3-107">События могут регистрироваться любым регистратором, включенным в пакете.</span><span class="sxs-lookup"><span data-stu-id="939b3-107">Events can be logged to any log provider that is enabled in the package.</span></span> <span data-ttu-id="939b3-108">Регистраторы сохраняют сведения о событиях в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="939b3-108">Log providers store information about events in a data store.</span></span> <span data-ttu-id="939b3-109">Задача «Скрипт» может также использовать метод <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> для занесения записей в регистратор без вызова событий.</span><span class="sxs-lookup"><span data-stu-id="939b3-109">The Script task can also use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method to log information to a log provider without raising an event.</span></span> <span data-ttu-id="939b3-110">Дополнительные сведения об использовании метода <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> см. в разделе [Ведение журналов в задаче "Скрипт"](logging-in-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="939b3-110">For more information about how to use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method, see [Logging in the Script Task](logging-in-the-script-task.md).</span></span>  
  
 <span data-ttu-id="939b3-111">Для вызова события задача «Скрипт» вызывает один из методов, предоставляемых свойством <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>.</span><span class="sxs-lookup"><span data-stu-id="939b3-111">To raise an event, the Script task calls one of the methods exposed by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property.</span></span> <span data-ttu-id="939b3-112">В следующей таблице перечислены методы, предоставляемые свойством <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>.</span><span class="sxs-lookup"><span data-stu-id="939b3-112">The following table lists the methods exposed by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property.</span></span>  
  
|<span data-ttu-id="939b3-113">Событие</span><span class="sxs-lookup"><span data-stu-id="939b3-113">Event</span></span>|<span data-ttu-id="939b3-114">Description</span><span class="sxs-lookup"><span data-stu-id="939b3-114">Description</span></span>|  
|-----------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A>|<span data-ttu-id="939b3-115">Вызывает в пакете определяемое пользователем событие.</span><span class="sxs-lookup"><span data-stu-id="939b3-115">Raises a user-defined custom event in the package.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A>|<span data-ttu-id="939b3-116">Извещает пакет об ошибке.</span><span class="sxs-lookup"><span data-stu-id="939b3-116">Informs the package of an error condition.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireInformation%2A>|<span data-ttu-id="939b3-117">Передает сведения пользователю.</span><span class="sxs-lookup"><span data-stu-id="939b3-117">Provides information to the user.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A>|<span data-ttu-id="939b3-118">Информирует пакет о ходе выполнения задачи.</span><span class="sxs-lookup"><span data-stu-id="939b3-118">Informs the package of the progress of the task.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireQueryCancel%2A>|<span data-ttu-id="939b3-119">Возвращает значение, которое указывает, нужно ли пакету, чтобы задача преждевременно прервала выполнение.</span><span class="sxs-lookup"><span data-stu-id="939b3-119">Returns a value that indicates whether the package needs the task to shut down prematurely.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A>|<span data-ttu-id="939b3-120">Информирует пакет, что задача находится в состоянии, которое требует уведомить пользователя, но не является состоянием ошибки.</span><span class="sxs-lookup"><span data-stu-id="939b3-120">Informs the package that the task is in a state that warrants user notification, but is not an error condition.</span></span>|  
  
## <a name="events-example"></a><span data-ttu-id="939b3-121">Пример события</span><span class="sxs-lookup"><span data-stu-id="939b3-121">Events Example</span></span>  
 <span data-ttu-id="939b3-122">В следующем примере демонстрируется вызов событий изнутри задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="939b3-122">The following example demonstrates how to raise events from within the Script task.</span></span> <span data-ttu-id="939b3-123">Пример использует собственную функцию API Windows, чтобы определить, доступно ли соединение с Интернетом.</span><span class="sxs-lookup"><span data-stu-id="939b3-123">The example uses a native Windows API function to determine whether an Internet connection is available.</span></span> <span data-ttu-id="939b3-124">Если соединения нет, создается ошибка.</span><span class="sxs-lookup"><span data-stu-id="939b3-124">If no connection is available, it raises an error.</span></span> <span data-ttu-id="939b3-125">Если используется потенциально нестабильное соединение по модему, пример формирует предупреждение.</span><span class="sxs-lookup"><span data-stu-id="939b3-125">If a potentially volatile modem connection is in use, the example raises a warning.</span></span> <span data-ttu-id="939b3-126">В противном случае возвращается информационное сообщение, что соединение с Интернетом обнаружено.</span><span class="sxs-lookup"><span data-stu-id="939b3-126">Otherwise, it returns an informational message that an Internet connection has been detected.</span></span>  
  
```vb  
Private Declare Function InternetGetConnectedState Lib "wininet" _  
    (ByRef dwFlags As Long, ByVal dwReserved As Long) As Long  
  
Private Enum ConnectedStates  
    LAN = &H2  
    Modem = &H1  
    Proxy = &H4  
    Offline = &H20  
    Configured = &H40  
    RasInstalled = &H10  
End Enum  
  
Public Sub Main()  
  
    Dim dwFlags As Long  
    Dim connectedState As Long  
    Dim fireAgain as Boolean  
  
    connectedState = InternetGetConnectedState(dwFlags, 0)  
  
    If connectedState <> 0 Then  
        If (dwFlags And ConnectedStates.Modem) = ConnectedStates.Modem Then  
            Dts.Events.FireWarning(0, "Script Task Example", _  
                "Volatile Internet connection detected.", String.Empty, 0)  
        Else  
            Dts.Events.FireInformation(0, "Script Task Example", _  
                "Internet connection detected.", String.Empty, 0, fireAgain)  
        End If  
    Else  
        ' If not connected to the Internet, raise an error.  
        Dts.Events.FireError(0, "Script Task Example", _  
            "Internet connection not available.", String.Empty, 0)  
    End If  
  
    Dts.TaskResult = ScriptResults.Success  
  
End Sub  
```  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Windows.Forms;  
using System.Runtime.InteropServices;  
  
public class ScriptMain  
{  
  
[DllImport("wininet")]  
        private extern static long InternetGetConnectedState(ref long dwFlags, long dwReserved);  
  
        private enum ConnectedStates  
        {  
            LAN = 0x2,  
            Modem = 0x1,  
            Proxy = 0x4,  
            Offline = 0x20,  
            Configured = 0x40,  
            RasInstalled = 0x10  
        };  
  
        public void Main()  
        {  
            //  
            long dwFlags = 0;  
            long connectedState;  
            bool fireAgain = true;  
            int state;  
  
            connectedState = InternetGetConnectedState(ref dwFlags, 0);  
            state = (int)ConnectedStates.Modem;  
            if (connectedState != 0)  
            {  
                if ((dwFlags & state) == state)  
                {  
                    Dts.Events.FireWarning(0, "Script Task Example", "Volatile Internet connection detected.", String.Empty, 0);  
                }  
                else  
                {  
                    Dts.Events.FireInformation(0, "Script Task Example", "Internet connection detected.", String.Empty, 0, ref fireAgain);  
                }  
            }  
            else  
            {  
                // If not connected to the Internet, raise an error.  
                Dts.Events.FireError(0, "Script Task Example", "Internet connection not available.", String.Empty, 0);  
            }  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
  
```  
  
<span data-ttu-id="939b3-127">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="939b3-127">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="939b3-128">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="939b3-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="939b3-129">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="939b3-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="939b3-130">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="939b3-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="939b3-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="939b3-131">See Also</span></span>  
 <span data-ttu-id="939b3-132">[Обработчики событий в службах Integration Services (SSIS)](../../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="939b3-132">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="939b3-133">Добавление обработчика событий к пакету</span><span class="sxs-lookup"><span data-stu-id="939b3-133">Add an Event Handler to a Package</span></span>](../../add-an-event-handler-to-a-package.md)  
  
  
