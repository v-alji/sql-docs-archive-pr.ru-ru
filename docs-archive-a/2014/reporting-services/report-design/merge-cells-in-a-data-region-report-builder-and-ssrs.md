---
title: Объединение ячеек в области данных (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 43551300-89b2-4f4e-af09-69084324afaf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c69ce8182bda3e0b644893e97b69280a003f5732
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735010"
---
# <a name="merge-cells-in-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="04730-102">Объединение ячеек в области данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="04730-102">Merge Cells in a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="04730-103">Можно объединить ячейки в области данных, чтобы соединить их, улучшить внешний вид области данных или сформировать метки для групп столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="04730-103">You can merge cells in a data region to combine cells, improve data region appearance, or provide spanning labels for column groups and row groups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04730-104">Объединить можно только ячейки в пределах одной области в области данных: угла, заголовка столбца, определения (или заголовка) группы и текста отчета.</span><span class="sxs-lookup"><span data-stu-id="04730-104">Cells can only be merged within each area of a data region: corner, column headers, group definition (or row headers), and body.</span></span> <span data-ttu-id="04730-105">Ячейки, относящиеся к разным областям, объединить нельзя.</span><span class="sxs-lookup"><span data-stu-id="04730-105">You cannot merge cells that cross area boundaries.</span></span> <span data-ttu-id="04730-106">Например, нельзя объединить ячейку из угловой области в области данных с ячейкой из области группы строк.</span><span class="sxs-lookup"><span data-stu-id="04730-106">For example, you cannot merge a cell in the data region corner area with a cell in the row group area.</span></span> <span data-ttu-id="04730-107">Дополнительные сведения об областях табликса см. в разделе [lists &#40;построитель отчетов and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="04730-107">For more information about tablix areas, see [Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-merge-cells-in-a-data-region"></a><span data-ttu-id="04730-108">Объединение ячеек в области данных</span><span class="sxs-lookup"><span data-stu-id="04730-108">To merge cells in a data region</span></span>  
  
1.  <span data-ttu-id="04730-109">В области данных конструктора отчета щелкните первую ячейку для объединения.</span><span class="sxs-lookup"><span data-stu-id="04730-109">In the data region on the report design surface, click the first cell to merge.</span></span> <span data-ttu-id="04730-110">Удерживая нажатой левую кнопку мыши, перетащите курсор вертикально или горизонтально, чтобы выбрать смежные ячейки.</span><span class="sxs-lookup"><span data-stu-id="04730-110">Holding the left mouse button down, drag vertically or horizontally to select adjacent cells.</span></span> <span data-ttu-id="04730-111">Выбранные ячейки будут выделены.</span><span class="sxs-lookup"><span data-stu-id="04730-111">The selected cells are highlighted.</span></span>  
  
2.  <span data-ttu-id="04730-112">Щелкните выбранные ячейки правой кнопкой мыши и выберите команду **Объединить ячейки**.</span><span class="sxs-lookup"><span data-stu-id="04730-112">Right-click the selected cells and select **Merge Cells**.</span></span> <span data-ttu-id="04730-113">Выбранные ячейки будут объединены в одну.</span><span class="sxs-lookup"><span data-stu-id="04730-113">The selected cells are combined into a single cell.</span></span>  
  
3.  <span data-ttu-id="04730-114">Повторяйте шаги 1 и 2, чтобы объединить другие смежные ячейки в области данных.</span><span class="sxs-lookup"><span data-stu-id="04730-114">Repeat steps 1 and 2 to merge other adjacent cells in a data region.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04730-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="04730-115">See Also</span></span>  
 <span data-ttu-id="04730-116">[Область данных табликса &#40;построитель отчетов и SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="04730-116">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="04730-117">[Таблицы &#40;построитель отчетов и службы SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="04730-117">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="04730-118">[Матрицы &#40;построитель отчетов и службы SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="04730-118">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="04730-119">[Содержит &#40;построитель отчетов и SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="04730-119">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="04730-120">Списки (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="04730-120">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
