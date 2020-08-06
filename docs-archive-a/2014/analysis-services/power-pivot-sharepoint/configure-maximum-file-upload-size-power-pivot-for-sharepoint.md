---
title: Настройка максимального размера передаваемого файла (PowerPivot для SharePoint) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ac516c63-1e79-4ae8-bca6-32d3c1a09c00
author: minewiskan
ms.author: owend
ms.openlocfilehash: 34a0adb2f22915289cccfa1f21c51038263acca0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727378"
---
# <a name="configure-maximum-file-upload-size-powerpivot-for-sharepoint"></a><span data-ttu-id="c9912-102">настроить максимальный размер передаваемого файла (PowerPivot для SharePoint)</span><span class="sxs-lookup"><span data-stu-id="c9912-102">Configure Maximum File Upload Size (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="c9912-103">Книги PowerPivot часто содержат большие объемы данных, при этом размер файлов превышает максимально возможный для передачи в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c9912-103">PowerPivot workbooks often contain large amounts of data that result in files that exceed the maximum file size allowed for SharePoint uploads.</span></span> <span data-ttu-id="c9912-104">При попытке передать файл, размер которого больше предельно допустимого, на SharePoint возникнет следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="c9912-104">When you try to upload a file that exceeds the upper limit, you will get the following error on SharePoint:</span></span>  
  
-   <span data-ttu-id="c9912-105">«Указанный файл больше максимально возможного размера файла».</span><span class="sxs-lookup"><span data-stu-id="c9912-105">"The specified file is larger than the maximum supported file size."</span></span>  
  
 <span data-ttu-id="c9912-106">Чтобы увеличить размер файла, сначала установите параметру «Максимальный размер книги для служб Excel Services» значение 50 мегабайт.</span><span class="sxs-lookup"><span data-stu-id="c9912-106">To increase the file size, start by adjusting the Maximum Workbook Size for Excel Services to 50 megabytes.</span></span> <span data-ttu-id="c9912-107">При этом максимальный размер файла для Excel станет таким же, как у веб-приложений SharePoint (50 МБ по умолчанию в SharePoint 2010 и 200 МБ в SharePoint 2013).</span><span class="sxs-lookup"><span data-stu-id="c9912-107">This aligns the maximum file size limits for Excel to those of SharePoint web applications (set to 50 megabytes by default in SharePoint 2010 and 200 in SharePoint 2013).</span></span> <span data-ttu-id="c9912-108">Если файлы больше 50 мегабайт, то следует увеличить максимальные размер файла как для служб Excel Services, так и для веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="c9912-108">If your files exceed 50 megabytes in size, increase the file size limits for both Excel Services and your web application.</span></span>  
  
 <span data-ttu-id="c9912-109">Для изменения максимального размера файла для передачи необходимо быть администратором SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c9912-109">You must be a SharePoint administrator to change the maximum file upload size.</span></span>  
  
### <a name="configure-maximum-file-size-for-excel-services"></a><span data-ttu-id="c9912-110">Настройка максимального размера файла для службы Excel Services</span><span class="sxs-lookup"><span data-stu-id="c9912-110">Configure maximum file size for Excel Services</span></span>  
  
1.  <span data-ttu-id="c9912-111">В разделе «Управление приложениями» центра администрирования выберите пункт **Управление приложениями служб**.</span><span class="sxs-lookup"><span data-stu-id="c9912-111">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="c9912-112">Выберите имя приложения службы Excel.</span><span class="sxs-lookup"><span data-stu-id="c9912-112">Click the name of your Excel Services Application.</span></span>  
  
3.  <span data-ttu-id="c9912-113">Выберите **Расположение доверенных файлов**.</span><span class="sxs-lookup"><span data-stu-id="c9912-113">Click **Trusted File Locations**.</span></span>  
  
4.  <span data-ttu-id="c9912-114">Выберите расположение, чтобы изменить его свойства.</span><span class="sxs-lookup"><span data-stu-id="c9912-114">Click the location to edit the properties.</span></span> <span data-ttu-id="c9912-115">По умолчанию служба Excel Services считает веб-приложение по умолчанию надежным сайтом.</span><span class="sxs-lookup"><span data-stu-id="c9912-115">By default, Excel Services considers the default web application a trusted site.</span></span> <span data-ttu-id="c9912-116">При использовании веб-приложения по умолчанию щелкните элемент **http://** , чтобы открыть страницу настройки для этого расположения.</span><span class="sxs-lookup"><span data-stu-id="c9912-116">If you are using the default web application, click **http://** to open the configuration page for this location.</span></span>  
  
