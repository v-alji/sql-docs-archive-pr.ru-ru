---
title: Составление списка для цикла по каждому элементу в задаче "Скрипт" | Документы Майкрософт
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Foreach Loop containers
- Script task [Integration Services], Foreach loops
- Script task [Integration Services], examples
- SSIS Script task, Foreach loops
ms.assetid: 694f0462-d0c5-4191-b64e-821b1bdef055
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 039860da121efaa52115bb515b158ea10373e459
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729633"
---
# <a name="gathering-a-list-for-the-foreach-loop-with-the-script-task"></a><span data-ttu-id="ddcfd-102">Составление списка для цикла по каждому элементу в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="ddcfd-102">Gathering a List for the ForEach Loop with the Script Task</span></span>
  <span data-ttu-id="ddcfd-103">Перечислитель по объекту из переменной перечисляет элементы в списке, передаваемом ему в переменной, и выполняет одни и те же задачи для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="ddcfd-103">The Foreach from Variable Enumerator enumerates over the items in a list that is passed to it in a variable and performs the same tasks on each item.</span></span> <span data-ttu-id="ddcfd-104">Чтобы заполнить список, можно использовать пользовательский код в задаче «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="ddcfd-104">You can use custom code in a Script task to populate a list for this purpose.</span></span> <span data-ttu-id="ddcfd-105">Дополнительные сведения о перечислителе см. в разделе [Контейнер "Цикл по каждому элементу"](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="ddcfd-105">For more information about the enumerator, see [Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ddcfd-106">Если нужно создать задачу, которую будет удобно использовать в нескольких пакетах, рекомендуется начать разработку пользовательской задачи с этого образца задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="ddcfd-106">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="ddcfd-107">Дополнительные сведения см. в разделе [Разработка пользовательской задачи](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="ddcfd-107">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="ddcfd-108">Description</span><span class="sxs-lookup"><span data-stu-id="ddcfd-108">Description</span></span>  
 <span data-ttu-id="ddcfd-109">В следующем примере для получения списка книг Excel на компьютере, которые новее или старше, чем указанное пользователем в переменной число дней, используются методы из пространства имен `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="ddcfd-109">The following example uses methods from the `System.IO` namespace to gather a list of Excel workbooks on the computer that are either newer or older than a number of days specified by the user in a variable.</span></span> <span data-ttu-id="ddcfd-110">В примере выполняется рекурсивный поиск в каталогах на диске С для нахождения файлов, имеющих расширение XLS, и проверяется дата последнего изменения каждого файла, чтобы определить, должен ли файл быть в списке.</span><span class="sxs-lookup"><span data-stu-id="ddcfd-110">It searches directories on Drive C recursively for files that have the .xls extension and examines the date on which each file was last modified to determine whether the file belongs in the list.</span></span> <span data-ttu-id="ddcfd-111">Он добавляет соответствующие файлы в `ArrayList` и сохраняет их в `ArrayList` переменную для последующего использования в контейнере «цикл по каждому элементу».</span><span class="sxs-lookup"><span data-stu-id="ddcfd-111">It adds qualifying files to an `ArrayList` and saves the `ArrayList` to a variable for later use in a Foreach Loop container.</span></span> <span data-ttu-id="ddcfd-112">Контейнер «цикл по каждому элементу» настроен для использования перечислителя по объекту из переменной.</span><span class="sxs-lookup"><span data-stu-id="ddcfd-112">The Foreach Loop container is configured to use the Foreach from Variable enumerator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ddcfd-113">Переменная, используемая с перечислителем по объекту из переменной, должна иметь тип `Object`.</span><span class="sxs-lookup"><span data-stu-id="ddcfd-113">The variable that you use with the Foreach from Variable Enumerator must be of type `Object`.</span></span> <span data-ttu-id="ddcfd-114">Объект, помещаемый в переменную, должен реализовывать один из следующих интерфейсов: `System.Collections.IEnumerable` , `System.Runtime.InteropServices.ComTypes.IEnumVARIANT` , `System.ComponentModel IListSource` или `Microsoft.SqlServer.Dts.Runtime.Wrapper.ForEachEnumeratorHost` .</span><span class="sxs-lookup"><span data-stu-id="ddcfd-114">The object that you place in the variable must implement one of the following interfaces: `System.Collections.IEnumerable`, `System.Runtime.InteropServices.ComTypes.IEnumVARIANT`, `System.ComponentModel IListSource`, or `Microsoft.SqlServer.Dts.Runtime.Wrapper.ForEachEnumeratorHost`.</span></span> <span data-ttu-id="ddcfd-115">Обычно используются объект `Array` или `ArrayList`.</span><span class="sxs-lookup"><span data-stu-id="ddcfd-115">An `Array` or `ArrayList` is commonly used.</span></span> <span data-ttu-id="ddcfd-116">Для объекта `ArrayList` необходима ссылка и инструкция `Imports` для пространства имен `System.Collections`.</span><span class="sxs-lookup"><span data-stu-id="ddcfd-116">The `ArrayList` requires a reference and an `Imports` statement for the `System.Collections` namespace.</span></span>  
  
 <span data-ttu-id="ddcfd-117">Можно поэкспериментировать с этой задачей, используя различные положительные и отрицательные значения для переменной пакета `FileAge`.</span><span class="sxs-lookup"><span data-stu-id="ddcfd-117">You can experiment with this task by using different positive and negative values for the `FileAge` package variable.</span></span> <span data-ttu-id="ddcfd-118">Например, можно ввести 5 для поиска файлов, созданных за последние пять дней, или ввести -3 для поиска файлов, созданных более трех дней назад.</span><span class="sxs-lookup"><span data-stu-id="ddcfd-118">For example, you can enter 5 to search for files created in the last five days, or enter -3 to search for files that were created more than three days ago.</span></span> <span data-ttu-id="ddcfd-119">Для этой задачи потребуется минута или две, чтобы выполнить поиск на диске с большим количеством папок.</span><span class="sxs-lookup"><span data-stu-id="ddcfd-119">This task may take a minute or two on a drive with many folders to search.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="ddcfd-120">Настройка этого образца задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="ddcfd-120">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="ddcfd-121">Создайте переменную пакета с именем `FileAge`, имеющую тип целого числа, и введите положительное или отрицательное целое значение.</span><span class="sxs-lookup"><span data-stu-id="ddcfd-121">Create a package variable named `FileAge` of type integer and enter a positive or negative integer value.</span></span> <span data-ttu-id="ddcfd-122">Если значение положительное, код выполняет поиск файлов, созданных позже указанного числа дней назад; если значение отрицательное, выполняется поиск файлов, созданных раньше указанного числа дней назад.</span><span class="sxs-lookup"><span data-stu-id="ddcfd-122">When the value is positive, the code searches for files newer than the specified number of days; when negative, for files older than the specified number of days.</span></span>  
  
2.  <span data-ttu-id="ddcfd-123">Создайте переменную пакета с именем `FileList`, имеющую тип `Object`, чтобы получить список файлов, полученных задачей «Скрипт» для дальнейшего использования перечислителем по объекту из переменной.</span><span class="sxs-lookup"><span data-stu-id="ddcfd-123">Create a package variable named `FileList` of type `Object` to receive the list of files gathered by the Script task for later use by the Foreach from Variable Enumerator.</span></span>  
  
3.  <span data-ttu-id="ddcfd-124">Добавьте переменную `FileAge` в свойство `ReadOnlyVariables` задачи «Скрипт» и добавьте переменную `FileList` в свойство `ReadWriteVariables`.</span><span class="sxs-lookup"><span data-stu-id="ddcfd-124">Add the `FileAge` variable to the Script task's `ReadOnlyVariables` property, and add the `FileList` variable to the `ReadWriteVariables` property.</span></span>  
  
4.  <span data-ttu-id="ddcfd-125">Импортируйте в коде пространства имен `System.Collections` и `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="ddcfd-125">In your code, import the `System.Collections` and the `System.IO` namespaces.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ddcfd-126">Код</span><span class="sxs-lookup"><span data-stu-id="ddcfd-126">Code</span></span>  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Math  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports System.Collections  
Imports System.IO  
  
Public Class ScriptMain  
  
  Private Const FILE_AGE As Integer = -50  
  
  Private Const FILE_ROOT As String = "C:\"  
  Private Const FILE_FILTER As String = "*.xls"  
  
  Private isCheckForNewer As Boolean = True  
  Dim fileAgeLimit As Integer  
  Private listForEnumerator As ArrayList  
  
  Public Sub Main()  
  
    fileAgeLimit = DirectCast(Dts.Variables("FileAge").Value, Integer)  
  
    ' If value provided is positive, we want files NEWER THAN n days.  
    '  If negative, we want files OLDER THAN n days.  
    If fileAgeLimit < 0 Then  
      isCheckForNewer = False  
    End If  
    ' Extract number of days as positive integer.  
    fileAgeLimit = Math.Abs(fileAgeLimit)  
  
    listForEnumerator = New ArrayList  
  
    GetFilesInFolder(FILE_ROOT)  
  
    ' Return the list of files to the variable  
    '  for later use by the Foreach from Variable enumerator.  
    System.Windows.Forms.MessageBox.Show("Matching files: " & listForEnumerator.Count.ToString, "Results", Windows.Forms.MessageBoxButtons.OK, Windows.Forms.MessageBoxIcon.Information)  
    Dts.Variables("FileList").Value = listForEnumerator  
  
    Dts.TaskResult = ScriptResults.Success  
  
  End Sub  
  
  Private Sub GetFilesInFolder(ByVal folderPath As String)  
  
    Dim localFiles() As String  
    Dim localFile As String  
    Dim fileChangeDate As Date  
    Dim fileAge As TimeSpan  
    Dim fileAgeInDays As Integer  
    Dim childFolder As String  
  
    Try  
      localFiles = Directory.GetFiles(folderPath, FILE_FILTER)  
      For Each localFile In localFiles  
        fileChangeDate = File.GetLastWriteTime(localFile)  
        fileAge = DateTime.Now.Subtract(fileChangeDate)  
        fileAgeInDays = fileAge.Days  
        CheckAgeOfFile(localFile, fileAgeInDays)  
      Next  
  
      If Directory.GetDirectories(folderPath).Length > 0 Then  
        For Each childFolder In Directory.GetDirectories(folderPath)  
          GetFilesInFolder(childFolder)  
        Next  
      End If  
  
    Catch  
      ' Ignore exceptions on special folders such as System Volume Information.  
    End Try  
  
  End Sub  
  
  Private Sub CheckAgeOfFile(ByVal localFile As String, ByVal fileAgeInDays As Integer)  
  
    If isCheckForNewer Then  
      If fileAgeInDays <= fileAgeLimit Then  
        listForEnumerator.Add(localFile)  
      End If  
    Else  
      If fileAgeInDays > fileAgeLimit Then  
        listForEnumerator.Add(localFile)  
      End If  
    End If  
  
  End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Math;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Collections;  
using System.IO;  
  
public partial class ScriptMain : Microsoft.SqlServer.Dts.Tasks.ScriptTask.VSTARTScriptObjectModelBase  
    {  
  
        private const int FILE_AGE = -50;  
  
        private const string FILE_ROOT = "C:\\";  
        private const string FILE_FILTER = "*.xls";  
  
        private bool isCheckForNewer = true;  
        int fileAgeLimit;  
        private ArrayList listForEnumerator;  
  
        public void Main()  
  {  
  
    fileAgeLimit = (int)(Dts.Variables["FileAge"].Value);  
  
    // If value provided is positive, we want files NEWER THAN n days.  
    // If negative, we want files OLDER THAN n days.  
    if (fileAgeLimit<0)  
    {  
      isCheckForNewer = false;  
    }  
    // Extract number of days as positive integer.  
    fileAgeLimit = Math.Abs(fileAgeLimit);  
  
    ArrayList listForEnumerator = new ArrayList();  
  
    GetFilesInFolder(FILE_ROOT);  
  
    // Return the list of files to the variable  
    // for later use by the Foreach from Variable enumerator.  
    System.Windows.Forms.MessageBox.Show("Matching files: "+ listForEnumerator.Count, "Results",   
MessageBoxButtons.OK, MessageBoxIcon.Information);  
    Dts.Variables["FileList"].Value = listForEnumerator;  
  
    Dts.TaskResult = (int)ScriptResults.Success;  
  
  }  
  
        private void GetFilesInFolder(string folderPath)  
        {  
  
            string[] localFiles;  
            DateTime fileChangeDate;  
            TimeSpan fileAge;  
            int fileAgeInDays;  
  
            try  
            {  
                localFiles = Directory.GetFiles(folderPath, FILE_FILTER);  
                foreach (string localFile in localFiles)  
                {  
                    fileChangeDate = File.GetLastWriteTime(localFile);  
                    fileAge = DateTime.Now.Subtract(fileChangeDate);  
                    fileAgeInDays = fileAge.Days;  
                    CheckAgeOfFile(localFile, fileAgeInDays);  
                }  
  
                if (Directory.GetDirectories(folderPath).Length > 0)  
                {  
                    foreach (string childFolder in Directory.GetDirectories(folderPath))  
                    {  
                        GetFilesInFolder(childFolder);  
                    }  
                }  
  
            }  
            catch  
            {  
                // Ignore exceptions on special folders, such as System Volume Information.  
            }  
  
        }  
  
        private void CheckAgeOfFile(string localFile, int fileAgeInDays)  
        {  
  
            if (isCheckForNewer)  
            {  
                if (fileAgeInDays <= fileAgeLimit)  
                {  
                    listForEnumerator.Add(localFile);  
                }  
            }  
            else  
            {  
                if (fileAgeInDays > fileAgeLimit)  
                {  
                    listForEnumerator.Add(localFile);  
                }  
            }  
  
        }  
  
    }  
```  
  
<span data-ttu-id="ddcfd-127">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="ddcfd-127">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ddcfd-128">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="ddcfd-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ddcfd-129">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="ddcfd-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ddcfd-130">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="ddcfd-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddcfd-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="ddcfd-131">See Also</span></span>  
 <span data-ttu-id="ddcfd-132">[Контейнер «цикл по каждому элементу»](../control-flow/foreach-loop-container.md) </span><span class="sxs-lookup"><span data-stu-id="ddcfd-132">[Foreach Loop Container](../control-flow/foreach-loop-container.md) </span></span>  
 [<span data-ttu-id="ddcfd-133">Настройка контейнера «цикл по каждому элементу»</span><span class="sxs-lookup"><span data-stu-id="ddcfd-133">Configure a Foreach Loop Container</span></span>](../configure-a-foreach-loop-container.md)  
  
  
