---
title: Задача 10. Добавление преобразования нечетких групп для обнаружения дубликатов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 90b2b323-babd-464a-8914-9dc5e66aca74
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 086625197850fdfd6381e9c0a4a7deac8ce3ae45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731209"
---
# <a name="task-10-adding-fuzzy-group-transform-to-identify-duplicates"></a><span data-ttu-id="1345f-102">Задача 10. Добавление преобразования "Нечеткое группирование" для выявления повторов</span><span class="sxs-lookup"><span data-stu-id="1345f-102">Task 10: Adding Fuzzy Group Transform to Identify Duplicates</span></span>
  <span data-ttu-id="1345f-103">В этой задаче вы добавляете в поток данных преобразование «Нечеткое группирование».</span><span class="sxs-lookup"><span data-stu-id="1345f-103">In this task, you add a Fuzzy Group Transform to the data flow.</span></span> <span data-ttu-id="1345f-104">Преобразование «Нечеткое группирование» помогает выявить повторения в исходных данных.</span><span class="sxs-lookup"><span data-stu-id="1345f-104">The Fuzzy Group transformation can help identify duplicates in the source data.</span></span> <span data-ttu-id="1345f-105">Дополнительные сведения см. в разделе [Преобразование «Нечеткое группирование](../integration-services/data-flow/transformations/fuzzy-grouping-transformation.md) ».</span><span class="sxs-lookup"><span data-stu-id="1345f-105">See [Fuzzy Grouping Transformation](../integration-services/data-flow/transformations/fuzzy-grouping-transformation.md) for more details.</span></span>  
  
1.  <span data-ttu-id="1345f-106">Перетащите **нечеткое преобразование группы** в **других преобразованиях** на **панели элементов служб SSIS** на вкладку **поток данных** в разделе **объединение правильных и исправленных записей**.</span><span class="sxs-lookup"><span data-stu-id="1345f-106">Drag-drop **Fuzzy Group** transform in **Other Transforms** on the **SSIS Toolbox** to the **Data Flow** tab under **Combine Correct and Corrected Records**.</span></span>  
  
2.  <span data-ttu-id="1345f-107">Щелкните правой кнопкой мыши преобразование **нечетких групп** на вкладке **поток данных** и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="1345f-107">Right-click **Fuzzy Group** Transform in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="1345f-108">Введите **группы поставщиков с совпадающими идентификаторами** и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="1345f-108">Type **Group Suppliers with matching IDs** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="1345f-109">Connect позволяет **объединить правильные и исправленные записи** в **группы поставщиков с совпадающими идентификаторами** с помощью синего соединителя.</span><span class="sxs-lookup"><span data-stu-id="1345f-109">Connect **Combine Correct and Corrected Records** to **Group Suppliers with matching IDs** using the blue connector.</span></span>  
  
     <span data-ttu-id="1345f-110">![Соединение с поставщиками группы с совпадающими идентификаторами](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-01.jpg "Соединение с поставщиками группы с совпадающими идентификаторами")</span><span class="sxs-lookup"><span data-stu-id="1345f-110">![Connection to Group Suppliers with Matching IDs](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-01.jpg "Connection to Group Suppliers with Matching IDs")</span></span>  
  
4.  <span data-ttu-id="1345f-111">Дважды щелкните **группы поставщики с совпадающими идентификаторами**.</span><span class="sxs-lookup"><span data-stu-id="1345f-111">Double-click **Group Suppliers with matching IDs**.</span></span>  
  
5.  <span data-ttu-id="1345f-112">В **редакторе преобразования «Нечеткое группирование**» нажмите кнопку **создать** рядом с раскрывающимся **списком OLE DB диспетчер соединений** , чтобы запустить диалоговое окно **Настройка диспетчера соединений OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="1345f-112">In the **Fuzzy Group Transformation Editor**, click **New** next to **OLE DB Connection Manager drop-down list** to launch **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
6.  <span data-ttu-id="1345f-113">В диалоговом окне нажмите кнопку **создать** , чтобы запустить диалоговое окно **Диспетчер соединений** .</span><span class="sxs-lookup"><span data-stu-id="1345f-113">In the dialog box, click **New** to launch **Connection Manager** dialog box.</span></span>  
  
7.  <span data-ttu-id="1345f-114">Введите **(local)** или **period** (.) в качестве имени сервера.</span><span class="sxs-lookup"><span data-stu-id="1345f-114">Type **(local)** or **period** (.) for the Server name.</span></span>  
  
