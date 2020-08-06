---
title: Загрузка выхода локального пакета | Документы Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data flow [Integration Services], loading results
- loading data flow results
ms.assetid: aba8ecb7-0dcf-40d0-a2a8-64da0da94b93
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6799e593ab9d5ae1a9358bf54f4927838991ebd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740142"
---
# <a name="loading-the-output-of-a-local-package"></a><span data-ttu-id="f8a54-102">Загрузка выхода локального пакета</span><span class="sxs-lookup"><span data-stu-id="f8a54-102">Loading the Output of a Local Package</span></span>
  <span data-ttu-id="f8a54-103">Клиентские приложения могут считывать значения на выходе пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], если этот выход сохранен в назначения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с использованием [!INCLUDE[vstecado](../../includes/vstecado-md.md)], либо если выход сохранен в назначение "Неструктурированный файл" с использованием классов в пространстве имен **System.IO**.</span><span class="sxs-lookup"><span data-stu-id="f8a54-103">Client applications can read the output of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages when the output is saved to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destinations by using [!INCLUDE[vstecado](../../includes/vstecado-md.md)], or when the output is saved to a flat file destination by using the classes in the **System.IO** namespace.</span></span> <span data-ttu-id="f8a54-104">Кроме того, клиентское приложение может считывать выход пакета непосредственно из памяти, без необходимости промежуточного шага для сохранения данных.</span><span class="sxs-lookup"><span data-stu-id="f8a54-104">However, a client application can also read the output of a package directly from memory, without the need for an intermediate step to persist the data.</span></span> <span data-ttu-id="f8a54-105">Ключом к этому решению является `Microsoft.SqlServer.Dts.DtsClient` пространство имен, которое содержит специализированные реализации `IDbConnection` `IDbCommand` интерфейсов, и **IDbDataParameter** из пространства имен **System. Data** .</span><span class="sxs-lookup"><span data-stu-id="f8a54-105">The key to this solution is the `Microsoft.SqlServer.Dts.DtsClient` namespace, which contains specialized implementations of the `IDbConnection`, `IDbCommand`, and **IDbDataParameter** interfaces from the **System.Data** namespace.</span></span> <span data-ttu-id="f8a54-106">По умолчанию сборка Microsoft.SqlServer.Dts.DtsClient.dll устанавливается в каталог **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span><span class="sxs-lookup"><span data-stu-id="f8a54-106">The assembly Microsoft.SqlServer.Dts.DtsClient.dll is installed by default in **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span></span>

> [!NOTE]
>  <span data-ttu-id="f8a54-107">Для процедуры, описанной в этом разделе, необходимо, чтобы свойству DelayValidation задачи потока данных и любых родительских объектов было присвоено значение по умолчанию**False**.</span><span class="sxs-lookup"><span data-stu-id="f8a54-107">The procedure described in this topic requires that the DelayValidation property of the Data Flow task and of any parent objects be set to its default value of **False**.</span></span>

## <a name="description"></a><span data-ttu-id="f8a54-108">Описание</span><span class="sxs-lookup"><span data-stu-id="f8a54-108">Description</span></span>
 <span data-ttu-id="f8a54-109">В этой процедуре демонстрируется, как разработать на управляемом коде клиентское приложение, которое загружает выход пакета с назначением DataReader непосредственно из памяти.</span><span class="sxs-lookup"><span data-stu-id="f8a54-109">This procedure demonstrates how to develop a client application in managed code that loads the output of a package with a DataReader destination directly from memory.</span></span> <span data-ttu-id="f8a54-110">Описанные здесь шаги демонстрируются в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="f8a54-110">The steps summarized here are demonstrated in the code sample that follows.</span></span>

#### <a name="to-load-data-package-output-into-a-client-application"></a><span data-ttu-id="f8a54-111">Загрузка данных с выхода пакета в клиентское приложение</span><span class="sxs-lookup"><span data-stu-id="f8a54-111">To load data package output into a client application</span></span>

1.  <span data-ttu-id="f8a54-112">В пакете настройте назначение DataReader для получения выхода, который необходимо считать в клиентском приложении.</span><span class="sxs-lookup"><span data-stu-id="f8a54-112">In the package, configure a DataReader destination to receive the output that you want to read into the client application.</span></span> <span data-ttu-id="f8a54-113">Дайте назначению DataReader описательное имя, поскольку оно понадобится в дальнейшем для использования в клиентском приложении.</span><span class="sxs-lookup"><span data-stu-id="f8a54-113">Give the DataReader destination a descriptive name, since you will use this name later in your client application.</span></span> <span data-ttu-id="f8a54-114">Запомните имя назначения DataReader.</span><span class="sxs-lookup"><span data-stu-id="f8a54-114">Make a note of the name of the DataReader destination.</span></span>

