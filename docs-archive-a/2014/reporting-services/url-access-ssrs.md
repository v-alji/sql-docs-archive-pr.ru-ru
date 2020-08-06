---
title: Доступ по URL-адресу (SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- URL access [Reporting Services]
- links [Reporting Services], URL access
- URL access [Reporting Services], about URL access
- parameters [Reporting Services], URL access
- report servers [Reporting Services], URL access
- hyperlinks [Reporting Services]
ms.assetid: 52c3f2a3-3d6d-4fee-9c46-83f366919398
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf44ea3c15c12f37eebf6e89faf4ff3affd64433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658069"
---
# <a name="url-access-ssrs"></a><span data-ttu-id="9e67b-102">Доступ по URL-адресу (SSRS)</span><span class="sxs-lookup"><span data-stu-id="9e67b-102">URL Access (SSRS)</span></span>
  <span data-ttu-id="9e67b-103">Доступ по URL-адресу сервера отчетов в службах SQL Server Reporting Services (SSRS) позволяет отправлять команды серверу отчетов посредством запроса по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="9e67b-103">URL access of the report server in SQL Server Reporting Services (SSRS) enables you to send commands to a report server through a URL request.</span></span> <span data-ttu-id="9e67b-104">Например, можно настроить подготовку отчета на сервере отчетов, работающем в собственном режиме, или в библиотеке SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9e67b-104">For example, you can customize the rendering of a report on a native mode report server or in a SharePoint library.</span></span> <span data-ttu-id="9e67b-105">Ранее пользователи могли просматривать отчет с использованием определенного набора значений параметров отчета или просматривать только определенную представляющую интерес страницу отчета.</span><span class="sxs-lookup"><span data-stu-id="9e67b-105">You may have viewed the report using a specific set of report parameter values, or you may have been viewing a particular page of interest in the report.</span></span> <span data-ttu-id="9e67b-106">Эти сведения можно инкапсулировать в URL адрес, используя параметры доступа по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="9e67b-106">You can encapsulate this information in the URL using predefined URL access parameters.</span></span> <span data-ttu-id="9e67b-107">Обработку отчета сервером отчетов можно настроить более подробно, внедрив параметры для форматов подготовки к просмотру или для внешнего вида обозревателя отчетов.</span><span class="sxs-lookup"><span data-stu-id="9e67b-107">You can further customize how the report server processes the report by embedding parameters for rendering formats or for the look and feel of the report viewer.</span></span> <span data-ttu-id="9e67b-108">Затем созданный URL-адрес можно непосредственно вставлять в электронное письмо или веб-страницу, чтобы дать возможность другим пользователям просматривать отчет в браузере в том же формате.</span><span class="sxs-lookup"><span data-stu-id="9e67b-108">You can then paste this URL directly into an email or Web page to let others to access your report in the same manner in the browser.</span></span>  
  
 <span data-ttu-id="9e67b-109">Другие действия, которые можно осуществлять посредством доступа по URL-адресу:</span><span class="sxs-lookup"><span data-stu-id="9e67b-109">Other actions you can perform through URL access are:</span></span>  
  
-   <span data-ttu-id="9e67b-110">Отправка команд средству просмотра HTML-страниц, например, для настройки внешнего вида</span><span class="sxs-lookup"><span data-stu-id="9e67b-110">Send commands to the HTML viewer, such as adjusting its look and feel</span></span>  
  
-   <span data-ttu-id="9e67b-111">Составление списка дочерних элементов папки каталога</span><span class="sxs-lookup"><span data-stu-id="9e67b-111">List the children of a catalog folder</span></span>  
  
-   <span data-ttu-id="9e67b-112">Получение XML-определения элемента каталога</span><span class="sxs-lookup"><span data-stu-id="9e67b-112">Retrieve the XML definition of a catalog item</span></span>  
  
-   <span data-ttu-id="9e67b-113">Подготовка определенного моментального снимка журнала отчета</span><span class="sxs-lookup"><span data-stu-id="9e67b-113">Render a specific report history snapshot</span></span>  
  
-   <span data-ttu-id="9e67b-114">Управление сеансами отчетов</span><span class="sxs-lookup"><span data-stu-id="9e67b-114">Manage report sessions</span></span>  
  
 <span data-ttu-id="9e67b-115">Полный список команд и параметров, применимых при доступе через URL-адрес, см. в разделе [Ссылка на параметр доступа по URL-адресу](url-access-parameter-reference.md).</span><span class="sxs-lookup"><span data-stu-id="9e67b-115">For the complete list of commands and settings available through URL access, see [URL Access Parameter Reference](url-access-parameter-reference.md).</span></span>  
  
## <a name="url-access-concepts"></a><span data-ttu-id="9e67b-116">Основные понятия доступа через URL-адрес</span><span class="sxs-lookup"><span data-stu-id="9e67b-116">URL Access Concepts</span></span>  
 <span data-ttu-id="9e67b-117">Запросы по URL-адресу к серверу отчетов содержат параметры, обрабатываемые сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="9e67b-117">URL requests to the report server contain parameters that are processed by the report server.</span></span> <span data-ttu-id="9e67b-118">Способ обработки сервером отчетов запросов по URL-адресу зависит от параметров, префиксов параметров и от типов элементов, включенных в URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="9e67b-118">The way in which the report server handles URL requests depends on the parameters, parameter prefixes, and types of items that are included in the URL.</span></span> <span data-ttu-id="9e67b-119">URL-адреса серверов отчетов соответствуют рекомендациям по форматированию URL-адресов, изложенным в проекте стандарта, разработанном совместно специалистами W3C и IETF.</span><span class="sxs-lookup"><span data-stu-id="9e67b-119">Report server URLs adhere to the URL formatting guidelines as proposed by the joint World Wide Web Consortium W3C/IETF draft standard.</span></span> [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="9e67b-120">по своим функциональным возможностям совместимы с большинством Интернет-браузеров или приложений, соответствующих стандарту адресации с использованием URL.</span><span class="sxs-lookup"><span data-stu-id="9e67b-120">URL functionality is compatible with most Internet browsers or applications that support standard URL addressing.</span></span>  
  
### <a name="url-access-syntax"></a><span data-ttu-id="9e67b-121">Синтаксис доступа по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="9e67b-121">URL Access Syntax</span></span>  
 <span data-ttu-id="9e67b-122">В запросах по URL-адресам могут содержаться несколько параметров, перечисленных в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="9e67b-122">URL requests can contain multiple parameters that are listed in any order.</span></span> <span data-ttu-id="9e67b-123">Параметры разделяются амперсандом (&); пары имя/значение разделяются знаком равенства (=).</span><span class="sxs-lookup"><span data-stu-id="9e67b-123">Parameters are separated by an ampersand (&) and name/value pairs are separated by an equal sign (=).</span></span>  
  
```  
  
rswebserviceurl  
?  
reportpath  
      [&prefix:param=value]...n]  
  
```  
  
### <a name="syntax-description"></a><span data-ttu-id="9e67b-124">Описание синтаксиса</span><span class="sxs-lookup"><span data-stu-id="9e67b-124">Syntax Description</span></span>  
 <span data-ttu-id="9e67b-125">*rswebserviceurl*</span><span class="sxs-lookup"><span data-stu-id="9e67b-125">*rswebserviceurl*</span></span>  
 <span data-ttu-id="9e67b-126">URL-адрес веб-службы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9e67b-126">The Web service URL of the report server.</span></span> <span data-ttu-id="9e67b-127">При работе в собственном режиме это URL-адрес веб-службы экземпляра сервера отчетов, настроенный в диспетчере конфигураций служб Reporting Services (см. статью [Настройка URL-адресов сервера отчетов (диспетчер конфигураций служб SSRS)](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)).</span><span class="sxs-lookup"><span data-stu-id="9e67b-127">For native mode, it is the Web service URL of the report server instance configured in Reporting Services Configuration Manager (see [Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)).</span></span> <span data-ttu-id="9e67b-128">Пример:</span><span class="sxs-lookup"><span data-stu-id="9e67b-128">For example:</span></span>  
  
```  
http://myrshost/reportserver  
https://machine.adventure-works.com/reportserver_MYNAMEDINSTANCE  
```  
  
 <span data-ttu-id="9e67b-129">При работе в режиме интеграции с Sharepoint — URL-адрес прокси-сервера [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] на сайте SharePoint, интегрированном со службами [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e67b-129">For SharePoint integrated mode, it is the URL of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] proxy at a SharePoint site integrated with [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="9e67b-130">Пример:</span><span class="sxs-lookup"><span data-stu-id="9e67b-130">For example:</span></span>  
  
```  
http://myspsite/subsite/_vti_bin/reportserver  
```  
  
> [!TIP]  
>  <span data-ttu-id="9e67b-131">Важно, чтобы URL-адрес содержал синтаксис прокси `_vti_bin` для отправки запроса с помощью центра администрирования SharePoint и прокси-сервера HTTP [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9e67b-131">It is important the URL include the `_vti_bin` proxy syntax to route the request through SharePoint and the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] HTTP proxy.</span></span> <span data-ttu-id="9e67b-132">Прокси-сервер добавляет в HTTP-запрос контекст, необходимый для обеспечения правильного выполнения отчета для серверов отчетов в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9e67b-132">The proxy adds some context to the HTTP request, context that is required to ensure proper execution of the report for SharePoint mode report servers.</span></span>  
  
 <span data-ttu-id="9e67b-133">*pathinfo*</span><span class="sxs-lookup"><span data-stu-id="9e67b-133">*pathinfo*</span></span>  
 <span data-ttu-id="9e67b-134">Имя относительного пути элемента в базе данных сервера отчетов, работающем в собственном режиме, или полный URL-адрес элемента в каталоге SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9e67b-134">The relative path name of the item in the native mode report server database, or the fully qualified URL of the item in a SharePoint catalog.</span></span>  
  
 <span data-ttu-id="9e67b-135">Путь элемента в каталоге.</span><span class="sxs-lookup"><span data-stu-id="9e67b-135">The path of the catalog item.</span></span> <span data-ttu-id="9e67b-136">При работе в собственном режиме — относительный путь элемента в базе данных сервера отчетов, начиная с символа косой черты (`/`).</span><span class="sxs-lookup"><span data-stu-id="9e67b-136">For native mode, it is the relative path of the item in the report server database, beginning with a slash (`/`).</span></span> <span data-ttu-id="9e67b-137">Пример:</span><span class="sxs-lookup"><span data-stu-id="9e67b-137">For example:</span></span>  
  
```  
/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2  
```  
  
 <span data-ttu-id="9e67b-138">При работе в режиме интеграции с Sharepoint — полный URL-адрес элемента в библиотеке SharePoint, включая расширение элемента.</span><span class="sxs-lookup"><span data-stu-id="9e67b-138">For SharePoint integrated mode, it is the fully qualified URL of the item in the SharePoint library, including the item extension.</span></span> <span data-ttu-id="9e67b-139">Пример:</span><span class="sxs-lookup"><span data-stu-id="9e67b-139">For example:</span></span>  
  
```  
http://myspsite/subsite/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2.rdl  
```  
  
 `&`  
 <span data-ttu-id="9e67b-140">Используется для разделения пар имен и значений в параметрах URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="9e67b-140">Used to separate name and value pairs of URL access parameters.</span></span>  
  
 <span data-ttu-id="9e67b-141">**prefix**</span><span class="sxs-lookup"><span data-stu-id="9e67b-141">**prefix**</span></span>  
 <span data-ttu-id="9e67b-142">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="9e67b-142">Optional.</span></span> <span data-ttu-id="9e67b-143">Префикс для параметра доступа по URL-адресу (например, `rs:` или `rc:`), обращающийся к определенному процессу, который выполняется на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="9e67b-143">A prefix for the URL access parameter (for example, `rs:` or `rc:`) that accesses a specific process running within the report server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9e67b-144">Если префикс параметра доступа по URL-адресу не указан, то параметр обрабатывается сервером отчетов как параметр отчета.</span><span class="sxs-lookup"><span data-stu-id="9e67b-144">If a prefix for a URL access parameter is not included, the parameter is processed by the report server as a report parameter.</span></span> <span data-ttu-id="9e67b-145">В параметрах отчета не используется префикс параметров и учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="9e67b-145">Report parameters do not use a parameter prefix and are case-sensitive.</span></span>  
  
 <span data-ttu-id="9e67b-146">**param**</span><span class="sxs-lookup"><span data-stu-id="9e67b-146">**param**</span></span>  
 <span data-ttu-id="9e67b-147">Имя параметра.</span><span class="sxs-lookup"><span data-stu-id="9e67b-147">The parameter name.</span></span>  
  
 <span data-ttu-id="9e67b-148">*value*</span><span class="sxs-lookup"><span data-stu-id="9e67b-148">*value*</span></span>  
 <span data-ttu-id="9e67b-149">Текст URL-адреса, соответствующий значению используемого параметра.</span><span class="sxs-lookup"><span data-stu-id="9e67b-149">URL text corresponding to the value of the parameter being used.</span></span>  
  
 <span data-ttu-id="9e67b-150">**Примечание.** Список доступных параметров для доступа по URL-адресу см. в статье [URL Access Parameter Reference](url-access-parameter-reference.md).</span><span class="sxs-lookup"><span data-stu-id="9e67b-150">**Note:** For a list of the available URL access parameters, see [URL Access Parameter Reference](url-access-parameter-reference.md).</span></span> <span data-ttu-id="9e67b-151">Примеры передачи параметров отчета в URL-адресе см. в разделе [Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="9e67b-151">For examples passing report parameters on the URL, see [Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="9e67b-152">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="9e67b-152">Related Tasks</span></span>  
  
|<span data-ttu-id="9e67b-153">Описания задач</span><span class="sxs-lookup"><span data-stu-id="9e67b-153">Task Descriptions</span></span>|<span data-ttu-id="9e67b-154">Ссылки</span><span class="sxs-lookup"><span data-stu-id="9e67b-154">Links</span></span>|  
|-----------------------|-----------|  
|<span data-ttu-id="9e67b-155">Доступ к элементам сервера отчетов, например, отчетам, общим источникам данных и ресурсам.</span><span class="sxs-lookup"><span data-stu-id="9e67b-155">Access report server items, such as reports, shared data sources, and resources.</span></span>|[<span data-ttu-id="9e67b-156">Доступ к элементам сервера отчетов с использованием URL-адресов</span><span class="sxs-lookup"><span data-stu-id="9e67b-156">Access Report Server Items Using URL Access</span></span>](access-report-server-items-using-url-access.md)|  
|<span data-ttu-id="9e67b-157">Передача отчету параметров отчета.</span><span class="sxs-lookup"><span data-stu-id="9e67b-157">Pass report parameters to a report.</span></span>|[<span data-ttu-id="9e67b-158">Передача параметра отчета в URL-адрес</span><span class="sxs-lookup"><span data-stu-id="9e67b-158">Pass a Report Parameter Within a URL</span></span>](pass-a-report-parameter-within-a-url.md)|  
|<span data-ttu-id="9e67b-159">Задание локали для параметров отчета в строке доступа по URL-адресу, определяющей уникальные для локали форматы дат, валют и т.п.</span><span class="sxs-lookup"><span data-stu-id="9e67b-159">Set the locale of the report parameters in the URL access string, which defines the locale-specific interpretations of dates, currencies, and so on.</span></span>|[<span data-ttu-id="9e67b-160">Выбранный язык для параметров отчета в URL-адресе</span><span class="sxs-lookup"><span data-stu-id="9e67b-160">Set the Language for Report Parameters in a URL</span></span>](set-the-language-for-report-parameters-in-a-url.md)|  
|<span data-ttu-id="9e67b-161">Отправка настроек, уникальных для модуля подготовки отчетов, которые влияют на процесс подготовки.</span><span class="sxs-lookup"><span data-stu-id="9e67b-161">Send rendering extension specific settings that customize how the report is rendered.</span></span>|[<span data-ttu-id="9e67b-162">Указание настроек сведений об устройстве в URL-адресе</span><span class="sxs-lookup"><span data-stu-id="9e67b-162">Specify Device Information Settings in a URL</span></span>](specify-device-information-settings-in-a-url.md)|  
|<span data-ttu-id="9e67b-163">Экспорт отчета непосредственно в формате файла, без просмотра в браузере.</span><span class="sxs-lookup"><span data-stu-id="9e67b-163">Export a report directly to a file format without viewing it in the browser.</span></span>|[<span data-ttu-id="9e67b-164">Export a Report Using URL Access</span><span class="sxs-lookup"><span data-stu-id="9e67b-164">Export a Report Using URL Access</span></span>](export-a-report-using-url-access.md)|  
|<span data-ttu-id="9e67b-165">Открытие отчета и переход непосредственно к месту расположения строки.</span><span class="sxs-lookup"><span data-stu-id="9e67b-165">Open a report and navigate directly to the location of a string.</span></span>|[<span data-ttu-id="9e67b-166">Поиск отчета с использованием URL-адресов</span><span class="sxs-lookup"><span data-stu-id="9e67b-166">Search a Report Using URL Access</span></span>](search-a-report-using-url-access.md)|  
|<span data-ttu-id="9e67b-167">Подготовка определенного моментального снимка журнала отчета.</span><span class="sxs-lookup"><span data-stu-id="9e67b-167">Render a specific report history snapshot.</span></span>|[<span data-ttu-id="9e67b-168">Обработка моментального снимка журнала отчета с помощью URL-адресов</span><span class="sxs-lookup"><span data-stu-id="9e67b-168">Render a Report History Snapshot Using URL Access</span></span>](render-a-report-history-snapshot-using-url-access.md)|  
  
## <a name="see-also"></a><span data-ttu-id="9e67b-169">См. также:</span><span class="sxs-lookup"><span data-stu-id="9e67b-169">See Also</span></span>  
 <span data-ttu-id="9e67b-170">[Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md) </span><span class="sxs-lookup"><span data-stu-id="9e67b-170">[Pass a Report Parameter Within a URL](pass-a-report-parameter-within-a-url.md) </span></span>  
 <span data-ttu-id="9e67b-171">[Справочник по параметрам доступа по URL-адресу](url-access-parameter-reference.md) </span><span class="sxs-lookup"><span data-stu-id="9e67b-171">[URL Access Parameter Reference](url-access-parameter-reference.md) </span></span>  
 <span data-ttu-id="9e67b-172">[Интеграция служб Reporting Services с помощью доступа по URL-адресу](application-integration/integrating-reporting-services-using-url-access.md) </span><span class="sxs-lookup"><span data-stu-id="9e67b-172">[Integrating Reporting Services Using URL Access](application-integration/integrating-reporting-services-using-url-access.md) </span></span>  
 [<span data-ttu-id="9e67b-173">Поиск, просмотр отчетов и управление ими (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="9e67b-173">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
