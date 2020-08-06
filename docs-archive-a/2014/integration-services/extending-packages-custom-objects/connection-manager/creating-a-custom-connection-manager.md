---
title: Создание пользовательского диспетчера подключений | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom connection managers [Integration Services], creating
ms.assetid: e83f8e02-ace4-42e0-b979-2f6be1460985
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 857efebbe311e5510e15cae9e78a2b424559ded7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751312"
---
# <a name="creating-a-custom-connection-manager"></a><span data-ttu-id="44c73-102">Создание пользовательского диспетчера соединений</span><span class="sxs-lookup"><span data-stu-id="44c73-102">Creating a Custom Connection Manager</span></span>
  <span data-ttu-id="44c73-103">Создание пользовательского диспетчера соединений осуществляется за несколько шагов, аналогично созданию любого другого пользовательского объекта служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="44c73-103">The steps that you must follow to create a custom connection manager are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="44c73-104">Создайте новый класс, наследующий базовый класс.</span><span class="sxs-lookup"><span data-stu-id="44c73-104">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="44c73-105">Для диспетчера соединений базовым классом является <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>.</span><span class="sxs-lookup"><span data-stu-id="44c73-105">For a connection manager, the base class is <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>.</span></span>  
  
-   <span data-ttu-id="44c73-106">Примените к классу атрибут, определяющий тип объекта.</span><span class="sxs-lookup"><span data-stu-id="44c73-106">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="44c73-107">Для диспетчера соединений используется атрибут <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="44c73-107">For a connection manager, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>.</span></span>  
  
-   <span data-ttu-id="44c73-108">Переопределите реализацию методов и свойств базового класса.</span><span class="sxs-lookup"><span data-stu-id="44c73-108">Override the implementation of the methods and properties of the base class.</span></span> <span data-ttu-id="44c73-109">Для диспетчера соединений это свойство <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A>, методы <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> и <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A>.</span><span class="sxs-lookup"><span data-stu-id="44c73-109">For a connection manager, these include the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> methods.</span></span>  
  
-   <span data-ttu-id="44c73-110">При необходимости разработайте настраиваемый пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="44c73-110">Optionally, develop a custom user interface.</span></span> <span data-ttu-id="44c73-111">В случае с диспетчером соединений для этого необходимо использовать класс, реализующий интерфейс <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI>.</span><span class="sxs-lookup"><span data-stu-id="44c73-111">For a connection manager, this requires a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI> interface.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="44c73-112">Большая часть задач, источников и назначений в службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] работает только с определенными типами встроенных диспетчеров соединений.</span><span class="sxs-lookup"><span data-stu-id="44c73-112">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="44c73-113">Поэтому данные образцы нельзя протестировать с помощью встроенных задач и компонентов.</span><span class="sxs-lookup"><span data-stu-id="44c73-113">Therefore, these samples cannot be tested with the built-in tasks and components.</span></span>  
  
## <a name="getting-started-with-a-custom-connection-manager"></a><span data-ttu-id="44c73-114">Приступая к работе над пользовательским диспетчером соединений</span><span class="sxs-lookup"><span data-stu-id="44c73-114">Getting Started with a Custom Connection Manager</span></span>  
  
### <a name="creating-projects-and-classes"></a><span data-ttu-id="44c73-115">Создание проектов и классов</span><span class="sxs-lookup"><span data-stu-id="44c73-115">Creating Projects and Classes</span></span>  
 <span data-ttu-id="44c73-116">Так как все управляемые диспетчеры соединений являются производными от базового класса <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>, на первом шаге создания пользовательского диспетчера соединений необходимо создать проект библиотеки классов на предпочитаемом языке программирования управляемого кода, а затем создать класс, наследующий от базового класса.</span><span class="sxs-lookup"><span data-stu-id="44c73-116">Because all managed connection managers derive from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> base class, the first step when you create a custom connection manager is to create a class library project in your preferred managed programming language and create a class that inherits from the base class.</span></span> <span data-ttu-id="44c73-117">В этом производном классе будут переопределены методы и свойства базового класса, чтобы реализовать пользовательские функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="44c73-117">In this derived class, you will override the methods and properties of the base class to implement your custom functionality.</span></span>  
  
 <span data-ttu-id="44c73-118">Создайте в том же решении второй проект библиотеки классов для собственного пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="44c73-118">In the same solution, create a second class library project for the custom user interface.</span></span> <span data-ttu-id="44c73-119">Для пользовательского интерфейса рекомендуется использовать отдельную сборку, что позволяет обновлять и заново развертывать диспетчер соединений или его пользовательский интерфейс независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="44c73-119">A separate assembly for the user interface is recommended for ease of deployment because it lets you update and redeploy the connection manager or its user interface independently.</span></span>  
  
 <span data-ttu-id="44c73-120">Настройте в обоих проектах подписывание сборок, которые будут создаваться во время построения, с помощью файла ключа для строгого имени.</span><span class="sxs-lookup"><span data-stu-id="44c73-120">Configure both projects to sign the assemblies that will be generated at build time by using a strong name key file.</span></span>  
  
