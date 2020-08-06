---
title: Перемещение базы данных Analysis Services | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- moving databases [Anlysis Services]
- moving databases
- operations [Analysis Services - multidimensional data]
ms.assetid: fa644e5d-e276-445e-98d9-673afcfb83fe
author: minewiskan
ms.author: owend
ms.openlocfilehash: bd9b099ad6765d9caccb9b0af6622eb4aa77d38c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740550"
---
# <a name="move-an-analysis-services-database"></a><span data-ttu-id="e35c8-102">Перемещение базы данных служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="e35c8-102">Move an Analysis Services Database</span></span>
  <span data-ttu-id="e35c8-103">Часто возникают ситуации, когда администратору баз данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] необходимо переместить базу данных для многомерной или табличной модели в другое место.</span><span class="sxs-lookup"><span data-stu-id="e35c8-103">There are often situations when an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database administrator (dba) wants to move a multidimensional or tabular model database to a different location.</span></span> <span data-ttu-id="e35c8-104">Такие ситуации часто обусловлены потребностями предприятия, например необходимостью переместить базу данных на другой диск для повышения производительности, освободить место для увеличения размера базы данных или при обновлении какого-либо продукта.</span><span class="sxs-lookup"><span data-stu-id="e35c8-104">These situations are often driven by business needs, such as moving the database to a different disk for better performance, gaining room for database growth, or to upgrade a product.</span></span>  
  
 <span data-ttu-id="e35c8-105">Существует много способов перенести базу данных в другое место.</span><span class="sxs-lookup"><span data-stu-id="e35c8-105">A database can be moved in many ways.</span></span> <span data-ttu-id="e35c8-106">В этом документе описаны следующие распространенные сценарии:</span><span class="sxs-lookup"><span data-stu-id="e35c8-106">This document explains the following common scenarios:</span></span>  
  
-   <span data-ttu-id="e35c8-107">интерактивно с помощью среды SSMS;</span><span class="sxs-lookup"><span data-stu-id="e35c8-107">Interactively using SSMS</span></span>  
  
-   <span data-ttu-id="e35c8-108">программным способом с помощью объектов AMO;</span><span class="sxs-lookup"><span data-stu-id="e35c8-108">Programmatically using AMO</span></span>  
  
-   <span data-ttu-id="e35c8-109">с помощью скриптов, используя XML для аналитики</span><span class="sxs-lookup"><span data-stu-id="e35c8-109">By script using XMLA</span></span>  
  
 <span data-ttu-id="e35c8-110">При выполнении любого сценария необходимо, чтобы пользователь получил доступ к папке базы данных и применил один из методов перемещения файлов в конечное место назначения.</span><span class="sxs-lookup"><span data-stu-id="e35c8-110">All scenarios require the user to access the database folder and to use a method for moving the files to the desired final destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e35c8-111">При отсоединении базы данных без назначения ей пароля эта база данных оказывается в незащищенном состоянии.</span><span class="sxs-lookup"><span data-stu-id="e35c8-111">Detaching a database without assigning a password to it leaves the database in an unsecured state.</span></span> <span data-ttu-id="e35c8-112">Рекомендуется назначить базе данных пароль для защиты конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="e35c8-112">We recommend assigning a password to the database to protect confidential information.</span></span> <span data-ttu-id="e35c8-113">Кроме того, к папке базы данных, к вложенным папкам и к файлам следует применять соответствующие меры защиты доступа, чтобы исключить несанкционированный доступ к этим объектам.</span><span class="sxs-lookup"><span data-stu-id="e35c8-113">Also, the corresponding access security should be applied to the database folder, sub-folders, and files to prevent unauthorized access to them.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="e35c8-114">Процедуры</span><span class="sxs-lookup"><span data-stu-id="e35c8-114">Procedures</span></span>  
  
#### <a name="moving-a-database-interactively-using-ssms"></a><span data-ttu-id="e35c8-115">Перемещение базы данных в интерактивном режиме с помощью среды SSMS</span><span class="sxs-lookup"><span data-stu-id="e35c8-115">Moving a database interactively using SSMS</span></span>  
  
1.  <span data-ttu-id="e35c8-116">Найдите перемещаемую базу данных на левой или правой панели среды SSMS.</span><span class="sxs-lookup"><span data-stu-id="e35c8-116">Locate the database to be moved in the left or right pane of SSMS.</span></span>  
  
2.  <span data-ttu-id="e35c8-117">Щелкните правой кнопкой мыши базу данных и выберите пункт **отсоединить...**</span><span class="sxs-lookup"><span data-stu-id="e35c8-117">Right-click on the database and select **Detach...**</span></span>  
  
3.  <span data-ttu-id="e35c8-118">Назначьте пароль отсоединяемой базе данных и нажмите кнопку **ОК** , чтобы выполнить команду отсоединения.</span><span class="sxs-lookup"><span data-stu-id="e35c8-118">Assign a password to the database to be detached, then click **OK** to execute the detach command.</span></span>  
  
