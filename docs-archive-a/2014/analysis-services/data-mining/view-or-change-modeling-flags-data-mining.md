---
title: Просмотр или изменение флагов модели (интеллектуальный анализ данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d1169735-fb18-417b-b8d6-9a161e444020
author: minewiskan
ms.author: owend
ms.openlocfilehash: bf0edd827321685a2d6a9041759328a7ac6e7cbd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733325"
---
# <a name="view-or-change-modeling-flags-data-mining"></a><span data-ttu-id="b4ae4-102">Просмотр или изменение флагов модели (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="b4ae4-102">View or Change Modeling Flags (Data Mining)</span></span>
  <span data-ttu-id="b4ae4-103">Флаги модели представляют собой свойства, которые можно задать в столбце структуры интеллектуального анализа данных или столбцах модели интеллектуального анализа данных для определения того, как алгоритм обрабатывает данные во время анализа.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-103">Modeling flags are properties that you set on a mining structure column or mining model columns to control how the algorithm processes the data during analysis.</span></span>  
  
 <span data-ttu-id="b4ae4-104">В конструкторе моделей интеллектуального анализа данных можно просматривать и изменять флаги модели, связанные со структурой интеллектуального анализа данных или столбцом интеллектуального анализа, рассматривая свойства структуры или модели.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-104">In Data Mining Designer, you can view and modify the modeling flags associated with a mining structure or mining column by viewing the properties of the structure or model.</span></span> <span data-ttu-id="b4ae4-105">Флаги моделирования также можно задавать с помощью DMX, AMO или XMLA.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-105">You can also set modeling flags by using DMX, AMO, or XMLA.</span></span>  
  
 <span data-ttu-id="b4ae4-106">В этой процедуре описывается, как изменять флаги моделирования в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-106">This procedure describes how to change the modeling flags in the designer.</span></span>  
  
### <a name="view-or-change-the-modeling-flag-for-a-structure-column-or-model-column"></a><span data-ttu-id="b4ae4-107">Просмотр или изменение флага моделирования для столбца структуры или столбца модели</span><span class="sxs-lookup"><span data-stu-id="b4ae4-107">View or change the modeling flag for a structure column or model column</span></span>  
  
1.  <span data-ttu-id="b4ae4-108">В среде SQL Server Design Studio откройте обозреватель решений и дважды щелкните структуру интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-108">In SQL Server Design Studio, open Solution Explorer, and then double-click the mining structure.</span></span>  
  
2.  <span data-ttu-id="b4ae4-109">Чтобы установить флаг моделирования NOT NULL, перейдите на вкладку **Структура интеллектуального анализа данных** . Чтобы установить флаги РЕГРЕССии или MODEL_EXISTENCE_ONLY, перейдите на вкладку **модель интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="b4ae4-109">To set the NOT NULL modeling flag, click the **Mining Structure** tab. To set the REGRESSOR or MODEL_EXISTENCE_ONLY flags, click the **Mining Model** tab.</span></span>  
  
3.  <span data-ttu-id="b4ae4-110">Щелкните правой кнопкой мыши столбец, который необходимо просмотреть или изменить, и выберите команду **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-110">Right-click the column you want to view or change, and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="b4ae4-111">Чтобы добавить новый флаг модели, щелкните текстовое поле рядом со свойством **ModelingFlags** и отметьте один или несколько флажков, относящихся к флагам модели, предназначенным для использования.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-111">To add a new modeling flag, click the text box next to the **ModelingFlags** property, and select the check box or check boxes for the modeling flags you want to use.</span></span>  
  
     <span data-ttu-id="b4ae4-112">Флаги модели отображаются, только если они соответствуют типу данных столбца.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-112">Modeling flags are displayed only if they are appropriate for the column data type.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b4ae4-113">После изменения флага модели необходимо повторно обработать модель.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-113">After you change a modeling flag, you must reprocess the model.</span></span>  
  
### <a name="get-the-modeling-flags-used-in-the-model"></a><span data-ttu-id="b4ae4-114">Получение флагов моделирования, используемых в модели</span><span class="sxs-lookup"><span data-stu-id="b4ae4-114">Get the modeling flags used in the model</span></span>  
  
-   <span data-ttu-id="b4ae4-115">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]откройте окно DMX-запроса и введите запрос наподобие следующего:</span><span class="sxs-lookup"><span data-stu-id="b4ae4-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open a DMX Query window, and type a query like the following:</span></span>  
  
    ```  
    SELECT COLUMN_NAME, CONTENT_TYPE, MODELING_FLAG  
    FROM $system.DMSCHEMA_MINING_COLUMNS  
    WHERE MODEL_NAME = 'Forecasting'  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b4ae4-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="b4ae4-116">See Also</span></span>  
 <span data-ttu-id="b4ae4-117">[Задачи и инструкции по модели интеллектуального анализа данных](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="b4ae4-117">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="b4ae4-118">Флаги моделирования (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="b4ae4-118">Modeling Flags &#40;Data Mining&#41;</span></span>](modeling-flags-data-mining.md)  
  
  
