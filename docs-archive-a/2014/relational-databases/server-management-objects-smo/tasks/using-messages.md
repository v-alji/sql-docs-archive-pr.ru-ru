---
title: Использование сообщений | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- messages [SMO]
ms.assetid: 4037a866-4826-4c1f-890c-e7e3658adf13
author: stevestein
ms.author: sstein
ms.openlocfilehash: 53b2e0fa4be2dfd53cdd8f4f0cacb7ae0bd79edb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667656"
---
# <a name="using-messages"></a><span data-ttu-id="26d6a-102">Использование сообщений</span><span class="sxs-lookup"><span data-stu-id="26d6a-102">Using Messages</span></span>
  <span data-ttu-id="26d6a-103">В SMO системные сообщения представлены объектом <xref:Microsoft.SqlServer.Management.Smo.SystemMessageCollection>, принадлежащим объекту `Server`.</span><span class="sxs-lookup"><span data-stu-id="26d6a-103">In SMO, system messages are represented by the <xref:Microsoft.SqlServer.Management.Smo.SystemMessageCollection> object that belongs to the `Server` object.</span></span> <span data-ttu-id="26d6a-104">Так как системные сообщения нельзя изменить, свойства объекта `SystemMessage` доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="26d6a-104">Because the system messages cannot be modified, `SystemMessage` object properties are read-only.</span></span>  
  
 <span data-ttu-id="26d6a-105">Определяемые пользователем сообщения представлены в SMO программно объектом <xref:Microsoft.SqlServer.Management.Smo.UserDefinedMessageCollection>.</span><span class="sxs-lookup"><span data-stu-id="26d6a-105">User-defined messages are represented programmatically in SMO by the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedMessageCollection> object.</span></span> <span data-ttu-id="26d6a-106">Существующие определяемые пользователем сообщения могут быть обнаружены при проходе по коллекции.</span><span class="sxs-lookup"><span data-stu-id="26d6a-106">Existing user-defined messages can be discovered by iterating through the collection.</span></span> <span data-ttu-id="26d6a-107">Новые определяемые пользователем сообщения могут создаваться путем создания нового объекта `UserDefinedMessage` и установки соответствующих свойств.</span><span class="sxs-lookup"><span data-stu-id="26d6a-107">New user-defined messages can be created by instantiating a new `UserDefinedMessage` object and setting the appropriate properties.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="26d6a-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="26d6a-108">Examples</span></span>  
 <span data-ttu-id="26d6a-109">В следующих примерах кода для создания приложения необходимо выбрать среду программирования, шаблон программирования и язык программирования.</span><span class="sxs-lookup"><span data-stu-id="26d6a-109">For the following code examples, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="26d6a-110">Дополнительные сведения см. в статьях [Создание проекта Visual Basic SMO в Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) и [Создание проекта Visual C&#35; SMO в Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="26d6a-110">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="finding-a-particular-system-message-in-visual-basic"></a><span data-ttu-id="26d6a-111">Обнаружение определенного системного сообщения на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26d6a-111">Finding a Particular System Message in Visual Basic</span></span>  
 <span data-ttu-id="26d6a-112">Пример кода показывает, как определить системное сообщение по идентификатору и отобразить его.</span><span class="sxs-lookup"><span data-stu-id="26d6a-112">The code example shows how to identify a system message by ID number and display the message.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMessages1](SMO How to#SMO_VBMessages1)]  -->  
  
## <a name="finding-a-particular-system-message-in-visual-c"></a><span data-ttu-id="26d6a-113">Обнаружение определенного системного сообщения на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="26d6a-113">Finding a Particular System Message in Visual C#</span></span>  
 <span data-ttu-id="26d6a-114">Пример кода показывает, как определить системное сообщение по идентификатору и отобразить его.</span><span class="sxs-lookup"><span data-stu-id="26d6a-114">The code example shows how to identify a system message by ID number and display the message.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
            //Reference an existing system message using the   
            //ItemByIdAndLanguage method.   
            SystemMessage msg = default(SystemMessage);  
            msg = srv.SystemMessages.ItemByIdAndLanguage(14126, "us_english");  
            //Display the message ID and text.   
            Console.WriteLine(msg.ID.ToString() + " " + msg.Text);  
        }  
