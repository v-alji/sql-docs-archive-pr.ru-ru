---
title: Свойства столбца (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.designers.properties.Column.ColumnIdentitySpec
- vdt.designers.properties.Column
- vdt.tablecolumn
- vdt.designers.properties.Column.ColumnComputedColumnSpec
- vdt.designers.properties.Column.ColumnFulltextSpec
ms.assetid: e549a2a8-4154-4ec8-b146-614564169b39
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6aeb4d01cae7c09c27cafa8284638bf0a7de9691
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727810"
---
# <a name="column-properties-visual-database-tools"></a><span data-ttu-id="12fbc-102">Свойства столбца (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="12fbc-102">Column Properties (Visual Database Tools)</span></span>
  <span data-ttu-id="12fbc-103">Имеется два набора свойств столбцов: полный набор, который можно увидеть на вкладке **Свойства столбца** в конструкторе таблиц (доступен только для баз данных [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), и сокращенный набор, который доступен в окне свойств обозревателя сервера.</span><span class="sxs-lookup"><span data-stu-id="12fbc-103">There are two sets of properties for columns: a full set that you can see in the **Column Properties** tab within Table Designer (available only for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases) and a subset you can see in the Properties window using Server Explorer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12fbc-104">Свойства в данном разделе сгруппированы по категориям, а не по алфавиту.</span><span class="sxs-lookup"><span data-stu-id="12fbc-104">The properties in this topic are ordered by category rather than alphabet.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12fbc-105">В зависимости от установок или выпуска сервера доступные диалоговые окна и команды меню могут отличаться от описанных в справке.</span><span class="sxs-lookup"><span data-stu-id="12fbc-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="12fbc-106">Чтобы изменить параметры, выберите **Импорт и экспорт параметров** в меню **Сервис** .</span><span class="sxs-lookup"><span data-stu-id="12fbc-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span>  
  
## <a name="properties-window"></a><span data-ttu-id="12fbc-107">Окно «Свойства»</span><span class="sxs-lookup"><span data-stu-id="12fbc-107">Properties Window</span></span>  
 <span data-ttu-id="12fbc-108">Эти свойства отображаются в окне «Свойства» при выборе столбца в обозревателе серверов.</span><span class="sxs-lookup"><span data-stu-id="12fbc-108">These properties appear in the Properties window when you select a column in Server Explorer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12fbc-109">Все они из обозревателя серверов доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="12fbc-109">These properties, accessed using Server Explorer, are read-only.</span></span> <span data-ttu-id="12fbc-110">Чтобы изменить свойства столбцов для баз данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , выберите столбец в конструкторе таблиц.</span><span class="sxs-lookup"><span data-stu-id="12fbc-110">To edit column properties for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases, select the column in Table Designer.</span></span> <span data-ttu-id="12fbc-111">Эти свойства подробно описаны ниже в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="12fbc-111">Those properties are described later in this topic.</span></span>  
  
 <span data-ttu-id="12fbc-112">**Категория «Идентификатор»**</span><span class="sxs-lookup"><span data-stu-id="12fbc-112">**Identity Category**</span></span>  
 <span data-ttu-id="12fbc-113">При развертывании отображает свойства **Имя** и **База данных** .</span><span class="sxs-lookup"><span data-stu-id="12fbc-113">Expands to show the **Name** and **Database** properties.</span></span>  
  
 <span data-ttu-id="12fbc-114">**Название**</span><span class="sxs-lookup"><span data-stu-id="12fbc-114">**Name**</span></span>  
 <span data-ttu-id="12fbc-115">Отображает имя столбца.</span><span class="sxs-lookup"><span data-stu-id="12fbc-115">Shows the name of the column.</span></span>  
  
 <span data-ttu-id="12fbc-116">**База данных**</span><span class="sxs-lookup"><span data-stu-id="12fbc-116">**Database**</span></span>  
 <span data-ttu-id="12fbc-117">Отображает имя источника данных для выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="12fbc-117">Shows the name of the data source for the selected column.</span></span> <span data-ttu-id="12fbc-118">(Относится только к OLE DB.)</span><span class="sxs-lookup"><span data-stu-id="12fbc-118">(Applies only to OLE DB.)</span></span>  
  
 <span data-ttu-id="12fbc-119">**Категория «Прочие»**</span><span class="sxs-lookup"><span data-stu-id="12fbc-119">**Misc Category**</span></span>  
 <span data-ttu-id="12fbc-120">Увеличивается для отображения остающихся свойств.</span><span class="sxs-lookup"><span data-stu-id="12fbc-120">Expands to show the remaining properties.</span></span>  
  
 <span data-ttu-id="12fbc-121">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="12fbc-121">**Data Type**</span></span>  
 <span data-ttu-id="12fbc-122">Отображает тип данных выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="12fbc-122">Shows the data type of the selected column.</span></span> <span data-ttu-id="12fbc-123">Дополнительные сведения см. в разделе [Типы данных (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="12fbc-123">For more information, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
 <span data-ttu-id="12fbc-124">**Шаг приращения идентификатора**</span><span class="sxs-lookup"><span data-stu-id="12fbc-124">**Identity Increment**</span></span>  
 <span data-ttu-id="12fbc-125">Указывает число, добавляемое к **начальному значению идентификатора** для каждой последующей строки в столбце идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="12fbc-125">Shows the increment that will be added to the **Identity Seed** for each subsequent row of the identity column.</span></span> <span data-ttu-id="12fbc-126">(Относится только к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="12fbc-126">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
 <span data-ttu-id="12fbc-127">**начальному значению идентификатора**</span><span class="sxs-lookup"><span data-stu-id="12fbc-127">**Identity Seed**</span></span>  
 <span data-ttu-id="12fbc-128">Указывает начальное значение, присваиваемое столбцу идентификаторов в первой строке таблице.</span><span class="sxs-lookup"><span data-stu-id="12fbc-128">Shows the seed value assigned to the first row in the table for the identity column.</span></span> <span data-ttu-id="12fbc-129">(Относится только к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="12fbc-129">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
 <span data-ttu-id="12fbc-130">**Столбец идентификаторов**</span><span class="sxs-lookup"><span data-stu-id="12fbc-130">**Is Identity**</span></span>  
 <span data-ttu-id="12fbc-131">Указывает, является ли выбранный столбец столбцом идентификаторов для таблицы.</span><span class="sxs-lookup"><span data-stu-id="12fbc-131">Shows whether the selected column is the identity column for the table.</span></span> <span data-ttu-id="12fbc-132">(Относится только к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="12fbc-132">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
 <span data-ttu-id="12fbc-133">**Длина**</span><span class="sxs-lookup"><span data-stu-id="12fbc-133">**Length**</span></span>  
 <span data-ttu-id="12fbc-134">Указывает число символов, допустимых для символьных типов данных.</span><span class="sxs-lookup"><span data-stu-id="12fbc-134">Shows the number of characters allowed for character-based data types.</span></span>  
  
 <span data-ttu-id="12fbc-135">**Допускает значения NULL**</span><span class="sxs-lookup"><span data-stu-id="12fbc-135">**Nullable**</span></span>  
 <span data-ttu-id="12fbc-136">Указывает, разрешены ли в столбце данного типа значения NULL.</span><span class="sxs-lookup"><span data-stu-id="12fbc-136">Shows whether or not the column allows null values.</span></span>  
  
 <span data-ttu-id="12fbc-137">**Точность**</span><span class="sxs-lookup"><span data-stu-id="12fbc-137">**Precision**</span></span>  
 <span data-ttu-id="12fbc-138">Указывает максимальное число разрядов, допустимых для числовых типов данных.</span><span class="sxs-lookup"><span data-stu-id="12fbc-138">Shows the maximum number of digits allowed for numeric data types.</span></span> <span data-ttu-id="12fbc-139">Для нечисловых типов данных в этом свойстве отображается **0** .</span><span class="sxs-lookup"><span data-stu-id="12fbc-139">This property shows **0** for nonnumeric data types.</span></span>  
  
 <span data-ttu-id="12fbc-140">**Масштабирование**</span><span class="sxs-lookup"><span data-stu-id="12fbc-140">**Scale**</span></span>  
 <span data-ttu-id="12fbc-141">Указывает максимальное количество цифр справа от запятой в числовых типах данных.</span><span class="sxs-lookup"><span data-stu-id="12fbc-141">Shows the maximum number of digits that can appear to the right of the decimal point for numeric data types.</span></span> <span data-ttu-id="12fbc-142">Это значение должно быть меньше или равно указанной точности.</span><span class="sxs-lookup"><span data-stu-id="12fbc-142">This value must be less than or equal to the precision.</span></span> <span data-ttu-id="12fbc-143">Для нечисловых типов данных в этом свойстве отображается **0** .</span><span class="sxs-lookup"><span data-stu-id="12fbc-143">This property shows **0** for nonnumeric data types.</span></span>  
  
## <a name="column-properties-tab"></a><span data-ttu-id="12fbc-144">Вкладка «Свойства столбца»</span><span class="sxs-lookup"><span data-stu-id="12fbc-144">Column Properties Tab</span></span>  
 <span data-ttu-id="12fbc-145">Для доступа к этим свойствам в обозревателе серверов щелкните правой кнопкой мыши таблицу, к которой относится столбец, выберите **Открыть определение таблицы**и затем в конструкторе таблиц выберите строку в табличной сетке.</span><span class="sxs-lookup"><span data-stu-id="12fbc-145">To access these properties, in Server Explorer right-click the table to which the column belongs, choose **Open Table Definition**, and select the row in the table grid in Table Designer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12fbc-146">Эти свойства относятся только к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12fbc-146">These properties apply only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="12fbc-147">**Общая категория**</span><span class="sxs-lookup"><span data-stu-id="12fbc-147">**General Category**</span></span>  
 <span data-ttu-id="12fbc-148">Отображает свойства **Имя**, **Разрешить значения NULL**, **Тип данных**, **Значение по умолчанию или привязка**, **Длина**, **Точность**и **Масштаб**.</span><span class="sxs-lookup"><span data-stu-id="12fbc-148">Expands to show **Name**, **Allow Nulls**, **Data Type**, **Default Value or Binding**, **Length**, **Precision**, and **Scale**.</span></span>  
  
 <span data-ttu-id="12fbc-149">**Название**</span><span class="sxs-lookup"><span data-stu-id="12fbc-149">**Name**</span></span>  
 <span data-ttu-id="12fbc-150">Отображает имя столбца.</span><span class="sxs-lookup"><span data-stu-id="12fbc-150">Displays the name of the column.</span></span> <span data-ttu-id="12fbc-151">Для изменения имени введите его в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="12fbc-151">To edit the name, type in the text box.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="12fbc-152">Если имеются запросы, представления, пользовательские функции, хранимые процедуры или программы, которые ссылаются на этот столбец, то после изменения имени все эти объекты становятся недействительными.</span><span class="sxs-lookup"><span data-stu-id="12fbc-152">If existing queries, views, user-defined functions, stored procedures, or programs refer to the column, the name modification will make these objects invalid.</span></span>  
  
 <span data-ttu-id="12fbc-153">**Разрешить значения NULL**</span><span class="sxs-lookup"><span data-stu-id="12fbc-153">**Allow Nulls**</span></span>  
 <span data-ttu-id="12fbc-154">Указывает, разрешены ли в столбце данного типа значения NULL.</span><span class="sxs-lookup"><span data-stu-id="12fbc-154">Shows whether or not the column's data type allows null values.</span></span>  
  
 <span data-ttu-id="12fbc-155">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="12fbc-155">**Data Type**</span></span>  
 <span data-ttu-id="12fbc-156">Указывает тип данных выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="12fbc-156">Shows the data type for the selected column.</span></span> <span data-ttu-id="12fbc-157">Для редактирования свойства щелкните его значение, откройте раскрывающийся список и выберите другое значение.</span><span class="sxs-lookup"><span data-stu-id="12fbc-157">To edit this property, click its value, expand the drop-down list, and choose another value.</span></span> <span data-ttu-id="12fbc-158">Дополнительные сведения см. в разделе [Типы данных (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="12fbc-158">For more information, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
 <span data-ttu-id="12fbc-159">**Значение по умолчанию или привязка**</span><span class="sxs-lookup"><span data-stu-id="12fbc-159">**Default Value or Binding**</span></span>  
 <span data-ttu-id="12fbc-160">Указывает значение по умолчанию для данного столбца, используемое в том случае, когда значение для данного столбца отсутствует.</span><span class="sxs-lookup"><span data-stu-id="12fbc-160">Shows the default for this column when no value is specified for this column.</span></span> <span data-ttu-id="12fbc-161">Раскрывающийся список содержит все глобальные значения по умолчанию, определенные в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="12fbc-161">The drop-down list contains all global defaults defined in the data source.</span></span> <span data-ttu-id="12fbc-162">Для привязки столбца к глобальным значениям по умолчанию выберите значение из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="12fbc-162">To bind the column to a global default, select from the drop-down list.</span></span> <span data-ttu-id="12fbc-163">Или же, чтобы создать ограничение столбца по умолчанию, введите значение по умолчанию непосредственно в текстовом виде.</span><span class="sxs-lookup"><span data-stu-id="12fbc-163">Alternatively, to create a default constraint for the column, type the default value directly as text.</span></span>  
  
 <span data-ttu-id="12fbc-164">**Длина**</span><span class="sxs-lookup"><span data-stu-id="12fbc-164">**Length**</span></span>  
 <span data-ttu-id="12fbc-165">Указывает число символов, допустимых для символьных типов данных.</span><span class="sxs-lookup"><span data-stu-id="12fbc-165">Shows the number of characters allowed for character-based data types.</span></span> <span data-ttu-id="12fbc-166">Данное свойство доступно только для символьных типов данных.</span><span class="sxs-lookup"><span data-stu-id="12fbc-166">This property is only available for character-based data types.</span></span>  
  
 <span data-ttu-id="12fbc-167">**Точность**</span><span class="sxs-lookup"><span data-stu-id="12fbc-167">**Precision**</span></span>  
 <span data-ttu-id="12fbc-168">Указывает максимальное число разрядов, допустимых для числовых типов данных.</span><span class="sxs-lookup"><span data-stu-id="12fbc-168">Shows the maximum number of digits allowed for numeric data types.</span></span> <span data-ttu-id="12fbc-169">Для нечисловых типов данных в этом свойстве отображается **0** .</span><span class="sxs-lookup"><span data-stu-id="12fbc-169">This property shows **0** for nonnumeric data types.</span></span> <span data-ttu-id="12fbc-170">Данное свойство доступно только для числовых типов данных.</span><span class="sxs-lookup"><span data-stu-id="12fbc-170">This property is only available for numeric data types.</span></span>  
  
 <span data-ttu-id="12fbc-171">**Масштабирование**</span><span class="sxs-lookup"><span data-stu-id="12fbc-171">**Scale**</span></span>  
 <span data-ttu-id="12fbc-172">Указывает максимальное количество цифр справа от запятой в числовых типах данных.</span><span class="sxs-lookup"><span data-stu-id="12fbc-172">Shows the maximum number of digits that can appear to the right of the decimal point for numeric data types.</span></span> <span data-ttu-id="12fbc-173">Это значение должно быть меньше или равно указанной точности.</span><span class="sxs-lookup"><span data-stu-id="12fbc-173">This value must be less than or equal to the precision.</span></span> <span data-ttu-id="12fbc-174">Для нечисловых типов данных в этом свойстве отображается **0** .</span><span class="sxs-lookup"><span data-stu-id="12fbc-174">This property shows **0** for nonnumeric data types.</span></span> <span data-ttu-id="12fbc-175">Данное свойство доступно только для числовых типов данных.</span><span class="sxs-lookup"><span data-stu-id="12fbc-175">This property is only available for numeric data types.</span></span>  
  
 <span data-ttu-id="12fbc-176">**Категория конструктора таблиц**</span><span class="sxs-lookup"><span data-stu-id="12fbc-176">**Table Designer Category**</span></span>  
 <span data-ttu-id="12fbc-177">Увеличивается для отображения остающихся свойств.</span><span class="sxs-lookup"><span data-stu-id="12fbc-177">Expands to show the remaining properties.</span></span>  
  
 <span data-ttu-id="12fbc-178">**Параметры сортировки**</span><span class="sxs-lookup"><span data-stu-id="12fbc-178">**Collation**</span></span>  
 <span data-ttu-id="12fbc-179">Отображает установку параметров сортировки для выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="12fbc-179">Shows the collation setting for the selected column.</span></span> <span data-ttu-id="12fbc-180">Чтобы изменить этот параметр, нажмите кнопку **Параметры сортировки**, а затем нажмите кнопку с многоточием **(...)** справа от значения.</span><span class="sxs-lookup"><span data-stu-id="12fbc-180">To change this setting, click **Collation** and then click the ellipses **(...)** to the right of the value.</span></span>  
  
 <span data-ttu-id="12fbc-181">**Категория описания вычисляемых столбцов**</span><span class="sxs-lookup"><span data-stu-id="12fbc-181">**Computed Column Specification Category**</span></span>  
 <span data-ttu-id="12fbc-182">При развертывании отображает свойства **Формула** и **Материализованный**.</span><span class="sxs-lookup"><span data-stu-id="12fbc-182">Expands to show properties for **Formula** and **Is Persisted**.</span></span> <span data-ttu-id="12fbc-183">Если столбец является вычисляемым, формула также будет отображена.</span><span class="sxs-lookup"><span data-stu-id="12fbc-183">If the column is computed, the formula will also be displayed.</span></span> <span data-ttu-id="12fbc-184">Для изменения формулы разверните категорию и измените ее в свойстве **Формула** .</span><span class="sxs-lookup"><span data-stu-id="12fbc-184">To edit the formula, expand this category and edit it in the **Formula** property.</span></span>  
  
 <span data-ttu-id="12fbc-185">**Формула**</span><span class="sxs-lookup"><span data-stu-id="12fbc-185">**Formula**</span></span>  
 <span data-ttu-id="12fbc-186">Содержит формулу, используемую выбранным столбцом, если он является вычисляемым.</span><span class="sxs-lookup"><span data-stu-id="12fbc-186">Shows the formula that the selected column uses if it is a computed column.</span></span> <span data-ttu-id="12fbc-187">В этом поле можно ввести или изменить формулу.</span><span class="sxs-lookup"><span data-stu-id="12fbc-187">In this field you can enter or change a formula.</span></span>  
  
 <span data-ttu-id="12fbc-188">**Материализованный**</span><span class="sxs-lookup"><span data-stu-id="12fbc-188">**Is Persisted**</span></span>  
 <span data-ttu-id="12fbc-189">Позволяет сохранять вычисляемый столбец вместе с источником данных.</span><span class="sxs-lookup"><span data-stu-id="12fbc-189">Allows you to save the computed column with the data source.</span></span> <span data-ttu-id="12fbc-190">Материализованный вычисляемый столбец может быть включен в индекс.</span><span class="sxs-lookup"><span data-stu-id="12fbc-190">A persisted computed column can be indexed.</span></span>  
  
 <span data-ttu-id="12fbc-191">**Сжатый тип данных**</span><span class="sxs-lookup"><span data-stu-id="12fbc-191">**Condensed Data Type**</span></span>  
 <span data-ttu-id="12fbc-192">Отображает сведения о типе данных поля в том же формате, что и в инструкции SQL CREATE TABLE.</span><span class="sxs-lookup"><span data-stu-id="12fbc-192">Displays information about the field's data type, in the same format as the SQL CREATE TABLE statement.</span></span> <span data-ttu-id="12fbc-193">Например, поле, содержащее строку переменной длины с максимальной длиной 20 символов, будет представлено как «varchar(20)».</span><span class="sxs-lookup"><span data-stu-id="12fbc-193">For example, a field containing a variable-length string with a maximum length of 20 characters would be represented as "varchar(20)."</span></span> <span data-ttu-id="12fbc-194">Чтобы изменить это свойство, введите значение непосредственно в поле.</span><span class="sxs-lookup"><span data-stu-id="12fbc-194">To change this property, type the value directly.</span></span>  
  
 <span data-ttu-id="12fbc-195">**Описание**</span><span class="sxs-lookup"><span data-stu-id="12fbc-195">**Description**</span></span>  
 <span data-ttu-id="12fbc-196">Отображает описание столбца.</span><span class="sxs-lookup"><span data-stu-id="12fbc-196">Shows the description of the column.</span></span> <span data-ttu-id="12fbc-197">Для просмотра или изменения полного описания щелкните в поле "Описание", а затем нажмите кнопку с многоточием **(...)** справа от значения.</span><span class="sxs-lookup"><span data-stu-id="12fbc-197">To see the full description or to edit it, click Description, and then click the ellipses **(...)** to the right of the property.</span></span>  
  
 <span data-ttu-id="12fbc-198">**Категория описания полнотекстового столбца**</span><span class="sxs-lookup"><span data-stu-id="12fbc-198">**Full-text Specification Category**</span></span>  
 <span data-ttu-id="12fbc-199">Раскрывается, отображая свойства, относящиеся к полнотекстовым столбцам.</span><span class="sxs-lookup"><span data-stu-id="12fbc-199">Expands to show properties specific to full-text columns.</span></span>  
  
 <span data-ttu-id="12fbc-200">**С полнотекстовой индексацией**</span><span class="sxs-lookup"><span data-stu-id="12fbc-200">**Is Full-text Indexed**</span></span>  
 <span data-ttu-id="12fbc-201">Указывает, имеет ли столбец полнотекстовую индексацию.</span><span class="sxs-lookup"><span data-stu-id="12fbc-201">Indicates whether this column is full-text indexed.</span></span> <span data-ttu-id="12fbc-202">Этому свойству может быть присвоено значение **Да** только в том случае, если тип данных для данного столбца допустим для полнотекстового поиска и если таблица, к которой относится этот столбец, имеет соответствующий полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="12fbc-202">This property can be set to **Yes** only if the data type for this column is full-text searchable and if the table to which this column belongs has a full-text index specified for it.</span></span> <span data-ttu-id="12fbc-203">Для изменения этого значения щелкните его, откройте раскрывающийся список и выберите другое значение.</span><span class="sxs-lookup"><span data-stu-id="12fbc-203">To change this value, click it, expand the drop-down list, and choose a new value.</span></span>  
  
 <span data-ttu-id="12fbc-204">**Столбец полнотекстового типа**</span><span class="sxs-lookup"><span data-stu-id="12fbc-204">**Full-text type column**</span></span>  
 <span data-ttu-id="12fbc-205">Указывает столбец, который используется для определения типа документа столбца типа IMAGE.</span><span class="sxs-lookup"><span data-stu-id="12fbc-205">Shows which column is used to define the document type of a column of type image.</span></span> <span data-ttu-id="12fbc-206">Этот тип может использоваться для хранения различных документов — от DOC до XML-файлов.</span><span class="sxs-lookup"><span data-stu-id="12fbc-206">The image data type can be used to store documents ranging from .doc files to xml files.</span></span>  
  
 <span data-ttu-id="12fbc-207">**Язык**</span><span class="sxs-lookup"><span data-stu-id="12fbc-207">**Language**</span></span>  
 <span data-ttu-id="12fbc-208">Указывает язык, который используется при индексации столбца.</span><span class="sxs-lookup"><span data-stu-id="12fbc-208">Indicates the language used to index the column.</span></span>  
  
 <span data-ttu-id="12fbc-209">**Статистическая семантика**</span><span class="sxs-lookup"><span data-stu-id="12fbc-209">**Statistical Semantics**</span></span>  
 <span data-ttu-id="12fbc-210">Укажите, следует ли включить статистическое семантическое индексирование для выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="12fbc-210">Select whether to enable statistical semantic indexing for the selected column.</span></span> <span data-ttu-id="12fbc-211">Дополнительные сведения см. в разделе [Семантический поиск (SQL Server)](../../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="12fbc-211">For more information, see [Semantic Search &#40;SQL Server&#41;](../../relational-databases/search/semantic-search-sql-server.md).</span></span>  
  
 <span data-ttu-id="12fbc-212">Если **Язык** выбран до выбора режима **Статистическая семантика**и выбранный язык не имеет связанной семантической модели языка, параметру **Статистическая семантика** присваивается значение **Нет** , которое нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="12fbc-212">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** option is set to **No** and cannot be modified.</span></span> <span data-ttu-id="12fbc-213">Если для параметра **Статистическая семантика** выбрано значение **Да** до выбора **Языка**, в столбце **Язык** будут доступны только языки, имеющие семантическую модель языка.</span><span class="sxs-lookup"><span data-stu-id="12fbc-213">If you select **Yes** for the **Statistical Semantics** option prior to selecting a **Language**, then the languages available in the **Language** column will be restricted to those for which there is Semantic Language Model support.</span></span>  
  
 <span data-ttu-id="12fbc-214">**Имеет подписчика, отличного от подписчика SQL Server**</span><span class="sxs-lookup"><span data-stu-id="12fbc-214">**Has Non-SQL Server Subscriber**</span></span>  
 <span data-ttu-id="12fbc-215">Указывает, имеет ли столбец подписчик, не являющийся сервером Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="12fbc-215">Shows whether the column has a non-Microsoft SQL Server subscriber.</span></span>  
  
 <span data-ttu-id="12fbc-216">**Категория определения идентификаторов**</span><span class="sxs-lookup"><span data-stu-id="12fbc-216">**Identity Specification Category**</span></span>  
 <span data-ttu-id="12fbc-217">При развертывании отображает свойства **Столбец идентификаторов**, **Шаг приращения идентификатора**и **Начальное значение идентификатора**.</span><span class="sxs-lookup"><span data-stu-id="12fbc-217">Expands to show properties for **Is Identity**, **Identity Increment**, and **Identity Seed**.</span></span>  
  
 <span data-ttu-id="12fbc-218">**Столбец идентификаторов**</span><span class="sxs-lookup"><span data-stu-id="12fbc-218">**Is Identity**</span></span>  
 <span data-ttu-id="12fbc-219">Указывает, является ли выбранный столбец столбцом идентификаторов для таблицы.</span><span class="sxs-lookup"><span data-stu-id="12fbc-219">Shows whether the selected column is the identity column for the table.</span></span> <span data-ttu-id="12fbc-220">Для изменения этого свойства откройте таблицу в конструкторе таблиц и измените его значение в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="12fbc-220">To change the property, open the table in Table Designer and edit the properties in the **Properties** window.</span></span> <span data-ttu-id="12fbc-221">Этот параметр применяется только к столбцам с числовым типом данных, например *int*.</span><span class="sxs-lookup"><span data-stu-id="12fbc-221">This setting applies only to columns with a number-based data type, such as *int*.</span></span>  
  
 <span data-ttu-id="12fbc-222">**Шаг приращения идентификатора**</span><span class="sxs-lookup"><span data-stu-id="12fbc-222">**Identity Increment**</span></span>  
 <span data-ttu-id="12fbc-223">Указывает число, добавляемое к значению **Начальное значение идентификатора** для каждой последующей строки.</span><span class="sxs-lookup"><span data-stu-id="12fbc-223">Shows the increment that will be added to the **Identity Seed** for each subsequent row.</span></span> <span data-ttu-id="12fbc-224">Если оставить эту ячейку пустой, по умолчанию будет присвоено значение 1.</span><span class="sxs-lookup"><span data-stu-id="12fbc-224">If you leave this cell blank, the value 1 will be assigned by default.</span></span> <span data-ttu-id="12fbc-225">Для изменения этого свойства введите новое значение непосредственно в поле.</span><span class="sxs-lookup"><span data-stu-id="12fbc-225">To edit this property, type the new value directly.</span></span>  
  
 <span data-ttu-id="12fbc-226">**начальному значению идентификатора**</span><span class="sxs-lookup"><span data-stu-id="12fbc-226">**Identity Seed**</span></span>  
 <span data-ttu-id="12fbc-227">Указывает начальное значение, присваиваемое столбцу идентификаторов в первой строке таблицы.</span><span class="sxs-lookup"><span data-stu-id="12fbc-227">Shows the value assigned to the first row in the table.</span></span> <span data-ttu-id="12fbc-228">Если оставить эту ячейку пустой, по умолчанию будет присвоено значение 1.</span><span class="sxs-lookup"><span data-stu-id="12fbc-228">If you leave this cell blank, the value 1 will be assigned by default.</span></span> <span data-ttu-id="12fbc-229">Для изменения этого свойства введите новое значение непосредственно в поле.</span><span class="sxs-lookup"><span data-stu-id="12fbc-229">To edit this property, type the new value directly.</span></span>  
  
 <span data-ttu-id="12fbc-230">**Детерминированный**</span><span class="sxs-lookup"><span data-stu-id="12fbc-230">**Is Deterministic**</span></span>  
 <span data-ttu-id="12fbc-231">Указывает, может ли тип данных для выбранного столбца быть определен точно.</span><span class="sxs-lookup"><span data-stu-id="12fbc-231">Shows whether the data type of the selected column can be determined with certainty.</span></span>  
  
 <span data-ttu-id="12fbc-232">**Опубликован через службы DTS**</span><span class="sxs-lookup"><span data-stu-id="12fbc-232">**Is DTS-published**</span></span>  
 <span data-ttu-id="12fbc-233">Указывает, опубликован ли столбец через службы DTS.</span><span class="sxs-lookup"><span data-stu-id="12fbc-233">Shows whether the column is DTS-published.</span></span>  
  
 <span data-ttu-id="12fbc-234">**Индексируемый**</span><span class="sxs-lookup"><span data-stu-id="12fbc-234">**Is Indexable**</span></span>  
 <span data-ttu-id="12fbc-235">Указывает, может ли столбец быть проиндексирован.</span><span class="sxs-lookup"><span data-stu-id="12fbc-235">Shows whether the selected column can be indexed.</span></span> <span data-ttu-id="12fbc-236">Например, недетерминированные вычисляемые столбцы не могут быть проиндексированы.</span><span class="sxs-lookup"><span data-stu-id="12fbc-236">For example, non-deterministic computed columns cannot be indexed.</span></span>  
  
 <span data-ttu-id="12fbc-237">**Опубликован слиянием**</span><span class="sxs-lookup"><span data-stu-id="12fbc-237">**Is Merge-published**</span></span>  
 <span data-ttu-id="12fbc-238">Указывает, опубликован ли столбец слиянием.</span><span class="sxs-lookup"><span data-stu-id="12fbc-238">Shows whether the column is merge-published.</span></span>  
  
 <span data-ttu-id="12fbc-239">**Не подлежит репликации**</span><span class="sxs-lookup"><span data-stu-id="12fbc-239">**Is Not For Replication**</span></span>  
 <span data-ttu-id="12fbc-240">Указывает, будут ли сохранены исходные значения идентификаторов во время репликации.</span><span class="sxs-lookup"><span data-stu-id="12fbc-240">Indicates whether original identity values are preserved during replication.</span></span> <span data-ttu-id="12fbc-241">Для редактирования свойства щелкните его значение, откройте раскрывающийся список и выберите другое значение.</span><span class="sxs-lookup"><span data-stu-id="12fbc-241">To edit this property, click its value, expand the drop-down list, and choose another value.</span></span>  
  
 <span data-ttu-id="12fbc-242">**Реплицирован**</span><span class="sxs-lookup"><span data-stu-id="12fbc-242">**Is Replicated**</span></span>  
 <span data-ttu-id="12fbc-243">Указывает, реплицирован ли данный столбец в другое место.</span><span class="sxs-lookup"><span data-stu-id="12fbc-243">Shows whether this column is replicated in another location.</span></span>  
  
 <span data-ttu-id="12fbc-244">**Является типом RowGuid**</span><span class="sxs-lookup"><span data-stu-id="12fbc-244">**Is RowGuid**</span></span>  
 <span data-ttu-id="12fbc-245">Указывает, будет ли [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] использовать столбец в качестве ROWGUID.</span><span class="sxs-lookup"><span data-stu-id="12fbc-245">Indicates whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the column as a ROWGUID.</span></span> <span data-ttu-id="12fbc-246">Этому значению можно присвоить значение **Да** только для столбца с типом данных `uniqueidentifier` .</span><span class="sxs-lookup"><span data-stu-id="12fbc-246">You can set this value to **Yes** only for a column with the data type of `uniqueidentifier`.</span></span> <span data-ttu-id="12fbc-247">Для редактирования свойства щелкните его значение, откройте раскрывающийся список и выберите другое значение.</span><span class="sxs-lookup"><span data-stu-id="12fbc-247">To edit this property, click its value, expand the drop-down list, and choose another value.</span></span>  
  
 <span data-ttu-id="12fbc-248">**Размер**</span><span class="sxs-lookup"><span data-stu-id="12fbc-248">**Size**</span></span>  
 <span data-ttu-id="12fbc-249">Указывает размер в байтах, который допускается типом данных столбца.</span><span class="sxs-lookup"><span data-stu-id="12fbc-249">Shows the size in bytes allowed by column's data type.</span></span> <span data-ttu-id="12fbc-250">Например, тип данных `nchar` может иметь длину 10 (количество символов), однако для работы с наборами символов в кодировке Юникод его длина будет равняться 20.</span><span class="sxs-lookup"><span data-stu-id="12fbc-250">For example, a `nchar` data type may have a length of 10 (the number of characters) but it would have a size of 20 to account for Unicode character sets.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12fbc-251">Длина типа данных `varchar(max)` различается для каждой строки.</span><span class="sxs-lookup"><span data-stu-id="12fbc-251">The length of a `varchar(max)` data type varies for each row.</span></span> <span data-ttu-id="12fbc-252">sp_help возвращает (-1) в качестве длины `varchar(max)` столбца.</span><span class="sxs-lookup"><span data-stu-id="12fbc-252">sp_help returns (-1) as the length of `varchar(max)` column.</span></span> [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] <span data-ttu-id="12fbc-253">отображает значение -1 как размер столбца.</span><span class="sxs-lookup"><span data-stu-id="12fbc-253">displays -1 as the column size.</span></span>  
  
  
