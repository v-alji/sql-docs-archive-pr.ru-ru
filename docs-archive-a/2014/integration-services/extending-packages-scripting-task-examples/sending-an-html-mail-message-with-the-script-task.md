---
title: Отправка почтового сообщения в формате HTML с помощью задачи "Скрипт" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Send Mail task [Integration Services]
- Script task [Integration Services], examples
- Script task [Integration Services], HTML mail message
ms.assetid: dd2b1eef-b04f-4946-87ab-7bc56bb525ce
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6c1a967b52a84e1ff9c2e54c48e40f4d149b2dbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728501"
---
# <a name="sending-an-html-mail-message-with-the-script-task"></a><span data-ttu-id="218f9-102">Отправка почтового сообщения в формате HTML с помощью задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="218f9-102">Sending an HTML Mail Message with the Script Task</span></span>
  <span data-ttu-id="218f9-103">Задача «Отправка почты» служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] поддерживает только почтовые сообщения в текстовом формате.</span><span class="sxs-lookup"><span data-stu-id="218f9-103">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] SendMail task only supports mail messages in plain text format.</span></span> <span data-ttu-id="218f9-104">Однако отправлять почтовые сообщения в формате HTML можно с помощью задачи «Скрипт» и почтовых функций платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="218f9-104">However you can easily send HTML mail messages by using the Script task and the mail capabilities of the .NET Framework.</span></span>

