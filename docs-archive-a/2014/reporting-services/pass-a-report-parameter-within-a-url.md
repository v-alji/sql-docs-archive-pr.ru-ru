---
title: Передача параметра отчета в URL-адресе | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- URL access [Reporting Services], passing parameters
- passing parameters [Reporting Services]
ms.assetid: f93a94cc-27b5-435a-aa85-69e6ec6459ad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cf41ed82728d5d7c840276e135937b08f83fb131
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739515"
---
# <a name="pass-a-report-parameter-within-a-url"></a><span data-ttu-id="f8e56-102">Pass a Report Parameter Within a URL</span><span class="sxs-lookup"><span data-stu-id="f8e56-102">Pass a Report Parameter Within a URL</span></span>
  <span data-ttu-id="f8e56-103">Чтобы передать параметры в отчет, можно включить их в URL-адрес отчета.</span><span class="sxs-lookup"><span data-stu-id="f8e56-103">You can pass report parameters to a report by including them in a report URL.</span></span> <span data-ttu-id="f8e56-104">Такие параметры URL-адреса не снабжаются префиксами, поскольку они передаются непосредственно в подсистему обработки отчетов.</span><span class="sxs-lookup"><span data-stu-id="f8e56-104">These URL parameters are not prefixed because they are passed directly to the report processing engine.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f8e56-105">Важно, чтобы URL-адрес содержал синтаксис прокси `_vti_bin` для отправки запроса с помощью центра администрирования SharePoint и прокси-сервера HTTP [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f8e56-105">It is important the URL include the `_vti_bin` proxy syntax to route the request through SharePoint and the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] HTTP proxy.</span></span> <span data-ttu-id="f8e56-106">Прокси-сервер добавляет в HTTP-запрос контекст, необходимый для обеспечения правильного выполнения отчета для серверов отчетов в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f8e56-106">The proxy adds some context to the HTTP request, context that is required to ensure proper execution of the report for SharePoint mode report servers.</span></span>  
