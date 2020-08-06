---
title: Слияние секций (XMLA) | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- merging partitions [XMLA]
- XMLA, partitions
- partitions [Analysis Services], XML for Analysis
- XML for Analysis, partitions
ms.assetid: 657e1d4d-6d50-40f8-a771-7b20c9d865f8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 65840066d3e95571db511a2015a1bee64aa8d922
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658476"
---
# <a name="merging-partitions-xmla"></a><span data-ttu-id="cd4df-102">Слияние секций (XMLA)</span><span class="sxs-lookup"><span data-stu-id="cd4df-102">Merging Partitions (XMLA)</span></span>
  <span data-ttu-id="cd4df-103">Если секции имеют одинаковую статистическую схему и структуру, можно выполнить слияние секции с помощью команды [MergePartitions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/mergepartitions-element-xmla) в XML для АНАЛИТИКИ (XMLA).</span><span class="sxs-lookup"><span data-stu-id="cd4df-103">If partitions have the same aggregation design and structure, you can merge the partition by using the [MergePartitions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/mergepartitions-element-xmla) command in XML for Analysis (XMLA).</span></span> <span data-ttu-id="cd4df-104">При управлении секциями их слияние является важным действием, особенно для тех секций, в которых содержатся исторические данные, секционированные по дате.</span><span class="sxs-lookup"><span data-stu-id="cd4df-104">Merging partitions is an important action to perform when you manage partitions, especially those partitions that contain historical data partitioned by date.</span></span>  
  
 <span data-ttu-id="cd4df-105">Например, в финансовом кубе может быть две секции.</span><span class="sxs-lookup"><span data-stu-id="cd4df-105">For example, a financial cube may use two partitions:</span></span>  
  
-   <span data-ttu-id="cd4df-106">Одна секция представляет финансовые данные по текущему году, используя для обеспечения высокой производительности параметры хранения реляционной OLAP (ROLAP) в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="cd4df-106">One partition represents financial data for the current year, using real-time relational OLAP (ROLAP) storage settings for performance.</span></span>  
  
-   <span data-ttu-id="cd4df-107">Другая секция содержит финансовые данные по предыдущим годам, используя параметры хранения многомерной OLAP (MOLAP) для обеспечения хранения.</span><span class="sxs-lookup"><span data-stu-id="cd4df-107">Another partition contains financial data for previous years, using multidimensional OLAP (MOLAP) storage settings for storage.</span></span>  
  
 <span data-ttu-id="cd4df-108">В двух секциях установлены разные параметры хранения, но одинаковые статистические схемы.</span><span class="sxs-lookup"><span data-stu-id="cd4df-108">Both partitions use different storage settings, but use the same aggregation design.</span></span> <span data-ttu-id="cd4df-109">Вместо того чтобы в конце года обрабатывать куб по годам исторических данных, можно воспользоваться командой `MergePartitions`, чтобы выполнить слияние секции для текущего года с секцией для предыдущих лет.</span><span class="sxs-lookup"><span data-stu-id="cd4df-109">Instead of processing the cube across years of historical data at the end of the year, you can instead use the `MergePartitions` command to merge the partition for the current year into the partition for previous years.</span></span> <span data-ttu-id="cd4df-110">В этом случае будут сохранены данные статистических вычислений; при этом не требуется полной обработки куба, на что может уйти много времени.</span><span class="sxs-lookup"><span data-stu-id="cd4df-110">This preserves the aggregation data without requiring a potentially time-consuming full processing of the cube.</span></span>  
  
## <a name="specifying-partitions-to-merge"></a><span data-ttu-id="cd4df-111">Указание секций для слияния</span><span class="sxs-lookup"><span data-stu-id="cd4df-111">Specifying Partitions to Merge</span></span>  
 <span data-ttu-id="cd4df-112">При `MergePartitions` выполнении команды данные агрегирования, хранящиеся в исходных секциях, указанных в свойстве [Source](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla) , добавляются в целевую секцию, указанную в свойстве [Target](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/target-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="cd4df-112">When the `MergePartitions` command runs, the aggregation data stored in the source partitions specified in the [Source](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla) property is added to the target partition specified in the [Target](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/target-element-xmla) property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd4df-113">Свойство `Source` может содержать несколько ссылок объектов на секции.</span><span class="sxs-lookup"><span data-stu-id="cd4df-113">The `Source` property can contain more than one partition object reference.</span></span> <span data-ttu-id="cd4df-114">Но свойство `Target` не предоставляет такой возможности.</span><span class="sxs-lookup"><span data-stu-id="cd4df-114">However, the `Target` property cannot.</span></span>  
  
 <span data-ttu-id="cd4df-115">Чтобы слияние секций, указанных в свойствах `Source` и `Target`, было выполнено успешно, они должны содержаться в одной группе мер и иметь одинаковые статистические схемы.</span><span class="sxs-lookup"><span data-stu-id="cd4df-115">To be successfully merged, the partitions specified in both the `Source` and `Target` must be contained by the same measure group and use the same aggregation design.</span></span> <span data-ttu-id="cd4df-116">В противном случае возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="cd4df-116">Otherwise, an error occurs.</span></span>  
  
 <span data-ttu-id="cd4df-117">Секции, указанные в свойстве `Source`, после успешного выполнения команды `MergePartitions` удаляются.</span><span class="sxs-lookup"><span data-stu-id="cd4df-117">The partitions specified in the `Source` are deleted after the `MergePartitions` command is successfully completed.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="cd4df-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="cd4df-118">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="cd4df-119">Описание</span><span class="sxs-lookup"><span data-stu-id="cd4df-119">Description</span></span>  
 <span data-ttu-id="cd4df-120">В следующем примере выполняется слияние всех секций в группе мер " **Подсчет клиентов** " Куба **Adventure** Works в образце базы данных **Adventure Works DW** в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] раздел **Customers_2004** .</span><span class="sxs-lookup"><span data-stu-id="cd4df-120">The following example merges all the partitions in the **Customer Counts** measure group of the **Adventure Works** cube in the **Adventure Works DW** sample [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database into the **Customers_2004** partition.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cd4df-121">Код</span><span class="sxs-lookup"><span data-stu-id="cd4df-121">Code</span></span>  
  
```  
<MergePartitions xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Sources>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2001</PartitionID>  
    </Source>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2002</PartitionID>  
    </Source>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2003</PartitionID>  
    </Source>  
  </Sources>  
  <Target>  
    <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    <CubeID>Adventure Works DW</CubeID>  
    <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
    <PartitionID>Internet_Sales_2004</PartitionID>  
  </Target>  
</MergePartitions>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd4df-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="cd4df-122">See Also</span></span>  
 [<span data-ttu-id="cd4df-123">Разработка с использованием XMLA в службах Analysis Services</span><span class="sxs-lookup"><span data-stu-id="cd4df-123">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
