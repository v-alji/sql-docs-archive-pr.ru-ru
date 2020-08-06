---
title: Создание пользовательского перечислителя по каждому элементу | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom foreach enumerators [Integration Services], creating
ms.assetid: 050e8455-2ed0-4b6d-b3ea-4e80e6c28487
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d99970d466aa53d25a80f0600f1fce7819e94956
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657166"
---
# <a name="creating-a-custom-foreach-enumerator"></a><span data-ttu-id="0b6fd-102">Создание пользовательского перечислителя по каждому элементу</span><span class="sxs-lookup"><span data-stu-id="0b6fd-102">Creating a Custom Foreach Enumerator</span></span>
  <span data-ttu-id="0b6fd-103">Создание пользовательского перечислителя по каждому элементу, как и любого другого пользовательского объекта для служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], осуществляется за несколько шагов, а именно:</span><span class="sxs-lookup"><span data-stu-id="0b6fd-103">The steps involved in creating a custom foreach enumerator are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="0b6fd-104">Создайте новый класс, наследующий базовый класс.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-104">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="0b6fd-105">Для перечислителя по каждому элементу базовым классом является <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-105">For a foreach enumerator, the base class is <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>.</span></span>  
  
-   <span data-ttu-id="0b6fd-106">Примените к классу атрибут, определяющий тип объекта.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-106">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="0b6fd-107">Для перечислителя по каждому элементу используется атрибут <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-107">For a foreach enumerator, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute>.</span></span>  
  
-   <span data-ttu-id="0b6fd-108">Переопределите реализацию методов и свойств базового класса.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-108">Override the implementation of the base class's methods and properties.</span></span> <span data-ttu-id="0b6fd-109">Наиболее важным методом для перечислителя по каждому элементу является <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-109">For a foreach enumerator, the most important is the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method.</span></span>  
  
-   <span data-ttu-id="0b6fd-110">При необходимости разработайте настраиваемый пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-110">Optionally, develop a custom user interface.</span></span> <span data-ttu-id="0b6fd-111">В случае с перечислителем по каждому элементу для этого необходимо использовать класс, реализующий интерфейс <xref:Microsoft.SqlServer.Dts.Runtime.IDTSForEachEnumeratorUI>.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-111">For a foreach enumerator, this requires a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSForEachEnumeratorUI> interface.</span></span>  
  
 <span data-ttu-id="0b6fd-112">Пользовательский перечислитель размещается в контейнере <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop>.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-112">A custom enumerator is hosted by the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> container.</span></span> <span data-ttu-id="0b6fd-113">Во время выполнения контейнером <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> вызывается метод <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> пользовательского перечислителя.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-113">At run time, the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> container calls the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method of the custom enumerator.</span></span> <span data-ttu-id="0b6fd-114">Пользовательский перечислитель возвращает объект, реализующий интерфейс `IEnumerable`, например, `ArrayList`.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-114">The custom enumerator returns an object that implements the `IEnumerable` interface, such as an `ArrayList`.</span></span> <span data-ttu-id="0b6fd-115">Затем перечислитель <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> просматривает последовательно все элементы коллекции, передает значение текущего элемента в поток управления через определяемую пользователем переменную и выполняет поток управления в контейнере.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-115">The <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> then iterates over each element in the collection, provides the value of the current element to the control flow through a user-defined variable, and executes the control flow in the container.</span></span>  
  
## <a name="getting-started-with-a-custom-foreach-enumerator"></a><span data-ttu-id="0b6fd-116">Приступая к работе над пользовательским перечислителем по каждому элементу</span><span class="sxs-lookup"><span data-stu-id="0b6fd-116">Getting Started with a Custom ForEach Enumerator</span></span>  
  
### <a name="creating-projects-and-classes"></a><span data-ttu-id="0b6fd-117">Создание проектов и классов</span><span class="sxs-lookup"><span data-stu-id="0b6fd-117">Creating Projects and Classes</span></span>  
 <span data-ttu-id="0b6fd-118">Так как все управляемые перечислители по каждому элементу являются производными от базового класса <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>, на первом шаге создания пользовательского перечислителя по каждому элементу необходимо создать проект библиотеки классов на предпочитаемом языке программирования управляемого кода, а затем создать класс, наследующий от базового класса.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-118">Because all managed foreach enumerators derive from the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> base class, the first step when you create a custom foreach enumerator is to create a class library project in your preferred managed programming language and create a class that inherits from the base class.</span></span> <span data-ttu-id="0b6fd-119">В этом производном классе будут переопределены методы и свойства базового класса, реализующие пользовательские функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-119">In this derived class you will override the methods and properties of the base class to implement your custom functionality.</span></span>  
  
 <span data-ttu-id="0b6fd-120">Создайте в том же решении второй проект библиотеки классов для собственного пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-120">In the same solution, create a second class library project for the custom user interface.</span></span> <span data-ttu-id="0b6fd-121">Для пользовательского интерфейса рекомендуется использовать отдельную сборку, что позволяет обновлять и заново развертывать перечислитель по каждому элементу или его пользовательский интерфейс независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-121">A separate assembly for the user interface is recommended for ease of deployment because it allows you to update and redeploy the foreach enumerator or its user interface independently.</span></span>  
  
 <span data-ttu-id="0b6fd-122">Настройте в обоих проектах подписывание сборок, которые будут создаваться во время построения, с помощью файла ключа для строгого имени.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-122">Configure both projects to sign the assemblies that will be generated at build time by using a strong name key file.</span></span>  
  
