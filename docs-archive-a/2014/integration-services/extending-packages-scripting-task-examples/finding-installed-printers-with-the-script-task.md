---
title: Обнаружение установленных принтеров с помощью задачи "Скрипт" | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- System.Drawing.Printing namespace
- printers [Integration Services]
- SSIS Script task, printers
- locating printers
- Printing namespace
- Script task [Integration Services], examples
- finding printers [SQL Server]
- Script task [Integration Services], printers
ms.assetid: 50a55014-e2c3-4ecd-84e1-3e877c55a260
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc4bc06879a55d4d07afca1011cc479dd7e7903a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736608"
---
# <a name="finding-installed-printers-with-the-script-task"></a><span data-ttu-id="858ee-102">Обнаружение установленных принтеров с помощью задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="858ee-102">Finding Installed Printers with the Script Task</span></span>
  <span data-ttu-id="858ee-103">Данные, преобразуемые с помощью пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], часто имеют в качестве своего конечного назначения печатаемый отчет.</span><span class="sxs-lookup"><span data-stu-id="858ee-103">The data that is transformed by [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages often has a printed report as its final destination.</span></span> <span data-ttu-id="858ee-104">`System.Drawing.Printing`Пространство имен в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] предоставляет классы для работы с принтерами.</span><span class="sxs-lookup"><span data-stu-id="858ee-104">The `System.Drawing.Printing` namespace in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides classes for working with printers.</span></span>

> [!NOTE]
>  <span data-ttu-id="858ee-105">Если нужно создать задачу, которую будет удобно использовать в нескольких пакетах, рекомендуется начать разработку пользовательской задачи с этого образца задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="858ee-105">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="858ee-106">Дополнительные сведения см. в разделе [Разработка пользовательской задачи](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="858ee-106">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>

## <a name="description"></a><span data-ttu-id="858ee-107">Description</span><span class="sxs-lookup"><span data-stu-id="858ee-107">Description</span></span>
 <span data-ttu-id="858ee-108">В следующем примере показано, как выполняется поиск установленных на сервере принтеров, которые поддерживают формат бумаги «стандарт» (применяемую в Соединенных Штатах).</span><span class="sxs-lookup"><span data-stu-id="858ee-108">The following example locates printers installed on the server that support legal size paper (as used in the United States).</span></span> <span data-ttu-id="858ee-109">Код проверки поддерживаемых форматов бумаги инкапсулирован в закрытой функции.</span><span class="sxs-lookup"><span data-stu-id="858ee-109">The code to check supported paper sizes is encapsulated in a private function.</span></span> <span data-ttu-id="858ee-110">Чтобы можно было следить за ходом выполнения в скрипте проверок параметров для каждого принтера, в скрипте используется метод <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> для инициирования информационного сообщения для принтеров, поддерживающих формат бумаги «стандарт», и инициирования предупреждения для принтеров, не поддерживающих формат бумаги «стандарт».</span><span class="sxs-lookup"><span data-stu-id="858ee-110">To enable you to track the progress of the script as it checks the settings for each printer, the script uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method to raise an informational message for printers with legal size paper, and to raise a warning for printers without legal size paper.</span></span> <span data-ttu-id="858ee-111">Эти сообщения появляются в окне **Вывод** интегрированной среды разработки средств [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] для приложений (VSTA) при выполнении пакета в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="858ee-111">These messages appear in the **Output** window of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE when you run the package in the designer.</span></span>

#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="858ee-112">Настройка этого образца задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="858ee-112">To configure this Script Task example</span></span>

1.  <span data-ttu-id="858ee-113">Создайте переменную с именем `PrinterList` типа `Object`.</span><span class="sxs-lookup"><span data-stu-id="858ee-113">Create the variable named `PrinterList` with type `Object`.</span></span>

2.  <span data-ttu-id="858ee-114">На странице **Скрипт** в **редакторе задачи "Скрипт"** добавьте эту переменную к свойству ReadWriteVariables.</span><span class="sxs-lookup"><span data-stu-id="858ee-114">On the **Script** page of the **Script Task Editor**, add this variable to the ReadWriteVariables property.</span></span>

3.  <span data-ttu-id="858ee-115">В проекте скрипта добавьте ссылку на пространство имен **System.Drawing**.</span><span class="sxs-lookup"><span data-stu-id="858ee-115">In the script project, add a reference to the **System.Drawing** namespace.</span></span>

4.  <span data-ttu-id="858ee-116">В коде используйте `Imports` инструкции для импорта **System. Collections** и `System.Drawing.Printing` пространств имен.</span><span class="sxs-lookup"><span data-stu-id="858ee-116">In your code, use `Imports` statements to import the **System.Collections** and the `System.Drawing.Printing` namespaces.</span></span>

### <a name="code"></a><span data-ttu-id="858ee-117">Код</span><span class="sxs-lookup"><span data-stu-id="858ee-117">Code</span></span>

```vb
Public Sub Main()

    Dim printerName As String
    Dim currentPrinter As New PrinterSettings
    Dim size As PaperSize

    Dim printerList As New ArrayList
    For Each printerName In PrinterSettings.InstalledPrinters
        currentPrinter.PrinterName = printerName
        If PrinterHasLegalPaper(currentPrinter) Then
            printerList.Add(printerName)
            Dts.Events.FireInformation(0, "Example", _
                "Printer " & printerName & " has legal paper.", _
                String.Empty, 0, False)
        Else
            Dts.Events.FireWarning(0, "Example", _
                "Printer " & printerName & " DOES NOT have legal paper.", _
                String.Empty, 0)
        End If
    Next

    Dts.Variables("PrinterList").Value = printerList

    Dts.TaskResult = ScriptResults.Success

End Sub

Private Function PrinterHasLegalPaper( _
    ByVal thisPrinter As PrinterSettings) As Boolean

    Dim size As PaperSize
    Dim hasLegal As Boolean = False

    For Each size In thisPrinter.PaperSizes
        If size.Kind = PaperKind.Legal Then
            hasLegal = True
        End If
    Next

    Return hasLegal

End Function
```

```csharp
public void Main()
        {

            PrinterSettings currentPrinter = new PrinterSettings();
            PaperSize size;
            Boolean Flag = false;

            ArrayList printerList = new ArrayList();
            foreach (string printerName in PrinterSettings.InstalledPrinters)
            {
                currentPrinter.PrinterName = printerName;
                if (PrinterHasLegalPaper(currentPrinter))
                {
                    printerList.Add(printerName);
                    Dts.Events.FireInformation(0, "Example", "Printer " + printerName + " has legal paper.", String.Empty, 0, ref Flag);
                }
                else
                {
                    Dts.Events.FireWarning(0, "Example", "Printer " + printerName + " DOES NOT have legal paper.", String.Empty, 0);
                }
            }

            Dts.Variables["PrinterList"].Value = printerList;

            Dts.TaskResult = (int)ScriptResults.Success;

        }

        private bool PrinterHasLegalPaper(PrinterSettings thisPrinter)
        {

            bool hasLegal = false;

            foreach (PaperSize size in thisPrinter.PaperSizes)
            {
                if (size.Kind == PaperKind.Legal)
                {
                    hasLegal = true;
                }
            }

            return hasLegal;

        }
```

<span data-ttu-id="858ee-118">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="858ee-118">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="858ee-119">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="858ee-119">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="858ee-120">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="858ee-120">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="858ee-121">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="858ee-121">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="858ee-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="858ee-122">See Also</span></span>
 [<span data-ttu-id="858ee-123">Примеры задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="858ee-123">Script Task Examples</span></span>](../extending-packages-scripting-task-examples/script-task-examples.md)


