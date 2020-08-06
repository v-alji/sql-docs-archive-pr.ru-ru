---
title: Занятие 4. пометить как таблицу дат | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c32cc336-b7d8-4122-9d62-4936344d2315
author: minewiskan
ms.author: owend
ms.openlocfilehash: c3ccc57d770d954e9523196d2393fa9dc2ada5b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665648"
---
# <a name="lesson-4-mark-as-date-table"></a><span data-ttu-id="0efc5-102">Занятие 4: Пометить как таблицу дат</span><span class="sxs-lookup"><span data-stu-id="0efc5-102">Lesson 4: Mark as Date Table</span></span>
  <span data-ttu-id="0efc5-103">В занятии 2. Добавление данных вы импортировали таблицу измерения с именем DimDate.</span><span class="sxs-lookup"><span data-stu-id="0efc5-103">In Lesson 2: Add Data, you imported a dimension table named DimDate.</span></span> <span data-ttu-id="0efc5-104">Затем вы переименовали таблицу DimDate в занятии 3. Переименование столбцов в простое значение Date.</span><span class="sxs-lookup"><span data-stu-id="0efc5-104">You then renamed the DimDate table, in Lesson 3: Rename Columns, to simply, Date.</span></span> <span data-ttu-id="0efc5-105">Хотя в модели таблица теперь называется "Дата", она также может называться *таблицей дат*, так как содержит данные по дате и времени.</span><span class="sxs-lookup"><span data-stu-id="0efc5-105">While in your model this table is now named Date, it can also be known as a *Date table*, in that it contains date and time data.</span></span>  
  
 <span data-ttu-id="0efc5-106">Каждый раз, когда вы используете в вычислениях логику операций со временем (Time Intelligence), что, например, потребуется немного позже, когда вы будете создавать измерения, необходимо указать свойства таблицы даты, в том числе *таблицу дат* и уникальный идентификатор *столбца дат* из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="0efc5-106">Whenever you use Time Intelligence functions in calculations, as you will do when you create measures a little later, you must specify date table properties, which include a *Date table* and a unique identifier *Date column* in that table.</span></span> <span data-ttu-id="0efc5-107">После этого можно создать допустимые связи между другими таблицами и таблицей Date, что необходимо для вычислений, использующих функции операций со временем DAX.</span><span class="sxs-lookup"><span data-stu-id="0efc5-107">You can then create valid relationships between other tables and the Date table; necessary for calculations using DAX time intelligence functions.</span></span>  
  
 <span data-ttu-id="0efc5-108">На этом занятии вы пометите импортированную и переименованную таблицу дат как *таблицу "Дата"* , а столбец дат (в таблице дат) как *столбец "Дата"* (уникальный идентификатор).</span><span class="sxs-lookup"><span data-stu-id="0efc5-108">In this lesson, you will mark the imported and renamed Date table as the *Date table* and the Date column (in the Date table) as the *Date column* (unique identifier).</span></span> <span data-ttu-id="0efc5-109">Использование даты имени может привести к путанице, но вскоре вы получите идею.</span><span class="sxs-lookup"><span data-stu-id="0efc5-109">All the use of the name Date can get kind of confusing, but you'll soon get the idea.</span></span>  
  
 <span data-ttu-id="0efc5-110">Предполагаемое время выполнения данного занятия: **3 минуты**</span><span class="sxs-lookup"><span data-stu-id="0efc5-110">Estimated time to complete this lesson: **3 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0efc5-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="0efc5-111">Prerequisites</span></span>  
 <span data-ttu-id="0efc5-112">Этот раздел входит в учебник по табличному моделированию, который следует изучать в предложенном порядке.</span><span class="sxs-lookup"><span data-stu-id="0efc5-112">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="0efc5-113">Прежде чем выполнять задания в этом занятии, необходимо завершить предыдущее [Занятие 3. Переименование столбцов](rename-columns.md).</span><span class="sxs-lookup"><span data-stu-id="0efc5-113">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 3: Rename Columns](rename-columns.md).</span></span>  
  
### <a name="to-set-mark-as-date-table"></a><span data-ttu-id="0efc5-114">Чтобы обозначить таблицу дат, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="0efc5-114">To set Mark as Date Table</span></span>  
  
1.  <span data-ttu-id="0efc5-115">В конструкторе моделей щелкните таблицу (вкладку) **Дата** .</span><span class="sxs-lookup"><span data-stu-id="0efc5-115">In the model designer, click the **Date** table (tab).</span></span>  
  
2.  <span data-ttu-id="0efc5-116">В меню **Таблица** выберите пункт **Дата**, а затем пункт **Пометить как таблицу дат**.</span><span class="sxs-lookup"><span data-stu-id="0efc5-116">Click the **Table** menu, then click **Date**, and then click **Mark as Date Table**.</span></span>  
  
3.  <span data-ttu-id="0efc5-117">В диалоговом окне **Пометить как таблицу дат** в списке **Дата** выберите столбец **Дата** в качестве уникального идентификатора.</span><span class="sxs-lookup"><span data-stu-id="0efc5-117">In the **Mark as Date Table** dialog box, in the **Date** listbox, select the **Date** column as the unique identifier.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0efc5-118">Next Steps</span><span class="sxs-lookup"><span data-stu-id="0efc5-118">Next Steps</span></span>  
 <span data-ttu-id="0efc5-119">Чтобы продолжить изучение этого учебника, перейдите к следующему занятию: [Занятие 5. Создание связей](lesson-4-create-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="0efc5-119">To continue this tutorial, go to the next lesson: [Lesson 5: Create Relationships](lesson-4-create-relationships.md).</span></span>  
  
  
