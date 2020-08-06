---
title: MSSQLSERVER_3437 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3437 (Database Engine error)
ms.assetid: b38216e2-b650-43bd-97af-061d54f60031
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ed8f2050f6f1b38bc5f3fcb7a9700b80e52f2763
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667110"
---
# <a name="mssqlserver_3437"></a><span data-ttu-id="c46ed-102">MSSQLSERVER_3437</span><span class="sxs-lookup"><span data-stu-id="c46ed-102">MSSQLSERVER_3437</span></span>
    
## <a name="details"></a><span data-ttu-id="c46ed-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="c46ed-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c46ed-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="c46ed-104">Product Name</span></span>|<span data-ttu-id="c46ed-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c46ed-105">SQL Server</span></span>|  
|<span data-ttu-id="c46ed-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="c46ed-106">Event ID</span></span>|<span data-ttu-id="c46ed-107">3437</span><span class="sxs-lookup"><span data-stu-id="c46ed-107">3437</span></span>|  
|<span data-ttu-id="c46ed-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="c46ed-108">Event Source</span></span>|<span data-ttu-id="c46ed-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c46ed-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c46ed-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="c46ed-110">Component</span></span>|<span data-ttu-id="c46ed-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c46ed-111">SQLEngine</span></span>|  
|<span data-ttu-id="c46ed-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="c46ed-112">Symbolic Name</span></span>|<span data-ttu-id="c46ed-113">NODTC</span><span class="sxs-lookup"><span data-stu-id="c46ed-113">NODTC</span></span>|  
|<span data-ttu-id="c46ed-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="c46ed-114">Message Text</span></span>|<span data-ttu-id="c46ed-115">При восстановлении базы данных «%.\*ls» произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="c46ed-115">An error occurred while recovering database '%.\*ls'.</span></span> <span data-ttu-id="c46ed-116">Невозможно подключиться к координатору распределенных транзакций Майкрософт (MS DTC) для проверки состояния завершения транзакции %S_XID.</span><span class="sxs-lookup"><span data-stu-id="c46ed-116">Unable to connect to Microsoft Distributed Transaction Coordinator (MS DTC) to check the completion status of transaction %S_XID.</span></span> <span data-ttu-id="c46ed-117">Исправьте MS DTC и запустите восстановление еще раз.</span><span class="sxs-lookup"><span data-stu-id="c46ed-117">Fix MS DTC, and run recovery again.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c46ed-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="c46ed-118">Explanation</span></span>  
 <span data-ttu-id="c46ed-119">На момент закрытия базы данных одна или несколько распределенных транзакций, использующих координатор распределенных транзакций [!INCLUDE[msCoName](../../includes/msconame-md.md)] (MS DTC), не были завершены.</span><span class="sxs-lookup"><span data-stu-id="c46ed-119">One or more distributed transactions that were using [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) were incomplete when the database was shut down.</span></span> <span data-ttu-id="c46ed-120">Восстановление этой базы данных завершилось неуспешно, так как [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удалось подключиться к MS DTC для завершения или отката транзакций.</span><span class="sxs-lookup"><span data-stu-id="c46ed-120">Recovery of this database failed because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot connect to MS DTC to complete or roll back the transactions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c46ed-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="c46ed-121">User Action</span></span>  
 <span data-ttu-id="c46ed-122">Для восстановления этой базы данных сначала необходимо устранить неполадку с MS DTC.</span><span class="sxs-lookup"><span data-stu-id="c46ed-122">To recover this database, you must first resolve the problem with MS DTC.</span></span> <span data-ttu-id="c46ed-123">Для поиска проблемы, связанной с MS DTC, просмотрите журналы событий Windows.</span><span class="sxs-lookup"><span data-stu-id="c46ed-123">To investigate the problem with MS DTC, examine the Windows event logs.</span></span> <span data-ttu-id="c46ed-124">Если решить проблему с MS DTC и исправить базу данных невозможно, восстановите базу данных из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="c46ed-124">If you cannot resolve the problem with MS DTC and recover the database, restore a backup of database.</span></span>  
  
  
