---
title: Разработка пользовательского интерфейса для пользовательской задачи | Документы Майкрософт
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
- custom user interfaces [Integration Services]
- IDtsTaskUI interface
- DtsTaskAttribute attribute
- custom tasks [Integration Services], user interface
- custom user interface [Integration Services], custom tasks
- user interface [Integration Services]
- SSIS custom tasks, user interface
ms.assetid: 1e940cd1-c5f8-4527-b678-e89ba5dc398a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ed96bbc302cba4c207e5ce7b2e4fb4b74fed4ee2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667810"
---
# <a name="developing-a-user-interface-for-a-custom-task"></a><span data-ttu-id="82188-102">Разработка пользовательского интерфейса для пользовательской задачи</span><span class="sxs-lookup"><span data-stu-id="82188-102">Developing a User Interface for a Custom Task</span></span>
  <span data-ttu-id="82188-103">Объектная модель служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] предоставляет разработчикам пользовательских задач удобный способ создания собственного пользовательского интерфейса для задачи, который можно затем интегрировать и вывести в среде [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82188-103">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] object model provides custom task developers the ability to easily create a custom user interface for a task that can then be integrated and displayed in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="82188-104">Пользовательский интерфейс может предоставлять пользователю полезную информацию в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] и помогать пользователям правильно конфигурировать свойства и настройки пользовательской задачи.</span><span class="sxs-lookup"><span data-stu-id="82188-104">The user interface can provide helpful information to the user in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, and guide users to correctly configure the properties and settings of the custom task.</span></span>  
  
 <span data-ttu-id="82188-105">Разработка собственного пользовательского интерфейса задачи требует использования двух важных классов.</span><span class="sxs-lookup"><span data-stu-id="82188-105">Developing a custom user interface for a task involves using two important classes.</span></span> <span data-ttu-id="82188-106">Эти классы описываются в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="82188-106">The following table describes those classes.</span></span>  
  
|<span data-ttu-id="82188-107">Class</span><span class="sxs-lookup"><span data-stu-id="82188-107">Class</span></span>|<span data-ttu-id="82188-108">Description</span><span class="sxs-lookup"><span data-stu-id="82188-108">Description</span></span>|  
|-----------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>|<span data-ttu-id="82188-109">Атрибут, который идентифицирует управляемую задачу и предоставляет через свои свойства информацию времени разработки, определяющую, каким образом конструктор служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] выводит объект и взаимодействует с ним.</span><span class="sxs-lookup"><span data-stu-id="82188-109">An attribute that identifies a managed task, and supplies design-time information through its properties to control how [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer displays and interacts with the object.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI>|<span data-ttu-id="82188-110">Интерфейс, используемый задачей для того, чтобы связать ее с собственным пользовательским интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="82188-110">An interface used by the task to associate the task with its custom user interface.</span></span>|  
  
 <span data-ttu-id="82188-111">В данном разделе описывается роль атрибута <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> и интерфейса <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> при разработке пользовательского интерфейса для пользовательской задачи и предоставляются подробные сведения о создании, интеграции, развертывании и отладке задачи в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82188-111">This section describes the role of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute and the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface when you are developing a user interface for a custom task, and provides details about how to create, integrate, deploy, and debug the task within [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="82188-112">Конструктор служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] предоставляет несколько точек входа в пользовательский интерфейс данной задачи: пользователь может выбрать пункт **Изменить** в контекстном меню, дважды щелкнуть задачу или щелкнуть ссылку **Показать редактор** в нижней части страницы свойств.</span><span class="sxs-lookup"><span data-stu-id="82188-112">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer provides multiple entry points to the user interface for the task: the user can select **Edit** on the shortcut menu, double-click the task, or click the **Show Editor** link at the bottom of the property sheet.</span></span> <span data-ttu-id="82188-113">Когда пользователь получает доступ к одной из этих точек входа, конструктор служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] находит и загружает сборку, содержащую пользовательский интерфейс для соответствующей задачи.</span><span class="sxs-lookup"><span data-stu-id="82188-113">When the user accesses one of these entry points, [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer locates and loads the assembly that contains the user interface for the task.</span></span> <span data-ttu-id="82188-114">Пользовательский интерфейс задачи отвечает за создание диалогового окна свойств, которое выводится для пользователя в среде разработки [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82188-114">The user interface for the task is responsible for creating the properties dialog box that is displayed to the user in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="82188-115">Задача и ее пользовательский интерфейс представляют собой отдельные сущности.</span><span class="sxs-lookup"><span data-stu-id="82188-115">A task and its user interface are separate entities.</span></span> <span data-ttu-id="82188-116">Их нужно реализовать в отдельных сборках, чтобы уменьшить объем работы по локализации, развертыванию и поддержке.</span><span class="sxs-lookup"><span data-stu-id="82188-116">They should be implemented in separate assemblies to reduce localization, deployment, and maintenance work.</span></span> <span data-ttu-id="82188-117">Динамическая библиотека задачи не загружает и не вызывает свой пользовательский интерфейс и вообще ничего о нем не знает, за исключением информации, содержащейся в значениях атрибутов объектов <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>, создаваемых в коде задачи.</span><span class="sxs-lookup"><span data-stu-id="82188-117">The task DLL does not load, call, or generally contain any knowledge of its user interface, except for the information that is contained in the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute values coded in the task.</span></span> <span data-ttu-id="82188-118">Это единственная связь между задачей и ее пользовательским интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="82188-118">This is the only way that a task and its user interface are associated.</span></span>  
  
## <a name="the-dtstask-attribute"></a><span data-ttu-id="82188-119">Атрибут DtsTask</span><span class="sxs-lookup"><span data-stu-id="82188-119">The DtsTask Attribute</span></span>  
 <span data-ttu-id="82188-120">Атрибут <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> включается в код класса задачи, чтобы связать задачу с ее пользовательским интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="82188-120">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute is included in the task class code to associate a task with its user interface.</span></span> <span data-ttu-id="82188-121">Конструктор служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] использует свойства атрибута, чтобы определить, каким образом показывать задачу в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="82188-121">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses the properties of the attribute to determine how to display the task in the designer.</span></span> <span data-ttu-id="82188-122">Свойства включают в себя имя задачи для вывода и значок задачи, если он есть.</span><span class="sxs-lookup"><span data-stu-id="82188-122">These properties include the name to display and the icon, if any.</span></span>  
  
 <span data-ttu-id="82188-123">В следующей таблице приводится описание свойств атрибута <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>.</span><span class="sxs-lookup"><span data-stu-id="82188-123">The following table describes the properties of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute.</span></span>  
  
