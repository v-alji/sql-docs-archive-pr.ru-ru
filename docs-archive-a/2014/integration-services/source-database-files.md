---
title: Файлы базы данных источника | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.sourcedbfiles.f1
ms.assetid: 7dc6bfeb-37c1-45e8-a705-a87564922265
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 31f0c0e0c633ead0c093bdc8e1f20c9b8f23cc28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751240"
---
# <a name="source-database-files"></a><span data-ttu-id="58f1c-102">Файлы базы данных-источника</span><span class="sxs-lookup"><span data-stu-id="58f1c-102">Source database files</span></span>
  <span data-ttu-id="58f1c-103">Диалоговое окно **Файлы базы данных-источника** используется для просмотра имен файлов базы данных и их размещения на исходном сервере, а также для указания общей сетевой папки в задаче «Передача базы данных».</span><span class="sxs-lookup"><span data-stu-id="58f1c-103">Use the **Source Database Files** dialog box to view the database file names and locations on the source server, or to specify a network file share location for the Transfer Database task.</span></span> <span data-ttu-id="58f1c-104">Дополнительные сведения об этой задаче см. в разделе [Задача "Передача базы данных"](control-flow/transfer-database-task.md).</span><span class="sxs-lookup"><span data-stu-id="58f1c-104">For more information about this task, see [Transfer Database Task](control-flow/transfer-database-task.md).</span></span>  
  
 <span data-ttu-id="58f1c-105">Чтобы наполнить диалоговое окно именами файлов базы данных и ресурсов исходного сервера, сначала укажите параметры **SourceConnection** (Подключение к источнику) и **SourceDatabaseName** (Имя базы данных-источника) на странице **Базы данных** диалогового окна **Редактор задачи «Передача базы данных»** .</span><span class="sxs-lookup"><span data-stu-id="58f1c-105">To populate this dialog box with the database file names and locations on the source server, specify the **SourceConnection** and **SourceDatabaseName** first in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="58f1c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="58f1c-106">Options</span></span>  
 <span data-ttu-id="58f1c-107">**Исходный файл**</span><span class="sxs-lookup"><span data-stu-id="58f1c-107">**Source File**</span></span>  
 <span data-ttu-id="58f1c-108">Имена файлов базы данных на исходном сервере, которые будут перенесены.</span><span class="sxs-lookup"><span data-stu-id="58f1c-108">Database file names on the source server that will be transferred.</span></span> <span data-ttu-id="58f1c-109">Параметр**Исходный файл** доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="58f1c-109">**Source File** is read only.</span></span>  
  
 <span data-ttu-id="58f1c-110">**Исходная папка**</span><span class="sxs-lookup"><span data-stu-id="58f1c-110">**Source Folder**</span></span>  
 <span data-ttu-id="58f1c-111">Папка на исходном сервере, в которой хранятся файлы базы данных, подлежащей переносу.</span><span class="sxs-lookup"><span data-stu-id="58f1c-111">Folder on the source server where the database files to be transferred reside.</span></span> <span data-ttu-id="58f1c-112">Параметр**Исходная папка** доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="58f1c-112">**Source Folder** is read only.</span></span>  
  
 <span data-ttu-id="58f1c-113">**Сетевая общая папка**</span><span class="sxs-lookup"><span data-stu-id="58f1c-113">**Network File Share**</span></span>  
 <span data-ttu-id="58f1c-114">Сетевая общая папка на исходном сервере, из которой будут перенесены файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="58f1c-114">Network shared folder on the source server from where the database files will be transferred.</span></span> <span data-ttu-id="58f1c-115">Параметр **Сетевая общая папка** используется при переносе базы данных в режиме вне сети путем задания значения **DatabaseOffline** (Автономный режим базы данных) параметру **Метод** на странице **Базы данных** диалогового окна **Редактор задачи «Передача базы данных»** .</span><span class="sxs-lookup"><span data-stu-id="58f1c-115">Use **Network File Share** when you transfer a database in offline mode by specifying **DatabaseOffline** for **Method** in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="58f1c-116">Введите путь к общей сетевой папке или нажмите кнопку обзора **(...)** , чтобы найти эту папку.</span><span class="sxs-lookup"><span data-stu-id="58f1c-116">Enter the network file share location, or click the browse button **(...)** to locate the network file share location.</span></span>  
  
 <span data-ttu-id="58f1c-117">При переносе базы данных в режиме вне сети файлы базы данных копируются в заданную параметром **Сетевая общая папка** папку на исходном сервере, прежде чем они будут перенесены на целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="58f1c-117">When you transfer a database in offline mode, the database files are copied to the **Network file share** location on the source server before they are transferred to the destination server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58f1c-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="58f1c-118">See Also</span></span>  
 <span data-ttu-id="58f1c-119">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="58f1c-119">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="58f1c-120">[Редактор задачи "Перемещение базы данных" &#40;общие&#41;страницы](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="58f1c-120">[Transfer Database Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="58f1c-121">Редактор задачи "Передача базы данных" (страница "Базы данных")</span><span class="sxs-lookup"><span data-stu-id="58f1c-121">Transfer Database Task Editor &#40;Databases Page&#41;</span></span>](../../2014/integration-services/transfer-database-task-editor-databases-page.md)  
  
  
