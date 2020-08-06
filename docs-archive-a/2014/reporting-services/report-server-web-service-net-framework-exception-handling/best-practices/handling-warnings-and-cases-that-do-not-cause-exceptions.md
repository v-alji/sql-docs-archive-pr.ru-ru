---
title: Обработка предупреждений и ситуаций, не вызывающих исключений | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], warnings that don't cause
- warnings [Reporting Services]
ms.assetid: 475c0713-6265-44e7-9ebc-ebdd1b89e0af
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 88d3daf63cf5f04975a2941d0634f357ce81456c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733562"
---
# <a name="handling-warnings-and-cases-that-do-not-cause-exceptions"></a><span data-ttu-id="3d227-102">Обработка предупреждений и ситуаций, не вызывающих исключения</span><span class="sxs-lookup"><span data-stu-id="3d227-102">Handling Warnings and Cases That Do Not Cause Exceptions</span></span>
  <span data-ttu-id="3d227-103">В службах [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] не формируются исключения применительно к предупреждениям и некоторым ошибкам.</span><span class="sxs-lookup"><span data-stu-id="3d227-103">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] does not throw exceptions for warnings and certain errors.</span></span> <span data-ttu-id="3d227-104">Например, при использовании метода <xref:ReportService2010.ReportingService2010.CreateCatalogItem%2A> с целью публикации нового отчета на сервере отчетов все возникающие предупреждения возвращаются в виде массива объектов <xref:ReportService2010.Warning>.</span><span class="sxs-lookup"><span data-stu-id="3d227-104">For example, when you use the <xref:ReportService2010.ReportingService2010.CreateCatalogItem%2A> method to publish a new report to a report server, any warnings that occur are returned as an array of <xref:ReportService2010.Warning> objects.</span></span> <span data-ttu-id="3d227-105">Эти предупреждения должны быть обработаны и отображены, чтобы можно было осуществлять соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="3d227-105">These warnings should be handled and displayed so that appropriate action can be taken.</span></span>  
  
```vb  
Try  
   rs.CreateCatalogItem(name, parentFolder, False, definition, Nothing, warnings)  
  
   If Not (warnings.Length = 0) Then  
      Dim warning As Warning  
      For Each warning In warnings  
         Console.WriteLine(warning.Message)  
      Next warning  
   Else  
      Console.WriteLine("Report {0} created successfully with no warnings", name)  
   End If  
  
Catch ex As SoapException  
   Console.WriteLine(ex.Detail("Message").InnerXml)  
End Try  
```  
  
```csharp  
try  
{  
   rs.CreateCatalogItem("Report", name, parentFolder, false, definition, null, out warnings);  
  
   if (warnings.Length != 0)  
   {  
      foreach (Warning warning in warnings)  
      {  
         Console.WriteLine(warning.Message);  
      }  
   }  
   else  
      Console.WriteLine("Report {0} created successfully with no warnings", name);  
}  
  
catch (SoapException ex)  
{  
   Console.WriteLine(ex.Detail["Message"].InnerXml);  
}  
```  
  
 <span data-ttu-id="3d227-106">Еще один способ обработки ошибок состоит в обработке возвращаемых значений определенных методов.</span><span class="sxs-lookup"><span data-stu-id="3d227-106">Another way to handle errors is to evaluate the return values of certain methods.</span></span> <span data-ttu-id="3d227-107">К примеру, метод <xref:ReportService2010.ReportingService2010.FindItems%2A> можно использовать для поиска определенных элементов в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="3d227-107">For example, the <xref:ReportService2010.ReportingService2010.FindItems%2A> method can be used to search for specific items in the report server database.</span></span> <span data-ttu-id="3d227-108">Если элементы, соответствующие критериям поиска, не обнаружены, возвращается пустой массив объектов <xref:ReportService2010.CatalogItem>.</span><span class="sxs-lookup"><span data-stu-id="3d227-108">If no items are found that match the search criteria, a null array of <xref:ReportService2010.CatalogItem> objects is returned.</span></span> <span data-ttu-id="3d227-109">Необходимо обработать этот массив, проверить его на наличие значений `null`, а если не обнаружены элементы, известить об этом пользователя.</span><span class="sxs-lookup"><span data-stu-id="3d227-109">You should evaluate the array, check for `null`, and let the user know if no items were found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d227-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="3d227-110">See Also</span></span>  
 <xref:ReportService2010.CatalogItem>   
 <span data-ttu-id="3d227-111">[Введение в обработку исключений в Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="3d227-111">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="3d227-112">Класс SoapException в службах Reporting Services</span><span class="sxs-lookup"><span data-stu-id="3d227-112">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
