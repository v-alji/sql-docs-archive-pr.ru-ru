---
title: Использование переменных в задаче "Скрипт" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Foreach Loop containers
- Script task [Integration Services], variables
- scripts [Integration Services], variables
- Variables property
- Variable object
- SSIS Script task, variables
- variables [Integration Services], Script task
ms.assetid: 593b5961-4bfa-4ce1-9531-a251c34e89d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2cd8fee5741c3d0e28e52c8712c3896428a05e8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752283"
---
# <a name="using-variables-in-the-script-task"></a><span data-ttu-id="a6804-102">Использование переменных в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="a6804-102">Using Variables in the Script Task</span></span>
  <span data-ttu-id="a6804-103">Переменные позволяют задаче «Скрипт» обмениваться данными с другими объектами в пакете.</span><span class="sxs-lookup"><span data-stu-id="a6804-103">Variables make it possible for the Script task to exchange data with other objects in the package.</span></span> <span data-ttu-id="a6804-104">Дополнительные сведения см. в разделе [Переменные служб Integration Services (SSIS)](../../integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="a6804-104">For more information, see [Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md).</span></span>  
  
 <span data-ttu-id="a6804-105">В задаче «Скрипт» используется свойство <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> объекта `Dts` для чтения из объектов <xref:Microsoft.SqlServer.Dts.Runtime.Variable> в пакете и записи в них.</span><span class="sxs-lookup"><span data-stu-id="a6804-105">The Script task uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property of the `Dts` object to read from and write to <xref:Microsoft.SqlServer.Dts.Runtime.Variable> objects in the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a6804-106">Свойство <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> класса <xref:Microsoft.SqlServer.Dts.Runtime.Variable> имеет тип `Object`.</span><span class="sxs-lookup"><span data-stu-id="a6804-106">The <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.Variable> class is of type `Object`.</span></span> <span data-ttu-id="a6804-107">В задаче «Скрипт» включен параметр `Option Strict`, поэтому необходимо привести свойство <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> к соответствующему типу, прежде чем можно будет его использовать.</span><span class="sxs-lookup"><span data-stu-id="a6804-107">Because the Script task has `Option Strict` enabled, you must cast the <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> property to the appropriate type before you can use it.</span></span>  
  
 <span data-ttu-id="a6804-108">Необходимо добавить существующие переменные в списки <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadOnlyVariables%2A> и <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadWriteVariables%2A> в **редакторе задачи "скрипт"** , чтобы сделать их доступными в пользовательском скрипте.</span><span class="sxs-lookup"><span data-stu-id="a6804-108">You add existing variables to the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadOnlyVariables%2A> and <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadWriteVariables%2A> lists in the **Script Task Editor** to make them available to the custom script.</span></span> <span data-ttu-id="a6804-109">Помните, что в именах переменных учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="a6804-109">Keep in mind that variable names are case-sensitive.</span></span> <span data-ttu-id="a6804-110">В скрипте можно получить доступ к переменным обоих типов с помощью свойства <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> объекта `Dts`.</span><span class="sxs-lookup"><span data-stu-id="a6804-110">Within the script, you access variables of both types through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property of the `Dts` object.</span></span> <span data-ttu-id="a6804-111">Используйте свойство `Value`, чтобы считывать значения отдельных переменных и записывать значения в них.</span><span class="sxs-lookup"><span data-stu-id="a6804-111">Use the `Value` property to read from and write to individual variables.</span></span> <span data-ttu-id="a6804-112">Задача «Скрипт» обеспечивает прозрачное для пользователя управление блокировкой во время считывания и изменение значений переменных в скрипте.</span><span class="sxs-lookup"><span data-stu-id="a6804-112">The Script task transparently manages locking as the script reads and modifies the values of variables.</span></span>  
  
 <span data-ttu-id="a6804-113">Чтобы проверить наличие переменной перед ее использованием в коде, можно использовать метод <xref:Microsoft.SqlServer.Dts.Runtime.Variables.Contains%2A> коллекции <xref:Microsoft.SqlServer.Dts.Runtime.Variables>, возвращенной свойством <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>.</span><span class="sxs-lookup"><span data-stu-id="a6804-113">You can use the <xref:Microsoft.SqlServer.Dts.Runtime.Variables.Contains%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection returned by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property to check for the existence of a variable before using it in your code.</span></span>  
  
 <span data-ttu-id="a6804-114">Для работы с переменными в задаче "скрипт" можно также использовать свойство <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> (Dts.VariableDispenser).</span><span class="sxs-lookup"><span data-stu-id="a6804-114">You can also use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> property (Dts.VariableDispenser) to work with variables in the Script task.</span></span> <span data-ttu-id="a6804-115">При использовании свойства <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> необходимо обрабатывать в коде и семантику блокирования, и приведение типов данных для значений переменных.</span><span class="sxs-lookup"><span data-stu-id="a6804-115">When using the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, you must handle both the locking semantics and the casting of data types for variable values in your own code.</span></span> <span data-ttu-id="a6804-116">Может потребоваться использовать свойство <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> вместо свойства <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>, если возникает необходимость работать с переменной, недоступной во время разработки, но создаваемой программным путем во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a6804-116">You may need to use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> property instead of the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property if you want to work with a variable that is not available at design time but is created programmatically at run time.</span></span>  
  
## <a name="using-the-script-task-within-a-foreach-loop-container"></a><span data-ttu-id="a6804-117">Использование задачи «Скрипт» в контейнере «цикл по каждому элементу»</span><span class="sxs-lookup"><span data-stu-id="a6804-117">Using the Script Task within a Foreach Loop Container</span></span>  
 <span data-ttu-id="a6804-118">Если задача «Скрипт» неоднократно запускается в контейнере «цикл по каждому элементу», то в скрипте обычно требуется обеспечить работу с содержимым текущего элемента в перечислителе.</span><span class="sxs-lookup"><span data-stu-id="a6804-118">When a Script task runs repeatedly within a Foreach Loop container, the script usually needs to work with the contents of the current item in the enumerator.</span></span> <span data-ttu-id="a6804-119">Например, при использовании перечислителя с циклом по каждому файлу в скрипте требуется определить имя текущего файла, а при использовании перечислителя ADO по каждой строке в скрипте необходимо получать содержимое столбцов в текущей строке данных.</span><span class="sxs-lookup"><span data-stu-id="a6804-119">For example, when using a Foreach File enumerator, the script needs to know the current file name; when using a Foreach ADO enumerator, the script needs to know the contents of the columns in the current row of data.</span></span>  
  
 <span data-ttu-id="a6804-120">Переменные делают возможной такую связь между контейнером «цикл по каждому элементу» и задачей «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="a6804-120">Variables make this communication between the Foreach Loop container and the Script task possible.</span></span> <span data-ttu-id="a6804-121">На странице **Сопоставления переменной** окна **Редактор циклов по каждому элементу** необходимо присвоить переменные каждому элементу данных, возвращаемому одним перечисленным элементом.</span><span class="sxs-lookup"><span data-stu-id="a6804-121">On the **Variable Mappings** page of the **Foreach Loop Editor**, assign variables to each item of data that is returned by a single enumerated item.</span></span> <span data-ttu-id="a6804-122">Например, перечислитель с циклом по каждому файлу возвращает только имя файла из позиции с индексом 0 и поэтому требует сопоставления лишь с одной переменной, а перечислитель, который возвращает несколько столбцов данных из каждой строки, требует сопоставить отдельную переменную с каждым столбцом, предназначенным для использования в задаче «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="a6804-122">For example, a Foreach File enumerator returns only a file name at Index 0 and therefore requires only one variable mapping, whereas an enumerator that returns several columns of data in each row requires you to map a different variable to each column that you want to use in the Script task.</span></span>  
  
 <span data-ttu-id="a6804-123">После сопоставления перечисленных элементов с переменными необходимо добавить сопоставленные переменные в `ReadOnlyVariables` свойство на странице **Скрипт** в **редакторе задачи «Скрипт** », чтобы сделать их доступными для скрипта.</span><span class="sxs-lookup"><span data-stu-id="a6804-123">After you have mapped enumerated items to variables, then you must add the mapped variables to the `ReadOnlyVariables` property on the **Script** page of the **Script Task Editor** to make them available to your script.</span></span> <span data-ttu-id="a6804-124">Пример применения задачи "Скрипт" в контейнере "цикл по каждому элементу" для обработки файлов изображений в папке см. в разделе [Работа с изображениями в задаче "Скрипт"](../../extending-packages-scripting-task-examples/working-with-images-with-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="a6804-124">For an example of a Script task within a Foreach Loop container that processes the image files in a folder, see [Working with Images with the Script Task](../../extending-packages-scripting-task-examples/working-with-images-with-the-script-task.md).</span></span>  
  
## <a name="variables-example"></a><span data-ttu-id="a6804-125">Пример использования переменных</span><span class="sxs-lookup"><span data-stu-id="a6804-125">Variables Example</span></span>  
 <span data-ttu-id="a6804-126">В следующем примере показано, как получить доступ и использовать переменные в задаче «Скрипт», чтобы определить пути рабочего процесса пакета.</span><span class="sxs-lookup"><span data-stu-id="a6804-126">The following example demonstrates how to access and use variables in a Script task to determine the path of package workflow.</span></span> <span data-ttu-id="a6804-127">В примере предполагается, что вы создали целочисленные переменные с именем `CustomerCount` и `MaxRecordCount` добавили их в `ReadOnlyVariables` коллекцию в **редакторе задачи «Скрипт**».</span><span class="sxs-lookup"><span data-stu-id="a6804-127">The sample assumes that you have created integer variables named `CustomerCount` and `MaxRecordCount` and added them to the `ReadOnlyVariables` collection in the **Script Task Editor**.</span></span> <span data-ttu-id="a6804-128">Переменная `CustomerCount` содержит количество записей с данными заказчиков, которые должны быть импортированы.</span><span class="sxs-lookup"><span data-stu-id="a6804-128">The `CustomerCount` variable contains the number of customer records to be imported.</span></span> <span data-ttu-id="a6804-129">Если это значение больше значения `MaxRecordCount`, задача «Скрипт» сообщает о неудачном завершении.</span><span class="sxs-lookup"><span data-stu-id="a6804-129">If its value is greater than the value of `MaxRecordCount`, the Script task reports failure.</span></span> <span data-ttu-id="a6804-130">Если неудачное завершение возникает из-за превышения порогового значения `MaxRecordCount`, в пути обработки ошибок рабочего процесса можно реализовать все необходимые операции очистки.</span><span class="sxs-lookup"><span data-stu-id="a6804-130">When a failure occurs because the `MaxRecordCount` threshold has been exceeded, the error path of the workflow can implement any required clean-up.</span></span>  
  
 <span data-ttu-id="a6804-131">Чтобы успешно откомпилировать этот образец, необходимо добавить ссылку на сборку Microsoft.SqlServer.ScriptTask.</span><span class="sxs-lookup"><span data-stu-id="a6804-131">To successfully compile the sample, you need to add a reference to the Microsoft.SqlServer.ScriptTask assembly.</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim customerCount As Integer  
    Dim maxRecordCount As Integer  
  
    If Dts.Variables.Contains("CustomerCount") = True AndAlso _  
        Dts.Variables.Contains("MaxRecordCount") = True Then  
  
        customerCount = _  
            CType(Dts.Variables("CustomerCount").Value, Integer)  
        maxRecordCount = _  
            CType(Dts.Variables("MaxRecordCount").Value, Integer)  
  
    End If  
  
    If customerCount > maxRecordCount Then  
            Dts.TaskResult = ScriptResults.Failure  
    Else  
            Dts.TaskResult = ScriptResults.Success  
    End If  
  
End Sub  
```  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Dts.Runtime;  
  
public class ScriptMain  
{  
  
    public void Main()  
    {  
        int customerCount;  
        int maxRecordCount;  
  
        if (Dts.Variables.Contains("CustomerCount")==true&&Dts.Variables.Contains("MaxRecordCount")==true)  
  
        {  
            customerCount = (int) Dts.Variables["CustomerCount"].Value;  
            maxRecordCount = (int) Dts.Variables["MaxRecordCount"].Value;  
  
        }  
  
        if (customerCount>maxRecordCount)  
        {  
            Dts.TaskResult = (int)ScriptResults.Failure;  
        }  
        else  
        {  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
  
    }  
  
}  
  
```  
  
<span data-ttu-id="a6804-132">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="a6804-132">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a6804-133">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="a6804-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a6804-134">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="a6804-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a6804-135">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="a6804-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6804-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="a6804-136">See Also</span></span>  
 <span data-ttu-id="a6804-137">[Переменные в службах Integration Services (SSIS)](../../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="a6804-137">[Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="a6804-138">Использование переменных в пакетах</span><span class="sxs-lookup"><span data-stu-id="a6804-138">Use Variables in Packages</span></span>](../../use-variables-in-packages.md)  
  
  
