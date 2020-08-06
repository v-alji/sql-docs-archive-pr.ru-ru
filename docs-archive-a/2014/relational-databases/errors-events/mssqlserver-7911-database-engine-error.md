---
title: MSSQLSERVER_7911 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7911 (Database Engine error)
ms.assetid: dd8390f3-0f77-4fb2-ba94-631a56e42bc6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6d37ce2dc11f231e8a6f8ae6cc8b95d8b2f87c12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664217"
---
# <a name="mssqlserver_7911"></a><span data-ttu-id="6718f-102">MSSQLSERVER_7911</span><span class="sxs-lookup"><span data-stu-id="6718f-102">MSSQLSERVER_7911</span></span>
    
## <a name="details"></a><span data-ttu-id="6718f-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="6718f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6718f-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="6718f-104">Product Name</span></span>|<span data-ttu-id="6718f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6718f-105">SQL Server</span></span>|  
|<span data-ttu-id="6718f-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6718f-106">Event ID</span></span>|<span data-ttu-id="6718f-107">7911</span><span class="sxs-lookup"><span data-stu-id="6718f-107">7911</span></span>|  
|<span data-ttu-id="6718f-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="6718f-108">Event Source</span></span>|<span data-ttu-id="6718f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6718f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6718f-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="6718f-110">Component</span></span>|<span data-ttu-id="6718f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6718f-111">SQLEngine</span></span>|  
|<span data-ttu-id="6718f-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="6718f-112">Symbolic Name</span></span>|<span data-ttu-id="6718f-113">DBCC2_REPAIR_PAGE_DEALLOCATED</span><span class="sxs-lookup"><span data-stu-id="6718f-113">DBCC2_REPAIR_PAGE_DEALLOCATED</span></span>|  
|<span data-ttu-id="6718f-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="6718f-114">Message Text</span></span>|<span data-ttu-id="6718f-115">Исправление: отменено выделение страницы P_ID объекту с идентификатором O_ID, идентификатором индекса I_ID, идентификатором секции PN_ID, идентификатором единицы распределения A_ID (тип TYPE).</span><span class="sxs-lookup"><span data-stu-id="6718f-115">Repair: The page P_ID has been deallocated from object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6718f-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="6718f-116">Explanation</span></span>  
 <span data-ttu-id="6718f-117">Это информационное сообщение инструкции REPAIR, указывающее, что страница была освобождена из карты распределения индекса (IAM)-страницы.</span><span class="sxs-lookup"><span data-stu-id="6718f-117">This is an informational message from REPAIR that states that a page has been deallocated from the single-page slot array of an Index Allocation Map (IAM) page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6718f-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="6718f-118">User Action</span></span>  
 <span data-ttu-id="6718f-119">None</span><span class="sxs-lookup"><span data-stu-id="6718f-119">None</span></span>  
  
  
