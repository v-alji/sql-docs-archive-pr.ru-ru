---
title: Копирование баз данных на другие серверы | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- servers [SQL Server], copying databases between
- bulk exporting [SQL Server], between servers
- database copying [SQL Server]
- migrating databases [SQL Server]
- moving databases
- copying databases
- bulk importing [SQL Server], between servers
ms.assetid: 978406d6-a3c8-4902-b1f4-4ced75234be5
author: stevestein
ms.author: sstein
ms.openlocfilehash: bcde6185f25129596b4be7a150d4ee230c54c1a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731721"
---
# <a name="copy-databases-to-other-servers"></a><span data-ttu-id="e0a37-102">Копирование баз данных на другие серверы</span><span class="sxs-lookup"><span data-stu-id="e0a37-102">Copy Databases to Other Servers</span></span>
  <span data-ttu-id="e0a37-103">В некоторых случаях можно скопировать базу данных с одного компьютера на другой и использовать ее для тестирования, проверки согласованности данных, разработки ПО, выполнения отчетов, создания зеркальной базы данных или предоставления доступа к базе данных сотрудникам удаленного филиала.</span><span class="sxs-lookup"><span data-stu-id="e0a37-103">It is sometimes useful to copy a database from one computer to another, whether for testing, checking consistency, developing software, running reports, creating a mirror database, or, possibly, to make the database available to remote-branch operations.</span></span>  
  
 <span data-ttu-id="e0a37-104">Скопировать базу данных можно одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="e0a37-104">There are several ways to copy a database:</span></span>  
  
-   <span data-ttu-id="e0a37-105">Использование мастера копирования баз данных</span><span class="sxs-lookup"><span data-stu-id="e0a37-105">Using the Copy Database Wizard</span></span>  
  
     <span data-ttu-id="e0a37-106">Мастер копирования баз данных можно использовать для копирования или перемещения баз данных между серверами, а также для обновления базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] до более новой версии.</span><span class="sxs-lookup"><span data-stu-id="e0a37-106">You can use the Copy Database Wizard to copy or move databases between servers or to upgrade a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database to a later version.</span></span> <span data-ttu-id="e0a37-107">Дополнительные сведения см. в статье [Use the Copy Database Wizard](use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="e0a37-107">For more information, see [Use the Copy Database Wizard](use-the-copy-database-wizard.md).</span></span>  
  
-   <span data-ttu-id="e0a37-108">Восстановление базы данных из резервной копии</span><span class="sxs-lookup"><span data-stu-id="e0a37-108">Restoring a database backup</span></span>  
  
     <span data-ttu-id="e0a37-109">Чтобы копировать целую базу данных, можно использовать инструкции BACKUP и RESTORE языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e0a37-109">To copy an entire database, you can use the BACKUP and RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="e0a37-110">Выбор методики восстановления базы данных из полной резервной копии для копирования базы данных с одного компьютера на другой может быть мотивирован разными причинами.</span><span class="sxs-lookup"><span data-stu-id="e0a37-110">Typically, restoring a full backup of a database is used to copy the database from one computer to another for a variety of reasons.</span></span> <span data-ttu-id="e0a37-111">Сведения о копировании базы данных путем восстановления из резервной копии см. в статье [Копирование баз данных путем создания и восстановления резервных копий](copy-databases-with-backup-and-restore.md).</span><span class="sxs-lookup"><span data-stu-id="e0a37-111">For information on using backup and restore to copy a database, see [Copy Databases with Backup and Restore](copy-databases-with-backup-and-restore.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0a37-112">Чтобы настроить зеркальную базу данных для зеркального отображения базы данных, необходимо восстановить базу данных на зеркальном сервере с помощью инструкции RESTORE DATABASE *<имя_базы_данных>* WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="e0a37-112">To set up a mirror database for database mirroring, you must restore the database onto the mirror server by using RESTORE DATABASE *<database_name>* WITH NORECOVERY.</span></span> <span data-ttu-id="e0a37-113">Дополнительные сведения см. в статье [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e0a37-113">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
-   <span data-ttu-id="e0a37-114">Использование мастера создания скриптов для публикации баз данных</span><span class="sxs-lookup"><span data-stu-id="e0a37-114">Using the Generate Scripts Wizard to publish databases</span></span>  
  
     <span data-ttu-id="e0a37-115">Мастер создания скриптов позволяет передать базу данных с локального компьютера на веб-поставщик услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="e0a37-115">You can use the Generate Scripts Wizard to transfer a database from a local computer to a Web hosting provider.</span></span> <span data-ttu-id="e0a37-116">Дополнительные сведения см. в статье [Мастер формирования и публикации скриптов](../scripting/generate-and-publish-scripts-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="e0a37-116">For more information, see [Generate and Publish Scripts Wizard](../scripting/generate-and-publish-scripts-wizard.md).</span></span>  
  
  
