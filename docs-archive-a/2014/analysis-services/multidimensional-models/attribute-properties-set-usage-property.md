---
title: Задание свойства использования | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Analysis Services], usage setting
- usage options [Analysis Services]
ms.assetid: 7b0ebc58-94b9-4523-8994-e7bc796b0bd8
author: minewiskan
ms.author: owend
ms.openlocfilehash: b437681bf8a6f132cc932061e1b42ad8497ff899
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658471"
---
# <a name="set-usage-property"></a><span data-ttu-id="ef38f-102">Установка свойства использования</span><span class="sxs-lookup"><span data-stu-id="ef38f-102">Set Usage Property</span></span>
  <span data-ttu-id="ef38f-103">Можно задать использование атрибута с помощью представления **Структура измерения** в конструкторе измерений, доступ к которому выполняется из среды [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef38f-103">You can set the usage for an attribute by using the **Dimension Structure** view in Dimension Designer, which is accessed from [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ef38f-104">При задании использования атрибута изменения вступают в силу только после обработки измерения.</span><span class="sxs-lookup"><span data-stu-id="ef38f-104">When you set usage for an attribute, your changes do not take effect until you process the dimension.</span></span> <span data-ttu-id="ef38f-105">Дополнительные сведения см. в разделе [Обработка объектов многомерной модели](processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="ef38f-105">For more information, see [Multidimensional Model Object Processing](processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
### <a name="to-set-usage-for-an-attribute"></a><span data-ttu-id="ef38f-106">Задание использования атрибута</span><span class="sxs-lookup"><span data-stu-id="ef38f-106">To set usage for an attribute</span></span>  
  
1.  <span data-ttu-id="ef38f-107">В обозревателе решений щелкните правой кнопкой мыши измерение и выберите пункт **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="ef38f-107">In Solution Explorer, right-click a dimension, and click **Open**.</span></span>  
  
     <span data-ttu-id="ef38f-108">По умолчанию откроется представление **Структура измерения** .</span><span class="sxs-lookup"><span data-stu-id="ef38f-108">The **Dimension Structure** view opens by default.</span></span>  
  
2.  <span data-ttu-id="ef38f-109">В списке **Атрибуты**щелкните правой кнопкой мыши атрибут, для которого требуется задать использование, и выберите пункт **Задать использование атрибута**, а затем установите один из следующих флажков:</span><span class="sxs-lookup"><span data-stu-id="ef38f-109">In **Attributes**, right-click the attribute for which you which you want to set usage, point to **Set Attribute Usage**, and then click one of the following options:</span></span>  
  
    -   <span data-ttu-id="ef38f-110">**Регулярно**</span><span class="sxs-lookup"><span data-stu-id="ef38f-110">**Regular**</span></span>  
  
    -   <span data-ttu-id="ef38f-111">**Key**</span><span class="sxs-lookup"><span data-stu-id="ef38f-111">**Key**</span></span>  
  
    -   <span data-ttu-id="ef38f-112">**Parent**</span><span class="sxs-lookup"><span data-stu-id="ef38f-112">**Parent**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef38f-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="ef38f-113">See Also</span></span>  
 <span data-ttu-id="ef38f-114">[Атрибуты и иерархии атрибутов](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="ef38f-114">[Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span></span>  
 [<span data-ttu-id="ef38f-115">Добавление атрибута в измерение</span><span class="sxs-lookup"><span data-stu-id="ef38f-115">Add an  Attribute to a Dimension</span></span>](attribute-properties-add-an-attribute-to-a-dimension.md)  
  
  