### <a name="applying-the-dtsforeachenumerator-attribute"></a><span data-ttu-id="0b6fd-123">Применение атрибута DtsForEachEnumerator</span><span class="sxs-lookup"><span data-stu-id="0b6fd-123">Applying the DtsForEachEnumerator Attribute</span></span>  
 <span data-ttu-id="0b6fd-124">Примените к созданному классу атрибут <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute>, чтобы определить его как перечислитель по каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-124">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> attribute to the class that you have created to identify it as a foreach enumerator.</span></span> <span data-ttu-id="0b6fd-125">Этот атрибут содержит сведения для времени разработки, например, имя и описание перечислителя по каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-125">This attribute provides design-time information such as the name and description of the foreach enumerator.</span></span> <span data-ttu-id="0b6fd-126">`Name`Свойство отображается в раскрывающемся списке доступных перечислителей на вкладке **коллекция** диалогового окна **Редактор циклов по каждому** элементу.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-126">The `Name` property appears in the dropdown list of available enumerators on the **Collection** tab of the **Foreach Loop Editor** dialog box.</span></span>  
  
 <span data-ttu-id="0b6fd-127">Используйте свойство <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute.UITypeName%2A>, чтобы связать перечислитель по каждому элементу с его пользовательским интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-127">Use the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute.UITypeName%2A> property to link the foreach enumerator to its custom user interface.</span></span> <span data-ttu-id="0b6fd-128">Чтобы получить токен открытого ключа, необходимый для этого свойства, можно использовать команду **sn.exe -t**, отображающую токен открытого ключа из SNK-файла пары ключей, который предназначен для подписывания сборки пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-128">To obtain the public key token that is required for this property, you an use **sn.exe -t** to display the public key token from the key pair (.snk) file that you intend to use to sign the user interface assembly.</span></span>  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
Namespace Microsoft.Samples.SqlServer.Dts  
    <DtsForEachEnumerator(DisplayName = "MyEnumerator", Description="A sample custom enumerator", UITypeName="FullyQualifiedTypeName,AssemblyName,Version=1.00.000.00,Culture=Neutral,PublicKeyToken=<publickeytoken>")> _   
    Public Class MyEnumerator  
     Inherits ForEachEnumerator  
        'Insert code here.  
    End Class  
End Namespace  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsForEachEnumerator( DisplayName = "MyEnumerator", Description="A sample custom enumerator", UITypeName="FullyQualifiedTypeName,AssemblyName,Version=1.00.000.00,Culture=Neutral,PublicKeyToken=<publickeytoken>")]  
    public class MyEnumerator : ForEachEnumerator  
    {  
        //Insert code here.  
    }  
}  
```  
  
## <a name="building-deploying-and-debugging-a-custom-enumerator"></a><span data-ttu-id="0b6fd-129">Построение, развертывание и отладка пользовательского перечислителя</span><span class="sxs-lookup"><span data-stu-id="0b6fd-129">Building, Deploying, and Debugging a Custom Enumerator</span></span>  
 <span data-ttu-id="0b6fd-130">Построение, развертывание и отладка пользовательского перечислителя по каждому элементу в службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] осуществляется за несколько шагов, аналогичных используемым при работе с другими типами пользовательских объектов.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-130">The steps for building, deploying, and debugging a custom foreach enumerator in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are very similar to the steps required for other types of custom objects.</span></span> <span data-ttu-id="0b6fd-131">Дополнительные сведения см. в разделе [Сборка, развертывание и отладка пользовательских объектов](../building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="0b6fd-131">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>  
  
<span data-ttu-id="0b6fd-132">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="0b6fd-132">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="0b6fd-133">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="0b6fd-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="0b6fd-134">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="0b6fd-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="0b6fd-135">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="0b6fd-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b6fd-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="0b6fd-136">See Also</span></span>  
 <span data-ttu-id="0b6fd-137">[Написание кода пользовательского перечислителя Foreach](coding-a-custom-foreach-enumerator.md) </span><span class="sxs-lookup"><span data-stu-id="0b6fd-137">[Coding a Custom Foreach Enumerator](coding-a-custom-foreach-enumerator.md) </span></span>  
 [<span data-ttu-id="0b6fd-138">Разработка пользовательского интерфейса для пользовательского перечислителя по каждому элементу</span><span class="sxs-lookup"><span data-stu-id="0b6fd-138">Developing a User Interface for a Custom ForEach Enumerator</span></span>](developing-a-user-interface-for-a-custom-foreach-enumerator.md)  
  
  
