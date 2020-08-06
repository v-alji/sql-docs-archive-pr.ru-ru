---
title: База данных Resource | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- system objects [SQL Server]
- read-only databases
- mssqlsystemresource.mdf file
- Resource database [SQL Server]
ms.assetid: d592b2b4-bc36-4eb9-9385-8fe4dff0dced
author: stevestein
ms.author: sstein
ms.openlocfilehash: cca2f9e1ff6069a608beb1df1880b37e15f4e869
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658808"
---
# <a name="resource-database"></a><span data-ttu-id="fd8a1-102">База данных Resource</span><span class="sxs-lookup"><span data-stu-id="fd8a1-102">Resource Database</span></span>
  <span data-ttu-id="fd8a1-103">База данных Resource — это доступная только для чтения база данных, которая содержит все системные объекты, включенные в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd8a1-103">The Resource database is a read-only database that contains all the system objects that are included with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fd8a1-104">Системные объекты физически хранятся в базе данных Resource, но логически отображаются в схеме sys любой базы данных.</span><span class="sxs-lookup"><span data-stu-id="fd8a1-104">system objects, such as sys.objects, are physically persisted in the Resource database, but they logically appear in the sys schema of every database.</span></span> <span data-ttu-id="fd8a1-105">База данных Resource не содержит пользовательских данных или метаданных.</span><span class="sxs-lookup"><span data-stu-id="fd8a1-105">The Resource database does not contain user data or user metadata.</span></span>  
  
 <span data-ttu-id="fd8a1-106">База данных Resource облегчает и ускоряет обновление до новой версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fd8a1-106">The Resource database makes upgrading to a new version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] an easier and faster procedure.</span></span> <span data-ttu-id="fd8a1-107">В ранних версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]при обновлении версии требовалось удаление и создание системных объектов.</span><span class="sxs-lookup"><span data-stu-id="fd8a1-107">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], upgrading required dropping and creating system objects.</span></span> <span data-ttu-id="fd8a1-108">Поскольку файл базы данных Resource содержит все системные объекты, обновление производится простым копированием одного файла базы данных Resource на локальный сервер.</span><span class="sxs-lookup"><span data-stu-id="fd8a1-108">Because the Resource database file contains all system objects, an upgrade is now accomplished simply by copying the single Resource database file to the local server.</span></span>  
  
## <a name="physical-properties-of-resource"></a><span data-ttu-id="fd8a1-109">Физические свойства базы данных Resource</span><span class="sxs-lookup"><span data-stu-id="fd8a1-109">Physical Properties of Resource</span></span>  
 <span data-ttu-id="fd8a1-110">Физические файлы базы данных Resource имеют имена mssqlsystemresource.mdf и mssqlsystemresource.ldf.</span><span class="sxs-lookup"><span data-stu-id="fd8a1-110">The physical file names of the Resource database are mssqlsystemresource.mdf and mssqlsystemresource.ldf.</span></span> <span data-ttu-id="fd8a1-111">Эти файлы расположены в папке \<*drive*>:\Program Files\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\, и их не следует перемещать.</span><span class="sxs-lookup"><span data-stu-id="fd8a1-111">These files are located in \<*drive*>:\Program Files\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\ and should not be moved.</span></span> <span data-ttu-id="fd8a1-112">С каждым экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] связан один и только один файл mssqlsystemresource.mdf, кроме того, и экземпляры не могут использовать этот файл совместно.</span><span class="sxs-lookup"><span data-stu-id="fd8a1-112">Each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has one and only one associated mssqlsystemresource.mdf file, and instances do not share this file.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="fd8a1-113">Обновления и пакеты обновления иногда предоставляют новую базу данных ресурсов, которая устанавливается в папку BINN.</span><span class="sxs-lookup"><span data-stu-id="fd8a1-113">Upgrades and service packs sometimes provide a new resource database which is installed to the BINN folder.</span></span> <span data-ttu-id="fd8a1-114">Не рекомендуется изменять расположения базы данных ресурсов. К тому же такая возможность не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="fd8a1-114">Changing the location of the resource database is not supported or recommended.</span></span>  
  
