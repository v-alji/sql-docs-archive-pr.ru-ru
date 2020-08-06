---
title: Создание пользовательской задачи | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom tasks [Integration Services], creating
ms.assetid: 42965c09-1782-4cdb-9ce1-216af4c23e0a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f752acad7a442a8e0aad2d24e94938c14195a35d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665439"
---
# <a name="creating-a-custom-task"></a><span data-ttu-id="325e1-102">Создание пользовательской задачи</span><span class="sxs-lookup"><span data-stu-id="325e1-102">Creating a Custom Task</span></span>
  <span data-ttu-id="325e1-103">Шаги, необходимые для создания пользовательской задачи, аналогичны шагам, необходимым для создания любого другого пользовательского объекта служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="325e1-103">The steps involved in creating a custom task are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="325e1-104">Создайте новый класс, наследующий базовый класс.</span><span class="sxs-lookup"><span data-stu-id="325e1-104">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="325e1-105">Для каждой задачи используется базовый класс [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task).</span><span class="sxs-lookup"><span data-stu-id="325e1-105">For a task, the base class is [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task).</span></span>  
  
-   <span data-ttu-id="325e1-106">Примените к классу атрибут, определяющий тип объекта.</span><span class="sxs-lookup"><span data-stu-id="325e1-106">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="325e1-107">Атрибутом для задачи является атрибут <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>.</span><span class="sxs-lookup"><span data-stu-id="325e1-107">For a task, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>.</span></span>  
  
-   <span data-ttu-id="325e1-108">Переопределите реализацию методов и свойств базового класса.</span><span class="sxs-lookup"><span data-stu-id="325e1-108">Override the implementation of the base class's methods and properties.</span></span> <span data-ttu-id="325e1-109">Для задачи это методы <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> и <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="325e1-109">For a task, these include the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> methods.</span></span>  
  
-   <span data-ttu-id="325e1-110">При необходимости разработайте настраиваемый пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="325e1-110">Optionally, develop a custom user interface.</span></span> <span data-ttu-id="325e1-111">Для задачи необходим класс, реализующий интерфейс <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI>.</span><span class="sxs-lookup"><span data-stu-id="325e1-111">For a task, this requires a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface.</span></span>  
  
## <a name="getting-started-with-a-custom-task"></a><span data-ttu-id="325e1-112">Приступая к работе с пользовательской задачей</span><span class="sxs-lookup"><span data-stu-id="325e1-112">Getting Started with a Custom Task</span></span>  
  