|<span data-ttu-id="82188-124">Свойство</span><span class="sxs-lookup"><span data-stu-id="82188-124">Property</span></span>|<span data-ttu-id="82188-125">Description</span><span class="sxs-lookup"><span data-stu-id="82188-125">Description</span></span>|  
|--------------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.DisplayName%2A>|<span data-ttu-id="82188-126">Выводит имя задачи в области элементов потока управления.</span><span class="sxs-lookup"><span data-stu-id="82188-126">Displays the task name in the Control Flow toolbox.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.Description%2A>|<span data-ttu-id="82188-127">Описание задачи (наследуется от <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute>).</span><span class="sxs-lookup"><span data-stu-id="82188-127">The task description (inherited from <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute>).</span></span> <span data-ttu-id="82188-128">Это свойство показывается во всплывающей подсказке.</span><span class="sxs-lookup"><span data-stu-id="82188-128">This property is shown in ToolTips.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A>|<span data-ttu-id="82188-129">Значок выводится в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82188-129">The icon displayed in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.RequiredProductLevel%2A>|<span data-ttu-id="82188-130">Если это свойство используется, нужно задать для него одно из значений перечисления <xref:Microsoft.SqlServer.Dts.Runtime.DTSProductLevel>.</span><span class="sxs-lookup"><span data-stu-id="82188-130">If used, set it to one of the values in the <xref:Microsoft.SqlServer.Dts.Runtime.DTSProductLevel> enumeration.</span></span> <span data-ttu-id="82188-131">Например, `RequiredProductLevel = DTSProductLevel.None`.</span><span class="sxs-lookup"><span data-stu-id="82188-131">For example, `RequiredProductLevel = DTSProductLevel.None`.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.TaskContact%2A>|<span data-ttu-id="82188-132">Хранит контактную информацию на случай, если работа задачи потребует технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="82188-132">Holds contact information for occasions when the task requires technical support.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.TaskType%2A>|<span data-ttu-id="82188-133">Присваивает задаче тип.</span><span class="sxs-lookup"><span data-stu-id="82188-133">Assigns a type to the task.</span></span>|  
|<span data-ttu-id="82188-134">Attribute.TypeId</span><span class="sxs-lookup"><span data-stu-id="82188-134">Attribute.TypeId</span></span>|<span data-ttu-id="82188-135">Возвращает уникальный идентификатор для этого атрибута при реализации в производном классе.</span><span class="sxs-lookup"><span data-stu-id="82188-135">When implemented in a derived class, gets a unique identifier for this Attribute.</span></span> <span data-ttu-id="82188-136">Дополнительные сведения см. в разделе, посвященном свойству `Attribute.TypeID` документации по библиотеке классов платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="82188-136">For more information, see `Attribute.TypeID` property in the .NET Framework Class Library.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A>|<span data-ttu-id="82188-137">Имя типа сборки, используемое конструктором служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] для загрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="82188-137">The type name of the assembly that is used by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer to load the assembly.</span></span> <span data-ttu-id="82188-138">Это свойство используется для поиска сборки пользовательского интерфейса данной задачи.</span><span class="sxs-lookup"><span data-stu-id="82188-138">This property is used to find the user interface assembly for the task.</span></span>|  
  
 <span data-ttu-id="82188-139">В следующем примере кода показан код атрибута <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>, расположенный выше определения класса.</span><span class="sxs-lookup"><span data-stu-id="82188-139">The following code example shows the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> as it would look, coded above the class definition.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
