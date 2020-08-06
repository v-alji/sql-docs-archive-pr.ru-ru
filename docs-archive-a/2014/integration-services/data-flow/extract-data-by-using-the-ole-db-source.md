---
title: Извлечение данных с помощью источника "OLE DB" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- extracting data [Integration Services]
- sources [Integration Services], OLE DB
- OLE DB source [Integration Services]
ms.assetid: 4ca6eeb5-b60e-4b81-86dd-0674be8ae8d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 352d62cc66e3f17fb10839086e7ee9c5307f1a17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751328"
---
# <a name="extract-data-by-using-the-ole-db-source"></a><span data-ttu-id="8b322-102">Извлечение данных с помощью источника OLE DB</span><span class="sxs-lookup"><span data-stu-id="8b322-102">Extract Data by Using the OLE DB Source</span></span>
  <span data-ttu-id="8b322-103">Чтобы добавить и настроить источник OLE DB, пакет уже должен иметь по крайней мере одну задачу потока данных.</span><span class="sxs-lookup"><span data-stu-id="8b322-103">To add and configure an OLE DB source, the package must already include at least one Data Flow task.</span></span>  
  
### <a name="to-extract-data-using-an-ole-db-source"></a><span data-ttu-id="8b322-104">Извлечение данных при помощи источника OLE DB</span><span class="sxs-lookup"><span data-stu-id="8b322-104">To extract data using an OLE DB Source</span></span>  
  
1.  <span data-ttu-id="8b322-105">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="8b322-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="8b322-106">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="8b322-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="8b322-107">Щелкните вкладку **Поток данных** и перетащите источник OLE DB из **области элементов**в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="8b322-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB source to the design surface.</span></span>  
  
4.  <span data-ttu-id="8b322-108">Дважды щелкните источник OLE DB.</span><span class="sxs-lookup"><span data-stu-id="8b322-108">Double-click the OLE DB source.</span></span>  
  
5.  <span data-ttu-id="8b322-109">В диалоговом окне **Редактор источника OLE DB** на странице **Диспетчер соединений** выберите существующий диспетчер соединений OLE DB или нажмите **Создать** , чтобы создать новый диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="8b322-109">In the **OLE DB Source Editor** dialog box, on the **Connection Manager** page, select an existing OLE DB connection manager or click **New** to create a new connection manager.</span></span> <span data-ttu-id="8b322-110">Дополнительные сведения см. в разделе [Диспетчер соединений OLE DB](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="8b322-110">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
6.  <span data-ttu-id="8b322-111">Выберите метод доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="8b322-111">Select the data access method:</span></span>  
  
    -   <span data-ttu-id="8b322-112">**Таблица или представление** .   Выберите таблицу или представление в базе данных, с которой соединяется диспетчер соединений OLE DB.</span><span class="sxs-lookup"><span data-stu-id="8b322-112">**Table or view** Select a table or view in the database to which the OLE DB connection manager connects.</span></span>  
  
    -   <span data-ttu-id="8b322-113">**Переменная имени представления или имени таблицы** . Выберите пользовательскую переменную, которая содержит имя таблицы или представления в базе данных, с которой соединяется диспетчер соединений OLE DB.</span><span class="sxs-lookup"><span data-stu-id="8b322-113">**Table name or view name variable** Select the user-defined variable that contains the name of a table or view in the database to which the OLE DB connection manager connects.</span></span>  
  
    -   <span data-ttu-id="8b322-114">**Команда SQL** .   Введите команду SQL или нажмите **Создать запрос** , чтобы написать команду SQL при помощи **Построителя запросов**.</span><span class="sxs-lookup"><span data-stu-id="8b322-114">**SQL command** Type an SQL command or click **Build Query** to write an SQL command using the **Query Builder**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="8b322-115">Команда может включать параметры.</span><span class="sxs-lookup"><span data-stu-id="8b322-115">The command can include parameters.</span></span> <span data-ttu-id="8b322-116">Дополнительные сведения см. в разделе [Сопоставления параметров запросов с переменными в компонентах потока данных](map-query-parameters-to-variables-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="8b322-116">For more information, see [Map Query Parameters to Variables in a Data Flow Component](map-query-parameters-to-variables-in-a-data-flow-component.md).</span></span>  
  
    -   <span data-ttu-id="8b322-117">**Команда SQL из переменной** . Выберите пользовательскую переменную, содержащую команду SQL.</span><span class="sxs-lookup"><span data-stu-id="8b322-117">**SQL command from variable** Select the user-defined variable that contains the SQL command.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="8b322-118">Переменные должны определяться в области той же задачи потока данных, которая содержит источник OLE DB, либо в области того же пакета. Кроме того, переменная должна иметь строковый тип данных.</span><span class="sxs-lookup"><span data-stu-id="8b322-118">The variables must be defined in the scope of the same Data Flow task that contains the OLE DB source, or in the scope of the same package; additionally, the variable must have a string data type.</span></span>  
  
7.  <span data-ttu-id="8b322-119">Чтобы обновить сопоставление между внешними и выходными столбцами, щелкните **Столбцы** и выберите другие столбцы в списке **Внешний столбец** .</span><span class="sxs-lookup"><span data-stu-id="8b322-119">To update the mapping between external and output columns, click **Columns** and select different columns in the **External Column** list.</span></span>  
  
8.  <span data-ttu-id="8b322-120">Существует дополнительная возможность обновления имен выходных столбцов путем редактирования значений в списке **Выходной столбец** .</span><span class="sxs-lookup"><span data-stu-id="8b322-120">Optionally, update the names of output columns by editing values in the **Output Column** list.</span></span>  
  
9. <span data-ttu-id="8b322-121">Чтобы настроить выход ошибок, щелкните **Вывод ошибок**.</span><span class="sxs-lookup"><span data-stu-id="8b322-121">To configure the error output, click **Error Output**.</span></span> <span data-ttu-id="8b322-122">Дополнительные сведения см. в разделе [Настройка вывода ошибок в компоненте потока данных](../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="8b322-122">For more information, see [Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
10. <span data-ttu-id="8b322-123">Можно нажать **Предварительный просмотр** , чтобы просмотреть до 200 строк данных, извлеченных из источника OLE DB.</span><span class="sxs-lookup"><span data-stu-id="8b322-123">You can click **Preview** to view up to 200 rows of the data extracted by the OLE DB source.</span></span>  
  
11. <span data-ttu-id="8b322-124">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8b322-124">Click **OK**.</span></span>  
  
12. <span data-ttu-id="8b322-125">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="8b322-125">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b322-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="8b322-126">See Also</span></span>  
 <span data-ttu-id="8b322-127">[Источник OLE DB](ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="8b322-127">[OLE DB Source](ole-db-source.md) </span></span>  
 <span data-ttu-id="8b322-128">[Преобразования служб Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="8b322-128">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="8b322-129">[Пути служб Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="8b322-129">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="8b322-130">Задача потока данных</span><span class="sxs-lookup"><span data-stu-id="8b322-130">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