8.  <span data-ttu-id="1345f-115">Выберите **MDS** для поля **выберите или введите имя базы данных** .</span><span class="sxs-lookup"><span data-stu-id="1345f-115">Select **MDS** for **Select or enter a database name** field.</span></span> <span data-ttu-id="1345f-116">База данных MDS будет использоваться как временное хранилище для преобразования « **Нечеткое группирование**».</span><span class="sxs-lookup"><span data-stu-id="1345f-116">You will use the MDS database as the temporary storage for the **Fuzzy Group Transform**.</span></span> <span data-ttu-id="1345f-117">Преобразование « **Нечеткое группирование** » требует соединения с экземпляром SQL Server для создания временных SQL Server таблиц, необходимых алгоритму преобразования для выполнения своей работы.</span><span class="sxs-lookup"><span data-stu-id="1345f-117">The **Fuzzy Grouping** transformation requires a connection to an instance of SQL Server to create the temporary SQL Server tables that the transformation algorithm requires to do its work.</span></span> <span data-ttu-id="1345f-118">Для этой цели вы можете создать базу данных или использовать существующую базу данных.</span><span class="sxs-lookup"><span data-stu-id="1345f-118">You can create a database or use another existing database for this purpose.</span></span>  
  
9. <span data-ttu-id="1345f-119">Нажмите кнопку **проверить подключение** , чтобы проверить подключение, и нажмите кнопку **ОК** в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="1345f-119">Click **Test Connection** to test the connection and click **OK** on the message box.</span></span>  
  
10. <span data-ttu-id="1345f-120">В диалоговом окне **Диспетчер соединений** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1345f-120">In the **Connection Manager** dialog box, click **OK**.</span></span>  
  
11. <span data-ttu-id="1345f-121">Выберите **(локальный). MDS** (или **localhost). MDS**) из **списка подключений к данным** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1345f-121">Select **(local).MDS** (or **localhost.MDS**) from the **list of Data Connections** and click **OK**.</span></span>  
  
12. <span data-ttu-id="1345f-122">В **редакторе преобразования «Нечеткое группирование**» убедитесь в том, что **(local). MDS** или \*\*localhost. \*\*Для **диспетчера соединений OLE DB**выбрано MDS.</span><span class="sxs-lookup"><span data-stu-id="1345f-122">In the **Fuzzy Grouping Transformation Editor**, confirm that **(local).MDS** or **localhost.MDS** is selected for the **OLE DB Connection Manager**.</span></span>  
  
13. <span data-ttu-id="1345f-123">Перейдите на вкладку **столбцы** .</span><span class="sxs-lookup"><span data-stu-id="1345f-123">Switch to the **Columns** tab.</span></span>  
  
14. <span data-ttu-id="1345f-124">Выберите (флажок) **SupplierID_Output** из списка **доступных входных столбцов**.</span><span class="sxs-lookup"><span data-stu-id="1345f-124">Select (check box) **SupplierID_Output** from the list of **Available Input Columns**.</span></span> <span data-ttu-id="1345f-125">Чтобы настроить преобразование, выберите входные столбцы, которые будут использоваться для поиска повторений.</span><span class="sxs-lookup"><span data-stu-id="1345f-125">To configure the transformation, select the input columns to use when identifying duplicates.</span></span> <span data-ttu-id="1345f-126">Для простоты на этом шаге используется только столбец SupplierID.</span><span class="sxs-lookup"><span data-stu-id="1345f-126">To keep it simple, you only use the SupplierID in this step.</span></span>  
  
     <span data-ttu-id="1345f-127">![редактор преобразования «Нечеткое группирование»](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-02.jpg "редактор преобразования «Нечеткое группирование»")</span><span class="sxs-lookup"><span data-stu-id="1345f-127">![Fuzzy Grouping Transformation Editor](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-02.jpg "Fuzzy Grouping Transformation Editor")</span></span>  
  
15. <span data-ttu-id="1345f-128">Нажмите кнопку **ОК** , чтобы закрыть **Редактор преобразования "Нечеткое группирование**".</span><span class="sxs-lookup"><span data-stu-id="1345f-128">Click **OK** to close the **Fuzzy Group Transformation Editor**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="1345f-129">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="1345f-129">Next Step</span></span>  
 [<span data-ttu-id="1345f-130">Задача 11. Добавление преобразования "Условное разбиение" для фильтрации повторов</span><span class="sxs-lookup"><span data-stu-id="1345f-130">Task 11: Adding Conditional Split Transform to Filter Duplicates</span></span>](../../2014/tutorials/task-11-adding-conditional-split-transform-to-filter-duplicates.md)  
  
  