namespace Microsoft.SSIS.Samples  
{  
  [DtsTask  
  (  
   DisplayName = "MyTask",  
   IconResource = "MyTask.MyTaskIcon.ico",  
   UITypeName = "My Custom Task," +  
   "Version=1.0.0.0," +  
   "Culture = Neutral," +  
   "PublicKeyToken = 12345abc6789de01",  
   TaskType = "PackageMaintenance",  
   TaskContact = "MyTask; company name; any other information",  
   RequiredProductLevel = DTSProductLevel.None  
   )]  
  public class MyTask : Task  
  {  
    // Your code here.  
  }  
}  
```  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
  
<DtsTask(DisplayName:="MyTask", _  
 IconResource:="MyTask.MyTaskIcon.ico", _  
 UITypeName:="My Custom Task," & _  
 "Version=1.0.0.0,Culture=Neutral," & _  
 "PublicKeyToken=12345abc6789de01", _  
 TaskType:="PackageMaintenance", _  
 TaskContact:="MyTask; company name; any other information", _  
 RequiredProductLevel:=DTSProductLevel.None)> _  
Public Class MyTask  
  Inherits Task  
  
  ' Your code here.  
  
End Class 'MyTask  
```  
  
 <span data-ttu-id="82188-140">Конструктор служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] использует свойство <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> этого атрибута, которое включает в себя имя сборки, имя типа, значения токенов версии, языка, культуры, а также открытого ключа для поиска сборки в глобальном кэше сборок (GAC) и ее загрузки для использования в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="82188-140">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> property of the attribute that includes the assembly name, type name, version, culture, and public key token, to locate the assembly in the Global Assembly Cache (GAC) and load it for use by the designer.</span></span>  
  
 <span data-ttu-id="82188-141">Когда сборка найдена, конструктор служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] использует другие свойства атрибута для вывода дополнительной информации о задаче в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] — например, имени, значка и описания задачи.</span><span class="sxs-lookup"><span data-stu-id="82188-141">After the assembly has been located, [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses the other properties in the attribute to display additional information about the task in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, such as the name, icon, and description of the task.</span></span>  
  
 <span data-ttu-id="82188-142">Свойства <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.DisplayName%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.Description%2A> и <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> указывают, как задача представляется пользователю.</span><span class="sxs-lookup"><span data-stu-id="82188-142">The <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.DisplayName%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.Description%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> properties specify how the task is presented to the user.</span></span> <span data-ttu-id="82188-143">Свойство <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> содержит идентификатор ресурса значка, внедренного в сборку пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="82188-143">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> property contains the resource ID of the icon embedded in the user interface assembly.</span></span> <span data-ttu-id="82188-144">Конструктор загружает ресурс значка по идентификатору из сборки и выводит его рядом с именем задачи в области элементов и в области конструктора, когда задача добавлена к пакету.</span><span class="sxs-lookup"><span data-stu-id="82188-144">The designer loads the icon resource by ID from the assembly, and displays it next to the task name in the toolbox and on the designer surface when the task is added to a package.</span></span> <span data-ttu-id="82188-145">Если задача не предоставляет ресурс значка, конструктор использует для нее значок по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="82188-145">If a task does not provide an icon resource, the designer uses a default icon for the task.</span></span>  
  
## <a name="the-idtstaskui-interface"></a><span data-ttu-id="82188-146">Интерфейс IDTSTaskUI</span><span class="sxs-lookup"><span data-stu-id="82188-146">The IDTSTaskUI Interface</span></span>  
 <span data-ttu-id="82188-147">Интерфейс <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> определяет коллекцию методов и свойств, вызываемых конструктором служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] для инициализации и вывода пользовательского интерфейса, связанного с данной задачей.</span><span class="sxs-lookup"><span data-stu-id="82188-147">The <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface defines the collection of methods and properties called by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer to initialize and display the user interface associated with the task.</span></span> <span data-ttu-id="82188-148">При вызове пользовательского интерфейса задачи конструктор вызывает метод <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.Initialize%2A>, реализованный в пользовательском интерфейсе задачи во время разработки, а затем передает коллекции <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> и <xref:Microsoft.SqlServer.Dts.Runtime.Connections> задачи и пакета соответственно в качестве параметров.</span><span class="sxs-lookup"><span data-stu-id="82188-148">When the user interface for a task is invoked, the designer calls the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.Initialize%2A> method, implemented by the task user interface when you wrote it, and then provides the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> and <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collections of the task and package, respectively, as parameters.</span></span> <span data-ttu-id="82188-149">Коллекции хранятся локально и последовательно используются методом <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A>.</span><span class="sxs-lookup"><span data-stu-id="82188-149">These collections are stored locally, and used subsequently in the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> method.</span></span>  
  
 <span data-ttu-id="82188-150">Конструктор служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] вызывает метод <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A>, чтобы запросить окно, выводимое в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="82188-150">The designer calls the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> method to request the window that is displayed in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="82188-151">Задача создает экземпляр окна, содержащего пользовательский интерфейс задачи, и возвращает пользовательский интерфейс конструктору для вывода.</span><span class="sxs-lookup"><span data-stu-id="82188-151">The task creates an instance of the window that contains the user interface for the task, and returns the user interface to the designer for display.</span></span> <span data-ttu-id="82188-152">Обычно окну через перегруженный конструктор предоставляются объекты <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> и <xref:Microsoft.SqlServer.Dts.Runtime.Connections>, чтобы их можно было использовать для настройки задачи.</span><span class="sxs-lookup"><span data-stu-id="82188-152">Typically, the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> and <xref:Microsoft.SqlServer.Dts.Runtime.Connections> objects are provided to the window through an overloaded constructor so they can be used to configure the task.</span></span>  
  
 <span data-ttu-id="82188-153">Конструктор служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] вызывает метод <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> пользовательского интерфейса задачи, чтобы вывести пользовательский интерфейс данной задачи.</span><span class="sxs-lookup"><span data-stu-id="82188-153">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer calls the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> method of the task UI to display the user interface for the task.</span></span> <span data-ttu-id="82188-154">Пользовательский интерфейс задачи возвращает после вызова данного метода форму Windows, и конструктор служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] выводит эту форму как модальное диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="82188-154">The task user interface returns the Windows form from this method, and [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer shows this form as a modal dialog box.</span></span> <span data-ttu-id="82188-155">После закрытия формы конструктор служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] исследует значение свойства `DialogResult` формы, чтобы определить, была ли задача изменена и следует ли сохранить эти изменения.</span><span class="sxs-lookup"><span data-stu-id="82188-155">When the form is closed, [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer examines the value of the `DialogResult` property of the form to determine whether the task has been modified and if these modifications should be saved.</span></span> <span data-ttu-id="82188-156">Если значение свойства `DialogResult` равно `OK`, конструктор служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] вызывает методы сохранения задачи, чтобы сохранить изменения; в противном случае изменения отменяются.</span><span class="sxs-lookup"><span data-stu-id="82188-156">If the value of the `DialogResult` property is `OK`, the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer calls the persistence methods of the task to save the changes; otherwise, the changes are discarded.</span></span>  
  
 <span data-ttu-id="82188-157">В приведенном образце кода реализован интерфейс <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI>. Предполагается существование класса форм Windows с именем SampleTaskForm.</span><span class="sxs-lookup"><span data-stu-id="82188-157">The following code sample implements the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface, and assumes the existence of a Windows form class named SampleTaskForm.</span></span>  
  
