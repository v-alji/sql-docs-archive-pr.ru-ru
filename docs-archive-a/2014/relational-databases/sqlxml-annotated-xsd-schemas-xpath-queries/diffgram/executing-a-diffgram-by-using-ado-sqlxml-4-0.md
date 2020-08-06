---
title: Запуск DiffGram с помощью ADO (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- providers [SQLXML], SQLOLEDB Provider
- ADO [SQLXML]
- SQLXMLOLEDB Provider, DiffGrams
- data providers [SQLXML], SQLOLEDB Provider
- DiffGrams [SQLXML], ADO
ms.assetid: 741fce82-de83-4923-86eb-30acb5b9a5e6
author: rothja
ms.author: jroth
ms.openlocfilehash: b96db25fd46b1ecbbc15c8acd912743e5560f178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664814"
---
# <a name="executing-a-diffgram-by-using-ado-sqlxml-40"></a><span data-ttu-id="b585c-102">Выполнение дельты с использованием ADO (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="b585c-102">Executing a DiffGram by Using ADO (SQLXML 4.0)</span></span>
  <span data-ttu-id="b585c-103">Следующее приложение на языке [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic использует ADO для установки соединения с экземпляром Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и выполняет DiffGram.</span><span class="sxs-lookup"><span data-stu-id="b585c-103">This [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic application uses ADO to establish a connection to an instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and then executes a DiffGram.</span></span> <span data-ttu-id="b585c-104">В этом приложении дельты и схема XSD хранятся в файле.</span><span class="sxs-lookup"><span data-stu-id="b585c-104">In this application, the DiffGram and the XSD schema are stored in a file.</span></span> <span data-ttu-id="b585c-105">Приложение загружает DiffGram из заданного файла.</span><span class="sxs-lookup"><span data-stu-id="b585c-105">The application loads the DiffGram from the specified file.</span></span> <span data-ttu-id="b585c-106">Вы можете использовать любую из дельтами (и связанную с ней схему XSD), описанную в разделе [примеры DiffGram](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="b585c-106">You can use any of the DiffGrams (and the associated XSD schema) described in [DiffGram Examples](diffgram-examples-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="b585c-107">Ниже приводится последовательность действий в образце приложения.</span><span class="sxs-lookup"><span data-stu-id="b585c-107">This is the process for the sample application:</span></span>  
  
-   <span data-ttu-id="b585c-108">Объект **conn** (**ADODB. Соединение**) устанавливает соединение с выполняющимся экземпляром SQL Server на определенном сервере.</span><span class="sxs-lookup"><span data-stu-id="b585c-108">The **conn** object (**ADODB.Connection**) establishes a connection to a running instance of SQL Server on a specific server.</span></span>  
  
-   <span data-ttu-id="b585c-109">Объект **cmd** (**ADODB. Command**) выполняется для установленного соединения.</span><span class="sxs-lookup"><span data-stu-id="b585c-109">The **cmd** object (**ADODB.Command**) executes on the established connection.</span></span>  
  
-   <span data-ttu-id="b585c-110">В качестве диалекта команды задано значение DBGUID_MSSQLXML.</span><span class="sxs-lookup"><span data-stu-id="b585c-110">The command dialect is set to DBGUID_MSSQLXML.</span></span>  
  
-   <span data-ttu-id="b585c-111">Объект DiffGram копируется в поток команд (**strmIn**) из файла.</span><span class="sxs-lookup"><span data-stu-id="b585c-111">The DiffGram is copied to the command stream (**strmIn**) from a file.</span></span>  
  
-   <span data-ttu-id="b585c-112">Поток вывода команды задается как объект **стрмаут** (**ADODB. Stream**) для получения возвращенных данных.</span><span class="sxs-lookup"><span data-stu-id="b585c-112">The command's output stream is set to the **StrmOut** object (**ADODB.Stream**) to receive any returned data.</span></span>  
  
-   <span data-ttu-id="b585c-113">При использовании поставщика SQLOLEDB вы по умолчанию получаете функциональность Microsoft SQLXML, предоставляемую библиотекой Sqlxmlx.dll.</span><span class="sxs-lookup"><span data-stu-id="b585c-113">When you are using the SQLOLEDB Provider, by default you will get the Microsoft SQLXML functionality provided by Sqlxmlx.dll.</span></span> <span data-ttu-id="b585c-114">Чтобы использовать Sqlxml4.dll с поставщиком SQLOLEDB, свойство **версии SQLXML** должно иметь значение **SQLXML. 4.0** для объекта **соединения** поставщика SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="b585c-114">To use Sqlxml4.dll with the SQLOLEDB Provider, the **SQLXML Version** property must be set to **SQLXML.4.0** on the SQLOLEDB Provider **Connection** object.</span></span>  
  
-   <span data-ttu-id="b585c-115">Команда (дельта) будет выполнена.</span><span class="sxs-lookup"><span data-stu-id="b585c-115">The command (DiffGram) is executed.</span></span>  
  
 <span data-ttu-id="b585c-116">Следующий код представляет собой образец приложения.</span><span class="sxs-lookup"><span data-stu-id="b585c-116">The following code is the sample application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b585c-117">В коде необходимо задать имя экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в строке соединения.</span><span class="sxs-lookup"><span data-stu-id="b585c-117">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
Private Sub Command1_Click()  
  Dim cmd As New ADODB.Command  
  Dim conn As New ADODB.Connection  
  Dim strmOut As New ADODB.Stream  
  Dim strmIn As New ADODB.Stream  
  
  'Open a connection to SQL Server.  
  conn.Provider = "SQLOLEDB"  
  conn.Open "server=SqlServerName; database=tempdb; Integrated Security=SSPI; "  
  conn.Properties("SQLXML Version") = "SQLXML.4.0"  
  Set cmd.ActiveConnection = conn  
  strmIn.Open  
  strmIn.Charset = "UTF-8"  
  strmIn.LoadFromFile "C:\SomeFilePath\SampleDiffGram.xml"  
  strmIn.Position = 0  
  Set cmd.CommandStream = strmIn  
  
  strmOut.Open  
  cmd.Properties("Output Stream").Value = strmOut  
  cmd.Properties("Output Encoding").Value = "UTF-8"  
  
  cmd.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  cmd.Properties("Mapping Schema") = "C:\SomeFilePath\SampleDiffGram.xml"  
  cmd.Execute , , adExecuteStream  
  strmOut.Position = 0  
  Set cmd = Nothing  
  strmOut.Charset = "UTF-8"  
  strmOut.SaveToFile "C:\DropIt.txt", adSaveCreateOverWrite  
  strmOut.Close  
  Set strmOut = Nothing  
  
End Sub  
```  
  
### <a name="to-test-the-diffgram"></a><span data-ttu-id="b585c-118">Проверка дельты</span><span class="sxs-lookup"><span data-stu-id="b585c-118">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="b585c-119">В папку на компьютере скопируйте любую из дельтами и соответствующую схему XSD из одного из примеров в [примерах DiffGram](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="b585c-119">To a folder on your computer, copy any one of the DiffGrams and the corresponding XSD schema from one of the examples in [DiffGram Examples](diffgram-examples-sqlxml-4-0.md).</span></span>  
  
2.  <span data-ttu-id="b585c-120">Откройте Visual Basic и создайте проект стандартного исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="b585c-120">Open Visual Basic and create a Standard EXE project.</span></span>  
  
3.  <span data-ttu-id="b585c-121">Добавьте эти ссылки в проект:</span><span class="sxs-lookup"><span data-stu-id="b585c-121">Add these references to the project:</span></span>  
  
    ```  
    Microsoft ActiveX Data Objects 2.8 Library  
    ```  
  
4.  <span data-ttu-id="b585c-122">На панели элементов щелкните **CommandButton**, а затем нарисуйте кнопку в форме.</span><span class="sxs-lookup"><span data-stu-id="b585c-122">In the Toolbox, click **CommandButton**, and then draw a button on the form.</span></span>  
  
5.  <span data-ttu-id="b585c-123">Дважды нажмите кнопку, чтобы изменить ее код, и добавьте код приложения из раздела.</span><span class="sxs-lookup"><span data-stu-id="b585c-123">Double-click the button to edit the code, and add the application code that is provided in the topic.</span></span>  
  
6.  <span data-ttu-id="b585c-124">Отредактируйте код, чтобы в нем указывались имена файлов DiffGram и XSD.</span><span class="sxs-lookup"><span data-stu-id="b585c-124">Edit the code to specify the DiffGram and XSD file names.</span></span> <span data-ttu-id="b585c-125">Также отредактируйте строку соединения.</span><span class="sxs-lookup"><span data-stu-id="b585c-125">Also edit the connection string as appropriate.</span></span>  
  
7.  <span data-ttu-id="b585c-126">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="b585c-126">Execute the application.</span></span> <span data-ttu-id="b585c-127">Результат выполнения зависит от типа DiffGram.</span><span class="sxs-lookup"><span data-stu-id="b585c-127">The result of the execution depends on what DiffGram you are executing.</span></span>  
  
  
