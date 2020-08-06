---
title: Изменение элемента в ячейке (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 91a54778-8929-41f9-bb4c-826cec636be4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 80ef171713e6505867e00e343ce17b70cab9045a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751735"
---
# <a name="change-an-item-within-a-cell-report-builder-and-ssrs"></a><span data-ttu-id="7da22-102">Изменение элемента в ячейке (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="7da22-102">Change an Item Within a Cell (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7da22-103">Заменять новыми элементами отчета можно только элементы, не являющиеся контейнерами, например текстовые поля, линии и рисунки.</span><span class="sxs-lookup"><span data-stu-id="7da22-103">Only a non-container item, such as a text box, line, or image, can be replaced by a new report item.</span></span> <span data-ttu-id="7da22-104">Например, можно перетащить таблицу в текстовое поле, чтобы заменить его этой таблицей.</span><span class="sxs-lookup"><span data-stu-id="7da22-104">For example, you can drag a table into a text box to replace the text box with a table.</span></span>  
  
 <span data-ttu-id="7da22-105">Если ячейка содержит прямоугольник, список, таблицу или матрицу, то новый элемент добавляется в контейнер, а не заменяет его.</span><span class="sxs-lookup"><span data-stu-id="7da22-105">If the cell contains a container item such as a rectangle, list, table, or matrix, the new item is added to the containing item instead of replacing it.</span></span> <span data-ttu-id="7da22-106">Чтобы заменить элемент-контейнер новым элементом, вначале его необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="7da22-106">To replace a container item with a new item, delete the container.</span></span> <span data-ttu-id="7da22-107">В результате контейнер будет заменен текстовым полем, которое затем можно будет заменить другим элементом.</span><span class="sxs-lookup"><span data-stu-id="7da22-107">Deleting the container item replaces it with a text box, which you can then replace with another item.</span></span>  
  
 <span data-ttu-id="7da22-108">По умолчанию все ячейки области данных таблицы, матрицы и списка содержат текстовые поля.</span><span class="sxs-lookup"><span data-stu-id="7da22-108">By default, all cells in a table, matrix, or list data region contain a text box.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-an-item-within-a-cell"></a><span data-ttu-id="7da22-109">Изменение элемента в ячейке</span><span class="sxs-lookup"><span data-stu-id="7da22-109">To change an item within a cell</span></span>  
  
-   <span data-ttu-id="7da22-110">На вкладке **Вставка** в группе **Области данных** или **Элементы отчета** щелкните элемент, который требуется добавить в отчет, а затем щелкните отчет.</span><span class="sxs-lookup"><span data-stu-id="7da22-110">On the **Insert** tab, in the **Data Regions** or **Report Items** group, click the item that you want to add to the report, and then click the report.</span></span> <span data-ttu-id="7da22-111">Элемент будет добавлен в отчет.</span><span class="sxs-lookup"><span data-stu-id="7da22-111">The item is added to the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7da22-112">После перетаскивания в ячейку элемента отчета, представляющего собой изображение, открывается диалоговое окно **Свойства изображения** , позволяющее задавать такие свойства, как источник изображения, прежде чем изображение будет добавлено к ячейке.</span><span class="sxs-lookup"><span data-stu-id="7da22-112">The **Image Properties** dialog box opens when you drag an image report item to a cell, where you can set properties such as the source of the image before the image is added to the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7da22-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="7da22-113">See Also</span></span>  
 <span data-ttu-id="7da22-114">[Изображения, текстовые поля, прямоугольники и линии (построитель отчетов и службы SSRS)](rectangles-and-lines-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7da22-114">[Images, Text Boxes, Rectangles, and Lines &#40;Report Builder and SSRS&#41;](rectangles-and-lines-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7da22-115">Списки (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="7da22-115">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
