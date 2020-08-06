---
title: Расширение вывода ошибок с помощью компонента скрипта | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- transformations [Integration Services], components
- Script component [Integration Services], examples
- error outputs [Integration Services], enhancing
- Script component [Integration Services], transformation components
ms.assetid: f7c02709-f1fa-4ebd-b255-dc8b81feeaa5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 18637aa1e147ce989645ae859681929f4d0c438a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668444"
---
# <a name="enhancing-an-error-output-with-the-script-component"></a><span data-ttu-id="d3595-102">Расширение вывода ошибок с помощью компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="d3595-102">Enhancing an Error Output with the Script Component</span></span>
  <span data-ttu-id="d3595-103">По умолчанию два дополнительных столбца в выводе ошибок служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], ErrorCode и ErrorColumn, содержат только числовые коды, представляющие номер ошибки и идентификатор столбца, в котором произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="d3595-103">By default, the two extra columns in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error output, ErrorCode and ErrorColumn, contain only numeric codes that represent an error number, and the ID of the column in which the error occurred.</span></span> <span data-ttu-id="d3595-104">Эти числовые значения могут быть малополезны без соответствующего описания ошибки.</span><span class="sxs-lookup"><span data-stu-id="d3595-104">These numeric values may be of limited use without the corresponding error description.</span></span>  
  
 <span data-ttu-id="d3595-105">В этом разделе описывается, как добавить столбец с описанием ошибки к существующим выходным данным ошибок в потоке данных с помощью компонента скрипта.</span><span class="sxs-lookup"><span data-stu-id="d3595-105">This topic describes how to add an error description column to existing error output data in the data flow by using the Script component.</span></span> <span data-ttu-id="d3595-106">В следующем примере с помощью метода <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> интерфейса <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>, доступ к которому можно получить через свойство <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> компонента скрипта, добавляется описание ошибки, соответствующее конкретному стандартному коду ошибки служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3595-106">The example adds the error description that corresponds to a specific predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error code by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, available through the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property of the Script component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d3595-107">Если нужно создать компонент, который будет полезен в нескольких задачах потока данных и нескольких пакетах, рекомендуется в качестве основы использовать этот образец компонента скрипта.</span><span class="sxs-lookup"><span data-stu-id="d3595-107">If you want to create a component that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in this Script component sample as the starting point for a custom data flow component.</span></span> <span data-ttu-id="d3595-108">Дополнительные сведения см. в разделе [Разработка пользовательского компонента потока данных](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="d3595-108">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3595-109">Пример</span><span class="sxs-lookup"><span data-stu-id="d3595-109">Example</span></span>  
 <span data-ttu-id="d3595-110">В приведенном примере компонент скрипта, настроенный в качестве преобразования, используется для добавления столбца с описанием ошибки к существующим выходным данным ошибок в потоке данных.</span><span class="sxs-lookup"><span data-stu-id="d3595-110">The example shown here uses a Script component configured as a transformation to add an error description column to existing error output data in the data flow.</span></span>  
  
 <span data-ttu-id="d3595-111">Дополнительные сведения о настройке компонента скрипта для использования в качестве преобразования в потоке данных см. в разделе [Создание синхронного преобразования с помощью компонента скрипта](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)и [Создание асинхронного преобразования с помощью компонента скрипта](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="d3595-111">For more information about how to configure the Script component for use as a transformation in the data flow, see [Creating a Synchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)and [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="d3595-112">Настройка этого примера компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="d3595-112">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="d3595-113">Перед созданием нового компонента скрипта настройте вышестоящий компонент в потоке данных для перенаправления строк в его вывод ошибок при возникновении ошибки или усечения.</span><span class="sxs-lookup"><span data-stu-id="d3595-113">Before creating the new Script component, configure an upstream component in the data flow to redirect rows to its error output when an error or truncation occurs.</span></span> <span data-ttu-id="d3595-114">В целях тестирования, возможно, следует настроить компонент таким образом, чтобы гарантировать возникновение ошибок, — например, настроив преобразование "Уточняющий запрос" между двумя таблицами, в котором уточняющий запрос непременно приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="d3595-114">For testing purposes, you may want to configure a component in a manner that ensures that errors will occur-for example, by configuring a Lookup transformation between two tables where the lookup will fail.</span></span>  
  
2.  <span data-ttu-id="d3595-115">Добавьте новый компонент скрипта в область конструктора потока данных и настройте его в качестве преобразования.</span><span class="sxs-lookup"><span data-stu-id="d3595-115">Add a new Script component to the Data Flow designer surface and configure it as a transformation.</span></span>  
  
3.  <span data-ttu-id="d3595-116">Соедините вывод ошибок вышестоящего компонента с новым компонентом скрипта.</span><span class="sxs-lookup"><span data-stu-id="d3595-116">Connect the error output from the upstream component to the new Script component.</span></span>  
  
4.  <span data-ttu-id="d3595-117">Откройте **Редактор преобразования "Скрипт"** и на странице **Скрипт** для свойства **ScriptLanguage** выберите язык скрипта.</span><span class="sxs-lookup"><span data-stu-id="d3595-117">Open the **Script Transformation Editor**, and on the **Script** page, for the **ScriptLanguage** property, select the script language.</span></span>  
  
5.  <span data-ttu-id="d3595-118">Нажмите кнопку **Изменить скрипт**, чтобы открыть интегрированную среду разработки средств [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] для приложений (VSTA), и добавьте приведенный ниже пример кода.</span><span class="sxs-lookup"><span data-stu-id="d3595-118">Click **Edit Script** to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE and add the sample code shown below.</span></span>  
  
6.  <span data-ttu-id="d3595-119">Закройте среду VSTA.</span><span class="sxs-lookup"><span data-stu-id="d3595-119">Close VSTA.</span></span>  
  
7.  <span data-ttu-id="d3595-120">В редакторе преобразования «Скрипт» на странице « **входные столбцы** » выберите столбец ErrorCode.</span><span class="sxs-lookup"><span data-stu-id="d3595-120">In the Script Transformation Editor, on the **Input Columns** page, select the ErrorCode column.</span></span>  
  
8.  <span data-ttu-id="d3595-121">На странице **входы и выходы** добавьте новый выходной столбец типа `String` с именем **ErrorDescription**.</span><span class="sxs-lookup"><span data-stu-id="d3595-121">On the **Inputs and Outputs** page, add a new output column of type `String` named **ErrorDescription**.</span></span> <span data-ttu-id="d3595-122">Увеличьте длину нового столбца по умолчанию до 255 для поддержки длинных сообщений.</span><span class="sxs-lookup"><span data-stu-id="d3595-122">Increase the default length of the new column to 255 to support long messages.</span></span>  
  
9. <span data-ttu-id="d3595-123">Закройте **редактор преобразования "Скрипт"**.</span><span class="sxs-lookup"><span data-stu-id="d3595-123">Close the **Script Transformation Editor.**</span></span>  
  
10. <span data-ttu-id="d3595-124">Соедините выход компонента скрипта с подходящим назначением.</span><span class="sxs-lookup"><span data-stu-id="d3595-124">Attach the output of the Script component to a suitable destination.</span></span> <span data-ttu-id="d3595-125">Назначение «Неструктурированный файл» проще всего при настройке в случае нерегламентированной отладки.</span><span class="sxs-lookup"><span data-stu-id="d3595-125">A Flat File destination is the easiest to configure for ad hoc testing.</span></span>  
  
11. <span data-ttu-id="d3595-126">Запустите пакет.</span><span class="sxs-lookup"><span data-stu-id="d3595-126">Run the package.</span></span>  
  
```vb  
Public Class ScriptMain  
    Inherits UserComponent  
    Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
  Row.ErrorDescription = _  
    Me.ComponentMetaData.GetErrorDescription(Row.ErrorCode)  
  
    End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain:  
    UserComponent  
{  
    public override void Input0_ProcessInputRow(Input0Buffer Row)  
    {  
  
  Row.ErrorDescription = this.ComponentMetaData.GetErrorDescription(Row.ErrorCode);  
  
    }  
}  
  
```  
  
<span data-ttu-id="d3595-127">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="d3595-127">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d3595-128">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="d3595-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d3595-129">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="d3595-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d3595-130">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="d3595-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3595-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="d3595-131">See Also</span></span>  
 <span data-ttu-id="d3595-132">[Обработка ошибок в данных](../data-flow/error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="d3595-132">[Error Handling in Data](../data-flow/error-handling-in-data.md) </span></span>  
 <span data-ttu-id="d3595-133">[Использование выводов ошибок в компоненте потока данных](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="d3595-133">[Using Error Outputs in a Data Flow Component](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="d3595-134">Создание синхронного преобразования с помощью компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="d3595-134">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md) 
  
  
