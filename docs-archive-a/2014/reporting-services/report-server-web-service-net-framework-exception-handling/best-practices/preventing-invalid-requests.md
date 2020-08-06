---
title: Предотвращение использования недопустимых запросов | Документы Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- invalid requests [Reporting Services]
- exceptions [Reporting Services], invalid requests
- valid requests [Reporting Services]
ms.assetid: 4a4a2d97-4c10-43a9-8298-ef5a820ea549
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 12343955c46fb98fea75048a38749b1db993fa11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667561"
---
# <a name="preventing-invalid-requests"></a><span data-ttu-id="d96b7-102">Предотвращение недопустимых запросов</span><span class="sxs-lookup"><span data-stu-id="d96b7-102">Preventing Invalid Requests</span></span>
  <span data-ttu-id="d96b7-103">Возникновение некоторых типов исключений можно предотвратить, проведя анализ потока работы приложения и убедившись в том, что все запросы, направляемые на сервер отчетов, являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="d96b7-103">You can prevent some types of exceptions from being thrown by analyzing your application flow and ensuring that the requests being sent to the report server are valid.</span></span> <span data-ttu-id="d96b7-104">Например, в приложениях, предоставляющих пользователям возможность добавить или обновить имя отчета, источник данных или другие параметры сервера отчетов, необходимо проверять текст, вводимый пользователем.</span><span class="sxs-lookup"><span data-stu-id="d96b7-104">For example, in applications that enable users to add or update the name of a report, data source, or other report server item, you should validate the text that a user might enter.</span></span> <span data-ttu-id="d96b7-105">Перед отправкой запроса на сервер отчетов следует всегда проверять, нет ли в нем зарезервированных символов.</span><span class="sxs-lookup"><span data-stu-id="d96b7-105">You should always check for reserved characters before sending the request to a report server.</span></span> <span data-ttu-id="d96b7-106">Чтобы предупредить пользователя о том, что он не выполнил необходимых условий для отправки запросов на сервер отчетов, используйте в коде условные операторы **if** или другие логические конструкции.</span><span class="sxs-lookup"><span data-stu-id="d96b7-106">Use conditional **if** statements or other logical constructs in your code to alert the user that they have not met the conditions necessary to send requests to the report server.</span></span>  
  
 <span data-ttu-id="d96b7-107">В следующем упрощенном примере на языке C# при попытке создать отчет с именем, содержащим символ косой черты (/), пользователи получают понятное сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="d96b7-107">In the following, simplified C# example, users are presented with a friendly error message when they attempt to create a report with a name that contains a forward slash (/) character.</span></span>  
  
```  
// C#  
private void PublishReport()  
{  
   int index;  
   string reservedChar;  
   string message;  
  
   // Check the text value of the name text box for "/",  
   // a reserved character  
   index = nameTextBox.Text.IndexOf(@"/");  
  
   if ( index != -1) // The text contains the character  
   {  
      reservedChar = nameTextBox.Text.Substring(index, 1);  
      // Build a user-friendly error message  
      message = "The name of the report cannot contain the reserved character " +  
         "\"" + reservedChar + "\". " +  
         "Please enter a valid name for the report. " +  
         "For more information about reserved characters, " +  
         "see the help documentation";  
  
      MessageBox.Show(message, "Invalid Input Error");  
   }  
   else // Publish the report  
   {  
      Byte[] definition = null;  
      Warning[] warnings = {};  
      string name = nameTextBox.Text;  
  
      FileStream stream = File.OpenRead("MyReport.rdl");  
      definition = new Byte[stream.Length];  
      stream.Read(definition, 0, (int) stream.Length);  
      stream.Close();  
      // Create report with user-defined name  
      rs.CreateCatalogItem("Report", name, "/Samples", false, definition, null, out warnings);  
      MessageBox.Show("Report: {0} created successfully", name);  
   }  
}  
```  
  
 <span data-ttu-id="d96b7-108">Дополнительные сведения о типах ошибок, которые могут быть устранены до отправки запросов на сервер отчетов, см. в разделе [Таблица ошибок SoapException](../soapexception-class/soapexception-errors-table.md).</span><span class="sxs-lookup"><span data-stu-id="d96b7-108">For more information about the types of errors that can be prevented before requests are sent to the report server, see [SoapException Errors Table](../soapexception-class/soapexception-errors-table.md).</span></span> <span data-ttu-id="d96b7-109">Дополнительные сведения об усовершенствовании предыдущего примера с помощью блоков try и catch см. в разделе [Использование блоков Try-Catch](using-try-and-catch-blocks.md).</span><span class="sxs-lookup"><span data-stu-id="d96b7-109">For more information about further enhancing the previous example using try/catch blocks, see [Using Try and Catch Blocks](using-try-and-catch-blocks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d96b7-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="d96b7-110">See Also</span></span>  
 <span data-ttu-id="d96b7-111">[Введение в обработку исключений в Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="d96b7-111">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="d96b7-112">Класс SoapException в службах Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d96b7-112">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
