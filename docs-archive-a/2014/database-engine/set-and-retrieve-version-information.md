---
title: Задание и получение сведений о версии | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- historical information [SQL Server]
- source controls [SQL Server Management Studio], version information
- retrieving version information
- current file version information
- version control services [SQL Server], retrieving version information
- version control services [SQL Server], setting version information
- status information [SQL Server], source control files
- historical information [SQL Server], source control files
ms.assetid: c3f253c4-4e3d-48e8-8d90-bd6ee899faf7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: eff3d40ba9b663ba8611508c5b9f0c9961005b81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728666"
---
# <a name="set-and-retrieve-version-information"></a><span data-ttu-id="51426-102">Задание и получение сведений о версии</span><span class="sxs-lookup"><span data-stu-id="51426-102">Set and Retrieve Version Information</span></span>
  <span data-ttu-id="51426-103">Сведения о версии содержат журнал изменений и текущее состояние файла в системе управления версиями.</span><span class="sxs-lookup"><span data-stu-id="51426-103">Version information includes the history and current status of a source-controlled file.</span></span> <span data-ttu-id="51426-104">Для каждого файла, контролируемого системой управления версиями, [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe создает исчерпывающий журнал, с помощью которого с течением времени можно проследить развитие одного или нескольких файлов.</span><span class="sxs-lookup"><span data-stu-id="51426-104">For every source-controlled file, [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe maintains a comprehensive history, so you can track the evolution of one or more files over time.</span></span> <span data-ttu-id="51426-105">Эти сведения можно также использовать для получения локальной копии версии файла или сравнения двух любых версий файла.</span><span class="sxs-lookup"><span data-stu-id="51426-105">You can also use this information to retrieve a local copy of any version of the file or to compare any two file versions.</span></span>  
  
 <span data-ttu-id="51426-106">Журнал файла содержит:</span><span class="sxs-lookup"><span data-stu-id="51426-106">The history of a file includes:</span></span>  
  
-   <span data-ttu-id="51426-107">номер версии, определяющий его место в последовательности других версий данного файла;</span><span class="sxs-lookup"><span data-stu-id="51426-107">The version number, which identifies its sequence among other versions of the same file.</span></span>  
  
-   <span data-ttu-id="51426-108">выполненные операции;</span><span class="sxs-lookup"><span data-stu-id="51426-108">The action performed.</span></span> <span data-ttu-id="51426-109">отслеживаются операции создания, возврата и удаления файла;</span><span class="sxs-lookup"><span data-stu-id="51426-109">Tracked operations include file creation, check in, and deletion.</span></span>  
  
-   <span data-ttu-id="51426-110">имя пользователя, выполнявшего операции с использованием файла;</span><span class="sxs-lookup"><span data-stu-id="51426-110">The user name of the person who performed an action involving the file.</span></span>  
  
-   <span data-ttu-id="51426-111">дату и время выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="51426-111">The date and time when the operation was performed.</span></span>  
  
 <span data-ttu-id="51426-112">Приложение Visual SourceSafe также сохраняет сведения о состоянии загруженного в данный момент решения.</span><span class="sxs-lookup"><span data-stu-id="51426-112">Visual SourceSafe also maintains current status information on the currently loaded solution.</span></span> <span data-ttu-id="51426-113">Эти сведения обеспечивают создание моментального снимка текущего состояния файла, включая:</span><span class="sxs-lookup"><span data-stu-id="51426-113">This information provides a snapshot of the current state of the file, including:</span></span>  
  
-   <span data-ttu-id="51426-114">удостоверение пользователя, извлекшего файл;</span><span class="sxs-lookup"><span data-stu-id="51426-114">The identity of the user who has the file checked out.</span></span>  
  
-   <span data-ttu-id="51426-115">номер последней версии выбранного файла;</span><span class="sxs-lookup"><span data-stu-id="51426-115">The latest version number of the selected file.</span></span>  
  
-   <span data-ttu-id="51426-116">дату создания версии;</span><span class="sxs-lookup"><span data-stu-id="51426-116">The date when the version was created.</span></span>  
  
-   <span data-ttu-id="51426-117">примечание пользователя, связанное с версией;</span><span class="sxs-lookup"><span data-stu-id="51426-117">The user comment associated with the version.</span></span>  
  
-   <span data-ttu-id="51426-118">пути проектов, имеющих общий доступ к этому файлу.</span><span class="sxs-lookup"><span data-stu-id="51426-118">The paths to the projects with which the file is shared.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="51426-119">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="51426-119">In This Section</span></span>  
  
-   [<span data-ttu-id="51426-120">Просмотр журнал файла</span><span class="sxs-lookup"><span data-stu-id="51426-120">View File History</span></span>](../../2014/database-engine/view-file-history.md)  
  
-   [<span data-ttu-id="51426-121">Просмотр журнала проекта</span><span class="sxs-lookup"><span data-stu-id="51426-121">View Project History</span></span>](../../2014/database-engine/view-project-history.md)  
  
-   [<span data-ttu-id="51426-122">Просмотр состояния файла</span><span class="sxs-lookup"><span data-stu-id="51426-122">View File Status</span></span>](../../2014/database-engine/view-file-status.md)  
  
-   [<span data-ttu-id="51426-123">Получение файлов</span><span class="sxs-lookup"><span data-stu-id="51426-123">Retrieve Files</span></span>](../../2014/database-engine/retrieve-files.md)  
  
-   [<span data-ttu-id="51426-124">Указание версии в качестве последней</span><span class="sxs-lookup"><span data-stu-id="51426-124">Specify a Version as the Latest Version</span></span>](../../2014/database-engine/specify-a-version-as-the-latest-version.md)  
  
-   [<span data-ttu-id="51426-125">Сравнение файлов</span><span class="sxs-lookup"><span data-stu-id="51426-125">Compare Files</span></span>](../../2014/database-engine/compare-files.md)  
  
-   [<span data-ttu-id="51426-126">Общий доступ к файлам</span><span class="sxs-lookup"><span data-stu-id="51426-126">Share Files</span></span>](../../2014/database-engine/share-files.md)  
  
-   [<span data-ttu-id="51426-127">Создание журналов и отчетов состояния</span><span class="sxs-lookup"><span data-stu-id="51426-127">Create History and Status Reports</span></span>](../../2014/database-engine/create-history-and-status-reports.md)  
  
## <a name="see-also"></a><span data-ttu-id="51426-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="51426-128">See Also</span></span>  
 [<span data-ttu-id="51426-129">Основы системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="51426-129">Source Control Basics</span></span>](../../2014/database-engine/source-control-basics.md)  
  
  
