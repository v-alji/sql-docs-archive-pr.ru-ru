---
title: Задача 3. Очистка данных в базе знаний поставщиков | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 647c924a-9b91-4294-8d96-e81416e4e90e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 13201a8b904a5fc5232b9fa860710e4e39cce67a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735585"
---
# <a name="task-3-cleansing-data-against-the-suppliers-knowledge-base"></a><span data-ttu-id="844de-102">Задача 3. Очистка данных в базе знаний о поставщиках</span><span class="sxs-lookup"><span data-stu-id="844de-102">Task 3: Cleansing Data against the Suppliers Knowledge Base</span></span>
  <span data-ttu-id="844de-103">В этой задаче вы выполняете автоматизированную очистку данных.</span><span class="sxs-lookup"><span data-stu-id="844de-103">In this task, you run the computer-assisted cleansing process.</span></span> <span data-ttu-id="844de-104">Службы DQS используют мощные алгоритмы и степени достоверности на основе пороговых значений, позволяющие анализировать данные по выбранной базе знаний, затем выполнять очистку.</span><span class="sxs-lookup"><span data-stu-id="844de-104">DQS uses advanced algorithms and confidence levels based on the threshold values specified to analyze the data against the selected knowledge base, and then cleanse it.</span></span> <span data-ttu-id="844de-105">Дополнительные сведения см. в разделе [Очистка данных с использованием набора знаний служб DQS (внутренних)](https://msdn.microsoft.com/library/hh213061.aspx) .</span><span class="sxs-lookup"><span data-stu-id="844de-105">See [Cleansing Data Using DQS (Internal) Knowledge](https://msdn.microsoft.com/library/hh213061.aspx) for more details.</span></span>

1.  <span data-ttu-id="844de-106">Нажмите кнопку **Запустить** , чтобы начать автоматизированный процесс очистки.</span><span class="sxs-lookup"><span data-stu-id="844de-106">Click **Start** to start the computer-assisted cleansing process.</span></span>

     <span data-ttu-id="844de-107">![Страница очистки процесса очистки](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-01.jpg "Страница очистки процесса очистки")</span><span class="sxs-lookup"><span data-stu-id="844de-107">![Cleanse Page of the Cleansing Process](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-01.jpg "Cleanse Page of the Cleansing Process")</span></span>

2.  <span data-ttu-id="844de-108">После завершения процесса очистки проверьте **статистику** на вкладке **Profiler (профилировщик** ). Статистика источника содержит количество обработанных записей, число записей, которые должны быть правильными, число записей, исправленных DQS, число записей с изменениями, предлагаемых службами DQS, и количество недопустимых записей.</span><span class="sxs-lookup"><span data-stu-id="844de-108">When the cleansing process is completed, review **statistics** in the **Profiler** tab. The Source Statistics provide the number of records processed, number of records that are found to be correct, number of records that DQS corrects, number of records that have changes suggested by DQS, and the number of records that are invalid.</span></span> <span data-ttu-id="844de-109">В списке справа можно увидеть исправленные значения, предлагаемые значения, а также полноту (степень наличия данных) и точность (степень, в которой данные можно использовать в запланированных целях) значений для каждого домена, участвующего в очистке.</span><span class="sxs-lookup"><span data-stu-id="844de-109">In the list box to the right, you can see the corrected values, suggested values, and the completeness (the extent to which the data is present) and accuracy (the extent to which the data can be used for intended purposes) of values for each domain involved in the cleansing process.</span></span>

     <span data-ttu-id="844de-110">![Результаты очистки](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-02.jpg "Результаты очистки")</span><span class="sxs-lookup"><span data-stu-id="844de-110">![Cleansing Results](../../2014/tutorials/media/et-cleansingdataagainstthesupplierkb-02.jpg "Cleansing Results")</span></span>

3.  <span data-ttu-id="844de-111">Нажмите кнопку **Далее** , чтобы перейти на страницу **Управление и просмотр результатов** .</span><span class="sxs-lookup"><span data-stu-id="844de-111">Click **Next** to switch to **Manage and View Results** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="844de-112">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="844de-112">Next Step</span></span>
 [<span data-ttu-id="844de-113">Задача 4. Manaing и просмотр результатов</span><span class="sxs-lookup"><span data-stu-id="844de-113">Task 4: Manaing and Viewing Results</span></span>](../../2014/tutorials/task-4-manaing-and-viewing-results.md)


