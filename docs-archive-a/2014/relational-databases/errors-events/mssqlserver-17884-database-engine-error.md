---
title: MSSQLSERVER_17884 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17884 (Database Engine error)
ms.assetid: 8d05ba05-3f71-4dc3-bd81-2ea5ac9fe843
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bd5beca2a7dfd20afbf9eff196d89452ef3533d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734110"
---
# <a name="mssqlserver_17884"></a><span data-ttu-id="bc94e-102">MSSQLSERVER_17884</span><span class="sxs-lookup"><span data-stu-id="bc94e-102">MSSQLSERVER_17884</span></span>
    
## <a name="details"></a><span data-ttu-id="bc94e-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="bc94e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bc94e-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="bc94e-104">Product Name</span></span>|<span data-ttu-id="bc94e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bc94e-105">SQL Server</span></span>|  
|<span data-ttu-id="bc94e-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="bc94e-106">Event ID</span></span>|<span data-ttu-id="bc94e-107">17884</span><span class="sxs-lookup"><span data-stu-id="bc94e-107">17884</span></span>|  
|<span data-ttu-id="bc94e-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="bc94e-108">Event Source</span></span>|<span data-ttu-id="bc94e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bc94e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bc94e-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="bc94e-110">Component</span></span>|<span data-ttu-id="bc94e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bc94e-111">SQLEngine</span></span>|  
|<span data-ttu-id="bc94e-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="bc94e-112">Symbolic Name</span></span>|<span data-ttu-id="bc94e-113">SRV_SCHEDULER_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="bc94e-113">SRV_SCHEDULER_DEADLOCK</span></span>|  
|<span data-ttu-id="bc94e-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="bc94e-114">Message Text</span></span>|<span data-ttu-id="bc94e-115">Новые запросы, предназначенные для обработки на узле %d, не приняты рабочим потоком в течение %d секунд.</span><span class="sxs-lookup"><span data-stu-id="bc94e-115">New queries assigned to process on Node %d have not been picked  up by a worker thread in the last %d seconds.</span></span> <span data-ttu-id="bc94e-116">Это может быть вызвано блокирующими или долго выполняющимися запросами, которые увеличивают время ответа клиента.</span><span class="sxs-lookup"><span data-stu-id="bc94e-116">Blocking or long-running queries can contribute to this condition, and may degrade client response time.</span></span> <span data-ttu-id="bc94e-117">При помощи параметра конфигурации max worker threads увеличьте число допустимых потоков либо оптимизируйте запросы, выполняемые в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="bc94e-117">Use the "max worker threads" configuration option to increase number  of allowable threads, or optimize current running queries.</span></span>  <span data-ttu-id="bc94e-118">Эффективность использования процесса SQL: %d%%.</span><span class="sxs-lookup"><span data-stu-id="bc94e-118">SQL Process Utilization: %d%%.</span></span> <span data-ttu-id="bc94e-119">Бездействие системы %d%%.</span><span class="sxs-lookup"><span data-stu-id="bc94e-119">System Idle: %d%%.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bc94e-120">Объяснение</span><span class="sxs-lookup"><span data-stu-id="bc94e-120">Explanation</span></span>  
 <span data-ttu-id="bc94e-121">Ни один из планировщиков не подает признаков выполнения. Это может быть вызвано взаимоблокировкой, при которой ни один поток не может продолжать работу и ни одно новое задание не может быть принято и обработано.</span><span class="sxs-lookup"><span data-stu-id="bc94e-121">There is no sign of progress in each of the schedulers and could be caused by deadlocks where none of the threads can advance and/or no new work can be picked up and processed.</span></span> <span data-ttu-id="bc94e-122">Если эффективность процесса низкая, то возможно, что другие процессы, выполняемые на том же компьютере, вызывают нехватку ресурсов ЦП для серверного процесса.</span><span class="sxs-lookup"><span data-stu-id="bc94e-122">If process utilization is low then other processes on the machine may be causing the server process CPU starvation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bc94e-123">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="bc94e-123">User Action</span></span>  
 <span data-ttu-id="bc94e-124">Определите причину блокировки и остановки выполнения. Устраните найденные проблемы.</span><span class="sxs-lookup"><span data-stu-id="bc94e-124">Determine why there is blocking and no progress being made and resolve situation accordingly.</span></span> <span data-ttu-id="bc94e-125">Если эффективность процесса низкая, проверьте, какую нагрузку на систему создают другие процессы.</span><span class="sxs-lookup"><span data-stu-id="bc94e-125">If process utilization is low check the load on the system caused by other processes.</span></span>  
  
  
