---
title: Страница «передача файла» (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7bb3166f-9374-4449-b66a-ffb77298507d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: de03c6c6bd03cbe083d5e1edfd320264d2cc3bde
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734913"
---
# <a name="upload-file-page-report-manager"></a><span data-ttu-id="7cbb1-102">Страница «Выгрузка файла» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="7cbb1-102">Upload File Page (Report Manager)</span></span>
  <span data-ttu-id="7cbb1-103">Используйте страницу «Передача файла», чтобы опубликовать файл из файловой системы в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-103">Use the Upload File page to publish a file from the file system into the report server database.</span></span> <span data-ttu-id="7cbb1-104">Переданные файлы представлены как элементы иерархии папок сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-104">Uploaded files are represented as items in the report server folder hierarchy.</span></span>  
  
-   <span data-ttu-id="7cbb1-105">Выгруженные файлы с расширением RDL публикуются на сервере отчетов как отчеты.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-105">Uploaded .rdl files are published to a report server as reports.</span></span>  
  
-   <span data-ttu-id="7cbb1-106">Переданные SMDL-файлы публикуются как модели отчетов, если содержат сведения о представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-106">Uploaded .smdl files are published as report models if they contain data source view information.</span></span> <span data-ttu-id="7cbb1-107">Если отсутствует ссылка на представление источника данных, возникает ошибка передачи.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-107">If they are missing a data source view reference, an error occurs during the upload.</span></span> <span data-ttu-id="7cbb1-108">Сведения о представлении источника данных могут отсутствовать, если передать SMDL-файл из [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] проекта модели отчета.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-108">Data source view information might be missing if you upload an .smdl file from a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] report model project.</span></span> <span data-ttu-id="7cbb1-109">В проектах моделей отчетов сведения о представлении источника данных хранятся не в самом SMDL-файле, а в отдельном файле.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-109">In report model projects, data source view information is stored in a separate file rather than in the .smdl file itself.</span></span>  
  
     <span data-ttu-id="7cbb1-110">Файлы моделей, содержащие сведения о представлении источника данных (для которых, таким образом, возможна успешная передача), — это файлы, ранее опубликованные на сервере отчетов, а затем сохраненные в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-110">Model files that do contain data source view information (and can therefore be successfully uploaded) are those that have been previously published to a report server and then saved from the server to a file on the file system.</span></span> <span data-ttu-id="7cbb1-111">Например, если открыть страницу «Общие свойства» модели и щелкнуть **Правка** для открытия модели, можно сохранить эту модель в файл и затем передать его как новую модель на сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-111">If you open the General Properties page of a model and click **Edit** to open the model, you can save it to a file and then upload it as a new model on the report server.</span></span> <span data-ttu-id="7cbb1-112">Переданный после этого SMDL-файл будет содержать все сведения, необходимые для публикации модели.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-112">The .smdl file that you subsequently upload will have all of information that is necessary for model publication.</span></span>  
  
-   <span data-ttu-id="7cbb1-113">Передаваемые файлы всех остальных типов хранятся в виде ресурсов.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-113">All other file types that you upload are stored as resources.</span></span> <span data-ttu-id="7cbb1-114">К ним относятся RDS-файлы, содержащие сведения о соединении с источником данных отчета.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-114">This includes .rds files that contain report data source connection information.</span></span> <span data-ttu-id="7cbb1-115">Передача RDS-файла не приводит к созданию общего элемента источника данных на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-115">Uploading an .rds file does not produce a shared data source item on the report server.</span></span>  
  
 <span data-ttu-id="7cbb1-116">При передаче элемента он помещается в текущую папку.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-116">When you upload an item, it is placed in the current folder.</span></span> <span data-ttu-id="7cbb1-117">После завершения передачи элемент может быть перемещен в другое местоположение.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-117">After the upload is complete, you can move the item to a different location.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7cbb1-118">Эта функция поддерживается не во всех выпусках [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cbb1-118">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7cbb1-119">Перечень функций, поддерживаемых в разных выпусках [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], см. в разделе [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="7cbb1-119">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="7cbb1-120">Навигация</span><span class="sxs-lookup"><span data-stu-id="7cbb1-120">Navigation</span></span>  
 <span data-ttu-id="7cbb1-121">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-121">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-upload-file-page"></a><span data-ttu-id="7cbb1-122">Открытие страницы «Передача файлов»</span><span class="sxs-lookup"><span data-stu-id="7cbb1-122">To open the Upload File page</span></span>  
  
1.  <span data-ttu-id="7cbb1-123">Откройте диспетчер отчетов и перейдите к папке, в которую необходимо передать файл.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-123">Open Report Manager, and navigate to the folder in which you want to upload a file.</span></span>  
  
2.  <span data-ttu-id="7cbb1-124">На панели инструментов нажмите кнопку **Передать файл**.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-124">In the toolbar, click **Upload File**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7cbb1-125">Варианты</span><span class="sxs-lookup"><span data-stu-id="7cbb1-125">Options</span></span>  
 <span data-ttu-id="7cbb1-126">**Файл для передачи**</span><span class="sxs-lookup"><span data-stu-id="7cbb1-126">**File to Upload**</span></span>  
 <span data-ttu-id="7cbb1-127">Отображает полный путь к файлу, который копируется из файловой системы.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-127">Displays the fully qualified path to the file you are copying from the file system.</span></span>  
  
 <span data-ttu-id="7cbb1-128">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="7cbb1-128">**Browse**</span></span>  
 <span data-ttu-id="7cbb1-129">Нажмите, чтобы выбрать файл в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-129">Click to choose a file from the file system.</span></span>  
  
 <span data-ttu-id="7cbb1-130">**имя**;</span><span class="sxs-lookup"><span data-stu-id="7cbb1-130">**Name**</span></span>  
 <span data-ttu-id="7cbb1-131">Введите имя файла в виде, в котором оно будет представлено в пространстве имен сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-131">Type the name of the file, as it will appear in the report server namespace.</span></span> <span data-ttu-id="7cbb1-132">Имя должно содержать хотя бы одну букву или цифру.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-132">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="7cbb1-133">Оно также может включать пробелы и специальные знаки.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-133">It can also include spaces and certain symbols.</span></span> <span data-ttu-id="7cbb1-134">Не используйте символы ; ?</span><span class="sxs-lookup"><span data-stu-id="7cbb1-134">Do not use the characters ; ?</span></span> <span data-ttu-id="7cbb1-135">: \@ & = +, $ \* \< > | "или/при указании имени элемента.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-135">: \@ & = + , $ \* \< > | " or / when specifying an item name.</span></span>  
  
 <span data-ttu-id="7cbb1-136">**Перезаписать элемент (если существует)**</span><span class="sxs-lookup"><span data-stu-id="7cbb1-136">**Overwrite item if it exists**</span></span>  
 <span data-ttu-id="7cbb1-137">Установите этот флажок, если нужно заменить существующий элемент новой версией.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-137">Select this check box if you want to replace an existing item with a newer version.</span></span> <span data-ttu-id="7cbb1-138">Чтобы перезаписать существующую версию, имена нового элемента и существующего элемента должны точно совпадать.</span><span class="sxs-lookup"><span data-stu-id="7cbb1-138">To overwrite an existing version, the name of the new item and the existing item must be an exact match.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cbb1-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="7cbb1-139">See Also</span></span>  
 <span data-ttu-id="7cbb1-140">[Диспетчер отчетов (службы Reporting Services в основном режиме)](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="7cbb1-140">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="7cbb1-141">[Страница "содержимое" &#40;диспетчер отчетов&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="7cbb1-141">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="7cbb1-142">[Справка F1 диспетчер отчетов](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="7cbb1-142">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 [<span data-ttu-id="7cbb1-143">Передача файлов в папку</span><span class="sxs-lookup"><span data-stu-id="7cbb1-143">Upload Files to a Folder</span></span>](report-server/upload-files-to-a-folder.md)  
  
  
