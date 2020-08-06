---
title: Экспорт отчета с применением доступа по URL-адресу | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- formats [Reporting Services], URL rendering
- URL access [Reporting Services], rendering formats
ms.assetid: 6a3b7fc3-3d91-4d12-8371-42ea12e74517
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 69f340855e37ffde49aec0af096c094a142659d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728074"
---
# <a name="export-a-report-using-url-access"></a><span data-ttu-id="c7ecd-102">Экспорт отчета с применением доступа по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="c7ecd-102">Export a Report Using URL Access</span></span>
  <span data-ttu-id="c7ecd-103">При необходимости можно указать формат отображения отчета с помощью параметра *RS: Format* .</span><span class="sxs-lookup"><span data-stu-id="c7ecd-103">You can optionally specify the format in which to render a report by using the *rs:Format* parameter.</span></span> <span data-ttu-id="c7ecd-104">Например, чтобы получить копию отчета в формате PDF прямо с сервера отчетов, работающего в собственном режиме:</span><span class="sxs-lookup"><span data-stu-id="c7ecd-104">For example, to get a PDF copy of a report directly from a native mode report server:</span></span>  
  
```  
http://myrshost/ReportServer?/myreport&rs:Format=PDF  
```  
  
 <span data-ttu-id="c7ecd-105">И с сервера отчетов, работающего в режиме интеграции с SharePoint:</span><span class="sxs-lookup"><span data-stu-id="c7ecd-105">And, from a SharePoint integrated mode report server:</span></span>  
  
```  
http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/myrereport.rdl&rs:Format=PDF  
```  
  
 <span data-ttu-id="c7ecd-106">Допустимые значения для этого параметра основаны на модулях подготовки отчетов, установленных на сервер отчетов, к которому осуществляется доступ.</span><span class="sxs-lookup"><span data-stu-id="c7ecd-106">Valid values for this parameter are based on the report rendering extensions that are installed on the report server being accessed.</span></span> <span data-ttu-id="c7ecd-107">Поддерживаемые модули: HTML4.0, WORD, MHTML, IMAGE, EXCEL, WORD, CSV, CSV, PDF, XML и NULL.</span><span class="sxs-lookup"><span data-stu-id="c7ecd-107">Common extensions are HTML4.0, MHTML, IMAGE, EXCEL, WORD, CSV, PDF, XML, and NULL.</span></span> <span data-ttu-id="c7ecd-108">Если указанный модуль подготовки отчетов не установлен на сервере отчетов, то отчет не будет подготовлен, а браузере выдаст ошибку.</span><span class="sxs-lookup"><span data-stu-id="c7ecd-108">If a specified rendering extension is not installed on the report server, the report is not rendered and an error is generated and displayed in the browser.</span></span>  
  
 <span data-ttu-id="c7ecd-109">Если в URL-адрес не включен параметр *Format* , то сервер отчетов определяет браузер и подготавливает для него отчет в соответствующем HTML-формате.</span><span class="sxs-lookup"><span data-stu-id="c7ecd-109">If you do not include the *Format* parameter as part of the URL, the report server detects the browser and renders the report in the appropriate HTML format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7ecd-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="c7ecd-110">See Also</span></span>  
 <span data-ttu-id="c7ecd-111">[Доступ по URL-адресу &#40;службы SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c7ecd-111">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="c7ecd-112">Ссылка на параметр доступа по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="c7ecd-112">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
