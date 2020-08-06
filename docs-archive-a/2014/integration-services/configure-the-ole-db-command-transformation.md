---
title: Настройка преобразования «Команда OLE DB» | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- parameters [Integration Services]
- OLE DB Command transformation
ms.assetid: c800f167-3d2e-4c10-8ba3-a02f1872ccea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d1714a6b798c6d8256052fd3c16bd86182480bcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738633"
---
# <a name="configure-the-ole-db-command-transformation"></a><span data-ttu-id="def03-102">настроить преобразование «Команда OLE DB»</span><span class="sxs-lookup"><span data-stu-id="def03-102">Configure the OLE DB Command Transformation</span></span>
  <span data-ttu-id="def03-103">Для добавления и настройки преобразования «Команда OLE DB» пакет должен уже содержать по меньшей мере одну задачу потока данных и такой источник, как источник неструктурированного файла или источник OLE DB.</span><span class="sxs-lookup"><span data-stu-id="def03-103">To add and configure an OLE DB Command transformation, the package must already include at least one Data Flow task and a source such as a Flat File source or an OLE DB source.</span></span> <span data-ttu-id="def03-104">Преобразование обычно используется для выполнения параметризованных запросов.</span><span class="sxs-lookup"><span data-stu-id="def03-104">This transformation is typically used for running parameterized queries.</span></span>  
  
### <a name="to-configure-the-ole-db-command-transformation"></a><span data-ttu-id="def03-105">Настройка преобразования «Команда OLE DB»</span><span class="sxs-lookup"><span data-stu-id="def03-105">To configure the OLE DB Command transformation</span></span>  
  
1.  <span data-ttu-id="def03-106">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="def03-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="def03-107">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="def03-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="def03-108">Перейдите на вкладку **Поток данных** , затем из **области элементов**переместите преобразование «Команда OLE DB» в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="def03-108">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB Command transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="def03-109">Подключите преобразование "Команда OLE DB" к потоку данных, перетащив соединитель — зеленую или красную стрелку — из источника данных или из предыдущего преобразования в преобразование "Команда OLE DB".</span><span class="sxs-lookup"><span data-stu-id="def03-109">Connect the OLE DB Command transformation to the data flow by dragging a connector-the green or red arrow-from a data source or a previous transformation to the OLE DB Command transformation.</span></span>  
  
5.  <span data-ttu-id="def03-110">Щелкните правой кнопкой мыши компонент и выберите редактировать или показать **Расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="def03-110">Right-click the component and select Edit or Show **Advanced Editor**.</span></span>  
  
6.  <span data-ttu-id="def03-111">На вкладке **Диспетчеры соединений** выберите диспетчер соединений OLE DB в списке **Диспетчер соединений** .</span><span class="sxs-lookup"><span data-stu-id="def03-111">On the **Connection Managers** tab, select an OLE DB connection manager in the **Connection Manager** list.</span></span> <span data-ttu-id="def03-112">Дополнительные сведения см. в разделе [Диспетчер соединений OLE DB](connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="def03-112">For more information, see [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span></span>  
  
7.  <span data-ttu-id="def03-113">Перейдите на вкладку **Свойства компонентов** и нажмите кнопку с многоточием **(…)** в поле **SqlCommand**.</span><span class="sxs-lookup"><span data-stu-id="def03-113">Click the **Component Properties** tab and click the ellipsis button **(...)** in the **SqlCommand** box.</span></span>  
  
8.  <span data-ttu-id="def03-114">В **редакторе строковых значений**введите параметризованную инструкцию SQL, используя знак вопроса (?) в качестве маркера параметра для каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="def03-114">In the **String Value Editor**, type the parameterized SQL statement using a question mark (?) as the parameter marker for each parameter.</span></span>  
  
9. <span data-ttu-id="def03-115">Нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="def03-115">Click **Refresh**.</span></span> <span data-ttu-id="def03-116">При нажатии кнопки **Обновить**преобразование создает столбец для каждого параметра в коллекции "Внешние столбцы" и устанавливает свойство DBParamInfoFlags.</span><span class="sxs-lookup"><span data-stu-id="def03-116">When you click **Refresh**, the transformation creates a column for each parameter in the External Columns collection and sets the DBParamInfoFlags property.</span></span>  
  
10. <span data-ttu-id="def03-117">Щелкните вкладку **Свойства входов и выходов** .</span><span class="sxs-lookup"><span data-stu-id="def03-117">Click the **Input and Output Properties** tab.</span></span>  
  
11. <span data-ttu-id="def03-118">Раскройте **Вход команды OLE DB**, затем раскройте коллекцию **Внешние столбцы**.</span><span class="sxs-lookup"><span data-stu-id="def03-118">Expand **OLE DB Command Input**, and then expand **External Columns**.</span></span>  
  
12. <span data-ttu-id="def03-119">Проверьте, что в коллекции **Внешние столбцы** перечисляются столбцы для всех параметров инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="def03-119">Verify that **External Columns** lists a column for each parameter in the SQL statement.</span></span> <span data-ttu-id="def03-120">Столбцы имеют имена **Param_0**, **Param_1**и т. д.</span><span class="sxs-lookup"><span data-stu-id="def03-120">The column names are **Param_0**, **Param_1**, and so on.</span></span>  
  
     <span data-ttu-id="def03-121">Не изменяйте имена столбцов.</span><span class="sxs-lookup"><span data-stu-id="def03-121">You should not change the column names.</span></span> <span data-ttu-id="def03-122">Если изменить имена столбцов, службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] сформирует ошибку проверки правильности для трансформации команды OLE DB.</span><span class="sxs-lookup"><span data-stu-id="def03-122">If you change the column names, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] generates a validation error for the OLE DB Command transformation.</span></span>  
  
     <span data-ttu-id="def03-123">Не изменяйте и тип данных.</span><span class="sxs-lookup"><span data-stu-id="def03-123">Also, you should not change the data type.</span></span> <span data-ttu-id="def03-124">Свойство DataType в каждом столбце устанавливается в соответствии с правильным типом данных.</span><span class="sxs-lookup"><span data-stu-id="def03-124">The DataType property of each column is set to the correct data type.</span></span>  
  
