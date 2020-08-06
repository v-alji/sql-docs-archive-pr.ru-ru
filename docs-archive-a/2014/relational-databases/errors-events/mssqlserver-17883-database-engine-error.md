---
title: MSSQLSERVER_17883 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17883 (Database Engine error)
ms.assetid: adaf1c04-e397-4a69-90b8-9353a37277ea
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 46488fb6f7adac2c1109871f2aad4c79352829ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729522"
---
# <a name="mssqlserver_17883"></a><span data-ttu-id="b18ee-102">MSSQLSERVER_17883</span><span class="sxs-lookup"><span data-stu-id="b18ee-102">MSSQLSERVER_17883</span></span>
    
## <a name="details"></a><span data-ttu-id="b18ee-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="b18ee-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b18ee-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="b18ee-104">Product Name</span></span>|<span data-ttu-id="b18ee-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b18ee-105">SQL Server</span></span>|  
|<span data-ttu-id="b18ee-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="b18ee-106">Event ID</span></span>|<span data-ttu-id="b18ee-107">17883</span><span class="sxs-lookup"><span data-stu-id="b18ee-107">17883</span></span>|  
|<span data-ttu-id="b18ee-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="b18ee-108">Event Source</span></span>|<span data-ttu-id="b18ee-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b18ee-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b18ee-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="b18ee-110">Component</span></span>|<span data-ttu-id="b18ee-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b18ee-111">SQLEngine</span></span>|  
|<span data-ttu-id="b18ee-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="b18ee-112">Symbolic Name</span></span>|<span data-ttu-id="b18ee-113">SRV_SCHEDULER_NONYIELDING</span><span class="sxs-lookup"><span data-stu-id="b18ee-113">SRV_SCHEDULER_NONYIELDING</span></span>|  
|<span data-ttu-id="b18ee-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="b18ee-114">Message Text</span></span>|<span data-ttu-id="b18ee-115">Процесс %ld:%ld:%ld (0x%lx) Worker 0x%p, по-видимому, не возвращает управление планировщику %ld.</span><span class="sxs-lookup"><span data-stu-id="b18ee-115">Process %ld:%ld:%ld (0x%lx) Worker 0x%p appears to be non-yielding on Scheduler %ld.</span></span> <span data-ttu-id="b18ee-116">Время создания потока: %I64d.</span><span class="sxs-lookup"><span data-stu-id="b18ee-116">Thread creation time: %I64d.</span></span> <span data-ttu-id="b18ee-117">Примерная загрузка ЦП для потока: ядро %I64d мс, пользователь %I64d мс.</span><span class="sxs-lookup"><span data-stu-id="b18ee-117">Approx Thread CPU Used: kernel %I64d ms, user %I64d ms.</span></span> <span data-ttu-id="b18ee-118">Эффективность использования процесса %d%%.</span><span class="sxs-lookup"><span data-stu-id="b18ee-118">Process Utilization %d%%.</span></span> <span data-ttu-id="b18ee-119">Бездействие системы %d%%.</span><span class="sxs-lookup"><span data-stu-id="b18ee-119">System Idle %d%%.</span></span> <span data-ttu-id="b18ee-120">Интервал: %I64d мс.</span><span class="sxs-lookup"><span data-stu-id="b18ee-120">Interval: %I64d ms.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b18ee-121">Объяснение</span><span class="sxs-lookup"><span data-stu-id="b18ee-121">Explanation</span></span>  
 <span data-ttu-id="b18ee-122">Указывает на возможную проблему, в результате которой поток не возвращает управление планировщику.</span><span class="sxs-lookup"><span data-stu-id="b18ee-122">Indicates that there is a possible problem with a thread not yielding on a scheduler.</span></span>  <span data-ttu-id="b18ee-123">Возможно, это сбой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] либо [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не получает достаточно циклов процессора для выполнения.</span><span class="sxs-lookup"><span data-stu-id="b18ee-123">This could be caused by a bug in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not getting enough cycles to execute.</span></span>  <span data-ttu-id="b18ee-124">Эта ошибка может исчезнуть, если поток, в конце концов, передаст управление.</span><span class="sxs-lookup"><span data-stu-id="b18ee-124">This error could go away if the thread eventually yields.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b18ee-125">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="b18ee-125">User Action</span></span>  
 <span data-ttu-id="b18ee-126">В случае избыточной нагрузки на систему уменьшите ее. В противном случае обратитесь в службу поддержки пользователей Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b18ee-126">If excessive load on system reduce load otherwise contact Microsoft Customer Support Services.</span></span>  
  
  
