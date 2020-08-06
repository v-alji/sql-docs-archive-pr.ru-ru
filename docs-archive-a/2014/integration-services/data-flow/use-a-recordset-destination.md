---
title: Использование назначения "Набора записей" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Recordset destination
ms.assetid: a7b143dc-8008-404f-83b0-b45ffbca6029
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 34d1d5a7aa76876a9d8718b691b1d24a8835e2e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667293"
---
# <a name="use-a-recordset-destination"></a><span data-ttu-id="173b9-102">использовать назначение «Набор записей»</span><span class="sxs-lookup"><span data-stu-id="173b9-102">Use a Recordset Destination</span></span>
  <span data-ttu-id="173b9-103">Назначение «Набор записей» не сохраняет данные во внешнем источнике данных.</span><span class="sxs-lookup"><span data-stu-id="173b9-103">The Recordset destination does not save data to an external data source.</span></span> <span data-ttu-id="173b9-104">Наоборот, назначение «Набор записей» сохраняет данные в памяти в наборе записей, который хранится в переменной пакета служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], относящейся к типу данных `Object`.</span><span class="sxs-lookup"><span data-stu-id="173b9-104">Instead, the Recordset destination saves data in memory in a recordset that is stored in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package variable of the `Object` data type.</span></span> <span data-ttu-id="173b9-105">После сохранения данных назначением «Набор записей», как правило, используется контейнер «цикл по каждому элементу» с перечислителем ADO по каждой строке для обработки одной строки набора записей за раз.</span><span class="sxs-lookup"><span data-stu-id="173b9-105">After the Recordset destination saves the data, you typically use a Foreach Loop container with the Foreach ADO enumerator to process one row of the recordset at a time.</span></span> <span data-ttu-id="173b9-106">Перечислитель ADO по каждой строке сохраняет значение из каждого столбца текущей строки в отдельной переменной пакета.</span><span class="sxs-lookup"><span data-stu-id="173b9-106">The Foreach ADO enumerator saves the value from each column of the current row into a separate package variable.</span></span> <span data-ttu-id="173b9-107">Затем настроенные в контейнере «цикл по каждому элементу» задания считывают эти значения из переменных и выполняют с ними ряд действий.</span><span class="sxs-lookup"><span data-stu-id="173b9-107">Then, the tasks that you configure inside the Foreach Loop container read those values from the variables and perform some action with them.</span></span>  
  
 <span data-ttu-id="173b9-108">Назначение «Набор записей» можно использовать во многих различных случаях.</span><span class="sxs-lookup"><span data-stu-id="173b9-108">You can use the Recordset destination in many different scenarios.</span></span> <span data-ttu-id="173b9-109">Ниже приведены некоторые примеры:</span><span class="sxs-lookup"><span data-stu-id="173b9-109">Here are some examples:</span></span>  
  
-   <span data-ttu-id="173b9-110">Задачу "Отправка почты" и язык выражений служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] можно использовать для отправки пользовательского сообщения электронной почты для каждой строки в наборе записей.</span><span class="sxs-lookup"><span data-stu-id="173b9-110">You can use a Send Mail task and the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language to send a customized e-mail message for each row in the recordset.</span></span>  
  
-   <span data-ttu-id="173b9-111">Компонент скрипта внутри задачи потока данных, настроенный как источник, можно использовать для считывания значений столбцов в столбцы потока данных.</span><span class="sxs-lookup"><span data-stu-id="173b9-111">You can use a Script component configured as a source, inside a Data Flow task, to read the column values into the columns of the data flow.</span></span> <span data-ttu-id="173b9-112">После этого можно использовать преобразования и назначения для преобразования и сохранения строки.</span><span class="sxs-lookup"><span data-stu-id="173b9-112">Then, you can use transformations and destinations to transform and save the row.</span></span> <span data-ttu-id="173b9-113">В приведенном примере задача потока данных выполняется один раз для каждой строки.</span><span class="sxs-lookup"><span data-stu-id="173b9-113">In this example, the Data Flow task runs once for each row.</span></span>  
  
 <span data-ttu-id="173b9-114">В следующих разделах сначала описан общий процесс использования назначения «Набор записей», а затем приводится конкретный пример использования назначения.</span><span class="sxs-lookup"><span data-stu-id="173b9-114">The following sections first describe the general process of using the Recordset destination and then show a specific example of how to use the destination.</span></span>  
  
