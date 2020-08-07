---
title: Создание пользовательского регистратора | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom log providers [Integration Services], creating
ms.assetid: fc20af96-9eb8-4195-8d3f-8a4d7c753f24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c1efb736aece2cc8d118c81326989559f0d17a60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732741"
---
# <a name="creating-a-custom-log-provider"></a><span data-ttu-id="acca6-102">Создание пользовательского регистратора</span><span class="sxs-lookup"><span data-stu-id="acca6-102">Creating a Custom Log Provider</span></span>
  <span data-ttu-id="acca6-103">Среда времени выполнения служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] располагает обширными возможностями по ведению журналов.</span><span class="sxs-lookup"><span data-stu-id="acca6-103">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] run-time environment has extensive logging capabilities.</span></span> <span data-ttu-id="acca6-104">С помощью журнала можно отслеживать события, происходящие во время выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="acca6-104">A log lets you capture events that occur during package execution.</span></span> <span data-ttu-id="acca6-105">Службы [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] включают целый ряд регистраторов, используя которые можно создавать и сохранять журналы в различных форматах, например в XML, текстовом файле, базе данных или в журнале событий Windows.</span><span class="sxs-lookup"><span data-stu-id="acca6-105">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes a variety of log providers that enable logs to be created and stored in multiple formats, such as XML, text, database, or in the Windows event log.</span></span> <span data-ttu-id="acca6-106">Если ни один из этих регистраторов или предлагаемых ими выходных форматов не соответствует потребностям пользователя, можно создать пользовательский регистратор.</span><span class="sxs-lookup"><span data-stu-id="acca6-106">If one of these providers or output formats does not fit your needs, you can create a custom log provider.</span></span>

 <span data-ttu-id="acca6-107">Создание пользовательского регистратора, как и любого другого пользовательского объекта для служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], осуществляется в несколько шагов, а именно:</span><span class="sxs-lookup"><span data-stu-id="acca6-107">The steps involved in creating a custom log provider are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>

-   <span data-ttu-id="acca6-108">Создайте новый класс, наследующий базовый класс.</span><span class="sxs-lookup"><span data-stu-id="acca6-108">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="acca6-109">Для регистратора базовым классом является <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase>.</span><span class="sxs-lookup"><span data-stu-id="acca6-109">For a log provider, the base class is <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase>.</span></span>

-   <span data-ttu-id="acca6-110">Примените к классу атрибут, определяющий тип объекта.</span><span class="sxs-lookup"><span data-stu-id="acca6-110">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="acca6-111">Для регистратора используется атрибут <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute>.</span><span class="sxs-lookup"><span data-stu-id="acca6-111">For a log provider, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute>.</span></span>

-   <span data-ttu-id="acca6-112">Переопределите реализацию методов и свойств базового класса.</span><span class="sxs-lookup"><span data-stu-id="acca6-112">Override the implementation of the base class's methods and properties.</span></span> <span data-ttu-id="acca6-113">Для регистратора это свойство <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>, методы <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> и <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A>.</span><span class="sxs-lookup"><span data-stu-id="acca6-113">For a log provider, these include the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> methods.</span></span>

-   <span data-ttu-id="acca6-114">Настраиваемые пользовательские интерфейсы для пользовательских регистраторов в службах [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] не реализуются.</span><span class="sxs-lookup"><span data-stu-id="acca6-114">Custom user interfaces for custom log providers are not implemented in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>

## <a name="getting-started-with-a-custom-log-provider"></a><span data-ttu-id="acca6-115">Приступая к работе над пользовательским регистратором</span><span class="sxs-lookup"><span data-stu-id="acca6-115">Getting Started with a Custom Log Provider</span></span>

### <a name="creating-projects-and-classes"></a><span data-ttu-id="acca6-116">Создание проектов и классов</span><span class="sxs-lookup"><span data-stu-id="acca6-116">Creating Projects and Classes</span></span>
 <span data-ttu-id="acca6-117">Так как все управляемые регистраторы являются производными от базового класса <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase>, на первом шаге создания пользовательского регистратора необходимо создать проект библиотеки классов на предпочитаемом языке программирования управляемого кода, а затем создать класс, наследующий от базового класса.</span><span class="sxs-lookup"><span data-stu-id="acca6-117">Because all managed log providers derive from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase> base class, the first step when you create a custom log provider is to create a class library project in your preferred managed programming language, and then create a class that inherits from the base class.</span></span> <span data-ttu-id="acca6-118">В этом производном классе будут переопределены методы и свойства базового класса, реализующие пользовательские функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="acca6-118">In this derived class you will override the methods and properties of the base class to implement your custom functionality.</span></span>

 <span data-ttu-id="acca6-119">Настройте проект таким образом, чтобы создаваемая сборка подписывалась с использованием файла ключа для строгого имени.</span><span class="sxs-lookup"><span data-stu-id="acca6-119">Configure the project to sign the assembly that will be generated with a strong name key file.</span></span>