4.  <span data-ttu-id="e35c8-119">При помощи любого механизма, поддерживаемого операционной системой, или стандартным для вас образом выполните перемещение папки базы данных в новое расположение.</span><span class="sxs-lookup"><span data-stu-id="e35c8-119">Use any operating system mechanism or your standard method for moving files to move the database folder to the new location.</span></span>  
  
5.  <span data-ttu-id="e35c8-120">Найдите папку **Базы данных** на левой или правой панели среды SSMS.</span><span class="sxs-lookup"><span data-stu-id="e35c8-120">Locate the **Databases** folder in the left or right pane of SSMS.</span></span>  
  
6.  <span data-ttu-id="e35c8-121">Щелкните правой кнопкой мыши папку **базы данных** и выберите команду **Присоединить...**</span><span class="sxs-lookup"><span data-stu-id="e35c8-121">Right-click on the **Databases** folder and select **Attach...**</span></span>  
  
7.  <span data-ttu-id="e35c8-122">В текстовое поле **папка** впечатайте новое местоположение папки базы данных.</span><span class="sxs-lookup"><span data-stu-id="e35c8-122">In the **folder** text box, type the new location of the database folder.</span></span> <span data-ttu-id="e35c8-123">Кроме того, можно нажать кнопку обзора (**...**), чтобы найти папку базы данных.</span><span class="sxs-lookup"><span data-stu-id="e35c8-123">Alternatively, you can use the browse button (**...**) to locate the database folder.</span></span>  
  
8.  <span data-ttu-id="e35c8-124">Выберите `ReadWrite` режим для базы данных.</span><span class="sxs-lookup"><span data-stu-id="e35c8-124">Select the `ReadWrite` mode for the database.</span></span>  
  
9. <span data-ttu-id="e35c8-125">Введите пароль, который использовался в шаге 3, и нажмите кнопку **ОК** , чтобы выполнить команду присоединения.</span><span class="sxs-lookup"><span data-stu-id="e35c8-125">Type the password used in step 3 and click **OK** to execute the attach command.</span></span>  
  
#### <a name="moving-a-database-programmatically-using-amo"></a><span data-ttu-id="e35c8-126">Перемещение базы данных программным путем с помощью объектов AMO</span><span class="sxs-lookup"><span data-stu-id="e35c8-126">Moving a database programmatically using AMO</span></span>  
  
1.  <span data-ttu-id="e35c8-127">В приложении на C# проведите адаптацию следующего образца кода и выполните указанные задачи.</span><span class="sxs-lookup"><span data-stu-id="e35c8-127">In your C# application, adapt the following sample code and complete the indicated tasks.</span></span>  
  
 `private void MoveDb(Server server, string dbName,`  
  
 `string dbInitialLocation, string dbFinalLocation,`  
  
 `string dbPassword, ReadWriteMode dbReadWriteMode)`  
  
 `{`  
  
 `//Verify dbInitialLocation exists before continuing`  
  
 `if (server.Databases.ContainsName(dbName))`  
  
 `{`  
  
 `Database db;`  
  
 `//Save current cursor and change cursor to Cursors.WaitCursor`  
  
 `db = server.Databases[dbName];`  
  
 `db.Detach(dbPassword);`  
  
 `//Add your own code to copy the database files to the destination where you intend to attach the database`  
  
 `//Verify dbFinalLocation exists before continuing`  
  
 `server.Attach(dbFinalLocation, dbReadWriteMode, dbPassword);`  
  
 `//Restore cursor to its original`  
  
 `}`  
  
 `}`  
  
1.  <span data-ttu-id="e35c8-128">В приложении на C# вызовите метод `MoveDb()` , указав необходимые параметры.</span><span class="sxs-lookup"><span data-stu-id="e35c8-128">In your C# application, invoke `MoveDb()` with the necessary parameters.</span></span>  
  
2.  <span data-ttu-id="e35c8-129">Скомпилируйте и выполните код для перемещения базы данных.</span><span class="sxs-lookup"><span data-stu-id="e35c8-129">Compile and execute your code to move the database.</span></span>  
  
#### <a name="moving-a-database-by-script-using-xmla"></a><span data-ttu-id="e35c8-130">Перемещение базы данных с помощью скрипта XML для аналитики</span><span class="sxs-lookup"><span data-stu-id="e35c8-130">Moving a database by script using XMLA</span></span>  
  
1.  <span data-ttu-id="e35c8-131">Откройте новую вкладку XML для аналитики в среде SSMS.</span><span class="sxs-lookup"><span data-stu-id="e35c8-131">Open a new XMLA tab in SSMS.</span></span>  
  
