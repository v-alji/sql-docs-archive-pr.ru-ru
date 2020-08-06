---
title: MSSQLSERVER_7913 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7913 (Database Engine error)
ms.assetid: 9d8ad456-b1a2-4f79-a252-657fbec9ad9b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fb4110ef3aed8697db426ebd80f6764d873944db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664933"
---
# <a name="mssqlserver_7913"></a><span data-ttu-id="64520-102">MSSQLSERVER_7913</span><span class="sxs-lookup"><span data-stu-id="64520-102">MSSQLSERVER_7913</span></span>
    
## <a name="details"></a><span data-ttu-id="64520-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="64520-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="64520-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="64520-104">Product Name</span></span>|<span data-ttu-id="64520-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="64520-105">SQL Server</span></span>|  
|<span data-ttu-id="64520-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="64520-106">Event ID</span></span>|<span data-ttu-id="64520-107">7913</span><span class="sxs-lookup"><span data-stu-id="64520-107">7913</span></span>|  
|<span data-ttu-id="64520-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="64520-108">Event Source</span></span>|<span data-ttu-id="64520-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="64520-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="64520-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="64520-110">Component</span></span>|<span data-ttu-id="64520-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="64520-111">SQLEngine</span></span>|  
|<span data-ttu-id="64520-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="64520-112">Symbolic Name</span></span>|<span data-ttu-id="64520-113">DBCC2_REPAIR_EXTENT_DEALLOCATED</span><span class="sxs-lookup"><span data-stu-id="64520-113">DBCC2_REPAIR_EXTENT_DEALLOCATED</span></span>|  
|<span data-ttu-id="64520-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="64520-114">Message Text</span></span>|<span data-ttu-id="64520-115">Исправление: выделение экстента P_ID отменено для объекта с идентификатором O_ID, индекса с идентификатором I_ID, секции с идентификатором PN_ID, единицы размещения с идентификатором A_ID (тип TYPE).</span><span class="sxs-lookup"><span data-stu-id="64520-115">Repair: Extent P_ID has been deallocated from object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="64520-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="64520-116">Explanation</span></span>  
 <span data-ttu-id="64520-117">Это информационное сообщение функции REPAIR, которое означает, что указанный объект был удален из экстента.</span><span class="sxs-lookup"><span data-stu-id="64520-117">This is an informational message from REPAIR that states that an extent has been deallocated from the specified object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="64520-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="64520-118">User Action</span></span>  
 <span data-ttu-id="64520-119">None</span><span class="sxs-lookup"><span data-stu-id="64520-119">None</span></span>  
  
  
