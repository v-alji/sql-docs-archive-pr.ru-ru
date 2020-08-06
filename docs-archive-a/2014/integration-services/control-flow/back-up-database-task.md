---
title: Задача "Резервное копирование базы данных" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.backupdatabasetask.f1
helpviewer_keywords:
- database backups [Integration Services]
- Back Up Database task [Integration Services]
- backing up databases [Integration Services]
- transaction log backups [Integration Services]
- backing up transaction logs [Integration Services]
ms.assetid: b8839d71-13b7-41f2-a434-cb95020e79d7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b0980d89cc915121414dd7d3c89be6f4d72eb715
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657218"
---
# <a name="back-up-database-task"></a><span data-ttu-id="d9dca-102">Задача «Создание резервной копии базы данных»</span><span class="sxs-lookup"><span data-stu-id="d9dca-102">Back Up Database Task</span></span>
  <span data-ttu-id="d9dca-103">Задача «Резервное копирование базы данных» выполняет различные типы резервного копирования базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d9dca-103">The Back Up Database task performs different types of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database backups.</span></span> <span data-ttu-id="d9dca-104">Дополнительные сведения см. в разделе [Резервное копирование и восстановление баз данных SQL Server](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="d9dca-104">For more information, see [Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span></span>  
  
 <span data-ttu-id="d9dca-105">С помощью задачи «Создание резервной копии базы данных» пакет может создать резервную копию отдельной базы данных или нескольких баз данных.</span><span class="sxs-lookup"><span data-stu-id="d9dca-105">By using the Back Up Database task, a package can back up a single database or multiple databases.</span></span> <span data-ttu-id="d9dca-106">При создании резервной копии только одной базы данных можно указать компонент для резервного копирования: база данных или ее файлы и файловые группы.</span><span class="sxs-lookup"><span data-stu-id="d9dca-106">If the task backs up only a single database, you can choose the backup component: the database, or its files and filegroups.</span></span>  
  
## <a name="supported-recover-models-and-backup-types"></a><span data-ttu-id="d9dca-107">Поддерживаемые модели восстановления и типы резервного копирования</span><span class="sxs-lookup"><span data-stu-id="d9dca-107">Supported Recover Models and Backup Types</span></span>  
 <span data-ttu-id="d9dca-108">В следующей таблице перечисляются модели восстановления и типы резервных копий, поддерживаемые задачей «Создание резервной копии базы данных».</span><span class="sxs-lookup"><span data-stu-id="d9dca-108">The following table lists the recovery models and backup types that the Back Up Database task supports.</span></span>  
  
|<span data-ttu-id="d9dca-109">Модель восстановления</span><span class="sxs-lookup"><span data-stu-id="d9dca-109">Recovery model</span></span>|<span data-ttu-id="d9dca-110">База данных</span><span class="sxs-lookup"><span data-stu-id="d9dca-110">Database</span></span>|<span data-ttu-id="d9dca-111">Разностное копирование базы данных</span><span class="sxs-lookup"><span data-stu-id="d9dca-111">Database differential</span></span>|<span data-ttu-id="d9dca-112">Журнал транзакций</span><span class="sxs-lookup"><span data-stu-id="d9dca-112">Transaction log</span></span>|<span data-ttu-id="d9dca-113">Файл или разностное копирование файлов</span><span class="sxs-lookup"><span data-stu-id="d9dca-113">File or file differential</span></span>|  
|--------------------|--------------|---------------------------|---------------------|-------------------------------|  
|<span data-ttu-id="d9dca-114">Простая</span><span class="sxs-lookup"><span data-stu-id="d9dca-114">Simple</span></span>|<span data-ttu-id="d9dca-115">Обязательно</span><span class="sxs-lookup"><span data-stu-id="d9dca-115">Required</span></span>|<span data-ttu-id="d9dca-116">Необязательно</span><span class="sxs-lookup"><span data-stu-id="d9dca-116">Optional</span></span>|<span data-ttu-id="d9dca-117">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="d9dca-117">Not supported</span></span>|<span data-ttu-id="d9dca-118">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="d9dca-118">Not supported</span></span>|  
|<span data-ttu-id="d9dca-119">Полное</span><span class="sxs-lookup"><span data-stu-id="d9dca-119">Full</span></span>|<span data-ttu-id="d9dca-120">Обязательно</span><span class="sxs-lookup"><span data-stu-id="d9dca-120">Required</span></span>|<span data-ttu-id="d9dca-121">Необязательно</span><span class="sxs-lookup"><span data-stu-id="d9dca-121">Optional</span></span>|<span data-ttu-id="d9dca-122">Обязательно</span><span class="sxs-lookup"><span data-stu-id="d9dca-122">Required</span></span>|<span data-ttu-id="d9dca-123">Необязательно</span><span class="sxs-lookup"><span data-stu-id="d9dca-123">Optional</span></span>|  
|<span data-ttu-id="d9dca-124">С массовой регистрацией</span><span class="sxs-lookup"><span data-stu-id="d9dca-124">Bulk-logged</span></span>|<span data-ttu-id="d9dca-125">Обязательно</span><span class="sxs-lookup"><span data-stu-id="d9dca-125">Required</span></span>|<span data-ttu-id="d9dca-126">Необязательно</span><span class="sxs-lookup"><span data-stu-id="d9dca-126">Optional</span></span>|<span data-ttu-id="d9dca-127">Обязательно</span><span class="sxs-lookup"><span data-stu-id="d9dca-127">Required</span></span>|<span data-ttu-id="d9dca-128">Необязательно</span><span class="sxs-lookup"><span data-stu-id="d9dca-128">Optional</span></span>|  
  
 <span data-ttu-id="d9dca-129">Задача «Создание резервной копии базы данных» содержит инструкцию BACKUP языка Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="d9dca-129">The Back Up Database task encapsulates a Transact-SQL BACKUP statement.</span></span> <span data-ttu-id="d9dca-130">Дополнительные сведения см. в разделе [BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d9dca-130">For more information, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
## <a name="configuration-of-the-back-up-database-task"></a><span data-ttu-id="d9dca-131">Настройка задачи «Резервное копирование базы данных»</span><span class="sxs-lookup"><span data-stu-id="d9dca-131">Configuration of the Back Up Database Task</span></span>  
 <span data-ttu-id="d9dca-132">Свойства задаются с помощью конструктора служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d9dca-132">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="d9dca-133">Эта задача находится в разделе **Задачи плана обслуживания** **области элементов** в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d9dca-133">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="d9dca-134">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="d9dca-134">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="d9dca-135">Задача "Резервное копирование базы данных" (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="d9dca-135">Back Up Database Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/options-in-the-back-up-database-task-for-maintenance-plan.md)  
  
 <span data-ttu-id="d9dca-136">Дополнительные сведения об установке этих свойств в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="d9dca-136">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="d9dca-137">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="d9dca-137">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
