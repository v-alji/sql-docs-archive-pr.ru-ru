---
title: Реализация внешних метаданных | Документы Майкрософт
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
- disconnected validation [Integration Services]
- connected validation [Integration Services]
- custom data flow components [Integration Services], validating
- validation [Integration Services], components
- metadata [Integration Services]
- data flow components [Integration Services], validating
- data flow components [Integration Services], external metadata
- custom data flow components [Integration Services], external metadata
- external metadata [Integration Services]
ms.assetid: 8f5bd3ed-3e79-43a4-b6c1-435e4c2cc8cc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7a6b77229c528bc08057e662a4b3761d1daf732f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729662"
---
# <a name="implementing-external-metadata"></a><span data-ttu-id="ff85c-102">Реализация внешних метаданных</span><span class="sxs-lookup"><span data-stu-id="ff85c-102">Implementing External Metadata</span></span>
  <span data-ttu-id="ff85c-103">Если компонент отключен от источника данных, можно выполнить проверку столбцов во входных и выходных коллекциях столбцов относительно внешнего источника данных с помощью интерфейса <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100>.</span><span class="sxs-lookup"><span data-stu-id="ff85c-103">When a component is disconnected from its data source, you can validate the columns in the input and output column collections against the columns at its external data source by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100> interface.</span></span> <span data-ttu-id="ff85c-104">Он позволяет сохранять моментальный снимок столбцов внешнего источника данных и сопоставлять эти столбцы со столбцами входных и выходных коллекций столбцов компонента.</span><span class="sxs-lookup"><span data-stu-id="ff85c-104">This interface lets you maintain a snapshot of the columns at the external data source and map these columns to the columns in the input and output column collection of the component.</span></span>  
  
 <span data-ttu-id="ff85c-105">Реализация столбцов внешних метаданных добавляет издержки и сложности при разработке компонента, поскольку необходимо хранить дополнительную коллекцию столбцов и выполнять их проверку, но возможность избежать затратных обращений к серверу во время проверки может оправдать такую разработку.</span><span class="sxs-lookup"><span data-stu-id="ff85c-105">Implementing external metadata columns adds a layer of overhead and complexity to component development, because you must maintain and validate against an additional column collection, but the ability to avoid expensive round trips to the server for validation may make this development work worthwhile.</span></span>  
  
## <a name="populating-external-metadata-columns"></a><span data-ttu-id="ff85c-106">Заполнение столбцов внешних метаданных</span><span class="sxs-lookup"><span data-stu-id="ff85c-106">Populating External Metadata Columns</span></span>  
 <span data-ttu-id="ff85c-107">Столбцы внешних метаданных обычно добавляются к коллекции, если создан соответствующий входной или выходной столбец.</span><span class="sxs-lookup"><span data-stu-id="ff85c-107">External metadata columns are typically added to the collection when the corresponding input or output column is created.</span></span> <span data-ttu-id="ff85c-108">Новые столбцы создаются вызовом метода <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.New%2A>.</span><span class="sxs-lookup"><span data-stu-id="ff85c-108">New columns are created by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.New%2A> method.</span></span> <span data-ttu-id="ff85c-109">Затем устанавливаются свойства столбца, чтобы соответствовать внешнему источнику данных.</span><span class="sxs-lookup"><span data-stu-id="ff85c-109">The properties of the column are then set to match the external data source.</span></span>  
  
 <span data-ttu-id="ff85c-110">Столбец внешних метаданных сопоставляется с соответствующим входным или выходным столбцом путем присвоения идентификатора столбца внешних метаданных свойству <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A> входного или выходного столбца.</span><span class="sxs-lookup"><span data-stu-id="ff85c-110">The external metadata column is mapped to the corresponding input or output column by assigning the ID of the external metadata column to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A> property of the input or output column.</span></span> <span data-ttu-id="ff85c-111">Это позволяет легко обнаружить столбец внешних метаданных для конкретного входного или выходного столбца с помощью метода <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.GetObjectByID%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="ff85c-111">This lets you locate the external metadata column easily for a specific input or output column by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.GetObjectByID%2A> method of the collection.</span></span>  
  
 <span data-ttu-id="ff85c-112">В следующем примере показано создание столбца внешних метаданных и его сопоставление с выходным столбцом с помощью установки свойства <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A>.</span><span class="sxs-lookup"><span data-stu-id="ff85c-112">The following example shows how to create an external metadata column and then map the column to an output column by setting the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A> property.</span></span>  
  
