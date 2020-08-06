---
title: Загрузка данных с помощью назначения "OLE DB" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- loading data
- OLE DB destination [Integration Services]
- destinations [Integration Services], OLE DB
ms.assetid: 78899498-725e-4300-a7af-f983f4ea384b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 43e8d1123ae91d9e68c00fbe3e05c490383afe0c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731934"
---
# <a name="load-data-by-using-the-ole-db-destination"></a><span data-ttu-id="867d7-102">Загрузка данных с помощью назначения «OLE DB»</span><span class="sxs-lookup"><span data-stu-id="867d7-102">Load Data by Using the OLE DB Destination</span></span>
  <span data-ttu-id="867d7-103">Чтобы добавить и настроить назначение «OLE DB», в пакет уже должны быть включены хотя бы одна задача потока данных и один источник данных.</span><span class="sxs-lookup"><span data-stu-id="867d7-103">To add and configure an OLE DB destination, the package must already include at least one Data Flow task and a source.</span></span>  
  
### <a name="to-load-data-using-an-ole-db-destination"></a><span data-ttu-id="867d7-104">Загрузка данных с помощью целевого объекта OLE DB</span><span class="sxs-lookup"><span data-stu-id="867d7-104">To load data using an OLE DB destination</span></span>  
  
1.  <span data-ttu-id="867d7-105">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="867d7-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="867d7-106">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="867d7-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="867d7-107">Выберите вкладку **Поток данных** и перетащите из **области элементов**целевой объект OLE DB в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="867d7-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB destination to the design surface.</span></span>  
  
4.  <span data-ttu-id="867d7-108">Подключите назначение «OLE DB» к потоку данных, перетащив соединитель из источника данных или предыдущего преобразования на назначение.</span><span class="sxs-lookup"><span data-stu-id="867d7-108">Connect the OLE DB destination to the data flow by dragging a connector from a data source or a previous transformation to the destination.</span></span>  
  
5.  <span data-ttu-id="867d7-109">Дважды щелкните целевой объект OLE DB.</span><span class="sxs-lookup"><span data-stu-id="867d7-109">Double-click the OLE DB destination.</span></span>  
  
6.  <span data-ttu-id="867d7-110">В диалоговом окне **Редактор назначения «OLE DB»** на странице **Диспетчер соединений** выберите уже существующий диспетчер соединений OLE DB или щелкните **Создать** , чтобы создать новый.</span><span class="sxs-lookup"><span data-stu-id="867d7-110">In the **OLE DB Destination Editor** dialog box, on the **Connection Manager** page, select an existing OLE DB connection manager or click **New** to create a new connection manager.</span></span> <span data-ttu-id="867d7-111">Дополнительные сведения см. в разделе [Диспетчер соединений OLE DB](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="867d7-111">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
7.  <span data-ttu-id="867d7-112">Выберите метод доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="867d7-112">Select the data access method:</span></span>  
  
    -   <span data-ttu-id="867d7-113">**Таблица или представление** .    Выберите в базе данных таблицу или представление, содержащие данные.</span><span class="sxs-lookup"><span data-stu-id="867d7-113">**Table or view** Select a table or view in the database that contains the data.</span></span>  
  
    -   <span data-ttu-id="867d7-114">**Быстрая загрузка таблицы или представления** . Выберите в базе данных таблицу или представление, содержащие данные, а затем определите параметры быстрой загрузки: **Сохранять ИД**, **Сохранять значения NULL**, **Блокировка таблицы**, **Проверочные ограничения**, **Строк на пакет**или **Макс. фиксируемый размер вставок**.</span><span class="sxs-lookup"><span data-stu-id="867d7-114">**Table or view - fast load** Select a table or view in the database that contains the data, and then set the fast-load options: **Keep identity**, **Keep null**, **Table lock**, **Check constraint**, **Rows per batch**, or **Maximum insert commit size**.</span></span>  
  
    -   <span data-ttu-id="867d7-115">**Переменная имени представления или имени таблицы** . Выберите пользовательскую переменную, содержащую имя таблицы или представления в базе данных.</span><span class="sxs-lookup"><span data-stu-id="867d7-115">**Table name or view name variable** Select the user-defined variable that contains the name of a table or view in the database.</span></span>  
  
    -   <span data-ttu-id="867d7-116">**Быстрая загрузка переменной имени представления или имени таблицы** . Выберите пользовательскую переменную, содержащую имя таблицы или представления в базе данных, а затем определите параметры быстрой загрузки.</span><span class="sxs-lookup"><span data-stu-id="867d7-116">**Table name or view name variable fast load** Select the user-defined variable that contains the name of a table or view in the database that contains the data, and then set the fast-load options.</span></span>  
  
    -   <span data-ttu-id="867d7-117">**Команда SQL** .    Введите команду SQL или щелкните **Создать запрос** , чтобы создать команду SQL с помощью **Построителя запросов**.</span><span class="sxs-lookup"><span data-stu-id="867d7-117">**SQL command** Type an SQL command or click **Build Query** to write an SQL command by using the **Query Builder**.</span></span>  
  
8.  <span data-ttu-id="867d7-118">Щелкните **Сопоставления** и сопоставьте столбцы из списка **Доступные входные столбцы** со столбцами из списка **Доступные целевые столбцы** , перетаскивая столбцы из одного списка в другой.</span><span class="sxs-lookup"><span data-stu-id="867d7-118">Click **Mappings** and then map columns from the **Available Input Columns** list to columns in the **Available Destination Columns** list by dragging columns from one list to another.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="867d7-119">Целевой объект OLE DB автоматически свяжет столбцы с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="867d7-119">The OLE DB destination automatically maps same-named columns.</span></span>  
  
9. <span data-ttu-id="867d7-120">Чтобы настроить выход ошибок, щелкните **Вывод ошибок**.</span><span class="sxs-lookup"><span data-stu-id="867d7-120">To configure the error output, click **Error Output**.</span></span> <span data-ttu-id="867d7-121">Дополнительные сведения см. в разделе [Настройка вывода ошибок в компоненте потока данных](../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="867d7-121">For more information, see [Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
10. <span data-ttu-id="867d7-122">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="867d7-122">Click **OK**.</span></span>  
  
11. <span data-ttu-id="867d7-123">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="867d7-123">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="867d7-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="867d7-124">See Also</span></span>  
 <span data-ttu-id="867d7-125">[Назначение OLE DB](ole-db-destination.md) </span><span class="sxs-lookup"><span data-stu-id="867d7-125">[OLE DB Destination](ole-db-destination.md) </span></span>  
 <span data-ttu-id="867d7-126">[Преобразования служб Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="867d7-126">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="867d7-127">[Пути служб Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="867d7-127">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="867d7-128">Задача потока данных</span><span class="sxs-lookup"><span data-stu-id="867d7-128">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
