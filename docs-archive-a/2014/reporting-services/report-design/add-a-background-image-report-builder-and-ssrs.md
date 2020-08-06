---
title: Добавление фонового изображения (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c777fefb-8695-44a7-b5cd-a18c587583f2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d7bc15e1b063a73c463cdb1e7e99075af2a3dce9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739389"
---
# <a name="add-a-background-image-report-builder-and-ssrs"></a><span data-ttu-id="15096-102">Добавление фонового изображения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="15096-102">Add a Background Image (Report Builder and SSRS)</span></span>
  <span data-ttu-id="15096-103">Фоновое изображение можно добавлять к таким элементам отчета, как прямоугольник, текстовое поле, список, матрица, таблица и некоторые части диаграммы, либо к разделу отчета, например к верхнему и нижнему колонтитулу страницы или тексту отчета.</span><span class="sxs-lookup"><span data-stu-id="15096-103">You can add a background image to a report item such as a rectangle, text box, list, matrix, table, and some parts of a chart, or a report section such as the page header, page footer, or report body.</span></span> <span data-ttu-id="15096-104">Фоновое изображение можно указать для любого выбранного элемента в области конструктора отчета, на панели свойств которого имеется раздел **BackgroundImage** .</span><span class="sxs-lookup"><span data-stu-id="15096-104">You can define a background image for any selected item on the report design surface that displays **BackgroundImage** in the Properties pane.</span></span> <span data-ttu-id="15096-105">Подобно другим изображениям, фоновое изображение может быть представлено ссылкой на URL-адрес изображения на сервере отчетов, изображением в поле набора данных или изображением, внедренным в определение отчета.</span><span class="sxs-lookup"><span data-stu-id="15096-105">Like other images, the background image can be a URL to an image on the report server, an image from a dataset field, or an image embedded in the report definition.</span></span> <span data-ttu-id="15096-106">Чтобы использовать изображение, внедренное в отчет, сначала необходимо добавить изображение к определению отчета, а затем добавить изображение в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="15096-106">To use an image embedded in the report, you must first add the image to the report definition before you can add the image to the design surface.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-embed-an-image-in-the-report-definition"></a><span data-ttu-id="15096-107">Внедрение изображения в определение отчета</span><span class="sxs-lookup"><span data-stu-id="15096-107">To embed an image in the report definition</span></span>  
  
1.  <span data-ttu-id="15096-108">В области данных отчета щелкните правой кнопкой мыши узел **Изображения** и выберите команду **Добавить изображение**.</span><span class="sxs-lookup"><span data-stu-id="15096-108">In the Report Data pane, right-click the **Images** node, and then click **Add Image**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="15096-109">Если область данных отчета не отображается, на вкладке **Вид** выберите пункт **Данные отчета**.</span><span class="sxs-lookup"><span data-stu-id="15096-109">If the Report Data pane is not visible, on the **View** tab, click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="15096-110">Выберите изображение, которое требуется внедрить в определение отчета, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="15096-110">Navigate to the image you want to embed in your report definition, and then click **OK**.</span></span>  
  
### <a name="to-add-a-background-image"></a><span data-ttu-id="15096-111">Добавление фонового изображения</span><span class="sxs-lookup"><span data-stu-id="15096-111">To add a background image</span></span>  
  
1.  <span data-ttu-id="15096-112">В режиме конструктора отчетов выберите элемент отчета, к которому нужно добавить фоновое изображение.</span><span class="sxs-lookup"><span data-stu-id="15096-112">In report design view, select the report item to which you want to add a background image.</span></span>  
  
2.  <span data-ttu-id="15096-113">Если панель свойств не отображается, выберите пункт **Свойства** на вкладке **Вид**.</span><span class="sxs-lookup"><span data-stu-id="15096-113">If the Properties pane is not visible, on the **View** tab, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="15096-114">На панели свойств разверните узел **BackgroundImage**и выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="15096-114">In the Properties pane, expand **BackgroundImage**, and then do the following:</span></span>  
  
    -   <span data-ttu-id="15096-115">Для внедренного изображения</span><span class="sxs-lookup"><span data-stu-id="15096-115">For an embedded image:</span></span>  
  
         <span data-ttu-id="15096-116">Задайте для свойства **Источник** значение **Внедренный**.</span><span class="sxs-lookup"><span data-stu-id="15096-116">Set **Source** to **Embedded**.</span></span>  
  
         <span data-ttu-id="15096-117">Укажите в качестве **Значения** имя изображения, внедренного в отчет.</span><span class="sxs-lookup"><span data-stu-id="15096-117">Set **Value** to the name of an image that is embedded in the report.</span></span>  
  
    -   <span data-ttu-id="15096-118">Для внешнего изображения</span><span class="sxs-lookup"><span data-stu-id="15096-118">For an external image:</span></span>  
  
         <span data-ttu-id="15096-119">Задайте для свойства **Источник** значение **Внешний**.</span><span class="sxs-lookup"><span data-stu-id="15096-119">Set **Source** to **External**.</span></span>  
  
         <span data-ttu-id="15096-120">Укажите в качестве **Значения** действительный путь к изображению.</span><span class="sxs-lookup"><span data-stu-id="15096-120">Set **Value** to a valid path to an image.</span></span> <span data-ttu-id="15096-121">Изображение может находиться на сервере отчетов в собственном режиме или в режиме интеграции с SharePoint либо находиться на любом другом веб-сайте.</span><span class="sxs-lookup"><span data-stu-id="15096-121">This can be on a report server in native mode or SharePoint integrated mode, or it can be on any other Web site.</span></span> <span data-ttu-id="15096-122">Дополнительные сведения см. в разделе [Добавление внешнего изображения (построитель отчетов и службы SSRS)](add-an-external-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="15096-122">For more information, see [Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span></span>  
  
    -   <span data-ttu-id="15096-123">Если изображение содержится в поле базы данных, с которой соединен элемент отчета, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="15096-123">For an image is that is contained in a field in the database to which the report item is connected:</span></span>  
  
         <span data-ttu-id="15096-124">Задайте для свойства **Источник** значение **База данных**.</span><span class="sxs-lookup"><span data-stu-id="15096-124">Set **Source** to **Database**.</span></span>  
  
         <span data-ttu-id="15096-125">Укажите в качестве **Значения** имя поля в наборе данных отчета.</span><span class="sxs-lookup"><span data-stu-id="15096-125">Set **Value** to the name of a field in the report dataset.</span></span> <span data-ttu-id="15096-126">Дополнительные сведения см. в разделе [Добавление привязанного к данным изображения (построитель отчетов и службы SSRS)](add-a-data-bound-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="15096-126">For more information, see [Add a Data-Bound Image &#40;Report Builder and SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span></span>  
  
         <span data-ttu-id="15096-127">В свойстве **MIMEType** или в формате файла выберите для изображения соответствующий тип MIME, например BMP.</span><span class="sxs-lookup"><span data-stu-id="15096-127">For **MIMEType**, or file format, select the appropriate MIME type for the image-for example, .bmp.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="15096-128">Значение MIMEType применяется только в том случае, если свойство **Источник** имеет значение **База данных**.</span><span class="sxs-lookup"><span data-stu-id="15096-128">MIMEType applies only if the **Source** property is set to **Database**.</span></span> <span data-ttu-id="15096-129">Если свойство **Источник** установлено как **Внешний** или **Внедренный**, то значение **MIMEType** игнорируется.</span><span class="sxs-lookup"><span data-stu-id="15096-129">If the **Source** property is set to **External** or **Embedded**, the value of **MIMEType** is ignored.</span></span>  
  
    -   <span data-ttu-id="15096-130">Для свойства **BackgroundRepeat**выберите выражение, **Default**, **Repeat**, **RepeatX**, **RepeatY**или **Clip**.</span><span class="sxs-lookup"><span data-stu-id="15096-130">For **BackgroundRepeat**, select an expression, **Default**, **Repeat**, **RepeatX**, or **RepeatY**, or **Clip**.</span></span>  
  
         <span data-ttu-id="15096-131">Для фоновых изображений в диаграмме свойству **BackgroundRepeat** можно присвоить значение **Default**, **Repeat**, **Fit**и **Clip**, но не **RepeatX** или **RepeatY**.</span><span class="sxs-lookup"><span data-stu-id="15096-131">For background images in a chart, **BackgroundRepeat** can be set to **Default**, **Repeat**, **Fit**, and **Clip**, but not **RepeatX** or **RepeatY**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15096-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="15096-132">See Also</span></span>  
 <span data-ttu-id="15096-133">[Изображения (построитель отчетов и службы SSRS)](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="15096-133">[Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="15096-134">Диалоговое окно "Свойства изображения" — "Общие" (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="15096-134">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
