---
title: Проверка наличия обновлений или отключение обновлений (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9c69792d-d7c4-453b-ae2f-6d2d071d8606
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 088d41e71d770f746367f2760cff8ff67b15623c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664015"
---
# <a name="check-for-updates-or-turn-updates-off-report-builder-and-ssrs"></a><span data-ttu-id="13ab0-102">Проверка наличия обновлений или отключение обновлений (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="13ab0-102">Check for Updates or Turn Updates Off (Report Builder and SSRS)</span></span>
  <span data-ttu-id="13ab0-103">При каждом открытии отчета построитель отчетов проверяет, не вносились ли на сервере или на сайте SharePoint, объединенном с сервером отчетов, изменения в опубликованные экземпляры элементов отчета в данном отчете.</span><span class="sxs-lookup"><span data-stu-id="13ab0-103">Every time you open a report, Report Builder checks to see if the published instances of report parts in that report have been updated on the report server or SharePoint site integrated with a report server.</span></span> <span data-ttu-id="13ab0-104">Построитель отчетов также проверяет элементы, зависящие от элементов отчетов, например наборы данных и параметры.</span><span class="sxs-lookup"><span data-stu-id="13ab0-104">It also checks for changes in the report parts' dependent items, such as the dataset and parameters.</span></span> <span data-ttu-id="13ab0-105">При обновлении элементов отчетов или их зависимостей на сайте или сервере в информационной панели отчета отображается количество обновленных элементов.</span><span class="sxs-lookup"><span data-stu-id="13ab0-105">If any report parts or their dependencies have been updated on the site or server, an information bar in your report displays the number of updated parts.</span></span> <span data-ttu-id="13ab0-106">Можно просмотреть и принять или отклонить изменения или отключить информационную панель.</span><span class="sxs-lookup"><span data-stu-id="13ab0-106">You can choose to view and accept or reject the updates, or dismiss the information bar.</span></span>  
  
 <span data-ttu-id="13ab0-107">Информационную панель можно также отключить, после чего пользователь не будет получать уведомления об изменении опубликованных экземпляров элементов отчетов.</span><span class="sxs-lookup"><span data-stu-id="13ab0-107">You can also disable the information bar and not be informed if published instances of report parts have changed.</span></span> <span data-ttu-id="13ab0-108">Это пользовательский параметр. Он будет отключен для всех отчетов, открываемых пользователем.</span><span class="sxs-lookup"><span data-stu-id="13ab0-108">This is a user setting; it will be disabled for all reports that you open.</span></span> <span data-ttu-id="13ab0-109">Даже после отключения информационной панели можно выполнять проверку наличия обновлений.</span><span class="sxs-lookup"><span data-stu-id="13ab0-109">Even if you have disabled the information bar, you can still check for updates.</span></span>  
  
### <a name="to-turn-on-and-off-report-part-updates"></a><span data-ttu-id="13ab0-110">Включение и выключение обновлений элементов отчетов</span><span class="sxs-lookup"><span data-stu-id="13ab0-110">To turn on and off report part updates</span></span>  
  
1.  <span data-ttu-id="13ab0-111">Нажмите кнопку построитель отчетов и выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="13ab0-111">Click the Report Builder button, and then click **Options**.</span></span>  
  
2.  <span data-ttu-id="13ab0-112">В диалоговом окне **Параметры** на вкладке **ресурсы** установите или снимите флажок **Показывать обновления для элементов отчета в папках "Мои отчеты** ".</span><span class="sxs-lookup"><span data-stu-id="13ab0-112">In the **Options** dialog box, on the **Resources** tab, select or clear the **Show updates to report parts in my reports** check box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="13ab0-113">Это пользовательский параметр.</span><span class="sxs-lookup"><span data-stu-id="13ab0-113">This is a user setting.</span></span> <span data-ttu-id="13ab0-114">Он будет отключен для всех отчетов, открываемых пользователем.</span><span class="sxs-lookup"><span data-stu-id="13ab0-114">It will be disabled for all reports that you open.</span></span>  
  
### <a name="to-check-for-updates"></a><span data-ttu-id="13ab0-115">Проверка обновлений</span><span class="sxs-lookup"><span data-stu-id="13ab0-115">To check for updates</span></span>  
  
-   <span data-ttu-id="13ab0-116">Щелкните правой кнопкой мыши область конструктора за пределами отчета или в тексте отчета и выберите пункт **проверить наличие обновлений**.</span><span class="sxs-lookup"><span data-stu-id="13ab0-116">Right-click the design surface outside the report, or in the report body, and click **Check for Updates**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ab0-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="13ab0-117">See Also</span></span>  
 <span data-ttu-id="13ab0-118">[Элементы отчета &#40;построитель отчетов и службы SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="13ab0-118">[Report Parts &#40;Report Builder and SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="13ab0-119">[Публикация и повторная публикация элементов отчетов &#40;построитель отчетов и SSRS&#41;](report-design/publish-and-republish-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="13ab0-119">[Publish and Republish Report Parts &#40;Report Builder and SSRS&#41;](report-design/publish-and-republish-report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="13ab0-120">[Поиск элементов отчета и задание папки по умолчанию &#40;построитель отчетов и SSRS&#41;](report-design/browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="13ab0-120">[Browse for Report Parts and Set a Default Folder &#40;Report Builder and SSRS&#41;](report-design/browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="13ab0-121">[Устранение неполадок элементов отчетов &#40;построитель отчетов и SSRS&#41;](../../2014/reporting-services/troubleshoot-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="13ab0-121">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](../../2014/reporting-services/troubleshoot-report-parts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="13ab0-122">Элементы отчета и наборы данных в построителе отчетов</span><span class="sxs-lookup"><span data-stu-id="13ab0-122">Report Parts and Datasets in Report Builder</span></span>](report-data/report-parts-and-datasets-in-report-builder.md)  
  
  
