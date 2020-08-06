---
title: Добавление или удаление таблиц или представлений в представлении источника данных (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsvdesigner.tablespane.f1
helpviewer_keywords:
- deleting tables
- tables [Analysis Services]
- removing tables
- adding tables
- data source views [Analysis Services], tables
- tables [Analysis Services], data source views
ms.assetid: 98307d04-6548-4d7d-9244-2371dd165249
author: minewiskan
ms.author: owend
ms.openlocfilehash: da1bc2b1ac0af7576cfe3c3593b451f78d6a9fae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668475"
---
# <a name="adding-or-removing-tables-or-views-in-a-data-source-view-analysis-services"></a><span data-ttu-id="80105-102">Добавление или удаление таблиц или представлений в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="80105-102">Adding or Removing Tables or Views in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="80105-103">После создания представления источников данных (DSV) в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]можно изменить его в конструкторе представлений источников данных, добавляя или удаляя таблицы и столбцы, в том числе из других источников данных.</span><span class="sxs-lookup"><span data-stu-id="80105-103">After you have created a data source view (DSV) in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can modify it in Data Source View Designer by adding or removing tables and columns, including tables and columns from another data source.</span></span>  
  
 <span data-ttu-id="80105-104">Чтобы открыть представление источника данных (DSV) в конструкторе представлений источников данных, дважды щелкните DSV в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="80105-104">To open the DSV in Data Source View Designer, you double-click the DSV in Solution Explorer.</span></span> <span data-ttu-id="80105-105">После открытия представления источников данных для его изменения или расширения можно использовать команду **Добавить или удалить таблицы** на панели кнопок или в меню.</span><span class="sxs-lookup"><span data-stu-id="80105-105">Once you open the DSV, you can use the **Add/Remove Tables** command on the button bar or menu to modify or extend the DSV.</span></span> <span data-ttu-id="80105-106">Также можно использовать объекты диаграммы.</span><span class="sxs-lookup"><span data-stu-id="80105-106">You can also work with the objects in the diagram.</span></span> <span data-ttu-id="80105-107">Например, можно выбрать объект и нажать клавишу «Delete» на клавиатуре для удаления объекта.</span><span class="sxs-lookup"><span data-stu-id="80105-107">For example, you can select an object and then use the Delete key on your keyboard to remove an object.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="80105-108">Будьте внимательны при удалении таблицы.</span><span class="sxs-lookup"><span data-stu-id="80105-108">Use caution when removing a table.</span></span> <span data-ttu-id="80105-109">При удалении таблицы удаляются все соответствующие столбцы и связи из представления источников данных (DSV), а все объекты, связанные с таблицей, становятся недействительными.</span><span class="sxs-lookup"><span data-stu-id="80105-109">Removing a table deletes all the associated columns and relationships from the DSV and invalidates all objects bound to that table.</span></span>  
  
## <a name="selecting-tables-or-views-to-add-or-remove"></a><span data-ttu-id="80105-110">Выбор таблиц и представлений для добавления или удаления</span><span class="sxs-lookup"><span data-stu-id="80105-110">Selecting Tables or Views to Add or Remove</span></span>  
 <span data-ttu-id="80105-111">С помощью диалогового окна **Добавление или удаление таблиц** можно перемещать таблицы или представления между списками **Доступные объекты** и **Включенные объекты** .</span><span class="sxs-lookup"><span data-stu-id="80105-111">Using the **Add/Remove Tables** dialog box, you can move tables or views between the **Available objects** and **Included objects** lists.</span></span> <span data-ttu-id="80105-112">Список **Доступные объекты** изначально включает все таблицы или представления в первичном источнике данных, которые пока не включены в представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="80105-112">The **Available objects** list initially includes any tables or views in the primary data source that are not already in the data source view.</span></span> <span data-ttu-id="80105-113">Если первичный источник данных поддерживает функцию `OPENROWSET`, то в проект или базу данных также можно добавлять таблицы или представления из других источников данных.</span><span class="sxs-lookup"><span data-stu-id="80105-113">If the primary data source supports the `OPENROWSET` function, you can also add tables or views from other data sources in the project or database.</span></span>  
  
 <span data-ttu-id="80105-114">При добавлении или удалении таблицы из представление источника данных (DSV) осуществляется добавление или удаление таблицы в текущую выбранную диаграмму в DSV.</span><span class="sxs-lookup"><span data-stu-id="80105-114">Adding or removing a table to the DSV also adds or removes the table to the currently selected diagram in the DSV.</span></span> <span data-ttu-id="80105-115">Дополнительные сведения о диаграммах см. в разделе [Работа с диаграммами в конструкторе представлений источника данных (службы Analysis Services)](work-with-diagrams-in-data-source-view-designer-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="80105-115">For more information on diagrams, see [Work with Diagrams in Data Source View Designer &#40;Analysis Services&#41;](work-with-diagrams-in-data-source-view-designer-analysis-services.md).</span></span>  
  
 <span data-ttu-id="80105-116">После перемещения таблицы в список **Включенные объекты** в диалоговом окне **Добавление или удаление таблиц** можно добавить все связанные таблицы.</span><span class="sxs-lookup"><span data-stu-id="80105-116">After you move a table to the **Included objects** list in the **Add/Remove Tables** dialog box, you can add all related tables.</span></span> <span data-ttu-id="80105-117">При этой операции таблицы добавляются в соответствии с ограничениями внешних ключей в источнике данных, если такие ограничения существуют.</span><span class="sxs-lookup"><span data-stu-id="80105-117">This operation adds tables according to foreign key constraints in the data source, if such constraints exist.</span></span> <span data-ttu-id="80105-118">При отсутствии ограничений внешних ключей можно использовать свойство `NameMatchingCriteria` представления источников данных для определения связей, указывая критерий для сопоставления имен столбцов в таблицах для формирования вероятных связей.</span><span class="sxs-lookup"><span data-stu-id="80105-118">If foreign key constraints do not exist, you can use the `NameMatchingCriteria` property of the data source view to determine relationships by specifying a criterion for matching column names in tables to generate likely relationships.</span></span> <span data-ttu-id="80105-119">Если `NameMatchingCriteria` для представления источника данных задано свойство, нажмите кнопку **Добавить связанные таблицы** , чтобы добавить таблицы из источника данных с совпадающими именами столбцов.</span><span class="sxs-lookup"><span data-stu-id="80105-119">If the `NameMatchingCriteria`property is specified for the data source view, click **Add Related Tables** to add tables from the data source that have matching column names.</span></span> <span data-ttu-id="80105-120">Дополнительные сведения о задании `NameMatchingCriteria` свойства см. [в разделе представления источников данных в многомерных моделях](data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="80105-120">For more information about setting the `NameMatchingCriteria` property, see [Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80105-121">Добавление или удаление объектов в представлении источника данных не влияет на базовый источник данных.</span><span class="sxs-lookup"><span data-stu-id="80105-121">Adding or removing objects in a data source view does not affect the underlying data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80105-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="80105-122">See Also</span></span>  
 <span data-ttu-id="80105-123">[Представления источников данных в многомерных моделях](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="80105-123">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="80105-124">Работа с диаграммами в конструкторе представлений источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="80105-124">Work with Diagrams in Data Source View Designer &#40;Analysis Services&#41;</span></span>](work-with-diagrams-in-data-source-view-designer-analysis-services.md)  
  
  
