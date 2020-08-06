---
title: Библиотеки классов пользовательского элемента отчета | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, RDL
- RDL [Reporting Services], custom report items
ms.assetid: f18c5d8f-1d6b-4f0b-8657-c14896c2ce0d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 60f8cf912eb6ff3f5080e9cf757df40f37e65079
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654918"
---
# <a name="custom-report-item-class-libraries"></a><span data-ttu-id="bd9cf-102">Библиотеки классов пользовательского элемента отчета</span><span class="sxs-lookup"><span data-stu-id="bd9cf-102">Custom Report Item Class Libraries</span></span>
  <span data-ttu-id="bd9cf-103">В пользовательских элементах отчетов используются классы из пространства имен `Microsoft.ReportDesigner`.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-103">Custom report items use classes from the `Microsoft.ReportDesigner` namespace.</span></span> <span data-ttu-id="bd9cf-104">Классы, используемые для реализации пользовательского элемента отчета, можно разделить на две основные группы: уникальные классы, созданные для поддержки инфраструктуры пользовательских элементов отчетов, и управляемые классы-оболочки, инкапсулирующие функциональные возможности соответствующих элементов языка определения отчетов.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-104">The classes used to implement a custom report item can be grouped into two main categories: unique classes designed to support custom report item infrastructure, and managed wrapper classes that encapsulate the functionality of relevant Report Definition Language (RDL) elements.</span></span> <span data-ttu-id="bd9cf-105">Образец кода для использования этих классов см. на странице [Образцы продуктов служб SQL Server Reporting](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="bd9cf-105">For a code sample on how to use these classes, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="custom-report-item-infrastructure-classes"></a><span data-ttu-id="bd9cf-106">Классы инфраструктуры пользовательского элемента отчета</span><span class="sxs-lookup"><span data-stu-id="bd9cf-106">Custom Report Item Infrastructure Classes</span></span>  
 <span data-ttu-id="bd9cf-107">Для реализации пользовательского элемента отчета используются следующие классы.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-107">The following classes are used to implement a custom report item.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd9cf-108">Приводимые далее в таблицах списки неполны; в них перечислены только наиболее часто используемые методы и свойства для каждого класса.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-108">The following tables are not complete listings; they include only the most commonly used properties and methods for each class.</span></span>  
  
### <a name="microsoftreportdesignercustomreportitemdesigner"></a><span data-ttu-id="bd9cf-109">Microsoft.ReportDesigner.CustomReportItemDesigner</span><span class="sxs-lookup"><span data-stu-id="bd9cf-109">Microsoft.ReportDesigner.CustomReportItemDesigner</span></span>  
 <span data-ttu-id="bd9cf-110">Это главный класс пользовательского элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-110">This is the main custom report item class.</span></span> <span data-ttu-id="bd9cf-111">Главный класс реализации пользовательского элемента отчета должен быть производным от этого класса.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-111">The main class of your custom report item implementation must inherit from this class.</span></span>  
  
#### <a name="public-properties"></a><span data-ttu-id="bd9cf-112">Открытые свойства</span><span class="sxs-lookup"><span data-stu-id="bd9cf-112">Public Properties</span></span>  
  
|||  
|-|-|  
|`Name`|<span data-ttu-id="bd9cf-113">Имя пользовательского элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-113">The name of the custom report item.</span></span>|  
|`Type`|<span data-ttu-id="bd9cf-114">Тип пользовательского элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-114">The type of the custom report item.</span></span>|  
|`CustomData`|<span data-ttu-id="bd9cf-115">Объект <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData>, инкапсулирующий свойства данных пользовательского элемента отчета, заданные во время разработки.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-115">A <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> object that encapsulates the custom report item data properties specified at design time.</span></span>|  
|`CustomProperties`|<span data-ttu-id="bd9cf-116">Коллекция пользовательских свойств пользовательского элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-116">A collection of custom properties for the custom report item.</span></span>|  
|`Height`|<span data-ttu-id="bd9cf-117">Высота элемента управления пользовательского элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-117">The height of the custom report item control.</span></span>|  
|`Width`|<span data-ttu-id="bd9cf-118">Ширина элемента управления пользовательского элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-118">The width of the custom report item control.</span></span>|  
|`Report`|<span data-ttu-id="bd9cf-119">Контейнер для свойств уровня отчета, таких как список наборов данных отчета.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-119">A container for the report-level properties, such as the list of datasets in the report.</span></span>|  
|`AltReportItem`|<span data-ttu-id="bd9cf-120">Альтернативный объект — элемент отчета, который будет использоваться там, где не поддерживается элемент управления времени выполнения для пользовательского элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-120">The alternate report item object, to be used where the custom report item run-time control is not supported.</span></span>|  
|`Style`|<span data-ttu-id="bd9cf-121">Свойства стиля для пользовательского элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-121">The style properties for the custom report item.</span></span>|  
|`Adornment`|<span data-ttu-id="bd9cf-122">Окно дополнения, используемое для интерактивного редактирования элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-122">An adornment window used for interactive editing of the control.</span></span>|  
|`Site`|<span data-ttu-id="bd9cf-123">`ISite` компонента.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-123">The `ISite` of the component.</span></span>|  
|`DesignerVerbCollection`|<span data-ttu-id="bd9cf-124">Набор пользовательских команд, доступных через контекстное меню элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-124">An array of custom verbs for the control's shortcut menu.</span></span>|  
  
#### <a name="public-methods"></a><span data-ttu-id="bd9cf-125">Открытые методы</span><span class="sxs-lookup"><span data-stu-id="bd9cf-125">Public Methods</span></span>  
  
|||  
|-|-|  
|`BeginEdit`|<span data-ttu-id="bd9cf-126">Активизирует интерактивное редактирование элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-126">Activates interactive editing for the control.</span></span>|  
|`DoDefaultAction`|<span data-ttu-id="bd9cf-127">Вызывается двойным щелчком или нажатием клавиши ВВОД в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-127">Called in response to double-clicking or pressing Return on the control.</span></span>|  
|`EndEdit`|<span data-ttu-id="bd9cf-128">Деактивирует интерактивное редактирование элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-128">Deactivates interactive editing for the control.</span></span>|  
|`GetService`|<span data-ttu-id="bd9cf-129">Возвращает объект, представляющий собой службу.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-129">Returns an object which represents a service.</span></span>|  
|`InitializeNewComponent`|<span data-ttu-id="bd9cf-130">Вызывается при создании нового пользовательского элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-130">Called when a new custom report item is created.</span></span>|  
|`Invalidate`|<span data-ttu-id="bd9cf-131">Перерисовывает всю область элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-131">Repaints the entire surface of the control.</span></span>|  
|`OnDragEnter`<br /><br /> `OnDragDrop`|<span data-ttu-id="bd9cf-132">Вызывается при перетаскивании объекта на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-132">Called when an object is dragged onto the control.</span></span>|  
|`OnPaint`|<span data-ttu-id="bd9cf-133">Вызывается в ответ на событие `Paint`.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-133">Called in response to the `Paint` event.</span></span>|  
  
### <a name="microsoftreportdesignercustomreportitemattribute"></a><span data-ttu-id="bd9cf-134">Microsoft.ReportDesigner.CustomReportItemAttribute</span><span class="sxs-lookup"><span data-stu-id="bd9cf-134">Microsoft.ReportDesigner.CustomReportItemAttribute</span></span>  
 <span data-ttu-id="bd9cf-135">Атрибут используется для выяснения типа пользовательского элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-135">This is the attribute used to identify the type of the custom report item.</span></span> <span data-ttu-id="bd9cf-136">Имя должно соответствовать значению `Name` атрибута <> `ReportItem` элемента в файле конфигурации конструктор отчетов.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-136">The name must match the value of the <`Name`> attribute of the `ReportItem` element in the Report Designer configuration file.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="bd9cf-137">Открытые методы</span><span class="sxs-lookup"><span data-stu-id="bd9cf-137">Public Methods</span></span>  
  
|||  
|-|-|  
|`CustomReportItemAttribute`|<span data-ttu-id="bd9cf-138">Создает объект CustomReportItemAttribute.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-138">Constructs the CustomReportItemAttribute object.</span></span>|  
  
### <a name="microsoftreportdesignerlocalizednameattribute"></a><span data-ttu-id="bd9cf-139">Microsoft.ReportDesigner.LocalizedNameAttribute</span><span class="sxs-lookup"><span data-stu-id="bd9cf-139">Microsoft.ReportDesigner.LocalizedNameAttribute</span></span>  
 <span data-ttu-id="bd9cf-140">Этот атрибут позволяет указать отображаемое имя, предназначенное для конструктора пользовательского элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-140">This is the attribute used to specify display name to use for the custom report item designer.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="bd9cf-141">Открытые методы</span><span class="sxs-lookup"><span data-stu-id="bd9cf-141">Public Methods</span></span>  
  
|||  
|-|-|  
|`LocalizedNameAttribute`|<span data-ttu-id="bd9cf-142">Создает объект LocalizedNameAttribute.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-142">Constructs the LocalizedNameAttribute object.</span></span>|  
  
### <a name="microsoftreportdesigneradornment"></a><span data-ttu-id="bd9cf-143">Microsoft.ReportDesigner.Adornment</span><span class="sxs-lookup"><span data-stu-id="bd9cf-143">Microsoft.ReportDesigner.Adornment</span></span>  
 <span data-ttu-id="bd9cf-144">Класс `Adornment` используется компонентом времени разработки пользовательского элемента отчета для предоставления областей за пределами основного прямоугольника области конструктора.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-144">The `Adornment` class is used by the custom report item design-time component to provide areas outside of the main rectangle of the design surface.</span></span> <span data-ttu-id="bd9cf-145">Эти области могут обрабатывать события пользовательского интерфейса, такие как щелчки кнопкой мыши и операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-145">These areas can handle user interface events, such as mouse clicks and drag-and-drop operations.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="bd9cf-146">Открытые методы</span><span class="sxs-lookup"><span data-stu-id="bd9cf-146">Public Methods</span></span>  
  
|||  
|-|-|  
|`OnShow`|<span data-ttu-id="bd9cf-147">Вызывается при активации объекта `Adornment`.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-147">Called when the `Adornment` is activated.</span></span>|  
|`OnHide`|<span data-ttu-id="bd9cf-148">Вызывается при деактивации объекта `Adornment`.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-148">Called when the `Adornment` is deactivated.</span></span>|  
|`Paint`|<span data-ttu-id="bd9cf-149">Вызывается в ответ на событие `Paint`.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-149">Called in response to the `Paint` event.</span></span>|  
|`OnDragEnter`<br /><br /> `OnDragOver`<br /><br /> `OnDragLeave`<br /><br /> `OnDragDrop`|<span data-ttu-id="bd9cf-150">Вызывается при перетаскивании объекта на элемент управления `Adornment`.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-150">Called when an object is dragged into the `Adornment`.</span></span>|  
  
### <a name="microsoftreportdesigneradornerservice"></a><span data-ttu-id="bd9cf-151">Microsoft.ReportDesigner.AdornerService</span><span class="sxs-lookup"><span data-stu-id="bd9cf-151">Microsoft.ReportDesigner.AdornerService</span></span>  
 <span data-ttu-id="bd9cf-152">Этот класс используется для предоставления коллекции служб отображения, используемых пользовательским элементом отчета для поддержки объектов `Adornment` для компонента времени разработки пользовательского элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-152">This class is used to provide a collection of display services used by the custom report item to support `Adornment` objects for the custom report item design-time component.</span></span>  
  
#### <a name="public-properties"></a><span data-ttu-id="bd9cf-153">Открытые свойства</span><span class="sxs-lookup"><span data-stu-id="bd9cf-153">Public Properties</span></span>  
  
|||  
|-|-|  
|`AdornerWindowBounds`|<span data-ttu-id="bd9cf-154">Границы окна Adorner.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-154">The bounds of the Adorner window.</span></span>|  
|`AdornerWindowRegion`|<span data-ttu-id="bd9cf-155">Область окна Adorner.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-155">The region of the Adorner window.</span></span>|  
|`AdornerWindowGraphics`|<span data-ttu-id="bd9cf-156">Графический контекст окна Adorner.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-156">A graphics context for the Adorner window.</span></span>|  
  
#### <a name="public-methods"></a><span data-ttu-id="bd9cf-157">Открытые методы</span><span class="sxs-lookup"><span data-stu-id="bd9cf-157">Public Methods</span></span>  
  
|||  
|-|-|  
|`ComponentRectInDesignerFrame`|<span data-ttu-id="bd9cf-158">Возвращает границы компонента, преобразованные в координаты экрана конструктора.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-158">Returns the bounds of the component translated into designer frame coordinates.</span></span>|  
|`InvalidateAdorner`|<span data-ttu-id="bd9cf-159">Делает недействительным окно Adorner.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-159">Invalidates the Adorner window.</span></span>|  
|`PointToAdorner`|<span data-ttu-id="bd9cf-160">Возвращает точку в экранных координатах, преобразованных в координаты окна Adorner.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-160">Returns a point in screen coordinates translated to Adorner window coordinates.</span></span>|  
  
### <a name="microsoftreportdesignerexpressioneditor"></a><span data-ttu-id="bd9cf-161">Microsoft.ReportDesigner.ExpressionEditor</span><span class="sxs-lookup"><span data-stu-id="bd9cf-161">Microsoft.ReportDesigner.ExpressionEditor</span></span>  
 <span data-ttu-id="bd9cf-162">Этот класс можно использовать из элемента управления времени разработки пользовательского элемента отчета для вызова редактора выражений.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-162">This class can be used from your custom report item design-time control to invoke the Expression Editor.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="bd9cf-163">Открытые методы</span><span class="sxs-lookup"><span data-stu-id="bd9cf-163">Public Methods</span></span>  
  
|||  
|-|-|  
|`EditValue`|<span data-ttu-id="bd9cf-164">Вызывает редактор выражений, инициализированный значением данного объекта.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-164">Invokes the Expression Editor, initialized with the given object value.</span></span>|  
  
### <a name="microsoftreportdesignerifieldsdataobject"></a><span data-ttu-id="bd9cf-165">Microsoft.ReportDesigner.IFieldsDataObject</span><span class="sxs-lookup"><span data-stu-id="bd9cf-165">Microsoft.ReportDesigner.IFieldsDataObject</span></span>  
 <span data-ttu-id="bd9cf-166">Этот класс представляет собой коллекцию полей служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] и используется для поддержки событий перетаскивания в среде разработки.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-166">This class is a collection of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] fields, and is used to support drag-and-drop events in the design environment.</span></span> <span data-ttu-id="bd9cf-167">Наследует от `IReportItemDataObject`.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-167">Inherits from `IReportItemDataObject`.</span></span>  
  
