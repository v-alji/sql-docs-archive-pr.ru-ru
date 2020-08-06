---
title: Доступ к элементам сервера отчетов с использованием URL-адресов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- referencing URL items for report server access
- URL access [Reporting Services], report servers
ms.assetid: a58b4ca6-129d-45e9-95c7-e9169fe5bba4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6693419490c1b3770ccb41b2645cbdba8996630a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665886"
---
# <a name="access-report-server-items-using-url-access"></a><span data-ttu-id="704f7-102">Доступ к элементам сервера отчетов с использованием URL-адреса</span><span class="sxs-lookup"><span data-stu-id="704f7-102">Access Report Server Items Using URL Access</span></span>
  <span data-ttu-id="704f7-103">В этом разделе описываются методы доступа к элементам каталога различных типов в базе данных сервера отчетов или на сайте SharePoint с использованием строки *rs:Command*=*Value*.</span><span class="sxs-lookup"><span data-stu-id="704f7-103">This topic describes how to access catalog items of different types in a report server data base or in a SharePoint site using *rs:Command*=*Value*.</span></span>  
  
 <span data-ttu-id="704f7-104">Указывать эту строку параметра не обязательно.</span><span class="sxs-lookup"><span data-stu-id="704f7-104">It is not necessary to add this parameter string.</span></span> <span data-ttu-id="704f7-105">Если она не указана, сервер отчетов оценивает тип элемента и выбирает подходящее значение параметра автоматически.</span><span class="sxs-lookup"><span data-stu-id="704f7-105">If you omit it, the report server evaluates the item type and selects the appropriate parameter value automatically.</span></span> <span data-ttu-id="704f7-106">Однако использование строки *rs:Command*=*Value* в URL-адресе улучшает производительность сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="704f7-106">However, using the *rs:Command*=*Value* string in the URL improves the performance of the report server.</span></span>  
  
 <span data-ttu-id="704f7-107">Обратите внимание на синтаксис прокси `_vti_bin` в приведенных далее примерах.</span><span class="sxs-lookup"><span data-stu-id="704f7-107">Note the `_vti_bin` proxy syntax in the examples below.</span></span> <span data-ttu-id="704f7-108">Дополнительные сведения об использовании этого синтаксиса см. в разделе [URL Access Parameter Reference](url-access-parameter-reference.md).</span><span class="sxs-lookup"><span data-stu-id="704f7-108">For more information about using the proxy syntax, see [URL Access Parameter Reference](url-access-parameter-reference.md).</span></span>  
  
## <a name="access-a-report"></a><span data-ttu-id="704f7-109">Доступ к отчету</span><span class="sxs-lookup"><span data-stu-id="704f7-109">Access a Report</span></span>  
 <span data-ttu-id="704f7-110">Чтобы просмотреть отчет в браузере, используйте параметр *RS: команда* = *Render* .</span><span class="sxs-lookup"><span data-stu-id="704f7-110">To view a report in the browser, use the *rs:Command*=*Render* parameter.</span></span> <span data-ttu-id="704f7-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="704f7-111">For example:</span></span>  
  
 <span data-ttu-id="704f7-112">`Native` `http://myrshost/reportserver?/Sales/YearlySalesByCategory&rs:Command=Render`</span><span class="sxs-lookup"><span data-stu-id="704f7-112">`Native` `http://myrshost/reportserver?/Sales/YearlySalesByCategory&rs:Command=Render`</span></span>  
  
 <span data-ttu-id="704f7-113">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/YearlySalesByCategory&rs:Command=Render`</span><span class="sxs-lookup"><span data-stu-id="704f7-113">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/YearlySalesByCategory&rs:Command=Render`</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="704f7-114">Важно, чтобы URL-адрес содержал синтаксис прокси `_vti_bin` для отправки запроса с помощью центра администрирования SharePoint и прокси-сервера HTTP [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="704f7-114">It is important the URL include the `_vti_bin` proxy syntax to route the request through SharePoint and the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] HTTP proxy.</span></span> <span data-ttu-id="704f7-115">Прокси-сервер добавляет в HTTP-запрос контекст, необходимый для обеспечения правильного выполнения отчета для серверов отчетов в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="704f7-115">The proxy adds some context to the HTTP request, context that is required to ensure proper execution of the report for SharePoint mode report servers.</span></span>  
  
## <a name="access-a-resource"></a><span data-ttu-id="704f7-116">Доступ к ресурсу</span><span class="sxs-lookup"><span data-stu-id="704f7-116">Access a Resource</span></span>  
 <span data-ttu-id="704f7-117">Чтобы получить доступ к ресурсу, используйте параметр *RS: Command* = *GetResourceContents* . Если ресурс совместим с браузером, например с изображением, он открывается в браузере.</span><span class="sxs-lookup"><span data-stu-id="704f7-117">To access a resource, use the *rs:Command*=*GetResourceContents* parameter.If the resource is compatible with the browser, such as an image, it is opened in the browser.</span></span> <span data-ttu-id="704f7-118">В противном случае будет предложено открыть или сохранить файл или ресурс на диск.</span><span class="sxs-lookup"><span data-stu-id="704f7-118">Otherwise, you are prompted to open or save the file or resource to disk.</span></span>  
  
 <span data-ttu-id="704f7-119">`Native` `http://myrshost/reportserver?/Sales/StorePicture&rs:Command=GetResourceContents`</span><span class="sxs-lookup"><span data-stu-id="704f7-119">`Native` `http://myrshost/reportserver?/Sales/StorePicture&rs:Command=GetResourceContents`</span></span>  
  
 <span data-ttu-id="704f7-120">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/StorePicture.jpg&rs:Command=GetResourceContents`</span><span class="sxs-lookup"><span data-stu-id="704f7-120">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/StorePicture.jpg&rs:Command=GetResourceContents`</span></span>  
  