> [!NOTE]
>  <span data-ttu-id="acca6-120">Многие регистраторы служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] имеют собственный пользовательский интерфейс, в котором реализован интерфейс <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsLogProviderUI>, а вместо содержимого текстового поля **Конфигурация** в диалоговом окне **Настройка журналов служб SSIS** используется фильтруемый раскрывающийся список доступных диспетчеров соединений.</span><span class="sxs-lookup"><span data-stu-id="acca6-120">Many [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] log providers have a custom user interface that implements <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsLogProviderUI> and replaces the **Configuration** text box in the **Configure SSIS Logs** dialog box with a filtered dropdown list of available connection managers.</span></span> <span data-ttu-id="acca6-121">Однако пользовательские интерфейсы для пользовательских регистраторов не реализуются в службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acca6-121">However custom user interfaces for custom log providers are not implemented in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>

### <a name="applying-the-dtslogprovider-attribute"></a><span data-ttu-id="acca6-122">Применение атрибута DtsLogProvider</span><span class="sxs-lookup"><span data-stu-id="acca6-122">Applying the DtsLogProvider Attribute</span></span>
 <span data-ttu-id="acca6-123">Примените к созданному классу атрибут <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute>, чтобы определить его в качестве регистратора.</span><span class="sxs-lookup"><span data-stu-id="acca6-123">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> attribute to the class that you have created to identify it as a log provider.</span></span> <span data-ttu-id="acca6-124">Этот атрибут содержит сведения для времени разработки, например, имя и описание регистратора.</span><span class="sxs-lookup"><span data-stu-id="acca6-124">This attribute provides design-time information such as the name and description of the log provider.</span></span> <span data-ttu-id="acca6-125">`DisplayName`Свойства и `Description` атрибута соответствуют **имени** и `Description` столбцам, отображаемым в редакторе " **Настройка журналов служб SSIS** ", который отображается при настройке ведения журнала для пакета в [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="acca6-125">The `DisplayName` and `Description` properties of the attribute correspond to the **Name** and `Description` columns displayed in the **Configure SSIS Logs** editor, which is displayed when configuring logging for a package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="acca6-126">Свойство <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute.LogProviderType%2A> атрибута не используется.</span><span class="sxs-lookup"><span data-stu-id="acca6-126">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute.LogProviderType%2A> property of the attribute is not used.</span></span> <span data-ttu-id="acca6-127">Однако необходимо ввести значение для него, в противном случае пользовательский регистратор не будет отображаться в списке доступных регистраторов.</span><span class="sxs-lookup"><span data-stu-id="acca6-127">However, you must enter a value for it, or the custom log provider will not appear in the list of available log providers.</span></span>

> [!NOTE]
>  <span data-ttu-id="acca6-128">Поскольку пользовательские интерфейсы для пользовательских регистраторов не реализуются в службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], указание значения для свойства <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute.UITypeName%2A> атрибута <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> не имеет никакого эффекта.</span><span class="sxs-lookup"><span data-stu-id="acca6-128">Since custom user interfaces for custom log providers are not implemented in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], specifying a value for the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute.UITypeName%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> has no effect.</span></span>

```vb
<DtsLogProvider(DisplayName:="MyLogProvider", Description:="A simple log provider.", LogProviderType:="Custom")> _
Public Class MyLogProvider
     Inherits LogProviderBase
    ' TODO: Override the base class methods.
End Class
```

```csharp
[DtsLogProvider(DisplayName="MyLogProvider", Description="A simple log provider.", LogProviderType="Custom")]
public class MyLogProvider : LogProviderBase
{
    // TODO: Override the base class methods.
}
```

## <a name="building-deploying-and-debugging-a-custom-log-provider"></a><span data-ttu-id="acca6-129">Построение, развертывание и отладка пользовательского регистратора</span><span class="sxs-lookup"><span data-stu-id="acca6-129">Building, Deploying, and Debugging a Custom Log Provider</span></span>
 <span data-ttu-id="acca6-130">Построение, развертывание и отладка пользовательского регистратора в службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] осуществляется за несколько шагов, аналогичных используемым при работе с другими типами пользовательских объектов.</span><span class="sxs-lookup"><span data-stu-id="acca6-130">The steps for building, deploying, and debugging a custom log provider in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are very similar to the steps required for other types of custom objects.</span></span> <span data-ttu-id="acca6-131">Дополнительные сведения см. в разделе [Сборка, развертывание и отладка пользовательских объектов](../building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="acca6-131">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>

<span data-ttu-id="acca6-132">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="acca6-132">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="acca6-133">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="acca6-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="acca6-134">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="acca6-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="acca6-135">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="acca6-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="acca6-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="acca6-136">See Also</span></span>
 <span data-ttu-id="acca6-137">[Программирование пользовательского](coding-a-custom-log-provider.md) регистратора [Разработка пользовательского интерфейса для пользовательского регистратора](developing-a-user-interface-for-a-custom-log-provider.md)</span><span class="sxs-lookup"><span data-stu-id="acca6-137">[Coding a Custom Log Provider](coding-a-custom-log-provider.md) [Developing a User Interface for a Custom Log Provider](developing-a-user-interface-for-a-custom-log-provider.md)</span></span>


