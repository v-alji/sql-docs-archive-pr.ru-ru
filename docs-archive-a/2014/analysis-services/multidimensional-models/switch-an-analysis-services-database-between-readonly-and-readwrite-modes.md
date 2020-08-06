---
title: Переключение базы данных Analysis Services между режимами ReadOnly и ReadWrite | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- ReadOnly property
- ReadWriteMode command
- operations [Analysis Services - multidimensional data]
ms.assetid: 4eff8181-08dd-4fad-b091-d400fc21a020
author: minewiskan
ms.author: owend
ms.openlocfilehash: 757aedd985d969f932deacf5599716078021a1af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727390"
---
# <a name="switch-an-analysis-services-database-between-readonly-and-readwrite-modes"></a><span data-ttu-id="c65f9-102">Переключение базы данных служб Analysis Services между режимами ReadOnly и ReadWrite</span><span class="sxs-lookup"><span data-stu-id="c65f9-102">Switch an Analysis Services database between ReadOnly and ReadWrite modes</span></span>
  <span data-ttu-id="c65f9-103">Часто возникают ситуации, когда администратору баз данных (dba) служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] необходимо изменить режим чтения/записи в табличной или многомерной базе данных.</span><span class="sxs-lookup"><span data-stu-id="c65f9-103">There are often situations when a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database administrator (dba) wants to change the read/write mode of a tabular or multidimensional database.</span></span> <span data-ttu-id="c65f9-104">Эти ситуации часто определяются бизнес-потребностями, например, совместное использование базы данных между пулом [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] серверов для повышения удобства работы пользователей.</span><span class="sxs-lookup"><span data-stu-id="c65f9-104">These situations are often driven by business needs, such as sharing the database among a pool of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] servers for a better user experience.</span></span>  
  
 <span data-ttu-id="c65f9-105">Существует много способов изменения режима работы базы данных.</span><span class="sxs-lookup"><span data-stu-id="c65f9-105">A database mode can be switched in many ways.</span></span> <span data-ttu-id="c65f9-106">В этом документе описаны следующие распространенные сценарии:</span><span class="sxs-lookup"><span data-stu-id="c65f9-106">This document explains the following common scenarios:</span></span>  
  
-   <span data-ttu-id="c65f9-107">интерактивно с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c65f9-107">Interactively using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span></span>  
  
-   <span data-ttu-id="c65f9-108">программным способом с помощью объектов AMO;</span><span class="sxs-lookup"><span data-stu-id="c65f9-108">Programmatically using AMO</span></span>  
  
-   <span data-ttu-id="c65f9-109">с помощью скриптов, используя XML для аналитики</span><span class="sxs-lookup"><span data-stu-id="c65f9-109">By script using XMLA</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="c65f9-110">Процедуры</span><span class="sxs-lookup"><span data-stu-id="c65f9-110">Procedures</span></span>  
  
#### <a name="to-switch-the-readwrite-mode-of-a-database-interactively-using-management-studio"></a><span data-ttu-id="c65f9-111">Интерактивное изменение режима чтения-записи базы данных с помощью среды Management Studio</span><span class="sxs-lookup"><span data-stu-id="c65f9-111">To switch the read/write mode of a database interactively using Management Studio</span></span>  
  
1.  <span data-ttu-id="c65f9-112">Найдите на левой или правой панели среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] базу данных для переключения.</span><span class="sxs-lookup"><span data-stu-id="c65f9-112">Locate the database to be switched in the left or right pane of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="c65f9-113">Щелкните правой кнопкой мыши базу данных и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c65f9-113">Right-click the database and select **Properties**.</span></span> <span data-ttu-id="c65f9-114">Найдите папку с базой данных и запишите ее расположение.</span><span class="sxs-lookup"><span data-stu-id="c65f9-114">Find the database folder and note the location.</span></span> <span data-ttu-id="c65f9-115">Пустое место хранения для базы данных означает, что папка базы данных находится в папке данных сервера.</span><span class="sxs-lookup"><span data-stu-id="c65f9-115">An empty database storage location indicates that the database folder is located in the server data folder.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c65f9-116">После отсоединения базы данных ее расположение будет невозможно определить при помощи среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c65f9-116">As soon as the database is detached, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] can no longer help you obtain the database location.</span></span>  
  
3.  <span data-ttu-id="c65f9-117">Щелкните правой кнопкой мыши базу данных и выберите пункт **отсоединить...**</span><span class="sxs-lookup"><span data-stu-id="c65f9-117">Right-click the database and select **Detach...**</span></span>  
  
4.  <span data-ttu-id="c65f9-118">Назначьте пароль отсоединяемой базе данных и нажмите кнопку **ОК** , чтобы выполнить команду отсоединения.</span><span class="sxs-lookup"><span data-stu-id="c65f9-118">Assign a password to the database to be detached, and then click **OK** to execute the detach command.</span></span>  
  
