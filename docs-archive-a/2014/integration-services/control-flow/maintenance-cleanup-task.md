---
title: Задача "Очистка после обслуживания" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.maintenancecleanuptask.f1
helpviewer_keywords:
- deleting files
- removing files
- Maintenance Cleanup task
ms.assetid: 73ad3cd6-9a6d-44cf-905f-c56aa658bf42
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4d39dd775402adadbe51eaadc530f4feb288ab9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658331"
---
# <a name="maintenance-cleanup-task"></a><span data-ttu-id="f14f7-102">задача «Очистка после обслуживания»</span><span class="sxs-lookup"><span data-stu-id="f14f7-102">Maintenance Cleanup Task</span></span>
  <span data-ttu-id="f14f7-103">Задача «Очистка после обслуживания» удаляет файлы, относящиеся к планам обслуживания, включая файлы резервных копий баз данных и отчеты, созданные планами обслуживания.</span><span class="sxs-lookup"><span data-stu-id="f14f7-103">The Maintenance Cleanup task removes files related to maintenance plans, including database backup files and reports created by maintenance plans.</span></span> <span data-ttu-id="f14f7-104">Дополнительные сведения см. в разделах [Планы обслуживания](../../relational-databases/maintenance-plans/maintenance-plans.md) и [Резервное копирование и восстановление баз данных SQL Server](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="f14f7-104">For more information, see [Maintenance Plans](../../relational-databases/maintenance-plans/maintenance-plans.md) and [Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span></span>  
  
 <span data-ttu-id="f14f7-105">С помощью задачи «Очистка после обслуживания» пакет может удалять файлы резервных копий или отчеты планов обслуживания на указанном сервере.</span><span class="sxs-lookup"><span data-stu-id="f14f7-105">By using the Maintenance Cleanup task, a package can remove the backup files or maintenance plan reports on the specified server.</span></span> <span data-ttu-id="f14f7-106">Задача «Очистка после обслуживания» имеет параметр удаления специфических файлов или удаления группы файлов в папке.</span><span class="sxs-lookup"><span data-stu-id="f14f7-106">The Maintenance Cleanup task includes an option to remove a specific file or remove a group of files in a folder.</span></span> <span data-ttu-id="f14f7-107">При необходимости можно указать расширение удаляемых файлов.</span><span class="sxs-lookup"><span data-stu-id="f14f7-107">Optionally you can specify the extension of the files to delete.</span></span>  
  
 <span data-ttu-id="f14f7-108">При настройке задачи «Очистка после обслуживания» для удаления файлов резервных копий по умолчанию установлено расширение файла BAK.</span><span class="sxs-lookup"><span data-stu-id="f14f7-108">When you configure the Maintenance Cleanup task to remove backup files, the default file name extension is BAK.</span></span> <span data-ttu-id="f14f7-109">Для файлов отчета расширение по умолчанию — TXT.</span><span class="sxs-lookup"><span data-stu-id="f14f7-109">For report files, the default file name extension is TXT.</span></span> <span data-ttu-id="f14f7-110">При необходимости расширение можно изменить; единственное ограничение: расширение должно иметь меньше 256 символов.</span><span class="sxs-lookup"><span data-stu-id="f14f7-110">You can update the extensions to suit your needs; the only limitation is that extensions must be less than 256 characters long.</span></span>  
  
 <span data-ttu-id="f14f7-111">Если необходимо удалить старые ненужные файлы, задача «Очистка после обслуживания» может быть настроена для удаления файлов, существующих определенный период времени.</span><span class="sxs-lookup"><span data-stu-id="f14f7-111">Typically, you want to remove old files that are no longer needed, and the Maintenance Cleanup task can be configured to delete files that have reached a specified age.</span></span> <span data-ttu-id="f14f7-112">Например, задача может быть настроена на файлы, существующие дольше двух недель.</span><span class="sxs-lookup"><span data-stu-id="f14f7-112">For example, the task can be configured to delete files that are older than four weeks.</span></span> <span data-ttu-id="f14f7-113">Можно указать давность удаляемых файлов, используя дни, недели, месяцы и годы.</span><span class="sxs-lookup"><span data-stu-id="f14f7-113">You can specify the age of files to delete by using days, weeks, months, or years.</span></span> <span data-ttu-id="f14f7-114">Если минимальный срок для удаления файлов не устанавливается, удаляются все файлы указанного типа.</span><span class="sxs-lookup"><span data-stu-id="f14f7-114">If you do not specify the minimum age of files to delete, all files of the specified type are deleted.</span></span>  
  
 <span data-ttu-id="f14f7-115">В отличие от ранних версий задачи «Очистка после обслуживания» версия [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] этой задачи не удаляет автоматически файлы во вложенных каталогах указанной папки.</span><span class="sxs-lookup"><span data-stu-id="f14f7-115">In contrast to earlier versions of the Maintenance Cleanup task, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version of the task does not automatically delete files in the subdirectories of the specified directory.</span></span> <span data-ttu-id="f14f7-116">Это ограничение сокращает контактную зону любой атаки, использующей функции задачи «Очистка после обслуживания» для умышленного удаления файлов.</span><span class="sxs-lookup"><span data-stu-id="f14f7-116">This constraint reduces the surface area of any attack that could exploit the functionality of the Maintenance Cleanup task to delete files maliciously.</span></span> <span data-ttu-id="f14f7-117">Для удаления вложенных папок первого уровня необходимо выбрать это действие, установив флажок **Включить вложенные папки первого уровня** в диалоговом окне **Задача "Очистка после обслуживания"** .</span><span class="sxs-lookup"><span data-stu-id="f14f7-117">To delete the first-level subfolders, you must explicitly elect to do this by checking the **Include first-level subfolders** option in the **Maintenance Cleanup Task** dialog box.</span></span>  
  
## <a name="configuration-of-the-maintenance-cleanup-task"></a><span data-ttu-id="f14f7-118">Настройка задачи «Очистка после обслуживания»</span><span class="sxs-lookup"><span data-stu-id="f14f7-118">Configuration of the Maintenance Cleanup Task</span></span>  
 <span data-ttu-id="f14f7-119">Свойства задаются с помощью конструктора служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f14f7-119">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="f14f7-120">Эта задача находится в разделе **Задачи плана обслуживания** **области элементов** в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f14f7-120">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="f14f7-121">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="f14f7-121">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="f14f7-122">Задача "Очистка после обслуживания" (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="f14f7-122">Maintenance Cleanup Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/maintenance-cleanup-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="f14f7-123">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="f14f7-123">Related Tasks</span></span>  
 <span data-ttu-id="f14f7-124">Дополнительные сведения о настройке свойств этих свойств в конструкторе [!INCLUDE[ssIS](../../includes/ssis-md.md)] см. в разделе [Задание свойств задач или контейнеров](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="f14f7-124">For details about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f14f7-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="f14f7-125">See Also</span></span>  
 <span data-ttu-id="f14f7-126">[Задачи служб Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="f14f7-126">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="f14f7-127">Поток управления</span><span class="sxs-lookup"><span data-stu-id="f14f7-127">Control Flow</span></span>](control-flow.md)  
  
  
