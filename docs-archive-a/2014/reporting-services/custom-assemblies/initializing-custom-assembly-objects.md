---
title: Инициализация объектов пользовательских сборок | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- initializing custom assemblies [Reporting Services]
- custom assemblies [Reporting Services], initializing
- OnInit method
ms.assetid: 26fd74dc-d02f-40f7-aeb3-50ce05e9e6b9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2aba0bd8b71b26651067a2370728dcdff521ceaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664012"
---
# <a name="initializing-custom-assembly-objects"></a><span data-ttu-id="96458-102">Инициализация объектов пользовательских сборок</span><span class="sxs-lookup"><span data-stu-id="96458-102">Initializing Custom Assembly Objects</span></span>
  <span data-ttu-id="96458-103">В некоторых случаях может понадобиться инициализировать значения свойств и полей в классах пользовательских сборок при создании их экземпляров.</span><span class="sxs-lookup"><span data-stu-id="96458-103">In some cases, you may need to initialize property and field values in your custom assembly classes when you instantiate them.</span></span> <span data-ttu-id="96458-104">Вероятнее всего, понадобится инициализировать пользовательские классы значениями, доступными из коллекции глобальных объектов отчета.</span><span class="sxs-lookup"><span data-stu-id="96458-104">You will most likely need to initialize your custom classes with values available to you from the report's global object collections.</span></span> <span data-ttu-id="96458-105">Это выполняется переопределением метода **OnInit** объекта **Code** отчета.</span><span class="sxs-lookup"><span data-stu-id="96458-105">You do this by overriding the **OnInit** method of the **Code** object of a report.</span></span> <span data-ttu-id="96458-106">Для доступа к методу **OnInit** используется элемент **Code** определения отчета.</span><span class="sxs-lookup"><span data-stu-id="96458-106">To access **OnInit**, use the **Code** element of the report definition.</span></span> <span data-ttu-id="96458-107">Существует два способа инициализации значений свойства или поля классов в пользовательской сборке, которую планируется использовать в отчете: можно объявить и создать новый экземпляр класса с помощью метода **OnInit** или вызвать общедоступный метод с помощью метода **OnInit**.</span><span class="sxs-lookup"><span data-stu-id="96458-107">There are two techniques for initializing property or field values of the classes in a custom assembly that you plan to use in your report: You can either declare and create a new instance of your class using **OnInit**, or you can call a publicly available method using **OnInit**.</span></span>  
  
## <a name="global-object-collections-and-initialization"></a><span data-ttu-id="96458-108">Коллекции глобальных объектов и инициализация</span><span class="sxs-lookup"><span data-stu-id="96458-108">Global Object Collections and Initialization</span></span>  
 <span data-ttu-id="96458-109">Имеется несколько доступных коллекций для инициализации переменных пользовательского класса.</span><span class="sxs-lookup"><span data-stu-id="96458-109">Several collections are available to you for initializing your custom class variables.</span></span> <span data-ttu-id="96458-110">Можно использовать коллекции **Globals** и **User**.</span><span class="sxs-lookup"><span data-stu-id="96458-110">You can use the **Globals** and **User** collections.</span></span> <span data-ttu-id="96458-111">Коллекции **Parameters**, **Fields** и **ReportItems** недоступны пользователю во время жизненного цикла отчета, если вызван метод **OnInit**.</span><span class="sxs-lookup"><span data-stu-id="96458-111">The **Parameters**, **Fields** and **ReportItems** collections are not available to you at the point in the report lifecycle when the **OnInit** method is invoked.</span></span> <span data-ttu-id="96458-112">Чтобы использовать общие коллекции **Globals** или **User**, нужно включить ссылку на объект **Report**.</span><span class="sxs-lookup"><span data-stu-id="96458-112">To use the shared collections, **Globals** or **User**, you need to include the **Report** object reference.</span></span> <span data-ttu-id="96458-113">Например, для инициализации пользовательского класса на основании текущего языка пользователя, обращающегося к отчету, элемент **Code** может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="96458-113">For example, to initialize your custom class based on the current language of the user accessing the report, your **Code** element might look like the following:</span></span>  
  
```  
<Code>  
   Dim m_myClass As MyClass  
  
   Protected Overrides Sub OnInit()  
      m_myClass = new MyClass(Report.User!Language, _  
         Report.Globals!ExecutionTime)  
   End Sub  
</Code>  
```  
  
 <span data-ttu-id="96458-114">Одним из способов инициализации значений свойств и полей класса, как показано выше, является объявление класса и создание его нового экземпляра вызовом переопределенного конструктора.</span><span class="sxs-lookup"><span data-stu-id="96458-114">One way to initialize the property and field values of a class as shown previously is to declare your class and create a new instance of it by calling an overridden constructor.</span></span>  
  
 <span data-ttu-id="96458-115">Другим способом инициализации значений свойств и полей классов пользовательских сборок является вызов общедоступного метода, определяемого на основании метода **OnInit**.</span><span class="sxs-lookup"><span data-stu-id="96458-115">Another way to initialize the property and field values of the classes in your custom assemblies is to call a publicly available method that you define from the **OnInit** method.</span></span> <span data-ttu-id="96458-116">Вначале необходимо добавить имя экземпляра класса в файл определения отчета.</span><span class="sxs-lookup"><span data-stu-id="96458-116">You first need to add an instance name for your class in the report definition file.</span></span> <span data-ttu-id="96458-117">После добавления нужной ссылки на сборку и имени экземпляра можно вызвать метод инициализации, чтобы инициализировать значения свойств и полей этого класса.</span><span class="sxs-lookup"><span data-stu-id="96458-117">Once you have added the appropriate assembly reference and instance name, you can call your initialization method to initialize property and field values for your class.</span></span> <span data-ttu-id="96458-118">Метод **OnInit** может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="96458-118">Your **OnInit** method might look like the following:</span></span>  
  
```  
<Code>  
   Protected Overrides Sub OnInit()  
      m_myClass.MyInitializationMethod(Report.User!Language, _  
         Report.Globals!ExecutionTime)  
   End Sub  
</Code>  
```  
  
 <span data-ttu-id="96458-119">Дополнительные сведения о добавлении ссылки на сборку и имени экземпляра для класса см. в разделе [Добавление в отчет ссылки на сборку (службы SSRS)](../report-design/add-an-assembly-reference-to-a-report-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="96458-119">For more information about adding an assembly reference and instance name for your custom class, see [Add an Assembly Reference to a Report &#40;SSRS&#41;](../report-design/add-an-assembly-reference-to-a-report-ssrs.md).</span></span>  
  
 <span data-ttu-id="96458-120">Дополнительные сведения о глобальных коллекциях объектов см. в разделе [Встроенные коллекции в выражениях (построитель отчетов и службы SSRS)](../report-design/built-in-collections-in-expressions-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="96458-120">For more information about the global object collections, see [Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96458-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="96458-121">See Also</span></span>  
 [<span data-ttu-id="96458-122">Использование пользовательских сборок с отчетами</span><span class="sxs-lookup"><span data-stu-id="96458-122">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