## <a name="general-steps-to-using-a-recordset-destination"></a><span data-ttu-id="173b9-115">Общие шаги использования назначения «Набор записей»</span><span class="sxs-lookup"><span data-stu-id="173b9-115">General Steps to Using a Recordset Destination</span></span>  
 <span data-ttu-id="173b9-116">В следующей процедуре приведены шаги, которые необходимо выполнить для сохранения данных в назначении «Набор записей», а затем используется контейнер «цикл по каждому элементу» для обработки каждой строки.</span><span class="sxs-lookup"><span data-stu-id="173b9-116">The following procedure summarizes the steps that are required to save data to a Recordset destination, and then use the Foreach Loop container to process each row.</span></span>  
  
#### <a name="to-save-data-to-a-recordset-destination-and-process-each-row-by-using-the-foreach-loop-container"></a><span data-ttu-id="173b9-117">Сохранение данных в назначении «Набор записей» и обработка каждой строки при помощи контейнера «цикл по каждому элементу»</span><span class="sxs-lookup"><span data-stu-id="173b9-117">To save data to a Recordset destination and process each row by using the Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="173b9-118">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]создайте или откройте пакет служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="173b9-118">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create or open an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
2.  <span data-ttu-id="173b9-119">Создайте переменную с набором записей, сохраненным в памяти назначением «Набор записей», и задайте тип переменной `Object`.</span><span class="sxs-lookup"><span data-stu-id="173b9-119">Create a variable that will contain the recordset saved into memory by the Recordset destination, and set the variable's type to `Object`.</span></span>  
  
3.  <span data-ttu-id="173b9-120">Создайте дополнительные переменные соответствующих типов для хранения значений каждого столбца в наборе записей, который требуется использовать.</span><span class="sxs-lookup"><span data-stu-id="173b9-120">Create additional variables of the appropriate types to contain the values of each column in the recordset that you want to use.</span></span>  
  
4.  <span data-ttu-id="173b9-121">Добавьте и настройте диспетчер соединений, необходимый для источника данных, который планируется использовать в потоке данных.</span><span class="sxs-lookup"><span data-stu-id="173b9-121">Add and configure the connection manager required by the data source that you plan to use in your data flow.</span></span>  
  
5.  <span data-ttu-id="173b9-122">Добавьте к пакету задачу потока данных и на вкладке «Поток данных» конструктора служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] настройте источники и преобразования для загрузки и преобразования данных.</span><span class="sxs-lookup"><span data-stu-id="173b9-122">Add a Data Flow task to the package, and on the Data Flow tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, configure sources and transformations to load and transform the data.</span></span>  
  
6.  <span data-ttu-id="173b9-123">Добавьте назначение «Набор записей» к потоку данных и соедините его с преобразованиями.</span><span class="sxs-lookup"><span data-stu-id="173b9-123">Add a Recordset destination to the data flow and connect it to the transformations.</span></span> <span data-ttu-id="173b9-124">Для свойства `VariableName` назначения «Набор записей» введите имя переменной, созданной для хранения набора записей.</span><span class="sxs-lookup"><span data-stu-id="173b9-124">For the `VariableName` property of the Recordset destination, enter the name of the variable that you created to hold the recordset.</span></span>  
  
7.  <span data-ttu-id="173b9-125">На вкладке «Поток управления» конструктора служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] добавьте контейнер «цикл по каждому элементу» и подключите его к задаче потока данных.</span><span class="sxs-lookup"><span data-stu-id="173b9-125">On the Control Flow tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a Foreach Loop container and connect this container after the Data Flow task.</span></span> <span data-ttu-id="173b9-126">Затем откройте **Редактор циклов по каждому элементу** , чтобы настроить следующие параметры контейнера.</span><span class="sxs-lookup"><span data-stu-id="173b9-126">Then, open the **Foreach Loop Editor** to configure the container with the following settings:</span></span>  
  
    1.  <span data-ttu-id="173b9-127">На странице **Коллекция** выберите «Перечислитель ADO по каждой строке».</span><span class="sxs-lookup"><span data-stu-id="173b9-127">On the **Collection** page, select the Foreach ADO Enumerator.</span></span> <span data-ttu-id="173b9-128">Далее для параметра **Переменная источника объекта ADO**выберите переменную с набором записей.</span><span class="sxs-lookup"><span data-stu-id="173b9-128">Then, for **ADO object source variable**, select the variable that contains the recordset.</span></span>  
  
    2.  <span data-ttu-id="173b9-129">На странице **Сопоставления переменных** сопоставьте индекс (с отсчетом от нуля) каждого столбца, который требуется использовать, с соответствующей переменной.</span><span class="sxs-lookup"><span data-stu-id="173b9-129">On the **Variable Mappings** page, map the zero-based index of each column that you want to use to the appropriate variable.</span></span>  
  
         <span data-ttu-id="173b9-130">При каждой итерации цикла перечислитель заполняет эти переменные значениями столбцов из текущей строки.</span><span class="sxs-lookup"><span data-stu-id="173b9-130">On each iteration of the loop, the enumerator populates these variables with the column values from the current row.</span></span>  
  
