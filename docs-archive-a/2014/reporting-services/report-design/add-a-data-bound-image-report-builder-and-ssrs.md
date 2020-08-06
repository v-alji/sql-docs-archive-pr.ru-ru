---
title: Добавление привязанного к данным изображения (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: df4c38d4-bfcc-41c4-aa6d-952ca6fd7a2e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ea85bdcd6eab04ff51c879a9e790b6e12f73a771
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654816"
---
# <a name="add-a-data-bound-image-report-builder-and-ssrs"></a><span data-ttu-id="a7eb9-102">Добавление привязанного к данным изображения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="a7eb9-102">Add a Data-Bound Image (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a7eb9-103">Отчет может включать ссылку на изображение, хранящееся в базе данных.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-103">A report can include a reference to an image that is stored in a database.</span></span> <span data-ttu-id="a7eb9-104">Такое изображение называется *изображением, привязанным к данным*.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-104">Such an image is known as a *data-bound image*.</span></span> <span data-ttu-id="a7eb9-105">Примерами изображений, привязанных к данным, служат картинки, выводящиеся вместе с наименованиями товаров в списке товаров.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-105">The pictures that appear alongside product names in a product list are examples of data-bound images.</span></span>  
  
 <span data-ttu-id="a7eb9-106">Чтобы добавить привязанное к данным изображение к верхнему или нижнему колонтитулу страницы, необходимы дополнительные шаги.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-106">Adding a data-bound image to a page header or page footer requires additional steps.</span></span> <span data-ttu-id="a7eb9-107">Дополнительные сведения см. в разделе [Верхние и нижние колонтитулы страницы (построитель отчетов и службы SSRS)](page-headers-and-footers-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a7eb9-107">For more information, see [Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-data-bound-image"></a><span data-ttu-id="a7eb9-108">Добавление привязанного к данным изображения</span><span class="sxs-lookup"><span data-stu-id="a7eb9-108">To add a data-bound image</span></span>  
  
1.  <span data-ttu-id="a7eb9-109">В режиме конструктора отчетов создайте таблицу с соединением с источником данных и набор данных с полем, содержащим двоичные данные изображения.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-109">In report design view, create a table with a data source connection and a dataset with a field that contains binary image data.</span></span> <span data-ttu-id="a7eb9-110">Дополнительные сведения см. в разделе [Таблицы (построитель отчетов и службы SSRS)](tables-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a7eb9-110">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="a7eb9-111">Вставьте столбец в таблицу.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-111">Insert a column in your table.</span></span> <span data-ttu-id="a7eb9-112">Дополнительные сведения см. в разделе [Вставка или удаление столбца (построитель отчетов и службы SSRS)](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a7eb9-112">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="a7eb9-113">В меню **Вставка** выберите **Изображение**, а затем щелкните строку данных нового столбца.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-113">On the **Insert** menu, click **Image**, and then click in the data row of the new column.</span></span>  
  
4.  <span data-ttu-id="a7eb9-114">На странице «Общие» диалогового окна **Свойства изображения** введите имя в текстовое поле **Имя** или примите имя по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-114">On the General page of the **Image Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span>  
  
5.  <span data-ttu-id="a7eb9-115">В текстовом поле **Подсказка** введите текст, отображаемый при наведении курсора мыши на изображение в отчете, подготовленном к просмотру в формате HTML (необязательно).</span><span class="sxs-lookup"><span data-stu-id="a7eb9-115">(Optional) In the **Tooltip** text box, type text to display when the user hovers over the image in the report rendered for HTML.</span></span>  
  
6.  <span data-ttu-id="a7eb9-116">В списке **Выберите источник изображения**выберите пункт **База данных**.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-116">In **Select the image source**, select **Database**.</span></span>  
  
7.  <span data-ttu-id="a7eb9-117">В списке **Использовать это поле**выберите поле, содержащее изображения в отчете.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-117">In **Use this Field**, select the field that contains images in your report.</span></span>  
  
8.  <span data-ttu-id="a7eb9-118">В списке **Использовать этот тип MIME** выберите тип MIME или формат файла, соответствующий изображению, например BMP.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-118">In **Use this MIME type**, select the MIME type, or file format, of the image-for example, bmp.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="a7eb9-119">В области конструктора отчета появится заполнитель изображения.</span><span class="sxs-lookup"><span data-stu-id="a7eb9-119">An image placeholder appears on the report design surface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7eb9-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7eb9-120">See Also</span></span>  
 <span data-ttu-id="a7eb9-121">[Изображения (построитель отчетов и службы SSRS)](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a7eb9-121">[Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a7eb9-122">[Внедрение изображения в отчет (построитель отчетов и службы SSRS)](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a7eb9-122">[Embed an Image in a Report &#40;Report Builder and SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a7eb9-123">[Добавление внешнего изображения (построитель отчетов и службы SSRS)](add-an-external-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a7eb9-123">[Add an External Image &#40;Report Builder and SSRS&#41;](add-an-external-image-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a7eb9-124">Диалоговое окно "Свойства изображения" — "Общие" (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="a7eb9-124">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
