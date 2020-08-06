---
title: Диалоговые окна «Создание связи атрибутов» и «изменение связи атрибутов» (вкладка «Конструктор связей атрибутов», конструктор измерений) (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.ardesigner.createrelationshipdialog.f1
ms.assetid: cb3bc7d8-9d4d-4da9-979d-bdad5e27e526
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7e720d31803057156c9b465f3e932bc734d03631
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656706"
---
# <a name="create-attribute-relationship-and-edit-attribute-relationship-dialog-boxes-attribute-relationship-designer-tab-dimension-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="3d9d7-102">Диалоговые окна «Создание связи атрибутов» и «Изменение связи атрибутов» (вкладка «Конструктор связей», конструктор измерений) (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="3d9d7-102">Create Attribute Relationship and Edit Attribute Relationship Dialog Boxes (Attribute Relationship Designer Tab, Dimension Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="3d9d7-103">Диалоговое окно **Создание связи атрибутов** используется, чтобы определить новые связи атрибутов, а диалоговое окно **Изменение связи атрибутов** — чтобы изменить связь атрибутов.</span><span class="sxs-lookup"><span data-stu-id="3d9d7-103">Use the **Create Attribute Relationship** dialog box to define new attribute relationships and the **Edit Attribute Relationship** dialog box to change an attribute relationship.</span></span> <span data-ttu-id="3d9d7-104">Дополнительные сведения см. в разделе [Определение связей атрибутов](multidimensional-models/attribute-relationships-define.md).</span><span class="sxs-lookup"><span data-stu-id="3d9d7-104">For more information, see [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md).</span></span>  
  
 <span data-ttu-id="3d9d7-105">**Открытие диалогового окна «Создание связи атрибутов»**</span><span class="sxs-lookup"><span data-stu-id="3d9d7-105">**To view the Create Attribute Relationship dialog box**</span></span>  
  
1.  <span data-ttu-id="3d9d7-106">В обозревателе решений в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]дважды щелкните измерение, чтобы открыть конструктор измерений, а затем перейдите на вкладку **Связь атрибутов** .</span><span class="sxs-lookup"><span data-stu-id="3d9d7-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, double-click a dimension to open the Dimension Designer, and then click the **Attribute Relationship** tab.</span></span>  
  
2.  <span data-ttu-id="3d9d7-107">Щелкните значок «Создать связь атрибутов» на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="3d9d7-107">On the toolbar, click the New Attribute Relationship icon.</span></span>  
  
     <span data-ttu-id="3d9d7-108">-или-</span><span class="sxs-lookup"><span data-stu-id="3d9d7-108">-or-</span></span>  
  
     <span data-ttu-id="3d9d7-109">На диаграмме связей атрибутов или списке **Атрибуты** щелкните атрибут правой кнопкой мыши, а затем выберите пункт **Создать связь атрибутов**.</span><span class="sxs-lookup"><span data-stu-id="3d9d7-109">In the attribute relationship diagram or **Attributes** list, right-click an attribute, and then click **New Attribute Relationship**.</span></span>  
  
 <span data-ttu-id="3d9d7-110">**Открытие диалогового окна «Изменение связи атрибутов»**</span><span class="sxs-lookup"><span data-stu-id="3d9d7-110">**To view the Edit Attribute Relationship dialog box**</span></span>  
  
1.  <span data-ttu-id="3d9d7-111">В обозревателе решений в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]дважды щелкните измерение, чтобы открыть конструктор измерений, а затем перейдите на вкладку **Связь атрибутов** .</span><span class="sxs-lookup"><span data-stu-id="3d9d7-111">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, double-click a dimension to open the Dimension Designer, and then click the **Attribute Relationship** tab.</span></span>  
  
2.  <span data-ttu-id="3d9d7-112">На диаграмме связей атрибутов или списке **Связи атрибутов** щелкните атрибут правой кнопкой мыши, а затем выберите пункт **Изменить связь атрибутов**.</span><span class="sxs-lookup"><span data-stu-id="3d9d7-112">In the attribute relationship diagram or **Attribute Relationships** list, right-click an attribute relationship, and then click **Edit Attribute Relationship**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3d9d7-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d9d7-113">Options</span></span>  
 <span data-ttu-id="3d9d7-114">**имя**;</span><span class="sxs-lookup"><span data-stu-id="3d9d7-114">**Name**</span></span>  
 <span data-ttu-id="3d9d7-115">В группе **Исходный атрибут** указывается имя атрибута, от которого исходит связь.</span><span class="sxs-lookup"><span data-stu-id="3d9d7-115">In the **Source Attribute** group, specifies the name of the attribute from which the relationship originates.</span></span>  
  
 <span data-ttu-id="3d9d7-116">В группе **Связанный атрибут** указывается имя атрибута, на который направлена связь.</span><span class="sxs-lookup"><span data-stu-id="3d9d7-116">In the **Related Attribute** group, specifies the name of the attribute to which the relationship is directed.</span></span>  
  
 <span data-ttu-id="3d9d7-117">**Число элементов**</span><span class="sxs-lookup"><span data-stu-id="3d9d7-117">**Member Count**</span></span>  
 <span data-ttu-id="3d9d7-118">Указывает предполагаемое количество элементов указанного атрибута.</span><span class="sxs-lookup"><span data-stu-id="3d9d7-118">Specifies the estimated number of members of the specified attribute.</span></span>  
  
 <span data-ttu-id="3d9d7-119">**Ключевые столбцы**</span><span class="sxs-lookup"><span data-stu-id="3d9d7-119">**Key Columns**</span></span>  
 <span data-ttu-id="3d9d7-120">Указывает ключевые столбцы, определенные для атрибута.</span><span class="sxs-lookup"><span data-stu-id="3d9d7-120">Specifies the key columns that are defined for the attribute.</span></span>  
  
 <span data-ttu-id="3d9d7-121">**Тип отношений**</span><span class="sxs-lookup"><span data-stu-id="3d9d7-121">**Relationship type**</span></span>  
 <span data-ttu-id="3d9d7-122">Указывает тип создаваемой связи — **гибкая (может изменяться со временем)** или **жесткая (не изменяется со временем)**.</span><span class="sxs-lookup"><span data-stu-id="3d9d7-122">Specifies the type of relationship to create, either **Flexible (may change over time)** or **Rigid (will not change over time)**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d9d7-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="3d9d7-123">See Also</span></span>  
 [<span data-ttu-id="3d9d7-124">Связи атрибутов &#40;конструктор измерений&#41; &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="3d9d7-124">Attribute Relationships &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](attribute-relationships-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
