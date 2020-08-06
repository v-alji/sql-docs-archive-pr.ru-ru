---
title: Проверка компонента потока данных | Документы Майкрософт
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
- ReinitializeMetaData method
- Validate method
- component validation [Integration Services]
- custom data flow components [Integration Services], validating
- validation [Integration Services], components
- data flow components [Integration Services], validating
- validation [Integration Services]
ms.assetid: 1a7d5925-b387-4e31-af7f-c7f3c5151040
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9a78588c1e75697235e62e8955b65da466a37ea5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657834"
---
# <a name="validating-a-data-flow-component"></a><span data-ttu-id="33135-102">Проверка компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="33135-102">Validating a Data Flow Component</span></span>
  <span data-ttu-id="33135-103">Метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> базового класса <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> предназначен для того, чтобы не допустить исполнения неправильно настроенного компонента.</span><span class="sxs-lookup"><span data-stu-id="33135-103">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class is provided to prevent execution of a component that is not configured correctly.</span></span> <span data-ttu-id="33135-104">С помощью этого метода можно убедиться, что у компонента есть нужное число входных и выходных объектов, его пользовательские свойства имеют допустимые значения и что любые нужные соединения заданы.</span><span class="sxs-lookup"><span data-stu-id="33135-104">Use this method to verify that a component has the expected number of input and output objects, that the custom properties of the component have acceptable values, and that any connections, if required, are specified.</span></span> <span data-ttu-id="33135-105">Этот метод также используется для проверки правильности типов данных во входной и выходной коллекциях столбцов и что свойство <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSUsageType> всех столбцов настроено в соответствии с типом компонента.</span><span class="sxs-lookup"><span data-stu-id="33135-105">Use this method also to verify that the columns in the input and output collections have the correct data types and that the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSUsageType> of each column is set appropriately for the component.</span></span> <span data-ttu-id="33135-106">Реализация метода в базовом классе участвует в проверке: она проверяет коллекцию входных столбцов компонента, гарантируя, что каждый столбец этой коллекции ссылается на столбец коллекции <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputCollection100> вышестоящего компонента.</span><span class="sxs-lookup"><span data-stu-id="33135-106">The base class implementation assists in the validation process by checking the input column collection of the component and ensuring that each column in the collection refers to a column in the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputCollection100> of the upstream component.</span></span>  
  