2.  <span data-ttu-id="f8a54-115">В проекте разработки задайте ссылку на `Microsoft.SqlServer.Dts.DtsClient` пространство имен, найдя сборку **Microsoft.SqlServer.Dts.DtsClient.dll**.</span><span class="sxs-lookup"><span data-stu-id="f8a54-115">In the development project, set a reference to the `Microsoft.SqlServer.Dts.DtsClient` namespace by locating the assembly **Microsoft.SqlServer.Dts.DtsClient.dll**.</span></span> <span data-ttu-id="f8a54-116">По умолчанию эта сборка устанавливается в **C:\Program Files\Microsoft SQL Server\100\DTS\Binn**.</span><span class="sxs-lookup"><span data-stu-id="f8a54-116">By default, this assembly is installed in **C:\Program Files\Microsoft SQL Server\100\DTS\Binn**.</span></span> <span data-ttu-id="f8a54-117">Импортируйте пространство имен в код с помощью C# `Using` или [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="f8a54-117">Import the namespace into your code by using the C# `Using` or the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] `Imports` statement.</span></span>

3.  <span data-ttu-id="f8a54-118">В коде создайте объект типа `DtsClient.DtsConnection` со строкой подключения, содержащей параметры командной строки, необходимые **dtexec.exe** для запуска пакета.</span><span class="sxs-lookup"><span data-stu-id="f8a54-118">In your code, create an object of type `DtsClient.DtsConnection` with a connection string that contains the command-line parameters required by **dtexec.exe** to run the package.</span></span> <span data-ttu-id="f8a54-119">Дополнительные сведения см. в статье [dtexec Utility](../packages/dtexec-utility.md).</span><span class="sxs-lookup"><span data-stu-id="f8a54-119">For more information, see [dtexec Utility](../packages/dtexec-utility.md).</span></span> <span data-ttu-id="f8a54-120">Затем откройте соединение с помощью этой строки подключения.</span><span class="sxs-lookup"><span data-stu-id="f8a54-120">Then open the connection with this connection string.</span></span> <span data-ttu-id="f8a54-121">Можно также использовать программу **dtexecui** для создания необходимой строки подключения в визуальном режиме.</span><span class="sxs-lookup"><span data-stu-id="f8a54-121">You can also use the **dtexecui** utility to create the required connection string visually.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="f8a54-122">В образце кода демонстрируется загрузка пакета из файловой системы с использованием синтаксиса `/FILE <path and filename>`.</span><span class="sxs-lookup"><span data-stu-id="f8a54-122">The sample code demonstrates loading the package from the file system by using the `/FILE <path and filename>` syntax.</span></span> <span data-ttu-id="f8a54-123">Однако можно также загрузить пакет из базы данных MSDB с помощью синтаксиса `/SQL <package name>` или из хранилища пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] с помощью синтаксиса `/DTS \<folder name>\<package name>`.</span><span class="sxs-lookup"><span data-stu-id="f8a54-123">However you can also load the package from the MSDB database by using the `/SQL <package name>` syntax, or from the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package store by using the `/DTS \<folder name>\<package name>` syntax.</span></span>

4.  <span data-ttu-id="f8a54-124">Создайте объект типа `DtsClient.DtsCommand`, использующий ранее созданный объект `DtsConnection`, и присвойте его свойству `CommandText` в качестве значения имя назначения DataReader в пакете.</span><span class="sxs-lookup"><span data-stu-id="f8a54-124">Create an object of type `DtsClient.DtsCommand` that uses the previously created `DtsConnection` and set its `CommandText` property to the name of the DataReader destination in the package.</span></span> <span data-ttu-id="f8a54-125">Затем вызовите метод `ExecuteReader` командного объекта, чтобы загрузить результаты пакета в новое назначение DataReader.</span><span class="sxs-lookup"><span data-stu-id="f8a54-125">Then call the `ExecuteReader` method of the command object to load the package results into a new DataReader.</span></span>

