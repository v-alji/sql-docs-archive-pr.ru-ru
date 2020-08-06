---
title: Сохранение отчетов на компьютере (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 56d2d0d7-1eb6-4c6b-aaf4-0521723ef4af
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62a631c295b606e1c5b246e484d6a2e6df077e0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656987"
---
# <a name="save-reports-to-your-computer-report-builder"></a><span data-ttu-id="5827b-102">Сохранение отчетов на компьютере (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="5827b-102">Save Reports to Your Computer (Report Builder)</span></span>
  <span data-ttu-id="5827b-103">В построителе отчетов можно сохранить определения отчетов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5827b-103">In Report Builder, you can save a report definitions to your computer.</span></span> <span data-ttu-id="5827b-104">Однако если сохранить их на компьютере, то другие пользователи не смогут просматривать эти отчеты, а отчеты, которые ссылаются на общие источники данных или элементы которых (изображения, вложенные отчеты и т. п.) хранятся вне компьютера, могут не запустится.</span><span class="sxs-lookup"><span data-stu-id="5827b-104">However, when they are saved to your compute,r other users cannot view the reports and reports that reference shared data sources or store report items such as images and subreports externally might not run.</span></span> <span data-ttu-id="5827b-105">Рекомендуется сохранять отчеты на сервере отчетов или сайте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5827b-105">It is recommended that you save reports to a report server or SharePoint site.</span></span>  
  
### <a name="to-save-a-report"></a><span data-ttu-id="5827b-106">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="5827b-106">To save a report</span></span>  
  
1.  <span data-ttu-id="5827b-107">В построителе отчетов нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5827b-107">From the Report Builder button, click **Save**.</span></span> <span data-ttu-id="5827b-108">**Save As** _\<Report Item>_ Откроется диалоговое окно Сохранить как.</span><span class="sxs-lookup"><span data-stu-id="5827b-108">The **Save As**_\<Report Item>_ dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5827b-109">Во время повторного сохранения отчет автоматически сохраняется в предыдущем расположении.</span><span class="sxs-lookup"><span data-stu-id="5827b-109">If you are resaving a report, it is automatically resaved to its previous location.</span></span> <span data-ttu-id="5827b-110">Чтобы изменить расположение, используйте параметр **Сохранить как** .</span><span class="sxs-lookup"><span data-stu-id="5827b-110">Use the **Save As** option to change location.</span></span>  
  
2.  <span data-ttu-id="5827b-111">При необходимости щелкните **Рабочий стол**, **мои документы**или **Мой компьютер** , чтобы сохранить отчет в одной из этих папок.</span><span class="sxs-lookup"><span data-stu-id="5827b-111">Optionally, click **Desktop**, **My Documents**, or **My Computer** to save the report to one of those folders.</span></span>  
  
3.  <span data-ttu-id="5827b-112">Перейдите в папку компьютера, куда нужно сохранить отчет.</span><span class="sxs-lookup"><span data-stu-id="5827b-112">Browse to the location on your computer where you want to save the report.</span></span> <span data-ttu-id="5827b-113">В поле **Имя**введите имя отчета.</span><span class="sxs-lookup"><span data-stu-id="5827b-113">In **Name**, type the name of the report.</span></span>  
  
4.  <span data-ttu-id="5827b-114">В поле **Элементы типа**выберите тип сохраняемого элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="5827b-114">In **Items of type**, select the type of report item you are saving.</span></span> <span data-ttu-id="5827b-115">Для отчетов используется тип «Отчеты» (RDL).</span><span class="sxs-lookup"><span data-stu-id="5827b-115">The type for reports is Reports(\*.rdl).</span></span>  
  
### <a name="to-save-a-report-as-a-different-name"></a><span data-ttu-id="5827b-116">Сохранение отчета с другим именем</span><span class="sxs-lookup"><span data-stu-id="5827b-116">To save a report as a different name</span></span>  
  
1.  <span data-ttu-id="5827b-117">Нажмите кнопку «Построитель отчетов» и выберите **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="5827b-117">From the Report Builder button, click **Save As**.</span></span> <span data-ttu-id="5827b-118">**Save As** _\<Report Item>_ Откроется диалоговое окно Сохранить как.</span><span class="sxs-lookup"><span data-stu-id="5827b-118">The **Save As**_\<Report Item>_ dialog box opens.</span></span>  
  
2.  <span data-ttu-id="5827b-119">Перейдите в папку компьютера, куда нужно сохранить отчет.</span><span class="sxs-lookup"><span data-stu-id="5827b-119">Browse to the location on your computer where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="5827b-120">В поле **Имя**введите имя отчета.</span><span class="sxs-lookup"><span data-stu-id="5827b-120">In **Name**, type the name of the report.</span></span> <span data-ttu-id="5827b-121">При необходимости щелкните **Рабочий стол**, **мои документы**или **Мой компьютер** , чтобы сохранить отчет в одной из этих папок.</span><span class="sxs-lookup"><span data-stu-id="5827b-121">Optionally, click **Desktop**, **My Documents**, or **My Computer** to save the report to one of those folders.</span></span>  
  
4.  <span data-ttu-id="5827b-122">В поле **Элементы типа**выберите тип сохраняемого элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="5827b-122">In **Items of type**, select the type of report item you are saving.</span></span> <span data-ttu-id="5827b-123">Для отчетов используется тип «Отчеты» (RDL).</span><span class="sxs-lookup"><span data-stu-id="5827b-123">The type for reports is Reports(\*.rdl).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5827b-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="5827b-124">See Also</span></span>  
 <span data-ttu-id="5827b-125">[Поиск, просмотр отчетов и управление ими &#40;построитель отчетов и SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5827b-125">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5827b-126">[Экспорт отчетов &#40;построитель отчетов и SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5827b-126">[Exporting Reports &#40;Report Builder and SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5827b-127">[Сохранение отчетов &#40;построитель отчетов&#41;](report-builder/saving-reports-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="5827b-127">[Saving Reports &#40;Report Builder&#41;](report-builder/saving-reports-report-builder.md) </span></span>  
 [<span data-ttu-id="5827b-128">Экспорт отчета в файл другого типа (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="5827b-128">Export a Report as Another File Type &#40;Report Builder and SSRS&#41;</span></span>](../../2014/reporting-services/export-a-report-as-another-file-type-report-builder-and-ssrs.md)  
  
  