## <a name="validate-method"></a><span data-ttu-id="33135-107">Метод Validate</span><span class="sxs-lookup"><span data-stu-id="33135-107">Validate Method</span></span>  
 <span data-ttu-id="33135-108">Метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> неоднократно вызывается при изменении компонента в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33135-108">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> method is called repeatedly when a component is edited in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="33135-109">Отзыв для конструктора и пользователей компонента можно обеспечить через возвращаемое значение <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus> из перечисления, а также с помощью выводимых предупреждений и сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="33135-109">You can provide feedback to the designer and to users of the component through the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus> enumeration return value, and by posting warnings and errors.</span></span> <span data-ttu-id="33135-110">Перечисление <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus> содержит три значения, указывающие на различные степени неудачи, и четвертое, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_ISVALID>, которое указывает, что компонент настроен правильно и готов к выполнению.</span><span class="sxs-lookup"><span data-stu-id="33135-110">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus> enumeration contains three values that indicate various stages of failure, and a fourth, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_ISVALID>, that indicates whether the component is correctly configured and ready to execute.</span></span>  
  
 <span data-ttu-id="33135-111">Значение <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_NEEDSNEWMETADATA> указывает, что в данных <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> есть ошибка и компонент может ее исправить.</span><span class="sxs-lookup"><span data-stu-id="33135-111">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_NEEDSNEWMETADATA> value indicates that an error exists in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>, and that the component can repair the errors.</span></span> <span data-ttu-id="33135-112">Если компонент обнаруживает ошибку в метаданных, которую может исправить, ее не следует исправлять в методе <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> и во время проверки не следует изменять метаданные <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="33135-112">If a component encounters a metadata error that it can repair, it should not fix the error in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> method, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> should not be modified during validation.</span></span> <span data-ttu-id="33135-113">Вместо этого метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> должен вернуть только значение <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_NEEDSNEWMETADATA>, а компонент должен исправить метаданные с помощью вызова метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>, как будет описано ниже в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="33135-113">Instead, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> method should return only <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_NEEDSNEWMETADATA>, and the component should repair the error in a call to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> method, as described later in this section.</span></span>  
  
 <span data-ttu-id="33135-114">Значение <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_ISBROKEN> указывает, что компонент содержит ошибку, которую можно исправить, изменив компонент в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="33135-114">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_ISBROKEN> value indicates that the component has an error that can be rectified by editing the component in the designer.</span></span> <span data-ttu-id="33135-115">Такая ошибка обычно вызвана неправильно заданным или настроенным пользовательским свойством или обязательным соединением.</span><span class="sxs-lookup"><span data-stu-id="33135-115">The error is typically caused by a custom property or a required connection that is not specified or is set incorrectly.</span></span>  
  
 <span data-ttu-id="33135-116">Последнее значение ошибки — <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_ISCORRUPT>: оно указывает, что компонент обнаружил ошибки, которые могут возникнуть только в случае непосредственного изменения свойства <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> редактированием XML-кода программного пакета или с помощью модели объектов.</span><span class="sxs-lookup"><span data-stu-id="33135-116">The final error value is <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_ISCORRUPT>, which indicates that the component has discovered errors that should only occur if the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> property has been modified directly, either by editing the package XML or by using the object model.</span></span> <span data-ttu-id="33135-117">Например, такая ошибка может возникнуть, если в компоненте добавлен только один входной параметр, но при проверке обнаруживается, что в метаданных <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> их указано несколько.</span><span class="sxs-lookup"><span data-stu-id="33135-117">For example, this kind of error occurs when a component has added only a single input, but validation discovers that more than one input exists in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span></span> <span data-ttu-id="33135-118">Ошибки, выдающие это возвращаемое значение, можно исправить только сбросом компонента с помощью кнопки **Сброс** в диалоговом окне **Расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="33135-118">Errors that generate this return value can only be repaired by resetting the component by using the **Reset** button in the **Advanced Editor** dialog box.</span></span>  
  
 <span data-ttu-id="33135-119">Кроме возвращения кода ошибки, компоненты предоставляют отзыв с помощью предупреждений и сообщений об ошибках, выдаваемых во время проверки.</span><span class="sxs-lookup"><span data-stu-id="33135-119">Besides returning error values, components provide feedback by posting warnings or errors during validation.</span></span> <span data-ttu-id="33135-120">Этот механизм поддерживают методы <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> и <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A>.</span><span class="sxs-lookup"><span data-stu-id="33135-120">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> methods provide this mechanism.</span></span> <span data-ttu-id="33135-121">При их вызове сообщения о соответствующих событиях публикуются в окне **Список ошибок** среды [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33135-121">When these methods are called, these events are posted in the **Error List** window of [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="33135-122">Затем разработчики компонента могут предоставить отзыв пользователям о происшедших ошибках и, по возможности, о способах их исправления.</span><span class="sxs-lookup"><span data-stu-id="33135-122">Component developers can then provide direct feedback to users on the errors that have occurred, and if appropriate, how to correct them.</span></span>  
  
 <span data-ttu-id="33135-123">В следующем примере кода показана переопределенная реализация метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="33135-123">The following code example shows an overridden implementation of <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>.</span></span>  
  
```csharp  
public override DTSValidationStatus Validate()  
{  
    bool pbCancel = false;  
  
    // Validate that there is one input.  
    if (ComponentMetaData.InputCollection.Count != 1)  
    {  
    ComponentMetaData.FireError(0, ComponentMetaData.Name, "Incorrect number of inputs.", "", 0, out pbCancel);  
    return DTSValidationStatus.VS_ISCORRUPT;  
    }  
  
    // Validate that the UserName custom property is set.  
    if (ComponentMetaData.CustomPropertyCollection["UserName"].Value == null || ((string)ComponentMetaData.CustomPropertyCollection["UserName"].Value).Length == 0)  
    {  
        ComponentMetaData.FireError(0, ComponentMetaData.Name, "The UserName property must be set.", "", 0, out pbCancel);  
        return DTSValidationStatus.VS_ISBROKEN;  
    }  
  
    // Validate that there is one output.  
    if (ComponentMetaData.OutputCollection.Count != 1)  
    {  
        ComponentMetaData.FireError(0, ComponentMetaData.Name, "Incorrect number of outputs.", "", 0, out pbCancel);  
        return DTSValidationStatus.VS_ISCORRUPT;  
    }  
  
    // Let the base class verify that the input column reflects the output   
    // of the upstream component.  
    return base.Validate();  
}  
```  
  
```vb  
Public  Overrides Function Validate() As DTSValidationStatus   
  
 Dim pbCancel As Boolean = False  
  
 ' Validate that there is one input.  
 If Not (ComponentMetaData.InputCollection.Count = 1) Then   
   ComponentMetaData.FireError(0, ComponentMetaData.Name, "Incorrect number of inputs.", "", 0, pbCancel)   
   Return DTSValidationStatus.VS_ISCORRUPT   
 End If   
  
 ' Validate that the UserName custom property is set.  
 If ComponentMetaData.CustomPropertyCollection("UserName").Value Is Nothing OrElse CType(ComponentMetaData.CustomPropertyCollection("UserName").Value, String).Length = 0 Then   
   ComponentMetaData.FireError(0, ComponentMetaData.Name, "The UserName property must be set.", "", 0, pbCancel)   
   Return DTSValidationStatus.VS_ISBROKEN   
 End If   
  
 ' Validate that there is one output.  
 If Not (ComponentMetaData.OutputCollection.Count = 1) Then   
   ComponentMetaData.FireError(0, ComponentMetaData.Name, "Incorrect number of outputs.", "", 0, pbCancel)   
   Return DTSValidationStatus.VS_ISCORRUPT   
 End If   
  
 ' Let the base class verify that the input column reflects the output   
 ' of the upstream component.  
  
 Return MyBase.Validate   
  
End Function  
```  
  
## <a name="reinitializemetadata-method"></a><span data-ttu-id="33135-124">Метод ReinitializeMetaData</span><span class="sxs-lookup"><span data-stu-id="33135-124">ReinitializeMetaData Method</span></span>  
 <span data-ttu-id="33135-125">Метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> вызывается конструктором служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] каждый раз, когда компонент возвращает значение <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_NEEDSNEWMETADATA> после вызова метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="33135-125">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> method is called by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer whenever you edit a component that returns <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_NEEDSNEWMETADATA> from its <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> method.</span></span> <span data-ttu-id="33135-126">Компоненты должны содержать код, который обнаруживает и устраняет проблемы, выявленные компонентом во время проверки.</span><span class="sxs-lookup"><span data-stu-id="33135-126">Components should contain code that detects and corrects the problems identified by the component during validation.</span></span>  
  
 <span data-ttu-id="33135-127">В этом примере показан компонент, обнаруживающий недостатки в ходе проверки и исправляющий их с помощью метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="33135-127">The following example shows a component that detects problems during validation and fixes these errors in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> method.</span></span>  
  
