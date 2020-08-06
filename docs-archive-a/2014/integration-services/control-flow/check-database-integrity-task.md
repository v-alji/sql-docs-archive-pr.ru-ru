---
title: Задача "Проверка целостности базы данных" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.checkdatabaseintegritytask.f1
helpviewer_keywords:
- data integrity [Integration Services]
- Check Database Integrity task [Integration Services]
- checking database consistency
- database consistency checks [Integration Services]
- verifying database consistency
- integrity checking [Integration Services]
ms.assetid: 5a82fe99-4503-429f-9337-e6bac7649fe4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 99a2620a6f3f6a9a73c27fe6bb1abd34af73707d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658952"
---
# <a name="check-database-integrity-task"></a><span data-ttu-id="5f9d0-102">Задача «Проверка целостности базы данных»</span><span class="sxs-lookup"><span data-stu-id="5f9d0-102">Check Database Integrity Task</span></span>
  <span data-ttu-id="5f9d0-103">Задача «Проверка целостности базы данных» заключается в проверке распределения и структурной целостности всех объектов в заданной базе данных.</span><span class="sxs-lookup"><span data-stu-id="5f9d0-103">The Check Database Integrity task checks the allocation and structural integrity of all the objects in the specified database.</span></span> <span data-ttu-id="5f9d0-104">Можно проверить одну или несколько баз данных. Кроме того, можно задать проверку индексов базы данных.</span><span class="sxs-lookup"><span data-stu-id="5f9d0-104">The task can check a single database or multiple databases, and you can choose whether to also check the database indexes.</span></span>  
  
 <span data-ttu-id="5f9d0-105">Задача проверки целостности базы данных содержит инструкцию DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="5f9d0-105">The Check Database Integrity task encapsulates the DBCC CHECKDB statement.</span></span> <span data-ttu-id="5f9d0-106">Дополнительные сведения см. в разделе [DBCC CHECKDB (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5f9d0-106">For more information, see [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql).</span></span>  
  
## <a name="configuration-of-the-check-database-integrity-task"></a><span data-ttu-id="5f9d0-107">Настройка задачи «Проверка целостности базы данных»</span><span class="sxs-lookup"><span data-stu-id="5f9d0-107">Configuration of the Check Database Integrity Task</span></span>  
 <span data-ttu-id="5f9d0-108">Свойства задаются с помощью конструктора служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5f9d0-108">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="5f9d0-109">Эта задача находится в разделе **Задачи плана обслуживания** **области элементов** в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5f9d0-109">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="5f9d0-110">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="5f9d0-110">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="5f9d0-111">Задача "Проверка целостности базы данных" (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="5f9d0-111">Check Database Integrity Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/check-database-integrity-task-maintenance-plan.md)  
  
 <span data-ttu-id="5f9d0-112">Дополнительные сведения об установке этих свойств в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="5f9d0-112">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="5f9d0-113">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="5f9d0-113">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
