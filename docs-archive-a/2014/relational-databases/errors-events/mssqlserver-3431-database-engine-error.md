---
title: MSSQLSERVER_3431 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3431 (Database Engine error)
ms.assetid: 9541217f-e5c6-4a12-a19a-006058f1d3f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9b62047a25d71ca05dc3ab03651e5672353bc0a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667115"
---
# <a name="mssqlserver_3431"></a><span data-ttu-id="7b620-102">MSSQLSERVER_3431</span><span class="sxs-lookup"><span data-stu-id="7b620-102">MSSQLSERVER_3431</span></span>
    
## <a name="details"></a><span data-ttu-id="7b620-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="7b620-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7b620-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="7b620-104">Product Name</span></span>|<span data-ttu-id="7b620-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7b620-105">SQL Server</span></span>|  
|<span data-ttu-id="7b620-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="7b620-106">Event ID</span></span>|<span data-ttu-id="7b620-107">3431</span><span class="sxs-lookup"><span data-stu-id="7b620-107">3431</span></span>|  
|<span data-ttu-id="7b620-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="7b620-108">Event Source</span></span>|<span data-ttu-id="7b620-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7b620-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7b620-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="7b620-110">Component</span></span>|<span data-ttu-id="7b620-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7b620-111">SQLEngine</span></span>|  
|<span data-ttu-id="7b620-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="7b620-112">Symbolic Name</span></span>|<span data-ttu-id="7b620-113">UNRESOLVED_XACT</span><span class="sxs-lookup"><span data-stu-id="7b620-113">UNRESOLVED_XACT</span></span>|  
|<span data-ttu-id="7b620-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="7b620-114">Message Text</span></span>|<span data-ttu-id="7b620-115">Не удалось восстановить базу данных «%.\*ls» (идентификатор базы данных — %d) из-за неразрешенных результатов транзакций.</span><span class="sxs-lookup"><span data-stu-id="7b620-115">Could not recover database '%.\*ls' (database ID %d) because of unresolved transaction outcomes.</span></span> <span data-ttu-id="7b620-116">Были подготовлены транзакции координатора распределенных транзакций Майкрософт (MS DTC), но координатору MS DTC не удалось выполнить разрешение.</span><span class="sxs-lookup"><span data-stu-id="7b620-116">Microsoft Distributed Transaction Coordinator (MS DTC) transactions were prepared, but MS DTC was unable to determine the resolution.</span></span> <span data-ttu-id="7b620-117">Для разрешения транзакций исправьте MS DTC, выполните восстановление из полной резервной копии или исправьте базу данных.</span><span class="sxs-lookup"><span data-stu-id="7b620-117">To resolve, either fix MS DTC, restore from a full backup, or repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7b620-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="7b620-118">Explanation</span></span>  
 <span data-ttu-id="7b620-119">На момент закрытия базы данных одна или несколько распределенных транзакций, использующих координатор распределенных транзакций [!INCLUDE[msCoName](../../includes/msconame-md.md)] (MS DTC), не были завершены.</span><span class="sxs-lookup"><span data-stu-id="7b620-119">One or more distributed transactions that were using [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) were incomplete when the database was shut down.</span></span> <span data-ttu-id="7b620-120">Восстановление этой базы данных завершилось неуспешно, так как [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удалось завершить или произвести откат транзакции, не имея дополнительной информации от MS DTC.</span><span class="sxs-lookup"><span data-stu-id="7b620-120">Recovery of this database failed because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot complete the transactions or roll back the transactions without more information from MS DTC.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7b620-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="7b620-121">User Action</span></span>  
 <span data-ttu-id="7b620-122">Для восстановления этой базы данных сначала необходимо устранить неполадку с MS DTC.</span><span class="sxs-lookup"><span data-stu-id="7b620-122">To recover this database, you must first resolve the problem with MS DTC.</span></span> <span data-ttu-id="7b620-123">Для поиска проблемы, связанной с MS DTC, просмотрите журналы событий Windows.</span><span class="sxs-lookup"><span data-stu-id="7b620-123">To investigate the problem with MS DTC, examine the Windows event logs.</span></span> <span data-ttu-id="7b620-124">Если решить проблему с MS DTC и исправить базу данных невозможно, восстановите базу данных из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="7b620-124">If you cannot resolve the problem with MS DTC and recover the database, restore a backup of database.</span></span>  
  
  
