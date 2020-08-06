---
title: Форматирование файла скрипта служб Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- scripts [Reporting Services], formats
- formats [Reporting Services], script files
ms.assetid: 85a207dd-4e0f-4d40-a41e-0c75f65d719c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c98a2f6561c3242fec34f7ca11c8304286ccebae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732358"
---
# <a name="format-a-reporting-services-script-file"></a><span data-ttu-id="81b8f-102">Форматирование файла скрипта служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="81b8f-102">Format a Reporting Services Script File</span></span>
  <span data-ttu-id="81b8f-103">Скрипт служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] — это файл кода [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET, написанный для прокси-сервера, построенного на основе языка описания веб-служб (язык WSDL), определяющего API-интерфейс протокола простого доступа к объектам служб Reporting Services (SOAP).</span><span class="sxs-lookup"><span data-stu-id="81b8f-103">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] script is a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET code file, written against a proxy that is built on Web Service Description Language (WSDL), which defines the Reporting Services SOAP API.</span></span> <span data-ttu-id="81b8f-104">Файл скрипта хранится как текстовый файл Юникод или UTF-8 с расширением RSS.</span><span class="sxs-lookup"><span data-stu-id="81b8f-104">A script file is stored as a Unicode or UTF-8 text file with the extension .rss.</span></span>  
  
 <span data-ttu-id="81b8f-105">Файл скрипта действует как модуль языка [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] . Он может содержать пользовательские процедуры и переменные уровня модуля.</span><span class="sxs-lookup"><span data-stu-id="81b8f-105">The script file acts as a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] module and can contain user-defined procedures and module-level variables.</span></span> <span data-ttu-id="81b8f-106">Для успешного выполнения файла скрипта он должен содержать главную процедуру.</span><span class="sxs-lookup"><span data-stu-id="81b8f-106">For the script file to run successfully, it must contain a Main procedure.</span></span> <span data-ttu-id="81b8f-107">Главная процедура — это первая процедура, к которой идет обращение при запуске файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="81b8f-107">The Main procedure is the first procedure that is accessed when your script file runs.</span></span> <span data-ttu-id="81b8f-108">В ней можно создавать операции веб-службы и запускать определяемые пользователем подпроцедуры.</span><span class="sxs-lookup"><span data-stu-id="81b8f-108">Main is where you can add your Web service operations and run your user defined subprocedures.</span></span> <span data-ttu-id="81b8f-109">Следующий фрагмент кода создает главную процедуру:</span><span class="sxs-lookup"><span data-stu-id="81b8f-109">The following code creates a Main procedure:</span></span>  
  
```  
Public Sub Main()  
    ' Your code goes here.  
End Sub  
```  
  
 <span data-ttu-id="81b8f-110">Среда скриптов автоматически соединяется с сервером отчетов, создает класс-посредник и формирует ссылку на переменную (*rs*) для объекта записи-посредника веб-службы.</span><span class="sxs-lookup"><span data-stu-id="81b8f-110">The script environment automatically connects to the report server, creates the Web proxy class, and generates a reference variable (*rs*) to the Web service proxy object.</span></span> <span data-ttu-id="81b8f-111">Отдельные создаваемые инструкции должны ссылаться только на переменную уровня модуля *rs* , для выполнения любых операций веб-службы, доступных в библиотеке веб-службы.</span><span class="sxs-lookup"><span data-stu-id="81b8f-111">Individual statements that you create need only refer to the *rs* module-level variable to perform any of the Web service operations that are available in the Web service library.</span></span> <span data-ttu-id="81b8f-112">Следующий код на языке [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] вызывает метод <xref:ReportService2010.ReportingService2010.ListChildren%2A> веб-службы из файла скрипта:</span><span class="sxs-lookup"><span data-stu-id="81b8f-112">The following [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] code calls the Web service <xref:ReportService2010.ReportingService2010.ListChildren%2A> method from within a script file:</span></span>  
  
```  
Public Sub Main()  
    Dim items() As CatalogItem  
    items = rs.ListChildren("/", True)  
  
    Dim item As CatalogItem  
    For Each item In items  
        Console.WriteLine(item.Name)  
    Next item  
End Sub   
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="81b8f-113">Учетные данные пользователей находятся под управлением среды скриптов и передаются через аргументы командной строки с помощью программы RS.exe.</span><span class="sxs-lookup"><span data-stu-id="81b8f-113">User credentials are managed by the script environment and passed through command prompt arguments through the use of RS.exe.</span></span> <span data-ttu-id="81b8f-114">Хотя проверку подлинности веб-службы можно задать с помощью переменной *rs* , рекомендуется использовать среду скриптов.</span><span class="sxs-lookup"><span data-stu-id="81b8f-114">Although you can use the *rs* variable to set the authentication of the Web service, it is recommended that you use the script environment.</span></span> <span data-ttu-id="81b8f-115">Внутри самого файла скрипта выполнять проверку подлинности веб-службы не требуется.</span><span class="sxs-lookup"><span data-stu-id="81b8f-115">You do not need to authenticate the Web service in the script file itself.</span></span> <span data-ttu-id="81b8f-116">Дополнительные сведения о проверке подлинности в среде скриптов см. в разделе [Служебная программа RS.exe (SSRS)](rs-exe-utility-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="81b8f-116">For more information about authenticating the script environment, see [RS.exe Utility &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span></span>  
  
 <span data-ttu-id="81b8f-117">Пространства имен не объявляются в файлах скриптов.</span><span class="sxs-lookup"><span data-stu-id="81b8f-117">You do not declare namespaces within the script file.</span></span> <span data-ttu-id="81b8f-118">Среда скриптов предоставляет доступ к нескольким полезным пространствам имен [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]: **System.Web.Services**, **System.Web.Services.Protocols**, **System.Xml** и **System.IO**.</span><span class="sxs-lookup"><span data-stu-id="81b8f-118">The scripting environment makes several useful [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] namespaces available to you: **System.Web.Services**, **System.Web.Services.Protocols**, **System.Xml**, and **System.IO**.</span></span>  
  
 <span data-ttu-id="81b8f-119">Образцы скриптов см. на странице [Образцы продуктов служб SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="81b8f-119">For script samples, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81b8f-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="81b8f-120">See Also</span></span>  
 <span data-ttu-id="81b8f-121">[Веб-служба сервера отчетов](../report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="81b8f-121">[Report Server Web Service](../report-server-web-service/report-server-web-service.md) </span></span>  
 <span data-ttu-id="81b8f-122">[Технический справочник (службы SSRS)](../technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="81b8f-122">[Technical Reference &#40;SSRS&#41;](../technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="81b8f-123">Служебная программа RS.exe (SSRS)</span><span class="sxs-lookup"><span data-stu-id="81b8f-123">RS.exe Utility &#40;SSRS&#41;</span></span>](rs-exe-utility-ssrs.md)  
  
  
