---
title: MSSQLSERVER_ 3168 | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3168 (Database Engine error)
ms.assetid: 991111d9-1eb3-43e9-9333-a75a775c3200
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 764f456653365c085e9f756a749910bbd03b4259
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664242"
---
# <a name="mssqlserver_3168"></a><span data-ttu-id="77e1b-102">MSSQLSERVER_3168</span><span class="sxs-lookup"><span data-stu-id="77e1b-102">MSSQLSERVER_3168</span></span>
    
## <a name="details"></a><span data-ttu-id="77e1b-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="77e1b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="77e1b-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="77e1b-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="77e1b-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="77e1b-105">Event ID</span></span>|<span data-ttu-id="77e1b-106">3168</span><span class="sxs-lookup"><span data-stu-id="77e1b-106">3168</span></span>|  
|<span data-ttu-id="77e1b-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="77e1b-107">Event Source</span></span>|<span data-ttu-id="77e1b-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="77e1b-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="77e1b-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="77e1b-109">Component</span></span>|<span data-ttu-id="77e1b-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="77e1b-110">SQLEngine</span></span>|  
|<span data-ttu-id="77e1b-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="77e1b-111">Symbolic Name</span></span>|<span data-ttu-id="77e1b-112">LDDB_SYSTEMWRONGVER</span><span class="sxs-lookup"><span data-stu-id="77e1b-112">LDDB_SYSTEMWRONGVER</span></span>|  
|<span data-ttu-id="77e1b-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="77e1b-113">Message Text</span></span>|<span data-ttu-id="77e1b-114">Резервную копию системной базы данных на устройстве %ls восстановить невозможно, поскольку она была создана на сервере другой версии (%ls), отличной от версии данного сервера (%ls).</span><span class="sxs-lookup"><span data-stu-id="77e1b-114">The backup of the system database on the device %ls cannot be restored because it was created by a different version of the server (%ls) than this server (%ls).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="77e1b-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="77e1b-115">Explanation</span></span>  
 <span data-ttu-id="77e1b-116">Невозможно выполнить восстановление резервной копии системной базы данных (**master**, **model** или **msdb**) на сервере, если его сборка отличается от сборки сервера, где была создана резервная копия.</span><span class="sxs-lookup"><span data-stu-id="77e1b-116">You cannot restore a backup of a system database (**master**, **model**, or **msdb**) on a server build that differs from the build on which the backup was originally performed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77e1b-117">При установке сборки с пакетом обновления или исправлениями изменяется номер сборки сервера. Номера сборок сервера всегда увеличиваются.</span><span class="sxs-lookup"><span data-stu-id="77e1b-117">Installing a service pack or a hotfix build changes the server build number, and server builds are always incremental.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="77e1b-118">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="77e1b-118">Possible Causes</span></span>  
 <span data-ttu-id="77e1b-119">Схемы системных баз данных могут различаться в разных сборках сервера.</span><span class="sxs-lookup"><span data-stu-id="77e1b-119">The database schema for system databases may be changed across server builds.</span></span> <span data-ttu-id="77e1b-120">Чтобы убедиться, что изменение схемы не приведет к несоответствию, выполните инструкцию RESTORE, которая сравнивает номер сборки сервера файла резервной копии с номером сервера, на котором пытаются восстановить базу данных из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="77e1b-120">To make sure that a schema change does not cause inconsistencies, the RESTORE statement compares the server build number on the backup file to the build number of the server on which you are trying to restore the backup.</span></span> <span data-ttu-id="77e1b-121">Если версии не совпадают, то инструкция выводит сообщение об ошибке 3168, и происходит аварийное завершение восстановления.</span><span class="sxs-lookup"><span data-stu-id="77e1b-121">If the builds are different, the statement issues the 3168 error message, and the restore operation terminates abnormally.</span></span>  
  
 <span data-ttu-id="77e1b-122">Ниже приведено несколько случаев, когда может возникнуть эта проблема.</span><span class="sxs-lookup"><span data-stu-id="77e1b-122">Some scenarios in which this problem may occur include the following:</span></span>  
  
-   <span data-ttu-id="77e1b-123">Пользователь пытается восстановить системную базу данных на сервере А из резервной копии, созданной на сервере Б. На серверах А и Б установлены разные сборки серверов.</span><span class="sxs-lookup"><span data-stu-id="77e1b-123">A user tries to restore a system database on Server A from a backup taken on Server B. Servers A and B are on different server builds.</span></span> <span data-ttu-id="77e1b-124">Например, на сервере А может быть установлена сборка первоначальной версии, а на сервере Б — сборка с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="77e1b-124">For example, Server A might be on the original release version build and Server B might be on a service pack 1 (SP1) build.</span></span>  
  
-   <span data-ttu-id="77e1b-125">Пользователь пытается восстановить системную базу данных с резервной копии, сделанной на том же сервере.</span><span class="sxs-lookup"><span data-stu-id="77e1b-125">A user tries to restore a system database from a backup taken on the same server.</span></span> <span data-ttu-id="77e1b-126">Однако при создании резервной копии на сервере была другая сборка.</span><span class="sxs-lookup"><span data-stu-id="77e1b-126">However, the server was running a different build when the backup occurred.</span></span> <span data-ttu-id="77e1b-127">Это означает, что с момента создания резервной копии сервер был обновлен.</span><span class="sxs-lookup"><span data-stu-id="77e1b-127">That is, the server was upgraded since the backup was performed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="77e1b-128">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="77e1b-128">User Action</span></span>  
 <span data-ttu-id="77e1b-129">В такой ситуации процесс восстановления является весьма запутанным и используется только в качестве последней меры.</span><span class="sxs-lookup"><span data-stu-id="77e1b-129">The restore process in this situation is fairly involved, and used only as a last resort.</span></span> <span data-ttu-id="77e1b-130">Дополнительные сведения см. в статье "[You cannot restore system database backups to a different build of SQL Server](https://support.microsoft.com/kb/264474)" (Невозможно восстановить системную базу данных из резервной копии на другую сборку SQL Server).</span><span class="sxs-lookup"><span data-stu-id="77e1b-130">For more information, see"[You cannot restore system database backups to a different build of SQL Server](https://support.microsoft.com/kb/264474)".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77e1b-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="77e1b-131">See Also</span></span>  
 [<span data-ttu-id="77e1b-132">Резервное копирование и восстановление системных баз данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="77e1b-132">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
  