### <a name="applying-the-dtsconnection-attribute"></a><span data-ttu-id="44c73-121">Применение атрибута DtsConnection</span><span class="sxs-lookup"><span data-stu-id="44c73-121">Applying the DtsConnection Attribute</span></span>  
 <span data-ttu-id="44c73-122">Примените к созданному классу атрибут <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>, чтобы определить его в качестве диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="44c73-122">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> attribute to the class that you have created to identify it as a connection manager.</span></span> <span data-ttu-id="44c73-123">Этот атрибут содержит сведения для времени разработки, например, имя, описание и тип соединения диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="44c73-123">This attribute provides design-time information such as the name, description, and connection type of the connection manager.</span></span> <span data-ttu-id="44c73-124"><xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.ConnectionType%2A>Свойства и `Description` соответствуют **типу** и `Description` столбцам, отображаемым в диалоговом окне **Добавление диспетчера соединений со службами SSIS** , которое отображается при настройке соединений для пакета в [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="44c73-124">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.ConnectionType%2A> and `Description` properties correspond to the **Type** and `Description` columns displayed in the **Add SSIS Connection Manager** dialog box, which is displayed when configuring connections for a package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="44c73-125">Используйте свойство <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.UITypeName%2A>, чтобы связать диспетчер соединений с его пользовательским интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="44c73-125">Use the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.UITypeName%2A> property to link the connection manager to its custom user interface.</span></span> <span data-ttu-id="44c73-126">Чтобы получить токен открытого ключа, необходимый для этого свойства, можно использовать команду **sn.exe -t**, отображающую токен открытого ключа из SNK-файла пары ключей, который предназначен для подписывания сборки пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="44c73-126">To obtain the public key token that is required for this property, you an use **sn.exe -t** to display the public key token from the key pair (.snk) file that you intend to use to sign the user interface assembly.</span></span>  
  
```vb  
<DtsConnection(ConnectionType:="SQLVB", _  
  DisplayName:="SqlConnectionManager (VB)", _  
  Description:="Connection manager for Sql Server", _  
  UITypeName:="SqlConnMgrUIVB.SqlConnMgrUIVB,SqlConnMgrUIVB,Version=1.0.0.0,Culture=neutral,PublicKeyToken=<insert public key token here>")> _  
Public Class SqlConnMgrVB  
  Inherits ConnectionManagerBase  
  . . .  
End Class  
```  
  
```csharp  
[DtsConnection(ConnectionType = "SQLCS",  
  DisplayName = "SqlConnectionManager (CS)",  
  Description = "Connection manager for Sql Server",  
  UITypeName = "SqlConnMgrUICS.SqlConnMgrUICS,SqlConnMgrUICS,Version=1.0.0.0,Culture=neutral,PublicKeyToken=<insert public key token here>")]  
public class SqlConnMgrCS :  
ConnectionManagerBase  
{  
  . . .  
}  
```  
  
## <a name="building-deploying-and-debugging-a-custom-connection-manager"></a><span data-ttu-id="44c73-127">Построение, развертывание и отладка пользовательского диспетчера соединений</span><span class="sxs-lookup"><span data-stu-id="44c73-127">Building, Deploying, and Debugging a Custom Connection Manager</span></span>  
 <span data-ttu-id="44c73-128">Построение, развертывание и отладка пользовательского диспетчера соединений в службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] осуществляется в несколько шагов, аналогичных используемым при работе с другими типами пользовательских объектов.</span><span class="sxs-lookup"><span data-stu-id="44c73-128">The steps for building, deploying, and debugging a custom connection manager in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are similar to the steps for other types of custom objects.</span></span> <span data-ttu-id="44c73-129">Дополнительные сведения см. в разделе [Сборка, развертывание и отладка пользовательских объектов](../building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="44c73-129">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>  
  
<span data-ttu-id="44c73-130">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="44c73-130">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="44c73-131">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="44c73-131">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="44c73-132">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="44c73-132">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="44c73-133">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="44c73-133">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44c73-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="44c73-134">See Also</span></span>  
 <span data-ttu-id="44c73-135">[Написание кода пользовательского диспетчера соединений](coding-a-custom-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="44c73-135">[Coding a Custom Connection Manager](coding-a-custom-connection-manager.md) </span></span>  
 [<span data-ttu-id="44c73-136">Разработка пользовательского интерфейса для пользовательского диспетчера соединений</span><span class="sxs-lookup"><span data-stu-id="44c73-136">Developing a User Interface for a Custom Connection Manager</span></span>](developing-a-user-interface-for-a-custom-connection-manager.md)  
  
  
