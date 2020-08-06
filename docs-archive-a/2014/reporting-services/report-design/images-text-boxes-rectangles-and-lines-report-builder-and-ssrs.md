---
title: Изображения, текстовые поля, прямоугольники и линии (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: aa7ad08f-dd49-401e-9619-522e27055bb9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2fb9a47bb3b8d68d48be42f8f0a2adddfc3ba130
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730181"
---
# <a name="images-text-boxes-rectangles-and-lines-report-builder-and-ssrs"></a><span data-ttu-id="f5f73-102">Изображения, текстовые поля, прямоугольники и линии (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="f5f73-102">Images, Text Boxes, Rectangles, and Lines (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f5f73-103">Помимо областей данных, таких как таблицы, матрицы и диаграммы, в отчетах используются другие элементы (например, изображения, текстовые поля и прямоугольники), добавляющие визуальные эффекты, выделяющие ключевые сведения и предоставляющие связанные данные.</span><span class="sxs-lookup"><span data-stu-id="f5f73-103">In addition to data regions like tables, matrices, and charts, reports use other report items like images, text boxes, and rectangles to add visual interest, highlight key information, or provide related information.</span></span> <span data-ttu-id="f5f73-104">Форматирование элемента отчета можно изменить.</span><span class="sxs-lookup"><span data-stu-id="f5f73-104">You can change the formatting of a report item.</span></span> <span data-ttu-id="f5f73-105">Например, можно добавить границу или заполнение, изменить первоначальную видимость или направление, а также указать точный размер и местоположение элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="f5f73-105">For example, you can add a border or padding, change the initial visibility or direction, or specify an exact size and location for the item.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a><span data-ttu-id="f5f73-106">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="f5f73-106">In This Section</span></span>  
 [<span data-ttu-id="f5f73-107">Текстовые поля (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="f5f73-107">Text Boxes &#40;Report Builder and SSRS&#41;</span></span>](text-boxes-report-builder-and-ssrs.md)  
 <span data-ttu-id="f5f73-108">Текстовое поле можно поместить в любое место в отчете. Оно может содержать метки, поля или вычисляемые данные.</span><span class="sxs-lookup"><span data-stu-id="f5f73-108">Text boxes can be placed anywhere on a report and can contain labels, fields, or calculated data.</span></span> <span data-ttu-id="f5f73-109">Чтобы определить значение, которое должно отображаться в текстовом поле при просмотре отчета, используются выражения.</span><span class="sxs-lookup"><span data-stu-id="f5f73-109">You use expressions to define the value to display in a text box when you view a report.</span></span>  
  
 <span data-ttu-id="f5f73-110">Каждая ячейка в таблице или матрице также представляет собой текстовое поле, которое можно форматировать аналогично изолированным текстовым полям в отчете.</span><span class="sxs-lookup"><span data-stu-id="f5f73-110">Every cell in a table or matrix is also a text box, which you can format in the same way that you format stand-alone text boxes.</span></span>  
  
 [<span data-ttu-id="f5f73-111">Прямоугольники и линии (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="f5f73-111">Rectangles and Lines &#40;Report Builder and SSRS&#41;</span></span>](rectangles-and-lines-report-builder-and-ssrs.md)  
 <span data-ttu-id="f5f73-112">**Линии** отображаются вертикально, горизонтально или по диагонали.</span><span class="sxs-lookup"><span data-stu-id="f5f73-112">**Lines** display horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="f5f73-113">Линия определяется начальной и конечной точками и может быть выполнена в различных стилях (например, иметь разные толщину и цвет).</span><span class="sxs-lookup"><span data-stu-id="f5f73-113">A line is defined with a start and end point and can have various styles (for example, weight and color) assigned to it.</span></span> <span data-ttu-id="f5f73-114">С линиями не связаны никакие данные.</span><span class="sxs-lookup"><span data-stu-id="f5f73-114">A line has no data associated with it.</span></span>  
  
 <span data-ttu-id="f5f73-115">**Прямоугольники** можно использовать как графические элементы или как контейнеры для других элементов отчета.</span><span class="sxs-lookup"><span data-stu-id="f5f73-115">**Rectangles** can be used as a graphical element, or as a container for other report items.</span></span> <span data-ttu-id="f5f73-116">Как графический элемент прямоугольник имеет такие же свойства, как и линия.</span><span class="sxs-lookup"><span data-stu-id="f5f73-116">As a graphical element, a rectangle has the same properties as a line.</span></span> <span data-ttu-id="f5f73-117">Прямоугольник-контейнер выступает в роли родительского контейнера для всех элементов отчета, находящихся внутри него.</span><span class="sxs-lookup"><span data-stu-id="f5f73-117">As a container, a rectangle acts as a parent container for all report items inside it.</span></span> <span data-ttu-id="f5f73-118">Элементы отчета располагают в родительском контейнере, чтобы было легче управлять их появлением на страницах отчета.</span><span class="sxs-lookup"><span data-stu-id="f5f73-118">Placing report items in a parent container helps control how they appear on each report page.</span></span>  
  
 [<span data-ttu-id="f5f73-119">Изображения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="f5f73-119">Images &#40;Report Builder and SSRS&#41;</span></span>](images-report-builder-and-ssrs.md)  
 <span data-ttu-id="f5f73-120">В изображениях выводятся двоичные графические данные отчета.</span><span class="sxs-lookup"><span data-stu-id="f5f73-120">Images display binary image data in a report.</span></span> <span data-ttu-id="f5f73-121">Для изображения необходимо указать источник.</span><span class="sxs-lookup"><span data-stu-id="f5f73-121">You provide the source for the image.</span></span> <span data-ttu-id="f5f73-122">Источником может служить ссылка на URL-адрес изображения, хранящегося на веб-сервере, ссылка на внедренные данные изображения или ссылка на двоичные данные изображения в базе данных.</span><span class="sxs-lookup"><span data-stu-id="f5f73-122">The source can be a URL reference to an image stored on a Web server, a reference to embedded image data, or a reference to binary image data in a database.</span></span> <span data-ttu-id="f5f73-123">Построитель отчетов и конструктор отчетов поддерживают файлы в форматах BMP, JPEG, GIF и PNG.</span><span class="sxs-lookup"><span data-stu-id="f5f73-123">Report Builder and Report Designer support .bmp, .jpeg, .gif, and .png files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5f73-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="f5f73-124">See Also</span></span>  
 [<span data-ttu-id="f5f73-125">Форматирование элементов отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="f5f73-125">Formatting Report Items &#40;Report Builder and SSRS&#41;</span></span>](formatting-report-items-report-builder-and-ssrs.md)  
  
  