5.  <span data-ttu-id="c65f9-119">Откройте папку **базы данных** в левой или правой области окна [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c65f9-119">Locate the **Databases** folder in the left or right pane of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
6.  <span data-ttu-id="c65f9-120">Щелкните правой кнопкой мыши папку **базы данных** и выберите команду **Присоединить...**</span><span class="sxs-lookup"><span data-stu-id="c65f9-120">Right-click the **Databases** folder and select **Attach...**</span></span>  
  
7.  <span data-ttu-id="c65f9-121">В текстовом поле **папка** введите начальное местоположение папки базы данных.</span><span class="sxs-lookup"><span data-stu-id="c65f9-121">In the **folder** text box, type the original location of the database folder.</span></span> <span data-ttu-id="c65f9-122">Кроме того, можно нажать кнопку обзора (**...**), чтобы найти папку базы данных.</span><span class="sxs-lookup"><span data-stu-id="c65f9-122">Alternatively, you can use the browse button (**...**) to locate the database folder.</span></span>  
  
8.  <span data-ttu-id="c65f9-123">Выберите режим чтения/записи для базы данных.</span><span class="sxs-lookup"><span data-stu-id="c65f9-123">Select the read/write mode for the database.</span></span>  
  
9. <span data-ttu-id="c65f9-124">Введите пароль, который использовался на шаге 3, и нажмите кнопку **ОК** , чтобы выполнить команду Attach.</span><span class="sxs-lookup"><span data-stu-id="c65f9-124">Type the password that was used in step 3 and click **OK** to execute the attach command.</span></span>  
  
#### <a name="to-switch-the-readwrite-mode-to-a-database-programmatically-using-amo"></a><span data-ttu-id="c65f9-125">Программное изменение режима чтения/записи базы данных с помощью объектов AMO</span><span class="sxs-lookup"><span data-stu-id="c65f9-125">To switch the read/write mode to a database programmatically using AMO</span></span>  
  
1.  <span data-ttu-id="c65f9-126">В приложении на C# проведите адаптацию следующего образца кода и выполните указанные задачи.</span><span class="sxs-lookup"><span data-stu-id="c65f9-126">In your C# application, adapt the following sample code and complete the indicated tasks.</span></span>  
  
 `private void SwitchReadWrite(Server server, string dbName,`  
  
 `ReadWriteMode dbReadWriteMode)`  
  
 `{`  
  
 `if (server.Databases.ContainsName(dbName))`  
  
 `{`  
  
 `Database db;`  
  
 `string databaseLocation;`  
  
 `db = server.Databases[dbName];`  
  
 `databaseLocation = db.DbStorageLocation;`  
  
 `if (databaseLocation == null)`  
  
 `{`  
  
 `string dataDir = server.ServerProperties["DataDir"].Value;`  
  
 `String[] possibleFolders = Directory.GetDirectories(dataDir, string.Concat(dbName,"*"), SearchOption.TopDirectoryOnly);`  
  
 `if (possibleFolders.Length > 1)`  
  
 `{`  
  
 `List<String> sortedFolders = new List<string>(possibleFolders.Length);`  
  
 `sortedFolders.AddRange(possibleFolders);`  
  
 `sortedFolders.Sort();`  
  
 `databaseLocation = sortedFolders[sortedFolders.Count - 1];`  
  
 `}`  
  
 `else`  
  
 `{`  
  
 `databaseLocation = possibleFolders[0];`  
  
 `}`  
  
 `}`  
  
 `db.Detach();`  
  
 `server.Attach(databaseLocation, dbReadWriteMode);`  
  
 `}`  
  
 `}`  
  
1.  <span data-ttu-id="c65f9-127">В приложении на C# вызовите метод `SwitchReadWrite()` , указав необходимые параметры.</span><span class="sxs-lookup"><span data-stu-id="c65f9-127">In your C# application, invoke `SwitchReadWrite()` with the necessary parameters.</span></span>  
  
2.  <span data-ttu-id="c65f9-128">Скомпилируйте и выполните код для перемещения базы данных.</span><span class="sxs-lookup"><span data-stu-id="c65f9-128">Compile and execute your code to move the database.</span></span>  
  
#### <a name="to-switch-the-readwrite-mode-to-a-database-by-script-using-xmla"></a><span data-ttu-id="c65f9-129">Изменение режима чтения/записи базы данных с помощью скрипта XML для аналитики</span><span class="sxs-lookup"><span data-stu-id="c65f9-129">To switch the read/write mode to a database by script using XMLA</span></span>  
  
1.  <span data-ttu-id="c65f9-130">Найдите на левой или правой панели среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] базу данных для переключения.</span><span class="sxs-lookup"><span data-stu-id="c65f9-130">Locate the database to be switched in the left or right pane of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="c65f9-131">Щелкните правой кнопкой мыши базу данных и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c65f9-131">Right-click the database and select **Properties**.</span></span> <span data-ttu-id="c65f9-132">Найдите папку с базой данных и запишите ее расположение.</span><span class="sxs-lookup"><span data-stu-id="c65f9-132">Find the database folder and note the location.</span></span> <span data-ttu-id="c65f9-133">Пустое место хранения для базы данных означает, что папка базы данных находится в папке данных сервера.</span><span class="sxs-lookup"><span data-stu-id="c65f9-133">An empty database storage location indicates that the database folder is located in the server data folder.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c65f9-134">После отсоединения базы данных ее расположение будет невозможно определить при помощи среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c65f9-134">As soon as the database is detached, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] can no longer help you obtain the database location.</span></span>  
  
