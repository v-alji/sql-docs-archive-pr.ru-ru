---
title: Задача "Сжатие базы данных" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.shrinkdatabasetask.f1
helpviewer_keywords:
- Shrink Database task
- database shrinking [Integration Services]
- shrinking databases
ms.assetid: e66286f8-97b1-4e5a-86b4-e56f1932b7d5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 587777928e362e87e4b691e3c46167c1239984cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667347"
---
# <a name="shrink-database-task"></a><span data-ttu-id="7d3b8-102">задача «Сжатие базы данных»</span><span class="sxs-lookup"><span data-stu-id="7d3b8-102">Shrink Database Task</span></span>
  <span data-ttu-id="7d3b8-103">Задача «Сжатие базы данных» уменьшает размер данных базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и файлов журналов.</span><span class="sxs-lookup"><span data-stu-id="7d3b8-103">The Shrink Database task reduces the size of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database data and log files.</span></span>  
  
 <span data-ttu-id="7d3b8-104">Используя задачу «Сжатие базы данных», пакет может сжимать файлы как одной базы данных, так и множества баз данных.</span><span class="sxs-lookup"><span data-stu-id="7d3b8-104">By using the Shrink Database task, a package can shrink files for a single database or multiple databases.</span></span>  
  
 <span data-ttu-id="7d3b8-105">Сжатие файлов данных позволяет освободить неиспользуемое пространство путем перемещения страниц данных с конца файла в незанятое пространство ближе к началу файла.</span><span class="sxs-lookup"><span data-stu-id="7d3b8-105">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="7d3b8-106">Когда в конце файла образуется достаточно свободного места, страницы данных в конце файла могут быть освобождены и возвращены в файловую систему.</span><span class="sxs-lookup"><span data-stu-id="7d3b8-106">When enough free space is created at the end of the file, data pages at end of the file can deallocated and returned to the file system.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="7d3b8-107">Данные, перемещаемые в процессе сжатия файла, могут быть разбросаны по любым доступным местам в файле.</span><span class="sxs-lookup"><span data-stu-id="7d3b8-107">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="7d3b8-108">Это вызывает фрагментацию индекса и может увеличить время выполнения запросов, выполняющих поиск в диапазоне индекса.</span><span class="sxs-lookup"><span data-stu-id="7d3b8-108">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="7d3b8-109">Чтобы устранить фрагментацию, предусмотрите возможность перестроения индексов файла после сжатия.</span><span class="sxs-lookup"><span data-stu-id="7d3b8-109">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
## <a name="commands"></a><span data-ttu-id="7d3b8-110">Команды</span><span class="sxs-lookup"><span data-stu-id="7d3b8-110">Commands</span></span>  
 <span data-ttu-id="7d3b8-111">Задача «Сжатие базы данных» содержит команду DBCC SHRINKDATABASE, включая следующие аргументы и параметры:</span><span class="sxs-lookup"><span data-stu-id="7d3b8-111">The Shrink Database task encapsulates a DBCC SHRINKDATABASE command, including the following arguments and options:</span></span>  
  
-   <span data-ttu-id="7d3b8-112">*database_name*</span><span class="sxs-lookup"><span data-stu-id="7d3b8-112">*database_name*</span></span>  
  
-   <span data-ttu-id="7d3b8-113">*target_percent*</span><span class="sxs-lookup"><span data-stu-id="7d3b8-113">*target_percent*</span></span>  
  
-   <span data-ttu-id="7d3b8-114">NOTRUNCATE или TRUNCATEONLY.</span><span class="sxs-lookup"><span data-stu-id="7d3b8-114">NOTRUNCATE or TRUNCATEONLY.</span></span>  
  
 <span data-ttu-id="7d3b8-115">Если задача «Сжатие базы данных» сжимает множество баз данных, то задача запускает множество команд SHRINKDATABASE, по одной на каждую базу данных.</span><span class="sxs-lookup"><span data-stu-id="7d3b8-115">If the Shrink Database task shrinks multiple databases, the task runs multiple SHRINKDATABASE commands, one for each database.</span></span> <span data-ttu-id="7d3b8-116">Все экземпляры команды SHRINKDATABASE используют одинаковые значения аргументов, за исключением аргумента *database_name* .</span><span class="sxs-lookup"><span data-stu-id="7d3b8-116">All instances of the SHRINKDATABASE command use the same argument values, except for the *database_name* argument.</span></span> <span data-ttu-id="7d3b8-117">Дополнительные сведения см. в разделе [DBCC SHRINKDATABASE (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7d3b8-117">For more information, see [DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql).</span></span>  
  
## <a name="configuration-of-the-shrink-database-task"></a><span data-ttu-id="7d3b8-118">Настройка задачи «Сжатие базы данных»</span><span class="sxs-lookup"><span data-stu-id="7d3b8-118">Configuration of the Shrink Database Task</span></span>  
 <span data-ttu-id="7d3b8-119">Установить свойства можно с помощью конструктора служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d3b8-119">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="7d3b8-120">Эта задача находится в разделе **Задачи плана обслуживания** **области элементов** в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d3b8-120">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="7d3b8-121">Дополнительные сведения о свойствах, которые можно установить с помощью конструктора служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="7d3b8-121">For more information about the properties that you can set in the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="7d3b8-122">Задача "Сжатие базы данных" (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="7d3b8-122">Shrink Database Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/shrink-database-task-maintenance-plan.md)  
  
 <span data-ttu-id="7d3b8-123">Дополнительные сведения об установке этих свойств в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="7d3b8-123">For more information about setting these properties in the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="7d3b8-124">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="7d3b8-124">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