5.  <span data-ttu-id="f8a54-126">При необходимости можно косвенно параметризовать выход пакета с использованием коллекции объектов `DtsDataParameter` для объекта `DtsCommand`, чтобы передать значения переменным, определенным в пакете.</span><span class="sxs-lookup"><span data-stu-id="f8a54-126">Optionally, you can indirectly parameterize the output of the package by using the collection of `DtsDataParameter` objects on the `DtsCommand` object to pass values to variables defined in the package.</span></span> <span data-ttu-id="f8a54-127">В рамках пакета можно использовать эти переменные в качестве параметров запроса или в выражениях для воздействия на результаты, возвращаемые в назначение DataReader.</span><span class="sxs-lookup"><span data-stu-id="f8a54-127">Within the package, you can use these variables as query parameters or in expressions to affect the results returned to the DataReader destination.</span></span> <span data-ttu-id="f8a54-128">Эти переменные необходимо определить в пакете в пространстве имен **DtsClient** , прежде чем их можно будет использовать с `DtsDataParameter` объектом из клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="f8a54-128">You must define these variables in the package in the **DtsClient** namespace before you can use them with the `DtsDataParameter` object from a client application.</span></span> <span data-ttu-id="f8a54-129">(Чтобы отобразить столбец **пространство имен** , может потребоваться нажать кнопку панели инструментов **Выбор столбцов переменных** в окне **переменные** .) В коде клиента при добавлении `DtsDataParameter` в `Parameters` коллекцию объекта не `DtsCommand` указывайте ссылку на пространство имен DtsClient из имени переменной.</span><span class="sxs-lookup"><span data-stu-id="f8a54-129">(You may need to click the **Choose Variable Columns** toolbar button in the **Variables** window to display the **Namespace** column.) In your client code, when you add a `DtsDataParameter` to the `Parameters` collection of the `DtsCommand`, omit the DtsClient namespace reference from the variable name.</span></span> <span data-ttu-id="f8a54-130">Пример:</span><span class="sxs-lookup"><span data-stu-id="f8a54-130">For example:</span></span>

    ```
    command.Parameters.Add(new DtsDataParameter("MyVariable", 1));
    ```

6.  <span data-ttu-id="f8a54-131">Вызовите метод `Read` назначения DataReader повторно по мере необходимости для прохождения цикла по строкам выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f8a54-131">Call the `Read` method of the DataReader repeatedly as needed to loop through the rows of output data.</span></span> <span data-ttu-id="f8a54-132">Используйте эти данные или сохраните их для дальнейшего использования в клиентском приложении.</span><span class="sxs-lookup"><span data-stu-id="f8a54-132">Use the data, or save the data for later use, in the client application.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="f8a54-133">Метод `Read` в этой реализации назначения DataReader возвращает значение `true` еще раз после считывания последней строки данных.</span><span class="sxs-lookup"><span data-stu-id="f8a54-133">The `Read` method of this implementation of the DataReader returns `true` one more time after the last row of data has been read.</span></span> <span data-ttu-id="f8a54-134">Возникают сложности с использованием обычного кода, реализующего цикл по назначению DataReader, пока метод `Read` возвращает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="f8a54-134">This makes it difficult to use the usual code that loops through the DataReader while `Read` returns `true`.</span></span> <span data-ttu-id="f8a54-135">Если пользовательским кодом предпринимается попытка закрыть назначение DataReader или соединение после считывания ожидаемого количества строк без дополнительного итогового вызова метода `Read`, будет выдано необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="f8a54-135">If your code attempts to close the DataReader or the connection after reading the expected number of rows, without an additional, final call to the `Read` method, the code will raise an unhandled exception.</span></span> <span data-ttu-id="f8a54-136">Однако если в коде предпринята попытка чтения данных в ходе этой последней итерации по циклу, метод `Read` все так же возвращает значение `true`, но после передачи последней строки кодом будет выдано необработанное исключение `ApplicationException` с сообщением, «Объект IDataReader служб SSIS находится за пределами результирующего набора».</span><span class="sxs-lookup"><span data-stu-id="f8a54-136">However, if your code attempts to read data on this final iteration through a loop, when `Read` still returns `true` but the last row has been passed, the code will raise an unhandled `ApplicationException` with the message, "The SSIS IDataReader is past the end of the resultset."</span></span> <span data-ttu-id="f8a54-137">Это поведение отличается от остальных реализаций назначения DataReader.</span><span class="sxs-lookup"><span data-stu-id="f8a54-137">This behavior is different from that of other DataReader implementations.</span></span> <span data-ttu-id="f8a54-138">Поэтому при использовании цикла для считывания строк в назначении DataReader, когда метод `Read` возвращает значение `true`, необходимо написать код для захвата, тестирования и отмены ожидаемого исключения `ApplicationException` в ходе последнего успешного вызова метода `Read`.</span><span class="sxs-lookup"><span data-stu-id="f8a54-138">Therefore, when using a loop to read through the rows in the DataReader while `Read` returns `true`, you need to write code to catch, test, and discard this anticipated `ApplicationException` on the last successful call to the `Read` method.</span></span> <span data-ttu-id="f8a54-139">Либо, если заранее известно число ожидаемых строк, можно обработать строки, а затем вызвать метод `Read` еще раз перед закрытием назначения DataReader и соединения.</span><span class="sxs-lookup"><span data-stu-id="f8a54-139">Or, if you know in advance the number of rows expected, you can process the rows, and then call the `Read` method one more time before closing the DataReader and the connection.</span></span>

