---
title: Подключаемые алгоритмы | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- third-party algorithms [Analysis Services]
- algorithms [data mining], creating
- plugin algorithms [Analysis Services]
ms.assetid: fe364ddc-576e-42fc-9ced-baa399992f92
author: minewiskan
ms.author: owend
ms.openlocfilehash: ebc5e007dcc6de7fb25d59547e21f1e892100570
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734625"
---
# <a name="plugin-algorithms"></a><span data-ttu-id="c8ed3-102">Подключаемые алгоритмы</span><span class="sxs-lookup"><span data-stu-id="c8ed3-102">Plugin Algorithms</span></span>
  <span data-ttu-id="c8ed3-103">Помимо алгоритмов, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] предоставляемых, существует множество других алгоритмов, которые можно использовать для интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="c8ed3-103">In addition to the algorithms that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides, there are many other algorithms that you can use for data mining.</span></span> <span data-ttu-id="c8ed3-104">Соответственно, службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] предоставляют механизм «подключения» алгоритмов, созданных сторонними производителями.</span><span class="sxs-lookup"><span data-stu-id="c8ed3-104">Accordingly, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides a mechanism for "plugging in" algorithms that are created by third parties.</span></span> <span data-ttu-id="c8ed3-105">При соблюдении алгоритмами определенных стандартов их можно использовать в рамках служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] так же, как алгоритмы [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c8ed3-105">As long as the algorithms follow certain standards, you can use them within [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] just as you use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms.</span></span> <span data-ttu-id="c8ed3-106">Алгоритмы подключаемых модулей обладают всеми возможностями алгоритмов, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] предоставляемых.</span><span class="sxs-lookup"><span data-stu-id="c8ed3-106">Plugin algorithms have all the capabilities of algorithms that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides.</span></span>  
  
 <span data-ttu-id="c8ed3-107">Полное описание интерфейсов, используемых службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] для связи с подключаемыми алгоритмами, см. в примерах создания пользовательского алгоритма и пользовательского средства просмотра моделей, которые опубликованы на веб-сайте [CodePlex](https://go.microsoft.com/fwlink/?LinkID=87843) .</span><span class="sxs-lookup"><span data-stu-id="c8ed3-107">For a full description of the interfaces that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] uses to communicate with plugin algorithms, see the samples for creating a custom algorithm and custom model viewer that are published on [CodePlex](https://go.microsoft.com/fwlink/?LinkID=87843) Web site.</span></span>  
  
## <a name="algorithm-requirements"></a><span data-ttu-id="c8ed3-108">Требования алгоритма</span><span class="sxs-lookup"><span data-stu-id="c8ed3-108">Algorithm Requirements</span></span>  
 <span data-ttu-id="c8ed3-109">Для подключения алгоритма к службам [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]необходимо реализовать следующие COM-интерфейсы:</span><span class="sxs-lookup"><span data-stu-id="c8ed3-109">To plug an algorithm into [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you must implement the following COM interfaces:</span></span>  
  
 `IDMAlgorithm`  
 <span data-ttu-id="c8ed3-110">Реализует алгоритм, создающий модели, и реализует операции прогнозирования итоговых моделей.</span><span class="sxs-lookup"><span data-stu-id="c8ed3-110">Implements an algorithm that produces models, and implements the prediction operations of the resulting models.</span></span>  
  
 `IDMAlgorithmNavigation`  
 <span data-ttu-id="c8ed3-111">Позволяет обозревателям получать доступ к содержимому моделей.</span><span class="sxs-lookup"><span data-stu-id="c8ed3-111">Enables browsers to access the content of the models.</span></span>  
  
 `IDMPersist`  
 <span data-ttu-id="c8ed3-112">Позволяет сохранять и загружать модели, обучаемые алгоритмом, при помощи служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8ed3-112">Enables the models that the algorithm trains to be saved and loaded by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 `IDMAlgorithmMetadata`  
 <span data-ttu-id="c8ed3-113">Описывает возможности и входные параметры алгоритма.</span><span class="sxs-lookup"><span data-stu-id="c8ed3-113">Describes the capabilities and input parameters of the algorithm.</span></span>  
  
 `IDMAlgorithmFactory`  
 <span data-ttu-id="c8ed3-114">Создает экземпляры объектов, которые реализуют интерфейс алгоритма, и обеспечивает службам [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] доступ к интерфейсу с метаданными алгоритма.</span><span class="sxs-lookup"><span data-stu-id="c8ed3-114">Creates instances of the objects that implement the algorithm interface, and provides [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] with access to the algorithm-metadata interface.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="c8ed3-115">используют данные COM-интерфейсы для связи с подключаемыми алгоритмами.</span><span class="sxs-lookup"><span data-stu-id="c8ed3-115">uses these COM interfaces to communicate with plugin algorithms.</span></span> <span data-ttu-id="c8ed3-116">Хотя используемые подключаемые алгоритмы должны поддерживать спецификацию [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB для интеллектуального анализа данных, им не обязательно поддерживать в спецификации все параметры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="c8ed3-116">Although plugin algorithms that you use must support the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB for Data Mining specification, they do not have to support all the data mining options in the specification.</span></span> <span data-ttu-id="c8ed3-117">Для определения возможностей алгоритма можно использовать набор строк схемы [MINING_SERVICES](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-services-rowset) .</span><span class="sxs-lookup"><span data-stu-id="c8ed3-117">You can use the [MINING_SERVICES](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-services-rowset) schema rowset to determine the capabilities of an algorithm.</span></span> <span data-ttu-id="c8ed3-118">В наборе строк схемы перечисляются параметры поддержки интеллектуального анализа данных для каждого поставщика подключаемых алгоритмов.</span><span class="sxs-lookup"><span data-stu-id="c8ed3-118">This schema rowset lists the data mining support options for each plugin algorithm provider.</span></span>  
  
 <span data-ttu-id="c8ed3-119">Прежде чем использовать новые алгоритмы со службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], их необходимо зарегистрировать.</span><span class="sxs-lookup"><span data-stu-id="c8ed3-119">You must register new algorithms before you use them with [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="c8ed3-120">Для регистрации алгоритма включите следующие сведения в INI-файл экземпляра служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , в котором необходимо включить алгоритмы:</span><span class="sxs-lookup"><span data-stu-id="c8ed3-120">To register an algorithm, include the following information in the .ini file of the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] on which you want to include the algorithms:</span></span>  
  
-   <span data-ttu-id="c8ed3-121">Название алгоритма</span><span class="sxs-lookup"><span data-stu-id="c8ed3-121">The algorithm name</span></span>  
  
-   <span data-ttu-id="c8ed3-122">ProgID (этот параметр необязателен и включается только для подключаемых алгоритмов)</span><span class="sxs-lookup"><span data-stu-id="c8ed3-122">ProgID (this is optional and will only be included for plugin algorithms)</span></span>  
  
-   <span data-ttu-id="c8ed3-123">Флажок означает, включен алгоритм или нет</span><span class="sxs-lookup"><span data-stu-id="c8ed3-123">A flag that indicates whether the algorithm is enabled or not</span></span>  
  
 <span data-ttu-id="c8ed3-124">В следующем образце кода показана регистрация нового алгоритма:</span><span class="sxs-lookup"><span data-stu-id="c8ed3-124">The following code sample illustrates how to register a new algorithm:</span></span>  
  
 `<ConfigurationSettings>`  
  
 `...`  
  
 `<DataMining>`  
  
 `...`  
  
 `<Algorithms>`  
  
 `...`  
  
 `<Sample_Plugin_Algorithm>`  
  
 `<Enabled>1</Enabled>`  
  
 `<ProgID>Microsoft.DataMining.SamplePlugInAlgorithm.Factory</ProgID>`  
  
 `</Sample_PlugIn_Algorithm>`  
  
 `...`  
  
 `</Algorithms>`  
  
 `...`  
  
 `</DataMining>`  
  
 `...`  
  
 `</ConfigurationSettings>`  
  
## <a name="see-also"></a><span data-ttu-id="c8ed3-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="c8ed3-125">See Also</span></span>  
 <span data-ttu-id="c8ed3-126">[Алгоритмы интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="c8ed3-126">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="c8ed3-127">Набор строк DMSCHEMA_MINING_SERVICES</span><span class="sxs-lookup"><span data-stu-id="c8ed3-127">DMSCHEMA_MINING_SERVICES Rowset</span></span>](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-services-rowset)  
  
  
