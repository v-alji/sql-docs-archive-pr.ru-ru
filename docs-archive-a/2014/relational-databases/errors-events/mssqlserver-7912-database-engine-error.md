---
title: MSSQLSERVER_7912 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7912 (Database Engine error)
ms.assetid: 8e6157c2-7e84-49f2-965a-c7426c2b23fa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 634ed43a4a8bcd2edde03fe5f6b9f052346ddb8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664935"
---
# <a name="mssqlserver_7912"></a><span data-ttu-id="f9019-102">MSSQLSERVER_7912</span><span class="sxs-lookup"><span data-stu-id="f9019-102">MSSQLSERVER_7912</span></span>
    
## <a name="details"></a><span data-ttu-id="f9019-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="f9019-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f9019-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="f9019-104">Product Name</span></span>|<span data-ttu-id="f9019-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f9019-105">SQL Server</span></span>|  
|<span data-ttu-id="f9019-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="f9019-106">Event ID</span></span>|<span data-ttu-id="f9019-107">7912</span><span class="sxs-lookup"><span data-stu-id="f9019-107">7912</span></span>|  
|<span data-ttu-id="f9019-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="f9019-108">Event Source</span></span>|<span data-ttu-id="f9019-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f9019-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f9019-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="f9019-110">Component</span></span>|<span data-ttu-id="f9019-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f9019-111">SQLEngine</span></span>|  
|<span data-ttu-id="f9019-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="f9019-112">Symbolic Name</span></span>|<span data-ttu-id="f9019-113">DBCC2_REPAIR_EXTENT_ALLOCATED</span><span class="sxs-lookup"><span data-stu-id="f9019-113">DBCC2_REPAIR_EXTENT_ALLOCATED</span></span>|  
|<span data-ttu-id="f9019-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="f9019-114">Message Text</span></span>|<span data-ttu-id="f9019-115">Исправление: экстент P_ID выделен для объекта с идентификатором O_ID, индекса с идентификатором I_ID, секции с идентификатором PN_ID, единицы распределения с идентификатором A_ID (тип TYPE).</span><span class="sxs-lookup"><span data-stu-id="f9019-115">Repair: Extent P_ID has been allocated to object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f9019-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="f9019-116">Explanation</span></span>  
 <span data-ttu-id="f9019-117">Это информационное сообщение функции REPAIR, которое означает, что для указанного объекта был выделен экстент.</span><span class="sxs-lookup"><span data-stu-id="f9019-117">This is an informational message from REPAIR that states that an extent has been allocated to the specified object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f9019-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="f9019-118">User Action</span></span>  
 <span data-ttu-id="f9019-119">None</span><span class="sxs-lookup"><span data-stu-id="f9019-119">None</span></span>  
  
  
