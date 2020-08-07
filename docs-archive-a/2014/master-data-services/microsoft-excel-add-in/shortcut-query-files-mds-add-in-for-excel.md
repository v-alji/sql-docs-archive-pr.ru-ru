---
title: Файлы ярлыков запросов (надстройка MDS для Excel) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 1ba0219a-6c40-41fa-aff9-8c8f41ef3220
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fe1bdbdadabe0e6448ed3bdc65316104fb26ba43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730789"
---
# <a name="shortcut-query-files-mds-add-in-for-excel"></a><span data-ttu-id="8adc9-102">Файлы ярлыков запросов (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="8adc9-102">Shortcut Query Files (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="8adc9-103">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]файл ярлыка запроса позволяет быстро устанавливать соединение и загружать часто используемые данные.</span><span class="sxs-lookup"><span data-stu-id="8adc9-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use shortcut query files to quickly connect and load frequently-used data.</span></span> <span data-ttu-id="8adc9-104">Они могут также использоваться в том случае, если необходим обмен данными MDS с другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="8adc9-104">You can also use them when you want to share MDS data with others.</span></span> <span data-ttu-id="8adc9-105">Вместо сохранения и отправки листа по электронной почте можно сохранить файл ярлыка запроса и отправить его.</span><span class="sxs-lookup"><span data-stu-id="8adc9-105">Instead of saving the worksheet and emailing it, you should save a shortcut query file and email that instead.</span></span> <span data-ttu-id="8adc9-106">Это гарантирует, что и вы, и ваш адресат будете получать из репозитория MDS самые актуальные данные.</span><span class="sxs-lookup"><span data-stu-id="8adc9-106">This ensures that you are both connecting to the MDS repository to get the latest data.</span></span>  
  
 <span data-ttu-id="8adc9-107">Файлы ярлыков запросов — это XML-файлы, которые содержат следующие данные.</span><span class="sxs-lookup"><span data-stu-id="8adc9-107">Shortcut query files are XML files that contain information about:</span></span>  
  
-   <span data-ttu-id="8adc9-108">Соединение с репозиторием MDS.</span><span class="sxs-lookup"><span data-stu-id="8adc9-108">The MDS repository connection.</span></span>  
  
-   <span data-ttu-id="8adc9-109">Модель, версия и сущность.</span><span class="sxs-lookup"><span data-stu-id="8adc9-109">The model, version, and entity.</span></span>  
  
-   <span data-ttu-id="8adc9-110">Все фильтры, применявшиеся при создании ярлыка.</span><span class="sxs-lookup"><span data-stu-id="8adc9-110">Any filters that were applied when the shortcut was created.</span></span>  
  
-   <span data-ttu-id="8adc9-111">Порядок столбцов слева направо, заданный при создании ярлыка.</span><span class="sxs-lookup"><span data-stu-id="8adc9-111">The left-to-right order of the columns when the shortcut was created.</span></span>  
  
 <span data-ttu-id="8adc9-112">Эти файлы можно сохранить в списке и выбрать при открытии надстройки.</span><span class="sxs-lookup"><span data-stu-id="8adc9-112">You can save these files in a list and choose from them when you open the Add-in.</span></span> <span data-ttu-id="8adc9-113">Их также можно экспортировать на компьютер или в общую папку или отправить другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="8adc9-113">You can export them to your computer or to a shared location, or you can send them to others.</span></span>  
  
