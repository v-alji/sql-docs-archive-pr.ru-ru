---
title: Изменение значения времени ожидания для запросов интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- time-out
ms.assetid: f1add4bc-e882-440a-a98b-333cfa274c3e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9dcdcdcbb6e2aef48dd8725f10f38180c73f5f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665680"
---
# <a name="change-the-time-out-value-for-data-mining-queries"></a><span data-ttu-id="4f5e2-102">изменить значение времени ожидания для запросов интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="4f5e2-102">Change the Time-out Value for Data Mining Queries</span></span>
  <span data-ttu-id="4f5e2-103">При построении диаграммы точности прогнозов или выполнении прогнозирующего запроса иногда может потребоваться много времени для создания всех данных, необходимых для формирования прогноза.</span><span class="sxs-lookup"><span data-stu-id="4f5e2-103">When you build a lift chart or execute a prediction query, sometimes it can take a long time to generate all the data required for the prediction.</span></span> <span data-ttu-id="4f5e2-104">Чтобы предотвратить возможность завершения запроса из-за истечения времени ожидания, можно изменить значение, управляющее тем, как долго сервер служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ожидает завершения запроса.</span><span class="sxs-lookup"><span data-stu-id="4f5e2-104">To prevent the query from timing out, you can change the value that controls how long the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server waits to complete a query.</span></span>  
  
 <span data-ttu-id="4f5e2-105">Значение по умолчанию равно 15, но этого может оказаться недостаточно, если модели являются сложными или источник данных имеет большой размер.</span><span class="sxs-lookup"><span data-stu-id="4f5e2-105">The default value is 15; however, if your models are complex or the data source is large, this might not be enough.</span></span> <span data-ttu-id="4f5e2-106">При необходимости можно намного увеличить это значение, чтобы отвести достаточное количество времени для обработки.</span><span class="sxs-lookup"><span data-stu-id="4f5e2-106">If necessary, you can increase the value significantly, to enable enough time for processing.</span></span> <span data-ttu-id="4f5e2-107">Например, если значение **Время ожидания запроса** равно 600, выполнение запроса может продолжаться до 10 минут.</span><span class="sxs-lookup"><span data-stu-id="4f5e2-107">For example, if you set **Query Timeout** to 600, the query could continue to run for up to 10 minutes.</span></span>  
  
 <span data-ttu-id="4f5e2-108">Дополнительные сведения о прогнозирующих запросах см. в разделе [Задачи и инструкции по запросам интеллектуального анализа данных](data-mining-query-tasks-and-how-tos.md).</span><span class="sxs-lookup"><span data-stu-id="4f5e2-108">For more information about prediction queries, see [Data Mining Query Tasks and How-tos](data-mining-query-tasks-and-how-tos.md).</span></span>  
  
### <a name="configure-the-time-out-value-for-data-mining-queries"></a><span data-ttu-id="4f5e2-109">Настройка значения времени ожидания для запросов интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="4f5e2-109">Configure the time-out value for data mining queries</span></span>  
  
1.  <span data-ttu-id="4f5e2-110">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]в меню **Сервис** выберите пункт **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="4f5e2-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], from the **Tools** menu, selection **Options**.</span></span>  
  
2.  <span data-ttu-id="4f5e2-111">На панели **Параметры** разверните элемент **Конструкторы бизнес-аналитики**.</span><span class="sxs-lookup"><span data-stu-id="4f5e2-111">In the **Options** pane, expand **Business Intelligence Designers**.</span></span>  
  
3.  <span data-ttu-id="4f5e2-112">В текстовое поле **Время ожидания запроса** введите значение в секундах.</span><span class="sxs-lookup"><span data-stu-id="4f5e2-112">Click the **Query Timeout** text box, and type a value for the number of seconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f5e2-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="4f5e2-113">See Also</span></span>  
 <span data-ttu-id="4f5e2-114">[Задачи и инструкции по запросам интеллектуального анализа данных](data-mining-query-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="4f5e2-114">[Data Mining Query Tasks and How-tos](data-mining-query-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="4f5e2-115">Запросы интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="4f5e2-115">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
