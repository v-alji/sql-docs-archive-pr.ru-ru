---
title: Просмотр журнала проекта | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- viewing project history
- version control services [SQL Server], project history
- projects [SQL Server Management Studio], historical information
- historical information [SQL Server], projects
ms.assetid: be0ea2ac-4a35-429c-9c9e-4001ea9035a4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 85028141050e19e6ed6394a5bb17709ac8f906ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668452"
---
# <a name="view-project-history"></a><span data-ttu-id="76b93-102">Просмотр журнала проекта</span><span class="sxs-lookup"><span data-stu-id="76b93-102">View Project History</span></span>
  <span data-ttu-id="76b93-103">Журнал проекта Visual SourceSafe (VSS) [!INCLUDE[msCoName](../includes/msconame-md.md)] содержит список всех операций, произведенных с каждым файлом проекта, включая создание, добавление, удаление и восстановление файла.</span><span class="sxs-lookup"><span data-stu-id="76b93-103">The history of a [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe (VSS) project includes a list of all the actions taken on each of the project files, including file creation, addition, deletion, and recovery.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76b93-104">Проект Visual SourceSafe более известен как папка сервера управления версиями — место, где на сервере хранится серверная версия файла, контролируемого системой управления версиями. </span><span class="sxs-lookup"><span data-stu-id="76b93-104">A Visual SourceSafe project is more commonly referred to as the source control server folder, the location where the server version of a source-controlled file is stored on the server.</span></span>  
  
 <span data-ttu-id="76b93-105">Для просмотра журнала проекта Visual SourceSafe, к которому относится загруженное в данный момент решение, можно использовать среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76b93-105">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to examine the history of the Visual SourceSafe project to which the currently loaded solution belongs.</span></span> <span data-ttu-id="76b93-106">На основе сведений, показанных как часть журнала проекта, можно получать локальные копии версий файлов, восстанавливать удаленные версии или предоставлять версию файла для общего доступа в разных проектах.</span><span class="sxs-lookup"><span data-stu-id="76b93-106">Based on the information displayed as part of the history of a project, you can retrieve local copies of file versions, restore deleted versions, or share a file version between projects.</span></span>  
  
### <a name="to-view-the-history-of-a-vss-project"></a><span data-ttu-id="76b93-107">Просмотр журнала проекта VSS</span><span class="sxs-lookup"><span data-stu-id="76b93-107">To view the history of a VSS project</span></span>  
  
1.  <span data-ttu-id="76b93-108">Выберите проект в Обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="76b93-108">In Solution Explorer, select the project.</span></span>  
  
2.  <span data-ttu-id="76b93-109">В меню **файл** выберите пункт **система управления версиями** и щелкните **Просмотр журнала**.</span><span class="sxs-lookup"><span data-stu-id="76b93-109">On the **File** menu, point to **Source Control** and click **View History**.</span></span>  
  
3.  <span data-ttu-id="76b93-110">В **History of** \<Project> диалоговом окне Журнал выполните любое из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="76b93-110">In the **History of** \<Project> dialog box, perform any of the following actions:</span></span>  
  
    -   <span data-ttu-id="76b93-111">просмотр копии выделенного файла в системе управления версиями;</span><span class="sxs-lookup"><span data-stu-id="76b93-111">View the source control system's copy of a selected file.</span></span>  
  
    -   <span data-ttu-id="76b93-112">просмотр подробных сведений о выделенном файле;</span><span class="sxs-lookup"><span data-stu-id="76b93-112">View detailed information about a selected file.</span></span>  
  
    -   <span data-ttu-id="76b93-113">получение выделенного файла на локальный диск;</span><span class="sxs-lookup"><span data-stu-id="76b93-113">Retrieve a selected file to your local disk.</span></span>  
  
    -   <span data-ttu-id="76b93-114">извлечение выделенного файла из хранилища;</span><span class="sxs-lookup"><span data-stu-id="76b93-114">Check out a selected file.</span></span>  
  
    -   <span data-ttu-id="76b93-115">предоставление общего доступа к выбранному файлу в двух проектах системы управления версиями;</span><span class="sxs-lookup"><span data-stu-id="76b93-115">Share a selected file between two source control projects.</span></span>  
  
    -   <span data-ttu-id="76b93-116">экспорт отчета по журналу на принтер, в файл или буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="76b93-116">Export the history report to a printer, a file, or the Clipboard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76b93-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="76b93-117">See Also</span></span>  
 <span data-ttu-id="76b93-118">[Задание и получение сведений о версии](../../2014/database-engine/set-and-retrieve-version-information.md) </span><span class="sxs-lookup"><span data-stu-id="76b93-118">[Set and Retrieve Version Information](../../2014/database-engine/set-and-retrieve-version-information.md) </span></span>  
 <span data-ttu-id="76b93-119">[Просмотр состояния файла](../../2014/database-engine/view-file-status.md) </span><span class="sxs-lookup"><span data-stu-id="76b93-119">[View File Status](../../2014/database-engine/view-file-status.md) </span></span>  
 <span data-ttu-id="76b93-120">[Получение файлов](../../2014/database-engine/retrieve-files.md) </span><span class="sxs-lookup"><span data-stu-id="76b93-120">[Retrieve Files](../../2014/database-engine/retrieve-files.md) </span></span>  
 [<span data-ttu-id="76b93-121">Сравнение файлов</span><span class="sxs-lookup"><span data-stu-id="76b93-121">Compare Files</span></span>](../../2014/database-engine/compare-files.md)  
  
  
