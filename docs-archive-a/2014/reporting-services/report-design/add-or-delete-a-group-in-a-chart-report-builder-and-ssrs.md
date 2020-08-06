---
title: Добавление или удаление группы в диаграмме (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0445b0ac-acae-4462-80fb-fe9735ac66db
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2ac558ccbd8855018877228b2b38debf769f1573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739344"
---
# <a name="add-or-delete-a-group-in-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="d901f-102">Добавление или удаление группы в диаграмме (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d901f-102">Add or Delete a Group in a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d901f-103">Щелкните в диаграммной области данных, чтобы отобразить панель **Данные диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="d901f-103">Click in the chart data region to display the **Chart Data** pane.</span></span> <span data-ttu-id="d901f-104">Создайте группы, перетащив поля набора данных в области **Группы категорий** и **Группы рядов** .</span><span class="sxs-lookup"><span data-stu-id="d901f-104">Create groups by dragging dataset fields to the **Category Groups** and **Series Groups** areas.</span></span> <span data-ttu-id="d901f-105">Чтобы добавить вложенные группы, в область добавляют несколько полей.</span><span class="sxs-lookup"><span data-stu-id="d901f-105">To add nested groups, add multiple fields to the area.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-parent-or-child-group-to-a-chart"></a><span data-ttu-id="d901f-106">Добавление дочерней или родительской группы к диаграмме</span><span class="sxs-lookup"><span data-stu-id="d901f-106">To add a parent or child group to a chart</span></span>  
  
1.  <span data-ttu-id="d901f-107">В области конструктора щелкните в любом месте диаграммы, чтобы ее выбрать.</span><span class="sxs-lookup"><span data-stu-id="d901f-107">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="d901f-108">Отображается панель **Данные диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="d901f-108">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="d901f-109">Перетащите поле из окна **Данные отчета** в область **Группы категорий** или **Группы рядов** .</span><span class="sxs-lookup"><span data-stu-id="d901f-109">Drag a field from the **Report Data** window to the **Category Groups** or **Series Groups** area.</span></span> <span data-ttu-id="d901f-110">Для добавления родительской группы поместите курсор перед существующей группой.</span><span class="sxs-lookup"><span data-stu-id="d901f-110">To add a parent group, position the cursor in front of an existing group.</span></span> <span data-ttu-id="d901f-111">Для добавления дочерней группы поместите курсор после существующей группы.</span><span class="sxs-lookup"><span data-stu-id="d901f-111">To add a child group, position the cursor after an existing group.</span></span>  
  
### <a name="to-edit-a-category-group-on-a-chart"></a><span data-ttu-id="d901f-112">Изменение группы категорий в диаграмме</span><span class="sxs-lookup"><span data-stu-id="d901f-112">To edit a category group on a chart</span></span>  
  
1.  <span data-ttu-id="d901f-113">В области конструктора щелкните в любом месте диаграммы, чтобы ее выбрать.</span><span class="sxs-lookup"><span data-stu-id="d901f-113">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="d901f-114">Отображается панель **Данные диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="d901f-114">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="d901f-115">Правой кнопкой мыши щелкните группу в области **Группы категорий** и выберите пункт **Свойства группы категорий**.</span><span class="sxs-lookup"><span data-stu-id="d901f-115">Right-click the group in the **Category Groups** area, and then click **Category Group Properties**.</span></span>  
  
3.  <span data-ttu-id="d901f-116">Добавьте или удалите выражения группы, фильтры, выражения сортировки и групповые переменные.</span><span class="sxs-lookup"><span data-stu-id="d901f-116">Add or remove group expressions, filters, sort expressions, and group variables.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-edit-a-series-group-on-a-chart"></a><span data-ttu-id="d901f-117">Изменение группы рядов в диаграмме</span><span class="sxs-lookup"><span data-stu-id="d901f-117">To edit a series group on a chart</span></span>  
  
1.  <span data-ttu-id="d901f-118">В области конструктора щелкните в любом месте диаграммы, чтобы ее выбрать.</span><span class="sxs-lookup"><span data-stu-id="d901f-118">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="d901f-119">Отображается панель **Данные диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="d901f-119">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="d901f-120">Щелкните правой кнопкой мыши группу в области **Группы рядов** и выберите пункт **Свойства группы рядов**.</span><span class="sxs-lookup"><span data-stu-id="d901f-120">Right-click the group in the **Series Groups** area, and then click **Series Group Properties**.</span></span>  
  
3.  <span data-ttu-id="d901f-121">Добавьте или удалите выражения группы, фильтры, выражения сортировки и групповые переменные.</span><span class="sxs-lookup"><span data-stu-id="d901f-121">Add or remove group expressions, filters, sort expressions, and group variables.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-group-from-a-chart"></a><span data-ttu-id="d901f-122">Удаление группы из диаграммы</span><span class="sxs-lookup"><span data-stu-id="d901f-122">To delete a group from a chart</span></span>  
  
1.  <span data-ttu-id="d901f-123">В области конструктора щелкните в любом месте диаграммы, чтобы ее выбрать.</span><span class="sxs-lookup"><span data-stu-id="d901f-123">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="d901f-124">Отображается панель **Данные диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="d901f-124">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="d901f-125">Щелкните правой кнопкой мыши группу в области **Группы категорий** или **Группы рядов** и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d901f-125">Right-click the group in the **Category Groups** or **Series Groups** area, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d901f-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="d901f-126">See Also</span></span>  
 [<span data-ttu-id="d901f-127">Диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d901f-127">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
