---
title: Изменение значков индикаторов и наборов индикаторов (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8a056adf-4473-473d-9b0c-314675af7bfd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 398d21319ab6da22f2b10c3607baf8f110d6e65b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737946"
---
# <a name="change-indicator-icons-and-indicator-sets-report-builder-and-ssrs"></a><span data-ttu-id="7b64d-102">Изменение значков индикаторов и наборов индикаторов (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="7b64d-102">Change Indicator Icons and Indicator Sets (Report Builder and SSRS)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]<span data-ttu-id="7b64d-103">предоставляет предварительно настроенные наборы индикаторов, которые не всегда эффективно описывают данные и хорошо работают в доставленном отчете.</span><span class="sxs-lookup"><span data-stu-id="7b64d-103">provides preconfigured indicators sets, which might not always depict your data effectively and work well in the delivered report.</span></span> <span data-ttu-id="7b64d-104">В этом разделе рассматриваются процедуры изменения внешнего вида значков индикатора и изменения наборов индикаторов — с включением других значков индикаторов, представленных в большем или меньшем количестве.</span><span class="sxs-lookup"><span data-stu-id="7b64d-104">This topic provides procedures to change the appearance of indicator icons and change the indicator sets to include different, more, or fewer indicator icons.</span></span>  
  
 <span data-ttu-id="7b64d-105">Такие параметры, как цвета, могут быть заданы с использованием выражений.</span><span class="sxs-lookup"><span data-stu-id="7b64d-105">Options such as colors can be set by using expressions.</span></span> <span data-ttu-id="7b64d-106">Дополнительные сведения см. в разделе [Выражения (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7b64d-106">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-color-of-an-indicator-icon"></a><span data-ttu-id="7b64d-107">Изменение цвета значка индикатора</span><span class="sxs-lookup"><span data-stu-id="7b64d-107">To change the color of an indicator icon</span></span>  
  
1.  <span data-ttu-id="7b64d-108">Щелкните правой кнопкой мыши индикатор, который необходимо изменить, и выберите **Свойства индикатора**.</span><span class="sxs-lookup"><span data-stu-id="7b64d-108">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="7b64d-109">Нажмите кнопку **Значения и состояния** на левой панели.</span><span class="sxs-lookup"><span data-stu-id="7b64d-109">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="7b64d-110">Нажмите стрелку вниз в столбце **Цвет** рядом со значком, который требуется изменить, и щелкните нужный цвет либо нажмите **Без цвета**или **Дополнительные цвета**.</span><span class="sxs-lookup"><span data-stu-id="7b64d-110">Click the down arrow in the **Color** column next to the icon that you want to change and click the color to use, **No Color**, or **More colors**.</span></span>  
  
     <span data-ttu-id="7b64d-111">Также можно нажать кнопку **Выражение** (*fx*), чтобы изменить выражение, которое задает значение параметра **Цвет** .</span><span class="sxs-lookup"><span data-stu-id="7b64d-111">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the **Color** option.</span></span>  
  
     <span data-ttu-id="7b64d-112">Если вы нажали **Дополнительные цвета**, откроется диалоговое окно **Выбор цвета** , позволяющее выбирать цвета из широкого массива.</span><span class="sxs-lookup"><span data-stu-id="7b64d-112">If you clicked **More Colors**, the **Select Color** dialog box opens, where you can choose from a wide array of colors.</span></span> <span data-ttu-id="7b64d-113">Дополнительные сведения о параметрах см. в разделе [Диалоговое окно "Выбор цвета" &#40;построитель отчетов и службы SSRS&#41;](../select-color-dialog-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7b64d-113">For more information about its options, see [Select Color Dialog Box &#40;Report Builder and SSRS&#41;](../select-color-dialog-box-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="7b64d-114">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Выбор цвета** .</span><span class="sxs-lookup"><span data-stu-id="7b64d-114">Click **OK** to close the **Select Color** dialog box.</span></span>  
  
4.  <span data-ttu-id="7b64d-115">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7b64d-115">Click **OK**.</span></span>  
  
### <a name="to-change-the-icon"></a><span data-ttu-id="7b64d-116">Изменение значка</span><span class="sxs-lookup"><span data-stu-id="7b64d-116">To change the icon</span></span>  
  
1.  <span data-ttu-id="7b64d-117">Щелкните правой кнопкой мыши индикатор, который необходимо изменить, и выберите **Свойства индикатора**.</span><span class="sxs-lookup"><span data-stu-id="7b64d-117">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="7b64d-118">Нажмите кнопку **Значения и состояния** на левой панели.</span><span class="sxs-lookup"><span data-stu-id="7b64d-118">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="7b64d-119">Щелкните стрелку вниз рядом со значком, который необходимо сменить, и выберите другой значок.</span><span class="sxs-lookup"><span data-stu-id="7b64d-119">Click the down arrow next to the icon that you want to change and select a different icon.</span></span>  
  
     <span data-ttu-id="7b64d-120">Также можно нажать кнопку **Выражение** (*fx*), чтобы изменить выражение, которое задает значение параметра **Значок** .</span><span class="sxs-lookup"><span data-stu-id="7b64d-120">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the **Icon** option.</span></span>  
  
4.  <span data-ttu-id="7b64d-121">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7b64d-121">Click **OK**.</span></span>  
  
### <a name="to-use-a-custom-image-as-an-indicator-icon"></a><span data-ttu-id="7b64d-122">Пользовательское изображение в качестве значка индикатора</span><span class="sxs-lookup"><span data-stu-id="7b64d-122">To use a custom image as an indicator icon</span></span>  
  
1.  <span data-ttu-id="7b64d-123">Щелкните правой кнопкой мыши индикатор, который необходимо изменить, и выберите **Свойства индикатора**.</span><span class="sxs-lookup"><span data-stu-id="7b64d-123">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="7b64d-124">Нажмите кнопку **Значения и состояния** на левой панели.</span><span class="sxs-lookup"><span data-stu-id="7b64d-124">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="7b64d-125">Щелкните стрелку вниз рядом со значком, который необходимо сменить, и выберите **Изображение**.</span><span class="sxs-lookup"><span data-stu-id="7b64d-125">Click the down arrow next to the icon that you wan to change and select **Image**.</span></span>  
  
4.  <span data-ttu-id="7b64d-126">В списке **Выберите источник изображения** щелкните **Внешнее**, **Внедренное**или **Из базы данных**.</span><span class="sxs-lookup"><span data-stu-id="7b64d-126">In the **Select the image source** list, click **External**, **Embedded**, or **Database**.</span></span>  
  
5.  <span data-ttu-id="7b64d-127">В зависимости от источника изображения, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="7b64d-127">Depending on the source of the image, do the one of the following:</span></span>  
  
    -   <span data-ttu-id="7b64d-128">Чтобы использовать изображение, которое хранится вне отчета, нажмите **Обзор** и найдите изображение.</span><span class="sxs-lookup"><span data-stu-id="7b64d-128">To use an image that is stored externally to the report, click **Browse** and locate the image.</span></span> <span data-ttu-id="7b64d-129">В отчет будет включена ссылка на изображение.</span><span class="sxs-lookup"><span data-stu-id="7b64d-129">The report will include a reference to the image.</span></span>  
  
    -   <span data-ttu-id="7b64d-130">Чтобы использовать изображение, внедренное в отчет, нажмите **Импорт** и найдите изображение.</span><span class="sxs-lookup"><span data-stu-id="7b64d-130">To use an image that is embedded in the report, click **Import** and locate the image.</span></span> <span data-ttu-id="7b64d-131">Изображение будет добавлено к определению отчета и сохранено вместе с ним.</span><span class="sxs-lookup"><span data-stu-id="7b64d-131">The image will be added to the report definition and saved with it.</span></span>  
  
    -   <span data-ttu-id="7b64d-132">Чтобы использовать изображение, которое находится в базе данных, выберите в списке **Использовать это поле** нужное поле.</span><span class="sxs-lookup"><span data-stu-id="7b64d-132">To use an image that is in a database, in the **Use this field** list.</span></span> <span data-ttu-id="7b64d-133">Затем в списке **Использовать этот тип MIME** выберите тип MIME изображения.</span><span class="sxs-lookup"><span data-stu-id="7b64d-133">select the field from the list and then in the **Use this MIME type** list, select the MIME type of the image.</span></span>  
  
6.  <span data-ttu-id="7b64d-134">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7b64d-134">Click **OK**.</span></span>  
  
### <a name="to-add-an-icon-to-the-indicator-set"></a><span data-ttu-id="7b64d-135">Добавление значка к набору индикаторов</span><span class="sxs-lookup"><span data-stu-id="7b64d-135">To add an icon to the indicator set</span></span>  
  
1.  <span data-ttu-id="7b64d-136">Щелкните правой кнопкой мыши индикатор, который необходимо изменить, и выберите **Свойства индикатора**.</span><span class="sxs-lookup"><span data-stu-id="7b64d-136">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="7b64d-137">Нажмите кнопку **Значения и состояния** на левой панели.</span><span class="sxs-lookup"><span data-stu-id="7b64d-137">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="7b64d-138">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7b64d-138">Click **Add**.</span></span> <span data-ttu-id="7b64d-139">Индикатор добавляется со значком по умолчанию и параметром **Без цвета** .</span><span class="sxs-lookup"><span data-stu-id="7b64d-139">An indicator is added, using the default icon and the **No Color** option.</span></span>  
  
     <span data-ttu-id="7b64d-140">Настройте для индикатора нужный значок и цвет.</span><span class="sxs-lookup"><span data-stu-id="7b64d-140">Configure the indictor to use the icon and color you want.</span></span> <span data-ttu-id="7b64d-141">Необходимые для этого шаги описаны в процедурах, приведенных выше в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="7b64d-141">Procedures earlier in this topic describe the steps to do this.</span></span>  
  
4.  <span data-ttu-id="7b64d-142">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7b64d-142">Click **OK**.</span></span>  
  
### <a name="to-delete-an-icon-to-the-indicator-set"></a><span data-ttu-id="7b64d-143">Удаление значка из набора индикаторов</span><span class="sxs-lookup"><span data-stu-id="7b64d-143">To delete an icon to the indicator set</span></span>  
  
1.  <span data-ttu-id="7b64d-144">Щелкните правой кнопкой мыши индикатор, который необходимо изменить, и выберите **Свойства индикатора**.</span><span class="sxs-lookup"><span data-stu-id="7b64d-144">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="7b64d-145">Нажмите кнопку **Значения и состояния** на левой панели.</span><span class="sxs-lookup"><span data-stu-id="7b64d-145">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="7b64d-146">Выберите значок и нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="7b64d-146">Select the icon to delete, and click **Delete**.</span></span>  
  
4.  <span data-ttu-id="7b64d-147">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7b64d-147">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b64d-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="7b64d-148">See Also</span></span>  
 [<span data-ttu-id="7b64d-149">Индикаторы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="7b64d-149">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