8.  <span data-ttu-id="173b9-131">Внутри контейнера «цикл по каждому элементу» добавьте и настройте задачи обработки одной строки набора записей за раз путем считывания значений из переменных.</span><span class="sxs-lookup"><span data-stu-id="173b9-131">Inside the Foreach Loop container, add and configure tasks to process one row of the recordset at a time by reading the values from the variables.</span></span>  
  
## <a name="example-of-using-the-recordset-destination"></a><span data-ttu-id="173b9-132">Пример использования назначения «Набор записей»</span><span class="sxs-lookup"><span data-stu-id="173b9-132">Example of Using the Recordset Destination</span></span>  
 <span data-ttu-id="173b9-133">В следующем примере задача потока данных выполняет загрузку сведений о сотрудниках [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] из таблицы Sales.SalesPerson в назначение «Набор записей».</span><span class="sxs-lookup"><span data-stu-id="173b9-133">In the following example, the Data Flow task loads information about [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] employees from the Sales.SalesPerson table into a Recordset destination.</span></span> <span data-ttu-id="173b9-134">Далее контейнер «цикл по каждому элементу» считывает одну строку данных за раз и вызывает задачу «Отправка почты».</span><span class="sxs-lookup"><span data-stu-id="173b9-134">Then, a Foreach Loop container reads one row of data at a time, and calls a Send Mail task.</span></span> <span data-ttu-id="173b9-135">Задача «Отправка почты» использует выражения для того, чтобы отправить каждому менеджеру по продажам персонифицированное сообщение о размере его или ее премии.</span><span class="sxs-lookup"><span data-stu-id="173b9-135">The Send Mail task uses expressions to send a customized e-mail message to each salesperson about the amount of his or her bonus.</span></span>  
  
#### <a name="to-create-the-project-and-configure-the-variables"></a><span data-ttu-id="173b9-136">Создание проекта и настройка переменных</span><span class="sxs-lookup"><span data-stu-id="173b9-136">To create the project and configure the variables</span></span>  
  
1.  <span data-ttu-id="173b9-137">В среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]создайте новый проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="173b9-137">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="173b9-138">В меню **Службы SSIS** выберите **Переменные**.</span><span class="sxs-lookup"><span data-stu-id="173b9-138">On the **SSIS** menu, select **Variables**.</span></span>  
  
3.  <span data-ttu-id="173b9-139">В окне **Переменные** создайте переменные, которые будут содержать набор записей и значения столбцов из текущей строки.</span><span class="sxs-lookup"><span data-stu-id="173b9-139">In the **Variables** window, create the variables that will hold the recordset and the column values from the current row:</span></span>  
  
    1.  <span data-ttu-id="173b9-140">Создайте переменную с именем `BonusRecordset` и типом `Object`.</span><span class="sxs-lookup"><span data-stu-id="173b9-140">Create a variable named, `BonusRecordset`, and set its type to `Object`.</span></span>  
  
         <span data-ttu-id="173b9-141">Переменная `BonusRecordset` хранит набор записей.</span><span class="sxs-lookup"><span data-stu-id="173b9-141">The `BonusRecordset` variable holds the recordset.</span></span>  
  
    2.  <span data-ttu-id="173b9-142">Создайте переменную с именем `EmailAddress` и типом `String`.</span><span class="sxs-lookup"><span data-stu-id="173b9-142">Create a variable named, `EmailAddress`, and set its type to `String`.</span></span>  
  
         <span data-ttu-id="173b9-143">Переменная `EmailAddress` хранит адрес электронной почты менеджера по продажам.</span><span class="sxs-lookup"><span data-stu-id="173b9-143">The `EmailAddress` variable holds the salesperson's e-mail address.</span></span>  
  
    3.  <span data-ttu-id="173b9-144">Создайте переменную с именем `FirstName` и типом `String`.</span><span class="sxs-lookup"><span data-stu-id="173b9-144">Create a variable named, `FirstName`, and set its type to `String`.</span></span>  
  
         <span data-ttu-id="173b9-145">Переменная `FirstName` хранит имя менеджера по продажам.</span><span class="sxs-lookup"><span data-stu-id="173b9-145">The `FirstName` variable holds the salesperson's first name.</span></span>  
  
    4.  <span data-ttu-id="173b9-146">Создайте переменную с именем `Bonus` и типом `Double`.</span><span class="sxs-lookup"><span data-stu-id="173b9-146">Create a variable named, `Bonus`, and set its type to `Double`.</span></span>  
  
         <span data-ttu-id="173b9-147">Переменная `Bonus` хранит размер премии менеджера по продажам.</span><span class="sxs-lookup"><span data-stu-id="173b9-147">The `Bonus` variable holds the amount of the salesperson's bonus.</span></span>  
  
