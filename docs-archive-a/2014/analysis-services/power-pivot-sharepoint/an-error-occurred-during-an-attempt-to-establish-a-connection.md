---
title: 'При попытке установить соединение с внешним источником данных произошла ошибка. Не удалось обновить следующие соединения: данные PowerPivot | Документация Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1b951da1-f62d-43d2-b40b-270a4a9ab92c
author: minewiskan
ms.author: owend
ms.openlocfilehash: eb4329440b69d1bdfdbb96fbcc3926fa000d8877
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732089"
---
# <a name="an-error-occurred-during-an-attempt-to-establish-a-connection-to-the-external-data-source-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="9ea83-103">При попытке установить соединение с внешним источником данных произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="9ea83-103">An error occurred during an attempt to establish a connection to the external data source.</span></span> <span data-ttu-id="9ea83-104">Следующие соединения не удалось обновить: данные PowerPivot</span><span class="sxs-lookup"><span data-stu-id="9ea83-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="9ea83-105">Эта ошибка возникает во время запроса данных PowerPivot на сервере, где не установлен PowerPivot для SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9ea83-105">This error occurs if you query PowerPivot data on a server that does not have PowerPivot for SharePoint installed.</span></span> <span data-ttu-id="9ea83-106">Она также возникает в случае, если службы SQL Server Analysis Services (PowerPivot) остановлены, или при попытке просмотра данных PowerPivot предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="9ea83-106">It also occurs if the SQL Server Analysis Services (PowerPivot) service is stopped, or if you are attempting to view PowerPivot data from an earlier version.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9ea83-107">Подробности</span><span class="sxs-lookup"><span data-stu-id="9ea83-107">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9ea83-108">Применяется к</span><span class="sxs-lookup"><span data-stu-id="9ea83-108">Applies to</span></span>|<span data-ttu-id="9ea83-109">PowerPivot для SharePoint</span><span class="sxs-lookup"><span data-stu-id="9ea83-109">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="9ea83-110">Версия продукта</span><span class="sxs-lookup"><span data-stu-id="9ea83-110">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="9ea83-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ea83-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="9ea83-112">Причина</span><span class="sxs-lookup"><span data-stu-id="9ea83-112">Cause</span></span>|<span data-ttu-id="9ea83-113">Ошибка подключения к данным.</span><span class="sxs-lookup"><span data-stu-id="9ea83-113">The data connection failed.</span></span>|  
|<span data-ttu-id="9ea83-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="9ea83-114">Message Text</span></span>|<span data-ttu-id="9ea83-115">При попытке установить соединение с внешним источником данных произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="9ea83-115">An error occurred during an attempt to establish a connection to the external data source.</span></span> <span data-ttu-id="9ea83-116">Следующие соединения не удалось обновить: данные PowerPivot</span><span class="sxs-lookup"><span data-stu-id="9ea83-116">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9ea83-117">Описание</span><span class="sxs-lookup"><span data-stu-id="9ea83-117">Explanation</span></span>  
 <span data-ttu-id="9ea83-118">Службы Excel возвращают эту ошибку во время запроса данных PowerPivot в книге Excel, которая опубликована на сайте SharePoint, при этом в среде SharePoint не установлен сервер PowerPivot для SharePoint, либо служба SQL Server Analysis Services (PowerPivot) остановлена.</span><span class="sxs-lookup"><span data-stu-id="9ea83-118">Excel Services returns this error when you query PowerPivot data in an Excel workbook that is published to SharePoint, and the SharePoint environment does not have a PowerPivot for SharePoint server, or the SQL Server Analysis Services (PowerPivot) service is stopped.</span></span>  
  
 <span data-ttu-id="9ea83-119">Эта ошибка возникает при срезе или фильтрации данных PowerPivot, когда ядро запросов недоступно.</span><span class="sxs-lookup"><span data-stu-id="9ea83-119">The error occurs when you slice or filter PowerPivot data when the query engine is not available.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9ea83-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="9ea83-120">User Action</span></span>  
 <span data-ttu-id="9ea83-121">Установите PowerPivot для SharePoint или переместите книгу PowerPivot в среду SharePoint, где установлен экземпляр PowerPivot для SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9ea83-121">Install PowerPivot for SharePoint or move the PowerPivot workbook to a SharePoint environment that has PowerPivot for SharePoint installed.</span></span> <span data-ttu-id="9ea83-122">Дополнительные сведения см. в разделе [PowerPivot for SharePoint 2010 Installation](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md).</span><span class="sxs-lookup"><span data-stu-id="9ea83-122">For more information, see [PowerPivot for SharePoint 2010 Installation](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md).</span></span>  
  
 <span data-ttu-id="9ea83-123">Если установлено программное обеспечение, убедитесь, что экземпляр служб SQL Server Analysis Services (PowerPivot) запущен.</span><span class="sxs-lookup"><span data-stu-id="9ea83-123">If the software is installed, verify that the SQL Server Analysis Services (PowerPivot) instance is running.</span></span> <span data-ttu-id="9ea83-124">Установите флажок **Управление службами на сервере** в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="9ea83-124">Check **Manage services on server** in Central Administration.</span></span> <span data-ttu-id="9ea83-125">Кроме того, проверьте консольное приложение «Службы» в разделе «Администрирование».</span><span class="sxs-lookup"><span data-stu-id="9ea83-125">Also check the Services console application in Administrative Tools.</span></span>  
  
 <span data-ttu-id="9ea83-126">Для книг PowerPivot, созданных в версии PowerPivot для Excel SQL Server 2008 R2, необходимо установить поставщик OLE DB служб Analysis Services версии SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="9ea83-126">For PowerPivot workbooks that were created in a SQL Server 2008 R2 version of PowerPivot for Excel, you must install the SQL Server 2008 R2 version of the Analysis Services OLE DB provider.</span></span> <span data-ttu-id="9ea83-127">Эта ошибка возникает, если поставщик установлен, но файл Microsoft.AnalysisServices.ChannelTransport.dll не зарегистрирован.</span><span class="sxs-lookup"><span data-stu-id="9ea83-127">This error will occur if you installed the provider, but did not register the Microsoft.AnalysisServices.ChannelTransport.dll file.</span></span> <span data-ttu-id="9ea83-128">Дополнительные сведения о регистрации файла см. в статье [Установка поставщика OLE DB служб Analysis Services на серверах SharePoint](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span><span class="sxs-lookup"><span data-stu-id="9ea83-128">For more information about file registration, see [Install the Analysis Services OLE DB Provider on SharePoint Servers](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ea83-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="9ea83-129">See Also</span></span>  
 [<span data-ttu-id="9ea83-130">При подключении к данным используется проверка подлинности Windows, а учетные данные пользователя не могут быть делегированы. Не удалось обновить следующие соединения: данные PowerPivot</span><span class="sxs-lookup"><span data-stu-id="9ea83-130">The data connection uses Windows Authentication and user credentials could not be delegated. The following connections failed to refresh: PowerPivot Data</span></span>](the-data-connection-user-could-not-be-delegated.md)  
  
  
