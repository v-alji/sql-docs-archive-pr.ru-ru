---
title: MSSQLSERVER_7910 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7910 (Database Engine error)
ms.assetid: 017a0113-2b17-40b3-a419-30bbc43d46b8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60e7cca3f6973374ae7aeaa959a0b31207a1258e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664219"
---
# <a name="mssqlserver_7910"></a><span data-ttu-id="05938-102">MSSQLSERVER_7910</span><span class="sxs-lookup"><span data-stu-id="05938-102">MSSQLSERVER_7910</span></span>
    
## <a name="details"></a><span data-ttu-id="05938-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="05938-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05938-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="05938-104">Product Name</span></span>|<span data-ttu-id="05938-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="05938-105">SQL Server</span></span>|  
|<span data-ttu-id="05938-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="05938-106">Event ID</span></span>|<span data-ttu-id="05938-107">7910</span><span class="sxs-lookup"><span data-stu-id="05938-107">7910</span></span>|  
|<span data-ttu-id="05938-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="05938-108">Event Source</span></span>|<span data-ttu-id="05938-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="05938-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="05938-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="05938-110">Component</span></span>|<span data-ttu-id="05938-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="05938-111">SQLEngine</span></span>|  
|<span data-ttu-id="05938-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="05938-112">Symbolic Name</span></span>|<span data-ttu-id="05938-113">DBCC2_REPAIR_PAGE_ALLOCATED</span><span class="sxs-lookup"><span data-stu-id="05938-113">DBCC2_REPAIR_PAGE_ALLOCATED</span></span>|  
|<span data-ttu-id="05938-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="05938-114">Message Text</span></span>|<span data-ttu-id="05938-115">Исправление: страница P_ID выделена объекту с идентификатором O_ID, идентификатором индекса I_ID, идентификатором секции PN_ID, идентификатором единицы распределения A_ID (тип TYPE).</span><span class="sxs-lookup"><span data-stu-id="05938-115">Repair: The page P_ID has been allocated to object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="05938-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="05938-116">Explanation</span></span>  
 <span data-ttu-id="05938-117">Это информационное сообщение инструкции REPAIR, указывающее, что страница была размещена в карте распределения индекса (IAM)-страницы.</span><span class="sxs-lookup"><span data-stu-id="05938-117">This is an informational message from REPAIR that states that a page has been allocated to the single-page slot array of an Index Allocation Map (IAM) page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="05938-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="05938-118">User Action</span></span>  
 <span data-ttu-id="05938-119">None</span><span class="sxs-lookup"><span data-stu-id="05938-119">None</span></span>  
  
  
