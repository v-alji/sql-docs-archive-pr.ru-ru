---
title: MSSQLSERVER_1205 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1205 (Database Engine error)
ms.assetid: 9fe3f67c-df3c-4642-a3a4-ccc0e138b632
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b6afa81a05eea37bc67cd2e9ac2433b6c82f35b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654325"
---
# <a name="mssqlserver_1205"></a><span data-ttu-id="83622-102">MSSQLSERVER_1205</span><span class="sxs-lookup"><span data-stu-id="83622-102">MSSQLSERVER_1205</span></span>
    
## <a name="details"></a><span data-ttu-id="83622-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="83622-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="83622-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="83622-104">Product Name</span></span>|<span data-ttu-id="83622-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="83622-105">SQL Server</span></span>|  
|<span data-ttu-id="83622-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="83622-106">Event ID</span></span>|<span data-ttu-id="83622-107">1205</span><span class="sxs-lookup"><span data-stu-id="83622-107">1205</span></span>|  
|<span data-ttu-id="83622-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="83622-108">Event Source</span></span>|<span data-ttu-id="83622-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="83622-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="83622-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="83622-110">Component</span></span>|<span data-ttu-id="83622-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="83622-111">SQLEngine</span></span>|  
|<span data-ttu-id="83622-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="83622-112">Symbolic Name</span></span>|<span data-ttu-id="83622-113">LK_VICTIM</span><span class="sxs-lookup"><span data-stu-id="83622-113">LK_VICTIM</span></span>|  
|<span data-ttu-id="83622-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="83622-114">Message Text</span></span>|<span data-ttu-id="83622-115">Транзакция (с идентификатором процесса %d) вызвала взаимоблокировку ресурсов %.\*ls с другим процессом и была выбрана в качестве жертвы для ее разрешения.</span><span class="sxs-lookup"><span data-stu-id="83622-115">Transaction (Process ID %d) was deadlocked on %.\*ls resources with another process and has been chosen as the deadlock victim.</span></span> <span data-ttu-id="83622-116">Запустите транзакцию повторно.</span><span class="sxs-lookup"><span data-stu-id="83622-116">Rerun the transaction.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="83622-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="83622-117">Explanation</span></span>  
 <span data-ttu-id="83622-118">Доступ к ресурсам осуществляется в конфликтном порядке в отдельных транзакциях, из-за чего возникает взаимоблокировка.</span><span class="sxs-lookup"><span data-stu-id="83622-118">Resources are accessed in conflicting order on separate transactions, causing a deadlock.</span></span> <span data-ttu-id="83622-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="83622-119">For example:</span></span>  
  
-   <span data-ttu-id="83622-120">Транзакция1 обновляет строку **Таблица1.Строка1**, а транзакция2 в то же время обновляет строку **Таблица2.Строка2**.</span><span class="sxs-lookup"><span data-stu-id="83622-120">Transaction1 updates **Table1.Row1**, while Transaction2 updates **Table2.Row2**.</span></span>  
  
-   <span data-ttu-id="83622-121">Транзакция1 пытается произвести обновление строки **Таблица2.Строка2**, но происходит блокировка, так как транзакция2 еще не зафиксирована.</span><span class="sxs-lookup"><span data-stu-id="83622-121">Transaction1 tries to update **Table2.Row2** but is blocked because Transaction2 has not yet committed.</span></span>  
  
-   <span data-ttu-id="83622-122">Теперь транзакция2 пытается провести обновление строки **Таблица1.Строка1**, но происходит блокировка, так как транзакция1 еще не зафиксирована.</span><span class="sxs-lookup"><span data-stu-id="83622-122">Transaction2 now tries to update **Table1.Row1** but is blocked because Transaction1 has not committed.</span></span>  
  
-   <span data-ttu-id="83622-123">Взаимоблокировка происходит из-за того, что транзакция1 ожидает завершения транзакции2, а транзакция2 ожидает завершения транзакции1.</span><span class="sxs-lookup"><span data-stu-id="83622-123">A deadlock occurs because Transaction1 is waiting for Transaction2 to complete, but Transaction2 is waiting for Transaction1 to complete.</span></span>  
  
 <span data-ttu-id="83622-124">Система обнаруживает эту взаимоблокировку, выбирает одну из транзакций в качестве "жертвы" и выдает это сообщение, выполняя откат этой транзакции.</span><span class="sxs-lookup"><span data-stu-id="83622-124">The system will detect this deadlock and will choose one of the transactions involved as a 'victim' and will issue this message, rolling back the victim's transaction.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="83622-125">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="83622-125">User Action</span></span>  
 <span data-ttu-id="83622-126">Выполните транзакцию еще раз.</span><span class="sxs-lookup"><span data-stu-id="83622-126">Execute the transaction again.</span></span> <span data-ttu-id="83622-127">Во избежание взаимоблокировок можно изменить выполняемое приложение.</span><span class="sxs-lookup"><span data-stu-id="83622-127">You can also revise the application to avoid deadlocks.</span></span> <span data-ttu-id="83622-128">Выбранную «жертвой» транзакцию можно выполнить повторно, вероятность ее успешного выполнения высока и зависит от того, какие операции выполнялись одновременно.</span><span class="sxs-lookup"><span data-stu-id="83622-128">The transaction that was chosen as a victim can be retried and will likely succeed, depending on what operations are being executed simultaneously.</span></span>  
  
 <span data-ttu-id="83622-129">Для предотвращения взаимоблокировок можно сделать так, чтобы транзакции обращались к строкам в одном и том же порядке (**Table1**, затем **Table2**). При таком подходе могут возникнуть блокировки, но не взаимоблокировка.</span><span class="sxs-lookup"><span data-stu-id="83622-129">To prevent or avoid deadlocks from occurring, consider having all transactions access rows in the same order (**Table1**, then **Table2**); this way, although blocking might occur, a deadlock will not occur.</span></span>  
  
  
