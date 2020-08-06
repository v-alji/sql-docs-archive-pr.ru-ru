---
title: Добавление внешнего изображения (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 81fd4a1f-79a9-4967-86d6-6229413c0995
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8d0030c8f29b14b2c62048be306daa15948cd8d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729053"
---
# <a name="add-an-external-image-report-builder-and-ssrs"></a><span data-ttu-id="4cbb2-102">Добавление внешнего изображения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="4cbb2-102">Add an External Image (Report Builder and SSRS)</span></span>
  <span data-ttu-id="4cbb2-103">Внешние изображения могут находиться на сервере отчетов в собственном режиме или в режиме интеграции с SharePoint либо находиться на любом другом веб-сайте.</span><span class="sxs-lookup"><span data-stu-id="4cbb2-103">External images can be on a report server in native mode or SharePoint integrated mode, or on any other Web site.</span></span> <span data-ttu-id="4cbb2-104">При включении внешних изображений в отчет необходимо проверить, что изображение существует и читатель отчета имеет разрешения на доступ к изображению.</span><span class="sxs-lookup"><span data-stu-id="4cbb2-104">When you include external images in your report, you must verify that the image exists and that the report reader has permissions to access the image.</span></span> <span data-ttu-id="4cbb2-105">Дополнительные сведения см. в разделе [Изображения (построитель отчетов и службы SSRS)](images-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4cbb2-105">For more information, see [Images &#40;Report Builder and SSRS&#41;](images-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-external-image"></a><span data-ttu-id="4cbb2-106">Добавление внешнего изображения</span><span class="sxs-lookup"><span data-stu-id="4cbb2-106">To add an external image</span></span>  
  
1.  <span data-ttu-id="4cbb2-107">В режиме конструктора отчетов нажмите на вкладке **Вставка** кнопку **Изображение**.</span><span class="sxs-lookup"><span data-stu-id="4cbb2-107">In report design view, on the **Insert** tab, click **Image**.</span></span>  
  
2.  <span data-ttu-id="4cbb2-108">В области конструктора щелкните и перетащите рамку, чтобы получилось изображение нужного размера.</span><span class="sxs-lookup"><span data-stu-id="4cbb2-108">On the design surface, click and then drag a box to the desired size of the image.</span></span>  
  
3.  <span data-ttu-id="4cbb2-109">На вкладке **Общие** диалогового окна **Свойства изображения** введите имя в текстовое поле **Имя** или примите имя по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4cbb2-109">On the **General** tab of the **Image Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span>  
  
4.  <span data-ttu-id="4cbb2-110">В текстовом поле **Подсказка** введите текст, отображаемый при наведении курсора на изображение в отчете, подготовленном к просмотру в формате HTML (необязательно).</span><span class="sxs-lookup"><span data-stu-id="4cbb2-110">(Optional) In the **Tooltip** text box, type text to display when the user hovers over the image in a report rendered for HTML.</span></span>  
  
5.  <span data-ttu-id="4cbb2-111">В списке **Выберите источник изображения**выберите **Внешний**.</span><span class="sxs-lookup"><span data-stu-id="4cbb2-111">In **Select the image source**, select **External**.</span></span>  
  
     <span data-ttu-id="4cbb2-112">Для изображения, расположенного на сервере отчетов в собственном режиме, введите относительный путь к изображению в поле **Использовать это изображение**, например ../images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="4cbb2-112">For an image on a report server in native mode, type a relative path to the image in the **Use this image** box-for example, ../images/image1.jpg.</span></span>  
  
     <span data-ttu-id="4cbb2-113">Для изображения на сервере отчетов в режиме интеграции с SharePoint или любого другого веб-сайта введите полный URL-адрес изображения в поле **использовать это изображение** , например http:// \<SharePointservername> / \<site> /документс/имажес/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="4cbb2-113">For an image on a report server in SharePoint integrated mode, or any other Web site, type a full URL to the image in the **Use this image** box-for example, http://\<SharePointservername>/\<site>/Documents/images/image1.jpg.</span></span>  
  
     <span data-ttu-id="4cbb2-114">Дополнительные сведения см. в разделе [Указание путей к внешним элементам (построитель отчетов и службы SSRS)](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4cbb2-114">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="4cbb2-115">Нажмите кнопку **Размер**, **Видимость**, **Действие**или **Граница** , чтобы задать дополнительные свойства изображения отчета (необязательно).</span><span class="sxs-lookup"><span data-stu-id="4cbb2-115">(Optional) Click **Size**, **Visibility**, **Action**, or **Border** to set additional properties for the image report item.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4cbb2-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="4cbb2-116">See Also</span></span>  
 <span data-ttu-id="4cbb2-117">[Внедрение изображения в отчет (построитель отчетов и службы SSRS)](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4cbb2-117">[Embed an Image in a Report &#40;Report Builder and SSRS&#41;](embed-an-image-in-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4cbb2-118">[Добавление фонового изображения (построитель отчетов и службы SSRS)](add-a-background-image-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4cbb2-118">[Add a Background Image &#40;Report Builder and SSRS&#41;](add-a-background-image-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4cbb2-119">Диалоговое окно "Свойства изображения" — "Общие" (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="4cbb2-119">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
