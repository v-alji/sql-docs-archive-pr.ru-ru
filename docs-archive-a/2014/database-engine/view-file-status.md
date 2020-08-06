---
title: Просмотр состояния файла | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- file status information [SQL Server]
- file history [SQL Server]
- version control services [SQL Server], file status
ms.assetid: 96601fc3-64b8-4dd8-9b73-cc6710293eb9
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 4cb1b986873dce2dbdb9fa777a9dc0f38c3ba168
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668454"
---
# <a name="view-file-status"></a><span data-ttu-id="d9dc3-102">Просмотр состояния файла</span><span class="sxs-lookup"><span data-stu-id="d9dc3-102">View File Status</span></span>
  <span data-ttu-id="d9dc3-103">Система управления версиями следит за состоянием всех находящихся под ее контролем элементов.</span><span class="sxs-lookup"><span data-stu-id="d9dc3-103">Source control maintains detailed status information on every source-controlled item.</span></span> <span data-ttu-id="d9dc3-104">Эти сведения можно использовать для определения текущего состояния файла и создания отчета о состоянии элемента.</span><span class="sxs-lookup"><span data-stu-id="d9dc3-104">You can use this information to identify the current state of the file, and to create a status report on the item.</span></span>  
  
 <span data-ttu-id="d9dc3-105">Сведения о состоянии включают:</span><span class="sxs-lookup"><span data-stu-id="d9dc3-105">Status information includes:</span></span>  
  
-   <span data-ttu-id="d9dc3-106">удостоверение пользователя, извлекшего файл;</span><span class="sxs-lookup"><span data-stu-id="d9dc3-106">The identity of the user who has the file checked out.</span></span>  
  
-   <span data-ttu-id="d9dc3-107">номер последней версии выбранного файла;</span><span class="sxs-lookup"><span data-stu-id="d9dc3-107">The latest version number of the selected file.</span></span>  
  
-   <span data-ttu-id="d9dc3-108">дату создания файла этой версии;</span><span class="sxs-lookup"><span data-stu-id="d9dc3-108">The date on which the version was created.</span></span>  
  
-   <span data-ttu-id="d9dc3-109">комментарий пользователя, связанный с любой версией файла;</span><span class="sxs-lookup"><span data-stu-id="d9dc3-109">The user comment associated with any version.</span></span>  
  
-   <span data-ttu-id="d9dc3-110">пути проектов, имеющих общий доступ к этому файлу.</span><span class="sxs-lookup"><span data-stu-id="d9dc3-110">The paths to the projects with which the file is shared.</span></span>  
  
### <a name="to-view-the-status-of-an-item"></a><span data-ttu-id="d9dc3-111">Просмотр состояния элемента</span><span class="sxs-lookup"><span data-stu-id="d9dc3-111">To view the status of an item</span></span>  
  
1.  <span data-ttu-id="d9dc3-112">Выберите элемент в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="d9dc3-112">In Solution Explorer, select an item.</span></span>  
  
2.  <span data-ttu-id="d9dc3-113">В меню **файл** укажите пункт **система управления версиями**и выберите пункт **Свойства SourceSafe**.</span><span class="sxs-lookup"><span data-stu-id="d9dc3-113">On the **File** menu, point to **Source Control**, and click **SourceSafe Properties**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9dc3-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="d9dc3-114">See Also</span></span>  
 <span data-ttu-id="d9dc3-115">[Задание и получение сведений о версии](../../2014/database-engine/set-and-retrieve-version-information.md) </span><span class="sxs-lookup"><span data-stu-id="d9dc3-115">[Set and Retrieve Version Information](../../2014/database-engine/set-and-retrieve-version-information.md) </span></span>  
 <span data-ttu-id="d9dc3-116">[Просмотр журнала проекта](../../2014/database-engine/view-project-history.md) </span><span class="sxs-lookup"><span data-stu-id="d9dc3-116">[View Project History](../../2014/database-engine/view-project-history.md) </span></span>  
 <span data-ttu-id="d9dc3-117">[Получение файлов](../../2014/database-engine/retrieve-files.md) </span><span class="sxs-lookup"><span data-stu-id="d9dc3-117">[Retrieve Files](../../2014/database-engine/retrieve-files.md) </span></span>  
 [<span data-ttu-id="d9dc3-118">Сравнение файлов</span><span class="sxs-lookup"><span data-stu-id="d9dc3-118">Compare Files</span></span>](../../2014/database-engine/compare-files.md)  
  
  
