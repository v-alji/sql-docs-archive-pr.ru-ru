---
title: Предупреждения (конструктор баз данных) (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.databasedesigner.warnings.f1
ms.assetid: 13f58b4d-f345-4fbc-ae2d-b3c8290a797d
author: minewiskan
ms.author: owend
ms.openlocfilehash: bf635460187fe56f4811de5090cada002ea8ca3b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657905"
---
# <a name="warnings-database-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="2f09f-102">Предупреждения (конструктор баз данных) (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="2f09f-102">Warnings (Database Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="2f09f-103">Чтобы просмотреть и отклонить правила глобально, а также просмотреть и повторно включить конкретные экземпляры отклоненных предупреждений, используется вкладка **Предупреждения** .</span><span class="sxs-lookup"><span data-stu-id="2f09f-103">Use the **Warnings** tab to view and dismiss rules globally, and to view and re-enable specific instances of dismissed warnings.</span></span> <span data-ttu-id="2f09f-104">На вкладке **Предупреждения** отображаются две сетки: **Правила предупреждений конструктора** и **Отключенные предупреждения**.</span><span class="sxs-lookup"><span data-stu-id="2f09f-104">The **Warnings** tab displays two grids: **Design Warning Rules** and **Dismissed Warnings**.</span></span>  
  
 <span data-ttu-id="2f09f-105">**Отображение вкладки «Предупреждения»**</span><span class="sxs-lookup"><span data-stu-id="2f09f-105">**To display the Warnings tab**</span></span>  
  
1.  <span data-ttu-id="2f09f-106">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f09f-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="2f09f-107">В **обозревателе решений**щелкните правой кнопкой мыши проект служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , выберите команду **Изменить базу данных**, а затем перейдите на вкладку **Предупреждения** .</span><span class="sxs-lookup"><span data-stu-id="2f09f-107">In **Solution Explorer**, right-click the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, click **Edit Database**, and then click the **Warnings** tab.</span></span>  
  
## <a name="design-warning-rules-grid"></a><span data-ttu-id="2f09f-108">Сетка «Правила предупреждений конструктора»</span><span class="sxs-lookup"><span data-stu-id="2f09f-108">Design Warning Rules Grid</span></span>  
 <span data-ttu-id="2f09f-109">В сетке **Правила предупреждений конструктора** отображаются все правила предупреждений конструктора.</span><span class="sxs-lookup"><span data-stu-id="2f09f-109">The **Design Warning Rules** grid displays all the design warning rules.</span></span> <span data-ttu-id="2f09f-110">Эта сетка также управляет правилами, которые включены в базу данных.</span><span class="sxs-lookup"><span data-stu-id="2f09f-110">This grid also controls which rules are enabled for the database.</span></span> <span data-ttu-id="2f09f-111">Чтобы включить или выключить правило предупреждения, установите или снимите флажок.</span><span class="sxs-lookup"><span data-stu-id="2f09f-111">To enable or disable a warning rule, select or clear its check box.</span></span>  
  
 <span data-ttu-id="2f09f-112">В сетке **Правила предупреждений конструктора** имеются следующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="2f09f-112">The **Design Warning Rules** grid has the following columns:</span></span>  
  
 <span data-ttu-id="2f09f-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2f09f-113">**Description**</span></span>  
 <span data-ttu-id="2f09f-114">Отображает имя правила.</span><span class="sxs-lookup"><span data-stu-id="2f09f-114">Displays the name of the rule.</span></span> <span data-ttu-id="2f09f-115">Правила группируются по категориям.</span><span class="sxs-lookup"><span data-stu-id="2f09f-115">Rules are grouped by category.</span></span>  
  
 <span data-ttu-id="2f09f-116">**Важность**</span><span class="sxs-lookup"><span data-stu-id="2f09f-116">**Importance**</span></span>  
 <span data-ttu-id="2f09f-117">Отображает уровень важности, назначенный правилу.</span><span class="sxs-lookup"><span data-stu-id="2f09f-117">Displays the importance assigned to the rule.</span></span>  
  
 <span data-ttu-id="2f09f-118">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="2f09f-118">**Comments**</span></span>  
 <span data-ttu-id="2f09f-119">Позволяет пользователю ввести комментарий, который объясняет, почему отключено предупреждение (необязательно).</span><span class="sxs-lookup"><span data-stu-id="2f09f-119">(Optional) Allows the user to type a comment that explains why you are dismissing the warning.</span></span>  
  
## <a name="dismissed-warnings-grid"></a><span data-ttu-id="2f09f-120">Сетка «Отключенные предупреждения»</span><span class="sxs-lookup"><span data-stu-id="2f09f-120">Dismissed Warnings Grid</span></span>  
 <span data-ttu-id="2f09f-121">В сетке **Отключенные предупреждения** отображаются все определенные предупреждения, которые были отключены в окне **Список ошибок**.</span><span class="sxs-lookup"><span data-stu-id="2f09f-121">The **Dismissed Warnings** grid displays all specific warning occurrences that have been dismissed from the **Error List**.</span></span> <span data-ttu-id="2f09f-122">Чтобы возобновить выдачу предупреждения, выделите его в сетке и нажмите кнопку **Включить заново**.</span><span class="sxs-lookup"><span data-stu-id="2f09f-122">To re-enable a warning, select it in the grid, and then click **Re-enable**.</span></span>  
  
 <span data-ttu-id="2f09f-123">Сетка **Отключенные предупреждения** содержит следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="2f09f-123">The **Dismissed Warnings** grid has the following :</span></span>  
  
 <span data-ttu-id="2f09f-124">**Объект**</span><span class="sxs-lookup"><span data-stu-id="2f09f-124">**Object**</span></span>  
 <span data-ttu-id="2f09f-125">Отображает значок, представляющий тип и имя объекта.</span><span class="sxs-lookup"><span data-stu-id="2f09f-125">Displays an icon that represents the object type and the object name.</span></span>  
  
 <span data-ttu-id="2f09f-126">**Тип**</span><span class="sxs-lookup"><span data-stu-id="2f09f-126">**Type**</span></span>  
 <span data-ttu-id="2f09f-127">Отображает тип объекта.</span><span class="sxs-lookup"><span data-stu-id="2f09f-127">Displays the object type.</span></span>  
  
 <span data-ttu-id="2f09f-128">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2f09f-128">**Description**</span></span>  
 <span data-ttu-id="2f09f-129">Отображает имя правила.</span><span class="sxs-lookup"><span data-stu-id="2f09f-129">Displays the name of the rule.</span></span>  
  
 <span data-ttu-id="2f09f-130">**Важность**</span><span class="sxs-lookup"><span data-stu-id="2f09f-130">**Importance**</span></span>  
 <span data-ttu-id="2f09f-131">Отображает уровень важности, назначенный правилу.</span><span class="sxs-lookup"><span data-stu-id="2f09f-131">Displays the importance assigned to the rule.</span></span>  
  
 <span data-ttu-id="2f09f-132">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="2f09f-132">**Comments**</span></span>  
 <span data-ttu-id="2f09f-133">Отображает комментарий, введенный, когда предупреждение было отклонено.</span><span class="sxs-lookup"><span data-stu-id="2f09f-133">Displays the comment that was entered when the warning was dismissed.</span></span> <span data-ttu-id="2f09f-134">Здесь можно добавить или изменить комментарий.</span><span class="sxs-lookup"><span data-stu-id="2f09f-134">You can add or modify a comment here.</span></span>  
  
 <span data-ttu-id="2f09f-135">**Включить заново**</span><span class="sxs-lookup"><span data-stu-id="2f09f-135">**Re-enable**</span></span>  
 <span data-ttu-id="2f09f-136">Заново включает выбранные предупреждения.</span><span class="sxs-lookup"><span data-stu-id="2f09f-136">Re-enables the selected warnings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f09f-137">Если объект имеет предупреждение, но находится в недопустимом состоянии или был вручную удален из проекта, то рядом с предупреждением в списке появляется значок ошибки.</span><span class="sxs-lookup"><span data-stu-id="2f09f-137">If an object has a warning, but the object is in an invalid state or was manually removed from the project, an error icon appears next to the warning in the list.</span></span> <span data-ttu-id="2f09f-138">Чтобы отклонить предупреждение, выделите его и нажмите кнопку **Включить заново**.</span><span class="sxs-lookup"><span data-stu-id="2f09f-138">To dismiss the warning, select it and then click **Re-enable**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f09f-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="2f09f-139">See Also</span></span>  
 <span data-ttu-id="2f09f-140">[Диалоговое окно "Отклонить предупреждение" &#40;Analysis Services многомерных данных&#41;](dismiss-warning-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="2f09f-140">[Dismiss Warning Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](dismiss-warning-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="2f09f-141">Общие &#40;конструктор баз данных&#41; &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="2f09f-141">General &#40;Database Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](general-database-designer-analysis-services-multidimensional-data.md)  
  
  
