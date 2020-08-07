---
title: Использование Database Mail | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- e-mail [SMO]
- Database Mail [SMO]
- mail [SMO]
ms.assetid: 7605390f-b485-48cc-8d97-e364a066067b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 86ceec7417638f53427ed5a62101f2fdb6d7440a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732486"
---
# <a name="using-database-mail"></a><span data-ttu-id="86940-102">Использование компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="86940-102">Using Database Mail</span></span>
  <span data-ttu-id="86940-103">В SMO подсистема компонента Database Mail представлена объектом <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail>, на который ссылается свойство <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A>.</span><span class="sxs-lookup"><span data-stu-id="86940-103">In SMO, the Database Mail subsystem is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object that is referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property.</span></span> <span data-ttu-id="86940-104">С помощью объекта SMO <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> можно настраивать подсистему компонента Database Mail и управлять профилями и учетными записями почты.</span><span class="sxs-lookup"><span data-stu-id="86940-104">By using the SMO <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object, you can configure the Database Mail subsystem and manage profiles and mail accounts.</span></span> <span data-ttu-id="86940-105">Объект SMO <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> принадлежит объекту `Server`, и это означает, что область действия учетных записей почты соответствует уровню сервера.</span><span class="sxs-lookup"><span data-stu-id="86940-105">The SMO <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object belongs to the `Server` object, meaning that scope of the mail accounts is at the server level.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="86940-106">Примеры</span><span class="sxs-lookup"><span data-stu-id="86940-106">Examples</span></span>  
 <span data-ttu-id="86940-107">Чтобы использовать какой-либо из представленных примеров кода, нужно выбрать среду, шаблон и язык программирования, с помощью которых будет создаваться приложение.</span><span class="sxs-lookup"><span data-stu-id="86940-107">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="86940-108">Дополнительные сведения см. в статьях [Создание проекта Visual Basic SMO в Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) или [Создание проекта Visual C&#35; SMO в Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="86940-108">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
 <span data-ttu-id="86940-109">Для программ, использующих [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Database Mail, необходимо включить `Imports` инструкцию для определения пространства имен почты.</span><span class="sxs-lookup"><span data-stu-id="86940-109">For programs that use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Database Mail, you must include the `Imports` statement to qualify the Mail namespace.</span></span> <span data-ttu-id="86940-110">Вставьте инструкцию после других инструкций `Imports` и перед любыми декларациями в приложении.</span><span class="sxs-lookup"><span data-stu-id="86940-110">Insert the statement after the other `Imports` statements, before any declarations in the application, such as:</span></span>  
  
 `Imports Microsoft.SqlServer.Management.Smo`  
  
 `Imports Microsoft.SqlServer.Management.Common`  
  
 `Imports Microsoft.SqlServer.Management.Smo.Mail`  
  
## <a name="creating-a-database-mail-account-by-using-visual-basic"></a><span data-ttu-id="86940-111">Создание учетной записи для компонента Database Mail на языке Visual Basic</span><span class="sxs-lookup"><span data-stu-id="86940-111">Creating a Database Mail Account by Using Visual Basic</span></span>  
 <span data-ttu-id="86940-112">В этом примере кода демонстрируется создание учетной записи электронной почты в объектах SMO.</span><span class="sxs-lookup"><span data-stu-id="86940-112">This code example shows how to create an e-mail account in SMO.</span></span> <span data-ttu-id="86940-113">Компонент Database Mail представлен объектом <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail>, и на него ссылается свойство <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> объекта <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="86940-113">Database Mail is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object and referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="86940-114">Объекты SMO можно использовать для программной настройки компонента Database Mail, но не для отправления или обработки полученной почты.</span><span class="sxs-lookup"><span data-stu-id="86940-114">SMO can be used to programmatically configure Database Mail, but it cannot be used to send or handle received e-mail.</span></span>  
  
 <span data-ttu-id="86940-115">VB.NET</span><span class="sxs-lookup"><span data-stu-id="86940-115">VB.NET</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMail1](SMO How to#SMO_VBMail1)]  -->  
  
## <a name="creating-a-database-mail-account-by-using-visual-c"></a><span data-ttu-id="86940-116">Создание учетной записи для компонента Database Mail на языке Visual C#</span><span class="sxs-lookup"><span data-stu-id="86940-116">Creating a Database Mail Account by Using Visual C#</span></span>  
 <span data-ttu-id="86940-117">В этом примере кода демонстрируется создание учетной записи электронной почты в объектах SMO.</span><span class="sxs-lookup"><span data-stu-id="86940-117">This code example shows how to create an e-mail account in SMO.</span></span> <span data-ttu-id="86940-118">Компонент Database Mail представлен объектом <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail>, и на него ссылается свойство <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> объекта <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="86940-118">Database Mail is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object and referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="86940-119">Объекты SMO можно использовать для программной настройки компонента Database Mail, но не для отправления или обработки полученной почты.</span><span class="sxs-lookup"><span data-stu-id="86940-119">SMO can be used to programmatically configure Database Mail, but it cannot be used to send or handle received e-mail.</span></span>  
  
```csharp  
{  
         //Connect to the local, default instance of SQL Server.  
         Server srv = default(Server);   
           srv = new Server();   
           //Define the Database Mail service with a SqlMail object variable   
           //and reference it using the Server Mail property.   
           SqlMail sm;   
           sm = srv.Mail;   
           //Define and create a mail account by supplying the Database Mail  
           //service, name, description, display name, and email address  
           //arguments in the constructor.   
           MailAccount a = default(MailAccount);   
           a = new MailAccount(sm, "AdventureWorks2012 Administrator", "AdventureWorks2012 Automated Mailer", "Mail account for administrative e-mail.", "dba@Adventure-Works.com");   
           a.Create();    
}  
```  
  
## <a name="creating-a-database-mail-account-by-using-powershell"></a><span data-ttu-id="86940-120">Создание учетной записи для компонента Database Mail в PowerShell</span><span class="sxs-lookup"><span data-stu-id="86940-120">Creating a Database Mail Account by Using PowerShell</span></span>  
 <span data-ttu-id="86940-121">В этом примере кода демонстрируется создание учетной записи электронной почты в объектах SMO.</span><span class="sxs-lookup"><span data-stu-id="86940-121">This code example shows how to create an e-mail account in SMO.</span></span> <span data-ttu-id="86940-122">Компонент Database Mail представлен объектом <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail>, и на него ссылается свойство <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> объекта <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="86940-122">Database Mail is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object and referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="86940-123">Объекты SMO можно использовать для программной настройки компонента Database Mail, но не для отправления или обработки полученной почты.</span><span class="sxs-lookup"><span data-stu-id="86940-123">SMO can be used to programmatically configure Database Mail, but it cannot be used to send or handle received e-mail.</span></span>
  
```powershell  
#Connect to the local, default instance of SQL Server.  
  
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Define the Database Mail; reference it using the Server Mail property.  
$sm = $srv.Mail  
  
#Define and create a mail account by supplying the Database Mail service,  
#name, description, display name, and email address arguments in the constructor.  
$a = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Mail.MailAccount -ArgumentList $sm, `  
"Adventure Works Administrator", "Adventure Works Automated Mailer",`  
 "Mail account for administrative e-mail.", "dba@Adventure-Works.com"  
$a.Create()  
```  
