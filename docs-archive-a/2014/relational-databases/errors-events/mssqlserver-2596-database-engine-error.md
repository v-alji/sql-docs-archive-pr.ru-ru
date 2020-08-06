---
title: MSSQLSERVER_2596 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2596 (Database Engine error)
ms.assetid: 49ab892f-8ba3-4ba1-b562-ddf205019802
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 27b2ceed40274df4ba57c4d61a83fbc60b6a7f80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664262"
---
# <a name="mssqlserver_2596"></a><span data-ttu-id="a2d5d-102">MSSQLSERVER_2596</span><span class="sxs-lookup"><span data-stu-id="a2d5d-102">MSSQLSERVER_2596</span></span>
    
## <a name="details"></a><span data-ttu-id="a2d5d-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="a2d5d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a2d5d-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="a2d5d-104">Product Name</span></span>|<span data-ttu-id="a2d5d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a2d5d-105">SQL Server</span></span>|  
|<span data-ttu-id="a2d5d-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a2d5d-106">Event ID</span></span>|<span data-ttu-id="a2d5d-107">2596</span><span class="sxs-lookup"><span data-stu-id="a2d5d-107">2596</span></span>|  
|<span data-ttu-id="a2d5d-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="a2d5d-108">Event Source</span></span>|<span data-ttu-id="a2d5d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a2d5d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a2d5d-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="a2d5d-110">Component</span></span>|<span data-ttu-id="a2d5d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a2d5d-111">SQLEngine</span></span>|  
|<span data-ttu-id="a2d5d-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="a2d5d-112">Symbolic Name</span></span>|<span data-ttu-id="a2d5d-113">DBCC_DATABASE_IN_READ_ONLY_MODE</span><span class="sxs-lookup"><span data-stu-id="a2d5d-113">DBCC_DATABASE_IN_READ_ONLY_MODE</span></span>|  
|<span data-ttu-id="a2d5d-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a2d5d-114">Message Text</span></span>|<span data-ttu-id="a2d5d-115">Инструкция восстановления не была обработана.</span><span class="sxs-lookup"><span data-stu-id="a2d5d-115">The repair statement was not processed.</span></span> <span data-ttu-id="a2d5d-116">База данных не может быть доступна только для чтения.</span><span class="sxs-lookup"><span data-stu-id="a2d5d-116">The database cannot be in read-only mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a2d5d-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="a2d5d-117">Explanation</span></span>  
 <span data-ttu-id="a2d5d-118">Это сообщение указывает, что база данных находится в режиме «только для чтения».</span><span class="sxs-lookup"><span data-stu-id="a2d5d-118">This message indicates that the database is in read-only mode.</span></span> <span data-ttu-id="a2d5d-119">Восстановление невозможно, если база данных находится в режиме «только для чтения».</span><span class="sxs-lookup"><span data-stu-id="a2d5d-119">Repairs are not possible when a database is in read-only mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a2d5d-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a2d5d-120">User Action</span></span>  
 <span data-ttu-id="a2d5d-121">При помощи инструкции ALTER DATABASE переведите базу данных в режим чтения и записи, а затем повторите команду DBCC.</span><span class="sxs-lookup"><span data-stu-id="a2d5d-121">Set the database to read-write by using ALTER DATABASE, and then re-run the DBCC command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2d5d-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="a2d5d-122">See Also</span></span>  
 [<span data-ttu-id="a2d5d-123">ALTER DATABASE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a2d5d-123">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
