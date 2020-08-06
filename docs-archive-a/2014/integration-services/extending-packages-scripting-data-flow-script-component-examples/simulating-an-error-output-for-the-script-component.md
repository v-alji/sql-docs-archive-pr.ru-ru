---
title: Имитация вывода ошибок для компонента скрипта | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], error output
- error outputs [Integration Services], Script component
ms.assetid: f8b6ecff-ac99-4231-a0e7-7ce4ad76bad0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bed458ce378eb26cd863811b4974b5f39429e1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729634"
---
# <a name="simulating-an-error-output-for-the-script-component"></a><span data-ttu-id="00d82-102">Имитация вывода ошибок для компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="00d82-102">Simulating an Error Output for the Script Component</span></span>
  <span data-ttu-id="00d82-103">Хотя невозможно напрямую настроить вывод ошибок в компоненте скрипта для автоматической обработки строк ошибок, можно воспроизвести функциональность встроенного вывода ошибок, создав дополнительный выход и используя условную логику в скрипте для направления строк на этот выход, когда это целесообразно.</span><span class="sxs-lookup"><span data-stu-id="00d82-103">Although you cannot directly configure an output as an error output in the Script component for automatic handling of error rows, you can reproduce the functionality of a built-in error output by creating an additional output and using conditional logic in your script to direct rows to this output when appropriate.</span></span> <span data-ttu-id="00d82-104">Возможно, потребуется имитация поведения встроенного вывода ошибок с помощью добавления двух дополнительных выходных столбцов для номера ошибки и идентификатора столбца, в котором эта ошибка возникла.</span><span class="sxs-lookup"><span data-stu-id="00d82-104">You may want to imitate the behavior of a built-in error output by adding two additional output columns to receive the error number and the ID of the column in which an error occurred.</span></span>  
  
 <span data-ttu-id="00d82-105">Если необходимо добавить описание ошибки, соответствующее конкретному стандартному коду ошибки служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], можно использовать метод <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> интерфейса <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>, доступ к которому можно получить через свойство <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> компонента скрипта.</span><span class="sxs-lookup"><span data-stu-id="00d82-105">If you want to add the error description that corresponds to a specific predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error code, you can use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, available through the Script component's <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00d82-106">Пример</span><span class="sxs-lookup"><span data-stu-id="00d82-106">Example</span></span>  
 <span data-ttu-id="00d82-107">В следующем примере используется компонент скрипта, настроенный в качестве преобразования и имеющий два синхронных выхода.</span><span class="sxs-lookup"><span data-stu-id="00d82-107">The example shown here uses a Script component configured as a transformation that has two synchronous outputs.</span></span> <span data-ttu-id="00d82-108">Этот компонент скрипта предназначен для фильтрации строк ошибок в строках, содержащих адреса, в образце базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="00d82-108">The purpose of the Script component is to filter error rows from address data in the AdventureWorks sample database.</span></span> <span data-ttu-id="00d82-109">Вымышленная ситуация, рассматриваемая в этом примере, предполагает увеличение количества клиентов в Северной Америке, в результате чего возникает необходимость выполнить фильтрацию, исключающую адреса, расположенные за пределами Северной Америки.</span><span class="sxs-lookup"><span data-stu-id="00d82-109">This fictitious example assumes that we are preparing a promotion for North American customers and need to filter out addresses that are not located in North America.</span></span>  
  
#### <a name="to-configure-the-example"></a><span data-ttu-id="00d82-110">Настройка примера</span><span class="sxs-lookup"><span data-stu-id="00d82-110">To configure the example</span></span>  
  
1.  <span data-ttu-id="00d82-111">Перед созданием нового компонента скрипта создайте диспетчер соединений и настройте источник потока данных, выбирающий адреса из образца базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="00d82-111">Before creating the new Script component, create a connection manager and configure a data flow source that selects address data from the AdventureWorks sample database.</span></span> <span data-ttu-id="00d82-112">В этом примере, где предусмотрено обращение только к столбцу CountryRegionName, можно просто использовать представление Person.vStateCountryProvinceRegion либо выбрать данные, соединив таблицы Person.Address, Person.StateProvince и Person.CountryRegion.</span><span class="sxs-lookup"><span data-stu-id="00d82-112">For this example, which only looks at the CountryRegionName column, you can simply use the Person.vStateCountryProvinceRegion view, or you can select data by joining the Person.Address, Person.StateProvince, and Person.CountryRegion tables.</span></span>  
  
