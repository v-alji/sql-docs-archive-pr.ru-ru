---
title: Обновление версии компонента потока данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- PerformUpgrade method
- custom data flow components [Integration Services], upgrading version
- data flow components [Integration Services], upgrading version
- upgrading data flow components [Integration Services]
ms.assetid: c2a298c6-01b3-4ad1-884d-6108165eb56e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f494793a20f1cdcd108553278b82a44daeea75ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669002"
---
# <a name="upgrading-the-version-of-a-data-flow-component"></a><span data-ttu-id="3b4a0-102">Обновление версии компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="3b4a0-102">Upgrading the Version of a Data Flow Component</span></span>
  <span data-ttu-id="3b4a0-103">Пакеты, созданные с устаревшей версией компонента, могут содержать недопустимые метаданные, например, пользовательские свойства, применение которых было изменено в более новых версиях компонента.</span><span class="sxs-lookup"><span data-stu-id="3b4a0-103">Packages that were created with an older version of your component may contain metadata that is no longer valid, such as custom properties whose usage has been modified in newer versions of the component.</span></span> <span data-ttu-id="3b4a0-104">Можно переопределить метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> базового класса <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>, чтобы обеспечить обновление метаданных, которые были сохранены в ранее созданных пакетах, для соответствия текущим свойствам компонента.</span><span class="sxs-lookup"><span data-stu-id="3b4a0-104">You can override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class to update the metadata previously saved in older packages to reflect the current properties of your component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b4a0-105">При перекомпиляции пользовательского компонента для более новой версии служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] нет необходимости изменять значение свойства <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A>, если свойства компонента не изменялись.</span><span class="sxs-lookup"><span data-stu-id="3b4a0-105">When you recompile a custom component for a new version of [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], you do not have to change the value of the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> property if the component's properties have not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b4a0-106">Пример</span><span class="sxs-lookup"><span data-stu-id="3b4a0-106">Example</span></span>  
 <span data-ttu-id="3b4a0-107">В следующем образце содержится код из версии 2.0 вымышленного компонента потока данных.</span><span class="sxs-lookup"><span data-stu-id="3b4a0-107">The following sample contains code from version 2.0 of a fictitious data flow component.</span></span> <span data-ttu-id="3b4a0-108">Номер новой версии определен в свойстве <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> атрибута <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3b4a0-108">The new version number is defined in the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span></span> <span data-ttu-id="3b4a0-109">Компонент имеет свойство, которым определяется обработка числовых значений, превышающих заданное пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="3b4a0-109">The component has a property that defines how numeric values that exceed a threshold are to be handled.</span></span> <span data-ttu-id="3b4a0-110">В версии 1.0 вымышленного компонента это свойство называлось `RaiseErrorOnInvalidValue` и принимало логическое значение (true или false).</span><span class="sxs-lookup"><span data-stu-id="3b4a0-110">In version 1.0 of the fictitious component, this property was named `RaiseErrorOnInvalidValue` and accepted a Boolean value of true or false.</span></span> <span data-ttu-id="3b4a0-111">В версии 2.0 вымышленного компонента свойство было переименовано в `InvalidValueHandling` и настроено для приема одного из четырех возможных значений, полученных в результате пользовательского перечисления.</span><span class="sxs-lookup"><span data-stu-id="3b4a0-111">In version 2.0 of the fictitious component, the property has been renamed to `InvalidValueHandling` and accepts one of four possible values from a custom enumeration.</span></span>  
  
 <span data-ttu-id="3b4a0-112">Переопределенный метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> в следующем образце выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3b4a0-112">The overridden <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> method in the following sample performs the following actions:</span></span>  
  
-   <span data-ttu-id="3b4a0-113">Возвращает текущую версию компонента.</span><span class="sxs-lookup"><span data-stu-id="3b4a0-113">Gets the current version of the component.</span></span>  
  
-   <span data-ttu-id="3b4a0-114">Возвращает предыдущее значение пользовательского свойства.</span><span class="sxs-lookup"><span data-stu-id="3b4a0-114">Gets the value of the old custom property.</span></span>  
  
-   <span data-ttu-id="3b4a0-115">Удаляет прежнее свойство из коллекции пользовательских свойств.</span><span class="sxs-lookup"><span data-stu-id="3b4a0-115">Removes the old property from the custom property collection.</span></span>  
  
-   <span data-ttu-id="3b4a0-116">Задает значение нового пользовательского свойства на основе значения прежнего свойства (если это возможно).</span><span class="sxs-lookup"><span data-stu-id="3b4a0-116">Sets the value of the new custom property based on the value of the old property, if possible.</span></span>  
  
-   <span data-ttu-id="3b4a0-117">Указывает версию метаданных в соответствии с текущей версией компонента.</span><span class="sxs-lookup"><span data-stu-id="3b4a0-117">Sets the version metadata to the current version of the component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b4a0-118">Подсистема обработки потока данных передает номер своей версии в метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> через параметр *pipelineVersion*.</span><span class="sxs-lookup"><span data-stu-id="3b4a0-118">The data flow engine passes its own version number into the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> method in the *pipelineVersion* parameter.</span></span> <span data-ttu-id="3b4a0-119">Этот параметр бесполезен в версии 1.0 служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], но может оказаться полезным в последующих версиях.</span><span class="sxs-lookup"><span data-stu-id="3b4a0-119">This parameter is not useful in version 1.0 of [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], but may become useful in subsequent versions.</span></span>  
  
 <span data-ttu-id="3b4a0-120">В образце кода используются только два значения перечисления, которые сопоставляются непосредственно с предыдущими логическими значениями пользовательского свойства.</span><span class="sxs-lookup"><span data-stu-id="3b4a0-120">The sample code uses only the two enumeration values that map directly to the prior Boolean values for the custom property.</span></span> <span data-ttu-id="3b4a0-121">Пользователи могут выбрать другие доступные значения перечисления с помощью пользовательского интерфейса компонента, в расширенном редакторе или программным способом.</span><span class="sxs-lookup"><span data-stu-id="3b4a0-121">Users can select the other available enumeration values through the component's custom user interface, in the Advanced Editor, or programmatically.</span></span> <span data-ttu-id="3b4a0-122">Сведения об отображении значений перечисления для пользовательского свойства в расширенном редакторе см. в подразделе "Создание пользовательских свойств" раздела [Методы времени разработки для компонента потока данных](design-time-methods-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="3b4a0-122">For information on displaying enumeration values for a custom property in the Advanced Editor, see "Creating Custom Properties" in [Design-time Methods of a Data Flow Component](design-time-methods-of-a-data-flow-component.md).</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
