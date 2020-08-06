---
title: Задание языка для параметров отчета в URL-адресе | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- overriding report language settings
- report servers [Reporting Services], language settings
- languages [Reporting Services]
- URL access [Reporting Services], language overrides
- international considerations [Reporting Services]
- global considerations [Reporting Services]
ms.assetid: e1ccf22f-80d6-45bc-aae0-f5f263275092
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8087a181906517bb60d4cd6839eed0681f52a5eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732381"
---
# <a name="set-the-language-for-report-parameters-in-a-url"></a><span data-ttu-id="62f90-102">Задать язык для параметров отчета в URL-адресе</span><span class="sxs-lookup"><span data-stu-id="62f90-102">Set the Language for Report Parameters in a URL</span></span>
  <span data-ttu-id="62f90-103">Параметр *rs:ParameterLanguage* для доступа по URL-адресу устраняет проблему, когда для интерпретации таких региональных параметров отчета, как дата, время, валюта и числа, используется язык браузера.</span><span class="sxs-lookup"><span data-stu-id="62f90-103">The *rs:ParameterLanguage* URL access parameter alleviates a problem in which culture-sensitive report parameters, such as dates, times, currency, and numbers, are interpreted using the browser language.</span></span> <span data-ttu-id="62f90-104">URL-адрес с указанным параметром *rs:ParameterLanguage*интерпретируется независимо от браузера.</span><span class="sxs-lookup"><span data-stu-id="62f90-104">With *rs:ParameterLanguage*, the URL is now interpreted independently of the browser.</span></span> <span data-ttu-id="62f90-105">Например, если на сервере отчетов установлены региональные параметры «Немецкий», но пользователь обращается к отчету по URL-адресу из браузера, в котором установлены региональные параметры «Английский (США)», то значения параметров, передаваемые на сервер отчетов, будут обрабатываться неправильно.</span><span class="sxs-lookup"><span data-stu-id="62f90-105">For example, if the report server is set to a regional setting of German, but a user is accessing a report via a URL using a browser that is set to English-United States, parameter values that are passed to a report server will be misinterpreted.</span></span>  
  
 <span data-ttu-id="62f90-106">Рассмотрим следующий URL-адрес отчета:</span><span class="sxs-lookup"><span data-stu-id="62f90-106">Consider the following URL to a report:</span></span>  
  
```  
http://myrshost/Reportserver?/SampleReports/Product+Line+Sales&rs:Command=Render&StartDate=4/10/2008&EndDate=11/10/2008  
```  
  
 <span data-ttu-id="62f90-107">В этом случае сервер, на котором установлен региональный стандарт «de-de», создает URL-адрес посредством подписки по электронной почте или через гиперссылку.</span><span class="sxs-lookup"><span data-stu-id="62f90-107">In the above case, the server, running under a culture of "de-de", generates a URL either through an e-mail subscription or a hyperlink.</span></span> <span data-ttu-id="62f90-108">Гиперссылка показывает, что для отчета необходимо передать параметр даты начала (4 октября 2008 г.) и дату окончания (11 октября 2008 г.) в соответствии с немецкими стандартами даты и времени.</span><span class="sxs-lookup"><span data-stu-id="62f90-108">The hyperlink indicates that the report should be parameterized by a start date of October 4, 2008 and an end date of October 11, 2008 according to German date/time standards.</span></span> <span data-ttu-id="62f90-109">Однако пользователь, выполняющий доступ по URL-адресу из браузера, где установлен стандарт «en-us», принудительно вызывает на сервере интерпретацию значений в соответствии со стандартами даты и времени, принятыми в США, в результате чего получаются значения 10 апреля 2008 г. и 10 ноября 2008 г.</span><span class="sxs-lookup"><span data-stu-id="62f90-109">However, a user that is accessing the URL through a browser set to "en-us" forces the server to interpret the values as April 10, 2008 and November 10, 2008 under United States English date/time standards.</span></span> <span data-ttu-id="62f90-110">Чтобы решить эту проблему, можно использовать параметр *rs:ParameterLanguage* , переопределяющий язык браузера для интерпретации параметров:</span><span class="sxs-lookup"><span data-stu-id="62f90-110">To fix the problem, *rs:ParameterLanguage* can be used to override the browser language for parameter interpretation:</span></span>  
  
```  
http://myrshost/Reportserver?/SampleReports/Product+Line+Sales&rs:Command=Render&StartDate=4/10/2008&EndDate=11/10/2008&rs:ParameterLanguage=de-DE  
```  
  
 <span data-ttu-id="62f90-111">Дополнительно к значениям **true** и **false** для параметра доступа по URL-адресу *rc:Parameters*теперь можно передавать значение **Collapsed**.</span><span class="sxs-lookup"><span data-stu-id="62f90-111">In addition to a value of **true** and **false** for the URL access parameter *rc:Parameters*, you can now pass a value of **Collapsed**.</span></span> <span data-ttu-id="62f90-112">Если в URL-адресе используется значение *rc:Parameters*=**Collapsed** , область параметров в средстве просмотра HTML-страниц сворачивается, но пользователь может ее включить.</span><span class="sxs-lookup"><span data-stu-id="62f90-112">When using *rc:Parameters*=**Collapsed** on a URL, the parameter prompt area of the HTML viewer is collapsed out of sight, but can still be toggled by the user.</span></span> <span data-ttu-id="62f90-113">Значение **false** полностью удаляет область параметров с панели инструментов средства просмотра HTML-страниц и делает ее недоступной для пользователя.</span><span class="sxs-lookup"><span data-stu-id="62f90-113">A value of **false** removes the parameter prompt area from the HTML viewer toolbar and makes it unavailable to the end-user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62f90-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="62f90-114">See Also</span></span>  
 <span data-ttu-id="62f90-115">[Доступ по URL-адресу (службы SSRS)](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="62f90-115">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="62f90-116">Ссылка на параметр доступа по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="62f90-116">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