5.  <span data-ttu-id="c9912-117">Прокрутите список до пункта **Свойства книги**.</span><span class="sxs-lookup"><span data-stu-id="c9912-117">Scroll to **Workbook Properties**.</span></span>  
  
6.  <span data-ttu-id="c9912-118">В поле «Максимальный размер книги» увеличьте размер файла с 10 (значение по умолчанию) до 50 или больше, в зависимости от потребностей.</span><span class="sxs-lookup"><span data-stu-id="c9912-118">In Maximum Workbook Size, increase the file size from 10 (the default value) to 50 or a larger size that accommodates the files you are working with.</span></span>  
  
     <span data-ttu-id="c9912-119">По умолчанию 50 МБ — это максимальный размер файла, который можно передать для веб-приложений SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c9912-119">By default, 50 megabytes is the maximum file upload size for SharePoint web applications.</span></span> <span data-ttu-id="c9912-120">Если параметру «Максимальный размер книги» задано значение больше 50 МБ, выполните шаги, описанные далее, чтобы увеличить максимальный размер передаваемого файла для веб-приложения SharePoint до такого же значения.</span><span class="sxs-lookup"><span data-stu-id="c9912-120">If you set Maximum Workbook Size to a number larger than 50 megabytes, follow the steps in the next procedure to increase the Maximum Upload Size for your SharePoint web application to the same value.</span></span>  
  
     <span data-ttu-id="c9912-121">Максимальное значение, которое можно указать, составляет 2 ГБ (или 2047 МБ в соответствии с параметром, заданным в центре администрирования).</span><span class="sxs-lookup"><span data-stu-id="c9912-121">The maximum value that you can specify is 2 gigabytes (or 2047 megabytes as specified in Central Administration).</span></span>  
  
7.  <span data-ttu-id="c9912-122">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c9912-122">Click **OK**.</span></span>  
  
### <a name="configure-maximum-file-size-for-a-sharepoint-web-application"></a><span data-ttu-id="c9912-123">Настройка максимального размера файла для веб-приложения SharePoint</span><span class="sxs-lookup"><span data-stu-id="c9912-123">Configure maximum file size for a SharePoint web application</span></span>  
  
1.  <span data-ttu-id="c9912-124">В центре администрирования в окне "Управление приложениями" щелкните **Управление веб-приложениями**.</span><span class="sxs-lookup"><span data-stu-id="c9912-124">In Central Administration, in Application Management, click **Manage web applications**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c9912-125">Выполните следующие шаги, только если параметр «Максимальный размер книги» в службе Excel Services был увеличен.</span><span class="sxs-lookup"><span data-stu-id="c9912-125">Perform the following steps only if you increased the Maximum Workbook Size in Excel Services.</span></span>  
  
2.  <span data-ttu-id="c9912-126">Выберите приложение (например, **SharePoint — 80**).</span><span class="sxs-lookup"><span data-stu-id="c9912-126">Select the application (for example, **SharePoint - 80**).</span></span>  
  
3.  <span data-ttu-id="c9912-127">На ленте «Веб-приложения» на кнопке «Общие параметры» щелкните стрелку вниз.</span><span class="sxs-lookup"><span data-stu-id="c9912-127">On the Web Applications ribbon, click the down arrow on the General Settings button.</span></span>  
  
4.  <span data-ttu-id="c9912-128">Щелкните **Общие параметры**.</span><span class="sxs-lookup"><span data-stu-id="c9912-128">Click **General Settings**.</span></span>  
  
5.  <span data-ttu-id="c9912-129">Прокрутите список до пункта **Максимальный размер передаваемого файла**.</span><span class="sxs-lookup"><span data-stu-id="c9912-129">Scroll to **Maximum Upload Size**.</span></span>  
  
6.  <span data-ttu-id="c9912-130">Задайте этому свойству такое же или большее значение, как для параметра «Максимальный размер книги» в службе Excel Services.</span><span class="sxs-lookup"><span data-stu-id="c9912-130">Set the property to the same number, or larger as the Maximum Workbook Size in Excel Services.</span></span>  
  
7.  <span data-ttu-id="c9912-131">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c9912-131">Click **OK**.</span></span>  
  
  