### <a name="creating-projects-and-classes"></a><span data-ttu-id="325e1-113">Создание проектов и классов</span><span class="sxs-lookup"><span data-stu-id="325e1-113">Creating Projects and Classes</span></span>  
 <span data-ttu-id="325e1-114">Поскольку все управляемые задачи являются наследниками базового класса [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task), первым шагом при создании пользовательской задачи является создание проекта библиотеки классов на управляемом языке программирования по выбору и класса, который наследует от этого базового класса.</span><span class="sxs-lookup"><span data-stu-id="325e1-114">Because all managed tasks derive from the [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class, the first step when you create a custom task is to create a class library project in your preferred managed programming language and create a class that inherits from the base class.</span></span> <span data-ttu-id="325e1-115">В этом производном классе будут переопределены методы и свойства базового класса, реализующие пользовательские функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="325e1-115">In this derived class you will override the methods and properties of the base class to implement your custom functionality.</span></span>  
  
 <span data-ttu-id="325e1-116">Создайте в том же решении второй проект библиотеки классов для собственного пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="325e1-116">In the same solution, create a second class library project for the custom user interface.</span></span> <span data-ttu-id="325e1-117">Для простоты развертывания рекомендуется создать для пользовательского интерфейса отдельную сборку, поскольку это позволит обновлять и повторно развертывать диспетчер соединений и пользовательский интерфейс независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="325e1-117">A separate assembly for the user interface is recommended for ease of deployment because it allows you to update and redeploy the connection manager or its user interface independently.</span></span>  
  
 <span data-ttu-id="325e1-118">Настройте в обоих проектах подписывание сборок, которые будут создаваться во время построения, с помощью файла ключа для строгого имени.</span><span class="sxs-lookup"><span data-stu-id="325e1-118">Configure both projects to sign the assemblies that will be generated at build time by using a strong name key file.</span></span>  
  
### <a name="applying-the-dtstask-attribute"></a><span data-ttu-id="325e1-119">Применение атрибута DtsTask</span><span class="sxs-lookup"><span data-stu-id="325e1-119">Applying the DtsTask Attribute</span></span>  
 <span data-ttu-id="325e1-120">Примените атрибут <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> к созданному классу для идентификации его в качестве задачи.</span><span class="sxs-lookup"><span data-stu-id="325e1-120">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute to the class that you have created to identify it as a task.</span></span> <span data-ttu-id="325e1-121">Этот атрибут предоставляет информацию времени разработки, такую как имя, описание и тип задачи.</span><span class="sxs-lookup"><span data-stu-id="325e1-121">This attribute provides design-time information such as the name, description, and task type of the task.</span></span>  
  
 <span data-ttu-id="325e1-122">Используйте свойство <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> для связывания задачи с пользовательским интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="325e1-122">Use the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> property to link the task to its custom user interface.</span></span> <span data-ttu-id="325e1-123">Чтобы получить токен открытого ключа, необходимый для этого свойства, можно использовать команду **sn.exe -t**, отображающую токен открытого ключа из SNK-файла пары ключей, который предназначен для подписывания сборки пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="325e1-123">To obtain the public key token that is required for this property, you an use **sn.exe -t** to display the public key token from the key pair (.snk) file that you intend to use to sign the user interface assembly.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
namespace Microsoft.SSIS.Samples  
{  
  [DtsTask  
  (  
   DisplayName = "MyTask",  
   IconResource = "MyTask.MyTaskIcon.ico",  
   UITypeName = "My Custom Task," +  
   "Version=1.0.0.0," +  
   "Culture = Neutral," +  
   "PublicKeyToken = 12345abc6789de01",  
   TaskType = "PackageMaintenance",  
   TaskContact = "MyTask; company name; any other information",  
   RequiredProductLevel = DTSProductLevel.None  
   )]  
  public class MyTask : Task  
  {  
    // Your code here.  
  }  
}  
```  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
  
<DtsTask(DisplayName:="MyTask", _  
 IconResource:="MyTask.MyTaskIcon.ico", _  
 UITypeName:="My Custom Task," & _  
 "Version=1.0.0.0,Culture=Neutral," & _  
 "PublicKeyToken=12345abc6789de01", _  
 TaskType:="PackageMaintenance", _  
 TaskContact:="MyTask; company name; any other information", _  
 RequiredProductLevel:=DTSProductLevel.None)> _  
Public Class MyTask  
  Inherits Task  
  
  ' Your code here.  
  
End Class 'MyTask  
```  
  
## <a name="building-deploying-and-debugging-a-custom-task"></a><span data-ttu-id="325e1-124">Построение, развертывание и отладка пользовательской задачи</span><span class="sxs-lookup"><span data-stu-id="325e1-124">Building, Deploying, and Debugging a Custom Task</span></span>  
 <span data-ttu-id="325e1-125">Шаги по построению, развертыванию и отладке пользовательской задачи в службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] аналогичны шагам, необходимым для других типов пользовательских объектов.</span><span class="sxs-lookup"><span data-stu-id="325e1-125">The steps for building, deploying, and debugging a custom task in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are similar to the steps required for other types of custom objects.</span></span> <span data-ttu-id="325e1-126">Дополнительные сведения см. в разделе [Сборка, развертывание и отладка пользовательских объектов](../building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="325e1-126">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>  
  
<span data-ttu-id="325e1-127">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="325e1-127">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="325e1-128">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="325e1-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="325e1-129">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="325e1-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="325e1-130">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="325e1-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="325e1-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="325e1-131">See Also</span></span>  
 <span data-ttu-id="325e1-132">[Создание пользовательской задачи](creating-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="325e1-132">[Creating a Custom Task](creating-a-custom-task.md) </span></span>  
 <span data-ttu-id="325e1-133">[Создание кода пользовательской задачи](coding-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="325e1-133">[Coding a Custom Task](coding-a-custom-task.md) </span></span>  
 [<span data-ttu-id="325e1-134">Разработка пользовательского интерфейса для пользовательской задачи</span><span class="sxs-lookup"><span data-stu-id="325e1-134">Developing a User Interface for a Custom Task</span></span>](developing-a-user-interface-for-a-custom-task.md)  
  
  
