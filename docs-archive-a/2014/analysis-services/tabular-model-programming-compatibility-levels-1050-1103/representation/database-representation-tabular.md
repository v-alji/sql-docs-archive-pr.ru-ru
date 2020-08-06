---
title: Представление базы данных (табличное) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 16a233fb-f83b-4ca1-acb5-6186eca0a62c
author: minewiskan
ms.author: owend
ms.openlocfilehash: c327e07685e98e6fa9f992025510e869d909e5ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657943"
---
# <a name="database-representationtabular"></a><span data-ttu-id="6e9c1-102">Представление базы данных (табличное)</span><span class="sxs-lookup"><span data-stu-id="6e9c1-102">Database Representation(Tabular)</span></span>
  <span data-ttu-id="6e9c1-103">В табличном режиме база данных является контейнером для всех объектов табличной модели.</span><span class="sxs-lookup"><span data-stu-id="6e9c1-103">In Tabular Mode, the database is the container for all objects in the tabular model.</span></span>  
  
## <a name="database-representation"></a><span data-ttu-id="6e9c1-104">Представление базы данных</span><span class="sxs-lookup"><span data-stu-id="6e9c1-104">Database Representation</span></span>  
 <span data-ttu-id="6e9c1-105">База данных — это место, где размещаются все объекты, образующие табличную модель.</span><span class="sxs-lookup"><span data-stu-id="6e9c1-105">The database is the place where all objects that form a tabular model reside.</span></span> <span data-ttu-id="6e9c1-106">В базе данных разработчик находит такие объекты, как соединения, таблицы, роли и т. д.</span><span class="sxs-lookup"><span data-stu-id="6e9c1-106">Contained by the database, the developer finds objects like connections, tables, roles and many more.</span></span>  
  
### <a name="database-in-amo"></a><span data-ttu-id="6e9c1-107">База данных в объектах AMO</span><span class="sxs-lookup"><span data-stu-id="6e9c1-107">Database in AMO</span></span>  
 <span data-ttu-id="6e9c1-108">Если для управления табличным шаблоном базы данных табличной модели используются объекты AMO, то объект <xref:Microsoft.AnalysisServices.Database> из AMO соответствует логическому объекту базы данных в табличной модели по схеме «один к одному».</span><span class="sxs-lookup"><span data-stu-id="6e9c1-108">When using AMO to manage a tabular model database, the <xref:Microsoft.AnalysisServices.Database> object in AMO matches one-to-one the database logical object in a tabular model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6e9c1-109">Чтобы получить доступ к объекту базы данных, пользователь объектов AMO должен получить доступ к объекту сервера и установить с ним соединение.</span><span class="sxs-lookup"><span data-stu-id="6e9c1-109">In order to gain access to a database object, in AMO, the user needs to have access to a server object and connect to it.</span></span>  
  
### <a name="database-in-adomdnet"></a><span data-ttu-id="6e9c1-110">База данных в ADOMD.Net</span><span class="sxs-lookup"><span data-stu-id="6e9c1-110">Database in ADOMD.Net</span></span>  
 <span data-ttu-id="6e9c1-111">Если ADOMD используется для просмотра табличного шаблона базы данных и отправки запросов к ней, то соединение с определенной базой данных устанавливается посредством объекта <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection>.</span><span class="sxs-lookup"><span data-stu-id="6e9c1-111">When using ADOMD to consult and query a tabular model database, connection to a specific database is obtained through the <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection> object.</span></span>  
  
 <span data-ttu-id="6e9c1-112">К определенной базе данных можно подключиться напрямую с помощью следующего фрагмента кода:</span><span class="sxs-lookup"><span data-stu-id="6e9c1-112">You can connect directly to a certain database using the following code snippet:</span></span>  
  
```csharp  
using ADOMD = Microsoft.AnalysisServices.AdomdClient;  
...  
   ADOMD.AdomdConnection currrentCnx = new ADOMD.AdomdConnection("Data Source=<<server\instance>>;Catalog=<<database>>");  
   currrentCnx.Open();  
...  
  
```  
  
 <span data-ttu-id="6e9c1-113">Кроме того, через существующий объект соединения (если оно не закрыто) можно изменить текущую базу данных на другую, как показано в следующем фрагменте кода:</span><span class="sxs-lookup"><span data-stu-id="6e9c1-113">Also, over an existing connection object (that hasn't been closed), you can change the current database to another as shown in the following code snippet:</span></span>  
  
```csharp  
currentCnx.ChangeDatabase("myOtherDatabase");  
  
```  
  
## <a name="database-in-amo"></a><span data-ttu-id="6e9c1-114">База данных в объектах AMO</span><span class="sxs-lookup"><span data-stu-id="6e9c1-114">Database in AMO</span></span>  
 <span data-ttu-id="6e9c1-115">При использовании объектов AMO для управления объектом базы данных начните с объекта <xref:Microsoft.AnalysisServices.Server>.</span><span class="sxs-lookup"><span data-stu-id="6e9c1-115">When using AMO to manage a database object, start with a <xref:Microsoft.AnalysisServices.Server> object.</span></span> <span data-ttu-id="6e9c1-116">Затем найдите свою базу данных в коллекции баз данных или создайте новую базу данных, добавив ее в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="6e9c1-116">Then search for your database in the databases collection or create a new database by adding one to the collection.</span></span>  
  
 <span data-ttu-id="6e9c1-117">В следующем фрагменте кода показаны шаги для подключения к серверу и создания пустой базы данных после проверки того, что база данных не существует.</span><span class="sxs-lookup"><span data-stu-id="6e9c1-117">The following code snippet shows the steps to connect to a server and create an empty database, after checking the database doesn't exist:</span></span>  
  
```  
  
AMO.Server CurrentServer = new AMO.Server();  
try  
{  
    CurrentServer.Connect(currentServerName);  
}  
catch (Exception cnxException)  
{  
    MessageBox.Show(string.Format("Error while trying to connect to server: [{0}]\nError message: {1}", currentServerName, cnxException.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
    return;  
}  
newDatabaseName = DatabaseName.Text;  
if (CurrentServer.Databases.Contains(newDatabaseName))  
{  
    return;  
}  
try  
{  
    AMO.Database newDatabase = CurrentServer.Databases.Add(newDatabaseName);  
  
    CurrentServer.Update();  
}  
catch (Exception createDBxc)  
{  
    MessageBox.Show(String.Format("Database [{0}] couldn't be created.\n{1}", newDatabaseName, createDBxc.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
    newDatabaseAvailable = false;  
}  
  
```  
  
 <span data-ttu-id="6e9c1-118">Практические сведения об использовании объектов AMO для создания представлений баз данных и управления ими см. в разделе исходный код в образце табличных объектов AMO 2012. в частности, верните следующий исходный файл: Database.cs.</span><span class="sxs-lookup"><span data-stu-id="6e9c1-118">For a practical understanding on how to use AMO to create and manipulate database representations, see source code in the Tabular AMO 2012 sample; specifically check in the following source file: Database.cs.</span></span> <span data-ttu-id="6e9c1-119">Образец кода приведен только для иллюстрации описываемых здесь логических концепций и не должен использоваться в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="6e9c1-119">Sample code is provided only as a support to the logical concepts explained here, and should not be used in a production environment.</span></span>  
  
  
