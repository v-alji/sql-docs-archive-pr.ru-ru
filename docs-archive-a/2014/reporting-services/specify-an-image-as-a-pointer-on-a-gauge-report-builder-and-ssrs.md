---
title: Указание изображения в качестве указателя на датчике (построитель отчетов и SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9d73b3c3-a068-4868-a2be-0cd261b6e92b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c694cdb90fb668c43eb7e9971bba967bad8dd9cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734946"
---
# <a name="specify-an-image-as-a-pointer-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="d6cf5-102">Задание изображения для указателя на датчике (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d6cf5-102">Specify an Image as a Pointer on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d6cf5-103">Датчик содержит три встроенных стиля, которые используются для настройки внешнего вида указателя.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-103">The gauge contains three built-in styles that can be used to customize the appearance of the pointer.</span></span> <span data-ttu-id="d6cf5-104">Для радиального датчика встроенные стили: стрелки, маркеры и линии.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-104">For a radial gauge, the built in styles are: Needle, Marker and Bar.</span></span> <span data-ttu-id="d6cf5-105">Для линейных датчиков существуют следующие стили: маркер, черта и термометр.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-105">For a linear gauge, the built-in styles are Marker, Bar, and Thermometer.</span></span> <span data-ttu-id="d6cf5-106">Если пользователю требуется особый указатель, он может создать и задать изображение, которое будет использоваться в качестве полностью функционального указателя.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-106">If a unique pointer is required, the user can create and specify an image which can be used as a fully functional pointer.</span></span>  
  
 <span data-ttu-id="d6cf5-107">При указании изображения для указателя оно должно отвечать следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-107">When you are specifying an image for the pointer, your image must have the following specifications:</span></span>  
  
-   <span data-ttu-id="d6cf5-108">Исходная точка указателя, или центр вращения, должна находиться наверху изображения.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-108">The origin of the pointer, or center of rotation, must be at the top of the image.</span></span>  
  
-   <span data-ttu-id="d6cf5-109">Конечная точка указателя должна показывать вниз.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-109">The end of the pointer must be pointing down.</span></span>  
  
 <span data-ttu-id="d6cf5-110">Поскольку указатель имеет неправильную форму, необходимо задать цвет прозрачности, чтобы скрыть ненужные части изображения.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-110">Since the pointer is an irregular shape, you will need to specify a transparency color to hide the unnecessary portions of the image.</span></span> <span data-ttu-id="d6cf5-111">Рекомендуется применять тот цвет прозрачности, который не будет отображаться на датчике, поскольку заданный цвет не появится на датчике.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-111">Consider using a color that would not normally be shown on the gauge as the transparency color, since the colors specified will not appear on the gauge.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-an-image-as-a-pointer-on-the-gauge"></a><span data-ttu-id="d6cf5-112">Установка изображения в качестве указателя датчика</span><span class="sxs-lookup"><span data-stu-id="d6cf5-112">To specify an image as a pointer on the gauge</span></span>  
  
1.  <span data-ttu-id="d6cf5-113">В режиме конструктора щелкните указатель датчика.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-113">In Design view, click the pointer of the gauge.</span></span>  
  
2.  <span data-ttu-id="d6cf5-114">Используемых Если на датчике не существует указателя, щелкните датчик правой кнопкой мыши и выберите команду **Добавить указатель**.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-114">(Optional) If no pointer exists on the gauge, right-click on the gauge and select **Add Pointer**.</span></span> <span data-ttu-id="d6cf5-115">К датчику добавится указатель.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-115">A pointer is added to the gauge.</span></span>  
  
3.  <span data-ttu-id="d6cf5-116">Щелкните вкладку **Вставка** на ленте и дважды щелкните значок изображения.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-116">Click the **Insert** tab on the ribbon and double-click the image icon.</span></span> <span data-ttu-id="d6cf5-117">Откроется диалоговое окно **Свойства изображения**.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-117">The **Image Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="d6cf5-118">Добавьте изображение к отчету.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-118">Add an image to your report.</span></span> <span data-ttu-id="d6cf5-119">Дополнительные сведения см. [в разделе внедрение изображения в отчет &#40;построитель отчетов и службы SSRS&#41;](report-design/embed-an-image-in-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d6cf5-119">For more information, see [Embed an Image in a Report &#40;Report Builder and SSRS&#41;](report-design/embed-an-image-in-a-report-report-builder-and-ssrs.md).</span></span>  
  
5.  <span data-ttu-id="d6cf5-120">Откройте панель «Свойства».</span><span class="sxs-lookup"><span data-stu-id="d6cf5-120">Open the Properties pane.</span></span>  
  
6.  <span data-ttu-id="d6cf5-121">Щелкните указатель в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-121">On the design surface, click on the pointer.</span></span> <span data-ttu-id="d6cf5-122">На панели «Свойства» отобразятся свойства указателя.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-122">The properties for the pointer are displayed in the Properties pane.</span></span>  
  
7.  <span data-ttu-id="d6cf5-123">Разверните узел Поинтеримаже.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-123">Expand the PointerImage node.</span></span>  
  
8.  <span data-ttu-id="d6cf5-124">В поле **источник**выберите **внедренный** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-124">In **Source**, select **Embedded** from the drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d6cf5-125">Если изображение хранится в базе данных или в Интернете, для этого свойства можно задать соответствующий параметр.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-125">If your image is stored in the database or on the web, you can specify the appropriate option for this property.</span></span> <span data-ttu-id="d6cf5-126">Дополнительные сведения см. в разделе [диалоговое окно "Свойства изображения", общие &#40;построитель отчетов и службы SSRS&#41;](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d6cf5-126">For more information, see [Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md).</span></span>  
  
9. <span data-ttu-id="d6cf5-127">В поле **значение**выберите имя изображения из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-127">In **Value**, select the name of your image from the drop-down list.</span></span>  
  
10. <span data-ttu-id="d6cf5-128">В **транспарентколор**выберите значение цвета, которое нужно удалить из изображения.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-128">In **TransparentColor**, pick a color value that you want to remove from the image.</span></span> <span data-ttu-id="d6cf5-129">Таким образом, создается цельное изображение указателя на датчике.</span><span class="sxs-lookup"><span data-stu-id="d6cf5-129">This will create a seamless appearance for the pointer in the gauge.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6cf5-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="d6cf5-130">See Also</span></span>  
 <span data-ttu-id="d6cf5-131">[Форматирование указателей в построитель отчетов &#40;датчика и SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6cf5-131">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](report-design/formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d6cf5-132">[Добавление датчика в построитель отчетов &#40;отчетов и службы SSRS&#41;](report-design/add-a-gauge-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6cf5-132">[Add a Gauge to a Report &#40;Report Builder and SSRS&#41;](report-design/add-a-gauge-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d6cf5-133">[Форматирование линий, цветов и изображений &#40;построитель отчетов и SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d6cf5-133">[Formatting Lines, Colors, and Images &#40;Report Builder and SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d6cf5-134">Датчики (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d6cf5-134">Gauges &#40;Report Builder and SSRS&#41;</span></span>](report-design/gauges-report-builder-and-ssrs.md)  
  
  