#### <a name="to-configure-the-connection-managers"></a><span data-ttu-id="173b9-148">Настройка диспетчеров соединений</span><span class="sxs-lookup"><span data-stu-id="173b9-148">To configure the connection managers</span></span>  
  
1.  <span data-ttu-id="173b9-149">В области «Диспетчеры соединений» конструктора служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] добавьте и настройте новый диспетчер соединений OLE DB, подключаемый к образцу базы данных [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="173b9-149">In the Connection Managers area of the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add and configure a new OLE DB connection manager that connects to the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database.</span></span>  
  
     <span data-ttu-id="173b9-150">Источник OLE DB в задаче потока данных будет использовать этот диспетчер соединений для извлечения данных.</span><span class="sxs-lookup"><span data-stu-id="173b9-150">The OLE DB source in the Data Flow task will use this connection manager to retrieve data.</span></span>  
  
2.  <span data-ttu-id="173b9-151">В области «Диспетчеры соединений» добавьте и настройте новый диспетчер соединений SMTP, подключаемый к доступному SMTP-серверу.</span><span class="sxs-lookup"><span data-stu-id="173b9-151">In the Connection Managers area, add and configure a new SMTP connection manager that connects to an available SMTP server.</span></span>  
  
     <span data-ttu-id="173b9-152">Задача «Отправка почты» внутри контейнера «цикл по каждому элементу» будет использовать этот диспетчер соединений для отправки сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="173b9-152">The Send Mail task inside the Foreach Loop container will use this connection manager to send emails.</span></span>  
  
#### <a name="to-configure-the-data-flow-and-the-recordset-destination"></a><span data-ttu-id="173b9-153">Настройка потока данных и назначения «Набор записей»</span><span class="sxs-lookup"><span data-stu-id="173b9-153">To configure the data flow and the Recordset Destination</span></span>  
  
1.  <span data-ttu-id="173b9-154">На вкладке **Поток управления** конструктора служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] добавьте в область конструктора задачу потока данных.</span><span class="sxs-lookup"><span data-stu-id="173b9-154">On the **Control Flow** tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a Data Flow task to the design surface.</span></span>  
  
2.  <span data-ttu-id="173b9-155">На вкладке **Поток данных** tab, add an OLE DB source to the Поток данных task, and then open the **Редактор источника «OLE DB»** .</span><span class="sxs-lookup"><span data-stu-id="173b9-155">On the **Data Flow** tab, add an OLE DB source to the Data Flow task, and then open the **OLE DB Source Editor.**</span></span>  
  
