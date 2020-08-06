---
title: Выполнение массовой загрузки данных с помощью назначения "SQL Server" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server destination
- loading data
- destinations [Integration Services], SQL Server
- inserting data
- bulk load [Integration Services]
ms.assetid: 8f982f85-a82e-4e2d-9cd8-cd2f85402d8e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 92ed530ae849f7a4ce123cded421ac0cd0c411ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658931"
---
# <a name="bulk-load-data-by-using-the-sql-server-destination"></a><span data-ttu-id="e16a0-102">Выполнение массовой загрузки данных с помощью назначения «SQL Server»</span><span class="sxs-lookup"><span data-stu-id="e16a0-102">Bulk Load Data by Using the SQL Server Destination</span></span>
  <span data-ttu-id="e16a0-103">Чтобы добавить и настроить назначение [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , пакет уже должен содержать как минимум одну задачу потока данных и один источник данных.</span><span class="sxs-lookup"><span data-stu-id="e16a0-103">To add and configure a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, the package must already include at least one Data Flow task and a data source.</span></span>  
  
### <a name="to-load-data-using-a-sql-server-destination"></a><span data-ttu-id="e16a0-104">Загрузка данных с помощью назначения SQL Server</span><span class="sxs-lookup"><span data-stu-id="e16a0-104">To load data using a SQL Server destination</span></span>  
  
1.  <span data-ttu-id="e16a0-105">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="e16a0-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="e16a0-106">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="e16a0-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="e16a0-107">Перейдите на вкладку **Поток данных** , затем из окна **Область элементов**перетащите назначение [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="e16a0-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination to the design surface.</span></span>  
  
4.  <span data-ttu-id="e16a0-108">Подключите назначение к источнику или предыдущему преобразованию в потоке данных, перетащив соединитель на назначение.</span><span class="sxs-lookup"><span data-stu-id="e16a0-108">Connect the destination to a source or a previous transformation in the data flow by dragging a connector to the destination.</span></span>  
  
5.  <span data-ttu-id="e16a0-109">Дважды щелкните назначение.</span><span class="sxs-lookup"><span data-stu-id="e16a0-109">Double-click the destination.</span></span>  
  
6.  <span data-ttu-id="e16a0-110">В окне **Редактор назначений SQL Server**на странице **Диспетчер соединений** выберите существующий диспетчер соединений OLE DB или нажмите кнопку **Создать** в целях создания нового диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="e16a0-110">In the **SQL Server Destination Editor**, on the **Connection Manager** page, select an existing OLE DB connection manager or click **New** to create a new connection manager.</span></span> <span data-ttu-id="e16a0-111">Дополнительные сведения см. в разделе [Диспетчер соединений OLE DB](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e16a0-111">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
7.  <span data-ttu-id="e16a0-112">Чтобы указать таблицу или представление, в которое следует загружать данные, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="e16a0-112">To specify the table or view into which to load the data, do one of the following:</span></span>  
  
    -   <span data-ttu-id="e16a0-113">Выберите существующую таблицу или представление.</span><span class="sxs-lookup"><span data-stu-id="e16a0-113">Select an existing table or view.</span></span>  
  
    -   <span data-ttu-id="e16a0-114">Нажмите кнопку **Создать**, затем в диалоговом окне **Создание таблицы** введите инструкцию SQL, которая создает таблицу или представление.</span><span class="sxs-lookup"><span data-stu-id="e16a0-114">Click **New**, and in the **Create Table** dialog boxwrite an SQL statement that creates a table or view.</span></span>  
  
        > [!NOTE]  
        >  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="e16a0-115">формируют инструкцию по умолчанию CREATE TABLE на основании подключенных источников данных.</span><span class="sxs-lookup"><span data-stu-id="e16a0-115">generates a default CREATE TABLE statement based on the connected data source.</span></span> <span data-ttu-id="e16a0-116">Эта инструкция CREATE TABLE не включает атрибут FILESTREAM, даже если исходная таблица содержит столбец, для которого объявлен атрибут FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e16a0-116">This default CREATE TABLE statement will not include the FILESTREAM attribute even if the source table includes a column with the FILESTREAM attribute declared.</span></span> <span data-ttu-id="e16a0-117">Чтобы запустить компонент служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] с атрибутом FILESTREAM, сначала следует создать хранилище FILESTREAM в целевой базе данных.</span><span class="sxs-lookup"><span data-stu-id="e16a0-117">To run an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] component with the FILESTREAM attribute, first implement FILESTREAM storage on the destination database.</span></span> <span data-ttu-id="e16a0-118">Затем добавьте атрибут FILESTREAM к инструкции CREATE TABLE в диалоговом окне **Создание таблицы** .</span><span class="sxs-lookup"><span data-stu-id="e16a0-118">Then, add the FILESTREAM attribute to the CREATE TABLE statement in the **Create Table** dialog box.</span></span> <span data-ttu-id="e16a0-119">Дополнительные сведения см. в разделе [Данные большого двоичного объекта (SQL Server)](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e16a0-119">For more information, see [Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span></span>  
  
8.  <span data-ttu-id="e16a0-120">Нажмите кнопку **Сопоставления** и сопоставьте столбцы из списка **Доступные входные столбцы** со столбцами из списка **Доступные целевые столбцы** , перетащив столбцы из одного списка в другой.</span><span class="sxs-lookup"><span data-stu-id="e16a0-120">Click **Mappings** and map columns from the **Available Input Columns** list to columns in the **Available Destination Columns** list by dragging columns from one list to another.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e16a0-121">Назначение автоматически сопоставит столбцы с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="e16a0-121">The destination automatically maps same-named columns.</span></span>  
  
9. <span data-ttu-id="e16a0-122">Нажмите кнопку **Дополнительно** и настройте параметры массовой загрузки: **Сохранять ИД**, **Сохранять значения NULL**, **Блокировка таблицы**, **Проверять ограничения**и **Запускать триггеры**.</span><span class="sxs-lookup"><span data-stu-id="e16a0-122">Click **Advanced** and set the bulk load options: **Keep identity**, **Keep nulls**, **Table lock**, **Check constraints**, and **Fire triggers**.</span></span>  
  
     <span data-ttu-id="e16a0-123">При необходимости укажите первую и последнюю входные строки для вставки, максимальное число ошибок до остановки операции вставки, а также столбцы, по которым сортируются вставляемые строки.</span><span class="sxs-lookup"><span data-stu-id="e16a0-123">Optionally, specify the first and last input rows to insert, the maximum number of errors that can occur before the insert operation stops, and the columns on which the insert is sorted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e16a0-124">Порядок сортировки определяется последовательностью, в которой перечислены столбцы.</span><span class="sxs-lookup"><span data-stu-id="e16a0-124">The sort order is determined by the order in which the columns are listed.</span></span>  
  
10. <span data-ttu-id="e16a0-125">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e16a0-125">Click **OK**.</span></span>  
  
11. <span data-ttu-id="e16a0-126">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="e16a0-126">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e16a0-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="e16a0-127">See Also</span></span>  
 <span data-ttu-id="e16a0-128">[SQL Server Destination](sql-server-destination.md) </span><span class="sxs-lookup"><span data-stu-id="e16a0-128">[SQL Server Destination](sql-server-destination.md) </span></span>  
 <span data-ttu-id="e16a0-129">[Преобразования служб Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="e16a0-129">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="e16a0-130">[Пути служб Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="e16a0-130">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="e16a0-131">Задача потока данных</span><span class="sxs-lookup"><span data-stu-id="e16a0-131">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
