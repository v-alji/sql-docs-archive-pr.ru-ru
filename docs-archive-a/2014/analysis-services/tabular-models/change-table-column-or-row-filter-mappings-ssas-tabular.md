---
title: Изменение сопоставлений фильтров таблиц, столбцов и строк (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2124c526-5772-4f84-a019-9dd3e906e8dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: d8a597fb51804ea12caace63f3308b07bffc5899
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658419"
---
# <a name="change-table-column-or-row-filter-mappings-ssas-tabular"></a><span data-ttu-id="50b10-102">Изменение сопоставлений фильтров таблиц, столбцов и строк (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="50b10-102">Change table, column, or row filter mappings (SSAS Tabular)</span></span>
  <span data-ttu-id="50b10-103">В этом разделе описано, как изменить сопоставления таблиц, столбцов или фильтров строк в диалоговом окне **Изменение свойств таблицы** в среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50b10-103">This topic describes how to change table, column, or row filter mappings by using the **Edit Table Properties** dialog box in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
 <span data-ttu-id="50b10-104">Параметры в диалоговом окне **Изменение свойств таблицы** различаются в зависимости от способа импорта данных — путем выбора таблиц из списка или с помощью SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="50b10-104">Options in the **Edit Table Properties** dialog box are different depending on whether you originally imported data by selecting tables from a list or by using a SQL query.</span></span> <span data-ttu-id="50b10-105">Если первоначальный импорт данных в таблицу был выполнен выбором из списка, то диалоговое окно **Изменение свойств таблицы** отображается в режиме предварительного просмотра таблицы.</span><span class="sxs-lookup"><span data-stu-id="50b10-105">If you originally imported the data by selecting from a list, the **Edit Table Properties** dialog box displays the Table Preview mode.</span></span> <span data-ttu-id="50b10-106">В этом режиме отображается только подмножество данных, ограниченное первыми 50 строками исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="50b10-106">This mode displays only a subset limited to the first fifty rows of the source table.</span></span> <span data-ttu-id="50b10-107">Если первоначальный импорт данных в таблицу был выполнен с помощью инструкции SQL, то диалоговое окно **Изменение свойств таблицы** содержит только инструкцию SQL.</span><span class="sxs-lookup"><span data-stu-id="50b10-107">If you originally imported the data by using a SQL statement, the **Edit Table Properties** dialog box only displays a SQL statement.</span></span> <span data-ttu-id="50b10-108">Используя инструкцию запроса SQL, можно получить подмножество строк, создав фильтр или вручную изменив инструкцию SQL.</span><span class="sxs-lookup"><span data-stu-id="50b10-108">Using a SQL query statement, you can retrieve a subset of rows, either by designing a filter, or by manually editing the SQL statement.</span></span>  
  
 <span data-ttu-id="50b10-109">Если заменить источник на таблицу, столбцы которой отличаются от столбцов текущей таблицы, то выводится сообщение с предупреждением об отличающихся столбцах.</span><span class="sxs-lookup"><span data-stu-id="50b10-109">If you change the source to a table that has different columns than the current table, a message is displayed warning that the columns are different.</span></span> <span data-ttu-id="50b10-110">Затем необходимо выбрать столбцы, которые нужно поместить в текущую таблицу, и нажать кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="50b10-110">You must then select the columns that you want to put in the current table and click **Save**.</span></span> <span data-ttu-id="50b10-111">Можно заменить таблицу целиком, установив флажок слева от таблицы.</span><span class="sxs-lookup"><span data-stu-id="50b10-111">You can replace the entire table by selecting the check box at the left of the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="50b10-112">Если таблица содержит больше одной секции, использовать диалоговое окно «Изменение свойств таблицы» для изменения сопоставлений фильтров строк нельзя.</span><span class="sxs-lookup"><span data-stu-id="50b10-112">If your table has more than one partition, you cannot use the Edit Table Properties dialog box to change row filter mappings.</span></span> <span data-ttu-id="50b10-113">Чтобы изменить сопоставления фильтров строк для таблиц с несколькими секциями, используйте диспетчер секций.</span><span class="sxs-lookup"><span data-stu-id="50b10-113">To change row filter mappings for tables with multiple partitions, use Partition Manager.</span></span> <span data-ttu-id="50b10-114">Дополнительные сведения см. в разделе [Секции (табличные службы SSAS)](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="50b10-114">For more information, see [Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
#### <a name="to-change-table-column-or-row-filter-mappings"></a><span data-ttu-id="50b10-115">Изменение сопоставлений фильтров таблицы, столбцов и строк</span><span class="sxs-lookup"><span data-stu-id="50b10-115">To change table, column, or row filter mappings</span></span>  
  
1.  <span data-ttu-id="50b10-116">В конструкторе моделей щелкните таблицу, затем откройте меню **Таблица** и выберите пункт **Свойства таблицы**.</span><span class="sxs-lookup"><span data-stu-id="50b10-116">In the model designer, click the table, then click on the **Table** menu, and then click **Table Properties**.</span></span>  
  
2.  <span data-ttu-id="50b10-117">В диалоговом окне **Изменение свойств таблицы** найдите столбец, содержащий критерий для выполнения фильтрации, и щелкните стрелку вниз справа от заголовка столбца.</span><span class="sxs-lookup"><span data-stu-id="50b10-117">In the **Edit Table Properties** dialog box, locate the column that contains the criteria you want to filter on, and then click the down arrow at the right of the column heading.</span></span>  
  
3.  <span data-ttu-id="50b10-118">В меню **Автофильтр** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="50b10-118">In the **AutoFilter** menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="50b10-119">В списке значений столбца выберите (или отмените выбор) одно или несколько значений, по которым будет выполняться фильтрация, и нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="50b10-119">In the list of column values, select or clear one or more values to filter by, and then click OK.</span></span>  
  
         <span data-ttu-id="50b10-120">Если количество значений слишком велико, некоторые элементы могут не войти в список.</span><span class="sxs-lookup"><span data-stu-id="50b10-120">If the number of values is extremely large, individual items might not be shown in the list.</span></span> <span data-ttu-id="50b10-121">Появится сообщение «Слишком много элементов для отображения».</span><span class="sxs-lookup"><span data-stu-id="50b10-121">Instead, you will see the message, "Too many items to show."</span></span>  
  
    -   <span data-ttu-id="50b10-122">Выберите пункт **Числовые фильтры** или **Текстовые фильтры** (в зависимости от типа столбца), а затем выберите одну из команд операторов сравнения (например, "Равно") или нажмите кнопку "Настраиваемый фильтр".</span><span class="sxs-lookup"><span data-stu-id="50b10-122">Click **Number Filters** or **Text Filters** (depending on the type of column), and then clicke of the comparison operator commands (such as Equals), or click Custom Filter.</span></span> <span data-ttu-id="50b10-123">В диалоговом окне **Настраиваемый фильтр** создайте фильтр и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="50b10-123">In the **Custom Filter** dialog box, create the filter, and then click **OK**.</span></span>  
  
         <span data-ttu-id="50b10-124">В случае ошибки и при необходимости начать заново нажмите кнопку **Очистить фильтры строк**.</span><span class="sxs-lookup"><span data-stu-id="50b10-124">If you make a mistake and need to start over, click **Clear Row Filters**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50b10-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="50b10-125">See Also</span></span>  
 [<span data-ttu-id="50b10-126">Диалоговое окно "Изменение свойств таблицы" (службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="50b10-126">Edit Table Properties Dialog Box &#40;SSAS&#41;</span></span>](../edit-table-properties-dialog-box-ssas.md)  
  
  
