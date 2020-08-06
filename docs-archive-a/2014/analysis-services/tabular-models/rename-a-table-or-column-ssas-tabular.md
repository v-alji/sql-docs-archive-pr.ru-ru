---
title: Переименование таблицы или столбца (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.renametableorcolumn.f1
ms.assetid: 88061a39-c5aa-403d-a52b-7fdb365fc235
author: minewiskan
ms.author: owend
ms.openlocfilehash: d3a2e9a9f41434e64f9ec5ea2180861b459e8f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738837"
---
# <a name="rename-a-table-or-column-ssas-tabular"></a><span data-ttu-id="919d0-102">Переименование таблицы или столбца (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="919d0-102">Rename a Table or Column (SSAS Tabular)</span></span>
  <span data-ttu-id="919d0-103">Имя таблицы можно изменить во время импорта, указав **Понятное имя** на странице **Выбор таблиц и представлений\*\*\*\*мастера импорта таблиц**.</span><span class="sxs-lookup"><span data-stu-id="919d0-103">You can change the name of a table during the import process by typing a **Friendly Name** in the **Select Tables and Views** page of the **Table Import Wizard**.</span></span> <span data-ttu-id="919d0-104">Имена таблицы и столбцов также можно изменить, если данные импортируются с помощью запроса на странице **Указание SQL-запроса\*\*\*\*мастера импорта таблиц**.</span><span class="sxs-lookup"><span data-stu-id="919d0-104">You can also change table and column names if you import data by specifying a query on the **Specify a SQL Query** page of the **Table Import Wizard**.</span></span>  
  
 <span data-ttu-id="919d0-105">После добавления данных в модель имя (или название) таблицы появляется на вкладке таблицы в нижней части конструктора моделей.</span><span class="sxs-lookup"><span data-stu-id="919d0-105">After you have added the data to the model, the name (or title) of a table appears on the table tab, at the bottom of the model designer.</span></span> <span data-ttu-id="919d0-106">Имя таблицы можно заменить более подходящим.</span><span class="sxs-lookup"><span data-stu-id="919d0-106">You can change the name of your table to give it a more appropriate name.</span></span> <span data-ttu-id="919d0-107">После добавления данных в модель можно также переименовать столбец.</span><span class="sxs-lookup"><span data-stu-id="919d0-107">You can also rename a column after the data has been added to the model.</span></span> <span data-ttu-id="919d0-108">Переименование столбца может оказаться полезным в том случае, если данные были импортированы из нескольких источников и необходимо сделать так, чтобы столбцы в разных таблицах имели легко различимые имена.</span><span class="sxs-lookup"><span data-stu-id="919d0-108">This option is especially important when you have imported data from multiple sources, and want to ensure that columns in different tables have names that are easy to distinguish.</span></span>  
  
### <a name="to-rename-a-table"></a><span data-ttu-id="919d0-109">Переименование таблицы</span><span class="sxs-lookup"><span data-stu-id="919d0-109">To rename a table</span></span>  
  
1.  <span data-ttu-id="919d0-110">В конструкторе моделей щелкните правой кнопкой мыши вкладку с таблицей, которую необходимо переименовать, и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="919d0-110">In the model designer, right-click the tab that contains the table that you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="919d0-111">Введите новое имя.</span><span class="sxs-lookup"><span data-stu-id="919d0-111">Type the new name.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="919d0-112">Другие свойства таблицы, включая сведения о соединении и сопоставления столбцов, можно изменить в диалоговом окне **Изменение свойств таблицы** .</span><span class="sxs-lookup"><span data-stu-id="919d0-112">You can edit other properties of a table, including the connection information and column mappings, by using the **Edit Table Properties** dialog box.</span></span> <span data-ttu-id="919d0-113">Однако изменить имя в этом диалоговом окне нельзя.</span><span class="sxs-lookup"><span data-stu-id="919d0-113">However, you cannot change the name in this dialog box.</span></span>  
  
### <a name="to-rename-a-column"></a><span data-ttu-id="919d0-114">Переименование столбца</span><span class="sxs-lookup"><span data-stu-id="919d0-114">To rename a column</span></span>  
  
1.  <span data-ttu-id="919d0-115">В конструкторе моделей дважды щелкните заголовок столбца, который необходимо переименовать, либо щелкните его правой кнопкой мыши и выберите в контекстном меню пункт **Переименовать столбец** .</span><span class="sxs-lookup"><span data-stu-id="919d0-115">In the model designer, double-click the header of the column that you want to rename, or right-click the header and select **Rename Column** from the context menu.</span></span>  
  
2.  <span data-ttu-id="919d0-116">Введите новое имя.</span><span class="sxs-lookup"><span data-stu-id="919d0-116">Type the new name.</span></span>  
  
## <a name="naming-requirements-for-columns-and-tables"></a><span data-ttu-id="919d0-117">Требования к именам для столбцов и таблиц</span><span class="sxs-lookup"><span data-stu-id="919d0-117">Naming Requirements for Columns and Tables</span></span>  
 <span data-ttu-id="919d0-118">Следующие слова и символы не могут быть использованы в именах таблиц и столбцов.</span><span class="sxs-lookup"><span data-stu-id="919d0-118">The following words and characters cannot be used in the name of a table or column:</span></span>  
  
-   <span data-ttu-id="919d0-119">Начальные и конечные пробелы</span><span class="sxs-lookup"><span data-stu-id="919d0-119">Leading or trailing spaces</span></span>  
  
-   <span data-ttu-id="919d0-120">Управляющие символы</span><span class="sxs-lookup"><span data-stu-id="919d0-120">Control characters</span></span>  
  
-   <span data-ttu-id="919d0-121">Следующие символы (которые недопустимы в именах объектов Analysis Services):.,; ':/ \\ \*|? &% $! + = () [] {}<></span><span class="sxs-lookup"><span data-stu-id="919d0-121">The following characters (which are not valid in the names of Analysis Services objects): .,;':/\\*|?&%$!+=()[]{}<></span></span>  
  
-   <span data-ttu-id="919d0-122">Зарезервированные ключевые слова служб Analysis Services, включая функциональные имена и операторы многомерных выражений (MDX) и выражений интеллектуального анализа (DMX).</span><span class="sxs-lookup"><span data-stu-id="919d0-122">Analysis Services reserved keywords, including Multidimensional Expressions (MDX) and Data Mining Extensions (DMX) function names and operators.</span></span>  
  
## <a name="effect-of-renaming-on-existing-tables-columns-and-calculations"></a><span data-ttu-id="919d0-123">Влияние переименования на существующие таблицы, столбцы и вычисления</span><span class="sxs-lookup"><span data-stu-id="919d0-123">Effect of Renaming on Existing Tables, Columns, and Calculations</span></span>  
 <span data-ttu-id="919d0-124">При каждом переименовании таблицы изменяется имя объекта базовой таблицы, которая может содержать много столбцов или измерений.</span><span class="sxs-lookup"><span data-stu-id="919d0-124">Whenever you change the name of a table, you change the name of the underlying table object, which may contain multiple columns or measures.</span></span> <span data-ttu-id="919d0-125">Поэтому столбцы в таблице и все связи, в которых участвуют таблицы, следует обновить для использования в определениях нового имени.</span><span class="sxs-lookup"><span data-stu-id="919d0-125">Therefore, any columns that are in the table, and any relationships that use the table, must be updated to use the new name in their definitions.</span></span> <span data-ttu-id="919d0-126">В некоторых случаях обновление происходит автоматически.</span><span class="sxs-lookup"><span data-stu-id="919d0-126">This update happens automatically in some cases.</span></span> <span data-ttu-id="919d0-127">Меры не обновляются автоматически.</span><span class="sxs-lookup"><span data-stu-id="919d0-127">Measures are not updated automatically.</span></span>  
  
 <span data-ttu-id="919d0-128">Вычисления, использующие переименованную таблицу или столбцы из переименованной таблицы, тоже должны быть обновлены, а данные, получаемые из этих вычислений, должны быть обновлены и пересчитаны.</span><span class="sxs-lookup"><span data-stu-id="919d0-128">Moreover, any calculations that use the renamed table, or that use columns from the renamed table, must also be updated, and the data derived from those calculations must be refreshed and recalculated.</span></span> <span data-ttu-id="919d0-129">В зависимости от числа таблиц и вычислений, которых коснулось это изменение, выполнение этой операции может занять определенное время.</span><span class="sxs-lookup"><span data-stu-id="919d0-129">Depending on how many tables and calculations are affected, this can take some time to complete.</span></span> <span data-ttu-id="919d0-130">Поэтому лучше всего переименовывать таблицы во время операции импорта или до начала построения сложных связей или вычислений.</span><span class="sxs-lookup"><span data-stu-id="919d0-130">Therefore, the best time to rename tables is either during the import process, or before you start to build complex relationships and calculations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="919d0-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="919d0-131">See Also</span></span>  
 <span data-ttu-id="919d0-132">[Таблицы и столбцы &#40;табличные&#41;SSAS](tables-and-columns-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="919d0-132">[Tables and Columns &#40;SSAS Tabular&#41;](tables-and-columns-ssas-tabular.md) </span></span>  
 <span data-ttu-id="919d0-133">[Импорт из табличного&#41;PowerPivot &#40;SSAS](import-from-power-pivot-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="919d0-133">[Import from PowerPivot &#40;SSAS Tabular&#41;](import-from-power-pivot-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="919d0-134">Импорт из служб Analysis Services (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="919d0-134">Import from Analysis Services &#40;SSAS Tabular&#41;</span></span>](import-from-analysis-services-ssas-tabular.md)  
  
  
