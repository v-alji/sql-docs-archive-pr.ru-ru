---
title: Добавление группы подробных сведений (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ef8efba-6d48-4aeb-a3b9-a02ba5a44614
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 24b1f6af1aaf336a69a0068636ced60c364e556d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663990"
---
# <a name="add-a-details-group-report-builder-and-ssrs"></a><span data-ttu-id="6145f-102">Добавление группы подробных сведений (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6145f-102">Add a Details Group (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6145f-103">Подробные данные из набора данных отчета указываются в виде группы, не содержащей выражение группы.</span><span class="sxs-lookup"><span data-stu-id="6145f-103">The detail data from a report dataset is specified as a group with no group expression.</span></span> <span data-ttu-id="6145f-104">Если необходимо отобразить подробные данные для матрицы, вернуть подробные данные, удаленные из таблицы или списка, или добавить дополнительные группы сведений, то следует добавить дополнительную группу сведений к существующей области данных табликса.</span><span class="sxs-lookup"><span data-stu-id="6145f-104">Add a detail group to an existing tablix data region when you want to display the detail data for a matrix, add back detail data that you have deleted from a table or list, or to add additional detail groups.</span></span> <span data-ttu-id="6145f-105">Дополнительные сведения о группах см. в разделе [Основные сведения о группах (построитель отчетов и службы SSRS)](understanding-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6145f-105">For more information about groups, see [Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-details-group-to-a-tablix-data-region"></a><span data-ttu-id="6145f-106">Добавление группы сведений к области данных табликса</span><span class="sxs-lookup"><span data-stu-id="6145f-106">To add a details group to a tablix data region</span></span>  
  
1.  <span data-ttu-id="6145f-107">В области конструктора щелкните в любом месте области данных табликса, чтобы выделить ее.</span><span class="sxs-lookup"><span data-stu-id="6145f-107">On the design surface, click anywhere in a tablix data region to select it.</span></span> <span data-ttu-id="6145f-108">В панели группирования будут отображены группы столбцов и строк для выбранной области данных.</span><span class="sxs-lookup"><span data-stu-id="6145f-108">The Grouping pane displays the row and column groups for the selected data region.</span></span>  
  
2.  <span data-ttu-id="6145f-109">В панели «Группирование» щелкните правой кнопкой мыши самую внутреннюю дочернюю группу.</span><span class="sxs-lookup"><span data-stu-id="6145f-109">In the Grouping pane, right-click a group that is an innermost child group.</span></span> <span data-ttu-id="6145f-110">Нажмите **Добавить группу**и выберите **Дочерняя группа**.</span><span class="sxs-lookup"><span data-stu-id="6145f-110">Click **Add Group**, and then click **Child Group**.</span></span> <span data-ttu-id="6145f-111">Откроется диалоговое окно **Группа табликсов** .</span><span class="sxs-lookup"><span data-stu-id="6145f-111">The **Tablix Group** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="6145f-112">Оставьте поле **Выражение группы**пустым.</span><span class="sxs-lookup"><span data-stu-id="6145f-112">In **Group expression**, leave the expression blank.</span></span> <span data-ttu-id="6145f-113">Группа подробностей не имеет выражения.</span><span class="sxs-lookup"><span data-stu-id="6145f-113">A details group has no expression.</span></span>  
  
4.  <span data-ttu-id="6145f-114">Выберите **Показать подробные данные**.</span><span class="sxs-lookup"><span data-stu-id="6145f-114">Select **Show detail data**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="6145f-115">Новая группа подробностей добавляется в панель «Группирование» в виде дочерней группы, и маркер строки для группы, выбранной в шаге 1, отображает значок группы подробностей.</span><span class="sxs-lookup"><span data-stu-id="6145f-115">A new details group is added as a child group in the Grouping pane, and the row handle for the group you selected in step 1 displays the details group icon.</span></span> <span data-ttu-id="6145f-116">Дополнительные сведения о маркерах см. в разделе [Ячейки, строки и столбцы области данных табликса &#40;построитель отчетов&#41; и службы SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6145f-116">For more information about handles, see [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6145f-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="6145f-117">See Also</span></span>  
 <span data-ttu-id="6145f-118">[Добавление или удаление группы в области данных (построитель отчетов и службы SSRS)](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6145f-118">[Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6145f-119">[Основные сведения о группах (построитель отчетов и службы SSRS)](understanding-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6145f-119">[Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6145f-120">[Область данных табликса (построитель отчетов и службы SSRS)](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6145f-120">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6145f-121">[Таблицы &#40;построитель отчетов и службы SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6145f-121">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6145f-122">[Матрицы &#40;построитель отчетов и службы SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6145f-122">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6145f-123">[Содержит &#40;построитель отчетов и SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6145f-123">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6145f-124">Таблицы, матрицы и списки (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6145f-124">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
