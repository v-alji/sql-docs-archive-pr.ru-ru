---
title: Добавление в отчет ссылку на сборку (службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- code [Reporting Services]
- custom assemblies [Reporting Services], referencing
- custom code [Reporting Services]
- adding assembly references
- assemblies [Reporting Services], references
ms.assetid: 0a03939e-48ce-4c30-b227-98533f2e0ccb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 23dda0c65589e55849f906c621e42ce70f0d7ab5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666436"
---
# <a name="add-an-assembly-reference-to-a-report-ssrs"></a><span data-ttu-id="7215b-102">Добавление в отчет ссылку на сборку (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="7215b-102">Add an Assembly Reference to a Report (SSRS)</span></span>
  <span data-ttu-id="7215b-103">При внедрении пользовательского кода, содержащего ссылки на классы [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], не входящие в <xref:System.Math> или <xref:System.Convert>, необходимо предоставить в отчете ссылку на сборку, чтобы обработчик отчетов мог разрешать имена этих классов.</span><span class="sxs-lookup"><span data-stu-id="7215b-103">When you embed custom code that contains references to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes that are not in <xref:System.Math> or <xref:System.Convert>, you must provide an assembly reference to the report so that the report processor can resolve the names.</span></span> <span data-ttu-id="7215b-104">Дополнительные сведения см. в разделе [Добавление кода в отчет (службы SSRS)](add-code-to-a-report-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7215b-104">For more information, see [Add Code to a Report &#40;SSRS&#41;](add-code-to-a-report-ssrs.md).</span></span>  
  
### <a name="to-add-an-assembly-reference-to-a-report"></a><span data-ttu-id="7215b-105">Добавление в отчет ссылки на сборку</span><span class="sxs-lookup"><span data-stu-id="7215b-105">To add an assembly reference to a report</span></span>  
  
1.  <span data-ttu-id="7215b-106">В режиме **конструктора** щелкните правой кнопкой мыши в области конструктора за границей отчета и выберите команду **Свойства отчета**.</span><span class="sxs-lookup"><span data-stu-id="7215b-106">In **Design** view, right-click the design surface outside the border of the report and click **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="7215b-107">Нажмите кнопку **Ссылки**.</span><span class="sxs-lookup"><span data-stu-id="7215b-107">Click **References**.</span></span>  
  
3.  <span data-ttu-id="7215b-108">В окне **Добавить или удалить сборки**нажмите кнопку **Добавить** и затем нажмите кнопку с многоточием, чтобы найти сборку.</span><span class="sxs-lookup"><span data-stu-id="7215b-108">In **Add or remove assemblies**, click **Add** and then click the ellipsis button to browse to the assembly.</span></span>  
  
4.  <span data-ttu-id="7215b-109">В окне **Добавить или удалить классы**нажмите кнопку **Добавить** , а затем введите имя класса и предоставьте имя экземпляра для использования в отчете.</span><span class="sxs-lookup"><span data-stu-id="7215b-109">In **Add or remove classes**, click **Add** and then type name of the class and provide an instance name to use within the report.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7215b-110">Укажите имя класса и имя экземпляра только для элементов, зависимых от экземпляров.</span><span class="sxs-lookup"><span data-stu-id="7215b-110">Specify a class and instance name only for instance-based members.</span></span> <span data-ttu-id="7215b-111">Не задавайте статические элементы в списке **Классы** .</span><span class="sxs-lookup"><span data-stu-id="7215b-111">Do not specify static members in the **Classes** list.</span></span> <span data-ttu-id="7215b-112">Дополнительные сведения см. в разделе [Пользовательский код и ссылки на сборки в выражениях в конструкторе отчетов (службы SSRS)](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7215b-112">For more information, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7215b-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="7215b-113">See Also</span></span>  
 <span data-ttu-id="7215b-114">[Использование пользовательских сборок с отчетами](../custom-assemblies/using-custom-assemblies-with-reports.md) </span><span class="sxs-lookup"><span data-stu-id="7215b-114">[Using Custom Assemblies with Reports](../custom-assemblies/using-custom-assemblies-with-reports.md) </span></span>  
 [<span data-ttu-id="7215b-115">Диалоговое окно "Свойства отчета" — "Ссылки"</span><span class="sxs-lookup"><span data-stu-id="7215b-115">Report Properties Dialog Box, References</span></span>](../report-properties-dialog-box-references.md)  
  
  
