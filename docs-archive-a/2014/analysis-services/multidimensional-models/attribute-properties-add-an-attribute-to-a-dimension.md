---
title: Добавление атрибута в измерение | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- adding attributes
- automatic attribute creation
- attributes [Analysis Services], creating
- attributes [Analysis Services], adding
- manual attribute creation [Analysis Services]
ms.assetid: 25826ba1-2b38-4b34-bd3a-7eba116093ae
author: minewiskan
ms.author: owend
ms.openlocfilehash: 776591e94deedc679592cfe36d53fb1fea4093d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668474"
---
# <a name="add-an--attribute-to-a-dimension"></a><span data-ttu-id="cc75d-102">Добавление атрибута в измерение</span><span class="sxs-lookup"><span data-stu-id="cc75d-102">Add an  Attribute to a Dimension</span></span>
  <span data-ttu-id="cc75d-103">Атрибут можно добавить в измерение автоматически или вручную в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc75d-103">You can add an attribute to a dimension either automatically or manually in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="cc75d-104">Чтобы создать атрибут автоматически, на вкладке **Структура измерения** конструктора измерений в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]выберите столбец, который нужно сопоставить с атрибутом, и перетащите его с панели **Представление источника данных** на панель **Атрибуты** .</span><span class="sxs-lookup"><span data-stu-id="cc75d-104">To create an attribute automatically, on the **Dimension Structure** tab of Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the column that you want to map to an attribute, and then drag that column from the **Data Source View** pane to the **Attributes** pane.</span></span> <span data-ttu-id="cc75d-105">Служба создаст сопоставленный столбцу атрибут, которому будет присвоено имя столбца.</span><span class="sxs-lookup"><span data-stu-id="cc75d-105">This creates an attribute that is mapped to the column, and assigns the same name to the attribute as the name of the column.</span></span> <span data-ttu-id="cc75d-106">Если атрибут с таким именем уже существует, службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] добавляют к имени порядковый номер, начинающийся с 1 для первого повторяющегося имени.</span><span class="sxs-lookup"><span data-stu-id="cc75d-106">If an attribute that uses that name already exists, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] adds an ordinal number suffix, starting with "1" for the first duplicate name.</span></span>  
  
 <span data-ttu-id="cc75d-107">Чтобы создать атрибут вручную, выберите режим просмотра панели **Attributes** в виде сетки.</span><span class="sxs-lookup"><span data-stu-id="cc75d-107">To create an attribute manually, set the **Attributes** pane to grid view.</span></span> <span data-ttu-id="cc75d-108">В столбце имя в последней строке сетки щелкните **\<new attribute>** элемент.</span><span class="sxs-lookup"><span data-stu-id="cc75d-108">In the name column of the last row in the grid, click the **\<new attribute>** item.</span></span> <span data-ttu-id="cc75d-109">Введите имя нового атрибута.</span><span class="sxs-lookup"><span data-stu-id="cc75d-109">Type a name for the new attribute.</span></span> <span data-ttu-id="cc75d-110">Будет создан атрибут, не сопоставленный столбцу, а всем свойствам атрибута будут присвоены значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cc75d-110">This creates an attribute that is not mapped to a column and that has default settings for all its properties.</span></span> <span data-ttu-id="cc75d-111">Атрибут можно сопоставить столбцу в окне **Свойства** среды [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] , настроив свойство **KeyColumns** нового атрибута.</span><span class="sxs-lookup"><span data-stu-id="cc75d-111">You can set the mapping in the **Properties** window of [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] by configuring the **KeyColumns** property for the new attribute.</span></span>  
  
 <span data-ttu-id="cc75d-112">Дополнительные сведения см. в разделах [Определение нового атрибута автоматически](attribute-properties-define-a-new-attribute-automatically.md), [Определение нового атрибута вручную](../define-a-new-attribute-manually.md), [Привязка атрибута к столбцу имени](attribute-properties-bind-an-attribute-to-a-name-column.md)и [Изменение свойства KeyColumn атрибута](attribute-properties-modify-the-keycolumn-property.md).</span><span class="sxs-lookup"><span data-stu-id="cc75d-112">For more information, see [Define a New Attribute Automatically](attribute-properties-define-a-new-attribute-automatically.md), [Define a New Attribute Manually](../define-a-new-attribute-manually.md), [Bind an Attribute to a Name Column](attribute-properties-bind-an-attribute-to-a-name-column.md), and [Modify the KeyColumn Property of an Attribute](attribute-properties-modify-the-keycolumn-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc75d-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="cc75d-113">See Also</span></span>  
 [<span data-ttu-id="cc75d-114">Справочник по свойствам атрибута измерения</span><span class="sxs-lookup"><span data-stu-id="cc75d-114">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
  
  
