---
title: Просмотр элементов отчета и назначение папки по умолчанию (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5cf38068-65d1-4fe8-81f3-a404d8fbc663
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6605a23732799ec07b3dbe8481e88c91b18ebe5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656163"
---
# <a name="browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs"></a><span data-ttu-id="9830e-102">Просмотр элементов отчета и назначение папки по умолчанию (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="9830e-102">Browse for Report Parts and Set a Default Folder (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9830e-103">Самым простым способом создания отчетов является добавление существующих элементов отчета, таких как таблицы и диаграммы, к отчету из галереи элементов отчетов.</span><span class="sxs-lookup"><span data-stu-id="9830e-103">The easiest way to create a report is to add existing report parts, such as tables and charts, to your report from the Report Part Gallery.</span></span> <span data-ttu-id="9830e-104">При добавлении элемента отчета к отчету добавляется также все, что необходимо для его выполнения.</span><span class="sxs-lookup"><span data-stu-id="9830e-104">When you add a report part to your report, you are also adding everything it must have to work.</span></span> <span data-ttu-id="9830e-105">Например, все элементы отчета, используемые для отображения данных, зависят от набора данных, т. е. запроса и соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="9830e-105">For example, any report part that displays data depends on a dataset, that is, a query and a connection to a data source.</span></span> <span data-ttu-id="9830e-106">После добавления элемента отчета к отчету ее можно изменить в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="9830e-106">After you add the report part to your report, you can modify it as much as you need.</span></span>  
  
 <span data-ttu-id="9830e-107">Можно задать папку по умолчанию для публикации элементов отчетов на сервере отчетов или сайте SharePoint, интегрированном с сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="9830e-107">You can set a default folder to publish report parts to the report server or SharePoint site integrated with a report server.</span></span>  
  
 <span data-ttu-id="9830e-108">Дополнительные сведения см. в разделе [Элементы отчета (построитель отчетов и службы SSRS)](../report-parts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9830e-108">For more information, see [Report Parts &#40;Report Builder and SSRS&#41;](../report-parts-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-browse-for-report-parts"></a><span data-ttu-id="9830e-109">Просмотр элементов отчетов</span><span class="sxs-lookup"><span data-stu-id="9830e-109">To browse for report parts</span></span>  
  
1.  <span data-ttu-id="9830e-110">В меню **Вставка** выберите **Элементы отчета**.</span><span class="sxs-lookup"><span data-stu-id="9830e-110">On the **Insert** menu, click **Report Parts**.</span></span>  
  
     <span data-ttu-id="9830e-111">При отсутствии подключения выберите **Соединиться с сервером отчетов**и введите имя сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9830e-111">If you are not already connected, click **Connect to a report server**, and enter the name.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9830e-112">Для поиска элементов отчетов необходимо подключение к серверу отчетов.</span><span class="sxs-lookup"><span data-stu-id="9830e-112">You must be connected to a report server to browse for report parts.</span></span>  
  
2.  <span data-ttu-id="9830e-113">Область поиска можно ограничить, указав сведения об элементе отчета.</span><span class="sxs-lookup"><span data-stu-id="9830e-113">You can narrow your search by specifying details about the report part.</span></span> <span data-ttu-id="9830e-114">Введите полное имя или часть его и описание в поле **Поиск** или нажмите **Добавить критерий** и добавьте значения для всех или отдельных полей:</span><span class="sxs-lookup"><span data-stu-id="9830e-114">Type all or part of the name and description in the **Search** box, or click **Add Criteria** and add values for any or all of these fields:</span></span>  
  
    -   <span data-ttu-id="9830e-115">Создан</span><span class="sxs-lookup"><span data-stu-id="9830e-115">Created by</span></span>  
  
    -   <span data-ttu-id="9830e-116">Дата создания</span><span class="sxs-lookup"><span data-stu-id="9830e-116">Date created</span></span>  
  
    -   <span data-ttu-id="9830e-117">Дата последнего изменения</span><span class="sxs-lookup"><span data-stu-id="9830e-117">Date last modified</span></span>  
  
    -   <span data-ttu-id="9830e-118">Последнее изменение выполнено</span><span class="sxs-lookup"><span data-stu-id="9830e-118">Last modified by</span></span>  
  
    -   <span data-ttu-id="9830e-119">Папка сервера</span><span class="sxs-lookup"><span data-stu-id="9830e-119">Server folder</span></span>  
  
    -   <span data-ttu-id="9830e-120">Тип</span><span class="sxs-lookup"><span data-stu-id="9830e-120">Type</span></span>  
  
     <span data-ttu-id="9830e-121">Например, для поиска изображения нажмите **Добавить критерий**, а затем выберите **Тип**.</span><span class="sxs-lookup"><span data-stu-id="9830e-121">For example, to find an image, click **Add Criteria**, and then click **Type**.</span></span> <span data-ttu-id="9830e-122">В раскрывающемся списке установите флажок **Изображение** , нажмите клавишу ВВОД и нажмите значок лупы рядом с полем поиска.</span><span class="sxs-lookup"><span data-stu-id="9830e-122">In the dropdown box, select the **Image** check box, press ENTER, and then click the Search magnifying glass.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9830e-123">При использовании значений **Создан** и **Последнее изменение выполнено** поиск имени пользователя для соответствующих лиц выполняется в том виде, в котором имя представлено на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="9830e-123">For the **Created by** and **Last modified by** values, search for the person's user name as it is represented on the report server.</span></span>  
  
### <a name="to-set-a-default-folder-for-report-parts"></a><span data-ttu-id="9830e-124">Определение папки по умолчанию для элементов отчетов</span><span class="sxs-lookup"><span data-stu-id="9830e-124">To set a default folder for report parts</span></span>  
  
1.  <span data-ttu-id="9830e-125">Выберите **Построитель отчетов**, а затем выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="9830e-125">Click **Report Builder**, and then click **Options**.</span></span>  
  
2.  <span data-ttu-id="9830e-126">В диалоговом окне **Параметры** на вкладке **Настройки** введите имя папки в текстовом поле **По умолчанию опубликовать элементы отчета в следующей папке** .</span><span class="sxs-lookup"><span data-stu-id="9830e-126">In the **Options** dialog box, on the **Settings** tab, type a folder name in the **Publish report parts to this folder by default** textbox.</span></span>  
  
 <span data-ttu-id="9830e-127">Если папка еще не существует и имеются разрешения для создания папок на сервере отчетов, то построитель отчетов создаст эту папку.</span><span class="sxs-lookup"><span data-stu-id="9830e-127">Report Builder will create this folder if you have permissions to create folders on the report server and the folder does not exist yet.</span></span>  
  
 <span data-ttu-id="9830e-128">Чтобы этот параметр вступил в силу, не нужно перезапускать построитель отчетов.</span><span class="sxs-lookup"><span data-stu-id="9830e-128">You do not need to restart Report Builder for this setting to take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9830e-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="9830e-129">See Also</span></span>  
 <span data-ttu-id="9830e-130">[Проверка наличия обновлений или отключение обновлений &#40;построитель отчетов и служб SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9830e-130">[Check for Updates or Turn Updates Off &#40;Report Builder and SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9830e-131">[Элементы отчета (построитель отчетов и службы SSRS)](../report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9830e-131">[Report Parts &#40;Report Builder and SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9830e-132">[Элементы отчета и наборы данных в построителе отчетов](../report-data/report-parts-and-datasets-in-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="9830e-132">[Report Parts and Datasets in Report Builder](../report-data/report-parts-and-datasets-in-report-builder.md) </span></span>  
 <span data-ttu-id="9830e-133">[Устранение неполадок элементов отчетов &#40;построитель отчетов и SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9830e-133">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9830e-134">Публикация и повторная публикация элементов отчетов (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="9830e-134">Publish and Republish Report Parts &#40;Report Builder and SSRS&#41;</span></span>](publish-and-republish-report-parts-report-builder-and-ssrs.md)  
  
  
