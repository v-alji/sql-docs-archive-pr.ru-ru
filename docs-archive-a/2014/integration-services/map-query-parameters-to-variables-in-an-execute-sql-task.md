---
title: Сопоставьте параметры запроса с переменными в задаче «Выполнение SQL» | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- queries [Integration Services], parameter mapping
- parameterized SQL commands [Integration Services]
- parameters [Integration Services]
- mapping query parameters to variables [Integration Services]
- Execute SQL task [Integration Services]
- variables [Integration Services], mapping parameters to
ms.assetid: 6a164349-dfcf-4995-80bc-d4e7aee52a83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8511d70b40f2934680e1cb790763045c04e8204a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658878"
---
# <a name="map-query-parameters-to-variables-in-an-execute-sql-task"></a><span data-ttu-id="ab22b-102">Сопоставление параметров запроса с переменными в задаче «Выполнение SQL»</span><span class="sxs-lookup"><span data-stu-id="ab22b-102">Map Query Parameters to Variables in an Execute SQL Task</span></span>

  <span data-ttu-id="ab22b-103">Данный раздел описывает использование параметризованной инструкции SQL в задаче «Выполнение SQL» и создание сопоставлений между переменными и параметрами в инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="ab22b-103">This topic describes how to use a parameterized SQL statement in the Execute SQL task and create mappings between variables and the parameters in the SQL statement.</span></span>  
  
 <span data-ttu-id="ab22b-104">Дополнительные сведения о задаче "Выполнение SQL", маркерах параметров и именах параметров, используемых с различными типами соединений, см. в разделах [Задача "Выполнение SQL"](control-flow/execute-sql-task.md) и [Параметры и коды возврата в задаче "Выполнение SQL"](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="ab22b-104">To learn more about the Execute SQL task, the parameter markers, and parameter names you use with different connection types, see [Execute SQL Task](control-flow/execute-sql-task.md) and [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>  
  
### <a name="to-map-a-query-parameter-to-a-variable"></a><span data-ttu-id="ab22b-105">Сопоставление параметра запроса с переменной</span><span class="sxs-lookup"><span data-stu-id="ab22b-105">To map a query parameter to a variable</span></span>  
  
1.  <span data-ttu-id="ab22b-106">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте необходимый пакет служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ab22b-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package you want to work with.</span></span>  
  
2.  <span data-ttu-id="ab22b-107">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="ab22b-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="ab22b-108">Перейдите на вкладку **Поток управления** .</span><span class="sxs-lookup"><span data-stu-id="ab22b-108">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="ab22b-109">Если пакет не включает задачу «Выполнение SQL», добавьте его к потоку управления пакета.</span><span class="sxs-lookup"><span data-stu-id="ab22b-109">If the package does not already include an Execute SQL task, add one to the control flow of the package.</span></span> <span data-ttu-id="ab22b-110">Дополнительные сведения см. [в разделе Добавление или удаление задачи или контейнера в потоке управления](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) .</span><span class="sxs-lookup"><span data-stu-id="ab22b-110">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="ab22b-111">.</span><span class="sxs-lookup"><span data-stu-id="ab22b-111">.</span></span>  
  
5.  <span data-ttu-id="ab22b-112">Дважды щелкните задачу «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="ab22b-112">Double-click the Execute SQL task.</span></span>  
  
6.  <span data-ttu-id="ab22b-113">Введите параметризированную команду SQL одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="ab22b-113">Provide a parameterized SQL command in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="ab22b-114">Используйте прямой ввод и введите команду SQL в свойство SQLStatement.</span><span class="sxs-lookup"><span data-stu-id="ab22b-114">Use direct input and type the SQL command in the SQLStatement property.</span></span>  
  
    -   <span data-ttu-id="ab22b-115">Используйте прямой ввод, нажмите кнопку **Создать запрос**и создайте команду SQL, используя графические средства, предоставляемые построителем запросов.</span><span class="sxs-lookup"><span data-stu-id="ab22b-115">Use direct input, click **Build Query**, and then create an SQL command using the graphical tools that the Query Builder provides.</span></span>  
  
    -   <span data-ttu-id="ab22b-116">Используйте подключение файла и укажите ссылку на файл, содержащий команду SQL.</span><span class="sxs-lookup"><span data-stu-id="ab22b-116">Use a file connection and then reference the file that contains the SQL command.</span></span>  
  
    -   <span data-ttu-id="ab22b-117">Используйте переменную и укажите ссылку на переменную, содержащую команду SQL.</span><span class="sxs-lookup"><span data-stu-id="ab22b-117">Use a variable and then reference the variable that contains the SQL command.</span></span>  
  
     <span data-ttu-id="ab22b-118">Маркеры параметров, которые используются в параметризованных инструкциях SQL, зависят от типа соединения, используемого задачей «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="ab22b-118">The parameter markers that you use in parameterized SQL statements depend on the connection type that the Execute SQL task uses.</span></span>  
  
    |<span data-ttu-id="ab22b-119">Тип соединений</span><span class="sxs-lookup"><span data-stu-id="ab22b-119">Connection type</span></span>|<span data-ttu-id="ab22b-120">Маркер параметра</span><span class="sxs-lookup"><span data-stu-id="ab22b-120">Parameter marker</span></span>|  
    |---------------------|----------------------|  
    |<span data-ttu-id="ab22b-121">ADO</span><span class="sxs-lookup"><span data-stu-id="ab22b-121">ADO</span></span>|<span data-ttu-id="ab22b-122">?</span><span class="sxs-lookup"><span data-stu-id="ab22b-122">?</span></span>|  
    |<span data-ttu-id="ab22b-123">ADO.NET и SQLMOBILE</span><span class="sxs-lookup"><span data-stu-id="ab22b-123">ADO.NET and SQLMOBILE</span></span>|@\<parameter name>|  
    |<span data-ttu-id="ab22b-124">ODBC</span><span class="sxs-lookup"><span data-stu-id="ab22b-124">ODBC</span></span>|<span data-ttu-id="ab22b-125">?</span><span class="sxs-lookup"><span data-stu-id="ab22b-125">?</span></span>|  
    |<span data-ttu-id="ab22b-126">EXCEL и OLE DB</span><span class="sxs-lookup"><span data-stu-id="ab22b-126">EXCEL and OLE DB</span></span>|<span data-ttu-id="ab22b-127">?</span><span class="sxs-lookup"><span data-stu-id="ab22b-127">?</span></span>|  
  
     <span data-ttu-id="ab22b-128">В следующей таблице приведен список примеров команды SELECT для разных типов диспетчеров соединений.</span><span class="sxs-lookup"><span data-stu-id="ab22b-128">The following table lists examples of the SELECT command by connection manager type.</span></span> <span data-ttu-id="ab22b-129">Параметры предоставляют значения фильтра в предложениях WHERE.</span><span class="sxs-lookup"><span data-stu-id="ab22b-129">Parameters provide the filter values in the WHERE clauses.</span></span> <span data-ttu-id="ab22b-130">В примерах инструкции SELECT возвращают из таблицы **Product** базы данных [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)] продукты, для которых значение **ProductID** больше и меньше значений, указанных двумя параметрами.</span><span class="sxs-lookup"><span data-stu-id="ab22b-130">The examples use SELECT to return products from the **Product** table in [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)] that have a **ProductID** greater than and less than the values specified by two parameters.</span></span>  
  
    |<span data-ttu-id="ab22b-131">Тип соединений</span><span class="sxs-lookup"><span data-stu-id="ab22b-131">Connection type</span></span>|<span data-ttu-id="ab22b-132">Синтаксис SELECT</span><span class="sxs-lookup"><span data-stu-id="ab22b-132">SELECT syntax</span></span>|  
    |---------------------|-------------------|  
    |<span data-ttu-id="ab22b-133">EXCEL, ODBC и OLEDB</span><span class="sxs-lookup"><span data-stu-id="ab22b-133">EXCEL, ODBC, and OLEDB</span></span>|`SELECT* FROM Production.Product WHERE ProductId > ? AND ProductID < ?`|  
    |<span data-ttu-id="ab22b-134">ADO</span><span class="sxs-lookup"><span data-stu-id="ab22b-134">ADO</span></span>|`SELECT* FROM Production.Product WHERE ProductId > ? AND ProductID < ?`|  
    |[!INCLUDE[vstecado](../includes/vstecado-md.md)]|`SELECT* FROM Production.Product WHERE ProductId > @parmMinProductID AND ProductID < @parmMaxProductID`|  
  
     <span data-ttu-id="ab22b-135">Примеры использования параметров с хранимыми процедурами см. в разделе [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="ab22b-135">For examples of using parameters with stored procedures, see [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>  
  
7.  <span data-ttu-id="ab22b-136">Щелкните **Сопоставление параметров**.</span><span class="sxs-lookup"><span data-stu-id="ab22b-136">Click **Parameter Mapping**.</span></span>  
  
8.  <span data-ttu-id="ab22b-137">Чтобы добавить сопоставление параметров, нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ab22b-137">To add a parameter mapping, click **Add**.</span></span>  
  
9. <span data-ttu-id="ab22b-138">Введите имя в поле **Имя параметра** .</span><span class="sxs-lookup"><span data-stu-id="ab22b-138">Provide a name in the **Parameter Name** box.</span></span>  
  
     <span data-ttu-id="ab22b-139">Имена параметров зависят от типа соединения, используемого задачей «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="ab22b-139">The parameter names that you use depend on the connection type that the Execute SQL task uses.</span></span>  
  
    |<span data-ttu-id="ab22b-140">Тип соединений</span><span class="sxs-lookup"><span data-stu-id="ab22b-140">Connection type</span></span>|<span data-ttu-id="ab22b-141">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="ab22b-141">Parameter name</span></span>|  
    |---------------------|--------------------|  
    |<span data-ttu-id="ab22b-142">ADO</span><span class="sxs-lookup"><span data-stu-id="ab22b-142">ADO</span></span>|<span data-ttu-id="ab22b-143">Param1, Param2, …</span><span class="sxs-lookup"><span data-stu-id="ab22b-143">Param1, Param2, ...</span></span>|  
    |<span data-ttu-id="ab22b-144">ADO.NET и SQLMOBILE</span><span class="sxs-lookup"><span data-stu-id="ab22b-144">ADO.NET and SQLMOBILE</span></span>|@\<parameter name>|  
    |<span data-ttu-id="ab22b-145">ODBC</span><span class="sxs-lookup"><span data-stu-id="ab22b-145">ODBC</span></span>|<span data-ttu-id="ab22b-146">1, 2, 3, ...</span><span class="sxs-lookup"><span data-stu-id="ab22b-146">1, 2, 3, ...</span></span>|  
    |<span data-ttu-id="ab22b-147">EXCEL и OLE DB</span><span class="sxs-lookup"><span data-stu-id="ab22b-147">EXCEL and OLE DB</span></span>|<span data-ttu-id="ab22b-148">0, 1, 2, 3, ...</span><span class="sxs-lookup"><span data-stu-id="ab22b-148">0, 1, 2, 3, ...</span></span>|  
  
10. <span data-ttu-id="ab22b-149">Выберите переменную из списка **Имя переменной** .</span><span class="sxs-lookup"><span data-stu-id="ab22b-149">From the **Variable Name** list, select a variable.</span></span> <span data-ttu-id="ab22b-150">Дополнительные сведения см. в разделе [Добавление, удаление и изменение области определяемой пользователем переменной в пакете](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="ab22b-150">For more information, see [Add, Delete, Change Scope of User-Defined Variable in a Package](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span></span>  
  
11. <span data-ttu-id="ab22b-151">В списке **Направление** укажите, является ли параметр входом, выходом или возвращаемым значением.</span><span class="sxs-lookup"><span data-stu-id="ab22b-151">In the **Direction** list, specify if the parameter is an input, an output, or a return value.</span></span>  
  
12. <span data-ttu-id="ab22b-152">В списке **Тип данных** укажите тип данных параметра.</span><span class="sxs-lookup"><span data-stu-id="ab22b-152">In the **Data Type** list, set the data type of the parameter.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="ab22b-153">Тип данных параметра должен быть совместим с типом данных переменной.</span><span class="sxs-lookup"><span data-stu-id="ab22b-153">The data type of the parameter must be compatible with the data type of the variable.</span></span>  
  
13. <span data-ttu-id="ab22b-154">Повторите шаги с 8 по 11 для каждого параметра инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="ab22b-154">Repeat steps 8 through 11 for each parameter in the SQL statement.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="ab22b-155">Порядок сопоставления параметров должен соответствовать порядку, в котором параметры появляются в инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="ab22b-155">The order of parameter mappings must be the same as the order in which the parameters appear in the SQL statement.</span></span>  
  
14. <span data-ttu-id="ab22b-156">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ab22b-156">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab22b-157">См. также:</span><span class="sxs-lookup"><span data-stu-id="ab22b-157">See Also</span></span>  
 <span data-ttu-id="ab22b-158">[Задача «Выполнение SQL»](control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="ab22b-158">[Execute SQL Task](control-flow/execute-sql-task.md) </span></span>  
 <span data-ttu-id="ab22b-159">[Параметры и коды возврата в задаче «Выполнение SQL»](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="ab22b-159">[Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md) </span></span>  
 [<span data-ttu-id="ab22b-160">Переменные в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="ab22b-160">Integration Services &#40;SSIS&#41; Variables</span></span>](integration-services-ssis-variables.md)  
  
  
