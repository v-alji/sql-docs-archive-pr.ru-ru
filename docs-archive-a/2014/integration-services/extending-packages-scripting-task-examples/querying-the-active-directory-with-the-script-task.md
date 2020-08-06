---
title: Запрос Active Directory в задаче "Скрипт" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], Active Directory access
- SSIS Script task, Active Directory access
- Script task [Integration Services], examples
- Active Directory [Integration Services]
ms.assetid: a88fefbb-9ea2-4a86-b836-e71315bac68e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 624aa56289b9cab9174882b586a37e5d0de7ca9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655879"
---
# <a name="querying-the-active-directory-with-the-script-task"></a><span data-ttu-id="94dcb-102">Запрос Active Directory в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="94dcb-102">Querying the Active Directory with the Script Task</span></span>
  <span data-ttu-id="94dcb-103">Часто задачей корпоративных приложений обработки данных, например, пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], является обработка данных различным образом, в зависимости от категории, названия должности, иных характеристик сотрудников, сведения о которых хранятся в службе каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="94dcb-103">Enterprise data processing applications, such as [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, often need to process data differently based on the rank, job title, or other characteristics of employees stored in Active Directory.</span></span> <span data-ttu-id="94dcb-104">Active Directory — служба каталогов [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, обеспечивающая централизованное хранение метаданных не только о пользователях, но и об используемых ими корпоративных ресурсах, например компьютерах и принтерах.</span><span class="sxs-lookup"><span data-stu-id="94dcb-104">Active Directory is a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows directory service that provides a centralized store of metadata, not only about users, but also about other organizational assets such as computers and printers.</span></span> <span data-ttu-id="94dcb-105">Пространство имен `System.DirectoryServices` платформы Microsoft .NET Framework предоставляет классы для работы со службой каталогов Active Directory, с помощью которых можно управлять рабочим процессом по обработке данных в зависимости от типа данных.</span><span class="sxs-lookup"><span data-stu-id="94dcb-105">The `System.DirectoryServices` namespace in the Microsoft .NET Framework provides classes for working with Active Directory, to help you direct data processing workflow based on the information that it stores.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="94dcb-106">Если нужно создать задачу, которую будет удобно использовать в нескольких пакетах, рекомендуется начать разработку пользовательской задачи с этого образца задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="94dcb-106">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="94dcb-107">Дополнительные сведения см. в разделе [Разработка пользовательской задачи](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="94dcb-107">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="94dcb-108">Description</span><span class="sxs-lookup"><span data-stu-id="94dcb-108">Description</span></span>  
 <span data-ttu-id="94dcb-109">В следующем примере имя сотрудника, название его должности и номер телефона извлекаются из службы каталогов Active Directory в соответствии со значением переменной `email`, которая содержит адрес электронной почты сотрудника.</span><span class="sxs-lookup"><span data-stu-id="94dcb-109">The following example retrieves an employee's name, title, and phone number from Active Directory based on the value of the `email` variable, which contains the e-mail address of the employee.</span></span> <span data-ttu-id="94dcb-110">Элементы управления очередностью в пакете могут использовать извлеченные данные, чтобы определить, например, с каким приоритетом – низким или высоким – следует отправить сообщение электронной почты, в зависимости от должности сотрудника.</span><span class="sxs-lookup"><span data-stu-id="94dcb-110">Precedence constraints in the package can use the retrieved information to determine, for example, whether to send a low-priority e-mail message or a high-priority page, based on the job title of the employee.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="94dcb-111">Настройка этого образца задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="94dcb-111">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="94dcb-112">Создайте три строковые переменные: `email`, `name` и `title`.</span><span class="sxs-lookup"><span data-stu-id="94dcb-112">Create the three string variables `email`, `name`, and `title`.</span></span> <span data-ttu-id="94dcb-113">Введите действительный корпоративный адрес электронной почты в качестве значения переменной `email`.</span><span class="sxs-lookup"><span data-stu-id="94dcb-113">Enter a valid corporate email address as the value of the `email` variable.</span></span>  
  
2.  <span data-ttu-id="94dcb-114">На странице **Скрипт** в **редакторе задачи "Скрипт**" добавьте `email` переменную в `ReadOnlyVariables` свойство.</span><span class="sxs-lookup"><span data-stu-id="94dcb-114">On the **Script** page of the **Script Task Editor**, add the `email` variable to the `ReadOnlyVariables` property.</span></span>  
  
3.  <span data-ttu-id="94dcb-115">Добавьте переменные `name` и `title` в свойство `ReadWriteVariables`.</span><span class="sxs-lookup"><span data-stu-id="94dcb-115">Add the `name` and `title` variables to the `ReadWriteVariables` property.</span></span>  
  
4.  <span data-ttu-id="94dcb-116">В проекте скрипта добавьте ссылку на пространство имен `System.DirectoryServices`.</span><span class="sxs-lookup"><span data-stu-id="94dcb-116">In the script project, add a reference to the `System.DirectoryServices` namespace.</span></span>  
  
5.  <span data-ttu-id="94dcb-117">.</span><span class="sxs-lookup"><span data-stu-id="94dcb-117">.</span></span> <span data-ttu-id="94dcb-118">Используйте инструкцию `Imports`, чтобы импортировать пространство имен `DirectoryServices`.</span><span class="sxs-lookup"><span data-stu-id="94dcb-118">In your code, use an `Imports` statement to import the `DirectoryServices` namespace.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="94dcb-119">Для успешного выполнения этого скрипта необходимо, чтобы в сети организации использовалась служба каталогов Active Directory и в ней хранились сведения, используемые в этом примере.</span><span class="sxs-lookup"><span data-stu-id="94dcb-119">To run this script successfully, your company must be using Active Directory on its network and storing the employee information that this example uses.</span></span>  
  
### <a name="code"></a><span data-ttu-id="94dcb-120">Код</span><span class="sxs-lookup"><span data-stu-id="94dcb-120">Code</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim directory As DirectoryServices.DirectorySearcher  
    Dim result As DirectoryServices.SearchResult  
    Dim email As String  
  
    email = Dts.Variables("email").Value.ToString  
  
    Try  
        directory = New _  
            DirectoryServices.DirectorySearcher("(mail=" & email & ")")  
        result = directory.FindOne  
        Dts.Variables("name").Value = _  
            result.Properties("displayname").ToString  
        Dts.Variables("title").Value = _  
            result.Properties("title").ToString  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        Dts.Events.FireError(0, _  
            "Script Task Example", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
```  
  
```csharp  
public void Main()  
{  
    //  
    DirectorySearcher directory;  
    SearchResult result;  
    string email;  
  
    email = (string)Dts.Variables["email"].Value;  
  
    try  
    {  
        directory = new DirectorySearcher("(mail=" + email + ")");  
        result = directory.FindOne();  
        Dts.Variables["name"].Value = result.Properties["displayname"].ToString();  
        Dts.Variables["title"].Value = result.Properties["title"].ToString();  
        Dts.TaskResult = (int)ScriptResults.Success;  
    }  
    catch (Exception ex)  
    {  
        Dts.Events.FireError(0, "Script Task Example", ex.Message + "\n" + ex.StackTrace, String.Empty, 0);  
        Dts.TaskResult = (int)ScriptResults.Failure;  
    }  
  
}  
```  
  
## <a name="external-resources"></a><span data-ttu-id="94dcb-121">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="94dcb-121">External Resources</span></span>  
  
-   <span data-ttu-id="94dcb-122">Техническая статья [Обработка данных Active Directory в службах SSIS](https://go.microsoft.com/fwlink/?LinkId=199588) на сайте social.technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="94dcb-122">Technical article, [Processing Active Directory Information in SSIS](https://go.microsoft.com/fwlink/?LinkId=199588), on social.technet.microsoft.com</span></span>  
  
<span data-ttu-id="94dcb-123">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="94dcb-123">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="94dcb-124">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="94dcb-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="94dcb-125">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="94dcb-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="94dcb-126">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="94dcb-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
