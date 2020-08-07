---
title: Добавление кода в отчет (службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- code [Reporting Services]
- custom code [Reporting Services]
- expressions [Reporting Services], code
- adding code
- reports [Reporting Services], code
ms.assetid: 00ef8fc6-99fe-49b2-8a22-7eb475881dc4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c1964e69d00e1a27da29ce8cfb73b7bee1bece7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733654"
---
# <a name="add-code-to-a-report-ssrs"></a><span data-ttu-id="4e5cb-102">Добавление кода в отчет (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="4e5cb-102">Add Code to a Report (SSRS)</span></span>
  <span data-ttu-id="4e5cb-103">В любом выражении можно вызвать собственный пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="4e5cb-103">In any expression, you can call your own custom code.</span></span> <span data-ttu-id="4e5cb-104">Данный код можно предоставить следующими способами.</span><span class="sxs-lookup"><span data-stu-id="4e5cb-104">You can provide code in the following two ways:</span></span>  
  
-   <span data-ttu-id="4e5cb-105">Напрямую внедрить в отчет код, написанный на [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4e5cb-105">Embed code written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] directly in your report.</span></span> <span data-ttu-id="4e5cb-106">Если код ссылается на классы [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], не принадлежащие пространству имен <xref:System.Math> или <xref:System.Convert>, то в отчет нужно добавить ссылку.</span><span class="sxs-lookup"><span data-stu-id="4e5cb-106">If your code refers to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] that is not <xref:System.Math> or <xref:System.Convert>, you must add the reference to the report.</span></span> <span data-ttu-id="4e5cb-107">Дополнительные сведения см. в разделе [Добавление в отчет ссылки на сборку (службы SSRS)](add-an-assembly-reference-to-a-report-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4e5cb-107">For more information, see [Add an Assembly Reference to a Report &#40;SSRS&#41;](add-an-assembly-reference-to-a-report-ssrs.md).</span></span> <span data-ttu-id="4e5cb-108">Дополнительные сведения о других ссылках, которые можно выполнить из кода, см. в разделе [Пользовательский код и ссылки на сборки в выражениях в конструкторе отчетов (службы SSRS)](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="4e5cb-108">For more information about other references you can make from your code, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
-   <span data-ttu-id="4e5cb-109">Предоставить сборку пользовательского кода, использующего платформу [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e5cb-109">Provide a custom code assembly by using the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="4e5cb-110">Если предоставляется пользовательская сборка, ее следует установить как на компьютере, на котором создается отчет, так и на сервере отчетов, где выполняется просмотр отчета.</span><span class="sxs-lookup"><span data-stu-id="4e5cb-110">If you provide a custom assembly, you must install it on both the computer where you author the report and the report server where you view the report.</span></span> <span data-ttu-id="4e5cb-111">Дополнительные сведения см. в статье [Using Custom Assemblies with Reports](../custom-assemblies/using-custom-assemblies-with-reports.md).</span><span class="sxs-lookup"><span data-stu-id="4e5cb-111">For more information, see [Using Custom Assemblies with Reports](../custom-assemblies/using-custom-assemblies-with-reports.md).</span></span>  
  
### <a name="to-add-embedded-code-to-a-report"></a><span data-ttu-id="4e5cb-112">Добавление в отчет внедренного кода</span><span class="sxs-lookup"><span data-stu-id="4e5cb-112">To add embedded code to a report</span></span>  
  
1.  <span data-ttu-id="4e5cb-113">В режиме **конструктора** щелкните правой кнопкой мыши в области конструктора за границей отчета и выберите команду **Свойства отчета**.</span><span class="sxs-lookup"><span data-stu-id="4e5cb-113">In **Design** view, right-click the design surface outside the border of the report and click **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="4e5cb-114">Щелкните **Код**.</span><span class="sxs-lookup"><span data-stu-id="4e5cb-114">Click **Code**.</span></span>  
  
3.  <span data-ttu-id="4e5cb-115">В поле **Пользовательский код**введите код.</span><span class="sxs-lookup"><span data-stu-id="4e5cb-115">In **Custom code**, type the code.</span></span> <span data-ttu-id="4e5cb-116">Если при выполнении отчета в коде возникают ошибки, то выводятся предупреждения.</span><span class="sxs-lookup"><span data-stu-id="4e5cb-116">Errors in the code produce warnings when the report runs.</span></span> <span data-ttu-id="4e5cb-117">В следующем примере создается пользовательская функция с именем `ChangeWord` , заменяющая слово «`Bike`» словом «`Bicycle`».</span><span class="sxs-lookup"><span data-stu-id="4e5cb-117">The following example creates a custom function named `ChangeWord` that replaces the word "`Bike`" with "`Bicycle`".</span></span>  
  
    ```  
    Public Function ChangeWord(ByVal s As String) As String  
       Dim strBuilder As New System.Text.StringBuilder(s)  
       If s.Contains("Bike") Then  
          strBuilder.Replace("Bike", "Bicycle")  
          Return strBuilder.ToString()  
          Else : Return s  
       End If  
    End Function  
    ```  
  
4.  <span data-ttu-id="4e5cb-118">В следующем примере показывается, как с помощью выражения передать этой функции поле набора данных с именем «Категория».</span><span class="sxs-lookup"><span data-stu-id="4e5cb-118">The following example shows how to pass a dataset field named Category to this function in an expression:</span></span>  
  
    ```  
    =Code.ChangeWord(Fields!Category.Value)  
    ```  
  
     <span data-ttu-id="4e5cb-119">Если поместить такое выражение в ячейку таблицы, отображающую значения категории, то при возникновении в поле набора данных для данной строки слова «Bike», в качестве значения ячейки таблицы будет отображено слово «Bicycle».</span><span class="sxs-lookup"><span data-stu-id="4e5cb-119">If you add this expression to a table cell that displays category values, whenever the word "Bike" is in the dataset field for that row, the table cell value displays the word "Bicycle" instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e5cb-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="4e5cb-120">See Also</span></span>  
 <span data-ttu-id="4e5cb-121">[Диалоговое окно «Свойства отчета» — «Код»](../report-properties-dialog-box-code.md) </span><span class="sxs-lookup"><span data-stu-id="4e5cb-121">[Report Properties Dialog Box, Code](../report-properties-dialog-box-code.md) </span></span>  
 <span data-ttu-id="4e5cb-122">[Примеры выражений (построитель отчетов и службы SSRS)](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4e5cb-122">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4e5cb-123">Ссылки на коллекцию параметров (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="4e5cb-123">Parameters Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-parameters-collection-references-report-builder.md)  
  
  
