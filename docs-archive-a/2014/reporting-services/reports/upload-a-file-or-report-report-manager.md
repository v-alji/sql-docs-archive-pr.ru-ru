---
title: Передача файла или отчета (диспетчер отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- publishing reports [Reporting Services], uploading files
- reports [Reporting Services], publishing
- uploading reports [Reporting Services]
- uploading files [Reporting Services]
- files [Reporting Services], uploading
ms.assetid: 79027e11-f4ba-4bfd-bd8c-d334e3da02a1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 119e2b22976dc227e017b81a59b698cf9eb7457f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656996"
---
# <a name="upload-a-file-or-report-report-manager"></a><span data-ttu-id="61fdc-102">Передача файла или отчета (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="61fdc-102">Upload a File or Report (Report Manager)</span></span>
  <span data-ttu-id="61fdc-103">В диспетчере отчетов предусмотрена функция передачи, позволяющая добавлять отчеты, модели и другие файлы к серверу отчетов без публикации этих элементов из клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="61fdc-103">Report Manager provides an upload feature so that you can add reports, models, and other files to a report server without having to publish those items from a client application.</span></span> <span data-ttu-id="61fdc-104">Файлы, переданные из файловой системы, сохраняются на сервере отчетов как элементы.</span><span class="sxs-lookup"><span data-stu-id="61fdc-104">Files that you upload from the file system are stored as items on the report server.</span></span> <span data-ttu-id="61fdc-105">Способ сохранения зависит от типа передаваемого файла.</span><span class="sxs-lookup"><span data-stu-id="61fdc-105">The type of file you upload determines how it is stored:</span></span>  
  
-   <span data-ttu-id="61fdc-106">RDL-файлы сохраняются как отчеты.</span><span class="sxs-lookup"><span data-stu-id="61fdc-106">.rdl files are stored as reports.</span></span>  
  
-   <span data-ttu-id="61fdc-107">SMDL-файлы сохраняются как модели отчетов.</span><span class="sxs-lookup"><span data-stu-id="61fdc-107">.smdl files are stored as report models.</span></span>  
  
-   <span data-ttu-id="61fdc-108">Все другие файлы, включая файлы общих источников данных (RDS), передаются как ресурсы.</span><span class="sxs-lookup"><span data-stu-id="61fdc-108">All other files, including shared data source (.rds) files, are uploaded as resources.</span></span> <span data-ttu-id="61fdc-109">Ресурсы не обрабатываются сервером отчетов, но могут быть просмотрены в диспетчере отчетов, если сервер отчетов поддерживает тип MIME файла.</span><span class="sxs-lookup"><span data-stu-id="61fdc-109">Resources are not processed by a report server, but can be viewed in Report Manager if the report server supports the MIME type of the file.</span></span>  
  
### <a name="to-upload-a-file-or-report"></a><span data-ttu-id="61fdc-110">Передача файла или отчета</span><span class="sxs-lookup"><span data-stu-id="61fdc-110">To upload a file or report</span></span>  
  
1.  <span data-ttu-id="61fdc-111">Запустите [Диспетчер отчетов (службы Reporting Services в основном режиме)](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="61fdc-111">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="61fdc-112">В диспетчер отчетов перейдите на страницу **содержимое** .</span><span class="sxs-lookup"><span data-stu-id="61fdc-112">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="61fdc-113">Перейдите к папке, в которую нужно добавить элемент.</span><span class="sxs-lookup"><span data-stu-id="61fdc-113">Navigate to the folder to which you want to add an item.</span></span>  
  
3.  <span data-ttu-id="61fdc-114">Щелкните **Передать файл**.</span><span class="sxs-lookup"><span data-stu-id="61fdc-114">Click **Upload File**.</span></span>  
  
4.  <span data-ttu-id="61fdc-115">Нажмите кнопку **Обзор** для выбора передаваемого файла.</span><span class="sxs-lookup"><span data-stu-id="61fdc-115">Click **Browse** to select a file to upload.</span></span> <span data-ttu-id="61fdc-116">Можно выгружать файл определения отчета, изображение, документ и любой другой файл, который нужно сделать доступным на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="61fdc-116">You can upload a report definition file, an image, a document, or any file that you want to make available on the report server.</span></span>  
  
5.  <span data-ttu-id="61fdc-117">Введите имя нового элемента.</span><span class="sxs-lookup"><span data-stu-id="61fdc-117">Type a name for the new item.</span></span> <span data-ttu-id="61fdc-118">Имя элемента может включать пробелы, но не может включать зарезервированные символы: ; ?</span><span class="sxs-lookup"><span data-stu-id="61fdc-118">An item name can include spaces, but cannot include the reserved characters: ; ?</span></span> <span data-ttu-id="61fdc-119">: \@ & = +, $/\* \< > |.</span><span class="sxs-lookup"><span data-stu-id="61fdc-119">: \@ & = + , $ / \* \< > |.</span></span>  
  
6.  <span data-ttu-id="61fdc-120">Если нужно заменить существующий элемент новым, установите флажок **Перезаписывать существующие элементы**.</span><span class="sxs-lookup"><span data-stu-id="61fdc-120">If you want to replace an existing item with the new item, select **Overwrite item if it exists**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="61fdc-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="61fdc-121">See Also</span></span>  
 <span data-ttu-id="61fdc-122">[Создание, удаление или изменение общего источника данных &#40;диспетчер отчетов&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="61fdc-122">[Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span></span>  
 <span data-ttu-id="61fdc-123">[Страница "содержимое" &#40;диспетчер отчетов&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="61fdc-123">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="61fdc-124">[Страница "Отправка файла" &#40;диспетчер отчетов&#41;](../upload-file-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="61fdc-124">[Upload File Page &#40;Report Manager&#41;](../upload-file-page-report-manager.md) </span></span>  
 [<span data-ttu-id="61fdc-125">Передача файлов в папку</span><span class="sxs-lookup"><span data-stu-id="61fdc-125">Upload Files to a Folder</span></span>](../report-server/upload-files-to-a-folder.md)  
  
  
