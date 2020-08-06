---
title: Использование ADO для выполнения запросов SQLXML 4.0
ms.custom: ''
ms.date: 12/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- query testers [SQLXML]
- test scripts
- ADO [SQLXML]
- queries [SQLXML], ADO
- SQLXML, ADO
ms.assetid: 3d54e3bb-7c5f-427e-82f8-1403a54c4f53
author: rothja
ms.author: jroth
ms.openlocfilehash: 169d20b4192e4a5b8e7b32839f2da255fc58d89c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729346"
---
# <a name="using-ado-to-execute-sqlxml-40-queries"></a><span data-ttu-id="3ed46-102">Использование ADO для выполнения запросов SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="3ed46-102">Using ADO to Execute SQLXML 4.0 Queries</span></span>
  <span data-ttu-id="3ed46-103">В предыдущих версиях SQLXML выполнение запросов по HTTP поддерживалось с помощью виртуальных каталогов SQLXML в IIS и ISAPI-фильтра SQLXML.</span><span class="sxs-lookup"><span data-stu-id="3ed46-103">In previous versions of SQLXML, HTTP-based query execution was supported using SQLXML IIS virtual directories and the SQLXML ISAPI filter.</span></span> <span data-ttu-id="3ed46-104">В SQLXML 4.0 эти компоненты были удалены, так как похожая и перекрывающаяся функциональность предоставляется собственными веб-службами с поддержкой XML, начиная с версии [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ed46-104">In SQLXML 4.0, these components have been removed as similar and overlapping functionality is provided with native XML Web services beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="3ed46-105">В качестве альтернативы можно выполнять запросы и использовать SQLXML 4.0 с приложениями на основе COM, используя расширения SQLXML для объектов данных ActiveX (ADO), которые появились в компонентах доступа к данным (MDAC) версии 2.6 и более поздних.</span><span class="sxs-lookup"><span data-stu-id="3ed46-105">As an alternative, you can execute queries and use SQLXML 4.0 with your COM-based applications, by leveraging the SQLXML extensions to ActiveX Data Objects (ADO) that were first introduced in Microsoft Data Access Components (MDAC) 2.6 and later.</span></span>  
  
 <span data-ttu-id="3ed46-106">В этом разделе демонстрируется использование SQLXML и ADO как части приложения Visual Basic Scripting Edition (VBScript) (скрипта с расширением файла VBS).</span><span class="sxs-lookup"><span data-stu-id="3ed46-106">This topic demonstrates using SQLXML and ADO as part of a Visual Basic Scripting Edition (VBScript) application (a script with the .vbs file extension).</span></span> <span data-ttu-id="3ed46-107">Обеспечивает начальную процедуру установки, которая помогает создать повторно и тестировать образцы запросов в документации SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="3ed46-107">It provides initial setup procedures to help you recreate and test query samples in the SQLXML 4.0 documentation.</span></span>  
  
## <a name="creating-the-sqlxml-40-test-script"></a><span data-ttu-id="3ed46-108">Создание тестового скрипта SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="3ed46-108">Creating the SQLXML 4.0 Test Script</span></span>  
 <span data-ttu-id="3ed46-109">В этой процедуре создается файл VBScript (.vbs), Sqlxml4test.vbs, который можно использовать для выполнения запросов SQLXML с использованием ADO-расширений SQLXML в ADO 2.6 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="3ed46-109">In this procedure, you create a VBScript (.vbs) file, Sqlxml4test.vbs, which can be used to execute SQLXML queries by leveraging the SQLXML ADO extensions in ADO 2.6 and later.</span></span>  
  
#### <a name="to-create-the-sqlxml-40-query-tester-using-ado-vbscript"></a><span data-ttu-id="3ed46-110">Создание испытателя запросов SQLXML 4.0 с использованием ADO (VBScript)</span><span class="sxs-lookup"><span data-stu-id="3ed46-110">To create the SQLXML 4.0 query tester using ADO (VBScript).</span></span>  
  
1.  <span data-ttu-id="3ed46-111">Скопируйте приведенный ниже код VBScript и вставьте его в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="3ed46-111">Copy the VBScript code below, and paste it into a text file.</span></span> <span data-ttu-id="3ed46-112">Сохраните файл с именем Sqlxml4test.xml.</span><span class="sxs-lookup"><span data-stu-id="3ed46-112">Save the file as Sqlxml4test.vbs.</span></span>  
  
    ```vb
    WScript.Echo "Query process may take a few seconds to complete. Please be patient."  
  
    ' Note that for SQL Server Native Client to be used as the data provider,  
    ' it needs to be installed on the client computer first. Also, SQLXML extensions   
    ' for ADO are used and available in MDAC 2.6 or later.  
  
    'Set script variables.  
    inputFile = "@@FILE_NAME@@"  
    strServer = "@@SERVER_NAME@@"  
    strDatabase = "@@DATABASE_NAME@@"  
    dbGuid = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  
    ' Establish ADO connection to SQL Server and   
    ' create an instance of the ADO Command object.  
    Set conn = CreateObject("ADODB.Connection")  
    Set cmd = CreateObject("ADODB.Command")  
    conn.Open "Provider=SQLXMLOLEDB.4.0;Data Provider=SQLNCLI11;Server=" & strServer & _  
              ";Database=" & strDatabase & ";Integrated Security=SSPI"  
    Set cmd.ActiveConnection = conn  
  
    ' Create the input stream as an instance of the ADO Stream object.  
    Set inStream = CreateObject("ADODB.Stream")  
    inStream.Open  
    inStream.Charset = "utf-8"  
    inStream.LoadFromFile inputFile  
  
    ' Set ADO Command instance to use input stream.  
    Set cmd.CommandStream = inStream  
  
    ' Set the command dialect.  
    cmd.Dialect = dbGuid  
  
    ' Set a second ADO Stream instance for use as a results stream.   
    Set outStream = CreateObject("ADODB.Stream")  
    outStream.Open  
  
    ' Set dynamic properties used by the SQLXML ADO command instance.   
    cmd.Properties("XML Root").Value = "ROOT"  
    cmd.Properties("Output Encoding").Value = "UTF-8"  
  
    ' Connect the results stream to the command instance and execute the command.  
    cmd.Properties("Output Stream").Value = outStream  
    cmd.Execute , , 1024  
  
    ' Echo cropped/partial results to console.  
    WScript.Echo Left(outStream.ReadText, 1023)  
  
    inStream.Close  
    outStream.Close  
    ```  
  
2.  <span data-ttu-id="3ed46-113">Обновите следующие значения скриптов для образца, который предстоит протестировать, и тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="3ed46-113">Update the following script values for the sample you are trying to test and your test environment.</span></span>  
  
    -   <span data-ttu-id="3ed46-114">Найдите «`@@FILE_NAME@@`» и замените его именем файла шаблона.</span><span class="sxs-lookup"><span data-stu-id="3ed46-114">Find "`@@FILE_NAME@@`" and replace it with the name of your template file.</span></span>  
  
    -   <span data-ttu-id="3ed46-115">Найдите «`@@SERVER_NAME@@`» и замените его именем экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (например, «`(local)`», если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняется локально).</span><span class="sxs-lookup"><span data-stu-id="3ed46-115">Find "`@@SERVER_NAME@@`" and replace it with the name of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (for example, "`(local)`" if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running locally).</span></span>  
  
    -   <span data-ttu-id="3ed46-116">Найдите «`@@DATABASE_NAME@@`» и замените его именем базы данных (например, «`AdventureWorks2012`» или «`tempdb`»).</span><span class="sxs-lookup"><span data-stu-id="3ed46-116">Find "`@@DATABASE_NAME@@`" and replace it with the name of the database (for example, either "`AdventureWorks2012`" or "`tempdb`").</span></span>  
  
     <span data-ttu-id="3ed46-117">Обновите любые другие значения, упомянутые в конкретных инструкциях для примера, который нужно создать повторно локально на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3ed46-117">Update any other values if mentioned in the specific instructions for the example you are attempting to recreate locally on your computer.</span></span>  
  
3.  <span data-ttu-id="3ed46-118">Сохраните файл и закройте его.</span><span class="sxs-lookup"><span data-stu-id="3ed46-118">Save the file and close it.</span></span>  
  
4.  <span data-ttu-id="3ed46-119">Проверьте, что созданы все дополнительные файлы, такие как XML-шаблоны или схемы, которые являются частью образца, который нужно локально создать повторно на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3ed46-119">Verify that you have created any additional files, such as XML templates or schemas that are part of the sample you are attempting to recreate locally on your computer.</span></span> <span data-ttu-id="3ed46-120">Эти файлы должны находиться в том же каталоге, в котором сохранен файл тестового скрипта (Sqlxml4test.vbs).</span><span class="sxs-lookup"><span data-stu-id="3ed46-120">These files should be located in the same directory where you have saved the test script file (Sqlxml4test.vbs).</span></span>  
  
5.  <span data-ttu-id="3ed46-121">Следуйте инструкциям следующего раздела по использованию тестового скрипта SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="3ed46-121">Follow the instructions in the next section for how to use the SQLXML 4.0 test script.</span></span>  
  
## <a name="using-the-sqlxml-40-test-script"></a><span data-ttu-id="3ed46-122">Использование тестового скрипта SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="3ed46-122">Using the SQLXML 4.0 Test Script</span></span>  
 <span data-ttu-id="3ed46-123">Следующая процедура описывает способ использования файлов Sqlxml4test.vbs для тестирования примеров запросов, предоставленных в этой документации.</span><span class="sxs-lookup"><span data-stu-id="3ed46-123">The following procedure describes how to use the Sqlxml4test.vbs files to test the example queries provided in this documentation.</span></span>  
  
#### <a name="to-use-the-sqlxml-40-query-tester"></a><span data-ttu-id="3ed46-124">Использование испытателя запросов SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="3ed46-124">To use the SQLXML 4.0 query tester</span></span>  
  
1.  <span data-ttu-id="3ed46-125">Проверьте, что установлен собственный клиент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ed46-125">Verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is installed, as follows:</span></span>  
  
    1.  <span data-ttu-id="3ed46-126">В меню " **Пуск** " выберите пункт " **Параметры**", а затем " **Панель управления**".</span><span class="sxs-lookup"><span data-stu-id="3ed46-126">From the **Start** menu, point to **Settings**, and then click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="3ed46-127">В панели управления откройте окно **Установка и удаление программ** .</span><span class="sxs-lookup"><span data-stu-id="3ed46-127">In Control Panel, open **Add or Remove Programs**</span></span>  
  
    3.  <span data-ttu-id="3ed46-128">В списке установленных программ убедитесь, что в списке присутствует **Microsoft SQL Server Native Client** .</span><span class="sxs-lookup"><span data-stu-id="3ed46-128">In the list of currently installed programs, verify that **Microsoft SQL Server Native Client** appears in the list.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="3ed46-129">Если необходимо установить [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственный клиент, см. статью [Установка SQL Server Native Client](../native-client/applications/installing-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="3ed46-129">If you need to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, see [Installing SQL Server Native Client](../native-client/applications/installing-sql-server-native-client.md).</span></span>  
  
2.  <span data-ttu-id="3ed46-130">Проверьте, что на клиентском компьютере установлена версия MDAC 2.6 или более поздняя.</span><span class="sxs-lookup"><span data-stu-id="3ed46-130">Verify that the version of MDAC installed for the client computer is 2.6 or later.</span></span> <span data-ttu-id="3ed46-131">Если необходимо проверить сведения о версии MDAC, можно использовать средство проверки компонентов MDAC, которое предоставляется бесплатно для загрузки с веб-сайта корпорации Майкрософт [https://www.microsoft.com/](https://www.microsoft.com/) .</span><span class="sxs-lookup"><span data-stu-id="3ed46-131">If you need to verify MDAC version information, you can use the MDAC Component Checker tool, which is provided as free download from the Microsoft Web site [https://www.microsoft.com/](https://www.microsoft.com/).</span></span> <span data-ttu-id="3ed46-132">Для получения дополнительных сведений выполните поиск по фразе "средство проверки компонентов MDAC" на веб-сайте Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3ed46-132">For more information, search on "MDAC Component Checker" on the Microsoft Web site.</span></span>  
  
3.  <span data-ttu-id="3ed46-133">Выполните скрипт.</span><span class="sxs-lookup"><span data-stu-id="3ed46-133">Execute the script.</span></span>  
  
     <span data-ttu-id="3ed46-134">Файл VBScript можно выполнить из командной строки с использованием Cscript.exe или дважды щелкнув файл Sqlxml4test.vbs, чтобы вызвать сервер скриптов Windows (WScript.exe).</span><span class="sxs-lookup"><span data-stu-id="3ed46-134">You can execute the VBScript file either at the command line using Cscript.exe or by double-clicking Sqlxml4test.vbs file to invoke the Windows Script Host (WScript.exe).</span></span>  
  
     <span data-ttu-id="3ed46-135">При выполнении скрипт должен вывести сообщение, предупреждая, что выполнение скрипта может занять некоторое время перед возвратом и отображением результатов запроса как вывода скрипта.</span><span class="sxs-lookup"><span data-stu-id="3ed46-135">When executed, the script should display a message to alert you that the script might take a few moments to execute before returning and displaying query results as script output.</span></span> <span data-ttu-id="3ed46-136">После того как данные будут выведены, сравните их с ожидаемыми результатами запроса.</span><span class="sxs-lookup"><span data-stu-id="3ed46-136">When the output appears, compare its contents to the expected results for the sample.</span></span>  
  
  
