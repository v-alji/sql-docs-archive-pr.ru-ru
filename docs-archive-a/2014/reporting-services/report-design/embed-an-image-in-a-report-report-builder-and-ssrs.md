---
title: Внедрение изображения в отчет (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.embeddedimages.f1
- "10060"
ms.assetid: aed77345-5eeb-41f0-96c9-db6b4a11ec6f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6599092e0ef37dd9bbc15f4815c0315c77e7943b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728045"
---
# <a name="embed-an-image-in-a-report-report-builder-and-ssrs"></a><span data-ttu-id="7935f-102">Внедрение изображения в отчет (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="7935f-102">Embed an Image in a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7935f-103">Отчет может содержать внедренное изображение.</span><span class="sxs-lookup"><span data-stu-id="7935f-103">A report can include an embedded image.</span></span> <span data-ttu-id="7935f-104">Внедрение изображения гарантирует постоянную доступность изображения для отчета, однако увеличивает размер определения отчета (файла, который определяет отчет).</span><span class="sxs-lookup"><span data-stu-id="7935f-104">Embedding an image ensures that the image is always available to a report, but can affect the size of the report definition, the file that defines the report.</span></span> <span data-ttu-id="7935f-105">Изображения, внедренные в отчет, перечислены на панель данных отчета.</span><span class="sxs-lookup"><span data-stu-id="7935f-105">The images embedded in a report are listed in the Report Data pane.</span></span>  
  
 <span data-ttu-id="7935f-106">Может возникнуть необходимость внедрить изображение в определение отчета перед добавлением изображения в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="7935f-106">You might want to embed an image in the report definition before adding the image to the design surface.</span></span> <span data-ttu-id="7935f-107">Дополнительные сведения см. в разделе [Добавление фонового изображения (построитель отчетов и службы SSRS)](add-a-background-image-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7935f-107">For more information, see [Add a Background Image &#40;Report Builder and SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-embed-an-image-in-a-report"></a><span data-ttu-id="7935f-108">Внедрение изображения в отчет</span><span class="sxs-lookup"><span data-stu-id="7935f-108">To embed an image in a report</span></span>  
  
1.  <span data-ttu-id="7935f-109">В режиме конструктора отчетов нажмите на вкладке **Вставка** кнопку **Изображение**.</span><span class="sxs-lookup"><span data-stu-id="7935f-109">In report design view, on the **Insert** tab, click **Image**.</span></span>  
  
2.  <span data-ttu-id="7935f-110">В области конструктора щелкните и перетащите рамку, чтобы получилось изображение нужного размера.</span><span class="sxs-lookup"><span data-stu-id="7935f-110">On the design surface, click and then drag a box to the desired size of the image.</span></span>  
  
3.  <span data-ttu-id="7935f-111">На странице **Общие** диалогового окна **Свойства изображения** введите имя в текстовое поле **Имя** или примите имя по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7935f-111">In the **General** page of the **Image Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span>  
  
4.  <span data-ttu-id="7935f-112">В текстовом поле **Подсказка** введите текст, который будет появляться при наведении курсора на изображение в отчете, готовом для просмотра (необязательно).</span><span class="sxs-lookup"><span data-stu-id="7935f-112">(Optional) In the **ToolTip** text box, type the text that you want to appear when the user hovers over the image in the rendered report.</span></span>  
  
5.  <span data-ttu-id="7935f-113">В списке **Выберите источник изображения**выберите **Внедренный**.</span><span class="sxs-lookup"><span data-stu-id="7935f-113">In **Select the image source**, select **Embedded**.</span></span>  
  
6.  <span data-ttu-id="7935f-114">Нажмите кнопку **Импортировать** рядом с текстовым полем **Использовать это изображение** .</span><span class="sxs-lookup"><span data-stu-id="7935f-114">Click the **Import** button next to the **Use this image** text box</span></span>  
  
7.  <span data-ttu-id="7935f-115">В поле **Файлы типа**выберите тип файлов изображения, перейдите к файлу и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="7935f-115">In **Files of type**, select the image file type, navigate to the file, and then click **Open**.</span></span>  
  
8.  <span data-ttu-id="7935f-116">В диалоговом окне **Свойства изображения** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7935f-116">In the **Image Properties** dialog box, click **OK**.</span></span>  
  
     <span data-ttu-id="7935f-117">Изображение отображается в рамке, перетащенной в область конструктора, а файл — в папке «Изображения» в области данных отчета.</span><span class="sxs-lookup"><span data-stu-id="7935f-117">The image is displayed in the box you drew on the design surface, and the file is displayed under the Images folder in the Report Data pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7935f-118">Кроме того, при импорте изображения автоматически извлекается тип MIME (например, BMP).</span><span class="sxs-lookup"><span data-stu-id="7935f-118">The MIME type (for example, bmp) is derived automatically when the image is imported.</span></span> <span data-ttu-id="7935f-119">Чтобы изменить тип MIME, см. следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="7935f-119">To change the MIME type, see the next procedure.</span></span>  
  
### <a name="optional-to-change-the-mime-type-of-an-imported-image"></a><span data-ttu-id="7935f-120">Изменение типа MIME импортированного изображения (необязательно)</span><span class="sxs-lookup"><span data-stu-id="7935f-120">(optional) To change the MIME type of an imported image</span></span>  
  
1.  <span data-ttu-id="7935f-121">Откройте отчет в режиме конструктора.</span><span class="sxs-lookup"><span data-stu-id="7935f-121">Open the report in Design view.</span></span>  
  
2.  <span data-ttu-id="7935f-122">Выберите изображение в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="7935f-122">Select the image on the design surface.</span></span> <span data-ttu-id="7935f-123">В панели **Свойства** отображаются свойства изображения.</span><span class="sxs-lookup"><span data-stu-id="7935f-123">The **Properties** pane displays the image properties.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7935f-124">Если панель "Свойства" не отображается, на вкладке **Вид** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7935f-124">If the Properties pane is not visible, on the **View** tab, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="7935f-125">Щелкните текстовое поле рядом со свойством **MIMEType** и выберите из раскрывающегося списка новый тип MIME.</span><span class="sxs-lookup"><span data-stu-id="7935f-125">Click in the text box next to the **MIMEType** property and select a new MIME type from the drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7935f-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="7935f-126">See Also</span></span>  
 <span data-ttu-id="7935f-127">[Изображения (построитель отчетов и службы SSRS)](images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7935f-127">[Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7935f-128">[Добавление привязанного к данным изображения (построитель отчетов и службы SSRS)](add-a-data-bound-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7935f-128">[Add a Data-Bound Image &#40;Report Builder and SSRS&#41;](add-a-data-bound-image-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7935f-129">Диалоговое окно "Свойства изображения" — "Общие" (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="7935f-129">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
