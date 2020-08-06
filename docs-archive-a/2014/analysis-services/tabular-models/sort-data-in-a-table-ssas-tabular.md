---
title: Сортировка данных в таблице (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5fa6ad56-bf68-4aac-a226-52556173b7e2
author: minewiskan
ms.author: owend
ms.openlocfilehash: d9a6636c2c11fc571e8d4c1bcbc25c1e02d815fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727358"
---
# <a name="sort-data-in-a-table-ssas-tabular"></a><span data-ttu-id="fcb90-102">Сортировка данных в таблице (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="fcb90-102">Sort Data in a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="fcb90-103">Данные могут быть отсортированы по алфавиту (в прямом или обратном порядке) и по значениям (по возрастанию или по убыванию) в одном или нескольких столбцах.</span><span class="sxs-lookup"><span data-stu-id="fcb90-103">You can sort data by text (A to Z or Z to A) and numbers (smallest to largest or largest to smallest) in one or more columns.</span></span>  
  
### <a name="to-sort-the-data-in-a-table-based-on-a-text-column"></a><span data-ttu-id="fcb90-104">Сортировка данных в таблице по текстовому столбцу</span><span class="sxs-lookup"><span data-stu-id="fcb90-104">To sort the data in a table based on a text column</span></span>  
  
1.  <span data-ttu-id="fcb90-105">В конструкторе моделей выберите столбец буквенно-цифровых данных, диапазон ячеек в столбце или удостоверьтесь в том, что активная ячейка находится в столбце таблицы, который содержит буквенно-цифровые данные, а затем щелкните стрелку в заголовке столбца, по которому необходимо отфильтровать данные.</span><span class="sxs-lookup"><span data-stu-id="fcb90-105">In the model designer, select a column of alphanumeric data, a range of cells in a column, or make sure that the active cell is in a table column that contains alphanumeric data, and then click the arrow in the header of the column that you want to filter by.</span></span>  
  
2.  <span data-ttu-id="fcb90-106">В меню автофильтра выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="fcb90-106">In the AutoFilter menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="fcb90-107">Для сортировки по алфавиту в прямом порядке выберите **Сортировка от А до Я**.</span><span class="sxs-lookup"><span data-stu-id="fcb90-107">To sort in ascending alphanumeric order, click **Sort A to Z**.</span></span>  
  
    -   <span data-ttu-id="fcb90-108">Чтобы отсортировать в нисходящем алфавитно-цифровом порядке, нажмите **Сортировать от Z до A**.</span><span class="sxs-lookup"><span data-stu-id="fcb90-108">To sort in descending alphanumeric order, click **Sort Z to A**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fcb90-109">В некоторых случаях данные, импортированные из другого приложения, могут иметь начальные пробелы перед данными.</span><span class="sxs-lookup"><span data-stu-id="fcb90-109">In some cases, data imported from another application might have leading spaces inserted before data.</span></span> <span data-ttu-id="fcb90-110">Для правильной сортировки данных необходимо удалить ведущие пробелы.</span><span class="sxs-lookup"><span data-stu-id="fcb90-110">You must remove the leading spaces in order to correctly sort the data.</span></span>  
  
### <a name="to-sort-the-data-in-a-table-based-on-a-numeric-column"></a><span data-ttu-id="fcb90-111">Сортировка данных в таблице по числовому столбцу</span><span class="sxs-lookup"><span data-stu-id="fcb90-111">To sort the data in a table based on a numeric column</span></span>  
  
1.  <span data-ttu-id="fcb90-112">В конструкторе моделей выберите столбец буквенно-цифровых данных, диапазон ячеек в столбце или удостоверьтесь в том, что активная ячейка находится в столбце таблицы, который содержит буквенно-цифровые данные, а затем щелкните стрелку в заголовке столбца, по которому необходимо отфильтровать данные.</span><span class="sxs-lookup"><span data-stu-id="fcb90-112">In the model designer, select a column of alphanumeric data, a range of cells in a column, or make sure that the active cell is in a table column that contains alphanumeric data, and then click the arrow in the header of the column that you want to filter by.</span></span>  
  
2.  <span data-ttu-id="fcb90-113">В меню автофильтра выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="fcb90-113">In the AutoFilter menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="fcb90-114">Чтобы отсортировать по возрастанию, нажмите **Сортировать от наименьшего к наибольшему**.</span><span class="sxs-lookup"><span data-stu-id="fcb90-114">To sort from low numbers to high numbers, click **Sort Smallest to Largest**.</span></span>  
  
    -   <span data-ttu-id="fcb90-115">Чтобы отсортировать по убыванию, нажмите **Сортировать от наибольшего к наименьшему**.</span><span class="sxs-lookup"><span data-stu-id="fcb90-115">To sort from high numbers to low numbers, click **Sort Largest to Smallest**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fcb90-116">Если результаты не соответствуют ожиданию, возможно, столбец содержит числа, сохраненные в формате текста.</span><span class="sxs-lookup"><span data-stu-id="fcb90-116">If the results are not what you expected, the column might contain numbers stored as text and not as numbers.</span></span> <span data-ttu-id="fcb90-117">Например, отрицательные числа, импортированные из систем составления отчетности, или число, введенное с апострофом «’» в начале, сохраняются как текст.</span><span class="sxs-lookup"><span data-stu-id="fcb90-117">For example, negative numbers imported from some accounting systems, or a number entered with a leading ' (apostrophe), are stored as text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcb90-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="fcb90-118">See Also</span></span>  
 <span data-ttu-id="fcb90-119">[Фильтрация и сортировка данных &#40;табличных&#41;SSAS](../filter-and-sort-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="fcb90-119">[Filter and Sort Data &#40;SSAS Tabular&#41;](../filter-and-sort-data-ssas-tabular.md) </span></span>  
 <span data-ttu-id="fcb90-120">[Перспективы &#40;табличные&#41;SSAS](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="fcb90-120">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="fcb90-121">Роли (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="fcb90-121">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
