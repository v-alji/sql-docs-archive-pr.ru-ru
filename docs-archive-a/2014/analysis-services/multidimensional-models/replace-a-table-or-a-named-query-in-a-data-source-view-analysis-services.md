---
title: Замена таблицы или именованного запроса в представлении источника данных (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- replacing tables
- data source views [Analysis Services], tables
- named queries [Analysis Services], replacing tables
- tables [Analysis Services], data source views
- partitions [Analysis Services], named queries
ms.assetid: 60c2a018-1299-4915-b60e-e73316524def
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b5055de60ba757c9dcfa118e4e2c4748c6534e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665622"
---
# <a name="replace-a-table-or-a-named-query-in-a-data-source-view-analysis-services"></a><span data-ttu-id="d566a-102">Замена таблицы или именованного запроса в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="d566a-102">Replace a Table or a Named Query in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="d566a-103">В конструкторе представлений источников данных можно заменить таблицу, представление или именованный запрос в представлении источника данных на другую таблицу или представление из того же или из другого источника данных или на именованный запрос, определенный в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="d566a-103">In Data Source View Designer, you can replace a table, view, or named query in a data source view (DSV) with a different table or view from the same or a different data source, or with a named query defined in the DSV.</span></span> <span data-ttu-id="d566a-104">При замене таблицы все другие объекты в базе данных или проекте служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] со ссылками на эту таблицу продолжают ссылаться на таблицу, так как идентификатор объекта для таблицы в представлении источника данных не изменился.</span><span class="sxs-lookup"><span data-stu-id="d566a-104">When you replace a table, all other objects in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or project that have references to the table continue to reference the table because the object ID for the table in the DSV does not change.</span></span> <span data-ttu-id="d566a-105">Любые связи по-прежнему остаются действительными (на основе соответствия имен и типа столбцов).</span><span class="sxs-lookup"><span data-stu-id="d566a-105">Any relationships that are still relevant (based on name and column-type matching) are retained.</span></span> <span data-ttu-id="d566a-106">Если таблица удаляется, а затем добавляется, то ссылки и связи также удаляются, поэтому их необходимо создавать повторно.</span><span class="sxs-lookup"><span data-stu-id="d566a-106">In contrast, if you delete and then add a table, references and relationships are lost and must be recreated.</span></span>  
  
 <span data-ttu-id="d566a-107">Чтобы заменить таблицу другой таблицей, необходимо активное соединение с источником данных в конструкторе представлений источников данных в режиме проектирования.</span><span class="sxs-lookup"><span data-stu-id="d566a-107">To replace a table with another table, you must have an active connection to the source data in Data Source View Designer in project mode.</span></span>  
  
 <span data-ttu-id="d566a-108">Чаще всего выполняется замена таблицы в представлении источника данных на другую таблицу в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="d566a-108">You most frequently replace a table in the data source view with another table in the data source.</span></span> <span data-ttu-id="d566a-109">На таблицу также можно заменить именованный запрос.</span><span class="sxs-lookup"><span data-stu-id="d566a-109">However, you can also replace a named query with a table.</span></span> <span data-ttu-id="d566a-110">Например, ранее таблица была заменена именованным запросом и теперь требуется вернуть таблицу.</span><span class="sxs-lookup"><span data-stu-id="d566a-110">For example, you previously replaced a table with a named query, and now want to revert to a table.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d566a-111">При переименовании таблицы в источнике данных выполните шаги по замене таблицы и укажите переименованную таблицу в качестве источника соответствующей таблицы в представлении источника данных до его обновления.</span><span class="sxs-lookup"><span data-stu-id="d566a-111">If you rename a table in a data source, follow the steps for replacing a table and specify the renamed table as the source of the corresponding table in the DSV before you refresh a DSV.</span></span> <span data-ttu-id="d566a-112">Завершение процесса замены и переименования сохраняет в представлении источника данных таблицу, ее ссылки и связи.</span><span class="sxs-lookup"><span data-stu-id="d566a-112">Completing the replacement and renaming process preserves the table, the table's references, and the table's relationships in the DSV.</span></span> <span data-ttu-id="d566a-113">В противном случае при обновлении представления источников данных переименованная таблица в источнике данных считается удаленной.</span><span class="sxs-lookup"><span data-stu-id="d566a-113">Otherwise, when you refresh the DSV, a renamed table in data source is interpreted as being deleted.</span></span> <span data-ttu-id="d566a-114">Дополнительные сведения см. в разделе [Обновление схемы в представлении источника данных (службы Analysis Services)](refresh-the-schema-in-a-data-source-view-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="d566a-114">For more information, see [Refresh the Schema in a Data Source View &#40;Analysis Services&#41;](refresh-the-schema-in-a-data-source-view-analysis-services.md).</span></span>  
  
##  <a name="replace-a-table-with-a-named-query"></a><a name="bkmk_nq"></a> <span data-ttu-id="d566a-115">Замена таблицы именованным запросом</span><span class="sxs-lookup"><span data-stu-id="d566a-115">Replace a table with a named query</span></span>  
  
1.  <span data-ttu-id="d566a-116">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект или подключитесь к базе данных, содержащей представление источника данных, в котором необходимо заменить таблицу или именованный запрос.</span><span class="sxs-lookup"><span data-stu-id="d566a-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to replace a table or a named query.</span></span>  
  
2.  <span data-ttu-id="d566a-117">В обозревателе решений откройте папку **Представления источников данных** , а затем дважды щелкните представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="d566a-117">In Solution Explorer, expand the **Data Source Views** folder, and then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="d566a-118">Откройте диалоговое окно **Создание именованного запроса** .</span><span class="sxs-lookup"><span data-stu-id="d566a-118">Open the **Create Named Query** dialog box.</span></span> <span data-ttu-id="d566a-119">На панели **Таблицы** либо на панели **Диаграмма** щелкните правой кнопкой мыши таблицу, которую необходимо заменить, укажите **Заменить таблицу** и выберите пункт **Новым именованным запросом**.</span><span class="sxs-lookup"><span data-stu-id="d566a-119">In either **Tables** or **Diagram** pane, right-click the table that you wish to replace, point to **Replace Table** and then click **With New Named Query**.</span></span>  
  
4.  <span data-ttu-id="d566a-120">В диалоговом окне **Создание именованного запроса** определите именованный запрос и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d566a-120">In the **Create Named Query** dialog box, define the named query and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="d566a-121">Сохраните измененное представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="d566a-121">Save the modified data source view.</span></span>  
  
## <a name="replace-a-table-or-named-query-with-a-table"></a><span data-ttu-id="d566a-122">Замена таблицы или именованного запроса на таблицу</span><span class="sxs-lookup"><span data-stu-id="d566a-122">Replace a table or named query with a table</span></span>  
  
1.  <span data-ttu-id="d566a-123">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект или подключитесь к базе данных, содержащей представление источника данных, в котором необходимо заменить таблицу или именованный запрос.</span><span class="sxs-lookup"><span data-stu-id="d566a-123">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to replace a table or a named query.</span></span>  
  
2.  <span data-ttu-id="d566a-124">В обозревателе решений откройте папку **Представления источников данных** , а затем дважды щелкните представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="d566a-124">In Solution Explorer, expand the **Data Source Views** folder, and then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="d566a-125">Откройте диалоговое окно **Замена таблицы другой таблицей** .</span><span class="sxs-lookup"><span data-stu-id="d566a-125">Open the **Replace Table with Other Table** dialog box.</span></span> <span data-ttu-id="d566a-126">На панели **Таблицы** либо на панели **Диаграмма** щелкните правой кнопкой мыши таблицу или именованный запрос, который необходимо заменить, укажите **Заменить таблицу** и выберите пункт **Другой таблицей**.</span><span class="sxs-lookup"><span data-stu-id="d566a-126">In either **Tables** or **Diagram** pane, right-click the table or named query that you wish to replace, point to **Replace Table** and then click **With Other Table**.</span></span>  
  
4.  <span data-ttu-id="d566a-127">В диалоговом окне **Замена таблицы другой таблицей** :</span><span class="sxs-lookup"><span data-stu-id="d566a-127">In the **Replace Table with Other Table** dialog box:</span></span>  
  
    1.  <span data-ttu-id="d566a-128">в раскрывающемся списке **Источник данных** выберите необходимый источник данных;</span><span class="sxs-lookup"><span data-stu-id="d566a-128">In the **DataSource** drop-down list box, select the desired data source</span></span>  
  
    2.  <span data-ttu-id="d566a-129">выберите таблицу, на которую необходимо заменить таблицу или именованный запрос;</span><span class="sxs-lookup"><span data-stu-id="d566a-129">Select the table with which you wish to replace the table or named query</span></span>  
  
5.  <span data-ttu-id="d566a-130">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d566a-130">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="d566a-131">Сохраните измененное представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="d566a-131">Save the modified data source view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d566a-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="d566a-132">See Also</span></span>  
 [<span data-ttu-id="d566a-133">Представления источников данных в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="d566a-133">Data Source Views in Multidimensional Models</span></span>](data-source-views-in-multidimensional-models.md)  
  
  