<DtsPipelineComponent(ComponentType:=ComponentType.Transform, CurrentVersion:=2)> _  
Public Class PerformUpgrade  
  Inherits PipelineComponent  
  
  ' Define the set of possible values for the new custom property.  
  Private Enum InvalidValueHandling  
    Ignore  
    FireInformation  
    FireWarning  
    FireError  
  End Enum  
  
  Public Overloads Overrides Sub PerformUpgrade(ByVal pipelineVersion As Integer)  
  
    ' Obtain the current component version from the attribute.  
    Dim componentAttribute As DtsPipelineComponentAttribute = _  
      CType(Attribute.GetCustomAttribute(Me.GetType, _  
      GetType(DtsPipelineComponentAttribute), False), _  
      DtsPipelineComponentAttribute)  
    Dim currentVersion As Integer = componentAttribute.CurrentVersion  
  
    ' If the component version saved in the package is less than  
    '  the current version, Version 2, perform the upgrade.  
    If ComponentMetaData.Version < currentVersion Then  
  
      ' Get the current value of the old custom property, RaiseErrorOnInvalidValue,   
      ' and then remove the property from the custom property collection.  
      Dim oldValue As Boolean = False  
      Try  
        Dim oldProperty As IDTSCustomProperty100 = _  
          ComponentMetaData.CustomPropertyCollection("RaiseErrorOnInvalidValue")  
        oldValue = CType(oldProperty.Value, Boolean)  
        ComponentMetaData.CustomPropertyCollection.RemoveObjectByIndex("RaiseErrorOnInvalidValue")  
      Catch ex As Exception  
        ' If the old custom property is not available, ignore the error.  
      End Try  
  
      ' Set the value of the new custom property, InvalidValueHandling,  
      '  by using the appropriate enumeration value.  
      Dim newProperty As IDTSCustomProperty100 = _  
        ComponentMetaData.CustomPropertyCollection("InvalidValueHandling")  
      If oldValue = True Then  
        newProperty.Value = InvalidValueHandling.FireError  
      Else  
        newProperty.Value = InvalidValueHandling.Ignore  
      End If  
  
    End If  
  
    ' Update the saved component version metadata to the current version.  
    ComponentMetaData.Version = currentVersion  
  
  End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
[DtsPipelineComponent(ComponentType = ComponentType.Transform, CurrentVersion = 2)]  
public class PerformUpgradeCS :  
  PipelineComponent  
  
  // Define the set of possible values for the new custom property.  
{  
  private enum InvalidValueHandling  
  {  
    Ignore,  
    FireInformation,  
    FireWarning,  
    FireError  
  };  
  
  public override void PerformUpgrade(int pipelineVersion)  
  {  
  
    // Obtain the current component version from the attribute.  
    DtsPipelineComponentAttribute componentAttribute =   
      (DtsPipelineComponentAttribute)Attribute.GetCustomAttribute(this.GetType(), typeof(DtsPipelineComponentAttribute), false);  
    int currentVersion = componentAttribute.CurrentVersion;  
  
    // If the component version saved in the package is less than  
    //  the current version, Version 2, perform the upgrade.  
    if (ComponentMetaData.Version < currentVersion)  
  
    // Get the current value of the old custom property, RaiseErrorOnInvalidValue,   
    // and then remove the property from the custom property collection.  
    {  
      bool oldValue = false;  
      try  
      {  
        IDTSCustomProperty100 oldProperty =   
          ComponentMetaData.CustomPropertyCollection["RaiseErrorOnInvalidValue"];  
        oldValue = (bool)oldProperty.Value;  
        ComponentMetaData.CustomPropertyCollection.RemoveObjectByIndex("RaiseErrorOnInvalidValue");  
      }  
      catch (Exception ex)  
      {  
        // If the old custom property is not available, ignore the error.  
      }  
  
      // Set the value of the new custom property, InvalidValueHandling,  
      //  by using the appropriate enumeration value.  
      IDTSCustomProperty100 newProperty =   
         ComponentMetaData.CustomPropertyCollection["InvalidValueHandling"];  
      if (oldValue == true)  
      {  
        newProperty.Value = InvalidValueHandling.FireError;  
      }  
      else  
      {  
        newProperty.Value = InvalidValueHandling.Ignore;  
      }  
  
    }  
  
    // Update the saved component version metadata to the current version.  
    ComponentMetaData.Version = currentVersion;  
  
  }  
  
}  
```  
  
<span data-ttu-id="3b4a0-123">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="3b4a0-123">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="3b4a0-124">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="3b4a0-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="3b4a0-125">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="3b4a0-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="3b4a0-126">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="3b4a0-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
