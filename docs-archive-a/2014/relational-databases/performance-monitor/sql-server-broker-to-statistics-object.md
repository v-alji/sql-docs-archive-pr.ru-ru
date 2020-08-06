---
title: SQL Server, объект Broker TO Statistics | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Broker Transmission Object object
- 'SQL Server: Broker Transmission Object'
ms.assetid: b5bc5dde-e540-4848-8aa3-5735c51df2fb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 93d9c24a175dedfee171eccfccb34673501660ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667035"
---
# <a name="sql-server-broker-to-statistics-object"></a><span data-ttu-id="7316f-102">SQL Server, объект Broker TO Statistics</span><span class="sxs-lookup"><span data-stu-id="7316f-102">SQL Server, Broker TO Statistics Object</span></span>
  <span data-ttu-id="7316f-103">Объект производительности SQLServer:Broker TO Statistics сообщает о том, сколько раз в диалогах компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)] запрашиваются объекты передачи и как часто объекты передачи записываются в базу данных **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="7316f-103">The SQLServer:Broker TO Statistics performance object reports information about how many times [!INCLUDE[ssSB](../../includes/sssb-md.md)] dialogs request transmission objects, and how often transmission objects are written to **tempdb**.</span></span>  
  
 <span data-ttu-id="7316f-104">В объектах передачи записывается состояние передач сообщений для диалога компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7316f-104">Transmission objects record the state of message transmissions for a [!INCLUDE[ssSB](../../includes/sssb-md.md)] dialog.</span></span> <span data-ttu-id="7316f-105">Они хранятся в памяти.</span><span class="sxs-lookup"><span data-stu-id="7316f-105">They are stored in memory.</span></span> <span data-ttu-id="7316f-106">Чтобы освободить память, компонент [!INCLUDE[ssSB](../../includes/sssb-md.md)] периодически записывает пакеты неактивных объектов передачи в рабочие таблицы базы данных **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="7316f-106">To free memory, [!INCLUDE[ssSB](../../includes/sssb-md.md)] periodically writes batches of inactive transmission objects to work tables in **tempdb**.</span></span>  
  
 <span data-ttu-id="7316f-107">В следующей таблице перечислены счетчики этого объекта.</span><span class="sxs-lookup"><span data-stu-id="7316f-107">The following table lists the counters that this object contains.</span></span>  
  
|<span data-ttu-id="7316f-108">Счетчики объекта SQL Server Broker TO Statistics</span><span class="sxs-lookup"><span data-stu-id="7316f-108">SQL Server Broker TO Statistics counters</span></span>|<span data-ttu-id="7316f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="7316f-109">Description</span></span>|  
|----------------------------------------------|-----------------|  
|<span data-ttu-id="7316f-110">**Средн. длина пакетов записи**</span><span class="sxs-lookup"><span data-stu-id="7316f-110">**Avg. Length of Batched Writes**</span></span>|<span data-ttu-id="7316f-111">Среднее число объектов передачи, сохраняемых в пакете.</span><span class="sxs-lookup"><span data-stu-id="7316f-111">The average number of transmission objects saved in a batch.</span></span>|  
|<span data-ttu-id="7316f-112">**Средн. время записи пакета (мс)**</span><span class="sxs-lookup"><span data-stu-id="7316f-112">**Avg. Time To Write Batch (ms)**</span></span>|<span data-ttu-id="7316f-113">Среднее время в миллисекундах, необходимое для сохранения пакета объектов передачи.</span><span class="sxs-lookup"><span data-stu-id="7316f-113">The average number of milliseconds required to save a batch of transmission objects.</span></span>|  
|<span data-ttu-id="7316f-114">**Средн. время между пакетами (мс)**</span><span class="sxs-lookup"><span data-stu-id="7316f-114">**Avg. Time Between Batches (ms)**</span></span>|<span data-ttu-id="7316f-115">Среднее время в миллисекундах между записью пакетов объектов передачи.</span><span class="sxs-lookup"><span data-stu-id="7316f-115">The average number of milliseconds between writes of transmission object batches.</span></span>|  
|<span data-ttu-id="7316f-116">**Получено объектов передачи/с**</span><span class="sxs-lookup"><span data-stu-id="7316f-116">**Tran Object Gets/sec**</span></span>|<span data-ttu-id="7316f-117">Число раз в секунду, когда диалоги запрашивали объекты передачи.</span><span class="sxs-lookup"><span data-stu-id="7316f-117">The number of times per second that dialogs requested transmission objects.</span></span>|  
|<span data-ttu-id="7316f-118">**Грязных объектов передачи/с**</span><span class="sxs-lookup"><span data-stu-id="7316f-118">**Tran Objects Marked Dirty/sec**</span></span>|<span data-ttu-id="7316f-119">Число раз в секунду, когда объекты передачи были отмечены как грязные.</span><span class="sxs-lookup"><span data-stu-id="7316f-119">The number of times per second that transmission objects were marked as dirty.</span></span> <span data-ttu-id="7316f-120">Объекты передачи отмечаются как грязные при первом изменении, которое приводит к тому, что копия в памяти отличается от копии в базе данных **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="7316f-120">Transmission objects are marked as dirty by the first modification that causes the in-memory copy to differ from the copy stored in **tempdb**.</span></span> <span data-ttu-id="7316f-121">Объекты передачи изменяются, когда компонент [!INCLUDE[ssSB](../../includes/sssb-md.md)] должен записать изменение в состоянии передач сообщений для диалога.</span><span class="sxs-lookup"><span data-stu-id="7316f-121">Transmission objects are modified when [!INCLUDE[ssSB](../../includes/sssb-md.md)] has to record a change in the state of message transmissions for the dialog.</span></span>|  
|<span data-ttu-id="7316f-122">**Запись объектов передачи/с**</span><span class="sxs-lookup"><span data-stu-id="7316f-122">**Tran Object Writes/sec**</span></span>|<span data-ttu-id="7316f-123">Число раз в секунду, когда пакет объектов передачи был записан в рабочие таблицы базы данных **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="7316f-123">The number of times per second that a batch of transmission objects were written to **tempdb** work tables.</span></span> <span data-ttu-id="7316f-124">Большое число записей может говорить о нехватке памяти для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7316f-124">Large numbers of writes could indicate that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory is being stressed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7316f-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="7316f-125">See Also</span></span>  
 <span data-ttu-id="7316f-126">[SQL Server, объект Access Methods](sql-server-access-methods-object.md) </span><span class="sxs-lookup"><span data-stu-id="7316f-126">[SQL Server, Access Methods Object](sql-server-access-methods-object.md) </span></span>  
 <span data-ttu-id="7316f-127">[SQL Server, объект Memory Manager](sql-server-memory-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="7316f-127">[SQL Server, Memory Manager Object](sql-server-memory-manager-object.md) </span></span>  
 [<span data-ttu-id="7316f-128">Наблюдение за использованием ресурсов (системный монитор)</span><span class="sxs-lookup"><span data-stu-id="7316f-128">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
