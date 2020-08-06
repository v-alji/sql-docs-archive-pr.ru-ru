---
title: Добавление или удаление верхнего или нижнего колонтитула страницы (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 72988623-fee8-4a05-9f72-8fcb8e668576
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b29db3f72323c460360c872a0f60d13a808e3e05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735037"
---
# <a name="add-or-remove-a-page-header-or-footer-report-builder-and-ssrs"></a><span data-ttu-id="6623b-102">Добавление или удаление верхнего или нижнего колонтитула страницы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6623b-102">Add or Remove a Page Header or Footer (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6623b-103">К верхним или нижним колонтитулам страниц можно добавить статический текст, изображения, линии, прямоугольники и границы.</span><span class="sxs-lookup"><span data-stu-id="6623b-103">You can add static text, images, lines, rectangles, and borders to page headers or footers.</span></span> <span data-ttu-id="6623b-104">Если в заголовке или нижнем колонтитуле необходимо разместить переменные или вычисляемые данные, поместите выражения и связанные с данными изображения в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="6623b-104">You can place expressions and data-bound images in a textbox if you want variable or computed data in a header or footer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6623b-105">Всякий модуль подготовки отчетов обрабатывает колонтитулы по-разному.</span><span class="sxs-lookup"><span data-stu-id="6623b-105">Each rendering extension processes page headers and footers differently.</span></span> <span data-ttu-id="6623b-106">Дополнительные сведения см. в разделах [Верхние и нижние колонтитулы страницы (построитель отчетов и службы SSRS)](page-headers-and-footers-report-builder-and-ssrs.md) и [Разбиение на страницы в службах Reporting Services (построитель отчетов и службы SSRS)](pagination-in-reporting-services-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6623b-106">For more information, see [Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) and [Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-page-header-or-footer"></a><span data-ttu-id="6623b-107">Добавление верхнего или нижнего колонтитула</span><span class="sxs-lookup"><span data-stu-id="6623b-107">To add a page header or footer</span></span>  
  
1.  <span data-ttu-id="6623b-108">Откройте отчет.</span><span class="sxs-lookup"><span data-stu-id="6623b-108">Open a report.</span></span>  
  
2.  <span data-ttu-id="6623b-109">В области конструктора щелкните правой кнопкой мыши отчет, укажите пункт **Вставить**и выберите **Верхний колонтитул** или **Нижний колонтитул**.</span><span class="sxs-lookup"><span data-stu-id="6623b-109">On the design surface, right-click the report, point to **Insert**, and then click **Header** or **Footer**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6623b-110">Параметры **Верхний колонтитул** или **Нижний колонтитул** появляются, только если верхний или нижний колонтитул еще не являются частью отчета.</span><span class="sxs-lookup"><span data-stu-id="6623b-110">The **Header** and **Footer** options appear only when a header or footer is not already part of the report.</span></span>  
  
### <a name="to-configure-a-page-header-or-footer"></a><span data-ttu-id="6623b-111">Настройка верхнего или нижнего колонтитула</span><span class="sxs-lookup"><span data-stu-id="6623b-111">To configure a page header or footer</span></span>  
  
1.  <span data-ttu-id="6623b-112">В области конструктора щелкните правой кнопкой мыши верхний или нижний колонтитул.</span><span class="sxs-lookup"><span data-stu-id="6623b-112">On the design surface, right-click the page header or footer.</span></span>  
  
2.  <span data-ttu-id="6623b-113">Укажите пункт **Вставить**, а затем выберите один из следующих элементов, чтобы добавить его в область верхнего или нижнего колонтитула:</span><span class="sxs-lookup"><span data-stu-id="6623b-113">Point to **Insert**, and then click one of the following items to add it to the header or footer area:</span></span>  
  
    -   <span data-ttu-id="6623b-114">**текстовое поле;**</span><span class="sxs-lookup"><span data-stu-id="6623b-114">**Textbox**</span></span>  
  
    -   <span data-ttu-id="6623b-115">**Линия**</span><span class="sxs-lookup"><span data-stu-id="6623b-115">**Line**</span></span>  
  
    -   <span data-ttu-id="6623b-116">**прямоугольник;**</span><span class="sxs-lookup"><span data-stu-id="6623b-116">**Rectangle**</span></span>  
  
    -   <span data-ttu-id="6623b-117">**Изображение**</span><span class="sxs-lookup"><span data-stu-id="6623b-117">**Image**</span></span>  
  
3.  <span data-ttu-id="6623b-118">Щелкните правой кнопкой мыши верхний колонтитул и выберите пункт **Свойства верхнего колонтитула** , чтобы добавить границы, фоновое изображение и цвета либо настроить ширину верхнего колонтитула.</span><span class="sxs-lookup"><span data-stu-id="6623b-118">Right-click the page header, and then click **Header Properties** to add borders, background images, or colors, or to adjust the width of the header.</span></span> <span data-ttu-id="6623b-119">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6623b-119">Then click **OK**.</span></span>  
  
4.  <span data-ttu-id="6623b-120">Щелкните правой кнопкой мыши нижний колонтитул и выберите пункт **Свойства нижнего колонтитула** , чтобы добавить границы, фоновое изображение и цвета либо настроить ширину нижнего колонтитула.</span><span class="sxs-lookup"><span data-stu-id="6623b-120">Right-click the page footer, and then click **Footer Properties** to add borders, background images, or colors, or to adjust the width of the footer.</span></span> <span data-ttu-id="6623b-121">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6623b-121">Then click **OK**.</span></span>  
  
### <a name="to-remove-a-page-header-or-footer"></a><span data-ttu-id="6623b-122">Удаление верхнего или нижнего колонтитула</span><span class="sxs-lookup"><span data-stu-id="6623b-122">To remove a page header or footer</span></span>  
  
1.  <span data-ttu-id="6623b-123">Откройте отчет.</span><span class="sxs-lookup"><span data-stu-id="6623b-123">Open a report.</span></span>  
  
2.  <span data-ttu-id="6623b-124">В области конструктора щелкните правой кнопкой мыши верхний или нижний колонтитул и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="6623b-124">On the design surface, right-click the page header or footer, and then click **Delete**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6623b-125">При удалении колонтитула он удаляется из отчета.</span><span class="sxs-lookup"><span data-stu-id="6623b-125">When you remove a page header or footer, you delete it from the report.</span></span> <span data-ttu-id="6623b-126">Любые элементы, которые ранее добавлялись в колонтитулы, не появятся после последующего создания колонтитула.</span><span class="sxs-lookup"><span data-stu-id="6623b-126">Any items that you previously added to the page header or footer will not reappear if you subsequently add the header or footer again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6623b-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="6623b-127">See Also</span></span>  
 [<span data-ttu-id="6623b-128">Верхние и нижние колонтитулы страницы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6623b-128">Page Headers and Footers &#40;Report Builder and SSRS&#41;</span></span>](page-headers-and-footers-report-builder-and-ssrs.md)  
  
  
