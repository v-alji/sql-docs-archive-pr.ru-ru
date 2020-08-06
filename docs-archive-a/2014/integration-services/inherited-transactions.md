---
title: Унаследованные транзакции | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Integration Services], inherited
- child packages
- inherited transactions [Integration Services]
ms.assetid: 90db5564-d41e-4cfe-8c9e-4e68d41eff1c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ecb480420fe9f2492c29fad37ee3cc6e6501e3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664411"
---
# <a name="inherited-transactions"></a><span data-ttu-id="60764-102">Наследуемые транзакции</span><span class="sxs-lookup"><span data-stu-id="60764-102">Inherited Transactions</span></span>
  <span data-ttu-id="60764-103">Пакет может запускать другой пакет с помощью задачи «Выполнение пакета».</span><span class="sxs-lookup"><span data-stu-id="60764-103">A package can run another package by using the Execute Package task.</span></span> <span data-ttu-id="60764-104">Дочерний пакет, то есть пакет, запускаемый задачей «Выполнение пакета», может создавать собственную транзакцию пакетов или наследовать родительскую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="60764-104">The child package, which is the package run by the Execute Package task, may create its own package transaction, or it may inherit the parent package transaction.</span></span>  
  
 <span data-ttu-id="60764-105">Дочерний пакет наследует родительскую транзакцию пакетов, если выполняются оба приведенных ниже условия:</span><span class="sxs-lookup"><span data-stu-id="60764-105">A child package inherits the parent package transaction if both of the following are true:</span></span>  
  
-   <span data-ttu-id="60764-106">Пакет вызывается задачей «Выполнение пакета».</span><span class="sxs-lookup"><span data-stu-id="60764-106">The package is invoked by an Execute Package task.</span></span>  
  
-   <span data-ttu-id="60764-107">Задача «Выполнение пакета», вызвавшая пакет, также присоединяется к родительской транзакции пакета.</span><span class="sxs-lookup"><span data-stu-id="60764-107">The Execute Package task that invoked the package also joined the parent package transaction.</span></span>  
  
 <span data-ttu-id="60764-108">Контейнеры и задачи в дочернем пакете не могут присоединяться к родительской транзакции пакетов, если только к ней не присоединяется сам дочерний пакет.</span><span class="sxs-lookup"><span data-stu-id="60764-108">Containers and tasks in the child package cannot join the parent package transaction unless the child package itself joins the transaction.</span></span>  
  
## <a name="illustration-of-package-transactions"></a><span data-ttu-id="60764-109">Иллюстрация к пакетным транзакциям</span><span class="sxs-lookup"><span data-stu-id="60764-109">Illustration of Package Transactions</span></span>  
 <span data-ttu-id="60764-110">Все три пакета, показанные на приведенной ниже диаграмме, используют транзакции.</span><span class="sxs-lookup"><span data-stu-id="60764-110">In the following diagram, there are three packages that all use transactions.</span></span> <span data-ttu-id="60764-111">Каждый пакет содержит несколько задач.</span><span class="sxs-lookup"><span data-stu-id="60764-111">Each package contains multiple tasks.</span></span> <span data-ttu-id="60764-112">Чтобы выделить поведение транзакций, показаны только задачи «Выполнение пакета».</span><span class="sxs-lookup"><span data-stu-id="60764-112">To emphasize the behavior of the transactions, only the Execute Package tasks are shown.</span></span> <span data-ttu-id="60764-113">Пакет A запускает пакеты B и C. В свою очередь пакет B запускает пакеты D и E, а пакет C запускает пакет F.</span><span class="sxs-lookup"><span data-stu-id="60764-113">Package A runs packages B and C. In turn, package B runs packages D and E, and package C runs package F.</span></span>  
  
 <span data-ttu-id="60764-114">Пакеты и задачи имеют следующие атрибуты транзакции:</span><span class="sxs-lookup"><span data-stu-id="60764-114">Packages and tasks have the following transaction attributes:</span></span>  
  
-   <span data-ttu-id="60764-115">Параметру**TransactionOption** присвоено значение **Required** для пакетов A и C</span><span class="sxs-lookup"><span data-stu-id="60764-115">**TransactionOption** is set to **Required** on packages A and C</span></span>  
  
-   <span data-ttu-id="60764-116">Параметру**TransactionOption** присвоено значение **Supported** в пакетах B и D, а также в задачах выполнения пакетов B, D и F.</span><span class="sxs-lookup"><span data-stu-id="60764-116">**TransactionOption** is set to **Supported** on packages B and D, and on the tasks Execute Package B, Execute Package D, and Execute Package F.</span></span>  
  
-   <span data-ttu-id="60764-117">Параметру**TransactionOption** присвоено значение **NotSupported** в пакете E, а также в задачах выполнения пакетов C и E.</span><span class="sxs-lookup"><span data-stu-id="60764-117">**TransactionOption** is set to **NotSupported** on package E, and on the tasks Execute Package C and Execute Package E.</span></span>  
  
 <span data-ttu-id="60764-118">![Поток унаследованных транзакций](media/mw-dts-executepack.gif "Поток унаследованных транзакций")</span><span class="sxs-lookup"><span data-stu-id="60764-118">![Flow of inherited transactions](media/mw-dts-executepack.gif "Flow of inherited transactions")</span></span>  
  
 <span data-ttu-id="60764-119">Наследовать транзакции от родительских пакетов могут только пакеты B, D и F.</span><span class="sxs-lookup"><span data-stu-id="60764-119">Only packages B, D, and F can inherit transactions from their parent packages.</span></span>  
  
 <span data-ttu-id="60764-120">Пакеты B и D наследуют транзакцию, запущенную пакетом A.</span><span class="sxs-lookup"><span data-stu-id="60764-120">Packages B and D inherit the transaction that was started by package A.</span></span>  
  
 <span data-ttu-id="60764-121">Пакет F наследует транзакцию, запущенную пакетом C.</span><span class="sxs-lookup"><span data-stu-id="60764-121">Package F inherits the transaction that was started by package C.</span></span>  
  
 <span data-ttu-id="60764-122">Пакеты A и C управляют своими собственными транзакциями.</span><span class="sxs-lookup"><span data-stu-id="60764-122">Packages A and C control their own transactions.</span></span>  
  
 <span data-ttu-id="60764-123">Пакет E не использует транзакции.</span><span class="sxs-lookup"><span data-stu-id="60764-123">Package E does not use transactions.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="60764-124">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="60764-124">Related Tasks</span></span>  
 [<span data-ttu-id="60764-125">Настройка пакета для использования транзакций</span><span class="sxs-lookup"><span data-stu-id="60764-125">Configure a Package to Use Transactions</span></span>](../relational-databases/native-client-ole-db-transactions/transactions.md)  
  
  
