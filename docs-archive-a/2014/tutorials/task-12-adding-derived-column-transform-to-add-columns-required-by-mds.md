---
title: Задача 12. Добавление преобразования "производный столбец" для добавления столбцов, необходимых для MDS | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 98ccb271-04da-4126-9729-67e9a479aaef
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a4a70dd4d288e425beb2821f6b2aaf440b1d1930
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734681"
---
# <a name="task-12-adding-derived-column-transform-to-add-columns-required-by-mds"></a><span data-ttu-id="89e53-102">Задача 12. Добавление преобразования "Производный столбец" для добавления требуемых столбцов MDS</span><span class="sxs-lookup"><span data-stu-id="89e53-102">Task 12: Adding Derived Column Transform to Add Columns Required by MDS</span></span>
  <span data-ttu-id="89e53-103">В этой задаче в поток данных добавляется преобразование «Производный столбец».</span><span class="sxs-lookup"><span data-stu-id="89e53-103">In this task, you add the Derive Column Transform to the data flow.</span></span> <span data-ttu-id="89e53-104">В записи, передаваемые в это преобразование, добавляются два производных столбца **ImportType** и **BatchTag**.</span><span class="sxs-lookup"><span data-stu-id="89e53-104">You add two derived columns, **ImportType** and **BatchTag**, to the records passed to this transform.</span></span> <span data-ttu-id="89e53-105">Необходимо добавить эти столбцы перед отправкой данных в промежуточные таблицы в MDS.</span><span class="sxs-lookup"><span data-stu-id="89e53-105">You should add these columns before uploading the data to staging tables in MDS.</span></span> <span data-ttu-id="89e53-106">Это необходимые столбцы для промежуточных таблиц в MDS.</span><span class="sxs-lookup"><span data-stu-id="89e53-106">These two are required columns for the staging tables in MDS.</span></span> <span data-ttu-id="89e53-107">Дополнительные сведения см. в разделе [промежуточные таблицы конечных элементов](../master-data-services/leaf-member-staging-table-master-data-services.md) .</span><span class="sxs-lookup"><span data-stu-id="89e53-107">See [Leaf Member Staging Tables](../master-data-services/leaf-member-staging-table-master-data-services.md) for more details.</span></span>  
  
1.  <span data-ttu-id="89e53-108">Перетащите **Преобразование Производный столбец** из раздела **Общие** в **области элементов служб SSIS** на вкладку **поток данных** .</span><span class="sxs-lookup"><span data-stu-id="89e53-108">Drag-drop **Derived Column transform** from **Common** section in the **SSIS Toolbox** to the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="89e53-109">Щелкните правой кнопкой мыши преобразование « **производный столбец** » на вкладке **поток данных** и нажмите кнопку **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="89e53-109">Right-click **Derived Column** Transform in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="89e53-110">Введите **Добавить столбцы, необходимые MDS** , и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="89e53-110">Type **Add Columns Required by MDS** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="89e53-111">Подключить **дубликаты фильтра** , чтобы **Добавить столбцы, необходимые MDS** с помощью синего соединителя.</span><span class="sxs-lookup"><span data-stu-id="89e53-111">Connect **Filter Duplicates** to **Add Columns Required by MDS** using the blue connector.</span></span> <span data-ttu-id="89e53-112">Вы должны увидеть диалоговое окно **Выбор входных данных** .</span><span class="sxs-lookup"><span data-stu-id="89e53-112">You should see the **Input Output Selection** dialog box.</span></span>  
  
4.  <span data-ttu-id="89e53-113">В диалоговом окне **Выбор входных данных** выберите **уникальные записи**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="89e53-113">In the **Input Output Selection** dialog box, select **Unique Records**, and click **OK**.</span></span>  
  
     <span data-ttu-id="89e53-114">![Диалоговое окно «Выбор входов и выходов»](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-01.jpg "Диалоговое окно «Выбор входов и выходов»")</span><span class="sxs-lookup"><span data-stu-id="89e53-114">![Input Output Selection Dialog Box](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-01.jpg "Input Output Selection Dialog Box")</span></span>  
  
5.  <span data-ttu-id="89e53-115">Щелкните **SSIS** в строке меню и выберите **переменные**.</span><span class="sxs-lookup"><span data-stu-id="89e53-115">Click **SSIS** on the menu bar and click **Variables**.</span></span>  
  
6.  <span data-ttu-id="89e53-116">В окне **переменные** нажмите кнопку **Добавить переменную** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="89e53-116">In the **Variables** window, click **Add Variable** button on the toolbar.</span></span>  
  
     <span data-ttu-id="89e53-117">![Окно переменных служб SSIS](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-02.jpg "Окно переменных служб SSIS")</span><span class="sxs-lookup"><span data-stu-id="89e53-117">![SSIS Variables Window](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-02.jpg "SSIS Variables Window")</span></span>  
  