2.  <span data-ttu-id="e35c8-132">Скопируйте следующий шаблон скрипта XML для аналитики.</span><span class="sxs-lookup"><span data-stu-id="e35c8-132">Copy the following script template for XMLA</span></span>  
  
 `<Detach xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">`  
  
 `<Object>`  
  
 `<DatabaseID>%dbName%</DatabaseID>`  
  
 `<Password>%password%</Password>`  
  
 `</Object>`  
  
 `</Detach>`  
  
1.  <span data-ttu-id="e35c8-133">Замените шаблон `%dbName%` именем базы данных, а шаблон `%password%` — соответствующим паролем.</span><span class="sxs-lookup"><span data-stu-id="e35c8-133">Replace `%dbName%` with the name of the database and `%password%` with the password.</span></span> <span data-ttu-id="e35c8-134">Символы «%» являются частью шаблона, и поэтому их необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="e35c8-134">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="e35c8-135">Выполните команду XML для аналитики.</span><span class="sxs-lookup"><span data-stu-id="e35c8-135">Execute the XMLA command.</span></span>  
  
3.  <span data-ttu-id="e35c8-136">При помощи любого механизма, поддерживаемого операционной системой, или стандартным для вас образом выполните перемещение папки базы данных в новое расположение.</span><span class="sxs-lookup"><span data-stu-id="e35c8-136">Use any operating system mechanism or your standard method for moving files to move the database folder to the new location.</span></span>  
  
4.  <span data-ttu-id="e35c8-137">Скопируйте следующий шаблон скрипта XML для аналитики в новую вкладку XML для аналитики.</span><span class="sxs-lookup"><span data-stu-id="e35c8-137">Copy the following script template for XMLA in a new XMLA tab</span></span>  
  
 `<Attach xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">`  
  
 `<Folder>%dbFolder%</Folder>`  
  
 `<ReadWriteMode xmlns="https://schemas.microsoft.com/analysisservices/2008/engine/100">%ReadOnlyMode%</ReadWriteMode>`  
  
 `</Attach>`  
  
1.  <span data-ttu-id="e35c8-138">Замените шаблон `%dbFolder%` полным путем к папке базы данных в формате UNC, шаблон `%ReadOnlyMode%` — соответствующим значением (`ReadOnly` или `ReadWrite`), а шаблон `%password%` — паролем.</span><span class="sxs-lookup"><span data-stu-id="e35c8-138">Replace `%dbFolder%` with the complete UNC path of the database folder, `%ReadOnlyMode%` with the corresponding value `ReadOnly` or `ReadWrite`, and `%password%` with the password.</span></span> <span data-ttu-id="e35c8-139">Символы «%» являются частью шаблона, и поэтому их необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="e35c8-139">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="e35c8-140">Выполните команду XML для аналитики.</span><span class="sxs-lookup"><span data-stu-id="e35c8-140">Execute the XMLA command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e35c8-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="e35c8-141">See Also</span></span>  
 <xref:Microsoft.AnalysisServices.Server.Attach%2A>   
 <span data-ttu-id="e35c8-142">[Microsoft. AnalysisServices. Database. Detach \*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span><span class="sxs-lookup"><span data-stu-id="e35c8-142">[Microsoft.AnalysisServices.Database.Detach\*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span></span>  
 <span data-ttu-id="e35c8-143">[Присоединение и отсоединение баз данных Analysis Services](attach-and-detach-analysis-services-databases.md) </span><span class="sxs-lookup"><span data-stu-id="e35c8-143">[Attach and Detach Analysis Services Databases](attach-and-detach-analysis-services-databases.md) </span></span>  
 <span data-ttu-id="e35c8-144">[Место хранения базы данных](database-storage-location.md) </span><span class="sxs-lookup"><span data-stu-id="e35c8-144">[Database Storage Location](database-storage-location.md) </span></span>  
 <span data-ttu-id="e35c8-145">[Режимы readwritemodes базы данных](database-readwritemodes.md) </span><span class="sxs-lookup"><span data-stu-id="e35c8-145">[Database ReadWriteModes](database-readwritemodes.md) </span></span>  
 <span data-ttu-id="e35c8-146">[Элемент Attach](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span><span class="sxs-lookup"><span data-stu-id="e35c8-146">[Attach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span></span>  
 <span data-ttu-id="e35c8-147">[Detach, элемент](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span><span class="sxs-lookup"><span data-stu-id="e35c8-147">[Detach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span></span>  
 <span data-ttu-id="e35c8-148">[ReadWriteMode, элемент](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span><span class="sxs-lookup"><span data-stu-id="e35c8-148">[ReadWriteMode Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span></span>  
 [<span data-ttu-id="e35c8-149">Элемент DbStorageLocation</span><span class="sxs-lookup"><span data-stu-id="e35c8-149">DbStorageLocation Element</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/dbstoragelocation-element)  
  
  