> [!NOTE]
>  <span data-ttu-id="218f9-105">Если нужно создать задачу, которую будет удобно использовать в нескольких пакетах, рекомендуется начать разработку пользовательской задачи с этого образца задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="218f9-105">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="218f9-106">Дополнительные сведения см. в разделе [Разработка пользовательской задачи](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="218f9-106">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>

## <a name="description"></a><span data-ttu-id="218f9-107">Description</span><span class="sxs-lookup"><span data-stu-id="218f9-107">Description</span></span>
 <span data-ttu-id="218f9-108">В следующем примере пространство имен `System.Net.Mail` используется для настройки и передачи почтового сообщения в формате HTML.</span><span class="sxs-lookup"><span data-stu-id="218f9-108">The following example uses the `System.Net.Mail` namespace to configure and send an HTML mail message.</span></span> <span data-ttu-id="218f9-109">Скрипт извлекает значения полей «Кому», «От кого», «Тема» и текст сообщения электронной почты из переменных пакета, использует их для создания нового сообщения `MailMessag`e и присваивает его свойству `IsBodyHtml` значение `True`.</span><span class="sxs-lookup"><span data-stu-id="218f9-109">The script obtains the To, From, Subject, and body of the e-mail from package variables, uses them to create a new `MailMessag`e, and sets its `IsBodyHtml` property to `True`.</span></span> <span data-ttu-id="218f9-110">Затем сценарий получает имя SMTP-сервера из другой переменной пакета, инициализирует экземпляр клиента `System.Net.Mail.SmtpClient` и вызывает его метод `Send`, чтобы отправить сообщение в формате HTML.</span><span class="sxs-lookup"><span data-stu-id="218f9-110">Then it obtains the SMTP server name from another package variable, initializes an instance of `System.Net.Mail.SmtpClient`, and calls its `Send` method to send the HTML message.</span></span> <span data-ttu-id="218f9-111">В образце функциональность отправки сообщений инкапсулируется в подпрограмме, которая может быть использована повторно в других скриптах.</span><span class="sxs-lookup"><span data-stu-id="218f9-111">The sample encapsulates the message sending functionality in a subroutine that could be reused in other scripts.</span></span>

#### <a name="to-configure-this-script-task-example-without-an-smtp-connection-manager"></a><span data-ttu-id="218f9-112">Настройка этого примера задачи «Скрипт» без диспетчера соединений SMTP</span><span class="sxs-lookup"><span data-stu-id="218f9-112">To configure this Script Task example without an SMTP Connection Manager</span></span>

1.  <span data-ttu-id="218f9-113">Создайте строковые переменные с именами `HtmlEmailTo`, `HtmlEmailFrom` и `HtmlEmailSubject`, затем присвойте им соответствующие значения, чтобы получить допустимое тестовое сообщение.</span><span class="sxs-lookup"><span data-stu-id="218f9-113">Create string variables named `HtmlEmailTo`, `HtmlEmailFrom`, and `HtmlEmailSubject` and assign appropriate values to them for a valid test message.</span></span>

2.  <span data-ttu-id="218f9-114">Создайте строковую переменную с именем `HtmlEmailBody` и присвойте ей в качестве значения строку с разметкой HTML.</span><span class="sxs-lookup"><span data-stu-id="218f9-114">Create a string variable named `HtmlEmailBody` and assign a string of HTML markup to it.</span></span> <span data-ttu-id="218f9-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="218f9-115">For example:</span></span>

    ```
    <html><body><h1>Testing</h1><p>This is a <b>test</b> message.</p></body></html>
    ```

3.  <span data-ttu-id="218f9-116">Создайте строковую переменную с именем `HtmlEmailServer` и присвойте ей в качестве значения имя доступного SMTP-сервера, принимающего анонимные исходящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="218f9-116">Create a string variable named `HtmlEmailServer` and assign the name of an available SMTP server that accepts anonymous outgoing messages.</span></span>

4.  <span data-ttu-id="218f9-117">Присвойте эти пять переменных свойству **ReadOnlyVariables** новой задачи "Скрипт".</span><span class="sxs-lookup"><span data-stu-id="218f9-117">Assign all five of these variables to the **ReadOnlyVariables** property of a new Script task.</span></span>

5.  <span data-ttu-id="218f9-118">Импортируйте пространства имен `System.Net` и `System.Net.Mail` в свой код.</span><span class="sxs-lookup"><span data-stu-id="218f9-118">Import the `System.Net` and `System.Net.Mail` namespaces into your code.</span></span>

 <span data-ttu-id="218f9-119">В образце кода в этом разделе имя SMTP-сервера извлекается из переменной пакета.</span><span class="sxs-lookup"><span data-stu-id="218f9-119">The sample code in this topic obtains the SMTP server name from a package variable.</span></span> <span data-ttu-id="218f9-120">Однако можно также воспользоваться возможностью диспетчера соединений SMTP по инкапсуляции данных соединения и извлечению имени сервера из диспетчера соединений в пользовательском коде.</span><span class="sxs-lookup"><span data-stu-id="218f9-120">However, you could also take advantage of an SMTP connection manager to encapsulate the connection information, and extract the server name from the connection manager in your code.</span></span> <span data-ttu-id="218f9-121">Метод <xref:Microsoft.SqlServer.Dts.ManagedConnections.SMTPConn.AcquireConnection%2A> диспетчера соединений SMTP возвращает строку в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="218f9-121">The <xref:Microsoft.SqlServer.Dts.ManagedConnections.SMTPConn.AcquireConnection%2A> method of the SMTP connection manager returns a string in the following format:</span></span>

 `SmtpServer=smtphost;UseWindowsAuthentication=False;EnableSsl=False;`

 <span data-ttu-id="218f9-122">Можно использовать метод `String.Split`, чтобы разделить этот список аргументов на фрагменты отдельных строк по каждой точке с запятой (;) или знаку равенства (=), а затем извлечь второй аргумент (subscript 1) из фрагмента как имя сервера.</span><span class="sxs-lookup"><span data-stu-id="218f9-122">You can use the `String.Split` method to separate this argument list into an array of individual strings at each semicolon (;) or equal sign (=), and then extract the second argument (subscript 1) from the array as the server name.</span></span>

#### <a name="to-configure-this-script-task-example-with-an-smtp-connection-manager"></a><span data-ttu-id="218f9-123">Настройка этого примера задачи «Скрипт» с диспетчером соединений SMTP</span><span class="sxs-lookup"><span data-stu-id="218f9-123">To configure this Script Task example with an SMTP Connection Manager</span></span>

1.  <span data-ttu-id="218f9-124">Измените задачу "Скрипт", настроенную выше, удалив переменную `HtmlEmailServer` из списка **ReadOnlyVariables**.</span><span class="sxs-lookup"><span data-stu-id="218f9-124">Modify the Script task configured earlier by removing the `HtmlEmailServer` variable from the list of **ReadOnlyVariables**.</span></span>

2.  <span data-ttu-id="218f9-125">Замените строку кода, извлекающую имя сервера:</span><span class="sxs-lookup"><span data-stu-id="218f9-125">Replace the line of code that obtains the server name:</span></span>

    ```
    Dim smtpServer As String = _
      Dts.Variables("HtmlEmailServer").Value.ToString
    ```

     <span data-ttu-id="218f9-126">следующими строками:</span><span class="sxs-lookup"><span data-stu-id="218f9-126">with the following lines:</span></span>

    ```
    Dim smtpConnectionString As String = _
      DirectCast(Dts.Connections("SMTP Connection Manager").AcquireConnection(Dts.Transaction), String)
    Dim smtpServer As String = _
      smtpConnectionString.Split(New Char() {"="c, ";"c})(1)
    ```

## <a name="code"></a><span data-ttu-id="218f9-127">Код</span><span class="sxs-lookup"><span data-stu-id="218f9-127">Code</span></span>

```vb
Public Sub Main()

  Dim htmlMessageTo As String = _
    Dts.Variables("HtmlEmailTo").Value.ToString
  Dim htmlMessageFrom As String = _
    Dts.Variables("HtmlEmailFrom").Value.ToString
  Dim htmlMessageSubject As String = _
    Dts.Variables("HtmlEmailSubject").Value.ToString
  Dim htmlMessageBody As String = _
    Dts.Variables("HtmlEmailBody").Value.ToString
  Dim smtpServer As String = _
    Dts.Variables("HtmlEmailServer").Value.ToString

  SendMailMessage( _
      htmlMessageTo, htmlMessageFrom, _
      htmlMessageSubject, htmlMessageBody, _
      True, smtpServer)

  Dts.TaskResult = ScriptResults.Success

End Sub

Private Sub SendMailMessage( _
    ByVal SendTo As String, ByVal From As String, _
    ByVal Subject As String, ByVal Body As String, _
    ByVal IsBodyHtml As Boolean, ByVal Server As String)

  Dim htmlMessage As MailMessage
  Dim mySmtpClient As SmtpClient

  htmlMessage = New MailMessage( _
    SendTo, From, Subject, Body)
  htmlMessage.IsBodyHtml = IsBodyHtml

  mySmtpClient = New SmtpClient(Server)
  mySmtpClient.Credentials = CredentialCache.DefaultNetworkCredentials
  mySmtpClient.Send(htmlMessage)

End Sub
```

```csharp
public void Main()
        {

            string htmlMessageTo = Dts.Variables["HtmlEmailTo"].Value.ToString();
            string htmlMessageFrom = Dts.Variables["HtmlEmailFrom"].Value.ToString();
            string htmlMessageSubject = Dts.Variables["HtmlEmailSubject"].Value.ToString();
            string htmlMessageBody = Dts.Variables["HtmlEmailBody"].Value.ToString();
            string smtpServer = Dts.Variables["HtmlEmailServer"].Value.ToString();

            SendMailMessage(htmlMessageTo, htmlMessageFrom, htmlMessageSubject, htmlMessageBody, true, smtpServer);

            Dts.TaskResult = (int)ScriptResults.Success;

        }

        private void SendMailMessage(string SendTo, string From, string Subject, string Body, bool IsBodyHtml, string Server)
        {

            MailMessage htmlMessage;
            SmtpClient mySmtpClient;

            htmlMessage = new MailMessage(SendTo, From, Subject, Body);
            htmlMessage.IsBodyHtml = IsBodyHtml;

            mySmtpClient = new SmtpClient(Server);
            mySmtpClient.Credentials = CredentialCache.DefaultNetworkCredentials;
            mySmtpClient.Send(htmlMessage);

        }
```

<span data-ttu-id="218f9-128">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="218f9-128">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="218f9-129">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="218f9-129">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="218f9-130">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="218f9-130">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="218f9-131">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="218f9-131">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="218f9-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="218f9-132">See Also</span></span>
 [<span data-ttu-id="218f9-133">Задача «Отправка почты»</span><span class="sxs-lookup"><span data-stu-id="218f9-133">Send Mail Task</span></span>](../control-flow/send-mail-task.md)