2.  <span data-ttu-id="00d82-113">Добавьте новый компонент скрипта в область конструктора потока данных и настройте его в качестве преобразования.</span><span class="sxs-lookup"><span data-stu-id="00d82-113">Add a new Script component to the Data Flow designer surface and configure it as a transformation.</span></span> <span data-ttu-id="00d82-114">Откройте **редактор преобразования "Скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="00d82-114">Open the **Script Transformation Editor**.</span></span>  
  
3.  <span data-ttu-id="00d82-115">На странице **Скрипт** задайте свойство **ScriptLanguage**, указав язык скрипта, используемый для создания скрипта.</span><span class="sxs-lookup"><span data-stu-id="00d82-115">On the **Script** page, set the **ScriptLanguage** property to the script language that you want to use to code the script.</span></span>  
  
4.  <span data-ttu-id="00d82-116">Нажмите кнопку **Изменить скрипт**, чтобы открыть среду [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="00d82-116">Click **Edit Script** to open [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span>  
  
5.  <span data-ttu-id="00d82-117">В методе `Input0_ProcessInputRow` введите или вставьте следующий образец кода:</span><span class="sxs-lookup"><span data-stu-id="00d82-117">In the `Input0_ProcessInputRow` method, type or paste the sample code shown below.</span></span>  
  
6.  <span data-ttu-id="00d82-118">Закройте среду VSTA.</span><span class="sxs-lookup"><span data-stu-id="00d82-118">Close VSTA.</span></span>  
  
7.  <span data-ttu-id="00d82-119">На странице **Входные столбцы** выберите столбцы, которые необходимо обработать в преобразовании "Скрипт".</span><span class="sxs-lookup"><span data-stu-id="00d82-119">On the **Input Columns** page, select the columns that you want to process in the Script transformation.</span></span> <span data-ttu-id="00d82-120">В этом примере используется только столбец CountryRegionName.</span><span class="sxs-lookup"><span data-stu-id="00d82-120">This example uses only the CountryRegionName column.</span></span> <span data-ttu-id="00d82-121">Невыбранные доступные входные столбцы будут пропущены без изменения в потоке данных.</span><span class="sxs-lookup"><span data-stu-id="00d82-121">Available input columns that you leave unselected will simply be passed through unchanged in the data flow.</span></span>  
  
8.  <span data-ttu-id="00d82-122">На странице **входы и выходы** добавьте новый, второй выход и задайте `SynchronousInputID` для его значения идентификатор входа, который также является значением `SynchronousInputID` свойства выходного значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="00d82-122">On the **Inputs and Outputs** page, add a new, second output, and set its `SynchronousInputID` value to the ID of the input, which is also the value of the `SynchronousInputID` property of the default output.</span></span> <span data-ttu-id="00d82-123">Присвойте свойству `ExclusionGroup` обоих выходов одно и то же ненулевое значение (например, 1), чтобы указать, что каждая строка должна быть направлена только в один из двух выходов.</span><span class="sxs-lookup"><span data-stu-id="00d82-123">Set the `ExclusionGroup` property of both outputs to the same non-zero value (for example, 1) to indicate that each row will be directed to only one of the two outputs.</span></span> <span data-ttu-id="00d82-124">Дайте новому выводу ошибок понятное описательное имя, например MyErrorOutput.</span><span class="sxs-lookup"><span data-stu-id="00d82-124">Give the new error output a distinctive name, such as "MyErrorOutput."</span></span>  
  
9. <span data-ttu-id="00d82-125">Добавьте в новый вывод ошибок дополнительные выходные столбцы для отслеживания требуемых данных ошибок. В их число может входить код ошибки, идентификатор столбца, в котором возникла ошибка, а также, возможно, описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="00d82-125">Add additional output columns to the new error output to capture the desired error information, which may include the error code, the ID of the column in which the error occurred, and possibly the error description.</span></span> <span data-ttu-id="00d82-126">В этом примере создаются новые столбцы, ErrorColumn и ErrorMessage.</span><span class="sxs-lookup"><span data-stu-id="00d82-126">This example creates the new columns, ErrorColumn and ErrorMessage.</span></span> <span data-ttu-id="00d82-127">Если в реализации обрабатываются стандартные ошибки служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], необходимо добавить столбец ErrorCode для номера ошибки.</span><span class="sxs-lookup"><span data-stu-id="00d82-127">If you are catching predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] errors in your own implementation, make sure to add an ErrorCode column for the error number.</span></span>  
  