```csharp  
public void CreateExternalMetaDataColumn(IDTSOutput100 output, int outputColumnID )  
{  
    IDTSOutputColumn100 oColumn = output.OutputColumnCollection.GetObjectByID(outputColumnID);  
    IDTSExternalMetadataColumn100 eColumn = output.ExternalMetadataColumnCollection.New();  
  
    eColumn.DataType = oColumn.DataType;  
    eColumn.Precision = oColumn.Precision;  
    eColumn.Scale = oColumn.Scale;  
    eColumn.Length = oColumn.Length;  
    eColumn.CodePage = oColumn.CodePage;  
  
    oColumn.ExternalMetadataColumnID = eColumn.ID;  
}  
```  
  
```vb  
Public Sub CreateExternalMetaDataColumn(ByVal output As IDTSOutput100, ByVal outputColumnID As Integer)   
 Dim oColumn As IDTSOutputColumn100 = output.OutputColumnCollection.GetObjectByID(outputColumnID)   
 Dim eColumn As IDTSExternalMetadataColumn100 = output.ExternalMetadataColumnCollection.New   
 eColumn.DataType = oColumn.DataType   
 eColumn.Precision = oColumn.Precision   
 eColumn.Scale = oColumn.Scale   
 eColumn.Length = oColumn.Length   
 eColumn.CodePage = oColumn.CodePage   
 oColumn.ExternalMetadataColumnID = eColumn.ID   
End Sub  
```  
  
## <a name="validating-with-external-metadata-columns"></a><span data-ttu-id="ff85c-113">Проверка с помощью столбцов внешних метаданных</span><span class="sxs-lookup"><span data-stu-id="ff85c-113">Validating with External Metadata Columns</span></span>  
 <span data-ttu-id="ff85c-114">Проверка требует дополнительных шагов для компонента, хранящего коллекцию столбцов внешних метаданных, поскольку проверку необходимо выполнять относительно дополнительной коллекции столбцов.</span><span class="sxs-lookup"><span data-stu-id="ff85c-114">Validation requires additional steps for components that maintain an external metadata column collection, because you must validate against an additional collection of columns.</span></span> <span data-ttu-id="ff85c-115">Проверку можно разделить на проверку с подключением и проверку с отключением.</span><span class="sxs-lookup"><span data-stu-id="ff85c-115">Validation can be divided into connected validation or disconnected validation.</span></span>  
  
