---
title: Создание связи между двумя таблицами (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.managereldb.f1
- sql12.asvs.bidtoolset.createrelatdb.f1
ms.assetid: 052d77b7-7922-408a-a200-786016ee4d15
author: minewiskan
ms.author: owend
ms.openlocfilehash: 33481b8d50be9ca632bcade932d51df86c1910a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657931"
---
# <a name="create-a-relationship-between-two-tables-ssas-tabular"></a><span data-ttu-id="361a4-102">Создание связи между двумя таблицами (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="361a4-102">Create a Relationship Between Two Tables (SSAS Tabular)</span></span>
  <span data-ttu-id="361a4-103">Если таблицы в источнике данных не участвуют в связях или добавляются новые таблицы, новые связи можно создать с помощью средств конструктора моделей.</span><span class="sxs-lookup"><span data-stu-id="361a4-103">If the tables in your data source do not have existing relationships, or if you add new tables, you can use the tools in the model designer to create new relationships.</span></span> <span data-ttu-id="361a4-104">Сведения об использовании связей в табличных моделях см. в разделе [Связи (табличные службы SSAS)](relationships-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="361a4-104">For information about how relationships are used in tabular models, see [Relationships &#40;SSAS Tabular&#41;](relationships-ssas-tabular.md).</span></span>  
  
## <a name="create-a-relationship-between-two-tables"></a><span data-ttu-id="361a4-105">Создание связи между двумя таблицами</span><span class="sxs-lookup"><span data-stu-id="361a4-105">Create a relationship between two tables</span></span>  
  
#### <a name="to-create-a-relationship-between-two-tables-in-diagram-view-click-and-drag"></a><span data-ttu-id="361a4-106">Создание связи между двумя таблицами в представлении диаграммы (перетаскивание)</span><span class="sxs-lookup"><span data-stu-id="361a4-106">To create a relationship between two tables in Diagram View (Click and drag)</span></span>  
  
1.  <span data-ttu-id="361a4-107">В среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]откройте меню **Модель** , выберите пункт **Представление модели**, а затем пункт **Представление диаграммы**.</span><span class="sxs-lookup"><span data-stu-id="361a4-107">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, then click **Model View**, and then click **Diagram View**.</span></span>  
  
2.  <span data-ttu-id="361a4-108">Щелкните (и удерживайте нажатым) столбец в таблице, а затем перетащите указатель в связанный столбец подстановки в связанной таблице подстановки и отпустите кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="361a4-108">Click (and hold) on a column within a table, then drag the cursor to a related lookup column in a related lookup table, and then release.</span></span> <span data-ttu-id="361a4-109">Связь будет создана автоматически в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="361a4-109">The relationship will be created in the correct order automatically.</span></span>  
  
#### <a name="to-create-a-relationship-between-two-tables-in-diagram-view-right-click"></a><span data-ttu-id="361a4-110">Создание связи между двумя таблицами в представлении диаграммы (щелчок правой кнопкой мыши)</span><span class="sxs-lookup"><span data-stu-id="361a4-110">To create a relationship between two tables in Diagram View (Right-click)</span></span>  
  
1.  <span data-ttu-id="361a4-111">В среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]откройте меню **Модель** , выберите пункт **Представление модели**, а затем пункт **Представление диаграммы**.</span><span class="sxs-lookup"><span data-stu-id="361a4-111">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, then click **Model View**, and then click **Diagram View**.</span></span>  
  
2.  <span data-ttu-id="361a4-112">Щелкните правой кнопкой мыши заголовок или столбец таблицы и выберите **Создать связь**.</span><span class="sxs-lookup"><span data-stu-id="361a4-112">Right-click a table heading or column, and then click **Create Relationship**.</span></span>  
  
3.  <span data-ttu-id="361a4-113">В диалоговом окне **Создать связь** щелкните стрелку вниз рядом с полем **Таблица**и выберите таблицу из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="361a4-113">In the **Create Relationship** dialog box, click the down arrow for **Table**, and select a table from the dropdown list.</span></span>  
  
     <span data-ttu-id="361a4-114">Эта таблица должна располагаться в части с многими элементами в связи «один к многим».</span><span class="sxs-lookup"><span data-stu-id="361a4-114">In a "one-to-many" relationship, this table should be on the "many" side.</span></span>  
  
4.  <span data-ttu-id="361a4-115">В качестве **Столбца**выберите столбец, который содержит данные, относящиеся к **Связанному столбцу уточняющего запроса**.</span><span class="sxs-lookup"><span data-stu-id="361a4-115">For **Column**, select the column that contains the data that is related to **Related Lookup Column**.</span></span> <span data-ttu-id="361a4-116">Столбец выбирается автоматически, если щелкнуть его правой кнопкой мыши для создания отношения.</span><span class="sxs-lookup"><span data-stu-id="361a4-116">The column is automatically selected if you right-clicked on a column to create the relationship.</span></span>  
  
5.  <span data-ttu-id="361a4-117">В поле **Связанная таблица уточняющих запросов**выберите таблицу, содержащую хотя бы один столбец данных, которые связаны с таблицей, выбранной в поле **Таблица**.</span><span class="sxs-lookup"><span data-stu-id="361a4-117">For **Related Lookup Table**, select a table that has at least one column of data that is related to the table you just selected for **Table**.</span></span>  
  
     <span data-ttu-id="361a4-118">В связи «один к многим» эта таблица должна находиться в части с одним элементом, что означает, что в выбранном столбце нет повторяющихся значений.</span><span class="sxs-lookup"><span data-stu-id="361a4-118">In a "one-to-many" relationship, this table should be on the "one" side, meaning that the values in the selected column do not contain duplicates.</span></span> <span data-ttu-id="361a4-119">При попытке создать связь в неправильном порядке ("один ко многим" вместо "многие к одному") рядом с полем **Связанный столбец подстановки** появится значок.</span><span class="sxs-lookup"><span data-stu-id="361a4-119">If you attempt to create the relationship in the wrong order (one-to-many instead of many-to-one), an icon will appear next to the **Related Lookup Column** field.</span></span> <span data-ttu-id="361a4-120">Для создания допустимой связи измените порядок на обратный.</span><span class="sxs-lookup"><span data-stu-id="361a4-120">Reverse the order to create a valid relationship.</span></span>  
  
6.  <span data-ttu-id="361a4-121">В поле **Связанный столбец подстановки**выберите столбец, содержащий уникальные значения, которые соответствуют значениям в столбце, выбранном в поле **Столбец**.</span><span class="sxs-lookup"><span data-stu-id="361a4-121">For **Related Lookup Column**, select a column that has unique values that match the values in the column you selected for **Column**.</span></span>  
  
7.  <span data-ttu-id="361a4-122">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="361a4-122">Click **Create**.</span></span>  
  
#### <a name="to-create-a-relationship-between-two-tables-in-data-view"></a><span data-ttu-id="361a4-123">Создание связи между двумя таблицами в представлении данных</span><span class="sxs-lookup"><span data-stu-id="361a4-123">To create a relationship between two tables in Data View</span></span>  
  
1.  <span data-ttu-id="361a4-124">В среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]откройте меню **Таблица** и выберите пункт **Создать связи**.</span><span class="sxs-lookup"><span data-stu-id="361a4-124">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Table** menu, and then click **Create Relationships**.</span></span>  
  
