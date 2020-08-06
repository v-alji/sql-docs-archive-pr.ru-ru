---
title: Предупреждение об использовании геометрии, GEOGRAPHY и HIERARCHYID на стороне клиента | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 500ee6b3-2154-45d2-a3cf-8760166d9413
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 66898aa056800c0a7573b5afa73762785706ff7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659121"
---
# <a name="warning-about-client-side-usage-of-geometry-geography-and-hierarchyid"></a><span data-ttu-id="dbed2-102">Предупреждение об использовании GEOMETRY, GEOGRAPHY и HIERARCHYID на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="dbed2-102">Warning about client side usage of GEOMETRY, GEOGRAPHY and HIERARCHYID</span></span>
  <span data-ttu-id="dbed2-103">Сборка **Microsoft.SqlServer.Types.dll**, содержащая пространственные типы данных, была обновлена с версии 10,0 до версии 11,0.</span><span class="sxs-lookup"><span data-stu-id="dbed2-103">The assembly **Microsoft.SqlServer.Types.dll**, which contains the spatial data types, has been upgraded from version 10.0 to version 11.0.</span></span> <span data-ttu-id="dbed2-104">Пользовательские приложения, ссылающиеся на эту сборку, могут завершаться с ошибками, если выполняются определенные условия.</span><span class="sxs-lookup"><span data-stu-id="dbed2-104">Custom applications that reference this assembly may fail when certain conditions are true.</span></span>  
  
## <a name="component"></a><span data-ttu-id="dbed2-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="dbed2-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="dbed2-106">Описание</span><span class="sxs-lookup"><span data-stu-id="dbed2-106">Description</span></span>  
 <span data-ttu-id="dbed2-107">Сборка **Microsoft.SqlServer.Types.dll**, содержащая пространственные типы данных, была обновлена с версии 10,0 до версии 11,0.</span><span class="sxs-lookup"><span data-stu-id="dbed2-107">The assembly **Microsoft.SqlServer.Types.dll**, which contains the spatial data types, has been upgraded from version 10.0 to version 11.0.</span></span> <span data-ttu-id="dbed2-108">Пользовательские приложения, ссылающиеся на эту сборку, могут завершаться с ошибками, если выполняются следующие условия.</span><span class="sxs-lookup"><span data-stu-id="dbed2-108">Custom applications that reference this assembly may fail when the following conditions are true.</span></span>  
  
-   <span data-ttu-id="dbed2-109">При перемещении пользовательского приложения с компьютера, на котором установлено приложение [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] , на компьютер, на котором [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] установлено только приложение, произойдет сбой приложения из-за отсутствия ссылки на версию 10,0 для сборки **sqltypes** .</span><span class="sxs-lookup"><span data-stu-id="dbed2-109">When you move a custom application from a computer on which [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] was installed to a computer on which only [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] is installed, the application will fail because the referenced version 10.0 of the **SqlTypes** assembly is not present.</span></span> <span data-ttu-id="dbed2-110">Может отображаться следующее сообщение об ошибке: `"Could not load file or assembly 'Microsoft.SqlServer.Types, Version=10.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91' or one of its dependencies. The system cannot find the file specified."`</span><span class="sxs-lookup"><span data-stu-id="dbed2-110">You may see this error message: `"Could not load file or assembly 'Microsoft.SqlServer.Types, Version=10.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91' or one of its dependencies. The system cannot find the file specified."`</span></span>  
  
-   <span data-ttu-id="dbed2-111">Если также установлена ссылка на сборку **sqltypes** версии 11,0 и версия 10,0, может появиться следующее сообщение об ошибке:`"System.InvalidCastException: Unable to cast object of type 'Microsoft.SqlServer.Types.SqlGeometry' to type 'Microsoft.SqlServer.Types.SqlGeometry'."`</span><span class="sxs-lookup"><span data-stu-id="dbed2-111">When you reference the **SqlTypes** assembly version 11.0, and version 10.0 is also installed, you may see this error message: `"System.InvalidCastException: Unable to cast object of type 'Microsoft.SqlServer.Types.SqlGeometry' to type 'Microsoft.SqlServer.Types.SqlGeometry'."`</span></span>  
  
