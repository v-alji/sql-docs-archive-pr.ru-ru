---
title: MSSQLSERVER_2516 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2516 (Database Engine error)
ms.assetid: 79ed14b5-f53c-40c6-8334-8a083f732207
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6be0809b3560d94bb883cf3a4acfa3d2c484b8b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729517"
---
# <a name="mssqlserver_2516"></a><span data-ttu-id="7a2ef-102">MSSQLSERVER_2516</span><span class="sxs-lookup"><span data-stu-id="7a2ef-102">MSSQLSERVER_2516</span></span>
    
## <a name="details"></a><span data-ttu-id="7a2ef-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="7a2ef-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7a2ef-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="7a2ef-104">Product Name</span></span>|<span data-ttu-id="7a2ef-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7a2ef-105">SQL Server</span></span>|  
|<span data-ttu-id="7a2ef-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="7a2ef-106">Event ID</span></span>|<span data-ttu-id="7a2ef-107">2516</span><span class="sxs-lookup"><span data-stu-id="7a2ef-107">2516</span></span>|  
|<span data-ttu-id="7a2ef-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="7a2ef-108">Event Source</span></span>|<span data-ttu-id="7a2ef-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7a2ef-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7a2ef-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="7a2ef-110">Component</span></span>|<span data-ttu-id="7a2ef-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7a2ef-111">SQLEngine</span></span>|  
|<span data-ttu-id="7a2ef-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="7a2ef-112">Symbolic Name</span></span>|<span data-ttu-id="7a2ef-113">DBCC_REPAIR_DIFF_MAP_INVALIDATED</span><span class="sxs-lookup"><span data-stu-id="7a2ef-113">DBCC_REPAIR_DIFF_MAP_INVALIDATED</span></span>|  
|<span data-ttu-id="7a2ef-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="7a2ef-114">Message Text</span></span>|<span data-ttu-id="7a2ef-115">Процесс восстановления сделал недействительной битовую карту для базы данных NAME.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-115">Repair has invalidated the differential bitmap for database NAME.</span></span> <span data-ttu-id="7a2ef-116">Цепочка разностного резервного копирования прервана.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-116">The differential backup chain is broken.</span></span> <span data-ttu-id="7a2ef-117">Перед тем как выполнять разностное резервное копирование, необходимо произвести полное резервное копирование базы данных.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-117">You must perform a full database backup before you can perform a differential backup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7a2ef-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="7a2ef-118">Explanation</span></span>  
 <span data-ttu-id="7a2ef-119">Это информационное сообщение возвращается при исправлении ошибки MSSQLEngine_2515.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-119">This informational message is returned when error MSSQLEngine_2515 is repaired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7a2ef-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="7a2ef-120">User Action</span></span>  
 <span data-ttu-id="7a2ef-121">Создайте полную резервную копию базы данных.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-121">Perform a full database backup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a2ef-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="7a2ef-122">See Also</span></span>  
 [<span data-ttu-id="7a2ef-123">Создание полной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7a2ef-123">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../backup-restore/create-a-full-database-backup-sql-server.md)  
  
  
