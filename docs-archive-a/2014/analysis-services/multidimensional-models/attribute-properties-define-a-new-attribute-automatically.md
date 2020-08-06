---
title: Автоматически определять новый атрибут | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- automatic attribute creation
- attributes [Analysis Services], creating
ms.assetid: 208a050a-5e2f-470c-b645-8d835e123db7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 40f9ae1f00dd0a6520c6d1b06111864fba02e8f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750347"
---
# <a name="define-a-new-attribute-automatically"></a><span data-ttu-id="1b9dd-102">Определение нового атрибута автоматически</span><span class="sxs-lookup"><span data-stu-id="1b9dd-102">Define a New Attribute Automatically</span></span>
  <span data-ttu-id="1b9dd-103">Новый атрибут измерения можно создать путем редактирования перетаскиванием элементов в конструкторе измерений.</span><span class="sxs-lookup"><span data-stu-id="1b9dd-103">You can create a new attribute in a dimension by using drag-and-drop editing in the Dimension Designer.</span></span>  
  
### <a name="to-create-a-new-attribute-automatically"></a><span data-ttu-id="1b9dd-104">Автоматическое создание нового атрибута</span><span class="sxs-lookup"><span data-stu-id="1b9dd-104">To create a new attribute automatically</span></span>  
  
1.  <span data-ttu-id="1b9dd-105">В конструкторе измерений откройте измерение, в котором необходимо создать атрибут.</span><span class="sxs-lookup"><span data-stu-id="1b9dd-105">In Dimension Designer, open the dimension in which you want to create the attribute.</span></span>  
  
2.  <span data-ttu-id="1b9dd-106">На вкладке **Структура измерения** , на панели **Представление источника данных** , в таблице, к которой нужно привязать атрибут, выберите столбец и перетащите его в панель **Атрибуты** .</span><span class="sxs-lookup"><span data-stu-id="1b9dd-106">On the **Dimension Structure** tab, in the **Data Source View** pane, in the table to which you want to bind the attribute, select the column, and then drag the column to the **Attributes** pane.</span></span>  
  
     [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="1b9dd-107">создают новый атрибут с тем же именем, что и у столбца, с которым он связан.</span><span class="sxs-lookup"><span data-stu-id="1b9dd-107">creates the new attribute that has the same name as the column to which it is bound.</span></span> <span data-ttu-id="1b9dd-108">Если к столбцу привязано несколько атрибутов, службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] добавляют номер к имени атрибута.</span><span class="sxs-lookup"><span data-stu-id="1b9dd-108">If there are multiple attributes that use the same column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] appends a number to the attribute name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b9dd-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="1b9dd-109">See Also</span></span>  
 <span data-ttu-id="1b9dd-110">[Измерения в многомерных моделях](dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="1b9dd-110">[Dimensions in Multidimensional Models](dimensions-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="1b9dd-111">Справочник по свойствам атрибута измерения</span><span class="sxs-lookup"><span data-stu-id="1b9dd-111">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
  
  
