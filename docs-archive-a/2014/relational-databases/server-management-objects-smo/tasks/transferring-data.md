---
title: Передача данных | Документация Майкрософт
ms.custom: ''
ms.date: 10/20/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- data transfers [SMO]
- transferring data
ms.assetid: eea255c3-8251-40f0-973b-fe4ef6cb5261
author: stevestein
ms.author: sstein
ms.openlocfilehash: dcbcdc1e61c2d18f6a98f797385145f04dfecc7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732489"
---
# <a name="transferring-data"></a><span data-ttu-id="0831c-102">Передача данных</span><span class="sxs-lookup"><span data-stu-id="0831c-102">Transferring Data</span></span>
  <span data-ttu-id="0831c-103">Класс <xref:Microsoft.SqlServer.Management.Smo.Transfer> является служебным классом, наделенным средствами для передачи объектов и данных.</span><span class="sxs-lookup"><span data-stu-id="0831c-103">The <xref:Microsoft.SqlServer.Management.Smo.Transfer> class is a utility class that provides tools to transfer objects and data.</span></span>  
  
 <span data-ttu-id="0831c-104">Объекты в схеме базы данных передаются в ходе выполнения сформированного скрипта на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="0831c-104">Objects in the database schema are transferred by executing a generated script on the target server.</span></span> <span data-ttu-id="0831c-105">Данные <xref:Microsoft.SqlServer.Management.Smo.Table> передаются вместе с динамически созданным пакетом DTS.</span><span class="sxs-lookup"><span data-stu-id="0831c-105"><xref:Microsoft.SqlServer.Management.Smo.Table> data is transferred with a dynamically created DTS package.</span></span>  
  
 <span data-ttu-id="0831c-106">Объект <xref:Microsoft.SqlServer.Management.Smo.Transfer> обладает всеми функциональными возможностями объектов <xref:Microsoft.SqlServer.Management.Smo.Transfer> в DMO и дополнительными функциональными возможностями [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0831c-106">The <xref:Microsoft.SqlServer.Management.Smo.Transfer> object contains all the functionality of the <xref:Microsoft.SqlServer.Management.Smo.Transfer> objects in DMO and additional [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] functionality.</span></span> <span data-ttu-id="0831c-107">Однако в SMO в [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] <xref:Microsoft.SqlServer.Management.Smo.Transfer> объект использует API [SQLBulkCopy](https://msdn.microsoft.com/library/system.data.sqlclient.sqlbulkcopy\(v=VS.90\).aspx) для перемещения данных.</span><span class="sxs-lookup"><span data-stu-id="0831c-107">However, in SMO in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], the <xref:Microsoft.SqlServer.Management.Smo.Transfer> object uses the [SQLBulkCopy](https://msdn.microsoft.com/library/system.data.sqlclient.sqlbulkcopy\(v=VS.90\).aspx) API to transfer data.</span></span> <span data-ttu-id="0831c-108">Кроме того, методы и свойства, используемые для передачи данных, располагаются в объекте <xref:Microsoft.SqlServer.Management.Smo.Transfer>, а не в объекте <xref:Microsoft.SqlServer.Management.Smo.Database>.</span><span class="sxs-lookup"><span data-stu-id="0831c-108">Also, the methods and properties that are used to perform data transfers reside on the <xref:Microsoft.SqlServer.Management.Smo.Transfer> object instead of the <xref:Microsoft.SqlServer.Management.Smo.Database> object.</span></span> <span data-ttu-id="0831c-109">Перенос функциональных возможностей с экземпляров классов на вспомогательные классы согласуется с облегченной объектной моделью, поскольку код для выполнения конкретных задач загружается только по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="0831c-109">Moving functionality from the instance classes to utility classes is consistent with a lighter object model because the code for specific tasks is loaded only when it is required.</span></span>  
  
 <span data-ttu-id="0831c-110">Объект <xref:Microsoft.SqlServer.Management.Smo.Transfer> не поддерживает передачи данных в целевую базу данных, у которой <xref:Microsoft.SqlServer.Management.Smo.Database.CompatibilityLevel%2A> меньше, чем у версии экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0831c-110">The <xref:Microsoft.SqlServer.Management.Smo.Transfer> object does not support data transfers to a target database that has a <xref:Microsoft.SqlServer.Management.Smo.Database.CompatibilityLevel%2A> less than the version of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="0831c-111">Пример</span><span class="sxs-lookup"><span data-stu-id="0831c-111">Example</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="transferring-schema-and-data-from-one-database-to-another-in-visual-basic"></a><span data-ttu-id="0831c-112">Передача схемы и данных из одной базы данных в другую на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0831c-112">Transferring Schema and Data from One Database to Another in Visual Basic</span></span>  
 <span data-ttu-id="0831c-113">Этот пример кода показывает, как передавать схему и данные из одной базы данных в другую с помощью объекта <xref:Microsoft.SqlServer.Management.Smo.Transfer>.</span><span class="sxs-lookup"><span data-stu-id="0831c-113">This code example shows how to transfer schema and data from one database to another using the <xref:Microsoft.SqlServer.Management.Smo.Transfer> object.</span></span>  
  
```vb
'Connect to the local, default instance of SQL Server.
Dim srv As Server
srv = New Server
'Reference the AdventureWorks2012 2008R2 database
Dim db As Database
db = srv.Databases("AdventureWorks2012")
'Create a new database that is to be destination database.
Dim dbCopy As Database
dbCopy = New Database(srv, "AdventureWorks2012Copy")
dbCopy.Create()
'Define a Transfer object and set the required options and properties.
Dim xfr As Transfer
xfr = New Transfer(db)
xfr.CopyAllTables = True
xfr.Options.WithDependencies = True
xfr.Options.ContinueScriptingOnError = True
xfr.DestinationDatabase = "AdventureWorks2012Copy"
xfr.DestinationServer = srv.Name
xfr.DestinationLoginSecure = True
xfr.CopySchema = True
'Script the transfer. Alternatively perform immediate data transfer with TransferData method.
xfr.ScriptTransfer()
```
  
## <a name="transferring-schema-and-data-from-one-database-to-another-in-visual-c"></a><span data-ttu-id="0831c-114">Передача схемы и данных из одной базы данных в другую на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="0831c-114">Transferring Schema and Data from One Database to Another in Visual C#</span></span>  
 <span data-ttu-id="0831c-115">Этот пример кода показывает, как передавать схему и данные из одной базы данных в другую с помощью объекта <xref:Microsoft.SqlServer.Management.Smo.Transfer>.</span><span class="sxs-lookup"><span data-stu-id="0831c-115">This code example shows how to transfer schema and data from one database to another using the <xref:Microsoft.SqlServer.Management.Smo.Transfer> object.</span></span>  
  
```csharp
{  
            Server srv;  
            srv = new Server();  
            //Reference the AdventureWorks2012 database   
            Database db;  
            db = srv.Databases["AdventureWorks2012"];  
            //Create a new database that is to be destination database.   
            Database dbCopy;  
            dbCopy = new Database(srv, "AdventureWorks2012Copy");  
            dbCopy.Create();  
            //Define a Transfer object and set the required options and properties.   
            Transfer xfr;  
            xfr = new Transfer(db);  
            xfr.CopyAllTables = true;  
            xfr.Options.WithDependencies = true;  
            xfr.Options.ContinueScriptingOnError = true;  
            xfr.DestinationDatabase = "AdventureWorks2012Copy";  
            xfr.DestinationServer = srv.Name;  
            xfr.DestinationLoginSecure = true;  
            xfr.CopySchema = true;  
            //Script the transfer. Alternatively perform immediate data transfer   
            // with TransferData method.   
            xfr.ScriptTransfer();  
        }   
```  
  
## <a name="transferring-schema-and-data-from-one-database-to-another-in-powershell"></a><span data-ttu-id="0831c-116">Передача схемы и данных из одной базы данных в другую в PowerShell</span><span class="sxs-lookup"><span data-stu-id="0831c-116">Transferring Schema and Data from One Database to Another in PowerShell</span></span>  
 <span data-ttu-id="0831c-117">Этот пример кода показывает, как передавать схему и данные из одной базы данных в другую с помощью объекта <xref:Microsoft.SqlServer.Management.Smo.Transfer>.</span><span class="sxs-lookup"><span data-stu-id="0831c-117">This code example shows how to transfer schema and data from one database to another using the <xref:Microsoft.SqlServer.Management.Smo.Transfer> object.</span></span>  
  
```powershell
#Connect to the local, default instance of SQL Server.  
  
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Reference the AdventureWorks2012 database.  
$db = $srv.Databases["AdventureWorks2012"]  
  
#Create a database to hold the copy of AdventureWorks  
$dbCopy = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Database -ArgumentList $srv, "AdventureWorksCopy"  
$dbCopy.Create()  
  
#Define a Transfer object and set the required options and properties.  
$xfr = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Transfer -ArgumentList $db  
  
#Set this objects properties  
$xfr.CopyAllTables = $true  
$xfr.Options.WithDependencies = $true  
$xfr.Options.ContinueScriptingOnError = $true  
$xfr.DestinationDatabase = "AdventureWorksCopy"  
$xfr.DestinationServer = $srv.Name  
$xfr.DestinationLoginSecure = $true  
$xfr.CopySchema = $true  
"Scripting Data Transfer"  
#Script the transfer. Alternatively perform immediate data transfer with TransferData method.  
$xfr.ScriptTransfer()  
```  
