---
title: Конструктор многомерных выражений (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.mdxbuilderdialof.f1
helpviewer_keywords:
- MDX Builder dialog box
ms.assetid: fecbf093-65ea-4e1b-b637-f04876f1cb0f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 391f4abe953184470be60cca41d53ee20e965423
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665161"
---
# <a name="mdx-builder-analysis-services---multidimensional-data"></a><span data-ttu-id="287ac-102">Конструктор многомерных выражений (службы Analysis Services - Многомерные Данные)</span><span class="sxs-lookup"><span data-stu-id="287ac-102">MDX Builder (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="287ac-103">Используйте диалоговое окно **Конструктор многомерных выражений** среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] или [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] для создания многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="287ac-103">Use the **MDX Builder** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] or [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to build a Multidimensional Expressions (MDX) expression.</span></span> <span data-ttu-id="287ac-104">Чтобы отобразить диалоговое **окно Конструктор многомерных выражений** , нажмите кнопку **Изменить многомерное** многоточие **(...**) для параметра **Разрешить чтение содержимого куба** , **Разрешить чтение содержимого ячейки в зависимости от параметров безопасности ячейки** или параметр **Разрешить чтение и запись содержимого куба** на странице **данные ячейки** **конструктора ролей**.</span><span class="sxs-lookup"><span data-stu-id="287ac-104">You can display the **MDX Builder** dialog box by clicking the **Edit MDX** ellipsis button (**...**) for the **Allow reading of cube content** option, the **Allow reading of cell content contingent on cell security** option, or the **Allow reading and writing of cube content** option on the **Cell Data** page of **Role Designer**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="287ac-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="287ac-105">Options</span></span>  
  
|<span data-ttu-id="287ac-106">Термин</span><span class="sxs-lookup"><span data-stu-id="287ac-106">Term</span></span>|<span data-ttu-id="287ac-107">Определение</span><span class="sxs-lookup"><span data-stu-id="287ac-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="287ac-108">**Выражение**</span><span class="sxs-lookup"><span data-stu-id="287ac-108">**Expression**</span></span>|<span data-ttu-id="287ac-109">Введите многомерное выражение, которое должно использоваться.</span><span class="sxs-lookup"><span data-stu-id="287ac-109">Type the MDX expression to be used.</span></span>|  
|<span data-ttu-id="287ac-110">**Проверка**</span><span class="sxs-lookup"><span data-stu-id="287ac-110">**Check**</span></span>|<span data-ttu-id="287ac-111">Нажмите кнопку **Проверить** для выполнения проверки многомерного выражения, определенного в поле **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="287ac-111">Click **Check** to test the MDX expression defined in **Expression**.</span></span>|  
|<span data-ttu-id="287ac-112">**Метаданные**</span><span class="sxs-lookup"><span data-stu-id="287ac-112">**Metadata**</span></span>|<span data-ttu-id="287ac-113">Отображает метаданные для текущего объекта служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , который может быть включен в многомерное выражение, определенное в поле **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="287ac-113">Displays metadata for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object that can be included in the MDX expression defined in **Expression**.</span></span><br /><br /> <span data-ttu-id="287ac-114">Скопировать синтаксис многомерного выражения для выбранного элемента можно, щелкнув этот элемент правой кнопкой мыши и выбрав пункт **Копировать** в контекстном меню или перетащив выбранный элемент в поле **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="287ac-114">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy** from the context menu, or by dragging the selected item to **Expression**.</span></span>|  
|<span data-ttu-id="287ac-115">**Функции**</span><span class="sxs-lookup"><span data-stu-id="287ac-115">**Functions**</span></span>|<span data-ttu-id="287ac-116">Отображает доступные функции многомерных выражений для текущего экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="287ac-116">Displays available MDX functions for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="287ac-117">Перечисленные элементы извлекаются из набора строк схемы MDSCHEMA_FUNCTIONS.</span><span class="sxs-lookup"><span data-stu-id="287ac-117">The items listed are retrieved from the MDSCHEMA_FUNCTIONS schema rowset.</span></span><br /><br /> <span data-ttu-id="287ac-118">Скопировать синтаксис многомерного выражения для выбранного элемента можно, щелкнув этот элемент правой кнопкой мыши и выбрав пункт **Копировать** в контекстном меню или перетащив выбранный элемент в поле **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="287ac-118">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy** from the context menu, or by dragging the selected item to **Expression**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="287ac-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="287ac-119">See Also</span></span>  
 <span data-ttu-id="287ac-120">[Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="287ac-120">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 <span data-ttu-id="287ac-121">[Конструктор ролей &#40;данных ячеек&#41; &#40;Analysis Services многомерных данных&#41;](https://msdn.microsoft.com/library/ms177279(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="287ac-121">[Cell Data &#40;Role Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](https://msdn.microsoft.com/library/ms177279(v=sql.120).aspx)</span></span>  
  
  
