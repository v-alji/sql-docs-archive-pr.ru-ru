---
title: Изображения (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fcc2db5c-5c26-4607-ae2b-f65c80360536
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4f0840a10cc1082ba8dc7912862f7cf34c64972d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730185"
---
# <a name="images-report-builder-and-ssrs"></a><span data-ttu-id="9362c-102">Изображения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="9362c-102">Images (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9362c-103">Изображение — это элемент отчета, содержащий ссылку на изображение, которое внедрено в отчет или хранится в базе данных, на сервере отчетов или где-либо еще в Интернете.</span><span class="sxs-lookup"><span data-stu-id="9362c-103">An image is a report item that contains a reference to an image that is embedded in the report, stored in a database, stored on the report server, or stored elsewhere on the Web.</span></span> <span data-ttu-id="9362c-104">Изображение может быть рисунком, повторяющимся в строках данных.</span><span class="sxs-lookup"><span data-stu-id="9362c-104">An image can be a picture that is repeated with rows of data.</span></span> <span data-ttu-id="9362c-105">Изображение можно также использовать в качестве фона некоторых элементов отчета.</span><span class="sxs-lookup"><span data-stu-id="9362c-105">You can also use an image as a background for certain report items.</span></span>  
  
 <span data-ttu-id="9362c-106">Хранить эмблемы на сервере удобно, поскольку один и тот же логотип может использоваться во многих отчетах.</span><span class="sxs-lookup"><span data-stu-id="9362c-106">Storing logos on a server is a good idea because you can use the same logo in many reports.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="comparing-external-embedded-and-data-bound-images"></a><a name="ComparingImages"></a> <span data-ttu-id="9362c-107">Сравнение внешних, внедренных и привязанных к данным изображений</span><span class="sxs-lookup"><span data-stu-id="9362c-107">Comparing External, Embedded, and Data-Bound Images</span></span>  
 <span data-ttu-id="9362c-108">При использовании в отчете связанного с сервером или другого внешнего изображения элемент изображения содержит путь, указывающий на изображение на сервере отчетов или где-либо в Интернете.</span><span class="sxs-lookup"><span data-stu-id="9362c-108">When you use a server-based or other external image in a report, the image item contains a path that points to an image on the report server or wherever it exists on the Web.</span></span> <span data-ttu-id="9362c-109">При использовании внедренных изображений необходимо учесть, что данные изображений хранятся в определении отчета и не существуют как отдельные файлы.</span><span class="sxs-lookup"><span data-stu-id="9362c-109">When you use an embedded image, however, the image data is stored within the report definition and does not exist as a separate file.</span></span>  
  
 <span data-ttu-id="9362c-110">Изображения, связанные с сервером, хорошо подходят для логотипов и статических рисунков, которые используются несколькими отчетами или веб-страницами.</span><span class="sxs-lookup"><span data-stu-id="9362c-110">Server-based images work well for logos and static pictures that are shared among several reports or Web pages.</span></span> <span data-ttu-id="9362c-111">Внедренные изображения всегда доступны для отчета, но они не могут быть общими.</span><span class="sxs-lookup"><span data-stu-id="9362c-111">Embedded images ensure that the images are always available to the report, but they cannot be shared.</span></span> <span data-ttu-id="9362c-112">Определения отчетов с внешними изображениями меньше определений с внедренными изображениями.</span><span class="sxs-lookup"><span data-stu-id="9362c-112">Report definitions with external images are smaller than definitions with embedded images.</span></span>  
  
 <span data-ttu-id="9362c-113">Изображения, связанные с данными, также могут быть взяты из двоичных данных, хранимых в БД.</span><span class="sxs-lookup"><span data-stu-id="9362c-113">Data-bound images can also be displayed from binary data stored in a database.</span></span> <span data-ttu-id="9362c-114">Например, рисунки, появляющиеся рядом с названиями продуктов в списке продуктов, являются изображениями базы данных.</span><span class="sxs-lookup"><span data-stu-id="9362c-114">For example, the pictures that appear alongside product names in a product list are database images.</span></span> <span data-ttu-id="9362c-115">На следующем рисунке изображения велосипедов хранятся в базе данных и подготавливаются в отчете, чтобы каждый продукт был иллюстрирован.</span><span class="sxs-lookup"><span data-stu-id="9362c-115">In the following picture, the images of bicycles are stored in a database and retrieved in the report to illustrate each product.</span></span>  
  
 <span data-ttu-id="9362c-116">![rs_DataboundBikes](../media/rs-databoundbikes.gif "rs_DataboundBikes")</span><span class="sxs-lookup"><span data-stu-id="9362c-116">![rs_DataboundBikes](../media/rs-databoundbikes.gif "rs_DataboundBikes")</span></span>  
  

  
##  <a name="images-as-report-parts"></a><a name="ImagesReportParts"></a> <span data-ttu-id="9362c-117">Изображения как элементы отчетов</span><span class="sxs-lookup"><span data-stu-id="9362c-117">Images as Report Parts</span></span>  
 <span data-ttu-id="9362c-118">Изображения можно сохранять отдельно от отчета как элементы отчета.</span><span class="sxs-lookup"><span data-stu-id="9362c-118">You can save images separately from a report as report parts.</span></span> [!INCLUDE[ssRBrptparts](../../includes/ssrbrptparts-md.md)]  
  
 
  
##  <a name="embedding-images"></a><a name="EmbedImages"></a> <span data-ttu-id="9362c-119">Внедренные изображения</span><span class="sxs-lookup"><span data-stu-id="9362c-119">Embedding Images</span></span>  
 <span data-ttu-id="9362c-120">Изображения можно внедрять в отчет, таким образом сохраняя их в определении отчета.</span><span class="sxs-lookup"><span data-stu-id="9362c-120">You can embed images in a report so that all image data is stored within the report definition.</span></span> <span data-ttu-id="9362c-121">При внедрении изображения оно кодируется в кодировке MIME и сохраняется в определении отчета в виде текста.</span><span class="sxs-lookup"><span data-stu-id="9362c-121">When you embed an image, the image is MIME-encoded and stored as text in the report definition.</span></span> <span data-ttu-id="9362c-122">Использование внедренного изображения обеспечивает отчету полный доступ к изображению, но также увеличивает размер определения отчета.</span><span class="sxs-lookup"><span data-stu-id="9362c-122">Using an embedded image ensures that the image is always available to the report, but it also increases the size of the report definition.</span></span>  
  
 <span data-ttu-id="9362c-123">Дополнительные сведения о внедрении изображений см. в разделе [Внедрение изображения в отчет (построитель отчетов и службы SSRS)](embed-an-image-in-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9362c-123">For more information about embedding an image, see [Embed an Image in a Report &#40;Report Builder and SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="external-images"></a><a name="ExternalImages"></a> <span data-ttu-id="9362c-124">Внешние изображения</span><span class="sxs-lookup"><span data-stu-id="9362c-124">External Images</span></span>  
 <span data-ttu-id="9362c-125">Можно включить изображение в отчет, указав его URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="9362c-125">You can include stored images in a report by specifying a URL to the image.</span></span> <span data-ttu-id="9362c-126">При использовании в отчете внешнего изображения его источник устанавливается как `External`, а значением является путь к изображению или его URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="9362c-126">When you use an external image in a report, the image source is set to `External` and the value for the image is the URL address or path to the image.</span></span>  
  
 <span data-ttu-id="9362c-127">Дополнительные сведения см. в разделе [Указание путей к внешним элементам (построитель отчетов и службы SSRS)](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9362c-127">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="9362c-128">Для воспроизведения изображения при запуске отчета в построителе отчетов или конструкторе отчетов используются учетные данные пользователя.</span><span class="sxs-lookup"><span data-stu-id="9362c-128">When the report is run in Report Builder or Report Designer, preview uses the credentials of the user to display the image.</span></span> <span data-ttu-id="9362c-129">При запуске отчета на сервере отчетов расположенное в нем изображение может не отображаться, если учетных данных сервера недостаточно для доступа к изображению.</span><span class="sxs-lookup"><span data-stu-id="9362c-129">When the report is run on the report server, the image in the report may not be displayed if the server credentials are not sufficient to access the image.</span></span> <span data-ttu-id="9362c-130">В этом случае обратитесь к системному администратору.</span><span class="sxs-lookup"><span data-stu-id="9362c-130">In that case, contact your system administrator.</span></span>  
  
 <span data-ttu-id="9362c-131">Дополнительные сведения о добавлении внешнего изображения в отчет см. в разделе [Добавление внешнего изображения (построитель отчетов и службы SSRS)](add-an-external-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9362c-131">For more information about adding an external image to a report, see [Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md).</span></span>  
  
 
  
##  <a name="background-images"></a><a name="BackgroundImages"></a> <span data-ttu-id="9362c-132">Фоновые изображения</span><span class="sxs-lookup"><span data-stu-id="9362c-132">Background Images</span></span>  
 <span data-ttu-id="9362c-133">Изображение можно использовать в качестве фона в тексте отчета или прямоугольнике, текстовом поле, списке, матрице или таблице.</span><span class="sxs-lookup"><span data-stu-id="9362c-133">You can use an image as a background image in the body of the report or in a rectangle, text box, list, matrix, or table.</span></span> <span data-ttu-id="9362c-134">Фоновое и обычное изображения имеют похожие свойства.</span><span class="sxs-lookup"><span data-stu-id="9362c-134">A background image and an image have similar properties.</span></span> <span data-ttu-id="9362c-135">Также можно указать шаблон заполнения, по которому изображение сформирует фон для элемента.</span><span class="sxs-lookup"><span data-stu-id="9362c-135">You can also specify how the image is repeated to fill the background of the item.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9362c-136">Некоторые модули подготовки отчетов, например HTML, подготавливают фоновое изображение к просмотру для тела отчета в теле, верхнем и нижнем колонтитулах страницы.</span><span class="sxs-lookup"><span data-stu-id="9362c-136">Some rendering extensions, like the HTML rendering extension, render the background image for the report body in the body, the page header, and the page footer.</span></span> <span data-ttu-id="9362c-137">Для верхнего и нижнего колонтитула страницы можно указать отдельное фоновое изображение; но если изображение не выбрано, отчет использует изображение тела.</span><span class="sxs-lookup"><span data-stu-id="9362c-137">You can define a separate background image for the page header and footer, but if no image is defined, the report uses the background image of the body.</span></span> <span data-ttu-id="9362c-138">Другие модули подготовки отчетов, такие как модуль подготовки изображений, не поддерживают фоновые изображения в верхнем и нижнем колонтитуле.</span><span class="sxs-lookup"><span data-stu-id="9362c-138">Other rendering extensions, like the Image rendering extension, do not render the body background image in the page header and footer.</span></span>  
  
 <span data-ttu-id="9362c-139">Дополнительные сведения о добавлении фонового изображения см. в разделе [Добавление фонового изображения (построитель отчетов и службы SSRS)](add-a-background-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9362c-139">For more information about adding a background image, see [Add a Background Image &#40;Report Builder and SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span></span>  
  
 
  
##  <a name="data-bound-images"></a><a name="DataboundImages"></a> <span data-ttu-id="9362c-140">Изображения, привязанные к данным</span><span class="sxs-lookup"><span data-stu-id="9362c-140">Data-bound Images</span></span>  
 <span data-ttu-id="9362c-141">В отчет можно добавить изображения, хранимые в базе данных.</span><span class="sxs-lookup"><span data-stu-id="9362c-141">You can add images that are stored in a database to your report.</span></span> <span data-ttu-id="9362c-142">Управление изображениями отчета не отличается от управления статическими изображениями, только имеет дополнительный набор свойств, указывающий, что изображение хранится в базе данных.</span><span class="sxs-lookup"><span data-stu-id="9362c-142">You use the same image report item as the one used for static images, but with a set of properties that indicate that the image is stored in a database.</span></span> <span data-ttu-id="9362c-143">Инструкции по работе с изображениями, привязанными к данным, см. в разделе [Добавление привязанного к данным изображения (построитель отчетов и службы SSRS)](add-a-data-bound-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9362c-143">To view instructions about working with data-bound images, see [Add a Data-Bound Image &#40;Report Builder and SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md).</span></span>  
  

  
##  <a name="how-to-topics"></a><a name="HowTo"></a> <span data-ttu-id="9362c-144">Инструкции</span><span class="sxs-lookup"><span data-stu-id="9362c-144">How-to Topics</span></span>  
 [<span data-ttu-id="9362c-145">Добавление внешнего изображения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="9362c-145">Add an External Image &#40;Report Builder and SSRS&#41;</span></span>](add-an-external-image-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="9362c-146">Внедрение изображения в отчет (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="9362c-146">Embed an Image in a Report &#40;Report Builder and SSRS&#41;</span></span>](embed-an-image-in-a-report-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="9362c-147">Добавление фонового изображения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="9362c-147">Add a Background Image &#40;Report Builder and SSRS&#41;</span></span>](add-a-background-image-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="9362c-148">Добавление привязанного к данным изображения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="9362c-148">Add a Data-Bound Image &#40;Report Builder and SSRS&#41;</span></span>](add-a-data-bound-image-report-builder-and-ssrs.md)  
  
  
  
## <a name="see-also"></a><span data-ttu-id="9362c-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="9362c-149">See Also</span></span>  
 <span data-ttu-id="9362c-150">[Экспорт в файл изображения (построитель отчетов и службы SSRS)](../report-builder/exporting-to-an-image-file-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9362c-150">[Exporting to an Image File &#40;Report Builder and SSRS&#41;](../report-builder/exporting-to-an-image-file-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9362c-151">Поведение при подготовке к просмотру (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="9362c-151">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](rendering-behaviors-report-builder-and-ssrs.md)  
  
  