### <a name="connected-validation"></a><span data-ttu-id="ff85c-116">Проверка с подключением</span><span class="sxs-lookup"><span data-stu-id="ff85c-116">Connected Validation</span></span>  
 <span data-ttu-id="ff85c-117">Если компонент подключен к внешнему источнику данных, столбцы во входной или выходной коллекции проверяются непосредственно по внешнему источнику данных.</span><span class="sxs-lookup"><span data-stu-id="ff85c-117">When a component is connected to an external data source, the columns in the input or output collections are verified directly against the external data source.</span></span> <span data-ttu-id="ff85c-118">Кроме того, необходимо выполнить проверку в отношении столбцов в коллекции внешних метаданных.</span><span class="sxs-lookup"><span data-stu-id="ff85c-118">Additionally, the columns in the external metadata collection must be validated.</span></span> <span data-ttu-id="ff85c-119">Она необходима, так как коллекцию внешних метаданных можно изменить с помощью **расширенного редактора** в среде [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], а изменения коллекции не обнаруживаются.</span><span class="sxs-lookup"><span data-stu-id="ff85c-119">This is required because the external metadata collection can be modified by using the **Advanced Editor** in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], and changes made to the collection are not detectable.</span></span> <span data-ttu-id="ff85c-120">Поэтому в подключенном состоянии компоненты должны гарантировать соответствие коллекции столбцов внешних метаданных столбцам во внешнем источнике данных.</span><span class="sxs-lookup"><span data-stu-id="ff85c-120">Therefore, when connected, components must make sure that the columns in the external metadata column collection continue to reflect the columns at the external data source.</span></span>  
  
 <span data-ttu-id="ff85c-121">Вы можете скрыть коллекцию внешних метаданных в **Расширенный редактор** , задав <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.IsUsed%2A> для свойства коллекции значение `false` .</span><span class="sxs-lookup"><span data-stu-id="ff85c-121">You may choose to hide the external metadata collection in the **Advanced Editor** by setting the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.IsUsed%2A> property of the collection to `false`.</span></span> <span data-ttu-id="ff85c-122">Однако при этом также скрывается вкладка **Сопоставление столбцов** редактора, которая позволяет пользователям сопоставлять столбцы из входной или выходной коллекции столбцам коллекции столбцов внешних метаданных.</span><span class="sxs-lookup"><span data-stu-id="ff85c-122">However this also hides the **Column Mapping** tab of the editor, which lets users map columns from the input or output collection to the columns in the external metadata column collection.</span></span> <span data-ttu-id="ff85c-123">Значение `false` этого свойства не мешает разработчиками программно изменять коллекцию, но оно обеспечивает уровень защиты коллекции столбцов внешних метаданных для компонента, который используется исключительно в среде [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff85c-123">Setting this property to `false` does not prevent developers from programmatically modifying the collection, but it does provide a level of protection for the external metadata column collection of a component that is used exclusively in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="disconnected-validation"></a><span data-ttu-id="ff85c-124">Проверка с отключением</span><span class="sxs-lookup"><span data-stu-id="ff85c-124">Disconnected Validation</span></span>  
 <span data-ttu-id="ff85c-125">Если компонент отключен от внешнего источника данных, проверка упрощается, поскольку столбцы во входной или выходной коллекции проверяются по коллекции внешних метаданных, а не по внешнему источнику данных.</span><span class="sxs-lookup"><span data-stu-id="ff85c-125">When a component is disconnected from an external data source, validation is simplified because the columns in the input or output collection are verified directly against the columns in the external metadata collection and not against the external source.</span></span> <span data-ttu-id="ff85c-126">Компонент должен выполнять проверку с отключением, если не установлено соединение с внешним источником данных или если свойство <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="ff85c-126">A component should perform disconnected validation when the connection to its external data source has not been established, or when the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> property is `false`.</span></span>  
  
 <span data-ttu-id="ff85c-127">В следующем примере кода показана реализация компонента, выполняющего проверку подлинности по коллекции столбцов внешних метаданных.</span><span class="sxs-lookup"><span data-stu-id="ff85c-127">The following code example demonstrates an implementation of a component that performs validation against its external metadata column collection.</span></span>  
  
```csharp  
public override DTSValidationStatus Validate()  
{  
    if( this.isConnected && ComponentMetaData.ValidateExternalMetaData )  
    {  
        // TODO: Perform connected validation.  
    }  
    else  
    {  
        // TODO: Perform disconnected validation.  
    }  
}  
```  
  
```vb  
Public  Overrides Function Validate() As DTSValidationStatus   
 If Me.isConnected AndAlso ComponentMetaData.ValidateExternalMetaData Then   
  ' TODO: Perform connected validation.  
 Else   
  ' TODO: Perform disconnected validation.  
 End If   
End Function  
```  
  
<span data-ttu-id="ff85c-128">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="ff85c-128">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ff85c-129">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="ff85c-129">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ff85c-130">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="ff85c-130">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ff85c-131">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="ff85c-131">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff85c-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="ff85c-132">See Also</span></span>  
 [<span data-ttu-id="ff85c-133">Поток данных</span><span class="sxs-lookup"><span data-stu-id="ff85c-133">Data Flow</span></span>](../../data-flow/data-flow.md)  
  
  
