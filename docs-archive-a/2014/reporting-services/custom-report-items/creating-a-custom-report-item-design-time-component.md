---
title: Создание компонента времени разработки для пользовательского элемента отчета | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, creating
ms.assetid: 323fd58a-a462-4c48-b188-77ebc0b4212e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b663dc3b0a9c54d1674bf153ee09dd36e0de7a00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654920"
---
# <a name="creating-a-custom-report-item-design-time-component"></a><span data-ttu-id="b8528-102">Создание компонента времени разработки пользовательского элемента отчета</span><span class="sxs-lookup"><span data-stu-id="b8528-102">Creating a Custom Report Item Design-Time Component</span></span>
  <span data-ttu-id="b8528-103">Компонент времени разработки пользовательского элемента отчета ― это элемент управления, который может быть использован в конструкторе отчетов среды Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b8528-103">A custom report item design-time component is a control that can be used in the Visual Studio Report Designer environment.</span></span> <span data-ttu-id="b8528-104">Компонент времени разработки пользовательского элемента отчета предоставляет активную область конструктора, поддерживающую операции перетаскивания, интеграцию с браузером свойств среды [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] и возможность использования пользовательских редакторов свойств.</span><span class="sxs-lookup"><span data-stu-id="b8528-104">The custom report item design-time component provides an activated design surface that can accept drag-and-drop operations, integration with the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] property browser, and the ability to provide custom property editors.</span></span>  
  
 <span data-ttu-id="b8528-105">Благодаря компоненту времени разработки пользователь может расположить пользовательский элемент отчета в отчете в среде конструктора, задать пользовательские свойства данных в элементе отчета и сохранить элемент отчета в виде части проекта отчета.</span><span class="sxs-lookup"><span data-stu-id="b8528-105">With a custom report item design-time component, the user can position a custom report item on a report in the design environment, set custom data properties on the custom report item, and then save the custom report item as part of the report project.</span></span>  
  
 <span data-ttu-id="b8528-106">Свойства, заданные при помощи компонента времени разработки в среде разработки, сериализуются и десериализуются средой проектирования узла и сохраняются в виде элементов в файле на языке определения отчетов (RDL).</span><span class="sxs-lookup"><span data-stu-id="b8528-106">The properties that are set using the design-time component in the development environment are serialized and deserialized by the host design environment and then stored as elements in the Report Definition Language (RDL) file.</span></span> <span data-ttu-id="b8528-107">При выполнении отчета обработчиком отчетов свойства, заданные при помощи компонента времени разработки, передаются компоненту времени выполнения пользовательского элемента отчета, который подготавливает к просмотру пользовательский элемент отчета и возвращает его обратно обработчику отчетов.</span><span class="sxs-lookup"><span data-stu-id="b8528-107">When the report is executed by the report processor, the properties that are set using the design-time component are passed by the report processor to a custom report item run-time component, which renders the custom report item and passes it back to the report processor.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b8528-108">Компонент времени разработки для пользовательского элемента отчета реализуется в виде компонента [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8528-108">The custom report item design-time component is implemented as a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] component.</span></span> <span data-ttu-id="b8528-109">В этом документе приводится описание реализации, характерной для компонента времени разработки пользовательского элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="b8528-109">This document will describe implementation details specific to the custom report item design-time component.</span></span> <span data-ttu-id="b8528-110">Дополнительные сведения о разработке компонентов с использованием платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] см. в разделе [Компоненты в Visual Studio](https://go.microsoft.com/fwlink/?LinkId=116576) библиотеки MSDN.</span><span class="sxs-lookup"><span data-stu-id="b8528-110">For more information about developing components using the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], see [Components in Visual Studio](https://go.microsoft.com/fwlink/?LinkId=116576) in the MSDN library.</span></span>  
  
 <span data-ttu-id="b8528-111">Образец полностью реализованного пользовательского элемента отчета см. на странице [Образцы продуктов служб SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="b8528-111">For a sample of a fully implemented custom report item, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="implementing-a-design-time-component"></a><span data-ttu-id="b8528-112">Реализация компонента времени разработки</span><span class="sxs-lookup"><span data-stu-id="b8528-112">Implementing a Design-Time Component</span></span>  
 <span data-ttu-id="b8528-113">Основной класс компонента времени разработки пользовательского элемента отчета наследуется от класса `Microsoft.ReportDesigner.CustomReportItemDesigner`.</span><span class="sxs-lookup"><span data-stu-id="b8528-113">The main class of a custom report item design-time component is inherited from the `Microsoft.ReportDesigner.CustomReportItemDesigner` class.</span></span> <span data-ttu-id="b8528-114">Помимо стандартных атрибутов, используемых для управления [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], класс компонента также должен определять атрибут `CustomReportItem`.</span><span class="sxs-lookup"><span data-stu-id="b8528-114">In addition to the standard attributes used for a [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] control, your component class should define a `CustomReportItem` attribute.</span></span> <span data-ttu-id="b8528-115">Этот атрибут должен соответствовать имени пользовательского элемента отчета, определенному в файле reportserver.config.</span><span class="sxs-lookup"><span data-stu-id="b8528-115">This attribute must correspond to the name of the custom report item as it is defined in the reportserver.config file.</span></span> <span data-ttu-id="b8528-116">Список атрибутов [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] см. в разделе «Атрибуты» документации по SDK [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8528-116">For a list of [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] attributes, see Attributes in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
 <span data-ttu-id="b8528-117">В следующем образце кода приводятся атрибуты, которые используются компонентом времени разработки пользовательского элемента отчета:</span><span class="sxs-lookup"><span data-stu-id="b8528-117">The following code example shows attributes being applied to a custom report item design-time control:</span></span>  
  
```csharp  
namespace PolygonsCRI  
{  
    [LocalizedName("Polygons")]  
    [Editor(typeof(CustomEditor), typeof(ComponentEditor))]  
        [ToolboxBitmap(typeof(PolygonsDesigner),"Polygons.ico")]  
        [CustomReportItem("Polygons")]  
  
    public class PolygonsDesigner : CustomReportItemDesigner  
    {  
...  
```  
  
### <a name="initializing-the-component"></a><span data-ttu-id="b8528-118">Инициализация компонента</span><span class="sxs-lookup"><span data-stu-id="b8528-118">Initializing the Component</span></span>  
 <span data-ttu-id="b8528-119">Определяемые пользователем свойства передаются пользовательскому элементу отчета при помощи класса <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData>.</span><span class="sxs-lookup"><span data-stu-id="b8528-119">You pass user-specified properties for a custom report item using a <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> class.</span></span> <span data-ttu-id="b8528-120">Реализация класса `CustomReportItemDesigner` должна переопределить метод `InitializeNewComponent`, который создает новый экземпляр класса <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> компонента и назначает ему значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b8528-120">Your implementation of the `CustomReportItemDesigner` class should override the `InitializeNewComponent` method to create a new instance of your component's <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> class and set it to default values.</span></span>  
  
 <span data-ttu-id="b8528-121">В следующем образце кода приводится класс компонента времени разработки пользовательского элемента отчета, переопределяющий метод `CustomReportItemDesigner.InitializeNewComponent`, в котором инициализируется класс <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> компонента:</span><span class="sxs-lookup"><span data-stu-id="b8528-121">The following code example shows an example of a custom report item design-time component class overriding the `CustomReportItemDesigner.InitializeNewComponent` method to initialize the component's <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> class:</span></span>  
  
```csharp  
public override void InitializeNewComponent()  
        {  
            CustomData = new CustomData();  
            CustomData.DataRowHierarchy = new DataHierarchy();  
  
            // Shape grouping  
            CustomData.DataRowHierarchy.DataMembers.Add(new DataMember());  
            CustomData.DataRowHierarchy.DataMembers[0].Group = new Group();  
            CustomData.DataRowHierarchy.DataMembers[0].Group.Name = Name + "_Shape";  
            CustomData.DataRowHierarchy.DataMembers[0].Group.GroupExpressions.Add(new ReportExpression());  
  
            // Point grouping  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers.Add(new DataMember());  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers[0].Group = new Group();  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers[0].Group.Name = Name + "_Point";  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers[0].Group.GroupExpressions.Add(new ReportExpression());  
  
            // Static column  
            CustomData.DataColumnHierarchy = new DataHierarchy();  
            CustomData.DataColumnHierarchy.DataMembers.Add(new DataMember());  
  
            // Points  
            IList<IList<DataValue>> dataValues = new List<IList<DataValue>>();  
            CustomData.DataRows.Add(dataValues);  
            CustomData.DataRows[0].Add(new List<DataValue>());  
            CustomData.DataRows[0][0].Add(NewDataValue("X", ""));  
            CustomData.DataRows[0][0].Add(NewDataValue("Y", ""));  
        }  
```  
  
### <a name="modifying-component-properties"></a><span data-ttu-id="b8528-122">Изменение свойств компонента</span><span class="sxs-lookup"><span data-stu-id="b8528-122">Modifying Component Properties</span></span>  
 <span data-ttu-id="b8528-123">Свойства `CustomData` в конструкторе можно изменить несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="b8528-123">You can modify `CustomData` properties in the design environment in several ways.</span></span> <span data-ttu-id="b8528-124">Любые свойства, предоставляемые компонентом времени разработки и отмеченные атрибутом <xref:System.ComponentModel.BrowsableAttribute>, можно изменить с помощью браузера свойств среды [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8528-124">You can modify any properties that are exposed by the design-time component that are marked with the <xref:System.ComponentModel.BrowsableAttribute> attribute by using the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] property browser.</span></span> <span data-ttu-id="b8528-125">Кроме того, свойства можно изменить, перетащив элементы в область конструктора пользовательского элемента отчета или щелкнув правой кнопкой мыши элемент управления в среде разработки и выбрав в контекстном меню пункт **Свойства** для отображения окна с пользовательскими свойствами.</span><span class="sxs-lookup"><span data-stu-id="b8528-125">In addition, you can modify properties by dragging items onto the custom report item's design surface, or by right-clicking the control in the design environment and selecting **Properties** on the shortcut menu to display a custom properties window.</span></span>  
  
 <span data-ttu-id="b8528-126">В следующем образце кода приводится свойство `Microsoft.ReportDesigner.CustomReportItemDesigner.CustomData`, к которому применен атрибут <xref:System.ComponentModel.BrowsableAttribute>:</span><span class="sxs-lookup"><span data-stu-id="b8528-126">The following code example shows a `Microsoft.ReportDesigner.CustomReportItemDesigner.CustomData` property that has the <xref:System.ComponentModel.BrowsableAttribute> attribute applied:</span></span>  
  
```csharp  
[Browsable(true), Category("Data")]  
public string DataSetName  
{  
      get  
      {  
         return CustomData.DataSetName;  
      }  
      set  
      {  
         CustomData.DataSetName = value;  
      }  
   }  
  
```  
  
 <span data-ttu-id="b8528-127">Компонент времени разработки можно снабдить диалоговым окном для редактирования пользовательских свойств.</span><span class="sxs-lookup"><span data-stu-id="b8528-127">You can provide your design-time component with a custom properties editor dialog box.</span></span> <span data-ttu-id="b8528-128">Реализация редактора пользовательских свойств должна наследовать класс <xref:System.ComponentModel.ComponentEditor> и создать экземпляр диалогового окна, который можно использовать для изменения свойств.</span><span class="sxs-lookup"><span data-stu-id="b8528-128">The custom property editor implementation should inherit from the <xref:System.ComponentModel.ComponentEditor> class, and it should create an instance of a dialog box that can be used for property editing.</span></span>  
  
 <span data-ttu-id="b8528-129">В следующем образце кода показана реализация класса, наследующего <xref:System.ComponentModel.ComponentEditor> и отображающего диалоговое окно редактора пользовательских свойств:</span><span class="sxs-lookup"><span data-stu-id="b8528-129">The following example shows an implementation of a class that inherits from <xref:System.ComponentModel.ComponentEditor> and displays a custom property editor dialog box:</span></span>  
  
```csharp  
internal sealed class CustomEditor : ComponentEditor  
{  
   public override bool EditComponent(  
      ITypeDescriptorContext context, object component)  
    {  
     PolygonsDesigner designer = (PolygonsDesigner)component;  
     PolygonProperties dialog = new PolygonProperties();  
     dialog.m_designerComponent = designer;  
     DialogResult result = dialog.ShowDialog();  
     if (result == DialogResult.OK)  
     {  
        designer.Invalidate();  
        designer.ChangeService().OnComponentChanged(designer, null, null, null);  
        return true;  
     }  
     else  
        return false;  
    }  
}  
```  
  
 <span data-ttu-id="b8528-130">Диалоговое окно редактора пользовательских свойств может вызывать редактор выражений конструктора отчетов.</span><span class="sxs-lookup"><span data-stu-id="b8528-130">Your custom property editor dialog box can invoke the Report Designer Expression Editor.</span></span> <span data-ttu-id="b8528-131">В следующем примере редактор выражений вызывается при выборе пользователем первого элемента в поле со списком:</span><span class="sxs-lookup"><span data-stu-id="b8528-131">In the following example, the Expression Editor is invoked when the user selects the first element in the combo box:</span></span>  
  
```csharp  
private void EditableCombo_SelectedIndexChanged(object sender,   
    EventArgs e)  
{  
   ComboBox combo = (ComboBox)sender;  
   if (combo.SelectedIndex == 0 && m_launchEditor)  
   {  
      m_launchEditor = false;  
      ExpressionEditor editor = new ExpressionEditor();  
      string newValue;  
      newValue = (string)editor.EditValue(null, m_designerComponent.Site, m_oldComboValue);  
      combo.Items[0] = newValue;  
   }  
}  
  
```  
  
### <a name="using-designer-verbs"></a><span data-ttu-id="b8528-132">Использование команд конструктора</span><span class="sxs-lookup"><span data-stu-id="b8528-132">Using Designer Verbs</span></span>  
 <span data-ttu-id="b8528-133">Команда конструктора ― это команда меню, связанная с обработчиком событий.</span><span class="sxs-lookup"><span data-stu-id="b8528-133">A designer verb is a menu command linked to an event handler.</span></span> <span data-ttu-id="b8528-134">Команды конструктора можно добавить в контекстное меню компонента во время использования элемента управления времени выполнения пользовательского элемента отчета в среде конструктора.</span><span class="sxs-lookup"><span data-stu-id="b8528-134">You can add designer verbs that will appear in a component's shortcut menu when your custom report item run-time control is being used in the design environment.</span></span> <span data-ttu-id="b8528-135">Список доступных команд конструктора возвращается из компонента времени выполнения при помощи свойства `Verbs`.</span><span class="sxs-lookup"><span data-stu-id="b8528-135">You can return the list of available designer verbs from your run-time component by using the `Verbs` property.</span></span>  
  
 <span data-ttu-id="b8528-136">В следующем образце кода приводится команда конструктора с добавлением обработчика событий в коллекцию <xref:System.ComponentModel.Design.DesignerVerbCollection>, а также код самого обработчика событий:</span><span class="sxs-lookup"><span data-stu-id="b8528-136">The following code example shows a designer verb and an event handler being added to the <xref:System.ComponentModel.Design.DesignerVerbCollection>, as well as the event handler code:</span></span>  
  
```csharp  
public override DesignerVerbCollection Verbs  
{  
    get  
    {  
        if (m_verbs == null)  
        {  
            m_verbs = new DesignerVerbCollection();  
            m_verbs.Add(new DesignerVerb("Proportional Scaling", new EventHandler(OnProportionalScaling)));  
         m_verbs[0].Checked = (GetCustomProperty("poly:Proportional") == bool.TrueString);  
        }  
  
        return m_verbs;  
    }  
}  
  
private void OnProportionalScaling(object sender, EventArgs e)  
{  
   bool proportional = !  
        (GetCustomProperty("poly:Proportional") == bool.TrueString);  
   m_verbs[0].Checked = proportional;  
   SetCustomProperty("poly:Proportional", proportional.ToString());  
   ChangeService().OnComponentChanged(this, null, null, null);  
   Invalidate();  
}  
```  
  
### <a name="using-adornments"></a><span data-ttu-id="b8528-137">Использование крайних элементов</span><span class="sxs-lookup"><span data-stu-id="b8528-137">Using Adornments</span></span>  
 <span data-ttu-id="b8528-138">Классы пользовательских элементов отчета также реализуют класс `Microsoft.ReportDesigner.Design.Adornment`.</span><span class="sxs-lookup"><span data-stu-id="b8528-138">Custom report item classes can also implement a `Microsoft.ReportDesigner.Design.Adornment` class.</span></span> <span data-ttu-id="b8528-139">Крайний элемент позволяет элементу управления пользовательского элемента отчета иметь области за пределами основного прямоугольника области конструктора.</span><span class="sxs-lookup"><span data-stu-id="b8528-139">An adornment allows the custom report item control to provide areas outside the main rectangle of the design surface.</span></span> <span data-ttu-id="b8528-140">Эти области могут обрабатывать события пользовательского интерфейса, такие как щелчки кнопкой мыши и операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="b8528-140">These areas can handle user interface events, such as mouse clicks and drag-and-drop operations.</span></span> <span data-ttu-id="b8528-141">`Adornment`Класс, определенный в [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] `Microsoft.ReportDesigner` пространстве имен, является сквозной реализацией <xref:System.Windows.Forms.Design.Behavior.Adorner> класса, найденного в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b8528-141">The `Adornment` class that is defined in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] `Microsoft.ReportDesigner` namespace is a pass-through implementation of the <xref:System.Windows.Forms.Design.Behavior.Adorner> class found in Windows Forms.</span></span> <span data-ttu-id="b8528-142">Полную документацию по `Adorner` классу см. в разделе [Общие сведения о службе поведения](https://go.microsoft.com/fwlink/?LinkId=116673) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="b8528-142">For complete documentation on the `Adorner` class, see [Behavior Service Overview](https://go.microsoft.com/fwlink/?LinkId=116673) in the MSDN library.</span></span> <span data-ttu-id="b8528-143">Пример кода, который реализует `Microsoft.ReportDesigner.Design.Adornment` класс, см. в разделе [SQL Server Reporting Services примеров продуктов](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="b8528-143">For sample code that implements a `Microsoft.ReportDesigner.Design.Adornment` class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
 <span data-ttu-id="b8528-144">Дополнительные сведения о программировании и использовании форм Windows Forms в среде [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] см. в следующих разделах библиотеки MSDN:</span><span class="sxs-lookup"><span data-stu-id="b8528-144">For more information about programming and using Windows Forms in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], see these topics in the MSDN Library:</span></span>  
  
-   <span data-ttu-id="b8528-145">Атрибуты времени разработки для компонентов</span><span class="sxs-lookup"><span data-stu-id="b8528-145">Design-Time Attributes for Components</span></span>  
  
-   <span data-ttu-id="b8528-146">Компоненты в среде [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8528-146">Components in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]</span></span>  
  
-   <span data-ttu-id="b8528-147">Пошаговое руководство. Создание элемента управления Windows Forms, использующего функции времени разработки среды Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b8528-147">Walkthrough: Creating a Windows Forms Control that Takes Advantage of Visual Studio Design-Time Features</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8528-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="b8528-148">See Also</span></span>  
 <span data-ttu-id="b8528-149">[Архитектура пользовательского элемента отчета](custom-report-item-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="b8528-149">[Custom Report Item Architecture](custom-report-item-architecture.md) </span></span>  
 <span data-ttu-id="b8528-150">[Создание компонента времени выполнения пользовательского элемента отчета](creating-a-custom-report-item-run-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="b8528-150">[Creating a Custom Report Item Run-Time Component](creating-a-custom-report-item-run-time-component.md) </span></span>  
 <span data-ttu-id="b8528-151">[Библиотеки классов пользовательских элементов отчета](custom-report-item-class-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="b8528-151">[Custom Report Item Class Libraries](custom-report-item-class-libraries.md) </span></span>  
 [<span data-ttu-id="b8528-152">Руководство. развернуть пользовательский элемент отчета</span><span class="sxs-lookup"><span data-stu-id="b8528-152">How to: Deploy a Custom Report Item</span></span>](how-to-deploy-a-custom-report-item.md)  
  
  