#### <a name="public-properties"></a><span data-ttu-id="bd9cf-168">Открытые свойства</span><span class="sxs-lookup"><span data-stu-id="bd9cf-168">Public Properties</span></span>  
  
|||  
|-|-|  
|`DataSetName`|<span data-ttu-id="bd9cf-169">Имя набора данных, содержащего поля, которые предназначены для перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-169">The name of the dataset containing the fields to be dropped.</span></span>|  
|`Fields`|<span data-ttu-id="bd9cf-170">Коллекция полей (`Microsoft.ReportDesigner.Field`), которые предназначены для перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="bd9cf-170">The collection of fields (`Microsoft.ReportDesigner.Field`) to be dropped.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd9cf-171">См. также:</span><span class="sxs-lookup"><span data-stu-id="bd9cf-171">See Also</span></span>  
 <span data-ttu-id="bd9cf-172">[Язык определения отчетов &#40;службы SSRS&#41;](../reports/report-definition-language-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bd9cf-172">[Report Definition Language &#40;SSRS&#41;](../reports/report-definition-language-ssrs.md) </span></span>  
 <span data-ttu-id="bd9cf-173">[Создание компонента времени выполнения пользовательского элемента отчета](creating-a-custom-report-item-run-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="bd9cf-173">[Creating a Custom Report Item Run-Time Component](creating-a-custom-report-item-run-time-component.md) </span></span>  
 [<span data-ttu-id="bd9cf-174">Создание компонента времени разработки пользовательского элемента отчета</span><span class="sxs-lookup"><span data-stu-id="bd9cf-174">Creating a Custom Report Item Design-Time Component</span></span>](creating-a-custom-report-item-design-time-component.md)  
  
  
