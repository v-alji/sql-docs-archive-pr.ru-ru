---
title: Счетчики производительности XTP (выполняющаяся в памяти OLTP) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: fe3cbaf4-65f4-44c5-acc6-7b735cda0c5d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4363a526ada3694e92d18cac0d7abe8a26f6a92f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730570"
---
# <a name="xtp-in-memory-oltp-performance-counters"></a><span data-ttu-id="4f9a7-102">Счетчики производительности XTP (In-Memory OLTP)</span><span class="sxs-lookup"><span data-stu-id="4f9a7-102">XTP (In-Memory OLTP) Performance Counters</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4f9a7-103">предоставляет объекты и счетчики, которые могут использоваться системным монитором для отслеживания активности In-Memory OLTP.</span><span class="sxs-lookup"><span data-stu-id="4f9a7-103">provides objects and counters that can be used by Performance Monitor to monitor In-Memory OLTP activity.</span></span>  
  
##  <a name="xtp-in-memory-oltp-performance-objects"></a><a name="SQLServerPOs"></a><span data-ttu-id="4f9a7-104">Объекты производительности XTP (выполняющаяся в памяти OLTP)</span><span class="sxs-lookup"><span data-stu-id="4f9a7-104">XTP (In-Memory OLTP) Performance Objects</span></span>  
 <span data-ttu-id="4f9a7-105">В следующей таблице описаны объекты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f9a7-105">The following table describes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects.</span></span>  
  
|<span data-ttu-id="4f9a7-106">Объект производительности</span><span class="sxs-lookup"><span data-stu-id="4f9a7-106">Performance object</span></span>|<span data-ttu-id="4f9a7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4f9a7-107">Description</span></span>|  
|------------------------|-----------------|  
|[<span data-ttu-id="4f9a7-108">Курсоры XTP</span><span class="sxs-lookup"><span data-stu-id="4f9a7-108">XTP Cursors</span></span>](../cursors.md)|<span data-ttu-id="4f9a7-109">Объект производительности XTP Cursors содержит счетчики, относящиеся к внутренним курсорам механизма XTP.</span><span class="sxs-lookup"><span data-stu-id="4f9a7-109">The XTP Cursors performance object contains counters related to internal XTP engine cursors.</span></span> <span data-ttu-id="4f9a7-110">Курсоры — низкоуровневые строительные блоки, используемые механизмом XTP для обработки запросов [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f9a7-110">Cursors are the low-level building blocks the XTP engine uses to process [!INCLUDE[tsql](../../includes/tsql-md.md)] queries.</span></span> <span data-ttu-id="4f9a7-111">Обычно вы не имеете прямого контроля над ними как таковыми.</span><span class="sxs-lookup"><span data-stu-id="4f9a7-111">As such, you do not typically have direct control over them.</span></span>|  
|[<span data-ttu-id="4f9a7-112">Сборка мусора XTP</span><span class="sxs-lookup"><span data-stu-id="4f9a7-112">XTP Garbage Collection</span></span>](sql-server-xtp-garbage-collection.md)|<span data-ttu-id="4f9a7-113">Объект производительности XTP Garbage Collection содержит счетчики, относящиеся к механизму сборщика мусора XTP.</span><span class="sxs-lookup"><span data-stu-id="4f9a7-113">The XTP Garbage Collection performance object contains counters related to the XTP engine's garbage collector.</span></span>|  
|[<span data-ttu-id="4f9a7-114">XTP Phantom Processor</span><span class="sxs-lookup"><span data-stu-id="4f9a7-114">XTP Phantom Processor</span></span>](sql-server-xtp-phantom-processor.md)|<span data-ttu-id="4f9a7-115">Объект производительности XTP Phantom Processor содержит счетчики, относящиеся к подсистеме обработки фантомов механизма XTP.</span><span class="sxs-lookup"><span data-stu-id="4f9a7-115">The XTP Phantom Processor performance object contains counters related to the XTP engine's phantom processing subsystem.</span></span> <span data-ttu-id="4f9a7-116">Этот компонент отвечает за обнаружение фантомных строк в транзакциях, выполняемых на уровне изоляции SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="4f9a7-116">This component is responsible for detecting phantom rows in transactions running at the SERIALIZABLE isolation level.</span></span>|  
|[<span data-ttu-id="4f9a7-117">Хранилище XTP</span><span class="sxs-lookup"><span data-stu-id="4f9a7-117">XTP Storage</span></span>](sql-server-xtp-storage.md)|<span data-ttu-id="4f9a7-118">Объект производительности XTP Storage содержит счетчики, относящиеся к хранилищу XTP в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f9a7-118">The XTP Storage performance object contains counters related to XTP storage in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="4f9a7-119">Журнал транзакций XTP</span><span class="sxs-lookup"><span data-stu-id="4f9a7-119">XTP Transaction Log</span></span>](sql-server-xtp-transaction-log.md)|<span data-ttu-id="4f9a7-120">Объект производительности XTP Transaction Log содержит счетчики, относящиеся к ведению журнала XTP в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f9a7-120">The XTP Transaction Log performance object contains counters related to XTP transaction logging in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="4f9a7-121">Транзакции XTP</span><span class="sxs-lookup"><span data-stu-id="4f9a7-121">XTP Transactions</span></span>](sql-server-xtp-transactions.md)|<span data-ttu-id="4f9a7-122">Объект производительности XTP Transactions содержит счетчики, относящиеся к транзакциям механизма XTP в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f9a7-122">The XTP Transactions performance object contains counters related to XTP engine transactions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
  
  
