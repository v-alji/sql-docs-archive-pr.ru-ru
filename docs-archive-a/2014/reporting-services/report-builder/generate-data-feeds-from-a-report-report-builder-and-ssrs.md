---
title: Формирование веб-каналов данных из отчета (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e68baae2-9f2a-4f13-9179-9ac7f29111c5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 340191396aaaa92fe14fe8c3c6b42539a713eb45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654874"
---
# <a name="generate-data-feeds-from-a-report-report-builder-and-ssrs"></a><span data-ttu-id="eff4f-102">Формирование веб-каналов данных из отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="eff4f-102">Generate Data Feeds from a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="eff4f-103">Можно создавать веб-каналы данных, совместимые с Atom, из отчетов, а затем использовать потоки данных в приложениях, таких как [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] клиент, которые могут использовать потоки данных.</span><span class="sxs-lookup"><span data-stu-id="eff4f-103">You can generate Atom-compliant data feeds from reports, and then use the data feeds in applications, such as the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] client, that can consume data feeds.</span></span>  
  
 <span data-ttu-id="eff4f-104">Модуль Atom подготовки отчетов служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] формирует сервисный документ канала Atom, в котором перечислены потоки данных, доступные в отчете.</span><span class="sxs-lookup"><span data-stu-id="eff4f-104">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Atom rendering extension generates an Atom service document that lists the data feeds available from a report.</span></span> <span data-ttu-id="eff4f-105">Этот документ содержит сведения по меньшей мере об одном потоке данных для каждой области данных отчета.</span><span class="sxs-lookup"><span data-stu-id="eff4f-105">The document lists at least one data feed for each data region in the report.</span></span> <span data-ttu-id="eff4f-106">В зависимости от типа области данных и самих данных, которые отображает эта область, службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] могут сформировать из нее несколько потоков данных.</span><span class="sxs-lookup"><span data-stu-id="eff4f-106">Depending on the type of data region and the data that the data region displays, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] might generate multiple data feeds from a data region.</span></span>  
  
 <span data-ttu-id="eff4f-107">Сервисный документ Atom содержит для каждого потока данных уникальный идентификатор, который упоминается в URL-адресе для доступа к содержимому потока данных.</span><span class="sxs-lookup"><span data-stu-id="eff4f-107">Atom service document contains a unique identifier for each the data feed and you use the identifier in a URL to view the content of the data feed.</span></span>  
  
 <span data-ttu-id="eff4f-108">Дополнительные сведения см. в разделе [Формирование веб-каналов данных из отчетов (построитель отчетов и службы SSRS)](generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="eff4f-108">For more information, see [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-generate-an-atom-service-document"></a><span data-ttu-id="eff4f-109">Формирование сервисного документа Atom</span><span class="sxs-lookup"><span data-stu-id="eff4f-109">To generate an Atom service document</span></span>  
  
1.  <span data-ttu-id="eff4f-110">Перейдите с **домашней** страницы диспетчера отчетов к отчету, из которого требуется сформировать потоки данных.</span><span class="sxs-lookup"><span data-stu-id="eff4f-110">From the Report Manager **Home** page, navigate to the report from which you want to generate data feeds.</span></span>  
  
2.  <span data-ttu-id="eff4f-111">Щелкните отчет.</span><span class="sxs-lookup"><span data-stu-id="eff4f-111">Click the report.</span></span>  
  
     <span data-ttu-id="eff4f-112">Отчет выполняется.</span><span class="sxs-lookup"><span data-stu-id="eff4f-112">The report is run.</span></span>  
  
3.  <span data-ttu-id="eff4f-113">На панели инструментов нажмите кнопку «Экспорт в поток данных».</span><span class="sxs-lookup"><span data-stu-id="eff4f-113">On the toolbar, click the Export to Data Feed icon.</span></span>  
  
     <span data-ttu-id="eff4f-114">Появится запрос, что нужно сделать с файлом: сохранить или открыть документ Atom, содержащий поток данных.</span><span class="sxs-lookup"><span data-stu-id="eff4f-114">A message appears asking you if you want to save or open the atom document that contains the data feed.</span></span>  
  
4.  <span data-ttu-id="eff4f-115">Щелкните **Сохранить** , чтобы сохранить документ в файловой системе, или **Открыть** , чтобы просмотреть содержимое документа перед сохранением.</span><span class="sxs-lookup"><span data-stu-id="eff4f-115">Click **Save** to save the document to the file system, or click **Open** to view the document content before saving.</span></span> <span data-ttu-id="eff4f-116">**По умолчанию документ открывается в браузере.**</span><span class="sxs-lookup"><span data-stu-id="eff4f-116">**By default, the document opens in a browser.**</span></span>  
  
5.  <span data-ttu-id="eff4f-117">Укажите расположение для сохранения документа.</span><span class="sxs-lookup"><span data-stu-id="eff4f-117">Browse to the location to save the document.</span></span>  
  
6.  <span data-ttu-id="eff4f-118">При необходимости имя файла можно изменить.</span><span class="sxs-lookup"><span data-stu-id="eff4f-118">Optionally, change the name of the document.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eff4f-119">По умолчанию имя документа совпадает с именем отчета.</span><span class="sxs-lookup"><span data-stu-id="eff4f-119">By default, the document name is the report name.</span></span>  
  
7.  <span data-ttu-id="eff4f-120">Убедитесь, что документ имеет тип **ATOMSVC**, затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="eff4f-120">Verify the document type is **ATOMSVC File**, and then click **Save**.</span></span>  
  
8.  <span data-ttu-id="eff4f-121">При необходимости откройте файл ATOMSVC в браузере либо в текстовом или XML-редакторе.</span><span class="sxs-lookup"><span data-stu-id="eff4f-121">Optionally, open the .atomsvc file in a browser or text or XML editor.</span></span>  
  
### <a name="to-view-an-atom-compliant-data-feed"></a><span data-ttu-id="eff4f-122">Просмотр Atom-совместимого потока данных</span><span class="sxs-lookup"><span data-stu-id="eff4f-122">To view an Atom-compliant data feed</span></span>  
  
1.  <span data-ttu-id="eff4f-123">Если сервисный документ Atom еще не открыт, найдите и откройте его в браузере, например в Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="eff4f-123">If the Atom service document is not already open, locate it and open it in a browser such as Internet Explorer.</span></span>  
  
2.  <span data-ttu-id="eff4f-124">Скопируйте в браузер URL-адрес потока данных, который требуется просмотреть из сервисного документа Atom.</span><span class="sxs-lookup"><span data-stu-id="eff4f-124">Copy the URL of the data feed that you want to view from the Atom service document to the browser.</span></span>  
  
     <span data-ttu-id="eff4f-125">Формат URL-адреса будет следующим:</span><span class="sxs-lookup"><span data-stu-id="eff4f-125">The format of the URL is the following:</span></span>  
  
 `http://<server name>/ReportServer?%2f<ReportName>rs%3aCommand=Render&rs%3aFormat=ATOM&rc%3aDataFeed=<Identifier>`  
  
1.  <span data-ttu-id="eff4f-126">Нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="eff4f-126">Press ENTER.</span></span>  
  
     <span data-ttu-id="eff4f-127">Появится запрос, что нужно сделать с файлом: сохранить или открыть документ Atom, содержащий поток данных.</span><span class="sxs-lookup"><span data-stu-id="eff4f-127">A message appears asking you if you want to save or open the atom document that contains the data feed.</span></span>  
  
2.  <span data-ttu-id="eff4f-128">Щелкните **Сохранить** , чтобы сохранить документ в файловой системе, или **Открыть** , чтобы просмотреть поток данных перед сохранением.</span><span class="sxs-lookup"><span data-stu-id="eff4f-128">Click **Save** to save the document to the file system, or click **Open** to view the data feed before saving.</span></span>  
  
3.  <span data-ttu-id="eff4f-129">Укажите расположение для сохранения документа.</span><span class="sxs-lookup"><span data-stu-id="eff4f-129">Browse to the location to save the document.</span></span>  
  
4.  <span data-ttu-id="eff4f-130">При необходимости имя файла можно изменить.</span><span class="sxs-lookup"><span data-stu-id="eff4f-130">Optionally, change the name of the document.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eff4f-131">По умолчанию имя документа совпадает с именем отчета.</span><span class="sxs-lookup"><span data-stu-id="eff4f-131">By default the document name is the report name.</span></span> <span data-ttu-id="eff4f-132">Если в сервисном документе Atom есть несколько потоков, все они используют по умолчанию одно и то же имя — имя отчета.</span><span class="sxs-lookup"><span data-stu-id="eff4f-132">If the Atom service document has multiple feeds, by default all use the same name, the report name.</span></span> <span data-ttu-id="eff4f-133">Чтобы различать их, дайте им значимые имена.</span><span class="sxs-lookup"><span data-stu-id="eff4f-133">To differentiate them, rename them to use meaningful names.</span></span>  
  
5.  <span data-ttu-id="eff4f-134">Убедитесь, что документ имеет тип **ATOM**, затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="eff4f-134">Verify the document type is **ATOM File**, and then click **Save**.</span></span>  
  
6.  <span data-ttu-id="eff4f-135">При необходимости откройте файл ATOM в браузере либо в текстовом или XML-редакторе.</span><span class="sxs-lookup"><span data-stu-id="eff4f-135">Optionally, open the .atom file in a browser or text editor or XML editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eff4f-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="eff4f-136">See Also</span></span>  
 [<span data-ttu-id="eff4f-137">Экспорт отчетов &#40;построитель отчетов и SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="eff4f-137">Exporting Reports &#40;Report Builder and SSRS&#41;</span></span>](export-reports-report-builder-and-ssrs.md)  
  
  