>   
>  <span data-ttu-id="f8e56-107">Если не указать синтаксис прокси-сервера, то необходимо добавить параметр с помощью *RP:*.</span><span class="sxs-lookup"><span data-stu-id="f8e56-107">If you don't include the proxy syntax, then you need to prefix the parameter with *rp:*.</span></span>  
  
 <span data-ttu-id="f8e56-108">Все параметры запроса могут иметь соответствующие параметры отчета.</span><span class="sxs-lookup"><span data-stu-id="f8e56-108">All query parameters can have corresponding report parameters.</span></span> <span data-ttu-id="f8e56-109">Параметр запроса можно передать в отчет.</span><span class="sxs-lookup"><span data-stu-id="f8e56-109">You pass a query parameter to a report by passing the corresponding report parameter.</span></span> <span data-ttu-id="f8e56-110">Дополнительные сведения см. в статье [Построение запроса в конструкторе реляционных запросов (построитель отчетов и службы SSRS)](report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f8e56-110">For more information, see [Build a Query in the Relational Query Designer &#40;Report Builder and SSRS&#41;](report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f8e56-111">В параметрах отчета учитывается регистр символов.</span><span class="sxs-lookup"><span data-stu-id="f8e56-111">Report parameters are case-sensitive.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="f8e56-112">Параметры отчета учитывают регистр символов и используют следующие специальные символы:</span><span class="sxs-lookup"><span data-stu-id="f8e56-112">Report parameters are case-sensitive and utilize the following special characters:</span></span>  
> 
>  -   <span data-ttu-id="f8e56-113">Все пробельные символы в строке URL-адресов заменяются символами «%20» в соответствии со стандартами кодировки URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="f8e56-113">Any space characters in the URL string are replaced with the characters "%20," according to URL encoding standards.</span></span>  
> -   <span data-ttu-id="f8e56-114">Пробел в секции параметров URL-адреса заменяется символом плюса (+).</span><span class="sxs-lookup"><span data-stu-id="f8e56-114">A space character in the parameter portion of the URL is replaced with a plus character (+).</span></span>  
> -   <span data-ttu-id="f8e56-115">Точка с запятой в любой части строки заменяется символами «%3A».</span><span class="sxs-lookup"><span data-stu-id="f8e56-115">A semicolon in any portion of the string is replaced with the characters "%3A."</span></span>  
> -   <span data-ttu-id="f8e56-116">Браузер должен автоматически выполнить необходимую кодировку URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="f8e56-116">Browsers should automatically perform the proper URL encoding.</span></span> <span data-ttu-id="f8e56-117">Пользователю нет необходимости выполнять кодировку символов вручную.</span><span class="sxs-lookup"><span data-stu-id="f8e56-117">You do not have to encode any of the characters manually.</span></span>  
  
 <span data-ttu-id="f8e56-118">Чтобы задать параметр отчета в URL-адресе, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="f8e56-118">To set a report parameter within a URL, use the following syntax:</span></span>  
  
```  
  
parameter=value  
```  
  
 <span data-ttu-id="f8e56-119">Например, чтобы указать параметры ReportMonth и ReportYear, заданные в отчете, используйте следующий URL-адрес для сервера отчетов, работающего в собственном режиме:</span><span class="sxs-lookup"><span data-stu-id="f8e56-119">For example, to specify two parameters, "ReportMonth" and "ReportYear", defined in a report, use the following URL for a native mode report server:</span></span>  
  
```  
http://myrshost/ReportServer?/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2&ReportMonth=3&ReportYear=2008  
```  
  
 <span data-ttu-id="f8e56-120">Например, чтобы указать те же два параметра, заданные в отчете, используйте следующий URL-адрес для сервера отчетов, работающего в режиме интеграции c SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f8e56-120">For example, to specify the same two parameters defined in a report, use the following URL for a SharePoint integrated mode report server.</span></span> <span data-ttu-id="f8e56-121">Обратите внимание на `/_vti_bin`!</span><span class="sxs-lookup"><span data-stu-id="f8e56-121">Note the `/_vti_bin`:</span></span>  
  
```  
http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2.rdl&ReportMonth=3&ReportYear=2008  
```  
  
 <span data-ttu-id="f8e56-122">Чтобы задать параметру значение NULL, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="f8e56-122">To pass a null value for a parameter, use the following syntax:</span></span>  
  
```  
  
parameter  
:isnull=true  
  
```  
  
 <span data-ttu-id="f8e56-123">например следующие.</span><span class="sxs-lookup"><span data-stu-id="f8e56-123">For example,</span></span>  
  
```  
SalesOrderNumber:isnull=true  
```  
  
 <span data-ttu-id="f8e56-124">Чтобы задать значение `Boolean` , используйте 0 для значения ложь и 1 для значения верно.</span><span class="sxs-lookup"><span data-stu-id="f8e56-124">To pass a `Boolean` value, use 0 for false and 1 for true.</span></span> <span data-ttu-id="f8e56-125">Чтобы задать значение `Float` , включите десятичный разделитель для языкового стандарта сервера</span><span class="sxs-lookup"><span data-stu-id="f8e56-125">To pass a `Float` value, include the decimal separator of the server locale</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f8e56-126">Если отчет содержит параметр отчета, имеющий значение по умолчанию, а свойство `Prompt` имеет значение `false` (то есть в диспетчере отчетов не выбрано свойство «Подсказка пользователю»), передать значение этого параметра отчета в URL-адресе невозможно.</span><span class="sxs-lookup"><span data-stu-id="f8e56-126">If your report contains a report parameter that has a default value and the value of the `Prompt` property is `false` (that is, the Prompt User property is not selected in Report Manager), then you cannot pass a value for that report parameter within a URL.</span></span> <span data-ttu-id="f8e56-127">Это позволяет администраторам запретить пользователям добавлять и изменять значения определенных параметров отчета.</span><span class="sxs-lookup"><span data-stu-id="f8e56-127">This provides administrators an option for preventing end users from adding or modifying the values of certain report parameters.</span></span>  
  
##  <a name="additional-examples"></a><a name="bkmk_examples"></a> <span data-ttu-id="f8e56-128">Дополнительные примеры</span><span class="sxs-lookup"><span data-stu-id="f8e56-128">Additional Examples</span></span>  
 <span data-ttu-id="f8e56-129">В следующем примере URL-адрес содержит пробелы и многозначные параметры.</span><span class="sxs-lookup"><span data-stu-id="f8e56-129">The following URL example includes spaces and multiple parameters</span></span>  
  
-   <span data-ttu-id="f8e56-130">Имя папки "Группы образования пользователя SQL Server" содержит пробелы, которые заменяются знаком "+".</span><span class="sxs-lookup"><span data-stu-id="f8e56-130">Folder name of "SQL Server User Education Team" includes spaces and therefore the "+" replaces each space.</span></span>  
  
-   <span data-ttu-id="f8e56-131">Имя отчета "Отчет по командному проекту" содержит пробелы, которые заменяются знаком "+".</span><span class="sxs-lookup"><span data-stu-id="f8e56-131">Report name of "team project report" includes spaces and therefore the "+" replaces each space.</span></span>  
  
-   <span data-ttu-id="f8e56-132">Передает два параметра: teamgrouping2 со значением xgroup и teamgrouping1 со значением ygroup.</span><span class="sxs-lookup"><span data-stu-id="f8e56-132">Passes two parameters of "teamgrouping2" with a value of "xgroup" and "teamgrouping1" with a value of "ygroup".</span></span>  
  
```  
https://myserver/Reportserver?/SQL+Server+User+Education+Team/_ContentTeams/folder123/team+project+report&teamgrouping2=xgroup&teamgrouping1=ygroup  
```  
  
 <span data-ttu-id="f8e56-133">В следующем примере URL-адрес содержит многозначный параметр OrderID.</span><span class="sxs-lookup"><span data-stu-id="f8e56-133">The following URL example includes a multi-value parameter "OrderID.</span></span> <span data-ttu-id="f8e56-134">Формат многозначного параметра должен повторять имя параметра для каждого значения.</span><span class="sxs-lookup"><span data-stu-id="f8e56-134">The format for a Multi-Value parameter is to repeat the parameter name for each value.</span></span>  
  
```  
https://myserver/Reportserver?/SQL+Server+User+Education+Team/_ContentTeams/folder123/team+project+report&teamgrouping2=xgroup&teamgrouping1=ygroup&OrderID=747&OrderID=787&OrderID=12  
```  
  
 <span data-ttu-id="f8e56-135">Следующий пример URL-адреса передает один параметр *SellStartDate* со значением "7/1/2005" для сервера отчетов в собственном режиме.</span><span class="sxs-lookup"><span data-stu-id="f8e56-135">The following URL example passes a single parameter of *SellStartDate* with a value of "7/1/2005", for a native mode report server.</span></span>  
  
```  
http://myserver/ReportServer/Pages/ReportViewer.aspx?%2fProduct_and_Sales_Report_AdventureWorks&SellStartDate=7/1/2005  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8e56-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="f8e56-136">See Also</span></span>  
 <span data-ttu-id="f8e56-137">[Доступ по URL-адресу &#40;службы SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f8e56-137">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="f8e56-138">Ссылка на параметр доступа по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="f8e56-138">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