```  
  
## <a name="finding-a-particular-system-message-in-powershell"></a><span data-ttu-id="26d6a-115">Обнаружение определенного системного сообщения в PowerShell</span><span class="sxs-lookup"><span data-stu-id="26d6a-115">Finding a Particular System Message in PowerShell</span></span>  
 <span data-ttu-id="26d6a-116">Пример кода показывает, как определить системное сообщение по идентификатору и отобразить его.</span><span class="sxs-lookup"><span data-stu-id="26d6a-116">The code example shows how to identify a system message by ID number and display the message.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\  
$srv = Get-Item default  
  
#Get the message 14126 in US English and display it  
$msg = $srv.SystemMessages.ItemByIdAndLanguage(14126, "us_english")  
$msg.ID.ToString() + " "+ $msg.Text  
```  
  
## <a name="adding-a-new-user-defined-message-in-visual-basic"></a><span data-ttu-id="26d6a-117">Добавление нового определяемого пользователем сообщения на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26d6a-117">Adding a New User-Defined Message in Visual Basic</span></span>  
 <span data-ttu-id="26d6a-118">Пример кода демонстрирует, как создать определяемое пользователем сообщение с идентификатором больше 50 000.</span><span class="sxs-lookup"><span data-stu-id="26d6a-118">The code example demonstrates how to create a user-defined message with an ID greater than 50000.</span></span>  
  
```vb
Dim mysrv As Server  
mysrv = New Server  
Dim udm As UserDefinedMessage  
udm = New UserDefinedMessage(mysrv, 50003, "us_english", 16, "Test message")  
udm.Create()  
```  
  
## <a name="adding-a-new-user-defined-message-in-visual-c"></a><span data-ttu-id="26d6a-119">Добавление нового определяемого пользователем сообщения на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="26d6a-119">Adding a New User-Defined Message in Visual C#</span></span>  
 <span data-ttu-id="26d6a-120">Пример кода демонстрирует, как создать определяемое пользователем сообщение с идентификатором больше 50 000.</span><span class="sxs-lookup"><span data-stu-id="26d6a-120">The code example demonstrates how to create a user-defined message with an ID greater than 50000.</span></span>  
  
```csharp
{
            Server mysrv = new Server();  
  
            UserDefinedMessage udm = new UserDefinedMessage(mysrv, 50030, "us_english",16, "Test message");  
            udm.Create();  
             UserDefinedMessage  msg = mysrv.UserDefinedMessages.ItemByIdAndLanguage(50030, "us_english");  
            //Display the message ID and text.   
            Console.WriteLine(msg.ID.ToString() + " " + msg.Text);  
  
        }  
```  
  
## <a name="adding-a-new-user-defined-message-in-powershell"></a><span data-ttu-id="26d6a-121">Добавление нового, определяемого пользователем сообщения в PowerShell</span><span class="sxs-lookup"><span data-stu-id="26d6a-121">Adding a New User-Defined Message in PowerShell</span></span>
 <span data-ttu-id="26d6a-122">Пример кода демонстрирует, как создать определяемое пользователем сообщение с идентификатором больше 50 000.</span><span class="sxs-lookup"><span data-stu-id="26d6a-122">The code example demonstrates how to create a user-defined message with an ID greater than 50000.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Create a new message
$udm = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedMessage -ArgumentList `  
$srv, 50030, "us_english", 16, "Test message"  
$udm.Create()  
$msg = $srv.UserDefinedMessages.ItemByIdAndLanguage(50030, "us_english");  
$msg  
```  
