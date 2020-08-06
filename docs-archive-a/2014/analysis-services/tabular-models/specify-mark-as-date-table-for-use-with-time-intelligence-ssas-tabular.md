---
title: Указание таблицы дат для использования с логикой операций со временем (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 30841d1f-0c3b-4575-8f4a-27a1492e248c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 81038369b8cb8636a2aa216f1c26783a96d5f7ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727361"
---
# <a name="specify-mark-as-date-table-for-use-with-time-intelligence-ssas-tabular"></a><span data-ttu-id="ff3d0-102">Указание таблицы дат для использования с логикой операций со временем (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="ff3d0-102">Specify Mark as Date Table for use with Time Intelligence (SSAS Tabular)</span></span>
  <span data-ttu-id="ff3d0-103">Для использования логики операций со временем в формулах DAX необходимо указать таблицу дат и уникальный столбец идентификаторов (datetime) типа данных Date.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-103">In order to use time intelligence functions in DAX formulas, you must specify a date table and a unique identifier (datetime) column of the Date data type.</span></span> <span data-ttu-id="ff3d0-104">После указания в таблице дат столбца в качестве уникального идентификатора можно создавать связи между столбцами таблицы дат и любых таблиц фактов.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-104">Once a column in the date table is specified as a unique identifier, you can create relationships between columns in the date table and any fact tables.</span></span>  
  
 <span data-ttu-id="ff3d0-105">При использовании логики операций со временем действуют следующие правила.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-105">When using time intelligence functions, the following rules apply:</span></span>  
  
-   <span data-ttu-id="ff3d0-106">При использовании логики операций со временем в DAX никогда не указывайте столбец datetime из таблицы фактов.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-106">When using DAX time intelligence functions, never specify a datetime column from a fact table.</span></span> <span data-ttu-id="ff3d0-107">Всегда создавайте в модели отдельную таблицу дат, содержащую хотя бы один столбец datetime с типом данных Date и уникальными значениями.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-107">Always create a separate date table in your model with at least one datetime column of Date data type and with unique values.</span></span>  
  
-   <span data-ttu-id="ff3d0-108">Убедитесь, что таблица дат содержит непрерывный диапазон дат.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-108">Make sure your date table has a continuous date range.</span></span>  
  
-   <span data-ttu-id="ff3d0-109">Столбец datetime в таблице дат должен иметь гранулярность по дням (без долей дня).</span><span class="sxs-lookup"><span data-stu-id="ff3d0-109">The datetime column in the date table should be at day granularity (without fractions of a day).</span></span>  
  
-   <span data-ttu-id="ff3d0-110">Таблицу дат и столбец уникальных идентификаторов необходимо указывать в диалоговом окне **Пометить как таблицу дат** .</span><span class="sxs-lookup"><span data-stu-id="ff3d0-110">You must specify a date table and a unique identifier column by using the **Mark the Date Table** dialog box.</span></span>  
  
-   <span data-ttu-id="ff3d0-111">Создайте связи между таблицами фактов и столбцами типа данных Date в таблице дат.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-111">Create relationships between fact tables and columns of Date data type in the date table.</span></span>  
  
#### <a name="to-specify-a-date-table-and-unique-identifier"></a><span data-ttu-id="ff3d0-112">Указание таблицы дат и уникального идентификатора</span><span class="sxs-lookup"><span data-stu-id="ff3d0-112">To specify a date table and unique identifier</span></span>  
  
1.  <span data-ttu-id="ff3d0-113">В конструкторе моделей щелкните таблицу дат.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-113">In the model designer, click the date table.</span></span>  
  
2.  <span data-ttu-id="ff3d0-114">Откройте меню **Таблица** , выберите пункт **Дата**, а затем пункт **Пометить как таблицу дат**</span><span class="sxs-lookup"><span data-stu-id="ff3d0-114">Click the **Table** menu, then click **Date**, and then click **Mark as Date Table**</span></span>  
  
3.  <span data-ttu-id="ff3d0-115">В диалоговом окне **Пометить как таблицу дат** в списке **Дата** выберите столбец, который будет служить уникальным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-115">In the **Mark as Date Table** dialog box, in the **Date** listbox, select a column to be used as a unique identifier.</span></span> <span data-ttu-id="ff3d0-116">Этот столбец должен содержать уникальные значения и иметь тип данных Date.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-116">This column must contain unique values and should be of Date data type.</span></span> <span data-ttu-id="ff3d0-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="ff3d0-117">For example:</span></span>  
  
    |<span data-ttu-id="ff3d0-118">Дата</span><span class="sxs-lookup"><span data-stu-id="ff3d0-118">Date</span></span>|  
    |----------|  
    |<span data-ttu-id="ff3d0-119">7/1/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="ff3d0-119">7/1/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="ff3d0-120">7/2/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="ff3d0-120">7/2/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="ff3d0-121">7/3/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="ff3d0-121">7/3/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="ff3d0-122">7/4/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="ff3d0-122">7/4/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="ff3d0-123">7/5/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="ff3d0-123">7/5/2010 12:00:00 AM</span></span>|  
  
4.  <span data-ttu-id="ff3d0-124">При необходимости создайте связи между таблицами фактов и таблицей дат.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-124">If necessary, create any relationships between fact tables and the date table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff3d0-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="ff3d0-125">See Also</span></span>  
 <span data-ttu-id="ff3d0-126">[Вычисления &#40;табличных&#41;SSAS](calculations-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="ff3d0-126">[Calculations &#40;SSAS Tabular&#41;](calculations-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="ff3d0-127">Функции логики операций со временем &#40;DAX&#41;</span><span class="sxs-lookup"><span data-stu-id="ff3d0-127">Time Intelligence Functions &#40;DAX&#41;</span></span>](/dax/time-intelligence-functions-dax)  
  
  