3.  <span data-ttu-id="173b9-156">На странице редактора **Диспетчер соединений** настройте источник со следующими параметрами.</span><span class="sxs-lookup"><span data-stu-id="173b9-156">On the **Connection Manager** page of the editor, configure the source with the following settings:</span></span>  
  
    1.  <span data-ttu-id="173b9-157">В области **Диспетчер соединений OLE DB**выберите ранее созданный диспетчер соединений OLE DB.</span><span class="sxs-lookup"><span data-stu-id="173b9-157">For **OLE DB connection manager**, select the OLE DB connection manager that you previously created.</span></span>  
  
    2.  <span data-ttu-id="173b9-158">В списке **Режим доступа к данным**выберите **Команда SQL**.</span><span class="sxs-lookup"><span data-stu-id="173b9-158">For **Data access mode**, select **SQL command**.</span></span>  
  
    3.  <span data-ttu-id="173b9-159">В области **Текст команды SQL**введите следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="173b9-159">For **SQL command text**, enter the following query:</span></span>  
  
        ```  
        SELECT     Person.Contact.EmailAddress, Person.Contact.FirstName, CONVERT(float, Sales.SalesPerson.Bonus) AS Bonus  
        FROM         Sales.SalesPerson INNER JOIN  
                              Person.Contact ON Sales.SalesPerson.SalesPersonID = Person.Contact.ContactID  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="173b9-160">Значение `currency` в столбце «Bonus» потребуется преобразовать к типу данных `float`, прежде чем его можно будет загрузить в переменную пакета типа `Double`.</span><span class="sxs-lookup"><span data-stu-id="173b9-160">You have to convert the `currency` value in the Bonus column to a `float` before you can load that value into a package variable whose type is `Double`.</span></span>  
  
4.  <span data-ttu-id="173b9-161">На вкладке **Поток данных** добавьте назначение «Набор записей» и подключитесь к назначению после источника OLE DB.</span><span class="sxs-lookup"><span data-stu-id="173b9-161">On the **Data Flow** tab, add a Recordset destination, and connect the destination after the OLE DB source.</span></span>  
  
5.  <span data-ttu-id="173b9-162">Откройте **Редактор назначения «Набор записей»** и настройте назначение со следующими параметрами.</span><span class="sxs-lookup"><span data-stu-id="173b9-162">Open the **Recordset Destination Editor**, and configure the destination with the following settings:</span></span>  
  
    1.  <span data-ttu-id="173b9-163">На вкладке **Свойства компонента** для `VariableName` Свойства выберите `User::BonusRecordset` .</span><span class="sxs-lookup"><span data-stu-id="173b9-163">On the **Component Properties** tab, for `VariableName` property, select `User::BonusRecordset`.</span></span>  
  
    2.  <span data-ttu-id="173b9-164">На вкладке **Входные столбцы** выберите все три доступных столбца.</span><span class="sxs-lookup"><span data-stu-id="173b9-164">On the **Input Columns** tab, select all three of the available columns.</span></span>  
  
#### <a name="to-configure-the-foreach-loop-container-and-run-the-package"></a><span data-ttu-id="173b9-165">Настройка контейнера «цикл по каждому элементу» и выполнение пакета</span><span class="sxs-lookup"><span data-stu-id="173b9-165">To configure the Foreach Loop container and run the package</span></span>  
  
1.  <span data-ttu-id="173b9-166">На вкладке **Поток управления** конструктора служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] добавьте контейнер «цикл по каждому элементу» и подключите его к задаче потока данных.</span><span class="sxs-lookup"><span data-stu-id="173b9-166">On the **Control Flow** tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a Foreach Loop container, and connect the container after the Data Flow task.</span></span>  
  
2.  <span data-ttu-id="173b9-167">Откройте **Редактор циклов по каждому элементу**и настройте следующие параметры контейнера.</span><span class="sxs-lookup"><span data-stu-id="173b9-167">Open the **Foreach Loop Editor**, and configure the container with the following settings:</span></span>  
  
    1.  <span data-ttu-id="173b9-168">На странице **коллекция** в поле **перечислитель**выберите **перечислитель ADO по каждому**элементу, а для **переменной источник объекта ADO**выберите `User::BonusRecordset` .</span><span class="sxs-lookup"><span data-stu-id="173b9-168">On the **Collection** page, for **Enumerator**, select **Foreach ADO Enumerator**, and for **ADO object source variable**, select `User::BonusRecordset`.</span></span>  
  
    2.  <span data-ttu-id="173b9-169">На странице **сопоставления переменных** сопоставьте `User::EmailAddress` с индексу 0, `User::FirstName` индексу 1 и `User::Bonus` индексу 2.</span><span class="sxs-lookup"><span data-stu-id="173b9-169">On the **Variable Mappings** page, map `User::EmailAddress` to index 0, `User::FirstName` to index 1, and `User::Bonus` to index 2.</span></span>  
  
3.  <span data-ttu-id="173b9-170">На вкладке **Поток управления** внутри контейнера «цикл по каждому элементу» добавьте задачу «Отправка почты».</span><span class="sxs-lookup"><span data-stu-id="173b9-170">On the **Control Flow** tab, inside the Foreach Loop container, add a Send Mail task.</span></span>  
  
4.  <span data-ttu-id="173b9-171">Откройте **Редактор задачи «Отправка почты»** и на странице **Почта** настройте следующие параметры задачи.</span><span class="sxs-lookup"><span data-stu-id="173b9-171">Open the **Send Mail Task Editor**, and then on the **Mail** page, configure the task with the following settings:</span></span>  
  
    1.  <span data-ttu-id="173b9-172">В области **SmtpConnection**выберите ранее настроенный диспетчер соединений SMTP.</span><span class="sxs-lookup"><span data-stu-id="173b9-172">For **SmtpConnection**, select the SMTP connection manager that was configured previously.</span></span>  
  
    2.  <span data-ttu-id="173b9-173">В поле **От**введите соответствующий адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="173b9-173">For **From**, enter an appropriate e-mail address.</span></span>  
  
         <span data-ttu-id="173b9-174">Если указать собственный адрес электронной почты, то можно будет проверить успешность выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="173b9-174">If you use your own e-mail address, you will be able to confirm that the package runs successfully.</span></span> <span data-ttu-id="173b9-175">Будут получены подтверждения о невозможности доставить сообщения, отправленные задачей «Отправка почты» несуществующим менеджерам по продажам [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="173b9-175">You will receive undeliverable receipts for the messages sent by the Send Mail task to the fictitious salespersons of [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span></span>  
  
    3.  <span data-ttu-id="173b9-176">В поле **Кому**введите адрес электронной почты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="173b9-176">For **To**, enter a default e-mail address.</span></span>  
  
         <span data-ttu-id="173b9-177">Это значение не будет использовано, а будет заменено во время выполнения адресом электронной почты каждого менеджера по продажам.</span><span class="sxs-lookup"><span data-stu-id="173b9-177">This value will not be used, but will be replaced at run time by the e-mail address of each salesperson.</span></span>  
  
    4.  <span data-ttu-id="173b9-178">В поле **Тема**введите «Ваша годовая премия».</span><span class="sxs-lookup"><span data-stu-id="173b9-178">For **Subject**, enter "Your annual bonus".</span></span>  
  
    5.  <span data-ttu-id="173b9-179">Для параметра **MessageSourceType**выберите значение **Прямой ввод**.</span><span class="sxs-lookup"><span data-stu-id="173b9-179">For **MessageSourceType**, select **Direct Input**.</span></span>  
  
5.  <span data-ttu-id="173b9-180">На странице **Выражения** окна **Редактор задачи "Отправка почты"** нажмите кнопку с многоточием ( **…** ), чтобы открыть **Редактор выражений свойств**.</span><span class="sxs-lookup"><span data-stu-id="173b9-180">On the **Expressions** page of the **Send Mail Task Editor**, click the ellipsis button (**...**) to open the **Property Expressions Editor**.</span></span>  
  
6.  <span data-ttu-id="173b9-181">В **Редакторе выражений свойств**введите следующие данные.</span><span class="sxs-lookup"><span data-stu-id="173b9-181">In the **Property Expressions Editor**, enter the following information:</span></span>  
  
    1.  <span data-ttu-id="173b9-182">В поле **ToLine**добавьте следующее выражение:</span><span class="sxs-lookup"><span data-stu-id="173b9-182">For **ToLine**, add the following expression:</span></span>  
  
        ```  
        @[User::EmailAddress]  
        ```  
  
    2.  <span data-ttu-id="173b9-183">Для свойства **MessageSource** добавьте следующее выражение:</span><span class="sxs-lookup"><span data-stu-id="173b9-183">For the **MessageSource** property, add the following expression:</span></span>  
  
        ```  
        "Dear " +  @[User::FirstName] + ": The amount of your bonus for this year is $" +  (DT_WSTR, 12) @[User::Bonus] + ". Thank you!"  
        ```  
  
7.  <span data-ttu-id="173b9-184">Запустите пакет.</span><span class="sxs-lookup"><span data-stu-id="173b9-184">Run the package.</span></span>  
  
     <span data-ttu-id="173b9-185">Если был указан допустимый SMTP-сервер и задан собственный адрес электронной почты, будут получены подтверждения о невозможности отправки сообщений задачей «Отправка почты» вымышленным менеджерам по продажам [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="173b9-185">If you have specified a valid SMTP server and provided your own e-mail address, you will receive undeliverable receipts for the messages that the Send Mail task sends to the fictitious salespersons of [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span></span>  
  
  