-   <span data-ttu-id="dbed2-112">При ссылке на сборку **sqltypes** версии 11,0 из пользовательского приложения, предназначенного для .NET 3,5, 4 или 4,5, происходит сбой приложения, так как SqlClient по проектированию загружает версию 10,0 сборки.</span><span class="sxs-lookup"><span data-stu-id="dbed2-112">When you reference the **SqlTypes** assembly version 11.0 from a custom application that targets .NET 3.5, 4, or 4.5, the application will fail because SqlClient by design loads version 10.0 of the assembly.</span></span> <span data-ttu-id="dbed2-113">Эта ошибка возникает, когда приложение вызывает один из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="dbed2-113">This failure occurs when the application calls one of the following methods:</span></span>  
  
    -   <span data-ttu-id="dbed2-114">Метод `GetValue` класса `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="dbed2-114">`GetValue` method of the `SqlDataReader` class</span></span>  
  
    -   <span data-ttu-id="dbed2-115">Метод `GetValues` класса `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="dbed2-115">`GetValues` method of the `SqlDataReader` class</span></span>  
  
    -   <span data-ttu-id="dbed2-116">индексный оператор квадратных скобок [] из класса `SqlDataReader`</span><span class="sxs-lookup"><span data-stu-id="dbed2-116">bracket index operator [] of the `SqlDataReader` class</span></span>  
  
    -   <span data-ttu-id="dbed2-117">Метод `ExecuteScalar` класса `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="dbed2-117">`ExecuteScalar` method of the `SqlCommand` class</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="dbed2-118">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="dbed2-118">Corrective Action</span></span>  
 <span data-ttu-id="dbed2-119">Для разрешения этой проблемы можно воспользоваться одним из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="dbed2-119">You can work around this issue by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="dbed2-120">Для разрешения этой проблемы в коде можно вызвать метод `GetSqlBytes` вместо перечисленных выше методов Get для получения системных типов CLR [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="dbed2-120">You can work around this issue in your code by calling the `GetSqlBytes` method, instead of the Get methods listed above, to retrieve CLR [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system types, as shown in the following example:</span></span>  
  
    ```csharp  
    string query = "SELECT [SpatialColumn] FROM [SpatialTable]";  
          using (SqlConnection conn = new SqlConnection("..."))  
          {  
                SqlCommand cmd = new SqlCommand(query, conn);  
  
                conn.Open();  
                SqlDataReader reader = cmd.ExecuteReader();  
  
                while (reader.Read())  
                {  
                      // In version 11.0 only  
                      SqlGeometry g =   
    SqlGeometry.Deserialize(reader.GetSqlBytes(0));  
  
                      // In version 10.0 or 11.0  
                      SqlGeometry g2 = new SqlGeometry();  
                      g.Read(new BinaryReader(reader.GetSqlBytes(0).Stream));  
                }  
          }  
    ```  
  
-   <span data-ttu-id="dbed2-121">Для разрешения этой проблемы можно воспользоваться перенаправлением сборок в файле конфигурации, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="dbed2-121">You can work around this issue by using assembly redirection in the application configuration file, as shown in the following example:</span></span>  
  
    ```xml  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
        ...  
        <dependentAssembly>  
            <assemblyIdentity name="Microsoft.SqlServer.Types" publicKeyToken="89845dcd8080cc91" culture="neutral" />  
            <bindingRedirect oldVersion="10.0.0.0" newVersion="11.0.0.0" />  
        </dependentAssembly>  
        ...  
    </assemblyBinding>  
    ```  
  
-   <span data-ttu-id="dbed2-122">Для разрешения этой проблемы в строке подключения можно указать значение «SQL Server 2012» для атрибута «Type System Version», что обеспечивает в SqlClient принудительную загрузку версии 11.0 сборки.</span><span class="sxs-lookup"><span data-stu-id="dbed2-122">You can work around this issue in your connection string by specifying a value of "SQL Server 2012" for the "Type System Version" attribute to force SqlClient to load version 11.0 of the assembly.</span></span> <span data-ttu-id="dbed2-123">Этот атрибут строки подключения доступен только в платформе .NET 4.5 и выше.</span><span class="sxs-lookup"><span data-stu-id="dbed2-123">This connection string attribute is available only in .NET 4.5 and above.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbed2-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="dbed2-124">See Also</span></span>  
 <span data-ttu-id="dbed2-125">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="dbed2-125">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="dbed2-126">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="dbed2-126">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md
)  
  
  
