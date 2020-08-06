---
title: Включение режима конструктора DirectQuery (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 71fc7ebd-2e86-4a76-994b-66d3a57bcc9b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8ccd2dc88f447e78f6558565a89accc341eac37c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665136"
---
# <a name="enable-directquery-design-mode-ssas-tabular"></a><span data-ttu-id="d97d3-102">Включить режим разработки DirectQuery (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="d97d3-102">Enable DirectQuery Design Mode (SSAS Tabular)</span></span>
  <span data-ttu-id="d97d3-103">Чтобы создать модель в режиме DirectQuery, следует сначала изменить среду времени разработки так, чтобы она поддерживала пользователя режима DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="d97d3-103">To create a model in DirectQuery mode, you must first change the design-time environment so that it supports the user of DirectQuery mode.</span></span> <span data-ttu-id="d97d3-104">Когда это будет сделано, конструктор также сделает следующее:</span><span class="sxs-lookup"><span data-stu-id="d97d3-104">When you do so, the designer will also do the following:</span></span>  
  
-   <span data-ttu-id="d97d3-105">Обеспечит использование свойств развертывания DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="d97d3-105">Enable the use of the DirectQuery deployment properties.</span></span>  
  
-   <span data-ttu-id="d97d3-106">Изменит запуск базы данных рабочей области на запуск в гибридном режиме, который использует кэш для разработки.</span><span class="sxs-lookup"><span data-stu-id="d97d3-106">Change the workspace database to run in a hybrid mode that uses the cache for designing.</span></span> <span data-ttu-id="d97d3-107">При фактическом развертывании модели режим будет изменен обратно на любое значение, указанное в свойствах развертывания проекта.</span><span class="sxs-lookup"><span data-stu-id="d97d3-107">When you actually deploy the model, the mode will be changed back to whatever value you specified in the project deployment properties.</span></span>  
  
-   <span data-ttu-id="d97d3-108">Отключит функции разработки, несовместимые с режимом DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="d97d3-108">Disable design features that are incompatible with DirectQuery mode.</span></span>  
  
-   <span data-ttu-id="d97d3-109">Проверит существующую модель.</span><span class="sxs-lookup"><span data-stu-id="d97d3-109">Validate the existing model.</span></span>  
  
 <span data-ttu-id="d97d3-110">В этой процедуре описывается, как включить режим DirectQuery в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="d97d3-110">This procedure describes how to enable DirectQuery mode in the designer.</span></span>  
  
### <a name="to-enable-use-of-directquery-in-a-model"></a><span data-ttu-id="d97d3-111">Включение использования DirectQuery в модели</span><span class="sxs-lookup"><span data-stu-id="d97d3-111">To enable use of DirectQuery in a model</span></span>  
  
1.  <span data-ttu-id="d97d3-112">Откройте файл решения в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d97d3-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the solution file.</span></span>  
  
2.  <span data-ttu-id="d97d3-113">В обозревателе объектов дважды щелкните файл Model.bim.</span><span class="sxs-lookup"><span data-stu-id="d97d3-113">In Object Explorer, double-click the Model.bim file.</span></span>  
  
3.  <span data-ttu-id="d97d3-114">На панели **Свойства** задайте для свойства **DirectQueryMode**значение **Вкл**.</span><span class="sxs-lookup"><span data-stu-id="d97d3-114">In the **Properties** pane, change the property, **DirectQueryMode**, to **On**.</span></span>  
  
4.  <span data-ttu-id="d97d3-115">При наличии ошибок откройте в Visual Studio **Список ошибок** и устраните проблемы, мешающие перевести модель в режим DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="d97d3-115">If there are errors, in Visual Studio, open the **Error List** and resolve any problems that would prevent the model from being switched to DirectQuery mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d97d3-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="d97d3-116">See Also</span></span>  
 [<span data-ttu-id="d97d3-117">Режим DirectQuery (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="d97d3-117">DirectQuery Mode &#40;SSAS Tabular&#41;</span></span>](directquery-mode-ssas-tabular.md)  
  
  
