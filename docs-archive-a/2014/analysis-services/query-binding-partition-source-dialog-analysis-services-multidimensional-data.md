---
title: Сведения о привязке запроса (диалоговое окно «Источник секции») (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.partitions.partitionfilterexpression.f1
ms.assetid: 697874d4-3f7a-4126-96f5-37cc8e2ee306
author: minewiskan
ms.author: owend
ms.openlocfilehash: 59d2ae1fed9d22366786e21a287a621f08418a5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664511"
---
# <a name="query-binding-detail-partition-source-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="d670d-102">Сведения о привязке запроса (диалоговое окно «Источник секции») (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="d670d-102">Query Binding Detail (Partition Source Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="d670d-103">Используйте параметр **Привязка запроса** в диалоговом окне **Источник секции** , чтобы указать запрос, предоставляющий данные для секции.</span><span class="sxs-lookup"><span data-stu-id="d670d-103">Use the **Query Binding** option in the **Partition Source** dialog box to specify the query that provides the data for the partition.</span></span> <span data-ttu-id="d670d-104">Можно отобразить эту панель, выбрав параметр **Привязка запроса** в качестве значения **Типа привязки** в диалоговом окне **Источник секции** .</span><span class="sxs-lookup"><span data-stu-id="d670d-104">You can display this pane by selecting **Query Binding** from the **Binding type** option in the **Partition Source** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d670d-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="d670d-105">Options</span></span>  
 <span data-ttu-id="d670d-106">**Источник данных**</span><span class="sxs-lookup"><span data-stu-id="d670d-106">**Data source**</span></span>  
 <span data-ttu-id="d670d-107">Выберите источник данных, в котором должен выполниться запрос, чтобы обеспечить секцию данными фактов.</span><span class="sxs-lookup"><span data-stu-id="d670d-107">Select the data source on which the query is executed to provide fact data for the partition.</span></span>  
  
 <span data-ttu-id="d670d-108">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="d670d-108">**Query**</span></span>  
 <span data-ttu-id="d670d-109">Введите или измените инструкцию SQL, используемую для получения данных фактов в процессе обработки секции.</span><span class="sxs-lookup"><span data-stu-id="d670d-109">Type or modify the SQL statement used when retrieving fact data when the partition is processed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d670d-110">Указав предложение WHERE, для этой секции можно использовать вложенный набор записей.</span><span class="sxs-lookup"><span data-stu-id="d670d-110">By specifying a WHERE clause, a subset of records can be used for this partition.</span></span> <span data-ttu-id="d670d-111">Данное действие необходимо во избежание дублирования данных в случае, если несколько параллельных секций функционируют с помощью единственной таблицы фактов.</span><span class="sxs-lookup"><span data-stu-id="d670d-111">This is essential to prevent duplication of data when multiple partitions are based on a single fact table.</span></span> <span data-ttu-id="d670d-112">Дополнительные сведения см. в разделе [Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](partition-source-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="d670d-112">For more information, see [Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](partition-source-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="d670d-113">**Проверка**</span><span class="sxs-lookup"><span data-stu-id="d670d-113">**Check**</span></span>  
 <span data-ttu-id="d670d-114">Щелкните, чтобы проверить, является ли инструкция в поле **Запрос** допустимой инструкцией SQL.</span><span class="sxs-lookup"><span data-stu-id="d670d-114">Click to verify that the statement in **Query** is a valid SQL statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d670d-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="d670d-115">See Also</span></span>  
 [<span data-ttu-id="d670d-116">Диалоговое окно «Источник секции» &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="d670d-116">Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](partition-source-dialog-box-analysis-services-multidimensional-data.md)  
  
  