7.  <span data-ttu-id="f8a54-140">Вызовите метод `Dispose` объекта `DtsCommand`.</span><span class="sxs-lookup"><span data-stu-id="f8a54-140">Call the `Dispose` method of the `DtsCommand` object.</span></span> <span data-ttu-id="f8a54-141">Это особенно важно, если были использованы какие-либо из объектов `DtsDataParameter`.</span><span class="sxs-lookup"><span data-stu-id="f8a54-141">This is particularly important if you have used any `DtsDataParameter` objects.</span></span>

8.  <span data-ttu-id="f8a54-142">Закройте назначение DataReader и объекты соединения.</span><span class="sxs-lookup"><span data-stu-id="f8a54-142">Close the DataReader and the connection objects.</span></span>

## <a name="example"></a><span data-ttu-id="f8a54-143">Пример</span><span class="sxs-lookup"><span data-stu-id="f8a54-143">Example</span></span>
 <span data-ttu-id="f8a54-144">В следующем примере выполняется пакет, который вычисляет единственное статистическое значение и сохраняет его в назначение DataReader, а затем считывает значение из DataReader и отображает его в текстовом поле в форме Windows.</span><span class="sxs-lookup"><span data-stu-id="f8a54-144">The following example runs a package that calculates a single aggregate value and saves the value to a DataReader destination, and then reads this value from the DataReader and displays the value in a text box on a Windows Form.</span></span>

 <span data-ttu-id="f8a54-145">Использование параметров не требуется при загрузке выхода пакета в клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="f8a54-145">The use of parameters is not required when loading the output of a package into a client application.</span></span> <span data-ttu-id="f8a54-146">Если вы не хотите использовать параметр, можно опустить использование переменной в пространстве имен **DtsClient** и опустить код, использующий `DtsDataParameter` объект.</span><span class="sxs-lookup"><span data-stu-id="f8a54-146">If you do not want to use a parameter, you can omit the use of the variable in the **DtsClient** namespace, and omit the code that uses the `DtsDataParameter` object.</span></span>

#### <a name="to-create-the-test-package"></a><span data-ttu-id="f8a54-147">Создание тестового пакета</span><span class="sxs-lookup"><span data-stu-id="f8a54-147">To create the test package</span></span>

1.  <span data-ttu-id="f8a54-148">Создайте новый пакет служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8a54-148">Create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="f8a54-149">В образце кода в качестве имени пакета используется «DtsClientWParamPkg.dtsx».</span><span class="sxs-lookup"><span data-stu-id="f8a54-149">The sample code uses "DtsClientWParamPkg.dtsx" as the name of the package.</span></span>

2.  <span data-ttu-id="f8a54-150">Добавьте переменную типа String в пространство имен DtsClient.</span><span class="sxs-lookup"><span data-stu-id="f8a54-150">Add a variable of type String in the DtsClient namespace.</span></span> <span data-ttu-id="f8a54-151">В образце кода в качестве имени переменной используется «Country».</span><span class="sxs-lookup"><span data-stu-id="f8a54-151">The sample code use Country as the name of the variable.</span></span> <span data-ttu-id="f8a54-152">(Может понадобиться нажать кнопку панели инструментов **Выбор столбцов переменных** в окне **Переменные**, чтобы отобразить столбец **Namespace**.)</span><span class="sxs-lookup"><span data-stu-id="f8a54-152">(You may need to click the **Choose Variable Columns** toolbar button in the **Variables** window to display the **Namespace** column.)</span></span>

