---
title: Диалоговое окно «Шаблон именования уровней» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.levelnamingtemplatedialog.f1
helpviewer_keywords:
- Level Naming Template dialog box
ms.assetid: 96cad715-213e-4eac-9003-130a2f5fc985
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4dd704e619e49f0dd1adb8fed8f1e743b61309af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752472"
---
# <a name="level-naming-template-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="36430-102">Диалоговое окно «Шаблон именования уровней» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="36430-102">Level Naming Template Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="36430-103">Используйте диалоговое окно **Шаблон именования уровней** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] для создания шаблона именования уровней родительского атрибута измерения.</span><span class="sxs-lookup"><span data-stu-id="36430-103">Use the **Level Naming Template** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to construct the level naming template for a parent attribute in a dimension.</span></span> <span data-ttu-id="36430-104">Дополнительные сведения о шаблонах именования уровней см. в разделе [Элемент NamingTemplate (ASSL)](https://docs.microsoft.com/bi-reference/assl/properties/namingtemplate-element-assl).</span><span class="sxs-lookup"><span data-stu-id="36430-104">For more information about level naming templates, see [NamingTemplate Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/namingtemplate-element-assl).</span></span> <span data-ttu-id="36430-105">Диалоговое окно **шаблон именования уровней** можно отобразить, нажав кнопку с многоточием (**...**) в `NamingTemplate` значении перевода для атрибута на панели **сведения о переводе** на вкладке **переводы** **конструктора измерений**.</span><span class="sxs-lookup"><span data-stu-id="36430-105">You can display the **Level Naming Template** dialog box by clicking the ellipsis button (**...**) on the `NamingTemplate` value of a translation for an attribute in the **Translation Details** pane on the **Translations** tab of **Dimension Designer**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="36430-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="36430-106">Options</span></span>  
  
|<span data-ttu-id="36430-107">Термин</span><span class="sxs-lookup"><span data-stu-id="36430-107">Term</span></span>|<span data-ttu-id="36430-108">Определение</span><span class="sxs-lookup"><span data-stu-id="36430-108">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="36430-109">**Определить шаблон данного уровня**</span><span class="sxs-lookup"><span data-stu-id="36430-109">**Define the level template**</span></span>|<span data-ttu-id="36430-110">Отображает сетку, в которой можно спроектировать иерархию уровней для родительского атрибута.</span><span class="sxs-lookup"><span data-stu-id="36430-110">Displays a grid in which you can design the hierarchy of levels in the parent attribute.</span></span> <span data-ttu-id="36430-111">Сетка содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="36430-111">The grid contains the following columns:</span></span><br /><br /> <span data-ttu-id="36430-112">**Уровень**: отображает порядковый номер уровня, для которого используется имя, указанное в поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="36430-112">**Level**: Displays the ordinal position of the level for which the name specified in **Name** is used.</span></span> <span data-ttu-id="36430-113">Чтобы добавить новый шаблон именования для уровня, выберите **Имя** в строке, содержащей звездочку (\*) в поле **Уровень**.</span><span class="sxs-lookup"><span data-stu-id="36430-113">To add a new naming template for a level, select **Name** on the row that contains an asterisk (\*) in **Level**.</span></span><br /><br /> <span data-ttu-id="36430-114">**Имя**: содержит шаблон именования, используемый для уровня, указанного в поле **уровень**.</span><span class="sxs-lookup"><span data-stu-id="36430-114">**Name**: Contains the naming template used for the level indicated in **Level**.</span></span> <span data-ttu-id="36430-115">Чтобы добавить заполнитель для порядкового положения уровня в шаблоне именования, вставьте одну звездочку (\*).</span><span class="sxs-lookup"><span data-stu-id="36430-115">To add a placeholder for the level ordinal position in the naming template, add a single asterisk (\*).</span></span> <span data-ttu-id="36430-116">Чтобы добавить звездочку как часть имени, созданного с помощью шаблона именования, добавьте две звездочки ( \* \* ).</span><span class="sxs-lookup"><span data-stu-id="36430-116">To add an asterisk as part of the name created by the naming template, add two asterisks (\*\*).</span></span>|  
|<span data-ttu-id="36430-117">**Очистить все**</span><span class="sxs-lookup"><span data-stu-id="36430-117">**Clear All**</span></span>|<span data-ttu-id="36430-118">Выберите удаление всех строк в **Определении шаблона уровня**.</span><span class="sxs-lookup"><span data-stu-id="36430-118">Select to remove all rows in **Define the level template**.</span></span>|  
|<span data-ttu-id="36430-119">**Результат**</span><span class="sxs-lookup"><span data-stu-id="36430-119">**Result**</span></span>|<span data-ttu-id="36430-120">Отображает шаблон именования уровня, созданный при помощи этого диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="36430-120">Displays the level naming template constructed by the dialog box.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36430-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="36430-121">See Also</span></span>  
 <span data-ttu-id="36430-122">[Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="36430-122">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="36430-123">Переводы &#40;конструктор измерений&#41; &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="36430-123">Translations &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](translations-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
