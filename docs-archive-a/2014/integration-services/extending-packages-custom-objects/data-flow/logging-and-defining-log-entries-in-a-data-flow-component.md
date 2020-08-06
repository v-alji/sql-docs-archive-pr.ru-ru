---
title: Ведение журнала и определение элементов журнала в компоненте потока данных | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- logs [Integration Services], custom
- custom log entries [Integration Services]
- custom data flow components [Integration Services], logging
- data flow components [Integration Services], logging
ms.assetid: 2190dba9-59b5-480b-b8e9-21d5a54c5917
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 14dfec71679bbe455ae8be5face98b776a80b9e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729641"
---
# <a name="logging-and-defining-log-entries-in-a-data-flow-component"></a><span data-ttu-id="28390-102">Ведение журнала и определение элементов журнала в компоненте потока данных</span><span class="sxs-lookup"><span data-stu-id="28390-102">Logging and Defining Log Entries in a Data Flow Component</span></span>
  <span data-ttu-id="28390-103">Пользовательские компоненты потока данных могут помещать сообщения в существующую запись журнала с помощью метода <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.PostLogMessage%2A> интерфейса <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>.</span><span class="sxs-lookup"><span data-stu-id="28390-103">Custom data flow components can post messages to an existing log entry by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.PostLogMessage%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span> <span data-ttu-id="28390-104">Они могут также предоставлять информацию для пользователя с помощью метода <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireInformation%2A> или подобных методов интерфейса <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>.</span><span class="sxs-lookup"><span data-stu-id="28390-104">They can also present information to the user by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireInformation%2A> method or similar methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span> <span data-ttu-id="28390-105">Однако этот подход создает нагрузку по вызову и обработке дополнительных событий и заставляет пользователя фильтровать многочисленные информационные сообщения в поисках сообщений, которые могут представлять интерес.</span><span class="sxs-lookup"><span data-stu-id="28390-105">However, this approach incurs the overhead of raising and handling additional events, and forces the user to sift through verbose informational messages for the messages that may be of interest to them.</span></span> <span data-ttu-id="28390-106">Можно использовать собственный формат записи журнала, как показано далее, для предоставления пользователям разработанного компонента точно обозначенной информации.</span><span class="sxs-lookup"><span data-stu-id="28390-106">You can use a custom log entry as described below to provide distinctly labeled custom log information to users of your component.</span></span>  
  
## <a name="registering-and-using-a-custom-log-entry"></a><span data-ttu-id="28390-107">Регистрация и использование пользовательской записи журнала</span><span class="sxs-lookup"><span data-stu-id="28390-107">Registering and Using a Custom Log Entry</span></span>  
  
### <a name="registering-a-custom-log-entry"></a><span data-ttu-id="28390-108">Регистрация пользовательской записи журнала</span><span class="sxs-lookup"><span data-stu-id="28390-108">Registering a Custom Log Entry</span></span>  
 <span data-ttu-id="28390-109">Для регистрации пользовательской записи журнала, чтобы ее мог использовать разрабатываемый компонент, нужно переопределить метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterLogEntries%2A> базового класса <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>.</span><span class="sxs-lookup"><span data-stu-id="28390-109">To register a custom log entry for use by your component, override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterLogEntries%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class.</span></span> <span data-ttu-id="28390-110">В следующем примере проводится регистрация пользовательской записи журнала и передается имя и описание.</span><span class="sxs-lookup"><span data-stu-id="28390-110">The following example registers a custom log entry and provides a name and description.</span></span>  
  
```csharp  
using Microsoft.SqlServer.Dts.Runtime;  
...  
private const string MyLogEntryName = "My Custom Component Log Entry";  
private const string MyLogEntryDescription = "Log entry from My Custom Component ";  
...  
    public override void RegisterLogEntries()  
    {  
      this.LogEntryInfos.Add(MyLogEntryName,  
        MyLogEntryDescription,  
        Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT);  
    }  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
...  
Private Const MyLogEntryName As String = "My Custom Component Log Entry"   
Private Const MyLogEntryDescription As String = "Log entry from My Custom Component "  
...  
Public  Overrides Sub RegisterLogEntries()   
  Me.LogEntryInfos.Add(MyLogEntryName, _  
    MyLogEntryDescription, _  
    Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT)   
End Sub  
```  
  
 <span data-ttu-id="28390-111">Перечисление <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency> подсказывает во время выполнения, как часто событие будет заноситься в журнал.</span><span class="sxs-lookup"><span data-stu-id="28390-111">The <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency> enumeration provides a hint to the runtime about how frequently the event will be logged:</span></span>  
  