13. <span data-ttu-id="def03-125">Если в списке **Внешние столбцы** нет ни одного столбца, введите их вручную.</span><span class="sxs-lookup"><span data-stu-id="def03-125">If **External Columns** lists no columns you must add them manually.</span></span>  
  
    -   <span data-ttu-id="def03-126">Щелкните **Добавить столбец** один раз для каждого параметра в инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="def03-126">Click **Add Column** one time for each parameter in the SQL statement.</span></span>  
  
    -   <span data-ttu-id="def03-127">Переименуйте столбцы в **Param_0**, **Param_1**и т. д.</span><span class="sxs-lookup"><span data-stu-id="def03-127">Update the column names to **Param_0**, **Param_1**, and so on.</span></span>  
  
    -   <span data-ttu-id="def03-128">Укажите значение в свойстве DBParamInfoFlags.</span><span class="sxs-lookup"><span data-stu-id="def03-128">Specify a value in the DBParamInfoFlags property.</span></span> <span data-ttu-id="def03-129">Значение должно соответствовать значению перечисления OLE DB DBPARAMFLAGSENUM.</span><span class="sxs-lookup"><span data-stu-id="def03-129">The value must match a value in the OLE DB DBPARAMFLAGSENUM enumeration.</span></span> <span data-ttu-id="def03-130">Дополнительные сведения см. в справочной документации по OLE DB.</span><span class="sxs-lookup"><span data-stu-id="def03-130">For more information, see the OLE DB reference documentation.</span></span>  
  
    -   <span data-ttu-id="def03-131">Задайте тип данных столбца и в зависимости от типа данных задайте кодовую страницу, длину, точность и масштаб столбца.</span><span class="sxs-lookup"><span data-stu-id="def03-131">Specify the data type of the column and, depending on the data type, specify the code page, length, precision, and scale of the column.</span></span>  
  
    -   <span data-ttu-id="def03-132">Чтобы удалить неиспользуемый параметр, выберите параметр в коллекции **Внешние столбцы**, затем щелкните **Удалить столбец**.</span><span class="sxs-lookup"><span data-stu-id="def03-132">To delete an unused parameter, select the parameter in **External Columns**, and then click **Remove Column**.</span></span>  
  
    -   <span data-ttu-id="def03-133">Щелкните **Сопоставления столбцов** и сопоставьте столбцы в списке **Входные столбцы** с параметрами в списке **Доступные целевые столбцы** .</span><span class="sxs-lookup"><span data-stu-id="def03-133">Click **Column Mappings** and map columns in the **Available Input Columns** list to parameters in the **Available Destination Columns** list.</span></span>  
  
14. <span data-ttu-id="def03-134">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="def03-134">Click **OK**.</span></span>  
  
15. <span data-ttu-id="def03-135">Чтобы сохранить обновленный пакет, щелкните **Сохранить** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="def03-135">To save the updated package, click **Save** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="def03-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="def03-136">See Also</span></span>  
 <span data-ttu-id="def03-137">[Преобразование «OLE DB команда»](data-flow/transformations/ole-db-command-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="def03-137">[OLE DB Command Transformation](data-flow/transformations/ole-db-command-transformation.md) </span></span>  
 <span data-ttu-id="def03-138">[Преобразования служб Integration Services](data-flow/transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="def03-138">[Integration Services Transformations](data-flow/transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="def03-139">[Пути служб Integration Services](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="def03-139">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 [<span data-ttu-id="def03-140">Задача потока данных</span><span class="sxs-lookup"><span data-stu-id="def03-140">Data Flow Task</span></span>](control-flow/data-flow-task.md)  
  
  
