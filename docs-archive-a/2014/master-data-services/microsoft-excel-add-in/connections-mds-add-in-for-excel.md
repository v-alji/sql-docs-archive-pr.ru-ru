---
title: Соединения (надстройка MDS для Excel) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 2f2b2f9d-7744-460e-83cd-56d34ea70ff0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d4dc41afc6dd59cade9e75475c7cb914d14a8937
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654388"
---
# <a name="connections-mds-add-in-for-excel"></a><span data-ttu-id="b50c8-102">Соединения (настройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="b50c8-102">Connections (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="b50c8-103">Для скачивания данных в [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]необходимо сначала создать соединение.</span><span class="sxs-lookup"><span data-stu-id="b50c8-103">To download data in to the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you must first create a connection.</span></span> <span data-ttu-id="b50c8-104">Соединение — это данные, по которым веб-служба [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] узнает, с какой базой данных MDS нужно устанавливать соединение.</span><span class="sxs-lookup"><span data-stu-id="b50c8-104">A connection is how the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web service knows which MDS database to connect to.</span></span>  
  
 <span data-ttu-id="b50c8-105">Строкой подключения обычно является URL-адрес веб-приложения [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], например http://contoso/mds.</span><span class="sxs-lookup"><span data-stu-id="b50c8-105">The connection string is usually the URL of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application, for example http://contoso/mds.</span></span>  
  
 <span data-ttu-id="b50c8-106">При каждом запуске Excel необходимо устанавливать соединение с репозиторием MDS.</span><span class="sxs-lookup"><span data-stu-id="b50c8-106">Each time you start Excel, you must connect to an MDS repository.</span></span> <span data-ttu-id="b50c8-107">Единственное исключение — когда активный лист уже содержит данные, управляемые MDS.</span><span class="sxs-lookup"><span data-stu-id="b50c8-107">The only exception is when the active spreadsheet already contains MDS-managed data.</span></span> <span data-ttu-id="b50c8-108">В этом случае соединение устанавливается автоматически при каждом обновлении и при каждой публикации данных на листе.</span><span class="sxs-lookup"><span data-stu-id="b50c8-108">In this case, a connection is automatically made each time you refresh or publish data in the sheet.</span></span>  
  
 <span data-ttu-id="b50c8-109">Можно создать несколько подключений.</span><span class="sxs-lookup"><span data-stu-id="b50c8-109">You can create multiple connections.</span></span> <span data-ttu-id="b50c8-110">Последнее соединение, к которому было обращение, считается соединением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b50c8-110">The most recently-accessed connection is considered the default.</span></span>  
  
 <span data-ttu-id="b50c8-111">Одновременно могут быть соединены несколько пользователей.</span><span class="sxs-lookup"><span data-stu-id="b50c8-111">Multiple users can be connected at the same time.</span></span> <span data-ttu-id="b50c8-112">Но если несколько пользователей попытаются опубликовать одни и те же данные, могут возникнуть конфликты.</span><span class="sxs-lookup"><span data-stu-id="b50c8-112">However, conflicts can arise when multiple users attempt to publish the same data.</span></span> <span data-ttu-id="b50c8-113">Дополнительные сведения см. в разделе [Publishing Data &#40;надстройка MDS для Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="b50c8-113">For more information, see [Publishing Data &#40;MDS Add-in for Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md).</span></span>  
  
## <a name="connect-automatically-and-load-frequently-used-data"></a><span data-ttu-id="b50c8-114">Автоматическое соединение и загрузка часто используемых данных</span><span class="sxs-lookup"><span data-stu-id="b50c8-114">Connect Automatically and Load Frequently-Used Data</span></span>  
 <span data-ttu-id="b50c8-115">Если вы всегда соединяетесь с одним и тем же сервером и загружаете один и тот же набор данных, то можно создать файл ярлыка запроса, который содержит сведения о соединении и фильтрах.</span><span class="sxs-lookup"><span data-stu-id="b50c8-115">If you want to always connect to the same server and load the same set of data, you can create shortcut query files, which contain connection and filter information.</span></span> <span data-ttu-id="b50c8-116">Дополнительные сведения о файлах запросов см. в разделе [файлы ярлыков запросов &#40;надстройки MDS для Excel&#41;](shortcut-query-files-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="b50c8-116">For more information about query files, see [Shortcut Query Files &#40;MDS Add-in for Excel&#41;](shortcut-query-files-mds-add-in-for-excel.md).</span></span>  
  
## <a name="data-quality-services"></a><span data-ttu-id="b50c8-117">Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="b50c8-117">Data Quality Services</span></span>  
 <span data-ttu-id="b50c8-118">[!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] включает функциональные возможности служб Data Quality Services, которые помогут сопоставить данные, прежде чем публиковать их в репозитории MDS.</span><span class="sxs-lookup"><span data-stu-id="b50c8-118">The [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] has Data Quality Services functionality to help you match data before publishing it to the MDS repository.</span></span> <span data-ttu-id="b50c8-119">Если при установлении соединения база данных DQS установлена на том же экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , что и база данных MDS, то на ленте появятся кнопки служб DQS.</span><span class="sxs-lookup"><span data-stu-id="b50c8-119">When you make a connection, if a DQS database is installed on the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as the MDS database, you will be able to view DQS buttons on the ribbon.</span></span> <span data-ttu-id="b50c8-120">Если база данных DQS_Main не существует на этом экземпляре, то эти кнопки не отображаются и функции качества данных будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="b50c8-120">If the DQS_Main database does not exist on the instance, these buttons are not displayed and data quality functionality is not available.</span></span>  
  
## <a name="troubleshooting-connections"></a><span data-ttu-id="b50c8-121">Устранение неполадок с соединениями</span><span class="sxs-lookup"><span data-stu-id="b50c8-121">Troubleshooting Connections</span></span>  
 <span data-ttu-id="b50c8-122">Если при подключении к MDS возникнут проблемы, см [https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx](https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx) . Советы по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="b50c8-122">When you connect to MDS, if you encounter any issues see [https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx](https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx) for troubleshooting tips.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="b50c8-123">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="b50c8-123">Related Tasks</span></span>  
  
|<span data-ttu-id="b50c8-124">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="b50c8-124">Task Description</span></span>|<span data-ttu-id="b50c8-125">Раздел</span><span class="sxs-lookup"><span data-stu-id="b50c8-125">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="b50c8-126">Установите соединение с базой данных служб [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b50c8-126">Create a connection to a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span>|[<span data-ttu-id="b50c8-127">Соединение с репозиторием MDS (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="b50c8-127">Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;</span></span>](connect-to-an-mds-repository-mds-add-in-for-excel.md)|  
|<span data-ttu-id="b50c8-128">Загрузка данных MDS в Excel.</span><span class="sxs-lookup"><span data-stu-id="b50c8-128">Load MDS data into Excel.</span></span>|[<span data-ttu-id="b50c8-129">Загрузка данных из MDS в Excel</span><span class="sxs-lookup"><span data-stu-id="b50c8-129">Load Data from MDS into Excel</span></span>](export-data-to-excel-from-master-data-services.md)|  
|<span data-ttu-id="b50c8-130">Фильтрация данных MDS перед их загрузкой в Excel.</span><span class="sxs-lookup"><span data-stu-id="b50c8-130">Filter MDS data before you load it into Excel.</span></span>|[<span data-ttu-id="b50c8-131">Фильтровать данные перед загрузкой &#40;надстройка MDS для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="b50c8-131">Filter Data before Loading &#40;MDS Add-in for Excel&#41;</span></span>](filter-data-before-exporting-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="b50c8-132">См. также</span><span class="sxs-lookup"><span data-stu-id="b50c8-132">Related Content</span></span>  
  
-   [<span data-ttu-id="b50c8-133">Загрузка надстройка MDS для Excel &#40;данных&#41;</span><span class="sxs-lookup"><span data-stu-id="b50c8-133">Loading Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="b50c8-134">Файлы ярлыков запросов (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="b50c8-134">Shortcut Query Files &#40;MDS Add-in for Excel&#41;</span></span>](shortcut-query-files-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="b50c8-135">Надстройка Master Data Services для Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="b50c8-135">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
  
