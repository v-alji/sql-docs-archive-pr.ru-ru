---
title: Диалоговое окно «Заливка» (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.reportbody.fill.f1
- "10065"
- "10501"
- sql12.rtp.rptdesigner.shared.filldv.f1
- sql12.rtp.rptdesigner.rectangleproperties.fill.f1
- "10064"
- sql12.rtp.rptdesigner.textboxproperties.fill.f1
- "10124"
ms.assetid: 93a91d02-d558-4a0e-8d17-3fdf21e208d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ae7f2b05d4d108c77f1dcae9ce7fefe5073e2522
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664726"
---
# <a name="fill-dialog-box-report-builder-and-ssrs"></a><span data-ttu-id="187e3-102">Диалоговое окно «Заливка» (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="187e3-102">Fill Dialog Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="187e3-103">На вкладке **Заливка** можно указать параметры цвета фона для одной или нескольких ячеек в области данных или текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="187e3-103">On the **Fill** tab, you can specify color options for the background of a single cell or multiple cells within a data region or a text box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="187e3-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="187e3-104">Options</span></span>  
 <span data-ttu-id="187e3-105">**Цвет заливки**</span><span class="sxs-lookup"><span data-stu-id="187e3-105">**Fill Color**</span></span>  
 <span data-ttu-id="187e3-106">Чтобы выбрать цвет заливки прямоугольника, нажмите кнопку выбора цвета.</span><span class="sxs-lookup"><span data-stu-id="187e3-106">Click the color button to select a fill color for the rectangle.</span></span> <span data-ttu-id="187e3-107">Нажмите кнопку **Выражение**_(fx)_ , чтобы изменить выражение. Оно может представлять собой шестнадцатеричное значение цвета в формате RGB или одно из названий стандартных цветов, список которых содержится в диалоговом окне **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="187e3-107">Click the **Expression**_(fx)_ button to edit the expression, which can be a hexadecimal value for the RGB color or one of the predefined color names that are provided in the **Expression** dialog box.</span></span> <span data-ttu-id="187e3-108">Чтобы увидеть список стандартных цветов, выберите **Веб** в панели **Элемент**.</span><span class="sxs-lookup"><span data-stu-id="187e3-108">To see a list of predefined colors, in the **Item** pane, select **Web**.</span></span> <span data-ttu-id="187e3-109">Названия цветов, перечисленные в панели **Заголовок** , можно ввести в панель для текста выражения.</span><span class="sxs-lookup"><span data-stu-id="187e3-109">The color names listed in the **Title** pane can be typed into the expression text pane.</span></span> <span data-ttu-id="187e3-110">При вводе названия цвета не пользуйтесь ни символом равенства (=), ни кавычками ("").</span><span class="sxs-lookup"><span data-stu-id="187e3-110">Do not use an equal sign (=) or quotation marks ("") when typing the color name.</span></span>  
  
 <span data-ttu-id="187e3-111">**Выберите источник изображения**</span><span class="sxs-lookup"><span data-stu-id="187e3-111">**Select the image source**</span></span>  
 <span data-ttu-id="187e3-112">Укажите место хранения изображения, чтобы обработчик отчетов смог его отобразить при подготовке отчета к просмотру.</span><span class="sxs-lookup"><span data-stu-id="187e3-112">Indicate where the image is stored so that when the report is rendered, the report processor can display it.</span></span>  
  
-   <span data-ttu-id="187e3-113">**Внешнее** Выберите этот параметр, если изображение должно храниться в виде файла на сервере отчетов или на веб-сервере.</span><span class="sxs-lookup"><span data-stu-id="187e3-113">**External** Choose this option when you want the image to continue to exist as a file on a report server or Web server.</span></span>  
  
-   <span data-ttu-id="187e3-114">**Внедренное** Выберите этот параметр, если изображение должно быть встроено в отчет.</span><span class="sxs-lookup"><span data-stu-id="187e3-114">**Embedded** Choose this option when you want to embed the image into the report.</span></span>  
  
-   <span data-ttu-id="187e3-115">**База данных** Выберите этот параметр, чтобы указать имя поля базы данных, представляющего изображение, которое должно быть включено в отчет.</span><span class="sxs-lookup"><span data-stu-id="187e3-115">**Database** Choose this option when you want to include a database field name that represents the images that you want to include in your report.</span></span>  
  
 <span data-ttu-id="187e3-116">**Использовать это изображение**</span><span class="sxs-lookup"><span data-stu-id="187e3-116">**Use this image**</span></span>  
 <span data-ttu-id="187e3-117">Этот параметр доступен в том случае, если выбран параметр **Внедренное** или **Внешнее** .</span><span class="sxs-lookup"><span data-stu-id="187e3-117">This option appears when you select the **Embedded** or **External** option.</span></span>  
  
 <span data-ttu-id="187e3-118">При внедрении изображения выберите из раскрывающегося списка изображение, добавляемое в отчет.</span><span class="sxs-lookup"><span data-stu-id="187e3-118">If you are embedding the image, choose the picture that you want to add to the report from the drop-down list.</span></span> <span data-ttu-id="187e3-119">Чтобы добавить изображение в раскрывающийся список, нажмите кнопку **Импорт** .</span><span class="sxs-lookup"><span data-stu-id="187e3-119">Click **Import** to add the image to the drop-down list.</span></span> <span data-ttu-id="187e3-120">После добавления изображения в панель **Данные** его можно выбрать из раскрывающегося списка после выбора параметра **Внедренное** .</span><span class="sxs-lookup"><span data-stu-id="187e3-120">If you added an image to the **Data** pane, you can select that image by choosing **Embedded** and then selecting the image from the drop-down list.</span></span>  
  
 <span data-ttu-id="187e3-121">Если выбран параметр **Внешний** , введите URL-адрес изображения.</span><span class="sxs-lookup"><span data-stu-id="187e3-121">If you select the **External** option, type the URL of the image.</span></span> <span data-ttu-id="187e3-122">Для отчета, опубликованного на сервере отчетов, настроенном для работы в собственном режиме, используйте полный или относительный путь (например, http:// *\<servername>* /images/image1.jpg).</span><span class="sxs-lookup"><span data-stu-id="187e3-122">For a report published to a report server configured for native mode, use a full or relative path (for example, http://*\<servername>*/images/image1.jpg).</span></span> <span data-ttu-id="187e3-123">Для отчета, опубликованного на сервере отчетов, настроенном в режиме интеграции с SharePoint, используйте полный URL-адрес (например, http:// *\<SharePointservername>/\<site>* /документс/имажес/image1.jpg).</span><span class="sxs-lookup"><span data-stu-id="187e3-123">For a report published to a report server configured in SharePoint integrated mode, use a fully qualified URL (for example, http://*\<SharePointservername>/\<site>*/Documents/images/image1.jpg).</span></span>  
  
 <span data-ttu-id="187e3-124">**Импорт**</span><span class="sxs-lookup"><span data-stu-id="187e3-124">**Import**</span></span>  
 <span data-ttu-id="187e3-125">Доступен при выборе параметра **Внедренное**.</span><span class="sxs-lookup"><span data-stu-id="187e3-125">Available when you select **Embedded**.</span></span> <span data-ttu-id="187e3-126">Нажмите, чтобы добавить изображение в раскрывающийся список **Использовать это изображение** .</span><span class="sxs-lookup"><span data-stu-id="187e3-126">Click to add an image to the **Use this image** drop-down list.</span></span>  
  
 <span data-ttu-id="187e3-127">**Использовать это поле**</span><span class="sxs-lookup"><span data-stu-id="187e3-127">**Use this field**</span></span>  
 <span data-ttu-id="187e3-128">Доступен при выборе параметра **База данных**.</span><span class="sxs-lookup"><span data-stu-id="187e3-128">Available when you select **Database**.</span></span> <span data-ttu-id="187e3-129">Выберите имя поля.</span><span class="sxs-lookup"><span data-stu-id="187e3-129">Select the field name.</span></span>  
  
 <span data-ttu-id="187e3-130">**Использовать этот тип MIME**</span><span class="sxs-lookup"><span data-stu-id="187e3-130">**Use this MIME type**</span></span>  
 <span data-ttu-id="187e3-131">Выберите формат изображения в базе данных (например, BMP, JPEG, GIF, PNG или X-PNG).</span><span class="sxs-lookup"><span data-stu-id="187e3-131">Choose the appropriate format of the pictures contained in the database (for example, .bmp, .jpeg, .gif, .png, or .x-png).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="187e3-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="187e3-132">See Also</span></span>  
 <span data-ttu-id="187e3-133">[Форматирование элементов отчета &#40;построитель отчетов и SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="187e3-133">[Formatting Report Items &#40;Report Builder and SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="187e3-134">[Форматирование текста и заполнителей &#40;построитель отчетов и SSRS&#41;](report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="187e3-134">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="187e3-135">Изображения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="187e3-135">Images &#40;Report Builder and SSRS&#41;</span></span>](report-design/images-report-builder-and-ssrs.md)  
  
  