## <a name="backing-up-and-restoring-the-resource-database"></a><span data-ttu-id="fd8a1-115">Резервное копирование и восстановление базы данных Resource</span><span class="sxs-lookup"><span data-stu-id="fd8a1-115">Backing Up and Restoring the Resource Database</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fd8a1-116">не позволяет создавать резервные копии базы данных Resource.</span><span class="sxs-lookup"><span data-stu-id="fd8a1-116">cannot back up the Resource database.</span></span> <span data-ttu-id="fd8a1-117">Пользователь может создать резервную копию файла mssqlsystemresource.mdf или диска с этим файлом так, будто это двоичный файл (EXE), а не файл базы данных; однако восстановить такие резервные копии с помощью [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удастся.</span><span class="sxs-lookup"><span data-stu-id="fd8a1-117">You can perform your own file-based or a disk-based backup by treating the mssqlsystemresource.mdf file as if it were a binary (.EXE) file, rather than a database file, but you cannot use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to restore your backups.</span></span> <span data-ttu-id="fd8a1-118">Восстановить резервную копию файла mssqlsystemresource.mdf можно будет только вручную; при этом следует соблюдать осторожность, чтобы не перезаписать текущую базу данных Resource устаревшей или потенциально небезопасной версией.</span><span class="sxs-lookup"><span data-stu-id="fd8a1-118">Restoring a backup copy of mssqlsystemresource.mdf can only be done manually, and you must be careful not to overwrite the current Resource database with an out-of-date or potentially insecure version.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fd8a1-119">После восстановления резервной копии файла mssqlsystemresource.mdf необходимо применить к ней все последующие обновления.</span><span class="sxs-lookup"><span data-stu-id="fd8a1-119">After restoring a backup of mssqlsystemresource.mdf, you must reapply any subsequent updates.</span></span>  
  
## <a name="accessing-the-resource-database"></a><span data-ttu-id="fd8a1-120">Доступ к базе данных Resource</span><span class="sxs-lookup"><span data-stu-id="fd8a1-120">Accessing the Resource Database</span></span>  
 <span data-ttu-id="fd8a1-121">База данных Resource может изменяться только специалистом службы поддержки пользователей Майкрософт либо под его руководством.</span><span class="sxs-lookup"><span data-stu-id="fd8a1-121">The Resource database should only be modified by or at the direction of a Microsoft Customer Support Services (CSS) specialist.</span></span> <span data-ttu-id="fd8a1-122">База данных Resource всегда имеет идентификатор 32767.</span><span class="sxs-lookup"><span data-stu-id="fd8a1-122">The ID of the Resource database is always 32767.</span></span> <span data-ttu-id="fd8a1-123">Другими важными значениями, связанными с базой данных Resource, являются номер версии и время последнего обновления базы данных.</span><span class="sxs-lookup"><span data-stu-id="fd8a1-123">Other important values associated with the Resource database are the version number and the last time that the database was updated.</span></span>  
  
 <span data-ttu-id="fd8a1-124">**Чтобы определить номер версии базы данных** Resource **, используйте следующую инструкцию**:</span><span class="sxs-lookup"><span data-stu-id="fd8a1-124">**To determine the version number of the** Resource **database, use**:</span></span>  
  
```  
SELECT SERVERPROPERTY('ResourceVersion');  
GO  
```  
  
 <span data-ttu-id="fd8a1-125">**Чтобы определить, когда в последний раз обновлялась база данных** Resource **, введите**:</span><span class="sxs-lookup"><span data-stu-id="fd8a1-125">**To determine when the** Resource **database was last updated, use**:</span></span>  
  
```  
SELECT SERVERPROPERTY('ResourceLastUpdateDateTime');  
GO  
```  
  
 <span data-ttu-id="fd8a1-126">**Для доступа к определениям SQL для системных объектов используется функция OBJECT_DEFINITION:**</span><span class="sxs-lookup"><span data-stu-id="fd8a1-126">**To access SQL definitions of system objects, use the OBJECT_DEFINITION function:**</span></span>  
  
```  
SELECT OBJECT_DEFINITION(OBJECT_ID('sys.objects'));  
GO  
```  
  
## <a name="related-content"></a><span data-ttu-id="fd8a1-127">См. также</span><span class="sxs-lookup"><span data-stu-id="fd8a1-127">Related Content</span></span>  
 [<span data-ttu-id="fd8a1-128">Системные базы данных</span><span class="sxs-lookup"><span data-stu-id="fd8a1-128">System Databases</span></span>](system-databases.md)  
  
 [<span data-ttu-id="fd8a1-129">Диагностическое соединение для администраторов баз данных</span><span class="sxs-lookup"><span data-stu-id="fd8a1-129">Diagnostic Connection for Database Administrators</span></span>](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md)  
  
 [<span data-ttu-id="fd8a1-130">OBJECT_DEFINITION (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fd8a1-130">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/object-definition-transact-sql)  
  
 [<span data-ttu-id="fd8a1-131">SERVERPROPERTY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fd8a1-131">SERVERPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/serverproperty-transact-sql)  
  
 [<span data-ttu-id="fd8a1-132">Запуск SQL Server в однопользовательском режиме</span><span class="sxs-lookup"><span data-stu-id="fd8a1-132">Start SQL Server in Single-User Mode</span></span>](../../database-engine/configure-windows/start-sql-server-in-single-user-mode.md)  
  
  