-   <span data-ttu-id="28390-112"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_OCCASIONAL>: событие заносится в журнал только иногда, но не во время каждого выполнения.</span><span class="sxs-lookup"><span data-stu-id="28390-112"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_OCCASIONAL>: Event is logged only sometimes, not during every execution.</span></span>  
  
-   <span data-ttu-id="28390-113"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT>: событие заносится в журнал определенное количество раз во время каждого выполнения.</span><span class="sxs-lookup"><span data-stu-id="28390-113"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT>: Event is logged a constant number of times during every execution.</span></span>  
  
-   <span data-ttu-id="28390-114"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_PROPORTIONAL>: событие заносится в журнал несколько раз пропорционально объему выполненной работы.</span><span class="sxs-lookup"><span data-stu-id="28390-114"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_PROPORTIONAL>: Event is logged a number of times proportional to the amount of work completed.</span></span>  
  
 <span data-ttu-id="28390-115">В приведенном выше примере используется значение <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT>, поскольку ожидается, что компонент будет создавать запись в журнале один раз во время каждого выполнения.</span><span class="sxs-lookup"><span data-stu-id="28390-115">The example above uses <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT> because the component expects to log an entry once per execution.</span></span>  
  
 <span data-ttu-id="28390-116">После регистрации собственного формата записи журнала и добавления экземпляра пользовательского компонента в рабочую область конструктора потока данных диалоговое окно **Ведение журнала** в конструкторе выводит новую запись журнала с именем "Мой собственный формат записи журнала" в списке доступных записей журнала.</span><span class="sxs-lookup"><span data-stu-id="28390-116">After registering the custom log entry and adding an instance of your custom component to the data flow designer surface, the **Logging** dialog box in the designer displays a new log entry with the name "My Custom Component Log Entry" in the list of available log entries.</span></span>  
  
### <a name="logging-to-a-custom-log-entry"></a><span data-ttu-id="28390-117">Внесение в журнал пользовательской записи</span><span class="sxs-lookup"><span data-stu-id="28390-117">Logging to a Custom Log Entry</span></span>  
 <span data-ttu-id="28390-118">После регистрации пользовательской записи журнала компонент может создавать такие записи в журнале.</span><span class="sxs-lookup"><span data-stu-id="28390-118">After registering the custom log entry, the component can now log custom messages.</span></span> <span data-ttu-id="28390-119">В приведенном ниже примере пользовательская запись журнала заносится в журнал во время работы метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>, содержащего текст инструкции SQL, используемой компонентом.</span><span class="sxs-lookup"><span data-stu-id="28390-119">The example below writes a custom log entry during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method that contains the text of a SQL statement used by the component.</span></span>  
  
```csharp  
public override void PreExecute()  
{  
  DateTime now = DateTime.Now;  
  byte[] additionalData = null;  
  this.ComponentMetaData.PostLogMessage(MyLogEntryName,  
    this.ComponentMetaData.Name,  
    "Command Sent was: " + myCommand.CommandText,  
    now, now, 0, ref additionalData);  
}  
```  
  
```vb  
Public  Overrides Sub PreExecute()   
  Dim now As DateTime = DateTime.Now   
  Dim additionalData As Byte() = Nothing   
  Me.ComponentMetaData.PostLogMessage(MyLogEntryName, _  
    Me.ComponentMetaData.Name, _  
    "Command Sent was: " + myCommand.CommandText, _  
    now, now, 0, additionalData)   
End Sub  
```  
  
 <span data-ttu-id="28390-120">Теперь, когда пользователь запустит пакет, после выбора пункта "Мой собственный формат записи журнала" в диалоговом окне **Ведение журнала** в журнале появится новая запись, явно помеченная как "Пользователь::Мой собственный формат записи журнала".</span><span class="sxs-lookup"><span data-stu-id="28390-120">Now when the user executes the package, after selecting the "My Custom Component Log Entry" in the **Logging** dialog box, the log will contain an entry clearly labeled as "User::My Custom Component Log Entry."</span></span> <span data-ttu-id="28390-121">Новая запись в журнале содержит текст инструкции SQL, отметку времени и всю дополнительную информацию, заданную разработчиком.</span><span class="sxs-lookup"><span data-stu-id="28390-121">This new log entry contains the text of the SQL statement, the timestamp, and any additional data logged by the developer.</span></span>  
  
<span data-ttu-id="28390-122">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="28390-122">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="28390-123">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="28390-123">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="28390-124">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="28390-124">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="28390-125">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="28390-125">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28390-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="28390-126">See Also</span></span>  
 [<span data-ttu-id="28390-127">Ведение журналов в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="28390-127">Integration Services &#40;SSIS&#41; Logging</span></span>](../../performance/integration-services-ssis-logging.md)  
  
  