2.  <span data-ttu-id="361a4-125">В диалоговом окне **Создать связь** щелкните стрелку вниз рядом с полем **Таблица**и выберите таблицу из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="361a4-125">In the **Create Relationship** dialog box, click the down arrow for **Table**, and select a table from the dropdown list.</span></span>  
  
     <span data-ttu-id="361a4-126">Эта таблица должна располагаться в части с многими элементами в связи «один к многим».</span><span class="sxs-lookup"><span data-stu-id="361a4-126">In a "one-to-many" relationship, this table should be on the "many" side.</span></span>  
  
3.  <span data-ttu-id="361a4-127">В качестве **Столбца**выберите столбец, который содержит данные, относящиеся к **Связанному столбцу уточняющего запроса**.</span><span class="sxs-lookup"><span data-stu-id="361a4-127">For **Column**, select the column that contains the data that is related to **Related Lookup Column**.</span></span>  
  
4.  <span data-ttu-id="361a4-128">В поле **Связанная таблица уточняющих запросов**выберите таблицу, содержащую хотя бы один столбец данных, которые связаны с таблицей, выбранной в поле **Таблица**.</span><span class="sxs-lookup"><span data-stu-id="361a4-128">For **Related Lookup Table**, select a table that has at least one column of data that is related to the table you just selected for **Table**.</span></span>  
  
     <span data-ttu-id="361a4-129">В связи «один к многим» эта таблица должна находиться в части с одним элементом, что означает, что в выбранном столбце нет повторяющихся значений.</span><span class="sxs-lookup"><span data-stu-id="361a4-129">In a "one-to-many" relationship, this table should be on the "one" side, meaning that the values in the selected column do not contain duplicates.</span></span> <span data-ttu-id="361a4-130">При попытке создать связь в неправильном порядке ("один ко многим" вместо "многие к одному") рядом с полем **Связанный столбец подстановки** появится значок.</span><span class="sxs-lookup"><span data-stu-id="361a4-130">If you attempt to create the relationship in the wrong order (one-to-many instead of many-to-one), an icon will appear next to the **Related Lookup Column** field.</span></span> <span data-ttu-id="361a4-131">Для создания допустимой связи измените порядок на обратный.</span><span class="sxs-lookup"><span data-stu-id="361a4-131">Reverse the order to create a valid relationship.</span></span>  
  
5.  <span data-ttu-id="361a4-132">В поле **Связанный столбец подстановки**выберите столбец, содержащий уникальные значения, которые соответствуют значениям в столбце, выбранном в поле **Столбец**.</span><span class="sxs-lookup"><span data-stu-id="361a4-132">For **Related Lookup Column**, select a column that has unique values that match the values in the column you selected for **Column**.</span></span>  
  
6.  <span data-ttu-id="361a4-133">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="361a4-133">Click **Create**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="361a4-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="361a4-134">See Also</span></span>  
 <span data-ttu-id="361a4-135">[Удаление связей &#40;табличных&#41;SSAS](delete-relationships-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="361a4-135">[Delete Relationships &#40;SSAS Tabular&#41;](delete-relationships-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="361a4-136">Связи (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="361a4-136">Relationships &#40;SSAS Tabular&#41;</span></span>](relationships-ssas-tabular.md)  
  
  
