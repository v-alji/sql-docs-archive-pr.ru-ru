---
title: Перемещение файлов баз данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- disaster recovery [SQL Server], moving database files
- files [SQL Server], moving
- data files [SQL Server], moving
- file moving [SQL Server]
- moving full-text catalogs
- moving databases
- full-text catalogs [SQL Server], moving
- moving database files
- scheduled disk maintenance [SQL Server]
- moving files
- relocating database files
- planned database relocations [SQL Server]
- databases [SQL Server], moving
ms.assetid: 89f01b10-5fae-4ed8-b0fb-a4b9f540fd28
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5491f3c4dfd47cac4047d0409c78001be80d6f13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736368"
---
# <a name="move-database-files"></a><span data-ttu-id="a849b-102">Перемещение файлов базы данных</span><span class="sxs-lookup"><span data-stu-id="a849b-102">Move Database Files</span></span>
  <span data-ttu-id="a849b-103">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]можно перемещать системные и пользовательские базы данных, задав в предложении FILENAME инструкции [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) новое местоположение файла.</span><span class="sxs-lookup"><span data-stu-id="a849b-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can move system and user databases by specifying the new file location in the FILENAME clause of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span> <span data-ttu-id="a849b-104">Таким образом могут быть перемещены файлы данных, журналов и полнотекстовых каталогов.</span><span class="sxs-lookup"><span data-stu-id="a849b-104">Data, log, and full-text catalog files can be moved in this way.</span></span> <span data-ttu-id="a849b-105">Это может быть полезно в следующих ситуациях.</span><span class="sxs-lookup"><span data-stu-id="a849b-105">This may be useful in the following situations:</span></span>  
  
-   <span data-ttu-id="a849b-106">Восстановление после сбоя.</span><span class="sxs-lookup"><span data-stu-id="a849b-106">Failure recovery.</span></span> <span data-ttu-id="a849b-107">Например, база данных находится в подозрительном режиме, или ее работа была прекращена из-за сбоя оборудования.</span><span class="sxs-lookup"><span data-stu-id="a849b-107">For example, the database is in suspect mode or has shut down, because of a hardware failure.</span></span>  
  
-   <span data-ttu-id="a849b-108">Плановое перемещение.</span><span class="sxs-lookup"><span data-stu-id="a849b-108">Planned relocation.</span></span>  
  
-   <span data-ttu-id="a849b-109">Перемещение для запланированного обслуживания дисков.</span><span class="sxs-lookup"><span data-stu-id="a849b-109">Relocation for scheduled disk maintenance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a849b-110">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="a849b-110">In This Section</span></span>  
  
|<span data-ttu-id="a849b-111">Раздел</span><span class="sxs-lookup"><span data-stu-id="a849b-111">Topic</span></span>|<span data-ttu-id="a849b-112">Description</span><span class="sxs-lookup"><span data-stu-id="a849b-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="a849b-113">Перемещение пользовательских баз данных</span><span class="sxs-lookup"><span data-stu-id="a849b-113">Move User Databases</span></span>](move-user-databases.md)|<span data-ttu-id="a849b-114">Описывает процедуры перемещения файлов пользовательской базы данных и файлов полнотекстовых каталогов в другое местоположение.</span><span class="sxs-lookup"><span data-stu-id="a849b-114">Describes the procedures for moving user database files and full-text catalog files to a new location.</span></span>|  
|[<span data-ttu-id="a849b-115">Перемещение системных баз данных</span><span class="sxs-lookup"><span data-stu-id="a849b-115">Move System Databases</span></span>](system-databases.md)|<span data-ttu-id="a849b-116">Описывает процедуры перемещения файлов системной базы данных в другое местоположение.</span><span class="sxs-lookup"><span data-stu-id="a849b-116">Describes the procedures for moving system database files to a new location.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a849b-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="a849b-117">See Also</span></span>  
 <span data-ttu-id="a849b-118">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a849b-118">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="a849b-119">[CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a849b-119">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="a849b-120">Присоединение и отсоединение базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a849b-120">Database Detach and Attach &#40;SQL Server&#41;</span></span>](database-detach-and-attach-sql-server.md)  
  
  
