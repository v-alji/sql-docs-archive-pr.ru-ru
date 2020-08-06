---
title: MSSQLSERVER_1457 | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1457 (Database Engine error)
ms.assetid: 28434ba1-b033-4866-ab41-111fccef45a2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c30ee6149c95d93bdaf1d2877f5fe1871a575ec1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667176"
---
# <a name="mssqlserver_1457"></a><span data-ttu-id="7903c-102">MSSQLSERVER_1457</span><span class="sxs-lookup"><span data-stu-id="7903c-102">MSSQLSERVER_1457</span></span>
    
## <a name="details"></a><span data-ttu-id="7903c-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="7903c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7903c-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="7903c-104">Product Name</span></span>|<span data-ttu-id="7903c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7903c-105">SQL Server</span></span>|  
|<span data-ttu-id="7903c-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="7903c-106">Event ID</span></span>|<span data-ttu-id="7903c-107">1457</span><span class="sxs-lookup"><span data-stu-id="7903c-107">1457</span></span>|  
|<span data-ttu-id="7903c-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="7903c-108">Event Source</span></span>|<span data-ttu-id="7903c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7903c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7903c-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="7903c-110">Component</span></span>|<span data-ttu-id="7903c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7903c-111">SQLEngine</span></span>|  
|<span data-ttu-id="7903c-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="7903c-112">Symbolic Name</span></span>|<span data-ttu-id="7903c-113">DBM_PAGE_UNDO_PENDING</span><span class="sxs-lookup"><span data-stu-id="7903c-113">DBM_PAGE_UNDO_PENDING</span></span>|  
|<span data-ttu-id="7903c-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="7903c-114">Message Text</span></span>|<span data-ttu-id="7903c-115">Синхронизация зеркальной базы данных «%.\*ls» прервана, база данных осталась в несогласованном состоянии.</span><span class="sxs-lookup"><span data-stu-id="7903c-115">Synchronization of the mirror database, '%.\*ls', was interrupted, leaving the database in an inconsistent state.</span></span> <span data-ttu-id="7903c-116">Ошибка при выполнении команды ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="7903c-116">The ALTER DATABASE command failed.</span></span> <span data-ttu-id="7903c-117">Убедитесь, что создана резервная копия зеркальной базы данных и она находится в режиме «в сети», а затем подключите заново экземпляр зеркального сервера и дайте возможность зеркальной базе данных завершить синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="7903c-117">Ensure that the mirror database is back up and online, and then reconnect the mirror server instance and allow the mirror database to finish synchronizing.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7903c-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="7903c-118">Explanation</span></span>  
 <span data-ttu-id="7903c-119">Это сообщение указывает на неуспешное завершение инструкции ALTER DATABASE *имя_базы_данных* SET PARTNER OFF.</span><span class="sxs-lookup"><span data-stu-id="7903c-119">This messages indicates that the ALTER DATABASE *database_name* SET PARTNER OFF statement has failed.</span></span> <span data-ttu-id="7903c-120">Неуспешная попытка удалить зеркальное отображение базы данных прервала синхронизацию зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="7903c-120">The failed attempt to remove database mirroring interrupted synchronization of the mirror database.</span></span> <span data-ttu-id="7903c-121">База данных в несогласованном состоянии.</span><span class="sxs-lookup"><span data-stu-id="7903c-121">The database is in an inconsistent state.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7903c-122">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="7903c-122">User Action</span></span>  
 <span data-ttu-id="7903c-123">Для устранения этой ошибки можно предпринять одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="7903c-123">To resolve this error, you can take either of the following actions:</span></span>  
  
-   <span data-ttu-id="7903c-124">Восстановите связь между зеркальным и основным сервером, чтобы обеспечить синхронизацию зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="7903c-124">Restore contact between the mirror server and the principal server to allow for the mirror database to synchronize.</span></span>  
  
-   <span data-ttu-id="7903c-125">Удалите зеркальную базу данных.</span><span class="sxs-lookup"><span data-stu-id="7903c-125">Drop the mirror database.</span></span>  
  
     <span data-ttu-id="7903c-126">После удаления зеркальной базы данных можно создать новую базу данных из резервных копий.</span><span class="sxs-lookup"><span data-stu-id="7903c-126">After you drop the mirror database, you can create a new mirror database from backups.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7903c-127">Удалить зеркальную базу данных при включенном зеркальном отображении можно только после того, как инструкция SET PARTNER OFF завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="7903c-127">You can drop the mirror database when mirroring is still enabled only after a failed SET PARTNER OFF statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7903c-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="7903c-128">See Also</span></span>  
 <span data-ttu-id="7903c-129">[Зеркальное отображение базы данных (SQL Server)](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7903c-129">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="7903c-130">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7903c-130">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="7903c-131">[Настройка зеркального отображения базы данных (SQL Server)](../../database-engine/database-mirroring/setting-up-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7903c-131">[Setting Up Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/setting-up-database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="7903c-132">[Удаление зеркального отображения базы данных (SQL Server)](../../database-engine/database-mirroring/removing-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7903c-132">[Removing Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/removing-database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="7903c-133">Подготовка зеркальной базы данных к зеркальному отображению (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7903c-133">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md)  
  
  
