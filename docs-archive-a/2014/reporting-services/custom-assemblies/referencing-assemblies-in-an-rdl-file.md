---
title: Ссылки на сборки в RDL-файле | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- RDL [Reporting Services], referencing assemblies
- referencing custom assemblies
- custom assemblies [Reporting Services], referencing
- Report Definition Language, referencing assemblies
- report definition files [Reporting Services]
ms.assetid: 9a48e552-7d47-4243-9be1-894990c506d9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 14593717d2319d7d702fd0c414e0c24428006f51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729142"
---
# <a name="referencing-assemblies-in-an-rdl-file"></a><span data-ttu-id="dc23b-102">Ссылки на сборки в RDL-файле</span><span class="sxs-lookup"><span data-stu-id="dc23b-102">Referencing Assemblies in an RDL File</span></span>
  <span data-ttu-id="dc23b-103">Для поддержки использования сборок с пользовательским кодом в файлах определения отчета в спецификацию языка определения отчетов были включены два элемента: **CodeModules** и **Classes**.</span><span class="sxs-lookup"><span data-stu-id="dc23b-103">To support the use of custom code assemblies in report definition files, two Report Definition Language (RDL) elements are included in the RDL specification: the **CodeModules** element and the **Classes** element.</span></span>  
  
 <span data-ttu-id="dc23b-104">Элемент **CodeModules** позволяет ссылаться на сборки с управляемым кодом в выражениях отчета.</span><span class="sxs-lookup"><span data-stu-id="dc23b-104">The **CodeModules** element enables you to refer to managed code assemblies in report expressions.</span></span> <span data-ttu-id="dc23b-105">Элемент высокого уровня **CodeModules** содержит ссылку на сборку, используемую в файлах определения отчета для вызова специализированных функций.</span><span class="sxs-lookup"><span data-stu-id="dc23b-105">**CodeModules** is a top-level element that contains the reference to the assembly that you use in your report definition files to call specialized functions.</span></span> <span data-ttu-id="dc23b-106">Запись в определении отчета, поддерживающая использование пользовательской сборки, может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="dc23b-106">An entry in a report definition that supports the use of a custom assembly might look like the following:</span></span>  
  
```  
<CodeModules>  
   <CodeModule>CurrencyConversion, Version=1.0.1363.31103, Culture=neutral, PublicKeyToken=null</CodeModule>  
</CodeModules>  
```  
  
 <span data-ttu-id="dc23b-107">Вместо вызова метода <xref:System.Reflection.Assembly.Load%2A> в пользовательском коде пользовательские сборки можно зарегистрировать либо вручную, добавив элементы **CodeModule** в RDL-файл, либо использовав вкладку **Ссылки** в диалоговом окне **Свойства отчета**.</span><span class="sxs-lookup"><span data-stu-id="dc23b-107">Instead of calling <xref:System.Reflection.Assembly.Load%2A> from your custom code, register your custom assemblies by either manually adding **CodeModule** elements to your RDL file or by using the **References** tab of the **Report Properties** dialog.</span></span> <span data-ttu-id="dc23b-108">Дополнительные сведения см. в разделе [Пользовательский код и ссылки на сборки в выражениях в конструкторе отчетов (службы SSRS)](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dc23b-108">For more information, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
 <span data-ttu-id="dc23b-109">Элемент **Classes** поддерживает использование членов экземпляров в определении отчета.</span><span class="sxs-lookup"><span data-stu-id="dc23b-109">The **Classes** element supports the use of instance members in a report definition.</span></span> <span data-ttu-id="dc23b-110">**Classes** — это высокоуровневый элемент, содержащий ссылку на имя класса и имя экземпляра.</span><span class="sxs-lookup"><span data-stu-id="dc23b-110">**Classes** is a top-level element that contains a reference to the class name and an instance name.</span></span> <span data-ttu-id="dc23b-111">Запись в определении отчета, поддерживающая использование членов экземпляров может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="dc23b-111">An entry in a report definition that supports the use of instance members might look like the following:</span></span>  
  
```  
<Classes>  
   <Class>  
      <ClassName>CurrencyConversion.DollarCurrencyConversion</ClassName>  
      <InstanceName>m_myDollarConversion</InstanceName>  
   </Class>  
</Classes>  
```  
  
 <span data-ttu-id="dc23b-112">Дополнительные сведения о доступе к коду см. в разделе [Доступ к пользовательским сборкам посредством выражений](accessing-custom-assemblies-through-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="dc23b-112">For more information, see [Accessing Custom Assemblies Through Expressions](accessing-custom-assemblies-through-expressions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc23b-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="dc23b-113">See Also</span></span>  
 [<span data-ttu-id="dc23b-114">Использование пользовательских сборок с отчетами</span><span class="sxs-lookup"><span data-stu-id="dc23b-114">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
