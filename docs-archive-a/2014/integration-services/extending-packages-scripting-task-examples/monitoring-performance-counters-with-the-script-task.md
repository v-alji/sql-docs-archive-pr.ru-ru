---
title: Наблюдение за счетчиками производительности в задаче "Скрипт" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- performance counters [Integration Services]
- SSIS Script task, performance counters
- custom performance counters [Integration Services]
- Script task [Integration Services], examples
- Script task [Integration Services], performance counters
- counters [Integration Services]
ms.assetid: 86609bf1-cae6-435e-a58d-41bdfc521e94
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 143e11ff966eb11961aa15073a503522c4b9c86b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736572"
---
# <a name="monitoring-performance-counters-with-the-script-task"></a><span data-ttu-id="bf6c3-102">Наблюдение за счетчиками производительности в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="bf6c3-102">Monitoring Performance Counters with the Script Task</span></span>
  <span data-ttu-id="bf6c3-103">Администраторам необходимо наблюдать за производительностью пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], выполняющих сложные преобразования больших объемов данных.</span><span class="sxs-lookup"><span data-stu-id="bf6c3-103">Administrators may need to monitor the performance of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages that perform complex transformations on large amounts of data.</span></span> <span data-ttu-id="bf6c3-104">Пространство имен **System.Diagnostics** платформы [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] предоставляет классы для использования существующих счетчиков производительности и создания собственных счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="bf6c3-104">The **System.Diagnostics** namespace of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides classes for using existing performance counters and for creating your own performance counters.</span></span>  
  
 <span data-ttu-id="bf6c3-105">Счетчики производительности хранят сведения о производительности приложения, которые можно использовать для анализа производительности программного обеспечения по времени.</span><span class="sxs-lookup"><span data-stu-id="bf6c3-105">Performance counters store application performance information that you can use to analyze the performance of software over time.</span></span> <span data-ttu-id="bf6c3-106">За счетчиками производительности можно наблюдать локально или удаленно с помощью средства **Системный монитор**.</span><span class="sxs-lookup"><span data-stu-id="bf6c3-106">Performance counters can be monitored locally or remotely by using the **Performance Monitor** tool.</span></span> <span data-ttu-id="bf6c3-107">Значения счетчиков производительности можно сохранить в переменных, чтобы далее в пакете можно было организовать ветвление потока управления.</span><span class="sxs-lookup"><span data-stu-id="bf6c3-107">You can store the values of performance counters in variables for later control flow branching in the package.</span></span>  
  
 <span data-ttu-id="bf6c3-108">В качестве альтернативы счетчикам производительности можно вызывать событие <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> через свойство <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> объекта `Dts`.</span><span class="sxs-lookup"><span data-stu-id="bf6c3-108">As an alternative to using performance counters, you can raise the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> event through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property of the `Dts` object.</span></span> <span data-ttu-id="bf6c3-109">Событие <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> возвращает среде выполнения служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] как сведения о добавочном ходе выполнения, так и процент завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="bf6c3-109">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> event returns both incremental progress and percentage complete information to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] runtime.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf6c3-110">Если нужно создать задачу, которую будет удобно использовать в нескольких пакетах, рекомендуется начать разработку пользовательской задачи с этого образца задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="bf6c3-110">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="bf6c3-111">Дополнительные сведения см. в разделе [Разработка пользовательской задачи](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="bf6c3-111">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="bf6c3-112">Description</span><span class="sxs-lookup"><span data-stu-id="bf6c3-112">Description</span></span>  
 <span data-ttu-id="bf6c3-113">Следующий пример создает пользовательский счетчик производительности и увеличивает его значение.</span><span class="sxs-lookup"><span data-stu-id="bf6c3-113">The following example creates a custom performance counter and increments the counter.</span></span> <span data-ttu-id="bf6c3-114">Во-первых, пример определяет, существует ли счетчик производительности.</span><span class="sxs-lookup"><span data-stu-id="bf6c3-114">First, the example determines whether the performance counter already exists.</span></span> <span data-ttu-id="bf6c3-115">Если счетчик производительности отсутствует, скрипт вызывает метод `Create` объекта `PerformanceCounterCategory` для его создания.</span><span class="sxs-lookup"><span data-stu-id="bf6c3-115">If the performance counter has not been created, the script calls the `Create` method of the `PerformanceCounterCategory` object to create it.</span></span> <span data-ttu-id="bf6c3-116">После создания счетчика производительности скрипт увеличивает его значение.</span><span class="sxs-lookup"><span data-stu-id="bf6c3-116">After the performance counter has been created, the script increments the counter.</span></span> <span data-ttu-id="bf6c3-117">Наконец, пример следует рекомендациям и вызывает метод `Close` для счетчика производительности, когда он становится ненужным.</span><span class="sxs-lookup"><span data-stu-id="bf6c3-117">Finally, the example follows the best practice of calling the `Close` method on the performance counter when it is no longer needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf6c3-118">Чтобы создать новую категорию счетчика производительности и сам счетчик производительности, необходимы права администратора.</span><span class="sxs-lookup"><span data-stu-id="bf6c3-118">Creating a new performance counter category and performance counter requires administrative rights.</span></span> <span data-ttu-id="bf6c3-119">Кроме того, новая категория и счетчик производительности после создания сохраняются на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bf6c3-119">Also, the new category and counter persist on the computer after creation.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="bf6c3-120">Настройка этого образца задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="bf6c3-120">To configure this Script Task example</span></span>  
  