## <a name="access-a-data-source"></a><span data-ttu-id="704f7-121">Доступ к источнику данных</span><span class="sxs-lookup"><span data-stu-id="704f7-121">Access a Data Source</span></span>  
 <span data-ttu-id="704f7-122">Для доступа к источнику данных используйте параметр *RS: Command* = *GetDataSourceContents* .</span><span class="sxs-lookup"><span data-stu-id="704f7-122">To access a data source, use the *rs:Command*=*GetDataSourceContents* parameter.</span></span> <span data-ttu-id="704f7-123">Если браузер поддерживает XML, то определение источника данных отображается при условии, что текущий пользователь прошел проверку подлинности и обладает разрешением `Read Contents` для источника данных.</span><span class="sxs-lookup"><span data-stu-id="704f7-123">If your browser supports XML, the data source definition is displayed if you are an authenticated user with `Read Contents` permission on the data source.</span></span> <span data-ttu-id="704f7-124">Пример:</span><span class="sxs-lookup"><span data-stu-id="704f7-124">For example:</span></span>  
  
 <span data-ttu-id="704f7-125">`Native` `http://myrshost/reportserver?/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span><span class="sxs-lookup"><span data-stu-id="704f7-125">`Native` `http://myrshost/reportserver?/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span></span>  
  
 <span data-ttu-id="704f7-126">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span><span class="sxs-lookup"><span data-stu-id="704f7-126">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span></span>  
  
 <span data-ttu-id="704f7-127">XML-структура может иметь вид, аналогичный следующему примеру:</span><span class="sxs-lookup"><span data-stu-id="704f7-127">The XML structure might look similar to the following example:</span></span>  
  
```  
<DataSourceDefinition>  
   <Extension>SQL</Extension>  
   <ConnectString>Provider=SQLOLEDB.1;Integrated Security=SSPI;Persist Security Info=False;Initial Catalog=AdventureWorks2012;Data Source=MYSERVER1;</ConnectString>  
   <CredentialRetrieval>Integrated</CredentialRetrieval>  
   <WindowsCredentials>False</WindowsCredentials>  
   <ImpersonateUser>False</ImpersonateUser>  
   <Prompt />  
   <Enabled>True</Enabled>  
</DataSourceDefinition>  
```  
  
 <span data-ttu-id="704f7-128">Строка соединения возвращается в зависимости от параметра **SecureConnectionLevel** для сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="704f7-128">The connection string is returned based on the **SecureConnectionLevel** setting of the report server.</span></span> <span data-ttu-id="704f7-129">Дополнительные сведения о параметре **SecureConnectionLevel** см. в разделе [Using Secure Web Service Methods](report-server-web-service/net-framework/using-secure-web-service-methods.md).</span><span class="sxs-lookup"><span data-stu-id="704f7-129">For more information about the **SecureConnectionLevel** setting, see [Using Secure Web Service Methods](report-server-web-service/net-framework/using-secure-web-service-methods.md).</span></span>  
  
## <a name="access-the-contents-of-a-folder"></a><span data-ttu-id="704f7-130">Доступ к содержимому папки</span><span class="sxs-lookup"><span data-stu-id="704f7-130">Access the Contents of a Folder</span></span>  
 <span data-ttu-id="704f7-131">Для доступа к содержимому папки используйте параметр *RS: Command* = *дочерние* .</span><span class="sxs-lookup"><span data-stu-id="704f7-131">To access the contents of a folder, use the *rs:Command*=*GetChildren* parameter.</span></span> <span data-ttu-id="704f7-132">Будет возвращена универсальная страница для переходов по папкам, содержащая вложенные папки, отчеты, источники данных и ресурсы запрошенной папки.</span><span class="sxs-lookup"><span data-stu-id="704f7-132">A generic folder-navigation page is returned that contains links to the subfolders, reports, data sources, and resources in the requested folder.</span></span> <span data-ttu-id="704f7-133">Пример:</span><span class="sxs-lookup"><span data-stu-id="704f7-133">For example:</span></span>  
  
 <span data-ttu-id="704f7-134">`Native` `http://myrshost/reportserver?/Sales&rs:Command=GetChildren`</span><span class="sxs-lookup"><span data-stu-id="704f7-134">`Native` `http://myrshost/reportserver?/Sales&rs:Command=GetChildren`</span></span>  
  
 <span data-ttu-id="704f7-135">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales&rs:Command=GetChildren`</span><span class="sxs-lookup"><span data-stu-id="704f7-135">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales&rs:Command=GetChildren`</span></span>  
  
 <span data-ttu-id="704f7-136">Отображаемый пользовательский интерфейс аналогичен режиму просмотра каталогов, используемому на сервере [!INCLUDE[msCoName](../includes/msconame-md.md)] IIS.</span><span class="sxs-lookup"><span data-stu-id="704f7-136">The user interface you see is similar to the directory browsing mode used by [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Information Server (IIS).</span></span> <span data-ttu-id="704f7-137">Номер версии сервера отчетов, включая номер построения, также выводится под списком папок.</span><span class="sxs-lookup"><span data-stu-id="704f7-137">The version number, including the build number, of the report server is also displayed below the folder listing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="704f7-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="704f7-138">See Also</span></span>  
 <span data-ttu-id="704f7-139">[Доступ по URL-адресу &#40;службы SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="704f7-139">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="704f7-140">Ссылка на параметр доступа по URL-адресу</span><span class="sxs-lookup"><span data-stu-id="704f7-140">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