## <a name="queryopener-application"></a><span data-ttu-id="8adc9-114">Приложение QueryOpener</span><span class="sxs-lookup"><span data-stu-id="8adc9-114">QueryOpener Application</span></span>  
 <span data-ttu-id="8adc9-115">Все пользователи, установившие [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] , имеют установленное приложение QueryOpener.</span><span class="sxs-lookup"><span data-stu-id="8adc9-115">All users who install the [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] have an application called QueryOpener installed.</span></span> <span data-ttu-id="8adc9-116">Оно служит для открытия файлов ярлыков запросов в [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8adc9-116">This application is used to open shortcut query files in the [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)].</span></span> <span data-ttu-id="8adc9-117">Если дважды щелкнуть файл ярлыка запроса, то это приложение автоматически открывает его в надстройке.</span><span class="sxs-lookup"><span data-stu-id="8adc9-117">If you double-click a shortcut query file, this application is automatically used to open the file in the Add-in.</span></span>  
  
 <span data-ttu-id="8adc9-118">При открытии файла ярлыка запроса в приложении вам будет предложено сделать соединение безопасным, а это означает, что вы доверяете содержимому из этого источника.</span><span class="sxs-lookup"><span data-stu-id="8adc9-118">When you open a shortcut query file with this application, you are prompted to make the connection a "safe" connection, which means you trust content from this location.</span></span> <span data-ttu-id="8adc9-119">Каждый раз, когда соединение помечается как безопасное, оно добавляется в список.</span><span class="sxs-lookup"><span data-stu-id="8adc9-119">Each time you mark a connection as safe, it is added to a list.</span></span> <span data-ttu-id="8adc9-120">Если нужно очистить этот список, откройте диалоговое окно **Настройки** и в разделе **Серверы, добавленные в список безопасных** нажмите кнопку **Очистить все**.</span><span class="sxs-lookup"><span data-stu-id="8adc9-120">If you want to clear this list, open the **Settings** dialog box and in the **Servers Added to Safe List** section, click **Clear All**.</span></span>  
  
 <span data-ttu-id="8adc9-121">Расположением по умолчанию для приложения является *диск*: \PROGRAM Files\Microsoft SQL Server\120\Master Data сервицес\ексцел Add-In\Microsoft.MasterDataServices.QueryOpener.exe.</span><span class="sxs-lookup"><span data-stu-id="8adc9-121">The default location for the application is *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Excel Add-In\Microsoft.MasterDataServices.QueryOpener.exe.</span></span>  
  
 <span data-ttu-id="8adc9-122">Открывать файлы запросов ярлыков можно двумя способами: импортировать их или двойным щелчком и открывать их автоматически.</span><span class="sxs-lookup"><span data-stu-id="8adc9-122">There are two ways to open shortcut query files: you can import them or you can double-click them and they are opened automatically.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="8adc9-123">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="8adc9-123">Related Tasks</span></span>  
  
|<span data-ttu-id="8adc9-124">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="8adc9-124">Task Description</span></span>|<span data-ttu-id="8adc9-125">Раздел</span><span class="sxs-lookup"><span data-stu-id="8adc9-125">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="8adc9-126">Сохранение содержимого активного листа в виде файла ярлыка запроса.</span><span class="sxs-lookup"><span data-stu-id="8adc9-126">Save the contents of the active worksheet as a shortcut query file.</span></span>|[<span data-ttu-id="8adc9-127">Сохранение файла ярлыка запроса (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="8adc9-127">Save a Shortcut Query File &#40;MDS Add-in for Excel&#41;</span></span>](save-a-shortcut-query-file-mds-add-in-for-excel.md)|  
|<span data-ttu-id="8adc9-128">Отправка файла ярлыка запроса, который представляет содержимое активного листа.</span><span class="sxs-lookup"><span data-stu-id="8adc9-128">Email a shortcut query file that represents the contents of the active worksheet.</span></span>|[<span data-ttu-id="8adc9-129">Отправка файла ярлыка запроса по электронной почте (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="8adc9-129">Email a Shortcut Query File &#40;MDS Add-in for Excel&#41;</span></span>](email-a-shortcut-query-file-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="8adc9-130">См. также</span><span class="sxs-lookup"><span data-stu-id="8adc9-130">Related Content</span></span>  
  
-   [<span data-ttu-id="8adc9-131">Соединения (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="8adc9-131">Connections &#40;MDS Add-in for Excel&#41;</span></span>](connections-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="8adc9-132">Надстройка Master Data Services для Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="8adc9-132">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
-   [<span data-ttu-id="8adc9-133">Безопасность (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="8adc9-133">Security &#40;Master Data Services&#41;</span></span>](../security-master-data-services.md)  
  
  
