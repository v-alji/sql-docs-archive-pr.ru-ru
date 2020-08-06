---
title: Работа с изображениями в задаче "Скрипт" | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- graphics [Integration Services]
- Script task [Integration Services], images
- Drawing namespace
- images [Integration Services]
- SSIS Script task, images
- Script task [Integration Services], examples
- thumbnails [Integration Services]
- System.Drawing namespace
- JPEG format [Integration Services]
- .jpeg files
ms.assetid: 74aeb7ab-51b2-4b9f-84ee-0b46a7908ab9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 75a5b72f87a4463d7270dc9f28529a81525860cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664424"
---
# <a name="working-with-images-with-the-script-task"></a><span data-ttu-id="4121f-102">Работа с изображениями в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="4121f-102">Working with Images with the Script Task</span></span>
  <span data-ttu-id="4121f-103">База данных продуктов или пользователи часто содержат изображения в дополнение к тексту и числовым данным.</span><span class="sxs-lookup"><span data-stu-id="4121f-103">A database of products or users frequently includes images in addition to text and numeric data.</span></span> <span data-ttu-id="4121f-104">Пространство имен `System.Drawing` платформы Microsoft .NET Framework предоставляет классы для управления изображениями.</span><span class="sxs-lookup"><span data-stu-id="4121f-104">The `System.Drawing` namespace in the Microsoft .NET Framework provides classes for manipulating images.</span></span>  
  
 [<span data-ttu-id="4121f-105">Пример 1. Преобразование изображений в формат JPEG</span><span class="sxs-lookup"><span data-stu-id="4121f-105">Example 1: Convert Images to JPEG Format</span></span>](#example1)  
  
 [<span data-ttu-id="4121f-106">Пример 2. Создание и сохранение уменьшенных представлений изображений</span><span class="sxs-lookup"><span data-stu-id="4121f-106">Example 2: Create and Save Thumbnail Images</span></span>](#example2)  
  
> [!NOTE]  
>  <span data-ttu-id="4121f-107">Если нужно создать задачу, которую будет удобно использовать в нескольких пакетах, рекомендуется начать разработку пользовательской задачи с этого образца задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="4121f-107">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="4121f-108">Дополнительные сведения см. в разделе [Разработка пользовательской задачи](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="4121f-108">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
##  <a name="example-1-description-convert-images-to-jpeg-format"></a><a name="example1"></a> <span data-ttu-id="4121f-109">Описание примера 1. Преобразование изображений в формат JPEG</span><span class="sxs-lookup"><span data-stu-id="4121f-109">Example 1 Description: Convert Images to JPEG Format</span></span>  
 <span data-ttu-id="4121f-110">В следующем примере открывается указанный переменной файл изображения. Затем он сохраняется как сжатый JPEG-файл с использованием кодировщика.</span><span class="sxs-lookup"><span data-stu-id="4121f-110">The following example opens an image file specified by a variable and saves it as a compressed JPEG file by using an encoder.</span></span> <span data-ttu-id="4121f-111">Код для получения данных кодировщика инкапсулирован в закрытой функции.</span><span class="sxs-lookup"><span data-stu-id="4121f-111">The code to retrieve encoder information is encapsulated in a private function.</span></span>  
  
#### <a name="to-configure-this-script-task-example-for-use-with-a-single-image-file"></a><span data-ttu-id="4121f-112">Настройка этого примера задачи «Скрипт» для работы с одним файлом изображения</span><span class="sxs-lookup"><span data-stu-id="4121f-112">To configure this Script Task example for use with a single image file</span></span>  
  
1.  <span data-ttu-id="4121f-113">Создайте строковую переменную с именем `CurrentImageFile` и задайте в качестве ее значения путь и имя существующего файла изображения.</span><span class="sxs-lookup"><span data-stu-id="4121f-113">Create a string variable named `CurrentImageFile` and set its value to the path and file name of an existing image file.</span></span>  
  
2.  <span data-ttu-id="4121f-114">На странице **Скрипт** в **редакторе задачи "Скрипт**" добавьте `CurrentImageFile` переменную в `ReadOnlyVariables` свойство.</span><span class="sxs-lookup"><span data-stu-id="4121f-114">On the **Script** page of the **Script Task Editor**, add the `CurrentImageFile` variable to the `ReadOnlyVariables` property.</span></span>  
  
3.  <span data-ttu-id="4121f-115">В проекте скрипта добавьте ссылку на пространство имен `System.Drawing`.</span><span class="sxs-lookup"><span data-stu-id="4121f-115">In the script project, set a reference to the `System.Drawing` namespace.</span></span>  
  
4.  <span data-ttu-id="4121f-116">Добавьте в код инструкции `Imports`, чтобы импортировать пространства имен `System.Drawing` и `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="4121f-116">In your code, use `Imports` statements to import the `System.Drawing` and `System.IO` namespaces.</span></span>  
  
#### <a name="to-configure-this-script-task-example-for-use-with-multiple-image-files"></a><span data-ttu-id="4121f-117">Настройка этого примера задачи «Скрипт» для работы с несколькими файлами изображения</span><span class="sxs-lookup"><span data-stu-id="4121f-117">To configure this Script Task example for use with multiple image files</span></span>  
  
1.  <span data-ttu-id="4121f-118">Поместите задачу «Скрипт» в контейнер «цикл по каждому элементу».</span><span class="sxs-lookup"><span data-stu-id="4121f-118">Place the Script task within a Foreach Loop container.</span></span>  
  
2.  <span data-ttu-id="4121f-119">На странице **Коллекция** окна **Редактор циклов по каждому элементу** выберите **Перечислитель с циклом по каждому файлу** в качестве перечислителя и укажите путь и маску исходных файлов, например "\*.bmp".</span><span class="sxs-lookup"><span data-stu-id="4121f-119">On the **Collection** page of the **Foreach Loop Editor**, select the **Foreach File Enumerator** as the enumerator, and specify the path and file mask of the source files, such as "\*.bmp."</span></span>  
  
3.  <span data-ttu-id="4121f-120">На странице **Сопоставления переменной** сопоставьте переменную `CurrentImageFile` с индексом 0.</span><span class="sxs-lookup"><span data-stu-id="4121f-120">On the **Variable Mappings** page, map the `CurrentImageFile` variable to Index 0.</span></span> <span data-ttu-id="4121f-121">Эта переменная передает текущее имя файла в задачу «Скрипт» на каждом проходе перечислителя.</span><span class="sxs-lookup"><span data-stu-id="4121f-121">This variable passes the current file name to the Script task on each iteration of the enumerator.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4121f-122">Эти шаги выполняются дополнительно к шагам, перечисленным в процедуре для использования одного файла изображения.</span><span class="sxs-lookup"><span data-stu-id="4121f-122">These steps are in addition to the steps listed in the procedure for use with a single image file.</span></span>  
  
### <a name="example-1-code"></a><span data-ttu-id="4121f-123">Код примера 1</span><span class="sxs-lookup"><span data-stu-id="4121f-123">Example 1 Code</span></span>  
  
```vb  
Public Sub Main()  
  
    'Create and initialize variables.  
    Dim currentFile As String  
    Dim newFile As String  
    Dim bmp As Bitmap  
    Dim eps As New Imaging.EncoderParameters(1)  
    Dim ici As Imaging.ImageCodecInfo  
    Dim supportedExtensions() As String = _  
        {".BMP", ".GIF", ".JPG", ".JPEG", ".EXIF", ".PNG", _  
        ".TIFF", ".TIF", ".ICO", ".ICON"}  
  
    Try  
        'Store the variable in a string for local manipulation.  
        currentFile = Dts.Variables("CurrentImageFile").Value.ToString  
        'Check the extension of the file against a list of  
        'files that the Bitmap class supports.  
        If Array.IndexOf(supportedExtensions, _  
            Path.GetExtension(currentFile).ToUpper) > -1 Then  
  
            'Load the file.  
            bmp = New Bitmap(currentFile)  
  
            'Calculate the new name for the compressed image.  
            'Note: This will overwrite existing JPEGs.  
            newFile = Path.Combine( _  
                Path.GetDirectoryName(currentFile), _  
                String.Concat(Path.GetFileNameWithoutExtension(currentFile), _  
                ".jpg"))  
  
            'Specify the compression ratio (0=worst quality, 100=best quality).  
            eps.Param(0) = New Imaging.EncoderParameter( _  
                Imaging.Encoder.Quality, 75)  
  
            'Retrieve the ImageCodecInfo associated with the jpeg format.  
            ici = GetEncoderInfo("image/jpeg")  
  
            'Save the file, compressing it into the jpeg encoding.  
            bmp.Save(newFile, ici, eps)  
        Else  
            'The file is not supported by the Bitmap class.  
            Dts.Events.FireWarning(0, "Image Resampling Sample", _  
                "File " & currentFile & " is not a supported format.", _  
                "", 0)  
         End If  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        'An error occurred.  
        Dts.Events.FireError(0, "Image Resampling Sample", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
  
Private Function GetEncoderInfo(ByVal mimeType As String) As Imaging.ImageCodecInfo  
  
    'The available image codecs are returned as an array,  
    'which requires code to iterate until the specified codec is found.  
  
    Dim count As Integer  
    Dim encoders() As Imaging.ImageCodecInfo  
  
    encoders = Imaging.ImageCodecInfo.GetImageEncoders()  
  
    For count = 0 To encoders.Length  
        If encoders(count).MimeType = mimeType Then  
            Return encoders(count)  
        End If  
    Next  
  
    'This point is only reached if a codec is not found.  
    Err.Raise(513, "Image Resampling Sample", String.Format( _  
        "The {0} codec is not available. Unable to compress file.", _  
            mimeType))  
    Return Nothing  
  
End Function  
  
```  
  
##  <a name="example-2-description-create-and-save-thumbnail-images"></a><a name="example2"></a> <span data-ttu-id="4121f-124">Описание примера 2. Создание и сохранение уменьшенных представлений изображений</span><span class="sxs-lookup"><span data-stu-id="4121f-124">Example 2 Description: Create and Save Thumbnail Images</span></span>  
 <span data-ttu-id="4121f-125">В следующем примере открывается файл изображения, заданный переменной, создается уменьшенное представление изображения с сохранением постоянной пропорции и сохраняется уменьшенное представление с измененным именем файла.</span><span class="sxs-lookup"><span data-stu-id="4121f-125">The following example opens an image file specified by a variable, creates a thumbnail of the image while maintaining a constant aspect ratio, and saves the thumbnail with a modified file name.</span></span> <span data-ttu-id="4121f-126">Код для вычисления высоты и ширины уменьшенного представления с сохранением постоянной пропорции инкапсулирован в закрытой подпрограмме.</span><span class="sxs-lookup"><span data-stu-id="4121f-126">The code that calculates the height and width of the thumbnail while maintaining a constant aspect ratio is encapsulated in a private subroutine.</span></span>  
  
#### <a name="to-configure-this-script-task-example-for-use-with-a-single-image-file"></a><span data-ttu-id="4121f-127">Настройка этого примера задачи «Скрипт» для работы с одним файлом изображения</span><span class="sxs-lookup"><span data-stu-id="4121f-127">To configure this Script Task example for use with a single image file</span></span>  
  
1.  <span data-ttu-id="4121f-128">Создайте строковую переменную с именем `CurrentImageFile` и задайте в качестве ее значения путь и имя существующего файла изображения.</span><span class="sxs-lookup"><span data-stu-id="4121f-128">Create a string variable named `CurrentImageFile` and set its value to the path and file name of an existing image file.</span></span>  
  
2.  <span data-ttu-id="4121f-129">Создайте также целочисленную переменную `MaxThumbSize` и присвойте значение в пикселях, например 100.</span><span class="sxs-lookup"><span data-stu-id="4121f-129">Also create the `MaxThumbSize` integer variable and assign a value in pixels, such as 100.</span></span>  
  
3.  <span data-ttu-id="4121f-130">На странице **Скрипт** в **редакторе задачи «Скрипт**» добавьте обе переменные в `ReadOnlyVariables` свойство.</span><span class="sxs-lookup"><span data-stu-id="4121f-130">On the **Script** page of the **Script Task Editor**, add both variables to the `ReadOnlyVariables` property.</span></span>  
  
4.  <span data-ttu-id="4121f-131">В проекте скрипта добавьте ссылку на пространство имен `System.Drawing`.</span><span class="sxs-lookup"><span data-stu-id="4121f-131">In the script project, set a reference to the `System.Drawing` namespace.</span></span>  
  
5.  <span data-ttu-id="4121f-132">Добавьте в код инструкции `Imports`, чтобы импортировать пространства имен `System.Drawing` и `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="4121f-132">In your code, use `Imports` statements to import the `System.Drawing` and `System.IO` namespaces.</span></span>  
  
#### <a name="to-configure-this-script-task-example-for-use-with-multiple-image-files"></a><span data-ttu-id="4121f-133">Настройка этого примера задачи «Скрипт» для работы с несколькими файлами изображения</span><span class="sxs-lookup"><span data-stu-id="4121f-133">To configure this Script Task example for use with multiple image files</span></span>  
  
1.  <span data-ttu-id="4121f-134">Поместите задачу «Скрипт» в контейнер «цикл по каждому элементу».</span><span class="sxs-lookup"><span data-stu-id="4121f-134">Place the Script task within a Foreach Loop container.</span></span>  
  
2.  <span data-ttu-id="4121f-135">На странице **Коллекция** окна **Редактор циклов по каждому элементу** выберите **Перечислитель с циклом по каждому файлу** в качестве **перечислителя** и укажите путь и маску исходных файлов, например "\*.jpg".</span><span class="sxs-lookup"><span data-stu-id="4121f-135">On the **Collection** page of the **Foreach Loop Editor**, select the **Foreach File Enumerator** as the **Enumerator**, and specify the path and file mask of the source files, such as "\*.jpg."</span></span>  
  
3.  <span data-ttu-id="4121f-136">На странице **Сопоставления переменной** сопоставьте переменную `CurrentImageFile` с индексом 0.</span><span class="sxs-lookup"><span data-stu-id="4121f-136">On the **Variable Mappings** page, map the `CurrentImageFile` variable to Index 0.</span></span> <span data-ttu-id="4121f-137">Эта переменная передает текущее имя файла в задачу «Скрипт» на каждом проходе перечислителя.</span><span class="sxs-lookup"><span data-stu-id="4121f-137">This variable passes the current file name to the Script task on each iteration of the enumerator.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4121f-138">Эти шаги выполняются дополнительно к шагам, перечисленным в процедуре для использования одного файла изображения.</span><span class="sxs-lookup"><span data-stu-id="4121f-138">These steps are in addition to the steps listed in the procedure for use with a single image file.</span></span>  
  
### <a name="example-2-code"></a><span data-ttu-id="4121f-139">Код примера 2</span><span class="sxs-lookup"><span data-stu-id="4121f-139">Example 2 Code</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim currentImageFile As String  
    Dim currentImage As Image  
    Dim maxThumbSize As Integer  
    Dim thumbnailImage As Image  
    Dim thumbnailFile As String  
    Dim thumbnailHeight As Integer  
    Dim thumbnailWidth As Integer  
  
    currentImageFile = Dts.Variables("CurrentImageFile").Value.ToString  
    thumbnailFile = Path.Combine( _  
        Path.GetDirectoryName(currentImageFile), _  
        String.Concat(Path.GetFileNameWithoutExtension(currentImageFile), _  
        "_thumbnail.jpg"))  
  
    Try  
        currentImage = Image.FromFile(currentImageFile)  
  
        maxThumbSize = CType(Dts.Variables("MaxThumbSize").Value, Integer)  
        CalculateThumbnailSize( _  
            maxThumbSize, currentImage, thumbnailWidth, thumbnailHeight)  
  
        thumbnailImage = currentImage.GetThumbnailImage( _  
           thumbnailWidth, thumbnailHeight, Nothing, Nothing)  
        thumbnailImage.Save(thumbnailFile)  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        Dts.Events.FireError(0, "Script Task Example", _  
        ex.Message & ControlChars.CrLf & ex.StackTrace, _  
        String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
  
Private Sub CalculateThumbnailSize( _  
    ByVal maxSize As Integer, ByVal sourceImage As Image, _  
    ByRef thumbWidth As Integer, ByRef thumbHeight As Integer)  
  
    If sourceImage.Width > sourceImage.Height Then  
        thumbWidth = maxSize  
        thumbHeight = CInt((maxSize / sourceImage.Width) * sourceImage.Height)  
    Else  
        thumbHeight = maxSize  
        thumbWidth = CInt((maxSize / sourceImage.Height) * sourceImage.Width)  
    End If  
  
End Sub  
```  
  
```csharp  
bool ThumbnailCallback()  
        {  
            return false;  
        }  
        public void Main()  
        {  
  
            string currentImageFile;  
            Image currentImage;  
            int maxThumbSize;  
            Image thumbnailImage;  
            string thumbnailFile;  
            int thumbnailHeight = 0;  
            int thumbnailWidth = 0;  
  
            currentImageFile = Dts.Variables["CurrentImageFile"].Value.ToString();  
            thumbnailFile = Path.Combine(Path.GetDirectoryName(currentImageFile), String.Concat(Path.GetFileNameWithoutExtension(currentImageFile), "_thumbnail.jpg"));  
  
            try  
            {  
  
                currentImage = Image.FromFile(currentImageFile);  
  
                maxThumbSize = (int)Dts.Variables["MaxThumbSize"].Value;  
                CalculateThumbnailSize(maxThumbSize, currentImage, ref thumbnailWidth, ref thumbnailHeight);  
  
                Image.GetThumbnailImageAbort myCallback = new Image.GetThumbnailImageAbort(ThumbnailCallback);  
  
                thumbnailImage = currentImage.GetThumbnailImage(thumbnailWidth, thumbnailHeight, ThumbnailCallback, IntPtr.Zero);  
                thumbnailImage.Save(thumbnailFile);  
                Dts.TaskResult = (int)ScriptResults.Success;  
            }  
            catch (Exception ex)  
            {  
                Dts.Events.FireError(0, "Script Task Example", ex.Message + "\r" + ex.StackTrace, String.Empty, 0);  
                Dts.TaskResult = (int)ScriptResults.Failure;  
            }  
  
        }  
  
        private void CalculateThumbnailSize(int maxSize, Image sourceImage, ref int thumbWidth, ref int thumbHeight)  
        {  
  
            if (sourceImage.Width > sourceImage.Height)  
            {  
                thumbWidth = maxSize;  
                thumbHeight = (int)(sourceImage.Height * maxSize / sourceImage.Width);  
            }  
            else  
            {  
                thumbHeight = maxSize;  
                thumbWidth = (int)(sourceImage.Width * maxSize / sourceImage.Height);  
  
            }  
  
        }  
  
```  
  
<span data-ttu-id="4121f-140">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="4121f-140">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="4121f-141">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="4121f-141">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="4121f-142">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="4121f-142">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="4121f-143">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="4121f-143">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