```csharp  
using System;  
using System.Windows.Forms;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Runtime.Design;  
  
namespace Sample  
{  
   public class HelloWorldTaskUI : IDtsTaskUI  
   {  
      TaskHost   taskHost;  
      Connections connections;  
      public void Initialize(TaskHost taskHost, IServiceProvider serviceProvider)  
      {  
         this.taskHost = taskHost;  
         IDtsConnectionService cs = serviceProvider.GetService  
         ( typeof( IDtsConnectionService ) ) as   IDtsConnectionService;   
         this.connections = cs.GetConnections();  
      }  
      public ContainerControl GetView()  
      {  
        return new HelloWorldTaskForm(this.taskHost, this.connections);  
      }  
     public void Delete(IWin32Window parentWindow)  
     {  
     }  
     public void New(IWin32Window parentWindow)  
     {  
     }  
   }  
}  
```  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Runtime.Design  
Imports System.Windows.Forms  
  
Public Class HelloWorldTaskUI  
  Implements IDtsTaskUI  
  
  Dim taskHost As TaskHost  
  Dim connections As Connections  
  
  Public Sub Initialize(ByVal taskHost As TaskHost, ByVal serviceProvider As IServiceProvider) _  
    Implements IDtsTaskUI.Initialize  
  
    Dim cs As IDtsConnectionService  
  
    Me.taskHost = taskHost  
    cs = DirectCast(serviceProvider.GetService(GetType(IDtsConnectionService)), IDtsConnectionService)  
    Me.connections = cs.GetConnections()  
  
  End Sub  
  
  Public Function GetView() As ContainerControl _  
    Implements IDtsTaskUI.GetView  
  
    Return New HelloWorldTaskForm(Me.taskHost, Me.connections)  
  
  End Function  
  
  Public Sub Delete(ByVal parentWindow As IWin32Window) _  
    Implements IDtsTaskUI.Delete  
  
  End Sub  
  
  Public Sub [New](ByVal parentWindow As IWin32Window) _  
    Implements IDtsTaskUI.[New]  
  
  End Sub  
  
End Class  
```  
  
<span data-ttu-id="82188-158">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="82188-158">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="82188-159">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="82188-159">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="82188-160">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="82188-160">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="82188-161">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="82188-161">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82188-162">См. также:</span><span class="sxs-lookup"><span data-stu-id="82188-162">See Also</span></span>  
 <span data-ttu-id="82188-163">[Создание пользовательской задачи](creating-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="82188-163">[Creating a Custom Task](creating-a-custom-task.md) </span></span>  
 <span data-ttu-id="82188-164">[Создание кода пользовательской задачи](coding-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="82188-164">[Coding a Custom Task](coding-a-custom-task.md) </span></span>  
 [<span data-ttu-id="82188-165">Разработка пользовательского интерфейса для пользовательской задачи</span><span class="sxs-lookup"><span data-stu-id="82188-165">Developing a User Interface for a Custom Task</span></span>](developing-a-user-interface-for-a-custom-task.md)  
  
  