```csharp  
private bool areInputColumnsValid = true;  
public override DTSValidationStatus Validate()  
{  
    IDTSInput100 input = ComponentMetaData.InputCollection[0];  
    IDTSVirtualInput100 vInput = input.GetVirtualInput();  
  
    bool Cancel = false;  
    foreach (IDTSInputColumn100 column in input.InputColumnCollection)  
    {  
        try  
        {  
            IDTSVirtualInputColumn100 vColumn = vInput.VirtualInputColumnCollection.GetVirtualInputColumnByLineageID(column.LineageID);  
        }  
        catch  
        {  
            ComponentMetaData.FireError(0, ComponentMetaData.Name, "The input column " + column.IdentificationString + " does not match a column in the upstream component.", "", 0, out Cancel);  
            areInputColumnsValid = false;  
            return DTSValidationStatus.VS_NEEDSNEWMETADATA;  
        }  
    }  
  
    return DTSValidationStatus.VS_ISVALID;  
}  
public override void ReinitializeMetaData()  
{  
    if (!areInputColumnsValid)  
    {  
        IDTSInput100 input = ComponentMetaData.InputCollection[0];  
        IDTSVirtualInput100 vInput = input.GetVirtualInput();  
  
        foreach (IDTSInputColumn100 column in input.InputColumnCollection)  
        {  
            IDTSVirtualInputColumn100 vColumn = vInput.VirtualInputColumnCollection.GetVirtualInputColumnByLineageID(column.LineageID);  
  
            if (vColumn == null)  
                input.InputColumnCollection.RemoveObjectByID(column.ID);  
        }  
        areInputColumnsValid = true;  
    }  
}  
```  
  
```vb  
Private areInputColumnsValid As Boolean = True   
  
Public  Overrides Function Validate() As DTSValidationStatus   
 Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)   
 Dim vInput As IDTSVirtualInput100 = input.GetVirtualInput   
 Dim Cancel As Boolean = False   
 For Each column As IDTSInputColumn100 In input.InputColumnCollection   
   Try   
     Dim vColumn As IDTSVirtualInputColumn100 = vInput.VirtualInputColumnCollection.GetVirtualInputColumnByLineageID(column.LineageID)   
   Catch   
     ComponentMetaData.FireError(0, ComponentMetaData.Name, "The input column " + column.IdentificationString + " does not match a column in the upstream component.", "", 0, Cancel)   
     areInputColumnsValid = False   
     Return DTSValidationStatus.VS_NEEDSNEWMETADATA   
   End Try   
 Next   
 Return DTSValidationStatus.VS_ISVALID   
End Function   
  
Public  Overrides Sub ReinitializeMetaData()   
 If Not areInputColumnsValid Then   
   Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)   
   Dim vInput As IDTSVirtualInput100 = input.GetVirtualInput   
   For Each column As IDTSInputColumn100 In input.InputColumnCollection   
     Dim vColumn As IDTSVirtualInputColumn100 = vInput.VirtualInputColumnCollection.GetVirtualInputColumnByLineageID(column.LineageID)   
     If vColumn Is Nothing Then   
       input.InputColumnCollection.RemoveObjectByID(column.ID)   
     End If   
   Next   
   areInputColumnsValid = True   
 End If   
End Sub  
```  
  
<span data-ttu-id="33135-128">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="33135-128">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="33135-129">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="33135-129">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="33135-130">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="33135-130">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="33135-131">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="33135-131">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
