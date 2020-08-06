---
title: MSSQLSERVER_7915 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7915 (Database Engine error)
ms.assetid: 63338587-7dd3-40e6-b70e-d8ae18fff47b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1dc7a69023e49b48a10da9f0388cbd72fbe46be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664930"
---
# <a name="mssqlserver_7915"></a><span data-ttu-id="be539-102">MSSQLSERVER_7915</span><span class="sxs-lookup"><span data-stu-id="be539-102">MSSQLSERVER_7915</span></span>
    
## <a name="details"></a><span data-ttu-id="be539-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="be539-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be539-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="be539-104">Product Name</span></span>|<span data-ttu-id="be539-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="be539-105">SQL Server</span></span>|  
|<span data-ttu-id="be539-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="be539-106">Event ID</span></span>|<span data-ttu-id="be539-107">7915</span><span class="sxs-lookup"><span data-stu-id="be539-107">7915</span></span>|  
|<span data-ttu-id="be539-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="be539-108">Event Source</span></span>|<span data-ttu-id="be539-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="be539-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="be539-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="be539-110">Component</span></span>|<span data-ttu-id="be539-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="be539-111">SQLEngine</span></span>|  
|<span data-ttu-id="be539-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="be539-112">Symbolic Name</span></span>|<span data-ttu-id="be539-113">DBCC2_REPAIR_IAM_CHAIN_REBUILT</span><span class="sxs-lookup"><span data-stu-id="be539-113">DBCC2_REPAIR_IAM_CHAIN_REBUILT</span></span>|  
|<span data-ttu-id="be539-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="be539-114">Message Text</span></span>|<span data-ttu-id="be539-115">Исправление: последовательность IAM для объекта с идентификатором O_ID, идентификатором индекса I_ID, идентификатором секции PN_ID, идентификатором единицы распределения A_ID (тип TYPE) была усечена до страницы P_ID и будет перестроена.</span><span class="sxs-lookup"><span data-stu-id="be539-115">Repair: IAM chain for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), has been truncated before page P_ID and will be rebuilt.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="be539-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="be539-116">Explanation</span></span>  
 <span data-ttu-id="be539-117">Это информационное сообщение, отправляемое командой REPAIR, указывает на то, что определенная цепочка карты распределения индекса (IAM) была обновлена, поэтому ее можно перестроить.</span><span class="sxs-lookup"><span data-stu-id="be539-117">This is an information message sent by REPAIR that indicates that the specified Index Allocation Map (IAM) chain was patched so that it could be rebuilt.</span></span> <span data-ttu-id="be539-118">Для этого обновления, возможно, потребуется размещение нового заголовка IAM-цепочки или удаление из цепочки испорченных страниц.</span><span class="sxs-lookup"><span data-stu-id="be539-118">This patching may have required the allocation of a new head of the IAM chain or the removal of bad pages from the chain.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="be539-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="be539-119">User Action</span></span>  
 <span data-ttu-id="be539-120">None</span><span class="sxs-lookup"><span data-stu-id="be539-120">None</span></span>  
  
  
