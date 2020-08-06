---
title: Получение и интерпретация измененных данных | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],retrieving data
ms.assetid: af366697-6942-42bb-aea5-18fdef018965
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 62f60bf4a79c39b4f0cb7d1ba8fb3f52680a1f11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735517"
---
# <a name="retrieve-and-understand-the-change-data"></a><span data-ttu-id="3e132-102">Получение и интерпретация измененных данных</span><span class="sxs-lookup"><span data-stu-id="3e132-102">Retrieve and Understand the Change Data</span></span>
  <span data-ttu-id="3e132-103">В потоке данных пакета служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , выполняющего добавочную загрузку измененных данных, первая задача — выполнение запроса, который получает информацию об изменениях.</span><span class="sxs-lookup"><span data-stu-id="3e132-103">In the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the first task is to run the query that retrieves the change data.</span></span> <span data-ttu-id="3e132-104">Этот запрос выполняется внутри исходного компонента задачи потока данных.</span><span class="sxs-lookup"><span data-stu-id="3e132-104">You execute this query inside a source component in a Data Flow task.</span></span> <span data-ttu-id="3e132-105">Затем можно использовать нисходящие преобразования и назначения, чтобы применить данные об изменениях к назначению.</span><span class="sxs-lookup"><span data-stu-id="3e132-105">You can then use downstream transformations and destinations to apply the change data to your destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e132-106">Создание запроса, содержащего возвращающую табличное значение функцию, является третьим шагом в процессе создания пакета, который осуществляет добавочную загрузку измененных данных.</span><span class="sxs-lookup"><span data-stu-id="3e132-106">The creation of a query that contains a table-valued function is the third step in the process of creating a package that performs an incremental load of change data.</span></span> <span data-ttu-id="3e132-107">Дополнительные сведения об этом запросе см. в разделе [Создание функции для получения информации об изменениях](create-the-function-to-retrieve-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="3e132-107">For more information about this query, see, [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md).</span></span> <span data-ttu-id="3e132-108">Описание общего процесса создания пакета, выполняющего добавочную загрузку информации об изменениях, см. в разделе [Система отслеживания измененных данных (SSIS)](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="3e132-108">For a description of the overall process for creating a package that performs an incremental load of change data, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="adding-the-data-flow-task"></a><span data-ttu-id="3e132-109">Добавление задачи потока данных</span><span class="sxs-lookup"><span data-stu-id="3e132-109">Adding the Data Flow Task</span></span>  
 <span data-ttu-id="3e132-110">В потоке данных пакета получаются измененные данные, отдельные строки на основе типа произошедших изменений, а затем изменения применяются к назначению.</span><span class="sxs-lookup"><span data-stu-id="3e132-110">In the data flow of the package, you retrieve the change data, separate the rows based on the type of change that occurred, and then apply the changes to the destination.</span></span>  
  
#### <a name="to-add-a-data-flow-task-to-the-package"></a><span data-ttu-id="3e132-111">Добавление задачи потока данных к пакету</span><span class="sxs-lookup"><span data-stu-id="3e132-111">To add a Data Flow task to the package</span></span>  
  
1.  <span data-ttu-id="3e132-112">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]на вкладке **Поток управления** добавьте задачу потока данных.</span><span class="sxs-lookup"><span data-stu-id="3e132-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Control Flow** tab, add a Data Flow task.</span></span>  
  
2.  <span data-ttu-id="3e132-113">Соедините предыдущую задачу, подготовившую строку запроса, с задачей потока данных.</span><span class="sxs-lookup"><span data-stu-id="3e132-113">Connect the preceding task that prepared the query string to the Data Flow task.</span></span>  
  
## <a name="configuring-the-source-component-to-query-for-changes"></a><span data-ttu-id="3e132-114">Настройка исходного компонента для выполнения запроса об изменениях</span><span class="sxs-lookup"><span data-stu-id="3e132-114">Configuring the Source Component to Query for Changes</span></span>  
 <span data-ttu-id="3e132-115">С помощью подготовленной и сохраненной в переменной строки запроса исходный компонент вызывает возвращающую табличное значение функцию, которая получает измененные данные.</span><span class="sxs-lookup"><span data-stu-id="3e132-115">The source component uses the query string that was prepared and stored in a variable to calls the table-valued function that retrieves the changed data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e132-116">Дополнительные сведения о подготовленной и сохраненной в переменной строке запроса см. в разделе [Подготовка к запросу информации об изменениях](prepare-to-query-for-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="3e132-116">For more information about the query string that was prepared and stored in a variable, see [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md).</span></span> <span data-ttu-id="3e132-117">Дополнительные сведения о возвращающей табличное значение функции, которая получает данные об изменениях, см. в разделе [Создание функции для получения информации об изменениях](create-the-function-to-retrieve-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="3e132-117">For more information about the table-valued function that retrieves the change data, see [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md).</span></span>  
  
#### <a name="to-configure-an-ole-db-source-to-retrieve-the-change-data"></a><span data-ttu-id="3e132-118">Настройка источника OLE DB для получения измененных данных.</span><span class="sxs-lookup"><span data-stu-id="3e132-118">To configure an OLE DB source to retrieve the change data</span></span>  
  
1.  <span data-ttu-id="3e132-119">На вкладке [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]Поток данных **среды** добавьте источник OLE DB.</span><span class="sxs-lookup"><span data-stu-id="3e132-119">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Data Flow** tab, add an OLE DB source.</span></span>  
  
2.  <span data-ttu-id="3e132-120">На странице **Диспетчер соединений**в области **Редактор источника OLE DB** установите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="3e132-120">In the **OLE DB Source Editor**, on the **Connection Manager** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="3e132-121">Настройте допустимое соединение с базой данных-источником.</span><span class="sxs-lookup"><span data-stu-id="3e132-121">Configure a valid connection to the source database.</span></span>  
  
    2.  <span data-ttu-id="3e132-122">В списке **Режим доступа к данным**выберите **Команда SQL из переменной**.</span><span class="sxs-lookup"><span data-stu-id="3e132-122">For **Data access mode**, select **SQL command from variable**.</span></span>  
  
    3.  <span data-ttu-id="3e132-123">В поле **Имя переменной**выберите **User::SqlDataQuery**.</span><span class="sxs-lookup"><span data-stu-id="3e132-123">For **Variable name**, select **User::SqlDataQuery**.</span></span>  
  
3.  <span data-ttu-id="3e132-124">В области **Редактор источника OLE DB**на странице **Столбцы** убедитесь, чтобы все необходимые столбцы были сопоставлены с выходными столбцами.</span><span class="sxs-lookup"><span data-stu-id="3e132-124">In the **OLE DB Source Editor**, on the **Columns** page, make sure that all the columns that you want are mapped to output columns.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="3e132-125">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="3e132-125">Next Step</span></span>  
 <span data-ttu-id="3e132-126">После настройки источника OLE DB для получения измененных данных начинается проектирование потока данных в пакете.</span><span class="sxs-lookup"><span data-stu-id="3e132-126">After you have configured an OLE DB source to retrieve the change data, the next step is to start designing the data flow in the package.</span></span>  
  
 <span data-ttu-id="3e132-127">**Следующая статья:** [Обработка операций вставки, обновления и удаления](process-inserts-updates-and-deletes.md)</span><span class="sxs-lookup"><span data-stu-id="3e132-127">**Next topic:** [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md)</span></span>  
  
  
