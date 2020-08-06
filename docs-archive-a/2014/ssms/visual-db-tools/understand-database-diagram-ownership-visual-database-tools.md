---
title: Основные сведения о владении диаграммами баз данных (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.diagnostic.CannotOpenWithInvalidOwner
helpviewer_keywords:
- diagrams [SQL Server], ownership
- database diagrams [SQL Server], ownership
- owners [SQL Server], database diagrams
ms.assetid: 4a27a48e-c4ef-4017-82b8-0cac4d0bbcac
author: stevestein
ms.author: sstein
ms.openlocfilehash: 21d0f6f006328d8843bbbe12ee066a8564fb722a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734841"
---
# <a name="understand-database-diagram-ownership-visual-database-tools"></a><span data-ttu-id="9669e-102">Основные сведения о владении диаграммами баз данных (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="9669e-102">Understand Database Diagram Ownership (Visual Database Tools)</span></span>
  <span data-ttu-id="9669e-103">Чтобы использовать конструктор схем баз данных, член роли db_owner (роль баз данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ) должен выполнить его настройку для обеспечения управления доступом к диаграммам.</span><span class="sxs-lookup"><span data-stu-id="9669e-103">To use Database Diagram Designer it must first be set up by a member of the db_owner role (a role of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases) to control access to diagrams.</span></span> <span data-ttu-id="9669e-104">Каждая диаграмма имеет одного и только одного владельца — пользователя, который ее создал.</span><span class="sxs-lookup"><span data-stu-id="9669e-104">Each diagram has one and only one owner, the user who created it.</span></span> <span data-ttu-id="9669e-105">Дополнительные сведения о настройке схемы см. в разделе [Настройка конструктора диаграмм баз данных &#40;визуальных инструментов для баз данных&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9669e-105">For more information on setting up diagramming see [Set Up Database Diagram Designer &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="9669e-106">Некоторые сведения о принадлежности диаграмм, которые нужно учитывать:</span><span class="sxs-lookup"><span data-stu-id="9669e-106">Some points to keep in mind about diagram ownership:</span></span>  
  
-   <span data-ttu-id="9669e-107">Хотя создать диаграмму может любой пользователь базы данных, просмотреть диаграмму после создания могут только ее создатель и члены роли db_owner.</span><span class="sxs-lookup"><span data-stu-id="9669e-107">Although any user with access to a database can create a diagram, once the diagram has been created, the only users who can see it are the diagram's creator and any member of the db_owner role.</span></span>  
  
-   <span data-ttu-id="9669e-108">Право владельца диаграммы можно передать только членам роли db_owner.</span><span class="sxs-lookup"><span data-stu-id="9669e-108">Ownership of diagrams can only be transferred to members of the db_owner role.</span></span> <span data-ttu-id="9669e-109">Это возможно, только если предыдущий владелец диаграммы был удален из базы данных.</span><span class="sxs-lookup"><span data-stu-id="9669e-109">This is only possible if the previous owner of the diagram has been removed from the database.</span></span>  
  
-   <span data-ttu-id="9669e-110">Если владелец диаграммы был удален из базы данных, диаграмма остается в базе данных, пока член роли db_owner не попытается ее открыть.</span><span class="sxs-lookup"><span data-stu-id="9669e-110">If the owner of a diagram has been removed from the database, the diagram will remain in the database until a member of the db_owner role attempts to open it.</span></span> <span data-ttu-id="9669e-111">В этот момент член роли db_owner может получить права владельца диаграммы.</span><span class="sxs-lookup"><span data-stu-id="9669e-111">At that point the db_owner member can choose to take over ownership of the diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9669e-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="9669e-112">See Also</span></span>  
 <span data-ttu-id="9669e-113">[Работа с диаграммами баз данных &#40;визуальных инструментов для баз данных&#41;](work-with-database-diagrams-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9669e-113">[Work with Database Diagrams &#40;Visual Database Tools&#41;](work-with-database-diagrams-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="9669e-114">Настройка конструктора диаграмм баз данных (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="9669e-114">Set Up Database Diagram Designer &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
