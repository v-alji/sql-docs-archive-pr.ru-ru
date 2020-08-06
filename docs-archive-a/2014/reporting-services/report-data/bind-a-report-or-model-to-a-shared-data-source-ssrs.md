---
title: Привязка отчета или модели к общему источнику данных (службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- shared data sources [Reporting Services]
- data sources [Reporting Services], shared
ms.assetid: 23cc15f2-2883-48e2-bc6c-fa0ab61a2e21
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 596caba042d476173b3c49d1ad18e79d0827fe89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730201"
---
# <a name="bind-a-report-or-model-to-a-shared-data-source-ssrs"></a><span data-ttu-id="39768-102">Привязка отчета или модели к общему источнику данных (SSRS)</span><span class="sxs-lookup"><span data-stu-id="39768-102">Bind a Report or Model to a Shared Data Source (SSRS)</span></span>
  <span data-ttu-id="39768-103">В некоторых ситуациях, например при переносе отчета или модели с тестового сервера на рабочий, бывает необходимо сохранить файл на локальном компьютере, а затем передать его на другой сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="39768-103">In some situations, such as when you move a report or model from a test server to a production server, you might want to save the file to your local computer and then upload it to a different report server.</span></span> <span data-ttu-id="39768-104">При передаче отчета или модели на новый сервер необходимо повторно привязать его к общему источнику данных, находящемуся на новом сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="39768-104">When you upload the report or model to the new server, you need to rebind it to a shared data source that is stored on the new report server.</span></span> <span data-ttu-id="39768-105">Если повторную привязку отчета или модели не выполнить, они не будут работоспособны при обращении к ним с нового сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="39768-105">If you don't rebind the report or model, it will not work correctly when accessed from the new report server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="39768-106">Перед повторной привязкой отчета или модели к общему источнику данных этот источник должен уже существовать на сервере отчетов или в библиотеке SharePoint.</span><span class="sxs-lookup"><span data-stu-id="39768-106">Before rebinding a report or model to a shared data source, the data source must already exist on the report server or SharePoint library.</span></span> <span data-ttu-id="39768-107">Дополнительные сведения об источниках данных см. в статье [Создание, изменение и удаление общих источников данных (службы SSRS)](create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="39768-107">For more information about data sources, see [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
### <a name="to-bind-a-report-or-model-to-a-shared-data-source-on-a-report-server-running-in-native-mode"></a><span data-ttu-id="39768-108">Привязка отчета или модели к общему источнику данных на сервере отчетов, работающем в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="39768-108">To bind a report or model to a shared data source on a report server running in native mode</span></span>  
  
1.  <span data-ttu-id="39768-109">Щелкните имя отчета или модели, передаваемых на сервер, в **диспетчере отчетов**.</span><span class="sxs-lookup"><span data-stu-id="39768-109">In **Report Manager**, click the name of the report or model that you uploaded to the server.</span></span>  
  
     <span data-ttu-id="39768-110">Откроется вкладка «Свойства».</span><span class="sxs-lookup"><span data-stu-id="39768-110">The Properties tab opens.</span></span>  
  
2.  <span data-ttu-id="39768-111">Щелкните **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="39768-111">Click **Data Sources**.</span></span>  
  
3.  <span data-ttu-id="39768-112">Нажмите кнопку **Обзор**и перейдите к источнику данных, с которым необходимо связать отчет или модель.</span><span class="sxs-lookup"><span data-stu-id="39768-112">Click **Browse**, and then navigate to the data source to which you want to bind the report or model.</span></span>  
  
4.  <span data-ttu-id="39768-113">Выберите источник данных и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="39768-113">Select the data source and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="39768-114">Щелкните **Применить**.</span><span class="sxs-lookup"><span data-stu-id="39768-114">Click **Apply**.</span></span>  
  
     <span data-ttu-id="39768-115">Теперь отчет или модель привязаны к выбранному источнику данных.</span><span class="sxs-lookup"><span data-stu-id="39768-115">The report or model is now bound to the data source that you selected.</span></span>  
  
### <a name="to-bind-a-report-or-model-to-a-shared-data-source-on-a-report-server-running-in-sharepoint-integrated-mode"></a><span data-ttu-id="39768-116">Привязка отчета или модели к общему источнику данных на сервере отчетов, работающем в режиме интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="39768-116">To bind a report or model to a shared data source on a report server running in SharePoint integrated mode</span></span>  
  
1.  <span data-ttu-id="39768-117">Если библиотека еще не открыта, щелкните ее имя на панели «Быстрый запуск».</span><span class="sxs-lookup"><span data-stu-id="39768-117">If the library is not already open, click its name on the Quick Launch bar.</span></span> <span data-ttu-id="39768-118">Если имя библиотеки не отображается, щелкните **Просмотреть содержимое всего сайта**и выберите имя библиотеки.</span><span class="sxs-lookup"><span data-stu-id="39768-118">If the name of your library does not appear, click **View All Site Content**, and then click the name of your library.</span></span>  
  
2.  <span data-ttu-id="39768-119">Укажите отчет или модель и щелкните стрелку вниз.</span><span class="sxs-lookup"><span data-stu-id="39768-119">Point to the report or model and click the down arrow.</span></span>  
  
3.  <span data-ttu-id="39768-120">Щелкните **Управление источниками данных**.</span><span class="sxs-lookup"><span data-stu-id="39768-120">Click **Manage Data Sources**.</span></span>  
  
4.  <span data-ttu-id="39768-121">Щелкните **источник_данных_1**.</span><span class="sxs-lookup"><span data-stu-id="39768-121">Click **dataSource1**.</span></span>  
  
5.  <span data-ttu-id="39768-122">Убедитесь, что в области **Тип соединения** выбран вариант **Общий источник данных** .</span><span class="sxs-lookup"><span data-stu-id="39768-122">In the **Connection Type** area, verify that **Shared data source** is selected.</span></span>  
  
6.  <span data-ttu-id="39768-123">В области **Связь с источником данных** нажмите кнопку с многоточием (...).</span><span class="sxs-lookup"><span data-stu-id="39768-123">In the **Data Source Link** area, click the ellipsis (...) button.</span></span>  
  
7.  <span data-ttu-id="39768-124">Найдите источник данных, который необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="39768-124">Locate the data source you want to use.</span></span>  
  
8.  <span data-ttu-id="39768-125">Выберите источник данных и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="39768-125">Select the data source and **click OK**.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. <span data-ttu-id="39768-126">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="39768-126">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39768-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="39768-127">See Also</span></span>  
 <span data-ttu-id="39768-128">[Отправка &#40;диспетчер отчетов файла или отчета&#41;](../reports/upload-a-file-or-report-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="39768-128">[Upload a File or Report &#40;Report Manager&#41;](../reports/upload-a-file-or-report-report-manager.md) </span></span>  
 <span data-ttu-id="39768-129">[Отправка документов в библиотеку SharePoint &#40;Reporting Services в режиме интеграции с SharePoint&#41;](../upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md) </span><span class="sxs-lookup"><span data-stu-id="39768-129">[Upload Documents to a SharePoint Library &#40;Reporting Services in SharePoint Mode&#41;](../upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md) </span></span>  
 <span data-ttu-id="39768-130">[Создание общих источников данных и управление ими &#40;Reporting Services в режиме интеграции с SharePoint&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md) </span><span class="sxs-lookup"><span data-stu-id="39768-130">[Create and Manage Shared Data Sources &#40;Reporting Services in SharePoint Integrated Mode&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md) </span></span>  
 <span data-ttu-id="39768-131">[Создание, удаление или изменение общего источника данных &#40;диспетчер отчетов&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="39768-131">[Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span></span>  
 <span data-ttu-id="39768-132">[Подключения к данным, источники данных и строки подключения в Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="39768-132">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="39768-133">Источники данных, поддерживаемые службами Reporting Services (SSRS)</span><span class="sxs-lookup"><span data-stu-id="39768-133">Data Sources Supported by Reporting Services &#40;SSRS&#41;</span></span>](../create-deploy-and-manage-mobile-and-paginated-reports.md)  
  
  
