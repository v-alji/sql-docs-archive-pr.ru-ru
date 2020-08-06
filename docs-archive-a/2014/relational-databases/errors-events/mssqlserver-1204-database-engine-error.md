---
title: MSSQLSERVER_1204 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1204 (Database Engine error)
ms.assetid: de6ece78-79de-484d-9224-ca0f7645815f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7ca03c19552b88e391d2de053193a70531571ece
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658794"
---
# <a name="mssqlserver_1204"></a><span data-ttu-id="96a08-102">MSSQLSERVER_1204</span><span class="sxs-lookup"><span data-stu-id="96a08-102">MSSQLSERVER_1204</span></span>
    
## <a name="details"></a><span data-ttu-id="96a08-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="96a08-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="96a08-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="96a08-104">Product Name</span></span>|<span data-ttu-id="96a08-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="96a08-105">SQL Server</span></span>|  
|<span data-ttu-id="96a08-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="96a08-106">Event ID</span></span>|<span data-ttu-id="96a08-107">1204</span><span class="sxs-lookup"><span data-stu-id="96a08-107">1204</span></span>|  
|<span data-ttu-id="96a08-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="96a08-108">Event Source</span></span>|<span data-ttu-id="96a08-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="96a08-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="96a08-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="96a08-110">Component</span></span>|<span data-ttu-id="96a08-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="96a08-111">SQLEngine</span></span>|  
|<span data-ttu-id="96a08-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="96a08-112">Symbolic Name</span></span>|<span data-ttu-id="96a08-113">LK_OUTOF</span><span class="sxs-lookup"><span data-stu-id="96a08-113">LK_OUTOF</span></span>|  
|<span data-ttu-id="96a08-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="96a08-114">Message Text</span></span>|<span data-ttu-id="96a08-115">Экземпляру компонента SQL Server Database Engine не удается получить ресурс LOCK в данный момент времени.</span><span class="sxs-lookup"><span data-stu-id="96a08-115">The instance of the SQL Server Database Engine cannot obtain a LOCK resource at this time.</span></span> <span data-ttu-id="96a08-116">Запустите инструкцию повторно, когда число активных пользователей уменьшится.</span><span class="sxs-lookup"><span data-stu-id="96a08-116">Rerun your statement when there are fewer active users.</span></span> <span data-ttu-id="96a08-117">Попросите администратора баз данных проверить конфигурацию блокировки и памяти для данного экземпляра либо выполнить проверку давно выполняющихся транзакций.</span><span class="sxs-lookup"><span data-stu-id="96a08-117">Ask the database administrator to check the lock and memory configuration for this instance, or to check for long-running transactions.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="96a08-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="96a08-118">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="96a08-119">не удается получить ресурс блокировки.</span><span class="sxs-lookup"><span data-stu-id="96a08-119">cannot obtain a lock resource.</span></span> <span data-ttu-id="96a08-120">Возможны следующие причины этой ошибки.</span><span class="sxs-lookup"><span data-stu-id="96a08-120">This can be caused by either of the following reasons:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="96a08-121">не удается получить дополнительную память операционной системы из-за того, что другие процессы используют ее, либо из-за того, что для сервера установлено значение параметра **max server memory**.</span><span class="sxs-lookup"><span data-stu-id="96a08-121">cannot allocate more memory from the operating system, either because other processes are using it, or because the server is operating with the **max server memory** option configured.</span></span>  
  
-   <span data-ttu-id="96a08-122">Диспетчер блокировок не может использовать более 60 процентов доступной памяти для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96a08-122">The lock manager will not use more than 60 percent of the memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="96a08-123">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="96a08-123">User Action</span></span>  
 <span data-ttu-id="96a08-124">Если возникли подозрения, что SQL Server не может выделить необходимое количество памяти, попробуйте следующее.</span><span class="sxs-lookup"><span data-stu-id="96a08-124">If you suspect that SQL Server cannot allocate sufficient memory, try the following:</span></span>  
  
-   <span data-ttu-id="96a08-125">Если другие приложения, кроме SQL Server, используют ресурсы, попытайтесь закрыть эти приложения или запустите их на отдельном сервере.</span><span class="sxs-lookup"><span data-stu-id="96a08-125">If applications besides SQL Server are consuming resources, try stopping these applications or consider running them on a separate server.</span></span> <span data-ttu-id="96a08-126">В результате память от других процессов освободится для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="96a08-126">This will remove release memory from other processes for SQL Server.</span></span>  
  
-   <span data-ttu-id="96a08-127">Если задан параметр max server memory, увеличьте его значение.</span><span class="sxs-lookup"><span data-stu-id="96a08-127">If you have configured max server memory, increase max server memory setting.</span></span>  
  
 <span data-ttu-id="96a08-128">Если есть подозрения, что диспетчер блокировок использовал максимальное количество свободной памяти, определите, какая транзакция удерживает больше всего блокировок, и завершите ее работу.</span><span class="sxs-lookup"><span data-stu-id="96a08-128">If you suspect that the lock manager has used the maximum amount of available memory identify the transaction that is holding the most locks and terminate it.</span></span> <span data-ttu-id="96a08-129">С помощью следующего скрипта можно определить, какая из транзакций удерживает больше всего блокировок:</span><span class="sxs-lookup"><span data-stu-id="96a08-129">The following script will identify the transaction with the most locks:</span></span>  
  
```  
SELECT request_session_id, COUNT (*) num_locks  
FROM sys.dm_tran_locks  
GROUP BY request_session_id   
ORDER BY count (*) DESC  
```  
  
 <span data-ttu-id="96a08-130">Завершите работу сеанса с первым идентификатором с помощью команды KILL.</span><span class="sxs-lookup"><span data-stu-id="96a08-130">Take the highest session id, and terminate it using the KILL command.</span></span>  
  
  