3.  <span data-ttu-id="c65f9-135">Откройте новую вкладку XML для аналитики в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c65f9-135">Open a new XMLA tab in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
4.  <span data-ttu-id="c65f9-136">Скопируйте следующий шаблон скрипта XML для аналитики.</span><span class="sxs-lookup"><span data-stu-id="c65f9-136">Copy the following script template for XMLA:</span></span>  
  
 `<Detach xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">`  
  
 `<Object>`  
  
 `<DatabaseID>%dbName%</DatabaseID>`  
  
 `<Password>%password%</Password>`  
  
 `</Object>`  
  
 `</Detach>`  
  
1.  <span data-ttu-id="c65f9-137">Замените шаблон `%dbName%` именем базы данных, а шаблон `%password%` — соответствующим паролем.</span><span class="sxs-lookup"><span data-stu-id="c65f9-137">Replace `%dbName%` with the name of the database and `%password%` with the password.</span></span> <span data-ttu-id="c65f9-138">Символы «%» являются частью шаблона, и поэтому их необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="c65f9-138">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="c65f9-139">Выполните команду XML для аналитики.</span><span class="sxs-lookup"><span data-stu-id="c65f9-139">Execute the XMLA command.</span></span>  
  
3.  <span data-ttu-id="c65f9-140">Скопируйте следующий шаблон скрипта XML для аналитики в новую вкладку XML для аналитики.</span><span class="sxs-lookup"><span data-stu-id="c65f9-140">Copy the following script template for XMLA in a new XMLA tab</span></span>  
  
 <span data-ttu-id="c65f9-141">`<Attach xmlns="https://schemas.microsoft.com/analysisservices/2003` `/engine` `">`</span><span class="sxs-lookup"><span data-stu-id="c65f9-141">`<Attach xmlns="https://schemas.microsoft.com/analysisservices/2003` `/engine` `">`</span></span>  
  
 `<Folder>%dbFolder%</Folder>`  
  
 `<ReadWriteMode xmlns="https://schemas.microsoft.com/analysisservices/2008/engine/100">%ReadOnlyMode%</ReadWriteMode>`  
  
 `</Attach>`  
  
1.  <span data-ttu-id="c65f9-142">Замените шаблон `%dbFolder%` полным путем к папке базы данных в формате UNC, шаблон `%ReadOnlyMode%` — соответствующим значением (`ReadOnly` или `ReadWrite`), а шаблон `%password%` — паролем.</span><span class="sxs-lookup"><span data-stu-id="c65f9-142">Replace `%dbFolder%` with the complete UNC path of the database folder, `%ReadOnlyMode%` with the corresponding value `ReadOnly` or `ReadWrite`, and `%password%` with the password.</span></span> <span data-ttu-id="c65f9-143">Символы «%» являются частью шаблона, и поэтому их необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="c65f9-143">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="c65f9-144">Выполните команду XML для аналитики.</span><span class="sxs-lookup"><span data-stu-id="c65f9-144">Execute the XMLA command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c65f9-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="c65f9-145">See Also</span></span>  
 <xref:Microsoft.AnalysisServices.Server.Attach%2A>   
 <span data-ttu-id="c65f9-146">[Microsoft. AnalysisServices. Database. Detach \*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span><span class="sxs-lookup"><span data-stu-id="c65f9-146">[Microsoft.AnalysisServices.Database.Detach\*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span></span>  
 <span data-ttu-id="c65f9-147">[Присоединение и отсоединение баз данных Analysis Services](attach-and-detach-analysis-services-databases.md) </span><span class="sxs-lookup"><span data-stu-id="c65f9-147">[Attach and Detach Analysis Services Databases](attach-and-detach-analysis-services-databases.md) </span></span>  
 <span data-ttu-id="c65f9-148">[Место хранения базы данных](database-storage-location.md) </span><span class="sxs-lookup"><span data-stu-id="c65f9-148">[Database Storage Location](database-storage-location.md) </span></span>  
 <span data-ttu-id="c65f9-149">[Режимы readwritemodes базы данных](database-readwritemodes.md) </span><span class="sxs-lookup"><span data-stu-id="c65f9-149">[Database ReadWriteModes](database-readwritemodes.md) </span></span>  
 <span data-ttu-id="c65f9-150">[Элемент Attach](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span><span class="sxs-lookup"><span data-stu-id="c65f9-150">[Attach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span></span>  
 <span data-ttu-id="c65f9-151">[Detach, элемент](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span><span class="sxs-lookup"><span data-stu-id="c65f9-151">[Detach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span></span>  
 <span data-ttu-id="c65f9-152">[ReadWriteMode, элемент](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span><span class="sxs-lookup"><span data-stu-id="c65f9-152">[ReadWriteMode Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span></span>  
 [<span data-ttu-id="c65f9-153">Элемент DbStorageLocation</span><span class="sxs-lookup"><span data-stu-id="c65f9-153">DbStorageLocation Element</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/dbstoragelocation-element)  
  
  
