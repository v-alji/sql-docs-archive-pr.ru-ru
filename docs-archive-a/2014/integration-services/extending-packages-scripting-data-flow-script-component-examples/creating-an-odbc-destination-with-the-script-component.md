---
title: Создание назначения ODBC с помощью компонента скрипта | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], destination components
- ODBC destination [Integration Services]
- destinations [Integration Services], components
- Script component [Integration Services], examples
ms.assetid: d198c866-78f4-4a50-ae15-333160645815
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 10adff11a7e1db24d9a244c3e83949a010b606c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665438"
---
# <a name="creating-an-odbc-destination-with-the-script-component"></a><span data-ttu-id="0cd47-102">Создание назначения ODBC с помощью компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="0cd47-102">Creating an ODBC Destination with the Script Component</span></span>
  <span data-ttu-id="0cd47-103">В службах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], как правило, сохранение данных в назначение ODBC осуществляется с использованием назначения [!INCLUDE[vstecado](../../includes/vstecado-md.md)] и поставщика данных платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] для ODBC.</span><span class="sxs-lookup"><span data-stu-id="0cd47-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you typically save data to an ODBC destination by using an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination and the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Data Provider for ODBC.</span></span> <span data-ttu-id="0cd47-104">Однако можно также создать нерегламентированное назначение ODBC для использования в отдельном пакете.</span><span class="sxs-lookup"><span data-stu-id="0cd47-104">However, you can also create an ad hoc ODBC destination for use in a single package.</span></span> <span data-ttu-id="0cd47-105">Для создания такого нерегламентированного назначения ODBC используется компонент скрипта, показанный в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0cd47-105">To create this ad hoc ODBC destination, you use the Script component as shown in the following example.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0cd47-106">Если нужно создать компонент, который будет полезен в нескольких задачах потока данных и нескольких пакетах, рекомендуется в качестве основы использовать этот образец компонента скрипта.</span><span class="sxs-lookup"><span data-stu-id="0cd47-106">If you want to create a component that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in this Script component sample as the starting point for a custom data flow component.</span></span> <span data-ttu-id="0cd47-107">Дополнительные сведения см. в разделе [Разработка пользовательского компонента потока данных](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="0cd47-107">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0cd47-108">Пример</span><span class="sxs-lookup"><span data-stu-id="0cd47-108">Example</span></span>  
 <span data-ttu-id="0cd47-109">В следующем примере демонстрируется, как создать целевой компонент, который использует существующий диспетчер подключений ODBC для сохранения данных из потока данных в таблицу [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cd47-109">The following example demonstrates how to create a destination component that uses an existing ODBC connection manager to save data from the data flow into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="0cd47-110">Этот пример представляет собой измененную версию пользовательского назначения [!INCLUDE[vstecado](../../includes/vstecado-md.md)], приведенного ранее в разделе [Создание назначения с помощью компонента скрипта](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="0cd47-110">This example is a modified version of the custom [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination that was demonstrated in the topic, [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span></span> <span data-ttu-id="0cd47-111">Однако в данном примере пользовательское назначение [!INCLUDE[vstecado](../../includes/vstecado-md.md)] изменено для работы с диспетчером соединений ODBC и сохранения данных в назначение ODBC.</span><span class="sxs-lookup"><span data-stu-id="0cd47-111">However, in this example, the custom [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination has been modified to work with an ODBC connection manager and save data to an ODBC destination.</span></span> <span data-ttu-id="0cd47-112">Были внесены, в частности, следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="0cd47-112">These modifications also include the following changes:</span></span>  
  
-   <span data-ttu-id="0cd47-113">Нельзя вызывать метод `AcquireConnection` диспетчера соединений ODBC из управляемого кода, поскольку при этом возвращается собственный объект.</span><span class="sxs-lookup"><span data-stu-id="0cd47-113">You cannot call the `AcquireConnection` method of the ODBC connection manager from managed code, because it returns a native object.</span></span> <span data-ttu-id="0cd47-114">Поэтому в данном образце строка соединения диспетчера соединений используется для соединения с источником данных непосредственно с помощью управляемого поставщика данных ODBC платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cd47-114">Therefore, this sample uses the connection string of the connection manager to connect to the data source directly by using the managed ODBC [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Data Provider.</span></span>  
  
-   <span data-ttu-id="0cd47-115">Команда `OdbcCommand` ожидает позиционированных параметров.</span><span class="sxs-lookup"><span data-stu-id="0cd47-115">The `OdbcCommand` expects positional parameters.</span></span> <span data-ttu-id="0cd47-116">Позиции параметров отмечаются вопросительными знаками (?) в тексте команды.</span><span class="sxs-lookup"><span data-stu-id="0cd47-116">The positions of the parameters are indicated by the question marks (?) in the text of the command.</span></span> <span data-ttu-id="0cd47-117">(Команда `SqlCommand`, напротив, ожидает именованных параметров.)</span><span class="sxs-lookup"><span data-stu-id="0cd47-117">(In contrast, a `SqlCommand` expects named parameters.)</span></span>  
  
 <span data-ttu-id="0cd47-118">В этом примере используется таблица **Person.Address** из образца базы данных **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="0cd47-118">This example uses the **Person.Address** table in the **AdventureWorks** sample database.</span></span> <span data-ttu-id="0cd47-119">В примере в потоке данных передаются первый и четвертый столбцы ( **int \* AddressID**\* и **nvarchar (30) City)** этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="0cd47-119">The example passes the first and fourth columns, the **int\*AddressID**\* and **nvarchar(30)City** columns, of this table through the data flow.</span></span> <span data-ttu-id="0cd47-120">Эти же данные используются в образцах источника, преобразования и назначения в разделе [Разработка определенных типов компонента скрипта](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span><span class="sxs-lookup"><span data-stu-id="0cd47-120">This same data is used in the source, transformation, and destination samples in the topic, [Developing Specific Types of Script Components](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="0cd47-121">Настройка этого примера компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="0cd47-121">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="0cd47-122">Создайте диспетчер подключений ODBC, который соединяется с базой данных **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="0cd47-122">Create an ODBC connection manager that connects to the **AdventureWorks** database.</span></span>  
  
2.  <span data-ttu-id="0cd47-123">Создайте целевую таблицу, выполнив следующую команду Transact-SQL в базе данных **AdventureWorks**:</span><span class="sxs-lookup"><span data-stu-id="0cd47-123">Create a destination table by running the following Transact-SQL command in the **AdventureWorks** database:</span></span>  
  
    ```  
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,  
        [City] [nvarchar](30) NOT NULL)  
    ```  
  
3.  <span data-ttu-id="0cd47-124">Добавьте новый компонент скрипта в область конструктора потока данных и настройте его в качестве назначения.</span><span class="sxs-lookup"><span data-stu-id="0cd47-124">Add a new Script component to the Data Flow designer surface and configure it as a destination.</span></span>  
  
4.  <span data-ttu-id="0cd47-125">Соедините выход источника или преобразования, расположенного выше в потоке данных, с компонентом назначения в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cd47-125">Connect the output of an upstream source or transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="0cd47-126">(Можно соединить источник непосредственно с назначением, не выполняя никаких преобразований.) Чтобы обеспечить работу этого образца, нужно включить в выход вышестоящего компонента, по меньшей мере, столбцы **AddressID** и **City** из таблицы **Person.Address** образца базы данных **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="0cd47-126">(You can connect a source directly to a destination without any transformations.) To ensure that this sample works, the output of the upstream component must include at least the **AddressID** and **City** columns from the **Person.Address** table of the **AdventureWorks** sample database.</span></span>  
  
5.  <span data-ttu-id="0cd47-127">Откройте **редактор преобразования "Скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="0cd47-127">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="0cd47-128">На странице **Входные столбцы** выберите столбцы **AddressID** и **City**.</span><span class="sxs-lookup"><span data-stu-id="0cd47-128">On the **Input Columns** page, select the **AddressID** and **City** columns.</span></span>  
  
6.  <span data-ttu-id="0cd47-129">На странице **Входы и выходы** измените имя входа на более описательное, например **ВходАдреса**.</span><span class="sxs-lookup"><span data-stu-id="0cd47-129">On the **Inputs and Outputs** page, rename the input with a more descriptive name such as **MyAddressInput**.</span></span>  
  
7.  <span data-ttu-id="0cd47-130">На странице **Диспетчеры соединений** добавьте или создайте диспетчер подключений ODBC с описательным именем, например **ДиспетчерПодключенийODBC**.</span><span class="sxs-lookup"><span data-stu-id="0cd47-130">On the **Connection Managers** page, add or create the ODBC connection manager with a descriptive name such as **MyODBCConnectionManager**.</span></span>  
  
8.  <span data-ttu-id="0cd47-131">На странице **Скрипт** нажмите кнопку **изменить скрипт**, а затем введите скрипт, показанный ниже в `ScriptMain` классе.</span><span class="sxs-lookup"><span data-stu-id="0cd47-131">On the **Script** page, click **Edit Script**, and then enter the script shown below in the `ScriptMain` class.</span></span>  
  
9. <span data-ttu-id="0cd47-132">Закройте среду разработки скриптов и **редактор преобразования "Скрипт"** , затем выполните образец.</span><span class="sxs-lookup"><span data-stu-id="0cd47-132">Close the script development environment, close the **Script Transformation Editor**, and then run the sample.</span></span>  
  
    ```vb  
    Imports System.Data.Odbc  
    ...  
    Public Class ScriptMain  
        Inherits UserComponent  
  
        Dim odbcConn As OdbcConnection  
        Dim odbcCmd As OdbcCommand  
        Dim odbcParam As OdbcParameter  
  
        Public Overrides Sub AcquireConnections(ByVal Transaction As Object)  
  
            Dim connectionString As String  
            connectionString = Me.Connections.MyODBCConnectionManager.ConnectionString  
            odbcConn = New OdbcConnection(connectionString)  
            odbcConn.Open()  
  
        End Sub  
  
        Public Overrides Sub PreExecute()  
  
            odbcCmd = New OdbcCommand("INSERT INTO Person.Address2(AddressID, City) " & _  
                "VALUES(?, ?)", odbcConn)  
            odbcParam = New OdbcParameter("@addressid", OdbcType.Int)  
            odbcCmd.Parameters.Add(odbcParam)  
            odbcParam = New OdbcParameter("@city", OdbcType.NVarChar, 30)  
            odbcCmd.Parameters.Add(odbcParam)  
  
        End Sub  
  
        Public Overrides Sub MyAddressInput_ProcessInputRow(ByVal Row As MyAddressInputBuffer)  
  
            With odbcCmd  
                .Parameters("@addressid").Value = Row.AddressID  
                .Parameters("@city").Value = Row.City  
                .ExecuteNonQuery()  
            End With  
  
        End Sub  
  
        Public Overrides Sub ReleaseConnections()  
  
            odbcConn.Close()  
  
        End Sub  
  
    End Class  
    ```  
  
    ```csharp  
    using System.Data.Odbc;  
    ...  
    public class ScriptMain :  
        UserComponent  
    {  
        OdbcConnection odbcConn;  
        OdbcCommand odbcCmd;  
        OdbcParameter odbcParam;  
  
        public override void AcquireConnections(object Transaction)  
        {  
  
            string connectionString;  
            connectionString = this.Connections.MyODBCConnectionManager.ConnectionString;  
            odbcConn = new OdbcConnection(connectionString);  
            odbcConn.Open();  
  
        }  
  
        public override void PreExecute()  
        {  
  
            odbcCmd = new OdbcCommand("INSERT INTO Person.Address2(AddressID, City) " +  
                "VALUES(?, ?)", odbcConn);  
            odbcParam = new OdbcParameter("@addressid", OdbcType.Int);  
            odbcCmd.Parameters.Add(odbcParam);  
            odbcParam = new OdbcParameter("@city", OdbcType.NVarChar, 30);  
            odbcCmd.Parameters.Add(odbcParam);  
  
        }  
  
        public override void MyAddressInput_ProcessInputRow(MyAddressInputBuffer Row)  
        {  
  
            {  
                odbcCmd.Parameters["@addressid"].Value = Row.AddressID;  
                odbcCmd.Parameters["@city"].Value = Row.City;  
                odbcCmd.ExecuteNonQuery();  
            }  
  
        }  
  
        public override void ReleaseConnections()  
        {  
  
            odbcConn.Close();  
  
        }  
    }  
    ```  
  
<span data-ttu-id="0cd47-133">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="0cd47-133">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="0cd47-134">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="0cd47-134">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="0cd47-135">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="0cd47-135">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="0cd47-136">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="0cd47-136">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cd47-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="0cd47-137">See Also</span></span>  
 [<span data-ttu-id="0cd47-138">Создание назначения с помощью компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="0cd47-138">Creating a Destination with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)  
  
  
