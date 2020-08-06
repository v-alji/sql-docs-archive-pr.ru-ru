---
title: Обнаружение пустого неструктурированного файла в задаче "Скрипт" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- flat files
- Script task [Integration Services], empty flat files
- SSIS Script task, empty flat files
- Script task [Integration Services], examples
ms.assetid: 1b4defb8-886a-483d-8056-d1b91d37bc90
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 379b11bd18752ad648fc5f24d11d9ed5bfb63e14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664991"
---
# <a name="detecting-an-empty-flat-file-with-the-script-task"></a><span data-ttu-id="3e7cc-102">Обнаружение пустого неструктурированного файла в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="3e7cc-102">Detecting an Empty Flat File with the Script Task</span></span>
  <span data-ttu-id="3e7cc-103">Источник данных «Неструктурированный файл» не проверяет до начала обработки, содержит ли неструктурированный файл строки данных.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-103">The Flat File source does not determine whether a flat file contains rows of data before attempting to process it.</span></span> <span data-ttu-id="3e7cc-104">Можно повысить эффективность пакета, особенно работающего с многочисленными неструктурированными файлами, если пропускать файлы, не содержащие строки данных.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-104">You may want to improve the efficiency of a package, especially of a package that iterates over numerous flat files, by skipping files that do not contain any rows of data.</span></span> <span data-ttu-id="3e7cc-105">Задача «Скрипт» может проверять, не является ли неструктурированный файл пустым, до начала обработки пакетом потока данных.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-105">The Script task can look for an empty flat file before the package begins to process the data flow.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e7cc-106">Если нужно создать задачу, которую будет удобно использовать в нескольких пакетах, рекомендуется начать разработку пользовательской задачи с этого образца задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="3e7cc-106">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="3e7cc-107">Дополнительные сведения см. в разделе [Разработка пользовательской задачи](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="3e7cc-107">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="3e7cc-108">Description</span><span class="sxs-lookup"><span data-stu-id="3e7cc-108">Description</span></span>  
 <span data-ttu-id="3e7cc-109">В следующем примере методы из пространства имен `System.IO` используются для проверки неструктурированного файла, указанного в диспетчере соединений с неструктурированными файлами, чтобы определить, не является ли этот файл пустым и не состоит ли он только из строк, не содержащих данные (например, заголовков столбцов или пустой строки).</span><span class="sxs-lookup"><span data-stu-id="3e7cc-109">The following example uses methods from the `System.IO` namespace to test the flat file specified in a Flat File connection manager to determine whether the file is empty, or whether it contains only expected non-data rows such as column headers or an empty line.</span></span> <span data-ttu-id="3e7cc-110">Сначала скрипт проверяет размер файла; если размер равен нулю, значит, файл пуст.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-110">The script checks the size of the file first; if the size is zero bytes, the file is empty.</span></span> <span data-ttu-id="3e7cc-111">Если размер файла отличен от нуля, скрипт читает строки из файла, пока они не кончатся или пока число строк не превысит ожидаемое число рядов без данных.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-111">If the file size is greater than zero, the script reads lines from the file until there are no more lines, or until the number of lines exceeds the expected number of non-data rows.</span></span> <span data-ttu-id="3e7cc-112">Если количество строк в файле меньше или равно ожидаемому числу рядов без данных, то файл считается пустым.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-112">If the number of lines in the file is less than or equal to the expected number of non-data rows, then the file is considered empty.</span></span> <span data-ttu-id="3e7cc-113">Результат возвращается как логическое значение в пользовательской переменной и может использоваться для переключения потока управления пакета.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-113">The result is returned as a Boolean value in a user variable, the value of which can be used for branching in the package's control flow.</span></span> <span data-ttu-id="3e7cc-114">`FireInformation`Метод также отображает результат в окне **вывод** [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] средств для приложений (VSTA).</span><span class="sxs-lookup"><span data-stu-id="3e7cc-114">The `FireInformation` method also displays the result in the **Output** window of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="3e7cc-115">Настройка этого образца задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="3e7cc-115">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="3e7cc-116">Создайте и настройте диспетчер соединений с неструктурированными файлами с именем `EmptyFlatFileTest` .</span><span class="sxs-lookup"><span data-stu-id="3e7cc-116">Create and configure a flat file connection manager named `EmptyFlatFileTest`.</span></span>  
  
2.  <span data-ttu-id="3e7cc-117">Создайте переменную целого типа с именем `FFNonDataRows` и присвойте ей в качестве значения количество ожидаемых в неструктурированном файле строк без данных.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-117">Create an integer variable named `FFNonDataRows` and set its value to the number of non-data rows expected in the flat file.</span></span>  
  
3.  <span data-ttu-id="3e7cc-118">Создайте логическую переменную с именем `FFIsEmpty`.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-118">Create a Boolean variable named `FFIsEmpty`.</span></span>  
  
4.  <span data-ttu-id="3e7cc-119">Добавьте переменную `FFNonDataRows` к свойству задачи "Скрипт" **ReadOnlyVariables**.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-119">Add the `FFNonDataRows` variable to the Script task's **ReadOnlyVariables** property.</span></span>  
  
5.  <span data-ttu-id="3e7cc-120">Добавьте переменную `FFIsEmpty` к свойству задачи "Скрипт" **ReadWriteVariables**.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-120">Add the `FFIsEmpty` variable to the Script task's **ReadWriteVariables** property.</span></span>  
  
6.  <span data-ttu-id="3e7cc-121">Импортируйте в код пространство имен `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-121">In your code, import the `System.IO` namespace.</span></span>  
  
 <span data-ttu-id="3e7cc-122">При использовании перечислителя с циклом по каждому файлу нужно вместо использования одного диспетчера соединений с неструктурированными файлами изменить приведенный ниже образец код для получения имени и пути файла из переменной, в которой хранится перечисляемая величина, а не из диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-122">If you are iterating over files with a Foreach File enumerator, instead of using a single Flat File connection manager, you will need to modify the sample code below to obtain the file name and path from the variable in which the enumerated value is stored instead of from the connection manager.</span></span>  
  
### <a name="code"></a><span data-ttu-id="3e7cc-123">Код</span><span class="sxs-lookup"><span data-stu-id="3e7cc-123">Code</span></span>  
  
```vb  
Public Sub Main()  
  
  Dim nonDataRows As Integer = _  
      DirectCast(Dts.Variables("FFNonDataRows").Value, Integer)  
  Dim ffConnection As String = _  
      DirectCast(Dts.Connections("EmptyFlatFileTest").AcquireConnection(Nothing), _  
      String)  
  Dim flatFileInfo As New FileInfo(ffConnection)  
  ' If file size is 0 bytes, flat file does not contain data.  
  Dim fileSize As Long = flatFileInfo.Length  
  If fileSize > 0 Then  
    Dim lineCount As Integer = 0  
    Dim line As String  
    Dim fsFlatFile As New StreamReader(ffConnection)  
    Do Until fsFlatFile.EndOfStream  
      line = fsFlatFile.ReadLine  
      lineCount += 1  
      ' If line count > expected number of non-data rows,  
      '  flat file contains data (default value).  
      If lineCount > nonDataRows Then  
        Exit Do  
      End If  
      ' If line count <= expected number of non-data rows,  
      '  flat file does not contain data.  
      If lineCount <= nonDataRows Then  
        Dts.Variables("FFIsEmpty").Value = True  
      End If  
    Loop  
  Else  
    Dts.Variables("FFIsEmpty").Value = True  
  End If  
  
  Dim fireAgain As Boolean = False  
  Dts.Events.FireInformation(0, "Script Task", _  
      String.Format("{0}: {1}", ffConnection, _  
      Dts.Variables("FFIsEmpty").Value.ToString), _  
      String.Empty, 0, fireAgain)  
  
  Dts.TaskResult = ScriptResults.Success  
  
End Sub  
```  
  
```csharp  
public void Main()  
        {  
  
            int nonDataRows = (int)(Dts.Variables["FFNonDataRows"].Value);  
            string ffConnection = (string)(Dts.Connections["EmptyFlatFileTest"].AcquireConnection(null) as String);  
            FileInfo flatFileInfo = new FileInfo(ffConnection);  
            // If file size is 0 bytes, flat file does not contain data.  
            long fileSize = flatFileInfo.Length;  
            if (fileSize > 0)  
            {  
  
                int lineCount = 0;  
                string line;  
                StreamReader fsFlatFile = new StreamReader(ffConnection);  
                while (!(fsFlatFile.EndOfStream))  
                {  
                    Console.WriteLine (fsFlatFile.ReadLine());  
                    lineCount += 1;  
                    // If line count > expected number of non-data rows,  
                    //  flat file contains data (default value).  
                    if (lineCount > nonDataRows)  
                    {  
                        break;  
                    }  
                    // If line count <= expected number of non-data rows,  
                    //  flat file does not contain data.  
                    if (lineCount <= nonDataRows)  
                    {  
                        Dts.Variables["FFIsEmpty"].Value = true;  
                    }  
                }  
            }  
            else  
            {  
                Dts.Variables["FFIsEmpty"].Value = true;  
            }  
  
            bool fireAgain = false;  
            Dts.Events.FireInformation(0, "Script Task", String.Format("{0}: {1}", ffConnection, Dts.Variables["FFIsEmpty"].Value), String.Empty, 0, ref fireAgain);  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
```  
  
<span data-ttu-id="3e7cc-124">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="3e7cc-124">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="3e7cc-125">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="3e7cc-125">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="3e7cc-126">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="3e7cc-126">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="3e7cc-127">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="3e7cc-127">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e7cc-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="3e7cc-128">See Also</span></span>  
 [<span data-ttu-id="3e7cc-129">Примеры задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="3e7cc-129">Script Task Examples</span></span>](../extending-packages-scripting-task-examples/script-task-examples.md)  
  
  
