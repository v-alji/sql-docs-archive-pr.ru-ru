---
title: Добавление в отчет границы (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 81412f94-2991-4e58-bc05-5ccc0cbf2a75
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf4a0c2c117774a0f3b25ca0644796fd067bc971
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739380"
---
# <a name="add-a-border-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="579c8-102">Добавление в отчет границы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="579c8-102">Add a Border to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="579c8-103">Можно добавить границу к отчету путем добавления границ к самим верхним колонтитулам, нижним колонтитулам и тексту отчета, не добавляя линии или прямоугольники.</span><span class="sxs-lookup"><span data-stu-id="579c8-103">You can add a border to a report by adding borders to the headers, footers, and report body themselves, without adding lines or rectangles.</span></span>  
  
 <span data-ttu-id="579c8-104">При добавлении границы отчета, которая появляется на колонтитулах страницы, не нужно отключать колонтитулы на первой и последней страницах отчета.</span><span class="sxs-lookup"><span data-stu-id="579c8-104">If you add a report border that appears on the page header and footer, do not suppress the header and footer on the first and last pages of the report.</span></span> <span data-ttu-id="579c8-105">Если это сделать, граница может выглядеть обрезанной в верхней или нижней части первой и последней страниц отчета.</span><span class="sxs-lookup"><span data-stu-id="579c8-105">If you do, the border may appear cut off at the top or bottom of the first and last pages of the report.</span></span> <span data-ttu-id="579c8-106">Дополнительные сведения см. в разделе [Верхние и нижние колонтитулы страницы (построитель отчетов и службы SSRS)](page-headers-and-footers-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="579c8-106">For more information, see [Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-border-to-a-report"></a><span data-ttu-id="579c8-107">Добавление границы в отчет</span><span class="sxs-lookup"><span data-stu-id="579c8-107">To add a border to a report</span></span>  
  
1.  <span data-ttu-id="579c8-108">Щелкните правой кнопкой мыши верхний колонтитул за пределами его элементов и выберите пункт **Свойства верхнего колонтитула**.</span><span class="sxs-lookup"><span data-stu-id="579c8-108">Right-click in the header outside any items in the header, and click **Header Properties**.</span></span> <span data-ttu-id="579c8-109">На вкладке **Граница** добавьте левую, верхнюю и правую границу с нужным стилем.</span><span class="sxs-lookup"><span data-stu-id="579c8-109">On the **Border** tab, add a left, top, and right border with the style you want.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="579c8-110">Если в отчете не используются верхние колонтитулы, можно поместить границы вокруг текста отчета или добавить заголовки с вкладки **Вставка** .</span><span class="sxs-lookup"><span data-stu-id="579c8-110">If you do not use headers in your report, you can place borders around just the report body, or you can add headers from the **Insert** tab.</span></span>  
  
2.  <span data-ttu-id="579c8-111">Щелкните правой кнопкой мыши текст отчета за пределами элементов области конструктора и выберите пункт **Свойства текста**.</span><span class="sxs-lookup"><span data-stu-id="579c8-111">Right-click in the body outside any items on the design surface, and click **Body Properties**.</span></span> <span data-ttu-id="579c8-112">На вкладке **Граница** добавьте левую и правую границу с нужным стилем.</span><span class="sxs-lookup"><span data-stu-id="579c8-112">On the **Border** tab, add a left and right border with the style you want.</span></span>  
  
3.  <span data-ttu-id="579c8-113">Щелкните правой кнопкой мыши нижний колонтитул за пределами его элементов и выберите пункт **Свойства нижнего колонтитула**.</span><span class="sxs-lookup"><span data-stu-id="579c8-113">Right-click in the footer outside any items in the footer, and click **Footer Properties**.</span></span> <span data-ttu-id="579c8-114">На вкладке **Граница** добавьте левую, нижнюю и правую границу с нужным стилем.</span><span class="sxs-lookup"><span data-stu-id="579c8-114">On the **Border** tab, add a left, bottom, and right border with the style you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="579c8-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="579c8-115">See Also</span></span>  
 [<span data-ttu-id="579c8-116">Прямоугольники и линии (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="579c8-116">Rectangles and Lines &#40;Report Builder and SSRS&#41;</span></span>](rectangles-and-lines-report-builder-and-ssrs.md)  
  
  