7.  <span data-ttu-id="89e53-118">Введите **ImportType** для **имени** и **2** в качестве **значения**.</span><span class="sxs-lookup"><span data-stu-id="89e53-118">Type **ImportType** for the **Name** and **2** for the **value**.</span></span> <span data-ttu-id="89e53-119">Вы задаете значение 2, поскольку требуется добавить новые элементы к сущности в MDS.</span><span class="sxs-lookup"><span data-stu-id="89e53-119">You specify the value as 2 because you want to add new members to an entity in MDS.</span></span> <span data-ttu-id="89e53-120">Дополнительные сведения об этом параметре см. в разделе [Промежуточная таблица конечного элемента](../master-data-services/leaf-member-staging-table-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="89e53-120">For details about this parameter, see [Leaf Member Staging Table](../master-data-services/leaf-member-staging-table-master-data-services.md).</span></span>  
  
8.  <span data-ttu-id="89e53-121">Снова нажмите кнопку **Добавить переменную** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="89e53-121">Click **Add Variable** toolbar button again.</span></span>  
  
9. <span data-ttu-id="89e53-122">Введите **BatchTag** в поле **имя**, выберите **строку** для **типа данных**и **еимбатч** в качестве **значения**.</span><span class="sxs-lookup"><span data-stu-id="89e53-122">Type **BatchTag** for the **Name**, select **String** for the **Data type**, and **EIMBatch** for the **Value**.</span></span> <span data-ttu-id="89e53-123">**BatchTag** — это просто уникальное имя пакета, который будет отправлен в MDS.</span><span class="sxs-lookup"><span data-stu-id="89e53-123">**BatchTag** is just a unique name for the batch you will be submitting to MDS.</span></span>  
  
10. <span data-ttu-id="89e53-124">На вкладке **поток данных** дважды щелкните **Добавить столбцы, необходимые для MDS**.</span><span class="sxs-lookup"><span data-stu-id="89e53-124">In the **Data Flow** tab, double-click **Add Columns Required by MDS**.</span></span>  
  
11. <span data-ttu-id="89e53-125">В диалоговом окне **Редактор преобразования «Производный столбец** » в **списке в нижней области**введите **ImportType** в поле **имя производного столбца**.</span><span class="sxs-lookup"><span data-stu-id="89e53-125">In the **Derived Column Transformation Editor** dialog box, in the **list box in the bottom pane**, type **ImportType** for the **Derived Column Name**.</span></span>  
  
12. <span data-ttu-id="89e53-126">Разверните узел **переменные и параметры** в верхней левой области, перетащите **пользователь:: ImportType** в столбец **выражение** .</span><span class="sxs-lookup"><span data-stu-id="89e53-126">Expand **Variables and Parameters** in the top-left pane, drag-drop **User::ImportType** to the **Expression** column.</span></span>  
  
     <span data-ttu-id="89e53-127">![редактор преобразования «Производный столбец»](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-03.jpg "редактор преобразования «Производный столбец»")</span><span class="sxs-lookup"><span data-stu-id="89e53-127">![Derived Column Transformation Editor](../../2014/tutorials/media/et-addingdcttoaddcolumnsrequiredbymds-03.jpg "Derived Column Transformation Editor")</span></span>  
  
13. <span data-ttu-id="89e53-128">Введите **BatchTag** в следующей строке для **имени производного столбца**.</span><span class="sxs-lookup"><span data-stu-id="89e53-128">Type **BatchTag** in the next row for the **Derived Column Name**.</span></span>  
  
14. <span data-ttu-id="89e53-129">Перетащите **User:: BatchTag** из **переменных и параметров** в столбец **выражение** .</span><span class="sxs-lookup"><span data-stu-id="89e53-129">Drag-drop **User::BatchTag** from **Variables and Parameters** to the **Expression** column.</span></span>  
  
15. <span data-ttu-id="89e53-130">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Преобразование «Производный столбец** ».</span><span class="sxs-lookup"><span data-stu-id="89e53-130">Click **OK** to close the **Derived Column Transformation** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="89e53-131">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="89e53-131">Next Step</span></span>  
 [<span data-ttu-id="89e53-132">Задача 13. Добавление назначения OLE DB для записи данных в промежуточную таблицу MDS</span><span class="sxs-lookup"><span data-stu-id="89e53-132">Task 13: Adding OLE DB Destination to Write Data to MDS Staging Table</span></span>](../../2014/tutorials/task-13-adding-ole-db-destination-to-write-data-to-mds-staging-table.md)  
  
  
