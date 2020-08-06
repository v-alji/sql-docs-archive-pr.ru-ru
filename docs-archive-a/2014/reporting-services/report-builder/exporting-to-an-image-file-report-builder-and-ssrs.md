---
title: Экспорт в файл изображения (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 020d8ea2-de07-4212-a2bb-2ed0df2c8db8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dc1c8539b39a99c252ebfcb0275b674f657de6c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664007"
---
# <a name="exporting-to-an-image-file-report-builder-and-ssrs"></a><span data-ttu-id="8aacd-102">Экспорт в файл изображения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="8aacd-102">Exporting to an Image File (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8aacd-103">Модуль подготовки отчетов изображений преобразует отчет в битовую карту или метафайл.</span><span class="sxs-lookup"><span data-stu-id="8aacd-103">The Image rendering extension renders a report to a bitmap or metafile.</span></span> <span data-ttu-id="8aacd-104">По умолчанию модуль подготовки изображения создает отчет в файле TIFF, который можно просматривать на нескольких страницах.</span><span class="sxs-lookup"><span data-stu-id="8aacd-104">By default, the Image rendering extension produces a TIFF file of the report, which can be viewed in multiple pages.</span></span> <span data-ttu-id="8aacd-105">Полученное изображение клиент может просмотреть в программе просмотра изображений и распечатать.</span><span class="sxs-lookup"><span data-stu-id="8aacd-105">When the client receives the image, it can be displayed in an image viewer and printed.</span></span> <span data-ttu-id="8aacd-106">В этом разделе содержатся сведения о модуле подготовки изображений и описаны исключения из правил подготовки к просмотру.</span><span class="sxs-lookup"><span data-stu-id="8aacd-106">This topic provides Image renderer-specific information and describes exceptions to the rendering rules.</span></span>  
  
 <span data-ttu-id="8aacd-107">Модуль подготовки изображений способен создавать файлы в любых форматах, поддерживаемых [!INCLUDE[ndptecgdiplus](../../includes/ndptecgdiplus-md.md)]: BMP, EMF, EMFPlus, GIF, JPEG, PNG и TIFF.</span><span class="sxs-lookup"><span data-stu-id="8aacd-107">The Image rendering extension can generate files in any of the formats supported by [!INCLUDE[ndptecgdiplus](../../includes/ndptecgdiplus-md.md)]: BMP, EMF, EMFPlus, GIF, JPEG, PNG, and TIFF.</span></span> <span data-ttu-id="8aacd-108">Если используется формат TIFF, то файлу для главного потока будет присвоено имя *имя_отчета*.tif.</span><span class="sxs-lookup"><span data-stu-id="8aacd-108">For TIFF format, the file name of the primary stream is *ReportName*.tif.</span></span> <span data-ttu-id="8aacd-109">Для других форматов, которые формируются по принципу "одна страница в одном файле", файлу будет присвоено имя *имя_отчета_страница.ext* , где</span><span class="sxs-lookup"><span data-stu-id="8aacd-109">For all other formats, which render as a single page per file, the file name is *ReportName_Page.ext* where.</span></span> <span data-ttu-id="8aacd-110">*ext* — расширение файла в зависимости от выбранного формата.</span><span class="sxs-lookup"><span data-stu-id="8aacd-110">*ext* is the file extension for the chosen format.</span></span> <span data-ttu-id="8aacd-111">Чтобы создать файл в другом поддерживаемом формате изображений, укажите в параметре **OutputFormatDeviceInfo** любую из перечисленных выше строк.</span><span class="sxs-lookup"><span data-stu-id="8aacd-111">To produce a file in another Image-supported format, specify any of the above listed strings in the **OutputFormatDeviceInfo** setting.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="supported-image-formats"></a><a name="SupportedImageFormats"></a> <span data-ttu-id="8aacd-112">Поддерживаемые форматы изображения</span><span class="sxs-lookup"><span data-stu-id="8aacd-112">Supported Image Formats</span></span>  
 <span data-ttu-id="8aacd-113">В следующей таблице приведены расширения имени файла и тип MIME для каждого формата модуля подготовки изображений.</span><span class="sxs-lookup"><span data-stu-id="8aacd-113">The following table shows the file extension and MimeType for each Image renderer format.</span></span>  
  
|<span data-ttu-id="8aacd-114">**Тип**</span><span class="sxs-lookup"><span data-stu-id="8aacd-114">**Type**</span></span>|<span data-ttu-id="8aacd-115">**Расширение**</span><span class="sxs-lookup"><span data-stu-id="8aacd-115">**Extension**</span></span>|<span data-ttu-id="8aacd-116">**MIMEType**</span><span class="sxs-lookup"><span data-stu-id="8aacd-116">**MIMEType**</span></span>|  
|--------------|-------------------|------------------|  
|<span data-ttu-id="8aacd-117">BMP</span><span class="sxs-lookup"><span data-stu-id="8aacd-117">BMP</span></span>|<span data-ttu-id="8aacd-118">bmp</span><span class="sxs-lookup"><span data-stu-id="8aacd-118">bmp</span></span>|<span data-ttu-id="8aacd-119">image/bmp</span><span class="sxs-lookup"><span data-stu-id="8aacd-119">image/bmp</span></span>|  
|<span data-ttu-id="8aacd-120">GIF</span><span class="sxs-lookup"><span data-stu-id="8aacd-120">GIF</span></span>|<span data-ttu-id="8aacd-121">GIF</span><span class="sxs-lookup"><span data-stu-id="8aacd-121">gif</span></span>|<span data-ttu-id="8aacd-122">image/gif</span><span class="sxs-lookup"><span data-stu-id="8aacd-122">image/gif</span></span>|  
|<span data-ttu-id="8aacd-123">JPEG</span><span class="sxs-lookup"><span data-stu-id="8aacd-123">JPEG</span></span>|<span data-ttu-id="8aacd-124">jpeg</span><span class="sxs-lookup"><span data-stu-id="8aacd-124">jpeg</span></span>|<span data-ttu-id="8aacd-125">image/jpeg</span><span class="sxs-lookup"><span data-stu-id="8aacd-125">image/jpeg</span></span>|  
|<span data-ttu-id="8aacd-126">PNG</span><span class="sxs-lookup"><span data-stu-id="8aacd-126">PNG</span></span>|<span data-ttu-id="8aacd-127">png</span><span class="sxs-lookup"><span data-stu-id="8aacd-127">png</span></span>|<span data-ttu-id="8aacd-128">image/png</span><span class="sxs-lookup"><span data-stu-id="8aacd-128">image/png</span></span>|  
|<span data-ttu-id="8aacd-129">TIFF</span><span class="sxs-lookup"><span data-stu-id="8aacd-129">TIFF</span></span>|<span data-ttu-id="8aacd-130">tif</span><span class="sxs-lookup"><span data-stu-id="8aacd-130">tif</span></span>|<span data-ttu-id="8aacd-131">image/tiff</span><span class="sxs-lookup"><span data-stu-id="8aacd-131">image/tiff</span></span>|  
|<span data-ttu-id="8aacd-132">EMF</span><span class="sxs-lookup"><span data-stu-id="8aacd-132">EMF</span></span>|<span data-ttu-id="8aacd-133">EMF</span><span class="sxs-lookup"><span data-stu-id="8aacd-133">emf</span></span>|<span data-ttu-id="8aacd-134">image/emf</span><span class="sxs-lookup"><span data-stu-id="8aacd-134">image/emf</span></span>|  
|<span data-ttu-id="8aacd-135">EMFPlus</span><span class="sxs-lookup"><span data-stu-id="8aacd-135">EMFPlus</span></span>|<span data-ttu-id="8aacd-136">EMF</span><span class="sxs-lookup"><span data-stu-id="8aacd-136">emf</span></span>|<span data-ttu-id="8aacd-137">image/emf</span><span class="sxs-lookup"><span data-stu-id="8aacd-137">image/emf</span></span>|  
  
  
##  <a name="rendering-multiple-pages"></a><a name="RenderingMultiplePages"></a> <span data-ttu-id="8aacd-138">Подготовка к просмотру нескольких страниц</span><span class="sxs-lookup"><span data-stu-id="8aacd-138">Rendering Multiple Pages</span></span>  
 <span data-ttu-id="8aacd-139">TIFF — это единственный формат, который позволяет представлять многостраничные документы в едином файле.</span><span class="sxs-lookup"><span data-stu-id="8aacd-139">TIFF is the only format that supports multiple page documents in a single file.</span></span> <span data-ttu-id="8aacd-140">Другие форматы, такие как JPG или PNG, выводят по одной странице одновременно и требуют отдельного вызова модуля подготовки отчетов для подготовки к просмотру каждой страницы.</span><span class="sxs-lookup"><span data-stu-id="8aacd-140">Other formats, such as JPG or PNG, output one page at a time and require a separate call to the rendering extension for each page.</span></span>  
  
  
##  <a name="interactivity"></a><a name="Interactivity"></a><span data-ttu-id="8aacd-141">Интерактивности</span><span class="sxs-lookup"><span data-stu-id="8aacd-141">Interactivity</span></span>  
 <span data-ttu-id="8aacd-142">Интерактивные возможности не поддерживаются ни одним из форматов изображения, формируемых этим модулем подготовки отчетов.</span><span class="sxs-lookup"><span data-stu-id="8aacd-142">Interactivity is not supported in any Image formats generated by this renderer.</span></span> <span data-ttu-id="8aacd-143">Не обрабатываются следующие интерактивные элементы.</span><span class="sxs-lookup"><span data-stu-id="8aacd-143">The following interactive elements are not rendered:</span></span>  
  
-   <span data-ttu-id="8aacd-144">Гиперссылки</span><span class="sxs-lookup"><span data-stu-id="8aacd-144">Hyperlinks</span></span>  
  
-   <span data-ttu-id="8aacd-145">Показать или скрыть</span><span class="sxs-lookup"><span data-stu-id="8aacd-145">Show or Hide</span></span>  
  
-   <span data-ttu-id="8aacd-146">Схема документа</span><span class="sxs-lookup"><span data-stu-id="8aacd-146">Document Map</span></span>  
  
-   <span data-ttu-id="8aacd-147">Ссылки с детализацией или дополнительной информацией</span><span class="sxs-lookup"><span data-stu-id="8aacd-147">Drillthrough or clickthrough links</span></span>  
  
-   <span data-ttu-id="8aacd-148">Сортировка конечным пользователем</span><span class="sxs-lookup"><span data-stu-id="8aacd-148">End user sort</span></span>  
  
-   <span data-ttu-id="8aacd-149">Фиксированные заголовки</span><span class="sxs-lookup"><span data-stu-id="8aacd-149">Fixed headers</span></span>  
  
-   <span data-ttu-id="8aacd-150">Закладки</span><span class="sxs-lookup"><span data-stu-id="8aacd-150">Bookmarks</span></span>  
  
  
##  <a name="device-information-settings"></a><a name="DeviceInfo"></a><span data-ttu-id="8aacd-151">Настройки сведений об устройстве</span><span class="sxs-lookup"><span data-stu-id="8aacd-151">Device Information Settings</span></span>  
 <span data-ttu-id="8aacd-152">Некоторые параметры по умолчанию для этого модуля подготовки отчетов можно изменить через настройку сведений об устройстве.</span><span class="sxs-lookup"><span data-stu-id="8aacd-152">You can change some default settings for this renderer by changing the device information settings.</span></span> <span data-ttu-id="8aacd-153">Дополнительные сведения см. в разделе [Image Device Information Settings](../image-device-information-settings.md).</span><span class="sxs-lookup"><span data-stu-id="8aacd-153">For more information, see [Image Device Information Settings](../image-device-information-settings.md).</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="8aacd-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="8aacd-154">See Also</span></span>  
 <span data-ttu-id="8aacd-155">[Разбиение на страницы в Reporting Services &#40;построитель отчетов и SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8aacd-155">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8aacd-156">[Поведения подготовки к просмотру &#40;построитель отчетов и SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8aacd-156">[Rendering Behaviors &#40;Report Builder  and SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8aacd-157">[Интерактивные функции для различных модулей подготовки отчетов к просмотру &#40;построитель отчетов и SSRS&#41;](interactive-functionality-different-report-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="8aacd-157">[Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;](interactive-functionality-different-report-rendering-extensions.md) </span></span>  
 <span data-ttu-id="8aacd-158">[Подготовка элементов отчета к просмотру &#40;построитель отчетов и SSRS&#41;](../report-design/rendering-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8aacd-158">[Rendering Report Items &#40;Report Builder and SSRS&#41;](../report-design/rendering-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8aacd-159">Таблицы, матрицы и списки (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="8aacd-159">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md)  
  
  
