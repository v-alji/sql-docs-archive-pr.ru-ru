---
title: Файлы целевой базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.destdbfiles.f1
ms.assetid: f6f90417-86fb-4b8c-a790-0b215c344ef6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d0ab2c0ff39fc728afc17b59f0d4bae076e4022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667826"
---
# <a name="destination-database-files"></a><span data-ttu-id="1f2cd-102">Файлы базы данных-назначения</span><span class="sxs-lookup"><span data-stu-id="1f2cd-102">Destination Database Files</span></span>
  <span data-ttu-id="1f2cd-103">Используйте диалоговое окно **Файлы целевой базы данных** для просмотра или изменения имен файлов базы данных и местоположений на целевом сервере, или для определения положения в сети файла для задачи «Передача базы данных».</span><span class="sxs-lookup"><span data-stu-id="1f2cd-103">Use the **Destination Database Files** dialog box to view or change the database file names and locations on the destination server, or to specify a network file location for the Transfer Database task.</span></span> <span data-ttu-id="1f2cd-104">Дополнительные сведения об этой задаче см. в разделе [Задача "Передача базы данных"](control-flow/transfer-database-task.md).</span><span class="sxs-lookup"><span data-stu-id="1f2cd-104">For more information about this task, see [Transfer Database Task](control-flow/transfer-database-task.md).</span></span>  
  
 <span data-ttu-id="1f2cd-105">Для автоматического заполнения этого диалогового окна именами файлов базы данных и положений на исходном сервере сначала укажите **SourceConnection**, **SourceDatabaseName**и **SourceDatabaseFiles** на странице **Базы данных** диалогового окна **Редактор задачи «Передача базы данных»** .</span><span class="sxs-lookup"><span data-stu-id="1f2cd-105">To automatically populate this dialog box with the database file names and locations on the source server, specify the **SourceConnection**, **SourceDatabaseName**, and **SourceDatabaseFiles** first in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1f2cd-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1f2cd-106">Options</span></span>  
 <span data-ttu-id="1f2cd-107">**Целевой файл**</span><span class="sxs-lookup"><span data-stu-id="1f2cd-107">**Destination File**</span></span>  
 <span data-ttu-id="1f2cd-108">Имена переданных файлов базы данных на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="1f2cd-108">Names of the transferred database files on the destination server.</span></span>  
  
 <span data-ttu-id="1f2cd-109">Введите имя файла или нажмите имя файла для редактирования.</span><span class="sxs-lookup"><span data-stu-id="1f2cd-109">Enter the file name, or click the file name to edit it.</span></span>  
  
 <span data-ttu-id="1f2cd-110">**Целевая папка**</span><span class="sxs-lookup"><span data-stu-id="1f2cd-110">**Destination Folder**</span></span>  
 <span data-ttu-id="1f2cd-111">Папка на целевом сервере, куда должны быть переданы файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="1f2cd-111">Folder on the destination server where the database files will be transferred to.</span></span>  
  
 <span data-ttu-id="1f2cd-112">Введите путь к папке, нажмите путь к папке для редактирования или нажмите кнопку обзора для указания папки, куда необходимо передать файлы базы данных на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="1f2cd-112">Enter the folder path, click the folder path to edit it, or click browse to locate the folder where you want to transfer the database files on the destination server.</span></span>  
  
 <span data-ttu-id="1f2cd-113">**Сетевая общая папка**</span><span class="sxs-lookup"><span data-stu-id="1f2cd-113">**Network File Share**</span></span>  
 <span data-ttu-id="1f2cd-114">Общая сетевая папка на целевом сервере, куда должны быть переданы файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="1f2cd-114">Network shared folder on the destination server where the database files will be transferred to.</span></span> <span data-ttu-id="1f2cd-115">Используйте **Сетевую общую папку** для передачи базы данных в режиме вне сети, указав значение **DatabaseOffline** параметра **Метод** на странице **Базы данных** диалогового окна **Редактор задачи «Передача базы данных»** .</span><span class="sxs-lookup"><span data-stu-id="1f2cd-115">Use **Network file share** when you transfer a database in offline mode by specifying **DatabaseOffline** for **Method** in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="1f2cd-116">Введите размещение сетевой общей папки или нажмите кнопку обзора для ее указания.</span><span class="sxs-lookup"><span data-stu-id="1f2cd-116">Enter the network file share location, or click browse to locate the network file share location.</span></span>  
  
 <span data-ttu-id="1f2cd-117">При передаче базы данных в режиме вне сети файлы базы данных копируются в **Сетевую общую папку** перед тем, как они переданы в расположение **Целевая папка** .</span><span class="sxs-lookup"><span data-stu-id="1f2cd-117">When you transfer a database in offline mode, the database files are copied to the **Network file share** location before they are transferred to the **Destination folder** location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f2cd-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="1f2cd-118">See Also</span></span>  
 <span data-ttu-id="1f2cd-119">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="1f2cd-119">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="1f2cd-120">[Редактор задачи "Перемещение базы данных" &#40;общие&#41;страницы](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="1f2cd-120">[Transfer Database Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="1f2cd-121">Редактор задачи "Передача базы данных" (страница "Базы данных")</span><span class="sxs-lookup"><span data-stu-id="1f2cd-121">Transfer Database Task Editor &#40;Databases Page&#41;</span></span>](../../2014/integration-services/transfer-database-task-editor-databases-page.md)  
  
  
