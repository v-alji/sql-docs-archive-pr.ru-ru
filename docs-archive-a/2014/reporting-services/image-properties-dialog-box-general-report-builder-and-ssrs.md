---
title: Диалоговое окно "Свойства изображения" — "Общие" (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10051"
- sql12.rtp.rptdesigner.pictureproperties.general.f1
ms.assetid: c2218b93-f7fe-46ef-995f-d7dadf9752ec
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e599a437ae367a38483dbde99ffff79f64b957ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751888"
---
# <a name="image-properties-dialog-box-general-report-builder-and-ssrs"></a><span data-ttu-id="f107a-102">Диалоговое окно «Свойства изображения» — «Общие» (построитель отчетов и SSRS)</span><span class="sxs-lookup"><span data-stu-id="f107a-102">Image Properties Dialog Box, General (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f107a-103">Перейдите на вкладку **Общие** в диалоговом окне **Свойства изображения** , чтобы добавить рисунок, изменить имя по умолчанию для изображения или добавить текст подсказки.</span><span class="sxs-lookup"><span data-stu-id="f107a-103">Select **General** on the **Image Properties** dialog box to add a picture, change the default name of the image, and add ToolTip text.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f107a-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="f107a-104">Options</span></span>  
 <span data-ttu-id="f107a-105">**имя**;</span><span class="sxs-lookup"><span data-stu-id="f107a-105">**Name**</span></span>  
 <span data-ttu-id="f107a-106">Введите имя элемента.</span><span class="sxs-lookup"><span data-stu-id="f107a-106">Type a name for the item.</span></span> <span data-ttu-id="f107a-107">В пределах отчета имя должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="f107a-107">The name must be unique within the report.</span></span> <span data-ttu-id="f107a-108">По умолчанию присваивается стандартное имя, например Изображение1 или Изображение2.</span><span class="sxs-lookup"><span data-stu-id="f107a-108">By default, a general name, such as Image1 or Image2, is assigned.</span></span>  
  
 <span data-ttu-id="f107a-109">**Подсказка**</span><span class="sxs-lookup"><span data-stu-id="f107a-109">**Tooltip**</span></span>  
 <span data-ttu-id="f107a-110">Введите подсказку или выражение, результатом вычисления которого является подсказка.</span><span class="sxs-lookup"><span data-stu-id="f107a-110">Type text or an expression that evaluates to a ToolTip.</span></span> <span data-ttu-id="f107a-111">Нажмите кнопку Выражение (*FX*), чтобы изменить выражение.</span><span class="sxs-lookup"><span data-stu-id="f107a-111">Click the Expression (*fx*) button to edit the expression.</span></span> <span data-ttu-id="f107a-112">**Подсказка** появляется в случае, если задержать указатель мыши над текстовым полем в HTML-отчете.</span><span class="sxs-lookup"><span data-stu-id="f107a-112">The **Tooltip** appears when the user pauses the pointer over the item in an HTML report.</span></span>  
  
 <span data-ttu-id="f107a-113">**Выберите источник изображения**</span><span class="sxs-lookup"><span data-stu-id="f107a-113">**Select the image source**</span></span>  
 <span data-ttu-id="f107a-114">Укажите место хранения изображения, чтобы обработчик отчетов смог его найти при подготовке отчета.</span><span class="sxs-lookup"><span data-stu-id="f107a-114">Indicate where the image is stored so that when the report is rendered, the report processor will know where to get the image from.</span></span>  
  
-   <span data-ttu-id="f107a-115">**Внешнее** Выберите этот параметр, если изображение должно храниться в виде файла на сервере отчетов или на веб-сервере.</span><span class="sxs-lookup"><span data-stu-id="f107a-115">**External** Choose this option when you want the image to continue to exist as a file on a report server or Web server.</span></span>  
  
-   <span data-ttu-id="f107a-116">**Внедренное** Выберите этот параметр, если изображение должно быть встроено в отчет.</span><span class="sxs-lookup"><span data-stu-id="f107a-116">**Embedded** Choose this option when you want to embed the image into the report.</span></span>  
  
-   <span data-ttu-id="f107a-117">**База данных** Выберите этот параметр, чтобы указать имя поля базы данных, представляющего изображение, которое должно быть включено в отчет.</span><span class="sxs-lookup"><span data-stu-id="f107a-117">**Database** Choose this option when you want to include a database field name that represents the images that you want to include in your report.</span></span>  
  
 <span data-ttu-id="f107a-118">**Использовать это изображение**</span><span class="sxs-lookup"><span data-stu-id="f107a-118">**Use this image**</span></span>  
 <span data-ttu-id="f107a-119">Этот параметр доступен в том случае, если выбран параметр **Внедренное** или **Внешнее** .</span><span class="sxs-lookup"><span data-stu-id="f107a-119">This option appears when you select the **Embedded** or **External** option.</span></span>  
  
 <span data-ttu-id="f107a-120">При внедрении выберите из раскрывающегося списка изображение, которое необходимо добавить в отчет.</span><span class="sxs-lookup"><span data-stu-id="f107a-120">If you are embedding the image, choose the image that you want to add to the report from the drop-down list.</span></span> <span data-ttu-id="f107a-121">Чтобы добавить изображение в раскрывающийся список, нажмите кнопку **Импорт** .</span><span class="sxs-lookup"><span data-stu-id="f107a-121">Click the **Import** button to add the image to the drop-down list.</span></span>  
  
 <span data-ttu-id="f107a-122">Если выбран параметр **Внешний** , введите URL-адрес изображения.</span><span class="sxs-lookup"><span data-stu-id="f107a-122">If you select the **External** option, type the URL of the image.</span></span> <span data-ttu-id="f107a-123">Для отчета, который опубликован на сервере отчетов, работающем в собственном режиме, используется полный или относительный путь,</span><span class="sxs-lookup"><span data-stu-id="f107a-123">For a report published to a report server configured for native mode, use a full or relative path.</span></span> <span data-ttu-id="f107a-124">Например, http:// \<servername> /images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="f107a-124">For example, http://\<servername>/images/image1.jpg.</span></span> <span data-ttu-id="f107a-125">Для отчета, который опубликован на сервере отчетов, работающем в режиме интеграции с SharePoint, используется полный URL-адрес,</span><span class="sxs-lookup"><span data-stu-id="f107a-125">For a report published to a report server configured in SharePoint integrated mode, use a fully qualified URL.</span></span> <span data-ttu-id="f107a-126">Например, http:// \<*SharePointservername*> / \<*site*> /документс/имажес/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="f107a-126">For example, http://\<*SharePointservername*>/\<*site*>/Documents/images/image1.jpg.</span></span>  
  
 <span data-ttu-id="f107a-127">**Импорт**</span><span class="sxs-lookup"><span data-stu-id="f107a-127">**Import**</span></span>  
 <span data-ttu-id="f107a-128">Нажмите, чтобы добавить изображение в раскрывающийся список **Использовать это изображение** .</span><span class="sxs-lookup"><span data-stu-id="f107a-128">Click to add an image to the **Use this image** drop-down list.</span></span>  
  
 <span data-ttu-id="f107a-129">**Использовать это поле**</span><span class="sxs-lookup"><span data-stu-id="f107a-129">**Use this field**</span></span>  
 <span data-ttu-id="f107a-130">Этот параметр доступен только после выбора параметра **База данных** .</span><span class="sxs-lookup"><span data-stu-id="f107a-130">This option appears if you select the **Database** option.</span></span> <span data-ttu-id="f107a-131">Выберите имя поля.</span><span class="sxs-lookup"><span data-stu-id="f107a-131">Select the field name.</span></span>  
  
 <span data-ttu-id="f107a-132">**Использовать этот тип MIME**</span><span class="sxs-lookup"><span data-stu-id="f107a-132">**Use this MIME type**</span></span>  
 <span data-ttu-id="f107a-133">Выберите формат изображения в базе данных (например, BMP, JPEG, GIF, PNG или X-PNG).</span><span class="sxs-lookup"><span data-stu-id="f107a-133">Choose the appropriate format of the images contained in the database, for example, .bmp, .jpeg, .gif, .png, and .x-png.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f107a-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="f107a-134">See Also</span></span>  
 <span data-ttu-id="f107a-135">[Примеры выражений (построитель отчетов и службы SSRS)](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f107a-135">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f107a-136">[Образы &#40;построитель отчетов и службы SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f107a-136">[Images &#40;Report Builder and SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f107a-137">Справка построителя отчетов для диалоговых окон, панелей и мастеров</span><span class="sxs-lookup"><span data-stu-id="f107a-137">Report Builder Help for Dialog Boxes, Panes, and Wizards</span></span>](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md)  
  
  