10. <span data-ttu-id="00d82-128">Запишите значение идентификатора входного столбца или столбцов, которые должны проверяться компонентом скрипта на наличие ошибок.</span><span class="sxs-lookup"><span data-stu-id="00d82-128">Note the ID value of the input column or columns that the Script component will check for error conditions.</span></span> <span data-ttu-id="00d82-129">В этом примере идентификатор столбца используется для заполнения значений в столбце ErrorColumn.</span><span class="sxs-lookup"><span data-stu-id="00d82-129">This example uses this column identifier to populate the ErrorColumn value.</span></span>  
  
11. <span data-ttu-id="00d82-130">Закройте **редактор преобразования "Скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="00d82-130">Close the **Script Transformation Editor.**</span></span>  
  
12. <span data-ttu-id="00d82-131">Соедините выходы компонента скрипта с подходящими назначениями.</span><span class="sxs-lookup"><span data-stu-id="00d82-131">Attach the outputs of the Script component to suitable destinations.</span></span> <span data-ttu-id="00d82-132">Назначение «Неструктурированный файл» проще всего для настройки тестирования в нерегламентированных случаях.</span><span class="sxs-lookup"><span data-stu-id="00d82-132">Flat file destinations are the easiest to configure for ad hoc testing.</span></span>  
  
13. <span data-ttu-id="00d82-133">Запустите пакет.</span><span class="sxs-lookup"><span data-stu-id="00d82-133">Run the package.</span></span>  
  
```vb  
Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
  If Row.CountryRegionName <> "Canada" _  
      And Row.CountryRegionName <> "United States" Then  
  
    Row.ErrorColumn = 68 ' ID of CountryRegionName column  
    Row.ErrorMessage = "Address is not in North America."  
    Row.DirectRowToMyErrorOutput()  
  
  Else  
  
    Row.DirectRowToOutput0()  
  
  End If  
  
End Sub  
```  
  
```csharp  
public override void Input0_ProcessInputRow(Input0Buffer Row)  
{  
  
  if (Row.CountryRegionName!="Canada"&&Row.CountryRegionName!="United States")  
  
  {  
    Row.ErrorColumn = 68; // ID of CountryRegionName column  
    Row.ErrorMessage = "Address is not in North America.";  
    Row.DirectRowToMyErrorOutput();  
  
  }  
  else  
  {  
  
    Row.DirectRowToOutput0();  
  
  }  
  
}  
```  
  
<span data-ttu-id="00d82-134">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="00d82-134">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="00d82-135">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="00d82-135">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="00d82-136">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="00d82-136">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="00d82-137">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="00d82-137">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00d82-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="00d82-138">See Also</span></span>  
 <span data-ttu-id="00d82-139">[Обработка ошибок в данных](../data-flow/error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="00d82-139">[Error Handling in Data](../data-flow/error-handling-in-data.md) </span></span>  
 <span data-ttu-id="00d82-140">[Использование вывода ошибок в компоненте потока данных](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="00d82-140">[Using Error Outputs in a Data Flow Component](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="00d82-141">Создание синхронного преобразования с помощью компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="00d82-141">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md) 
  
  
