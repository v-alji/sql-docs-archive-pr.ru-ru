---
title: Скрытие верхнего или нижнего колонтитула первой или последней страницы (построитель отчетов и SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f87ce79b-00d7-4458-a17e-e253a20f720d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 60c8789fd098df7347e9cc0f583426478aee06e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727958"
---
# <a name="hide-a-page-header-or-footer-on-the-first-or-last-page-report-builder-and-ssrs"></a><span data-ttu-id="46e20-102">Скрытие верхнего или нижнего колонтитула первой или последней страницы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="46e20-102">Hide a Page Header or Footer on the First or Last Page (Report Builder and SSRS)</span></span>
  <span data-ttu-id="46e20-103">Отчет может содержать верхний и нижний колонтитулы, которые располагаются в верхней и нижней части каждой страницы соответственно.</span><span class="sxs-lookup"><span data-stu-id="46e20-103">A report can contain a page header and page footer that run along the top and bottom of each page, respectively.</span></span> <span data-ttu-id="46e20-104">После добавления верхнего или нижнего колонтитула можно выборочно скрыть его на первой и последней странице отчета.</span><span class="sxs-lookup"><span data-stu-id="46e20-104">After you a add a header or footer, you can selectively hide it on the first and last pages of a report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-hide-a-page-header-on-the-first-or-last-page"></a><span data-ttu-id="46e20-105">Скрытие верхнего или нижнего колонтитула на первой или последней странице</span><span class="sxs-lookup"><span data-stu-id="46e20-105">To hide a page header on the first or last page</span></span>  
  
1.  <span data-ttu-id="46e20-106">Откройте отчет в режиме конструктора.</span><span class="sxs-lookup"><span data-stu-id="46e20-106">Open a report in Design view.</span></span>  
  
2.  <span data-ttu-id="46e20-107">Щелкните правой кнопкой мыши верхний колонтитул страницы, а затем выберите пункт **Свойства верхнего колонтитула**.</span><span class="sxs-lookup"><span data-stu-id="46e20-107">Right-click the page header, and then click **Header Properties**.</span></span> <span data-ttu-id="46e20-108">Откроется диалоговое окно **Свойства верхнего колонтитула отчета** .</span><span class="sxs-lookup"><span data-stu-id="46e20-108">The **Report Header Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="46e20-109">Убедитесь, что снят флажок **Показать верхний колонтитул для этого отчета** .</span><span class="sxs-lookup"><span data-stu-id="46e20-109">Verify that **Display header for this report** is not selected.</span></span>  
  
4.  <span data-ttu-id="46e20-110">В разделе **Параметры печати** снимите флажки параметров, чтобы скрыть соответствующие элементы на первой и последней страницах отчета.</span><span class="sxs-lookup"><span data-stu-id="46e20-110">In the **Print options** section, clear the check box for each option to hide the display on the first or last page of the report.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-hide-a-page-footer-on-the-first-or-last-page"></a><span data-ttu-id="46e20-111">Скрытие нижнего колонтитула на первой или последней странице</span><span class="sxs-lookup"><span data-stu-id="46e20-111">To hide a page footer on the first or last page</span></span>  
  
1.  <span data-ttu-id="46e20-112">Откройте отчет в режиме конструктора.</span><span class="sxs-lookup"><span data-stu-id="46e20-112">Open a report in Design view.</span></span>  
  
2.  <span data-ttu-id="46e20-113">Щелкните правой кнопкой мыши нижний колонтитул страницы, а затем выберите пункт **Свойства нижнего колонтитула**.</span><span class="sxs-lookup"><span data-stu-id="46e20-113">Right-click the page footer, and then click **Footer Properties**.</span></span> <span data-ttu-id="46e20-114">Откроется диалоговое окно **Свойства нижнего колонтитула отчета** .</span><span class="sxs-lookup"><span data-stu-id="46e20-114">The **Report Footer Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="46e20-115">Убедитесь, что снят флажок **Показать нижний колонтитул для этого отчета** .</span><span class="sxs-lookup"><span data-stu-id="46e20-115">Verify that **Display footer for this report** is not selected.</span></span>  
  
4.  <span data-ttu-id="46e20-116">В разделе **Параметры печати** снимите флажки параметров, чтобы скрыть соответствующие элементы на первой и последней страницах отчета.</span><span class="sxs-lookup"><span data-stu-id="46e20-116">In the **Print options** section, clear the check box for each option to hide the display on the first or last page of the report.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="46e20-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="46e20-117">See Also</span></span>  
 <span data-ttu-id="46e20-118">[Верхние и нижние колонтитулы страницы (построитель отчетов и службы SSRS)](page-headers-and-footers-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="46e20-118">[Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="46e20-119">[Разбиение на страницы в службах Reporting Services (построитель отчетов и службы SSRS)](pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="46e20-119">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="46e20-120">Добавление или удаление верхнего или нижнего колонтитула страницы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="46e20-120">Add or Remove a Page Header or Footer &#40;Report Builder and SSRS&#41;</span></span>](add-or-remove-a-page-header-or-footer-report-builder-and-ssrs.md)  
  
  
