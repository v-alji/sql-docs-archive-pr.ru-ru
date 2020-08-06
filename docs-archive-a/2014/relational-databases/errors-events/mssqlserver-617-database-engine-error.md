---
title: MSSQLSERVER_617 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 617 (Database Engine error)
ms.assetid: 213545d9-08a7-4427-bfd1-8b7e16644281
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 88e9feb7c3ac5d8cf646d2243319b2b160b7757e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734078"
---
# <a name="mssqlserver_617"></a><span data-ttu-id="a6106-102">MSSQLSERVER_617</span><span class="sxs-lookup"><span data-stu-id="a6106-102">MSSQLSERVER_617</span></span>
    
## <a name="details"></a><span data-ttu-id="a6106-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="a6106-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6106-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="a6106-104">Product Name</span></span>|<span data-ttu-id="a6106-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a6106-105">SQL Server</span></span>|  
|<span data-ttu-id="a6106-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a6106-106">Event ID</span></span>|<span data-ttu-id="a6106-107">617</span><span class="sxs-lookup"><span data-stu-id="a6106-107">617</span></span>|  
|<span data-ttu-id="a6106-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="a6106-108">Event Source</span></span>|<span data-ttu-id="a6106-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a6106-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a6106-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="a6106-110">Component</span></span>|<span data-ttu-id="a6106-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a6106-111">SQLEngine</span></span>|  
|<span data-ttu-id="a6106-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="a6106-112">Symbolic Name</span></span>|<span data-ttu-id="a6106-113">NODESHASH</span><span class="sxs-lookup"><span data-stu-id="a6106-113">NODESHASH</span></span>|  
|<span data-ttu-id="a6106-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a6106-114">Message Text</span></span>|<span data-ttu-id="a6106-115">Дескриптор объекта с идентификатором %ld в базе данных с идентификатором %d не обнаружен в хэш-таблице при попытке его восстановления по хэшу.</span><span class="sxs-lookup"><span data-stu-id="a6106-115">Descriptor for object ID %ld in database ID %d not found in the hash table during attempt to unhash it.</span></span> <span data-ttu-id="a6106-116">В рабочей таблице отсутствует запись.</span><span class="sxs-lookup"><span data-stu-id="a6106-116">A work table is missing an entry.</span></span> <span data-ttu-id="a6106-117">Повторите запрос.</span><span class="sxs-lookup"><span data-stu-id="a6106-117">Rerun the query.</span></span> <span data-ttu-id="a6106-118">Если используется курсор, закройте и заново откройте его.</span><span class="sxs-lookup"><span data-stu-id="a6106-118">If a cursor is involved, close and reopen the cursor.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a6106-119">Объяснение</span><span class="sxs-lookup"><span data-stu-id="a6106-119">Explanation</span></span>  
 <span data-ttu-id="a6106-120">SQL Server не может найти рабочую таблицу для конкретной записи.</span><span class="sxs-lookup"><span data-stu-id="a6106-120">SQL Server cannot locate the work table for a specific entry.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a6106-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a6106-121">User Action</span></span>  
  
1.  <span data-ttu-id="a6106-122">Если используется курсор, закройте и заново откройте его.</span><span class="sxs-lookup"><span data-stu-id="a6106-122">If a cursor is involved, close the cursor and re-open the cursor.</span></span>  
  
2.  <span data-ttu-id="a6106-123">Повторите запрос.</span><span class="sxs-lookup"><span data-stu-id="a6106-123">Run the query again.</span></span>  
  
  
