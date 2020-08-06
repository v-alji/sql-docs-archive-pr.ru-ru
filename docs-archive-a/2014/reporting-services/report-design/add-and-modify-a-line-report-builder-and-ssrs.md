---
title: Добавление и изменение линии (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8dc4998b-a214-49b6-96e7-fbc179015209
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f7508cc45bf2a5fcb8bafde95ae2fa52a3317ef4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729050"
---
# <a name="add-and-modify-a-line-report-builder-and-ssrs"></a><span data-ttu-id="0695f-102">Добавление и изменение линии (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="0695f-102">Add and Modify a Line (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0695f-103">Если нужно отделить разделы отчета каким-либо графическим элементом, можно добавить в отчет линию.</span><span class="sxs-lookup"><span data-stu-id="0695f-103">You can add a line to your report when you want a graphical element to separate sections of the report.</span></span> <span data-ttu-id="0695f-104">Настроить внешний вид линии можно, изменяя ее свойства, такие как цвет или стиль.</span><span class="sxs-lookup"><span data-stu-id="0695f-104">You can customize the appearance of the line by editing line properties such as color or style.</span></span> <span data-ttu-id="0695f-105">Например, можно встроить в отчет корпоративные цвета компании.</span><span class="sxs-lookup"><span data-stu-id="0695f-105">For example, you might want to incorporate company colors into the report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-line"></a><span data-ttu-id="0695f-106">Добавление линии</span><span class="sxs-lookup"><span data-stu-id="0695f-106">To add a line</span></span>  
  
1.  <span data-ttu-id="0695f-107">На вкладке **Вставка** щелкните **Линия**.</span><span class="sxs-lookup"><span data-stu-id="0695f-107">On the **Insert** tab, click **Line**.</span></span>  
  
2.  <span data-ttu-id="0695f-108">В области конструктора щелкните место, где должен находиться один конец линии, затем щелкните место, где должен находиться другой ее конец.</span><span class="sxs-lookup"><span data-stu-id="0695f-108">On the design surface, click where you want one end of the line, and then click where you want the other end.</span></span>  
  
     <span data-ttu-id="0695f-109">Обратите внимание, что при перемещении конца линии появляются «линии привязки», если ее конец выравнивается с другим объектом в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="0695f-109">Note that as you move the end of the line, "snap lines" appear as the end lines up with other objects on the design surface.</span></span> <span data-ttu-id="0695f-110">Это облегчает выравнивание объектов.</span><span class="sxs-lookup"><span data-stu-id="0695f-110">These help you if you want objects to be aligned.</span></span>  
  
3.  <span data-ttu-id="0695f-111">Для изменения свойств линии выберите ее в области конструктора и измените свойства в разделе **Граница** вкладки **Корневая папка** .</span><span class="sxs-lookup"><span data-stu-id="0695f-111">To change the line properties, select the line on the design surface and then edit its properties in the **Border** section of the **Home** tab.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0695f-112">Если для стиля линии задано значение **Double** , а ширина линии — 1 1/2 пт или более, то при запуске отчета в построитель отчетов, конструктор отчетов или диспетчер отчетов строка может не отображаться двойной.</span><span class="sxs-lookup"><span data-stu-id="0695f-112">If you set the line style to **Double** and the line width is 1 1/2 pt or narrower, the line may not appear double when you run the report in Report Builder, Report Designer, or Report Manager.</span></span> <span data-ttu-id="0695f-113">После экспорта отчета в другие форматы, такие как Microsoft Word и Acrobat PDF, линия будет отображаться двойной.</span><span class="sxs-lookup"><span data-stu-id="0695f-113">It will appear double when you export the report to other formats such as Microsoft Word and Acrobat PDF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0695f-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="0695f-114">See Also</span></span>  
 [<span data-ttu-id="0695f-115">Прямоугольники и линии (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="0695f-115">Rectangles and Lines &#40;Report Builder and SSRS&#41;</span></span>](rectangles-and-lines-report-builder-and-ssrs.md)  
  
  
