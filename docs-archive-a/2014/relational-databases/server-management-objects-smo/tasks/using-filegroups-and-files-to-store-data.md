---
title: Использование файловых групп и файлов для хранения данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- filegroups [SMO]
- storing data [SMO]
- files [SMO]
- files [SMO], about files
- storage [SMO]
ms.assetid: 7e2327ce-e1a6-4904-83d1-0944b24a7b43
author: stevestein
ms.author: sstein
ms.openlocfilehash: 15ac5fd0c43c9b58432a774ae11aeb6500f0403b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667657"
---
# <a name="using-filegroups-and-files-to-store-data"></a><span data-ttu-id="7ef67-102">Использование файловых групп и файлов для хранения данных</span><span class="sxs-lookup"><span data-stu-id="7ef67-102">Using Filegroups and Files to Store Data</span></span>
  <span data-ttu-id="7ef67-103">Для хранения файлов базы данных используются файлы данных.</span><span class="sxs-lookup"><span data-stu-id="7ef67-103">Data files are used to store database files.</span></span> <span data-ttu-id="7ef67-104">Файлы данных делятся на файловые группы.</span><span class="sxs-lookup"><span data-stu-id="7ef67-104">The data files are subdivided into file groups.</span></span> <span data-ttu-id="7ef67-105">Объект <xref:Microsoft.SqlServer.Management.Smo.Database> содержит свойство <xref:Microsoft.SqlServer.Management.Smo.Database.FileGroups%2A>, которое ссылается на объект <xref:Microsoft.SqlServer.Management.Smo.FileGroupCollection>.</span><span class="sxs-lookup"><span data-stu-id="7ef67-105">The <xref:Microsoft.SqlServer.Management.Smo.Database> object has a <xref:Microsoft.SqlServer.Management.Smo.Database.FileGroups%2A> property that references a <xref:Microsoft.SqlServer.Management.Smo.FileGroupCollection> object.</span></span> <span data-ttu-id="7ef67-106">Каждый объект <xref:Microsoft.SqlServer.Management.Smo.FileGroup> в этой коллекции содержит свойство <xref:Microsoft.SqlServer.Management.Smo.FileGroup.Files%2A>.</span><span class="sxs-lookup"><span data-stu-id="7ef67-106">Each <xref:Microsoft.SqlServer.Management.Smo.FileGroup> object in that collection has a <xref:Microsoft.SqlServer.Management.Smo.FileGroup.Files%2A> property.</span></span> <span data-ttu-id="7ef67-107">Это свойство ссылается на коллекцию <xref:Microsoft.SqlServer.Management.Smo.DataFileCollection>, которая содержит все файлы данных, принадлежащие базе данных.</span><span class="sxs-lookup"><span data-stu-id="7ef67-107">This property refers to a <xref:Microsoft.SqlServer.Management.Smo.DataFileCollection> collection that contains all the data files that belong to the database.</span></span> <span data-ttu-id="7ef67-108">Файловые группы в основном используются для объединения файлов, используемых для хранения объекта базы данных.</span><span class="sxs-lookup"><span data-stu-id="7ef67-108">A file group is principally used to group files together that are used to store a database object.</span></span> <span data-ttu-id="7ef67-109">Одной из причин разделения объекта базы данных по нескольким файлам является повышение производительности, особенно если файлы хранятся на разных дисках.</span><span class="sxs-lookup"><span data-stu-id="7ef67-109">One reason for spreading a database object over several files is that it can improve performance, especially if the files are stored on different disk drives.</span></span>  
  
 <span data-ttu-id="7ef67-110">В каждой созданной автоматически базе данных есть файловая группа с именем «Первичная» и файл данных, имя которого совпадает с именем базы данных.</span><span class="sxs-lookup"><span data-stu-id="7ef67-110">Every database that is created automatically has a file group named "Primary" and a data file with the same name as the database.</span></span> <span data-ttu-id="7ef67-111">В коллекции можно добавлять дополнительные файлы и группы.</span><span class="sxs-lookup"><span data-stu-id="7ef67-111">Additional files and groups can be added to the collections.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7ef67-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="7ef67-112">Examples</span></span>  
 <span data-ttu-id="7ef67-113">В следующих примерах кода для создания приложения необходимо выбрать среду программирования, шаблон программирования и язык программирования.</span><span class="sxs-lookup"><span data-stu-id="7ef67-113">For the following code examples, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="7ef67-114">Дополнительные сведения см. в статьях [Создание проекта Visual Basic SMO в Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) и [Создание проекта Visual C&#35; SMO в Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="7ef67-114">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="adding-filegroups-and-datafiles-to-a-database-in-visual-basic"></a><span data-ttu-id="7ef67-115">Добавление файловых групп и файлов данных в базу данных на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ef67-115">Adding FileGroups and DataFiles to a Database in Visual Basic</span></span>  
 <span data-ttu-id="7ef67-116">Основная файловая группа и файл данных создаются автоматически со значениями свойств по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7ef67-116">The primary file group and data file are created automatically with default property values.</span></span> <span data-ttu-id="7ef67-117">В этом примере кода задаются некоторые значения свойств, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="7ef67-117">The code example specifies some property values that you can use.</span></span> <span data-ttu-id="7ef67-118">Иным образом, можно использовать значения свойств по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7ef67-118">Otherwise, the default property values are used.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBFileGroups1](SMO How to#SMO_VBFileGroups1)]  -->  
  
## <a name="adding-filegroups-and-datafiles-to-a-database-in-visual-c"></a><span data-ttu-id="7ef67-119">Добавление файловых групп и файлов данных в базу данных на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="7ef67-119">Adding FileGroups and DataFiles to a Database in Visual C#</span></span>  
 <span data-ttu-id="7ef67-120">Основная файловая группа и файл данных создаются автоматически со значениями свойств по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7ef67-120">The primary file group and data file are created automatically with default property values.</span></span> <span data-ttu-id="7ef67-121">В этом примере кода задаются некоторые значения свойств, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="7ef67-121">The code example specifies some property values that you can use.</span></span> <span data-ttu-id="7ef67-122">Иным образом, можно использовать значения свойств по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7ef67-122">Otherwise, the default property values are used.</span></span>  
  
```csharp
{  
            Server srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db = default(Database);  
            db = srv.Databases["AdventureWorks2012"];  
            //Define a FileGroup object called SECONDARY on the database.   
            FileGroup fg1 = default(FileGroup);  
            fg1 = new FileGroup(db, "SECONDARY");  
            //Call the Create method to create the file group on the instance of SQL Server.   
            fg1.Create();  
            //Define a DataFile object on the file group and set the FileName property.   
            DataFile df1 = default(DataFile);  
            df1 = new DataFile(fg1, "datafile1");  
            df1.FileName = "c:\\Program Files\\Microsoft SQL Server\\MSSQL.1\\MSSQL\\Data\\datafile2.ndf";  
            //Call the Create method to create the data file on the instance of SQL Server.   
            df1.Create();  
        }  
```  
  
## <a name="adding-filegroups-and-datafiles-to-a-database-in-powershell"></a><span data-ttu-id="7ef67-123">Добавление файловых групп и файлов данных в базу данных в PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ef67-123">Adding FileGroups and DataFiles to a Database in PowerShell</span></span>  
 <span data-ttu-id="7ef67-124">Основная файловая группа и файл данных создаются автоматически со значениями свойств по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7ef67-124">The primary file group and data file are created automatically with default property values.</span></span> <span data-ttu-id="7ef67-125">В этом примере кода задаются некоторые значения свойств, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="7ef67-125">The code example specifies some property values that you can use.</span></span> <span data-ttu-id="7ef67-126">Иным образом, можно использовать значения свойств по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7ef67-126">Otherwise, the default property values are used.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\default\Databases\  
  
#And the database object corresponding to AdventureWorks2012.  
$db = get-item AdventureWorks2012  
  
#Create a new filegroup  
$fg1 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Filegroup -argumentlist $db, "SECONDARY"  
$fg1.Create()  
  
#Define a DataFile object on the file group and set the FileName property.   
$df1 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.DataFile -argumentlist $fg1, "datafile1"  
  
#Make sure to have a directory created to hold the designated data file  
$df1.FileName = "c:\\TestData\\datafile2.ndf"  
  
#Call the Create method to create the data file on the instance of SQL Server.   
$df1.Create()  
```  
  
## <a name="creating-altering-and-removing-a-log-file-in-visual-basic"></a><span data-ttu-id="7ef67-127">Создание, изменение и удаление файла журнала на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ef67-127">Creating, Altering, and Removing a Log File in Visual Basic</span></span>  
 <span data-ttu-id="7ef67-128">В этом примере кода создается объект <xref:Microsoft.SqlServer.Management.Smo.LogFile>, изменяется одно из его свойств, а затем он удаляется из базы данных.</span><span class="sxs-lookup"><span data-stu-id="7ef67-128">The code example creates a <xref:Microsoft.SqlServer.Management.Smo.LogFile> object, changes one of the properties, and then removes it from the database.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBFileGroups3](SMO How to#SMO_VBFileGroups3)]  -->  
  
## <a name="creating-altering-and-removing-a-log-file-in-visual-c"></a><span data-ttu-id="7ef67-129">Создание, изменение и удаление файла журнала на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="7ef67-129">Creating, Altering, and Removing a Log File in Visual C#</span></span>  
 <span data-ttu-id="7ef67-130">В этом примере кода создается объект <xref:Microsoft.SqlServer.Management.Smo.LogFile>, изменяется одно из его свойств, а затем он удаляется из базы данных.</span><span class="sxs-lookup"><span data-stu-id="7ef67-130">The code example creates a <xref:Microsoft.SqlServer.Management.Smo.LogFile> object, changes one of the properties, and then removes it from the database.</span></span>  
  
```csharp
//Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db = default(Database);  
            db = srv.Databases["AdventureWorks2012"];  
            //Define a LogFile object and set the database, name, and file name properties in the constructor.   
            LogFile lf1 = default(LogFile);  
            lf1 = new LogFile(db, "logfile1", "c:\\Program Files\\Microsoft SQL Server\\MSSQL.10_50.MSSQLSERVER\\MSSQL\\Data\\logfile1.ldf");  
            //Set the file growth to 6%.   
            lf1.GrowthType = FileGrowthType.Percent;  
            lf1.Growth = 6;  
            //Run the Create method to create the log file on the instance of SQL Server.   
            lf1.Create();  
            //Alter the growth percentage.
            lf1.Growth = 7;  
            lf1.Alter();  
            //Remove the log file.
            lf1.Drop();
```  
  
## <a name="creating-altering-and-removing-a-log-file-in-powershell"></a><span data-ttu-id="7ef67-131">Создание, изменение и удаление файла журнала в PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ef67-131">Creating, Altering, and Removing a Log File in PowerShell</span></span>  
 <span data-ttu-id="7ef67-132">В этом примере кода создается объект <xref:Microsoft.SqlServer.Management.Smo.LogFile>, изменяется одно из его свойств, а затем он удаляется из базы данных.</span><span class="sxs-lookup"><span data-stu-id="7ef67-132">The code example creates a <xref:Microsoft.SqlServer.Management.Smo.LogFile> object, changes one of the properties, and then removes it from the database.</span></span>  
  
```powershell
#Load the assembly containing the enums used in this example  
[reflection.assembly]::LoadWithPartialName("Microsoft.SqlServer.SqlEnum")  
  
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\default\Databases\  
  
#And the database object corresponding to AdventureWorks2012  
$db = get-item AdventureWorks2012  
  
#Create a filegroup  
$fg1 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Filegroup -argumentlist $db, "Secondary"  
  
#Call the Create method to create the file group on the instance of SQL Server.   
$fg1.Create()  
  
#Define a LogFile object on the file group and set the FileName property.   
$lf1 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.LogFile -argumentlist $db, "LogFile2"  
  
#Set a location for it - make sure the directory exists  
$lf1.FileName = "logfile1", "c:\\Program Files\\Microsoft SQL Server\\MSSQL.10_50.MSSQLSERVER\\MSSQL\\Data\\logfile1.ldf"  
  
#Set file growth to 6%  
$lf1.GrowthType = [Microsoft.SqlServer.Management.Smo.FileGrowthType]::Percent  
$lf1.Growth = 6.0  
  
#Call the Create method to create the data file on the instance of SQL Server.   
$lf1.Create()  
  
#Alter a value and drop the log file  
$lf1.Growth = 7.0  
$lf1.Alter()  
$lf1.Drop()
```  
  
## <a name="see-also"></a><span data-ttu-id="7ef67-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="7ef67-133">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.FileGroup>   
 [<span data-ttu-id="7ef67-134">Файлы и файловые группы базы данных</span><span class="sxs-lookup"><span data-stu-id="7ef67-134">Database Files and Filegroups</span></span>](../../databases/database-files-and-filegroups.md)  