-   <span data-ttu-id="bf6c3-121">Используйте `Imports` оператор в коде для импорта пространства имен **System. Diagnostics** .</span><span class="sxs-lookup"><span data-stu-id="bf6c3-121">Use an `Imports` statement in your code to import the **System.Diagnostics** namespace.</span></span>  
  
### <a name="example-code"></a><span data-ttu-id="bf6c3-122">Пример кода</span><span class="sxs-lookup"><span data-stu-id="bf6c3-122">Example Code</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim myCounter As PerformanceCounter  
  
    Try  
        'Create the performance counter if it does not already exist.  
        If Not _  
        PerformanceCounterCategory.Exists("TaskExample") Then  
            PerformanceCounterCategory.Create("TaskExample", _  
                "Task Performance Counter Example", "Iterations", _  
                "Number of times this task has been called.")  
        End If  
  
        'Initialize the performance counter.  
        myCounter = New PerformanceCounter("TaskExample", _  
            "Iterations", String.Empty, False)  
  
        'Increment the performance counter.  
        myCounter.Increment()  
  
         myCounter.Close()  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        Dts.Events.FireError(0, _  
            "Task Performance Counter Example", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
```  
  
```csharp  
  
public class ScriptMain  
{  
  
public void Main()  
        {  
  
            PerformanceCounter myCounter;  
  
            try  
            {  
                //Create the performance counter if it does not already exist.  
                if (!PerformanceCounterCategory.Exists("TaskExample"))  
                {  
                    PerformanceCounterCategory.Create("TaskExample", "Task Performance Counter Example", "Iterations", "Number of times this task has been called.");  
                }  
  
                //Initialize the performance counter.  
                myCounter = new PerformanceCounter("TaskExample", "Iterations", String.Empty, false);  
  
                //Increment the performance counter.  
                myCounter.Increment();  
  
                myCounter.Close();  
                Dts.TaskResult = (int)ScriptResults.Success;  
            }  
            catch (Exception ex)  
            {  
                Dts.Events.FireError(0, "Task Performance Counter Example", ex.Message + "\r" + ex.StackTrace, String.Empty, 0);  
                Dts.TaskResult = (int)ScriptResults.Failure;  
            }  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
  
```  
  
<span data-ttu-id="bf6c3-123">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="bf6c3-123">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="bf6c3-124">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="bf6c3-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="bf6c3-125">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="bf6c3-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="bf6c3-126">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="bf6c3-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
