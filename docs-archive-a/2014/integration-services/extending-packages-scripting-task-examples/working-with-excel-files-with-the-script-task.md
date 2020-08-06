---
title: Работа с файлами Excel в задаче "Скрипт" | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], Excel files
- Script task [Integration Services], examples
- Excel [Integration Services]
ms.assetid: b8fa110a-2c9c-4f5a-8fe1-305555640e44
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 68a764452de548cd46e74d2a7f2f588a050a21c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664425"
---
# <a name="working-with-excel-files-with-the-script-task"></a><span data-ttu-id="524a8-102">Работа с файлами Excel в задаче "Скрипт"</span><span class="sxs-lookup"><span data-stu-id="524a8-102">Working with Excel Files with the Script Task</span></span>
  <span data-ttu-id="524a8-103">Службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] предоставляют диспетчер соединений Excel, источник «Excel» и назначение «Excel» для работы с данными, хранящимися в электронных таблицах в формате [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel.</span><span class="sxs-lookup"><span data-stu-id="524a8-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides the Excel connection manager, Excel source, and Excel destination for working with data stored in spreadsheets in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel file format.</span></span> <span data-ttu-id="524a8-104">Технологии, описанные в этом разделе, используют задачу «Скрипт» для получения сведений о доступных базах данных Excel (файлах книги) и таблицах (листах и именованных диапазонах).</span><span class="sxs-lookup"><span data-stu-id="524a8-104">The techniques described in this topic use the Script task to obtain information about available Excel databases (workbook files) and tables (worksheets and named ranges).</span></span> <span data-ttu-id="524a8-105">Эти образцы можно легко изменить для работы с любыми другими источниками данных на основе файлов, поддерживаемыми поставщиком OLE DB [!INCLUDE[msCoName](../../includes/msconame-md.md)] Jet.</span><span class="sxs-lookup"><span data-stu-id="524a8-105">These samples can easily be modified to work with any of the other file-based data sources supported by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Jet OLE DB Provider.</span></span>  
  
 [<span data-ttu-id="524a8-106">Настройка пакета для проверки образцов</span><span class="sxs-lookup"><span data-stu-id="524a8-106">Configuring a Package to Test the Samples</span></span>](#configuring)  
  
 [<span data-ttu-id="524a8-107">Пример 1. Проверка существования файла Excel</span><span class="sxs-lookup"><span data-stu-id="524a8-107">Example1: Check Whether an Excel File Exists</span></span>](#example1)  
  
 [<span data-ttu-id="524a8-108">Пример 2. Проверка существования таблицы Excel</span><span class="sxs-lookup"><span data-stu-id="524a8-108">Example 2: Check Whether an Excel Table Exists</span></span>](#example2)  
  
 [<span data-ttu-id="524a8-109">Пример 3. Получение списка файлов Excel в папке</span><span class="sxs-lookup"><span data-stu-id="524a8-109">Example 3: Get a List of Excel Files in a Folder</span></span>](#example3)  
  
 [<span data-ttu-id="524a8-110">Пример 4. Получение списка таблиц в файле Excel</span><span class="sxs-lookup"><span data-stu-id="524a8-110">Example 4: Get a List of Tables in an Excel File</span></span>](#example4)  
  
 [<span data-ttu-id="524a8-111">Отображение результатов образцов</span><span class="sxs-lookup"><span data-stu-id="524a8-111">Displaying the Results of the Samples</span></span>](#testing)  
  
> [!NOTE]  
>  <span data-ttu-id="524a8-112">Если нужно создать задачу, которую будет удобно использовать в нескольких пакетах, рекомендуется начать разработку пользовательской задачи с этого образца задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="524a8-112">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="524a8-113">Дополнительные сведения см. в разделе [Разработка пользовательской задачи](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="524a8-113">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
##  <a name="configuring-a-package-to-test-the-samples"></a><a name="configuring"></a> <span data-ttu-id="524a8-114">Настройка пакета для проверки образцов</span><span class="sxs-lookup"><span data-stu-id="524a8-114">Configuring a Package to Test the Samples</span></span>  
 <span data-ttu-id="524a8-115">Для тестирования всех образцов этого раздела можно настроить отдельный пакет.</span><span class="sxs-lookup"><span data-stu-id="524a8-115">You can configure a single package to test all the samples in this topic.</span></span> <span data-ttu-id="524a8-116">В них используется много одинаковых переменных пакета и классов платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="524a8-116">The samples use many of the same package variables and the same [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes.</span></span>  
  
#### <a name="to-configure-a-package-for-use-with-the-examples-in-this-topic"></a><span data-ttu-id="524a8-117">Настройка пакета для использования с примерами этого раздела</span><span class="sxs-lookup"><span data-stu-id="524a8-117">To configure a package for use with the examples in this topic</span></span>  
  
1.  <span data-ttu-id="524a8-118">Создайте новый проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] и откройте пакет по умолчанию для изменения.</span><span class="sxs-lookup"><span data-stu-id="524a8-118">Create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and open the default package for editing.</span></span>  
  
2.  <span data-ttu-id="524a8-119">**Переменные**.</span><span class="sxs-lookup"><span data-stu-id="524a8-119">**Variables**.</span></span> <span data-ttu-id="524a8-120">Откройте окно **Переменные** и определите следующие переменные:</span><span class="sxs-lookup"><span data-stu-id="524a8-120">Open the **Variables** window and define the following variables:</span></span>  
  
    -   <span data-ttu-id="524a8-121">`ExcelFile` типа `String`.</span><span class="sxs-lookup"><span data-stu-id="524a8-121">`ExcelFile`, of type `String`.</span></span> <span data-ttu-id="524a8-122">Введите полный путь и имя файла существующей книги Excel.</span><span class="sxs-lookup"><span data-stu-id="524a8-122">Enter the complete path and filename to an existing Excel workbook.</span></span>  
  
    -   <span data-ttu-id="524a8-123">`ExcelTable` типа `String`.</span><span class="sxs-lookup"><span data-stu-id="524a8-123">`ExcelTable`, of type `String`.</span></span> <span data-ttu-id="524a8-124">Введите имя существующего листа или именованного диапазона в книге, имя которой было указано в качестве значения переменной `ExcelFile`.</span><span class="sxs-lookup"><span data-stu-id="524a8-124">Enter the name of an existing worksheet or named range in the workbook named in the value of the `ExcelFile` variable.</span></span> <span data-ttu-id="524a8-125">Это значение учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="524a8-125">This value is case-sensitive.</span></span>  
  
    -   <span data-ttu-id="524a8-126">`ExcelFileExists` типа `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="524a8-126">`ExcelFileExists`, of type `Boolean`.</span></span>  
  
    -   <span data-ttu-id="524a8-127">`ExcelTableExists` типа `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="524a8-127">`ExcelTableExists`, of type `Boolean`.</span></span>  
  
    -   <span data-ttu-id="524a8-128">`ExcelFolder` типа `String`.</span><span class="sxs-lookup"><span data-stu-id="524a8-128">`ExcelFolder`, of type `String`.</span></span> <span data-ttu-id="524a8-129">Введите полный путь к папке, содержащей, по меньшей мере, одну книгу Excel.</span><span class="sxs-lookup"><span data-stu-id="524a8-129">Enter the complete path of a folder that contains at least one Excel workbook.</span></span>  
  
    -   <span data-ttu-id="524a8-130">`ExcelFiles` типа `Object`.</span><span class="sxs-lookup"><span data-stu-id="524a8-130">`ExcelFiles`, of type `Object`.</span></span>  
  
    -   <span data-ttu-id="524a8-131">`ExcelTables` типа `Object`.</span><span class="sxs-lookup"><span data-stu-id="524a8-131">`ExcelTables`, of type `Object`.</span></span>  
  
3.  <span data-ttu-id="524a8-132">**Инструкции импорта**.</span><span class="sxs-lookup"><span data-stu-id="524a8-132">**Imports statements**.</span></span> <span data-ttu-id="524a8-133">Для большинства образцов кода необходимо импортировать одно из следующих пространств имен платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] либо оба пространства в начале файла скрипта:</span><span class="sxs-lookup"><span data-stu-id="524a8-133">Most of the code samples require you to import one or both of the following [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] namespaces at the top of your script file:</span></span>  
  
    -   <span data-ttu-id="524a8-134">`System.IO` для операций с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="524a8-134">`System.IO`, for file system operations.</span></span>  
  
    -   <span data-ttu-id="524a8-135">`System.Data.OleDb` для открытия файлов Excel как источников данных.</span><span class="sxs-lookup"><span data-stu-id="524a8-135">`System.Data.OleDb`, to open Excel files as data sources.</span></span>  
  
4.  <span data-ttu-id="524a8-136">**Ссылки**.</span><span class="sxs-lookup"><span data-stu-id="524a8-136">**References**.</span></span> <span data-ttu-id="524a8-137">Для образцов кода, выполняющих чтение данных схемы из файлов Excel, требуется дополнительная ссылка на проект скрипта пространства имен `System.Xml`.</span><span class="sxs-lookup"><span data-stu-id="524a8-137">The code samples that read schema information from Excel files require an additional reference in the script project to the `System.Xml` namespace.</span></span>  
  
5.  <span data-ttu-id="524a8-138">Установите язык скрипта по умолчанию для компонента скрипта, воспользовавшись параметром **Язык скрипта** страницы **Общие** диалогового окна **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="524a8-138">Set the default scripting language for the Script component by using the **Scripting language** option on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="524a8-139">Дополнительные сведения см. в разделе [General Page](../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="524a8-139">For more information, see [General Page](../general-page-of-integration-services-designers-options.md).</span></span>  
  
##  <a name="example-1-description-check-whether-an-excel-file-exists"></a><a name="example1"></a> <span data-ttu-id="524a8-140">Описание примера 1. Проверка существования файла Excel</span><span class="sxs-lookup"><span data-stu-id="524a8-140">Example 1 Description: Check Whether an Excel File Exists</span></span>  
 <span data-ttu-id="524a8-141">В этом примере определяется, существует ли файл книги Excel, указанной в переменной `ExcelFile`, а затем присваивается логическое значение переменной `ExcelFileExists` в соответствии с результатом.</span><span class="sxs-lookup"><span data-stu-id="524a8-141">This example determines whether the Excel workbook file specified in the `ExcelFile` variable exists, and then sets the Boolean value of the `ExcelFileExists` variable to the result.</span></span> <span data-ttu-id="524a8-142">С помощью этого логического значения можно реализовать ветвление в рабочем процессе пакета.</span><span class="sxs-lookup"><span data-stu-id="524a8-142">You can use this Boolean value for branching in the workflow of the package.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="524a8-143">Настройка этого образца задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="524a8-143">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="524a8-144">Добавьте в пакет новую задачу «Скрипт» и измените ее имя на `ExcelFileExists` .</span><span class="sxs-lookup"><span data-stu-id="524a8-144">Add a new Script task to the package and change its name to `ExcelFileExists`.</span></span>  
  
2.  <span data-ttu-id="524a8-145">В **редакторе задачи "Скрипт"** на вкладке **Скрипт** щелкните свойство **ReadOnlyVariables** и введите значение свойства одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="524a8-145">In the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="524a8-146">Введите `ExcelFile`.</span><span class="sxs-lookup"><span data-stu-id="524a8-146">Type `ExcelFile`.</span></span>  
  
         <span data-ttu-id="524a8-147">-или-</span><span class="sxs-lookup"><span data-stu-id="524a8-147">-or-</span></span>  
  
    -   <span data-ttu-id="524a8-148">Нажмите кнопку с многоточием (**...**) рядом с полем свойства и в диалоговом окне **Выбор переменных** выберите `ExcelFile` переменную.</span><span class="sxs-lookup"><span data-stu-id="524a8-148">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelFile` variable.</span></span>  
  
3.  <span data-ttu-id="524a8-149">Щелкните свойство **ReadWriteVariables** и введите значение свойства одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="524a8-149">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="524a8-150">Введите `ExcelFileExists`.</span><span class="sxs-lookup"><span data-stu-id="524a8-150">Type `ExcelFileExists`.</span></span>  
  
         <span data-ttu-id="524a8-151">-или-</span><span class="sxs-lookup"><span data-stu-id="524a8-151">-or-</span></span>  
  
    -   <span data-ttu-id="524a8-152">Нажмите кнопку с многоточием (**...**) рядом с полем свойства и в диалоговом окне **Выбор переменных** выберите `ExcelFileExists` переменную.</span><span class="sxs-lookup"><span data-stu-id="524a8-152">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelFileExists` variable.</span></span>  
  
4.  <span data-ttu-id="524a8-153">Нажмите кнопку **Изменить скрипт**, чтобы открыть редактор скриптов.</span><span class="sxs-lookup"><span data-stu-id="524a8-153">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="524a8-154">В верхней части файла скрипта добавьте инструкцию `Imports` для пространства имен `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="524a8-154">Add an `Imports` statement for the `System.IO` namespace at the top of the script file.</span></span>  
  
6.  <span data-ttu-id="524a8-155">Добавьте следующий код.</span><span class="sxs-lookup"><span data-stu-id="524a8-155">Add the following code.</span></span>  
  
### <a name="example-1-code"></a><span data-ttu-id="524a8-156">Код примера 1</span><span class="sxs-lookup"><span data-stu-id="524a8-156">Example 1 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Dim fileToTest As String  
  
    fileToTest = Dts.Variables("ExcelFile").Value.ToString  
    If File.Exists(fileToTest) Then  
      Dts.Variables("ExcelFileExists").Value = True  
    Else  
      Dts.Variables("ExcelFileExists").Value = False  
    End If  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
  {  
    string fileToTest;  
  
    fileToTest = Dts.Variables["ExcelFile"].Value.ToString();  
    if (File.Exists(fileToTest))  
    {  
      Dts.Variables["ExcelFileExists"].Value = true;  
    }  
    else  
    {  
      Dts.Variables["ExcelFileExists"].Value = false;  
    }  
  
    Dts.TaskResult = (int)ScriptResults.Success;  
  }  
}  
```  
  
##  <a name="example-2-description-check-whether-an-excel-table-exists"></a><a name="example2"></a> <span data-ttu-id="524a8-157">Описание примера 2. Проверка существования таблицы Excel</span><span class="sxs-lookup"><span data-stu-id="524a8-157">Example 2 Description: Check Whether an Excel Table Exists</span></span>  
 <span data-ttu-id="524a8-158">В этом примере определяется, существует ли лист или именованный диапазон Excel, указанный в переменной `ExcelTable`, в книге Excel, указанной в переменной `ExcelFile`, а затем присваивается логическое значение переменной `ExcelTableExists` в соответствии с результатом.</span><span class="sxs-lookup"><span data-stu-id="524a8-158">This example determines whether the Excel worksheet or named range specified in the `ExcelTable` variable exists in the Excel workbook file specified in the `ExcelFile` variable, and then sets the Boolean value of the `ExcelTableExists` variable to the result.</span></span> <span data-ttu-id="524a8-159">С помощью этого логического значения можно реализовать ветвление в рабочем процессе пакета.</span><span class="sxs-lookup"><span data-stu-id="524a8-159">You can use this Boolean value for branching in the workflow of the package.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="524a8-160">Настройка этого образца задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="524a8-160">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="524a8-161">Добавьте в пакет новую задачу «Скрипт» и измените ее имя на `ExcelTableExists` .</span><span class="sxs-lookup"><span data-stu-id="524a8-161">Add a new Script task to the package and change its name to `ExcelTableExists`.</span></span>  
  
2.  <span data-ttu-id="524a8-162">В **редакторе задачи "Скрипт"** на вкладке **Скрипт** щелкните свойство **ReadOnlyVariables** и введите значение свойства одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="524a8-162">In the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="524a8-163">Введите `ExcelTable` и `ExcelFile` разделяйте запятыми`.`</span><span class="sxs-lookup"><span data-stu-id="524a8-163">Type `ExcelTable` and `ExcelFile` separated by commas`.`</span></span>  
  
         <span data-ttu-id="524a8-164">-или-</span><span class="sxs-lookup"><span data-stu-id="524a8-164">-or-</span></span>  
  
    -   <span data-ttu-id="524a8-165">Нажмите кнопку с многоточием (**...**) рядом с полем свойства и в диалоговом окне **Выбор переменных** выберите `ExcelTable` `ExcelFile` переменные и.</span><span class="sxs-lookup"><span data-stu-id="524a8-165">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelTable` and `ExcelFile` variables.</span></span>  
  
3.  <span data-ttu-id="524a8-166">Щелкните свойство **ReadWriteVariables** и введите значение свойства одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="524a8-166">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="524a8-167">Введите `ExcelTableExists`.</span><span class="sxs-lookup"><span data-stu-id="524a8-167">Type `ExcelTableExists`.</span></span>  
  
         <span data-ttu-id="524a8-168">-или-</span><span class="sxs-lookup"><span data-stu-id="524a8-168">-or-</span></span>  
  
    -   <span data-ttu-id="524a8-169">Нажмите кнопку с многоточием (**...**) рядом с полем свойства и в диалоговом окне **Выбор переменных** выберите `ExcelTableExists` переменную.</span><span class="sxs-lookup"><span data-stu-id="524a8-169">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelTableExists` variable.</span></span>  
  
4.  <span data-ttu-id="524a8-170">Нажмите кнопку **Изменить скрипт**, чтобы открыть редактор скриптов.</span><span class="sxs-lookup"><span data-stu-id="524a8-170">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="524a8-171">Добавьте ссылку на сборку `System.Xml` в проект скрипта.</span><span class="sxs-lookup"><span data-stu-id="524a8-171">Add a reference to the `System.Xml` assembly in the script project.</span></span>  
  
6.  <span data-ttu-id="524a8-172">В верхней части файла скрипта добавьте инструкции `Imports` для пространств имен `System.IO` и `System.Data.OleDb`.</span><span class="sxs-lookup"><span data-stu-id="524a8-172">Add `Imports` statements for the `System.IO` and `System.Data.OleDb` namespaces at the top of the script file.</span></span>  
  
7.  <span data-ttu-id="524a8-173">Добавьте следующий код.</span><span class="sxs-lookup"><span data-stu-id="524a8-173">Add the following code.</span></span>  
  
### <a name="example-2-code"></a><span data-ttu-id="524a8-174">Код примера 2</span><span class="sxs-lookup"><span data-stu-id="524a8-174">Example 2 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Dim fileToTest As String  
    Dim tableToTest As String  
    Dim connectionString As String  
    Dim excelConnection As OleDbConnection  
    Dim excelTables As DataTable  
    Dim excelTable As DataRow  
    Dim currentTable As String  
  
    fileToTest = Dts.Variables("ExcelFile").Value.ToString  
    tableToTest = Dts.Variables("ExcelTable").Value.ToString  
  
    Dts.Variables("ExcelTableExists").Value = False  
    If File.Exists(fileToTest) Then  
      connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" & _  
        "Data Source=" & fileToTest & _  
        ";Extended Properties=Excel 8.0"  
      excelConnection = New OleDbConnection(connectionString)  
      excelConnection.Open()  
      excelTables = excelConnection.GetSchema("Tables")  
      For Each excelTable In excelTables.Rows  
        currentTable = excelTable.Item("TABLE_NAME").ToString  
        If currentTable = tableToTest Then  
          Dts.Variables("ExcelTableExists").Value = True  
        End If  
      Next  
    End If  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
    public void Main()  
        {  
            string fileToTest;  
            string tableToTest;  
            string connectionString;  
            OleDbConnection excelConnection;  
            DataTable excelTables;  
            string currentTable;  
  
            fileToTest = Dts.Variables["ExcelFile"].Value.ToString();  
            tableToTest = Dts.Variables["ExcelTable"].Value.ToString();  
  
            Dts.Variables["ExcelTableExists"].Value = false;  
            if (File.Exists(fileToTest))  
            {  
                connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" +  
                "Data Source=" + fileToTest + ";Extended Properties=Excel 8.0";  
                excelConnection = new OleDbConnection(connectionString);  
                excelConnection.Open();  
                excelTables = excelConnection.GetSchema("Tables");  
                foreach (DataRow excelTable in excelTables.Rows)  
                {  
                    currentTable = excelTable["TABLE_NAME"].ToString();  
                    if (currentTable == tableToTest)  
                    {  
                        Dts.Variables["ExcelTableExists"].Value = true;  
                    }  
                }  
            }  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
}  
```  
  
##  <a name="example-3-description-get-a-list-of-excel-files-in-a-folder"></a><a name="example3"></a> <span data-ttu-id="524a8-175">Описание примера 3. Получение списка файлов Excel в папке</span><span class="sxs-lookup"><span data-stu-id="524a8-175">Example 3 Description: Get a List of Excel Files in a Folder</span></span>  
 <span data-ttu-id="524a8-176">В этом примере массив заполняется списком файлов Excel, найденных в папке, которая была указана в качестве значения переменной `ExcelFolder`, а затем этот массив копируется в переменную `ExcelFiles`.</span><span class="sxs-lookup"><span data-stu-id="524a8-176">This example fills an array with the list of Excel files found in the folder specified in the value of the `ExcelFolder` variable, and then copies the array into the `ExcelFiles` variable.</span></span> <span data-ttu-id="524a8-177">Можно использовать перечислитель по объекту из переменной, чтобы выполнить итерацию по файлам в массиве.</span><span class="sxs-lookup"><span data-stu-id="524a8-177">You can use the Foreach from Variable enumerator to iterate over the files in the array.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="524a8-178">Настройка этого образца задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="524a8-178">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="524a8-179">Добавьте в пакет новую задачу "Скрипт" и измените ее имя на **GetExcelFiles**.</span><span class="sxs-lookup"><span data-stu-id="524a8-179">Add a new Script task to the package and change its name to **GetExcelFiles**.</span></span>  
  
2.  <span data-ttu-id="524a8-180">В **редакторе задачи "Скрипт"** на вкладке **Скрипт** щелкните свойство **ReadOnlyVariables** и введите значение свойства одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="524a8-180">Open the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="524a8-181">Введите `ExcelFolder`</span><span class="sxs-lookup"><span data-stu-id="524a8-181">Type `ExcelFolder`</span></span>  
  
         <span data-ttu-id="524a8-182">-или-</span><span class="sxs-lookup"><span data-stu-id="524a8-182">-or-</span></span>  
  
    -   <span data-ttu-id="524a8-183">Нажмите кнопку с многоточием (**...**) рядом с полем свойства и в диалоговом окне **Выбор переменных** выберите переменную ExcelFolder.</span><span class="sxs-lookup"><span data-stu-id="524a8-183">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelFolder variable.</span></span>  
  
3.  <span data-ttu-id="524a8-184">Щелкните свойство **ReadWriteVariables** и введите значение свойства одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="524a8-184">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="524a8-185">Введите `ExcelFiles`.</span><span class="sxs-lookup"><span data-stu-id="524a8-185">Type `ExcelFiles`.</span></span>  
  
         <span data-ttu-id="524a8-186">-или-</span><span class="sxs-lookup"><span data-stu-id="524a8-186">-or-</span></span>  
  
    -   <span data-ttu-id="524a8-187">Нажмите кнопку с многоточием (**...**) рядом с полем свойства и в диалоговом окне **Выбор переменных** выберите переменную ExcelFiles.</span><span class="sxs-lookup"><span data-stu-id="524a8-187">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelFiles variable.</span></span>  
  
4.  <span data-ttu-id="524a8-188">Нажмите кнопку **Изменить скрипт**, чтобы открыть редактор скриптов.</span><span class="sxs-lookup"><span data-stu-id="524a8-188">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="524a8-189">В верхней части файла скрипта добавьте инструкцию `Imports` для пространства имен `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="524a8-189">Add an `Imports` statement for the `System.IO` namespace at the top of the script file.</span></span>  
  
6.  <span data-ttu-id="524a8-190">Добавьте следующий код.</span><span class="sxs-lookup"><span data-stu-id="524a8-190">Add the following code.</span></span>  
  
### <a name="example-3-code"></a><span data-ttu-id="524a8-191">Пример кода 3</span><span class="sxs-lookup"><span data-stu-id="524a8-191">Example 3 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Const FILE_PATTERN As String = "*.xls"  
  
    Dim excelFolder As String  
    Dim excelFiles As String()  
  
    excelFolder = Dts.Variables("ExcelFolder").Value.ToString  
    excelFiles = Directory.GetFiles(excelFolder, FILE_PATTERN)  
  
    Dts.Variables("ExcelFiles").Value = excelFiles  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
  {  
    const string FILE_PATTERN = "*.xls";  
  
    string excelFolder;  
    string[] excelFiles;  
  
    excelFolder = Dts.Variables["ExcelFolder"].Value.ToString();  
    excelFiles = Directory.GetFiles(excelFolder, FILE_PATTERN);  
  
    Dts.Variables["ExcelFiles"].Value = excelFiles;  
  
    Dts.TaskResult = (int)ScriptResults.Success;  
  }  
}  
```  
  
### <a name="alternate-solution"></a><span data-ttu-id="524a8-192">Альтернативное решение</span><span class="sxs-lookup"><span data-stu-id="524a8-192">Alternate Solution</span></span>  
 <span data-ttu-id="524a8-193">Вместо того чтобы использовать задачу «Скрипт» для сбора списка файлов Excel в массив, можно применить перечислитель с циклом по каждому файлу для выполнения итерации по всем файлам Excel в папке.</span><span class="sxs-lookup"><span data-stu-id="524a8-193">Instead of using a Script task to gather a list of Excel files into an array, you can also use the ForEach File enumerator to iterate over all the Excel files in a folder.</span></span> <span data-ttu-id="524a8-194">Дополнительные сведения см. в разделе [Просмотр файлов и таблиц Excel с помощью контейнера "цикл по каждому элементу"](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="524a8-194">For more information, see [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
##  <a name="example-4-description-get-a-list-of-tables-in-an-excel-file"></a><a name="example4"></a> <span data-ttu-id="524a8-195">Описание примера 4. Получение списка таблиц в файле Excel</span><span class="sxs-lookup"><span data-stu-id="524a8-195">Example 4 Description: Get a List of Tables in an Excel File</span></span>  
 <span data-ttu-id="524a8-196">В этом примере массив заполняется списком листов и именованных диапазонов, найденных в файле книги Excel, которая была указана в переменной `ExcelFile`, а затем этот массив копируется в переменную `ExcelTables`.</span><span class="sxs-lookup"><span data-stu-id="524a8-196">This example fills an array with the list of worksheets and named ranges found in the Excel workbook file specified by the value of the `ExcelFile` variable, and then copies the array into the `ExcelTables` variable.</span></span> <span data-ttu-id="524a8-197">Можно использовать перечислитель по объекту из переменной, чтобы выполнить итерацию по таблицам в массиве.</span><span class="sxs-lookup"><span data-stu-id="524a8-197">You can use the Foreach from Variable Enumerator to iterate over the tables in the array.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="524a8-198">Список таблиц в книге Excel включает в себя и листы (которые имеют суффикс $), и именованные диапазоны.</span><span class="sxs-lookup"><span data-stu-id="524a8-198">The list of tables in an Excel workbook includes both worksheets (which have the $ suffix) and named ranges.</span></span> <span data-ttu-id="524a8-199">Если нужно отфильтровать список только по листам или только по именованным диапазонам, то, возможно, понадобится добавить дополнительный код.</span><span class="sxs-lookup"><span data-stu-id="524a8-199">If you have to filter the list for only worksheets or only named ranges, you may have to add additional code for this purpose.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="524a8-200">Настройка этого образца задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="524a8-200">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="524a8-201">Добавьте в пакет новую задачу "Скрипт" и измените ее имя на **GetExcelTables**.</span><span class="sxs-lookup"><span data-stu-id="524a8-201">Add a new Script task to the package and change its name to **GetExcelTables**.</span></span>  
  
2.  <span data-ttu-id="524a8-202">В **редакторе задачи "Скрипт"** на вкладке **Скрипт** щелкните свойство **ReadOnlyVariables** и введите значение свойства одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="524a8-202">Open the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="524a8-203">Введите `ExcelFile`.</span><span class="sxs-lookup"><span data-stu-id="524a8-203">Type `ExcelFile`.</span></span>  
  
         <span data-ttu-id="524a8-204">-или-</span><span class="sxs-lookup"><span data-stu-id="524a8-204">-or-</span></span>  
  
    -   <span data-ttu-id="524a8-205">Нажмите кнопку с многоточием (**...**) рядом с полем свойства и в диалоговом окне **Выбор переменных** выберите переменную ExcelFile.</span><span class="sxs-lookup"><span data-stu-id="524a8-205">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelFile variable.</span></span>  
  
3.  <span data-ttu-id="524a8-206">Щелкните свойство **ReadWriteVariables** и введите значение свойства одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="524a8-206">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="524a8-207">Введите `ExcelTables`.</span><span class="sxs-lookup"><span data-stu-id="524a8-207">Type `ExcelTables`.</span></span>  
  
         <span data-ttu-id="524a8-208">-или-</span><span class="sxs-lookup"><span data-stu-id="524a8-208">-or-</span></span>  
  
    -   <span data-ttu-id="524a8-209">Нажмите кнопку с многоточием (**...**) рядом с полем свойства и в диалоговом окне **Выбор переменных** выберите ексцелтаблесвариабле.</span><span class="sxs-lookup"><span data-stu-id="524a8-209">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelTablesvariable.</span></span>  
  
4.  <span data-ttu-id="524a8-210">Нажмите кнопку **Изменить скрипт**, чтобы открыть редактор скриптов.</span><span class="sxs-lookup"><span data-stu-id="524a8-210">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="524a8-211">Добавьте ссылку на пространство имен `System.Xml` в проект скрипта.</span><span class="sxs-lookup"><span data-stu-id="524a8-211">Add a reference to the `System.Xml` namespace in the script project.</span></span>  
  
6.  <span data-ttu-id="524a8-212">В верхней части файла скрипта добавьте инструкцию `Imports` для пространства имен `System.Data.OleDb`.</span><span class="sxs-lookup"><span data-stu-id="524a8-212">Add an `Imports` statement for the `System.Data.OleDb` namespace at the top of the script file.</span></span>  
  
7.  <span data-ttu-id="524a8-213">Добавьте следующий код.</span><span class="sxs-lookup"><span data-stu-id="524a8-213">Add the following code.</span></span>  
  
### <a name="example-4-code"></a><span data-ttu-id="524a8-214">Код примера 4</span><span class="sxs-lookup"><span data-stu-id="524a8-214">Example 4 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Dim excelFile As String  
    Dim connectionString As String  
    Dim excelConnection As OleDbConnection  
    Dim tablesInFile As DataTable  
    Dim tableCount As Integer = 0  
    Dim tableInFile As DataRow  
    Dim currentTable As String  
    Dim tableIndex As Integer = 0  
  
    Dim excelTables As String()  
  
    excelFile = Dts.Variables("ExcelFile").Value.ToString  
    connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" & _  
        "Data Source=" & excelFile & _  
        ";Extended Properties=Excel 8.0"  
    excelConnection = New OleDbConnection(connectionString)  
    excelConnection.Open()  
    tablesInFile = excelConnection.GetSchema("Tables")  
    tableCount = tablesInFile.Rows.Count  
    ReDim excelTables(tableCount - 1)  
    For Each tableInFile In tablesInFile.Rows  
      currentTable = tableInFile.Item("TABLE_NAME").ToString  
      excelTables(tableIndex) = currentTable  
      tableIndex += 1  
    Next  
  
    Dts.Variables("ExcelTables").Value = excelTables  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
        {  
            string excelFile;  
            string connectionString;  
            OleDbConnection excelConnection;  
            DataTable tablesInFile;  
            int tableCount = 0;  
            string currentTable;  
            int tableIndex = 0;  
  
            string[] excelTables = new string[5];  
  
            excelFile = Dts.Variables["ExcelFile"].Value.ToString();  
            connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" +  
                "Data Source=" + excelFile + ";Extended Properties=Excel 8.0";  
            excelConnection = new OleDbConnection(connectionString);  
            excelConnection.Open();  
            tablesInFile = excelConnection.GetSchema("Tables");  
            tableCount = tablesInFile.Rows.Count;  
  
            foreach (DataRow tableInFile in tablesInFile.Rows)  
            {  
                currentTable = tableInFile["TABLE_NAME"].ToString();  
                excelTables[tableIndex] = currentTable;  
                tableIndex += 1;  
            }  
  
            Dts.Variables["ExcelTables"].Value = excelTables;  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
}  
```  
  
### <a name="alternate-solution"></a><span data-ttu-id="524a8-215">Альтернативное решение</span><span class="sxs-lookup"><span data-stu-id="524a8-215">Alternate Solution</span></span>  
 <span data-ttu-id="524a8-216">Вместо того чтобы использовать задачу «Скрипт» для сбора списка таблиц Excel в массив, можно применить перечислитель по набору строк схемы ADO.NET для перебора всех таблиц (т.е. листов и именованных диапазонов) в файле книги Excel.</span><span class="sxs-lookup"><span data-stu-id="524a8-216">Instead of using a Script task to gather a list of Excel tables into an array, you can also use the ForEach ADO.NET Schema Rowset Enumerator to iterate over all the tables (that is, worksheets and named ranges) in an Excel workbook file.</span></span> <span data-ttu-id="524a8-217">Дополнительные сведения см. в разделе [Просмотр файлов и таблиц Excel с помощью контейнера "цикл по каждому элементу"](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="524a8-217">For more information, see [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
##  <a name="displaying-the-results-of-the-samples"></a><a name="testing"></a><span data-ttu-id="524a8-218">Отображение результатов выборок</span><span class="sxs-lookup"><span data-stu-id="524a8-218">Displaying the Results of the Samples</span></span>  
 <span data-ttu-id="524a8-219">Если все образцы в этом разделе были настроены для использования с одним пакетом, можно соединить все задачи «Скрипт» с дополнительной задачей «Скрипт», отображающей выход всех образцов.</span><span class="sxs-lookup"><span data-stu-id="524a8-219">If you have configured each of the examples in this topic in the same package, you can connect all the Script tasks to an additional Script task that displays the output of all the examples.</span></span>  
  
#### <a name="to-configure-a-script-task-to-display-the-output-of-the-examples-in-this-topic"></a><span data-ttu-id="524a8-220">Настройка задачи «Скрипт» для отображения выхода всех образцов в этом разделе</span><span class="sxs-lookup"><span data-stu-id="524a8-220">To configure a Script task to display the output of the examples in this topic</span></span>  
  
1.  <span data-ttu-id="524a8-221">Добавьте в пакет новую задачу "Скрипт" и измените ее имя на **DisplayResults**.</span><span class="sxs-lookup"><span data-stu-id="524a8-221">Add a new Script task to the package and change its name to **DisplayResults**.</span></span>  
  
2.  <span data-ttu-id="524a8-222">Соедините каждую задачу "Скрипт" всех четырех образцов друг с другом, чтобы каждая задача выполнялась после успешного завершения предыдущей, и соедините задачу четвертого образца с задачей **DisplayResults**.</span><span class="sxs-lookup"><span data-stu-id="524a8-222">Connect each of the four example Script tasks to one another, so that each task runs after the preceding task completes successfully, and connect the fourth example task to the **DisplayResults** task.</span></span>  
  
3.  <span data-ttu-id="524a8-223">Откройте задачу **DisplayResults** в **редакторе задачи "Скрипт"**.</span><span class="sxs-lookup"><span data-stu-id="524a8-223">Open the **DisplayResults** task in the **Script Task Editor**.</span></span>  
  
4.  <span data-ttu-id="524a8-224">На вкладке **Скрипт** щелкните **ReadOnlyVariables** и используйте один из следующих методов, чтобы добавить все семь переменных, перечисленных в разделе [Настройка пакета для тестирования образцов](#configuring):</span><span class="sxs-lookup"><span data-stu-id="524a8-224">On the **Script** tab, click **ReadOnlyVariables** and use one of the following methods to add all seven variables listed in [Configuring a Package to Test the Samples](#configuring):</span></span>  
  
    -   <span data-ttu-id="524a8-225">Введите имена переменных, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="524a8-225">Type the name of each variable separated by commas.</span></span>  
  
         <span data-ttu-id="524a8-226">-или-</span><span class="sxs-lookup"><span data-stu-id="524a8-226">-or-</span></span>  
  
    -   <span data-ttu-id="524a8-227">Нажмите кнопку с многоточием (**...**) рядом с полем свойства и в диалоговом окне **Выбор переменных** выберите переменные.</span><span class="sxs-lookup"><span data-stu-id="524a8-227">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, selecting the variables.</span></span>  
  
5.  <span data-ttu-id="524a8-228">Нажмите кнопку **Изменить скрипт**, чтобы открыть редактор скриптов.</span><span class="sxs-lookup"><span data-stu-id="524a8-228">Click **Edit Script** to open the script editor.</span></span>  
  
6.  <span data-ttu-id="524a8-229">В верхней части файла скрипта добавьте инструкции `Imports` для пространств имен `Microsoft.VisualBasic` и `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="524a8-229">Add `Imports` statements for the `Microsoft.VisualBasic` and `System.Windows.Forms` namespaces at the top of the script file.</span></span>  
  
7.  <span data-ttu-id="524a8-230">Добавьте следующий код.</span><span class="sxs-lookup"><span data-stu-id="524a8-230">Add the following code.</span></span>  
  
8.  <span data-ttu-id="524a8-231">Выполните пакет и просмотрите результаты, отобразившиеся в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="524a8-231">Run the package and examine the results displayed in a message box.</span></span>  
  
### <a name="code-to-display-the-results"></a><span data-ttu-id="524a8-232">Код для отображения результатов</span><span class="sxs-lookup"><span data-stu-id="524a8-232">Code to Display the Results</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Const EOL As String = ControlChars.CrLf  
  
    Dim results As String  
    Dim filesInFolder As String()  
    Dim fileInFolder As String  
    Dim tablesInFile As String()  
    Dim tableInFile As String  
  
    results = _  
      "Final values of variables:" & EOL & _  
      "ExcelFile: " & Dts.Variables("ExcelFile").Value.ToString & EOL & _  
      "ExcelFileExists: " & Dts.Variables("ExcelFileExists").Value.ToString & EOL & _  
      "ExcelTable: " & Dts.Variables("ExcelTable").Value.ToString & EOL & _  
      "ExcelTableExists: " & Dts.Variables("ExcelTableExists").Value.ToString & EOL & _  
      "ExcelFolder: " & Dts.Variables("ExcelFolder").Value.ToString & EOL & _  
      EOL  
  
    results &= "Excel files in folder: " & EOL  
    filesInFolder = DirectCast(Dts.Variables("ExcelFiles").Value, String())  
    For Each fileInFolder In filesInFolder  
      results &= " " & fileInFolder & EOL  
    Next  
    results &= EOL  
  
    results &= "Excel tables in file: " & EOL  
    tablesInFile = DirectCast(Dts.Variables("ExcelTables").Value, String())  
    For Each tableInFile In tablesInFile  
      results &= " " & tableInFile & EOL  
    Next  
  
    MessageBox.Show(results, "Results", MessageBoxButtons.OK, MessageBoxIcon.Information)  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
        {  
            const string EOL = "\r";  
  
            string results;  
            string[] filesInFolder;  
            //string fileInFolder;  
            string[] tablesInFile;  
            //string tableInFile;  
  
            results = "Final values of variables:" + EOL + "ExcelFile: " + Dts.Variables["ExcelFile"].Value.ToString() + EOL + "ExcelFileExists: " + Dts.Variables["ExcelFileExists"].Value.ToString() + EOL + "ExcelTable: " + Dts.Variables["ExcelTable"].Value.ToString() + EOL + "ExcelTableExists: " + Dts.Variables["ExcelTableExists"].Value.ToString() + EOL + "ExcelFolder: " + Dts.Variables["ExcelFolder"].Value.ToString() + EOL + EOL;  
  
            results += "Excel files in folder: " + EOL;  
            filesInFolder = (string[])(Dts.Variables["ExcelFiles"].Value);  
            foreach (string fileInFolder in filesInFolder)  
            {  
                results += " " + fileInFolder + EOL;  
            }  
            results += EOL;  
  
            results += "Excel tables in file: " + EOL;  
            tablesInFile = (string[])(Dts.Variables["ExcelTables"].Value);  
            foreach (string tableInFile in tablesInFile)  
            {  
                results += " " + tableInFile + EOL;  
            }  
  
            MessageBox.Show(results, "Results", MessageBoxButtons.OK, MessageBoxIcon.Information);  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
}  
```  
  
<span data-ttu-id="524a8-233">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="524a8-233">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="524a8-234">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="524a8-234">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="524a8-235">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="524a8-235">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="524a8-236">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="524a8-236">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="524a8-237">См. также:</span><span class="sxs-lookup"><span data-stu-id="524a8-237">See Also</span></span>  
 <span data-ttu-id="524a8-238">[Диспетчер соединений с Excel](../connection-manager/excel-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="524a8-238">[Excel Connection Manager](../connection-manager/excel-connection-manager.md) </span></span>  
 [<span data-ttu-id="524a8-239">Просмотр файлов и таблиц Excel с помощью контейнера «цикл по каждому элементу»</span><span class="sxs-lookup"><span data-stu-id="524a8-239">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](../control-flow/foreach-loop-container.md)  
  
  