3.  <span data-ttu-id="f8a54-153">Добавьте диспетчер соединений OLE DB, соединяющийся с образцом базы данных [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8a54-153">Add an OLE DB connection manager that connects to the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database.</span></span>

4.  <span data-ttu-id="f8a54-154">Добавьте задачу потока данных в пакет и переключитесь в область конструктора потока данных.</span><span class="sxs-lookup"><span data-stu-id="f8a54-154">Add a data flow task to the package and switch to the Data Flow design surface.</span></span>

5.  <span data-ttu-id="f8a54-155">Добавьте источник OLE DB в поток данных и настройте его для использования ранее созданного диспетчера соединений OLE DB, затем выполните следующую команду SQL:</span><span class="sxs-lookup"><span data-stu-id="f8a54-155">Add an OLE DB source to the data flow and configure it to use the OLE DB connection manager created previously, and the following SQL command:</span></span>

    ```
    SELECT * FROM Sales.vIndividualCustomer WHERE CountryRegionName = ?
    ```

6.  <span data-ttu-id="f8a54-156">Щелкните `Parameters` и в диалоговом окне **Установка параметров запроса** сопоставьте один входной параметр в запросе Parameter0 с переменной DtsClient:: Country.</span><span class="sxs-lookup"><span data-stu-id="f8a54-156">Click `Parameters` and, in the **Set Query Parameters** dialog box, map the single input parameter in the query, Parameter0, to the DtsClient::Country variable.</span></span>

7.  <span data-ttu-id="f8a54-157">Добавьте преобразование «Статистическая обработка» в поток данных и соедините выход источника OLE DB с этим преобразованием.</span><span class="sxs-lookup"><span data-stu-id="f8a54-157">Add an Aggregate transformation to the data flow, and connect the output of the OLE DB source to the transformation.</span></span> <span data-ttu-id="f8a54-158">Откройте редактор преобразования "Статистическая обработка" и настройте его для выполнения операции "подсчет всех" во всех входных столбцах (\*) и вывода агрегированного значения с псевдонимом Кустомеркаунт.</span><span class="sxs-lookup"><span data-stu-id="f8a54-158">Open the Aggregate Transformation Editor and configure it to perform a "Count all" operation on all input columns (\*) and to output the aggregated value with the alias CustomerCount.</span></span>

8.  <span data-ttu-id="f8a54-159">Добавьте назначение DataReader в поток данных и соедините выход преобразования «Статистическая обработка» с назначением DataReader.</span><span class="sxs-lookup"><span data-stu-id="f8a54-159">Add a DataReader destination to the data flow and connect the output of the Aggregate transformation to the DataReader destination.</span></span> <span data-ttu-id="f8a54-160">В образце кода в качестве имени назначения DataReader используется «DataReaderDest».</span><span class="sxs-lookup"><span data-stu-id="f8a54-160">The sample code uses "DataReaderDest" as the name of the DataReader.</span></span> <span data-ttu-id="f8a54-161">Укажите единственный доступный входной столбец, CustomerCount, в качестве назначения.</span><span class="sxs-lookup"><span data-stu-id="f8a54-161">Select the single available input column, CustomerCount, for the destination.</span></span>

9. <span data-ttu-id="f8a54-162">Сохраните пакет.</span><span class="sxs-lookup"><span data-stu-id="f8a54-162">Save the package.</span></span> <span data-ttu-id="f8a54-163">Тестовое приложение, которое создается далее, выполнит пакет и извлечет его выход непосредственно из памяти.</span><span class="sxs-lookup"><span data-stu-id="f8a54-163">The test application created next will run the package and retrieve its output directly from memory.</span></span>

#### <a name="to-create-the-test-application"></a><span data-ttu-id="f8a54-164">Создание тестового приложения</span><span class="sxs-lookup"><span data-stu-id="f8a54-164">To create the test application</span></span>

1.  <span data-ttu-id="f8a54-165">Создайте новое приложение Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f8a54-165">Create a new Windows Forms application.</span></span>

2.  <span data-ttu-id="f8a54-166">Добавьте ссылку на `Microsoft.SqlServer.Dts.DtsClient` пространство имен, перейдя к сборке с тем же именем в **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span><span class="sxs-lookup"><span data-stu-id="f8a54-166">Add a reference to the `Microsoft.SqlServer.Dts.DtsClient` namespace by browsing to the assembly of the same name in **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span></span>

3.  <span data-ttu-id="f8a54-167">Скопируйте и вставьте следующий образец кода в программный модуль формы.</span><span class="sxs-lookup"><span data-stu-id="f8a54-167">Copy and paste the following sample code into the code module for the form.</span></span>

4.  <span data-ttu-id="f8a54-168">Измените значение `dtexecArgs` переменной в соответствии с требованиями, чтобы она содержала параметры командной строки, необходимые **dtexec.exe** для запуска пакета.</span><span class="sxs-lookup"><span data-stu-id="f8a54-168">Modify the value of the `dtexecArgs` variable as required so that it contains the command-line parameters required by **dtexec.exe** to run the package.</span></span> <span data-ttu-id="f8a54-169">В образце кода пакет загружается из файловой системы.</span><span class="sxs-lookup"><span data-stu-id="f8a54-169">The sample code loads the package from the file system.</span></span>

5.  <span data-ttu-id="f8a54-170">Измените значение `dataReaderName` переменной в соответствии с требованиями, чтобы она содержала имя назначения DataReader в пакете.</span><span class="sxs-lookup"><span data-stu-id="f8a54-170">Modify the value of the `dataReaderName` variable as required so that it contains the name of the DataReader destination in the package.</span></span>

6.  <span data-ttu-id="f8a54-171">Поместите в форму кнопку и текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="f8a54-171">Put a button and a text box on the form.</span></span> <span data-ttu-id="f8a54-172">В примере кода используется в `btnRun` качестве имени кнопки, а в `txtResults` качестве имени текстового поля.</span><span class="sxs-lookup"><span data-stu-id="f8a54-172">The sample code uses `btnRun` as the name of the button, and `txtResults` as the name of the text box.</span></span>

7.  <span data-ttu-id="f8a54-173">Запустите приложение и нажмите кнопку.</span><span class="sxs-lookup"><span data-stu-id="f8a54-173">Run the application and click the button.</span></span> <span data-ttu-id="f8a54-174">После небольшой паузы, связанной с выполнением пакета, статистическое значение, вычисленное пакетом (количество клиентов в Канаде), должно отобразиться в текстовом поле формы.</span><span class="sxs-lookup"><span data-stu-id="f8a54-174">After a brief pause while the package runs, you should see the aggregate value calculated by the package (the count of customers in Canada) displayed in the text box on the form.</span></span>

### <a name="sample-code"></a><span data-ttu-id="f8a54-175">Пример кода</span><span class="sxs-lookup"><span data-stu-id="f8a54-175">Sample Code</span></span>

```vb
Imports System.Data
Imports Microsoft.SqlServer.Dts.DtsClient

Public Class Form1

  Private Sub btnRun_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles btnRun.Click

    Dim dtexecArgs As String
    Dim dataReaderName As String
    Dim countryName As String

    Dim dtsConnection As DtsConnection
    Dim dtsCommand As DtsCommand
    Dim dtsDataReader As IDataReader
    Dim dtsParameter As DtsDataParameter

    Windows.Forms.Cursor.Current = Cursors.WaitCursor

    dtexecArgs = "/FILE ""C:\...\DtsClientWParamPkg.dtsx"""
    dataReaderName = "DataReaderDest"
    countryName = "Canada"

    dtsConnection = New DtsConnection()
    With dtsConnection
      .ConnectionString = dtexecArgs
      .Open()
    End With

    dtsCommand = New DtsCommand(dtsConnection)
    dtsCommand.CommandText = dataReaderName

    dtsParameter = New DtsDataParameter("Country", DbType.String)
    dtsParameter.Direction = ParameterDirection.Input
    dtsCommand.Parameters.Add(dtsParameter)

    dtsParameter.Value = countryName

    dtsDataReader = dtsCommand.ExecuteReader(CommandBehavior.Default)

    With dtsDataReader
      .Read()
      txtResults.Text = .GetInt32(0).ToString("N0")
    End With

    'After reaching the end of data rows,
    ' call the Read method one more time.
    Try
      dtsDataReader.Read()
    Catch ex As Exception
      MessageBox.Show("Exception on final call to Read method:" & ControlChars.CrLf & _
      ex.Message & ControlChars.CrLf & _
      ex.InnerException.Message, "Exception on final call to Read method", _
      MessageBoxButtons.OK, MessageBoxIcon.Error)
    End Try

    ' The following method is a best practice, and is
    '  required when using DtsDataParameter objects.
    dtsCommand.Dispose()

    Try
      dtsDataReader.Close()
    Catch ex As Exception
      MessageBox.Show("Exception closing DataReader:" & ControlChars.CrLf & _
      ex.Message & ControlChars.CrLf & _
      ex.InnerException.Message, "Exception closing DataReader", _
      MessageBoxButtons.OK, MessageBoxIcon.Error)
    End Try

    Try
      dtsConnection.Close()
    Catch ex As Exception
      MessageBox.Show("Exception closing connection:" & ControlChars.CrLf & _
      ex.Message & ControlChars.CrLf & _
      ex.InnerException.Message, "Exception closing connection", _
      MessageBoxButtons.OK, MessageBoxIcon.Error)
    End Try

    Windows.Forms.Cursor.Current = Cursors.Default

  End Sub

End Class
```

```csharp
using System;
using System.Windows.Forms;
using System.Data;
using Microsoft.SqlServer.Dts.DtsClient;

namespace DtsClientWParamCS
{
  public partial class Form1 : Form
  {
    public Form1()
    {
      InitializeComponent();
      this.btnRun.Click += new System.EventHandler(this.btnRun_Click);
    }

    private void btnRun_Click(object sender, EventArgs e)
    {
      string dtexecArgs;
      string dataReaderName;
      string countryName;

      DtsConnection dtsConnection;
      DtsCommand dtsCommand;
      IDataReader dtsDataReader;
      DtsDataParameter dtsParameter;

      Cursor.Current = Cursors.WaitCursor;

      dtexecArgs = @"/FILE ""C:\...\DtsClientWParamPkg.dtsx""";
      dataReaderName = "DataReaderDest";
      countryName = "Canada";

      dtsConnection = new DtsConnection();
      {
        dtsConnection.ConnectionString = dtexecArgs;
        dtsConnection.Open();
      }

      dtsCommand = new DtsCommand(dtsConnection);
      dtsCommand.CommandText = dataReaderName;

      dtsParameter = new DtsDataParameter("Country", DbType.String);
      dtsParameter.Direction = ParameterDirection.Input;
      dtsCommand.Parameters.Add(dtsParameter);

      dtsParameter.Value = countryName;

      dtsDataReader = dtsCommand.ExecuteReader(CommandBehavior.Default);

      {
        dtsDataReader.Read();
        txtResults.Text = dtsDataReader.GetInt32(0).ToString("N0");
      }

      //After reaching the end of data rows,
      // call the Read method one more time.
      try
      {
        dtsDataReader.Read();
      }
      catch (Exception ex)
      {
        MessageBox.Show(
          "Exception on final call to Read method:\n" + ex.Message + "\n" + ex.InnerException.Message,
          "Exception on final call to Read method", MessageBoxButtons.OK, MessageBoxIcon.Error);
      }

      // The following method is a best practice, and is
      //  required when using DtsDataParameter objects.
      dtsCommand.Dispose();

      try
      {
        dtsDataReader.Close();
      }
      catch (Exception ex)
      {
        MessageBox.Show(
          "Exception closing DataReader:\n" + ex.Message + "\n" + ex.InnerException.Message,
          "Exception closing DataReader", MessageBoxButtons.OK, MessageBoxIcon.Error);
      }

      try
      {
        dtsConnection.Close();
      }
      catch (Exception ex)
      {
        MessageBox.Show(
          "Exception closing connection:\n" + ex.Message + "\n" + ex.InnerException.Message,
          "Exception closing connection", MessageBoxButtons.OK, MessageBoxIcon.Error);
      }

      Cursor.Current = Cursors.Default;

    }
  }
}
```

<span data-ttu-id="f8a54-176">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="f8a54-176">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="f8a54-177">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="f8a54-177">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="f8a54-178">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="f8a54-178">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="f8a54-179">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="f8a54-179">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8a54-180">См. также:</span><span class="sxs-lookup"><span data-stu-id="f8a54-180">See Also</span></span>
 <span data-ttu-id="f8a54-181">[Основные сведения о различиях между локальной и удаленной](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) [загрузкой и запуском локального пакета](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) программным путем к программной [загрузке и запуску удаленного пакета](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)</span><span class="sxs-lookup"><span data-stu-id="f8a54-181">[Understanding the Differences between Local and Remote Execution](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) [Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) [Loading and Running a Remote Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)</span></span>


