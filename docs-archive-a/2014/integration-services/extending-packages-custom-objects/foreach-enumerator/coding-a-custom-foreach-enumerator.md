---
title: Написание кода пользовательского перечислителя по каждому элементу | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom foreach enumerators [Integration Services], coding
ms.assetid: 279cf6de-d06f-40e7-b8ca-569310449f36
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2b7e6c16124f4682dbdc98f602417bf8f68ce099
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657168"
---
# <a name="coding-a-custom-foreach-enumerator"></a><span data-ttu-id="425cd-102">Написание кода пользовательского перечислителя по каждому элементу</span><span class="sxs-lookup"><span data-stu-id="425cd-102">Coding a Custom Foreach Enumerator</span></span>
  <span data-ttu-id="425cd-103">После создания класса, наследующего от базового класса <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>, и применения к нему атрибута <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute>, необходимо переопределить реализацию свойств и методов базового класса, чтобы обеспечить пользовательские функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="425cd-103">After you have created a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>  
  
 <span data-ttu-id="425cd-104">Рабочий образец пользовательского перечислителя см. в разделе [Разработка пользовательского интерфейса для пользовательского перечислителя по каждому элементу](developing-a-user-interface-for-a-custom-foreach-enumerator.md).</span><span class="sxs-lookup"><span data-stu-id="425cd-104">For a working sample of a custom enumerator, see [Developing a User Interface for a Custom ForEach Enumerator](developing-a-user-interface-for-a-custom-foreach-enumerator.md).</span></span>  
  
## <a name="initializing-the-enumerator"></a><span data-ttu-id="425cd-105">Инициализация перечислителя</span><span class="sxs-lookup"><span data-stu-id="425cd-105">Initializing the Enumerator</span></span>  
 <span data-ttu-id="425cd-106">Метод <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.InitializeForEachEnumerator%2A> можно переопределить для кэширования ссылок на диспетчеры соединений, определенные в пакете, и на интерфейс событий, который можно использовать для формирования ошибок, предупреждений и информационных сообщений.</span><span class="sxs-lookup"><span data-stu-id="425cd-106">You can override the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.InitializeForEachEnumerator%2A> method to cache references to the connection managers defined in the package, and to cache references to the events interface that you can use to raise errors, warnings, and informational messages.</span></span>  
  
## <a name="validating-the-enumerator"></a><span data-ttu-id="425cd-107">Проверка перечислителя</span><span class="sxs-lookup"><span data-stu-id="425cd-107">Validating the Enumerator</span></span>  
 <span data-ttu-id="425cd-108">Метод <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> переопределяется для проверки правильности настройки перечислителя.</span><span class="sxs-lookup"><span data-stu-id="425cd-108">You override the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> method to verify that the enumerator is correctly configured.</span></span> <span data-ttu-id="425cd-109">Если этот метод возвращает значение `Failure`, то перечислитель не будет выполнен в содержащем его пакете.</span><span class="sxs-lookup"><span data-stu-id="425cd-109">If the method returns `Failure`, the enumerator and the package that contains the enumerator will not be executed.</span></span> <span data-ttu-id="425cd-110">Реализация данного метода индивидуальна для каждого перечислителя, но если перечислитель опирается на объект <xref:Microsoft.SqlServer.Dts.Runtime.Variable> или <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>, то необходимо добавить код для проверки наличия этих объектов в коллекции, переданной методу.</span><span class="sxs-lookup"><span data-stu-id="425cd-110">The implementation of this method is specific to each enumerator, but if the enumerator relies on <xref:Microsoft.SqlServer.Dts.Runtime.Variable> or <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects, you should add code to verify that these objects exist in the collections that are provided to the method.</span></span>  
  
 <span data-ttu-id="425cd-111">Следующий пример кода иллюстрирует реализацию метода <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A>, который проверяет переменную, указанную в свойстве перечислителя.</span><span class="sxs-lookup"><span data-stu-id="425cd-111">The following code example demonstrates an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> that checks for a variable specified in a property of the enumerator.</span></span>  
  
