---
title: Определение групп элементов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- member groups [Analysis Services]
- grouping members
- DiscretizationMethod property
ms.assetid: 006cc915-c499-4781-b9a7-01ad31bebf6a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 95f9516c7a0077e97af348afa863fe15c8d4528b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750335"
---
# <a name="define-member-groups"></a><span data-ttu-id="ce3b6-102">Определение групп элементов</span><span class="sxs-lookup"><span data-stu-id="ce3b6-102">Define Member Groups</span></span>
  <span data-ttu-id="ce3b6-103">Если атрибут содержит большое число элементов, можно сгруппировать их в контейнеры, уменьшая таким образом число элементов, которые будут видеть пользователи при просмотре иерархии данных.</span><span class="sxs-lookup"><span data-stu-id="ce3b6-103">If an attribute has a large number of members, you can choose to group those members into buckets, reducing the number of members that users see when they browse the data in a hierarchy.</span></span> <span data-ttu-id="ce3b6-104">Также можно задать число контейнеров, по которым будут группироваться контейнеры, и установить схему именования контейнеров.</span><span class="sxs-lookup"><span data-stu-id="ce3b6-104">You can also determine the number of buckets in which the members are groups and set a naming scheme for the buckets.</span></span> <span data-ttu-id="ce3b6-105">Дополнительные сведения см. в разделе [Группирование элементов атрибутов (дискретизация)](attribute-properties-group-attribute-members.md).</span><span class="sxs-lookup"><span data-stu-id="ce3b6-105">For more information, see [Group Attribute Members &#40;Discretization&#41;](attribute-properties-group-attribute-members.md).</span></span>  
  
 <span data-ttu-id="ce3b6-106">Элементы группируются путем установки свойства **DiscretizationMethod** , доступ к которому можно получить с помощью окна **Свойства** в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce3b6-106">You group members by setting the **DiscretizationMethod** property, which is accessed through the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ce3b6-107">Когда создаются группы элементов, изменения не будут доступны пользователям до обработки измерения.</span><span class="sxs-lookup"><span data-stu-id="ce3b6-107">When you create member groups, your changes are not available to users until you process the dimension.</span></span> <span data-ttu-id="ce3b6-108">Дополнительные сведения см. в разделе [Обработка объектов многомерной модели](processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="ce3b6-108">For more information, see [Multidimensional Model Object Processing](processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
### <a name="to-create-member-groups"></a><span data-ttu-id="ce3b6-109">Создание групп элементов</span><span class="sxs-lookup"><span data-stu-id="ce3b6-109">To create member groups</span></span>  
  
1.  <span data-ttu-id="ce3b6-110">Откройте измерение, необходимое для работы.</span><span class="sxs-lookup"><span data-stu-id="ce3b6-110">Open the dimension that you want to work with.</span></span> <span data-ttu-id="ce3b6-111">По умолчанию откроется вкладка **Структура измерения** .</span><span class="sxs-lookup"><span data-stu-id="ce3b6-111">The **Dimension Structure** tab opens by default.</span></span>  
  
2.  <span data-ttu-id="ce3b6-112">В окне **Атрибуты**щелкните правой кнопкой мыши атрибут, элементы которого нужно сгруппировать, а затем выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ce3b6-112">In **Attributes**, right-click the attribute whose members you want to group, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="ce3b6-113">В раскрывающемся списке рядом с полем **DiscretizationMethod**выберите метод группирования элементов.</span><span class="sxs-lookup"><span data-stu-id="ce3b6-113">From the drop-down list next to **DiscretizationMethod**, select a method by which to group the members.</span></span> <span data-ttu-id="ce3b6-114">Дополнительные сведения о настройках **DiscretizationMethod** см. в разделе [Группирование элементов атрибутов (дискретизация)](attribute-properties-group-attribute-members.md).</span><span class="sxs-lookup"><span data-stu-id="ce3b6-114">For more information about **DiscretizationMethod** settings, see [Group Attribute Members &#40;Discretization&#41;](attribute-properties-group-attribute-members.md).</span></span>  
  
  
