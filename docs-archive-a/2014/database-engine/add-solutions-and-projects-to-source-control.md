---
title: Добавление решений и проектов в систему управления версиями | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], source controls
- solutions [SQL Server Management Studio], source controls
- source controls [SQL Server Management Studio], solutions
- source controls [SQL Server Management Studio], projects
ms.assetid: 3eaed80e-6f55-42ea-a964-aca31c09d055
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5256795677f4e8ce4249737d25d3ded1c4cd69c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730910"
---
# <a name="add-solutions-and-projects-to-source-control"></a><span data-ttu-id="259dd-102">Добавление решений и проектов в систему управления версиями</span><span class="sxs-lookup"><span data-stu-id="259dd-102">Add Solutions and Projects to Source Control</span></span>
  <span data-ttu-id="259dd-103">При добавлении решения в систему управления версиями это решение становится частью динамического архива истории версий, созданного и поддерживаемого поставщиком управления версиями.</span><span class="sxs-lookup"><span data-stu-id="259dd-103">When you add a solution to source control, the solution becomes part of a dynamic versioning archive created and maintained by the source control provider.</span></span> <span data-ttu-id="259dd-104">Каждый раз, когда кто-либо возвращает новую версию решения, она становится частью архива, доступной другим пользователям системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="259dd-104">Each time someone checks in a new version of the solution, that version becomes part of the archive and is available to other source control users.</span></span>  
  
 <span data-ttu-id="259dd-105">При добавлении решения в систему управления версиями также запускается система централизованного управления файлами.</span><span class="sxs-lookup"><span data-stu-id="259dd-105">Adding a solution to source control also starts a system of centralized file management.</span></span> <span data-ttu-id="259dd-106">Поставщики управления версиями, такие как [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, управляют доступом к контролируемым системой элементам; клиенты системы управления версиями не могут осуществлять запись в локальные копии управляемых системой файлов без их извлечения.</span><span class="sxs-lookup"><span data-stu-id="259dd-106">Source control providers, such as [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, control access to source-controlled items; source control clients cannot write to local copies of source-controlled files without checking them out.</span></span>  
  
 <span data-ttu-id="259dd-107">В следующей таблице описаны подразделы, содержащиеся в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="259dd-107">The following table describes the topics in this section.</span></span>  
  
|<span data-ttu-id="259dd-108">Раздел</span><span class="sxs-lookup"><span data-stu-id="259dd-108">Topic</span></span>|<span data-ttu-id="259dd-109">Описание</span><span class="sxs-lookup"><span data-stu-id="259dd-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="259dd-110">Добавление решений в систему управления версиями</span><span class="sxs-lookup"><span data-stu-id="259dd-110">Add Solutions to Source Control</span></span>](../../2014/database-engine/add-solutions-to-source-control.md)|<span data-ttu-id="259dd-111">Описание типов проектов, которые можно добавлять в систему управления версиями, а также инструкции по добавлению решения в систему.</span><span class="sxs-lookup"><span data-stu-id="259dd-111">Describes the project types you can add, and provides instructions on how to add a solution to source control.</span></span>|  
|[<span data-ttu-id="259dd-112">Добавление проектов в систему управления версиями</span><span class="sxs-lookup"><span data-stu-id="259dd-112">Add Projects to Source Control</span></span>](../../2014/database-engine/add-projects-to-source-control.md)|<span data-ttu-id="259dd-113">Инструкции по добавлению проекта к решению.</span><span class="sxs-lookup"><span data-stu-id="259dd-113">Provides instructions on how to add a project to a solution.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="259dd-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="259dd-114">See Also</span></span>  
 [<span data-ttu-id="259dd-115">Открытие решений и проектов из системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="259dd-115">Open Solutions and Projects from Source Control</span></span>](../../2014/database-engine/open-solutions-and-projects-from-source-control.md)  
  
  