```csharp  
private string variableNameValue;  
  
public string VariableName  
{  
    get{ return this.variableNameValue; }  
    set{ this.variableNameValue = value; }  
}  
  
public override DTSExecResult Validate(Connections connections, VariableDispenser variableDispenser, IDTSInfoEvents infoEvents, IDTSLogging log)  
{  
    if (!variableDispenser.Contains(this.variableNameValue))  
    {  
        infoEvents.FireError(0, "MyEnumerator", "The Variable " + this.variableNameValue + " does not exist in the collection.", "", 0);  
            return DTSExecResult.Failure;  
    }  
    return DTSExecResult.Success;  
}  
```  
  
```vb  
Private variableNameValue As String  
  
Public Property VariableName() As String  
    Get   
         Return Me.variableNameValue  
    End Get  
    Set (ByVal Value As String)   
         Me.variableNameValue = value  
    End Set  
End Property  
  
Public Overrides Function Validate(ByVal connections As Connections, ByVal variableDispenser As VariableDispenser, ByVal infoEvents As IDTSInfoEvents, ByVal log As IDTSLogging) As DTSExecResult  
    If Not variableDispenser.Contains(Me.variableNameValue) Then  
        infoEvents.FireError(0, "MyEnumerator", "The Variable " + Me.variableNameValue + " does not exist in the collection.", "", 0)  
            Return DTSExecResult.Failure  
    End If  
    Return DTSExecResult.Success  
End Function  
```  
  
## <a name="returning-the-collection"></a><span data-ttu-id="425cd-112">Возврат коллекции</span><span class="sxs-lookup"><span data-stu-id="425cd-112">Returning the Collection</span></span>  
 <span data-ttu-id="425cd-113">В процессе выполнения контейнер <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> вызывает метод пользовательского перечислителя <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="425cd-113">During execution, the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> container calls the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method of the custom enumerator.</span></span> <span data-ttu-id="425cd-114">В этом методе перечислитель создает и заполняет коллекцию элементов, после чего возвращает эту коллекцию.</span><span class="sxs-lookup"><span data-stu-id="425cd-114">In this method, the enumerator creates and populates its collection of items, and then returns the collection.</span></span> <span data-ttu-id="425cd-115">Затем объект <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> последовательно перебирает элементы коллекции и выполняет поток управления для каждого элемента коллекции.</span><span class="sxs-lookup"><span data-stu-id="425cd-115">The <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> then iterates the items in the collection, and executes its control flow for each item in the collection.</span></span>  
  
 <span data-ttu-id="425cd-116">Следующий пример иллюстрирует реализацию метода <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A>, который возвращает массив случайных значений.</span><span class="sxs-lookup"><span data-stu-id="425cd-116">The following example shows an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> that returns an array of random integers.</span></span>  
  
```csharp  
public override object GetEnumerator()  
{  
    ArrayList numbers = new ArrayList();  
  
    Random randomNumber = new Random(DateTime.Now);  
  
    for( int x=0; x < 100; x++ )  
        numbers.Add( randomNumber.Next());  
  
    return numbers;  
}  
```  
  
```vb  
Public Overrides Function GetEnumerator() As Object  
    Dim numbers As ArrayList =  New ArrayList()   
  
    Dim randomNumber As Random =  New Random(DateTime.Now)   
  
        Dim x As Integer  
        For  x = 0 To  100- 1  Step  x + 1  
        numbers.Add(randomNumber.Next())  
        Next  
  
    Return numbers  
End Function  
```  
  
<span data-ttu-id="425cd-117">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="425cd-117">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="425cd-118">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="425cd-118">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="425cd-119">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="425cd-119">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="425cd-120">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="425cd-120">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="425cd-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="425cd-121">See Also</span></span>  
 <span data-ttu-id="425cd-122">[Создание пользовательского перечислителя Foreach](creating-a-custom-foreach-enumerator.md) </span><span class="sxs-lookup"><span data-stu-id="425cd-122">[Creating a Custom Foreach Enumerator](creating-a-custom-foreach-enumerator.md) </span></span>  
 [<span data-ttu-id="425cd-123">Разработка пользовательского интерфейса для пользовательского перечислителя по каждому элементу</span><span class="sxs-lookup"><span data-stu-id="425cd-123">Developing a User Interface for a Custom ForEach Enumerator</span></span>](developing-a-user-interface-for-a-custom-foreach-enumerator.md)  
  
  
