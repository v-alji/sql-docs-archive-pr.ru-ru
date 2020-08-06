---
title: MSSQLSERVER_41301 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41301 (Database Engine error)
ms.assetid: c6127e1e-2846-4ee9-bc42-2d896ea9730e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d4fa78b334f32033f96df002aeaf039994b396cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665366"
---
# <a name="mssqlserver_41301"></a><span data-ttu-id="fb9a8-102">MSSQLSERVER_41301</span><span class="sxs-lookup"><span data-stu-id="fb9a8-102">MSSQLSERVER_41301</span></span>
    
## <a name="details"></a><span data-ttu-id="fb9a8-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="fb9a8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fb9a8-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="fb9a8-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="fb9a8-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="fb9a8-105">Event ID</span></span>|<span data-ttu-id="fb9a8-106">41301</span><span class="sxs-lookup"><span data-stu-id="fb9a8-106">41301</span></span>|  
|<span data-ttu-id="fb9a8-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="fb9a8-107">Event Source</span></span>|<span data-ttu-id="fb9a8-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fb9a8-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fb9a8-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="fb9a8-109">Component</span></span>|<span data-ttu-id="fb9a8-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fb9a8-110">SQLEngine</span></span>|  
|<span data-ttu-id="fb9a8-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="fb9a8-111">Symbolic Name</span></span>|<span data-ttu-id="fb9a8-112">COMMIT_DEPENDENCY_FAILURE</span><span class="sxs-lookup"><span data-stu-id="fb9a8-112">COMMIT_DEPENDENCY_FAILURE</span></span>|  
|<span data-ttu-id="fb9a8-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="fb9a8-113">Message Text</span></span>|<span data-ttu-id="fb9a8-114">Предыдущая транзакция, от которой зависит текущая транзакция, прервана, текущая транзакция не может быть зафиксирована.</span><span class="sxs-lookup"><span data-stu-id="fb9a8-114">A previous transaction that the current transaction took a dependency on has aborted, and the current transaction can no longer commit.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fb9a8-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="fb9a8-115">Explanation</span></span>  
 <span data-ttu-id="fb9a8-116">В ходе транзакции произошла ошибка зависимости, поэтому транзакция завершается.</span><span class="sxs-lookup"><span data-stu-id="fb9a8-116">The transaction encountered a dependency failure, and is now doomed.</span></span>  
  
 <span data-ttu-id="fb9a8-117">Эта ошибка также может быть вызвана слишком большим числом зависимых транзакций.</span><span class="sxs-lookup"><span data-stu-id="fb9a8-117">This error can also be caused by too many dependent transactions.</span></span> <span data-ttu-id="fb9a8-118">Любые транзакции записи могут иметь только ограниченное число зависимых транзакций.</span><span class="sxs-lookup"><span data-stu-id="fb9a8-118">Any write transaction can have a limited number of dependent transactions.</span></span> <span data-ttu-id="fb9a8-119">Например, эта ошибка может возникнуть в случае, если слишком большое число транзакций чтения пытаются установить зависимость от транзакции обновления.</span><span class="sxs-lookup"><span data-stu-id="fb9a8-119">For example, this error can occur if too many read transactions try to take a dependency on the update transaction.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fb9a8-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="fb9a8-120">User Action</span></span>  
 <span data-ttu-id="fb9a8-121">Не выполняйте никаких действий в ходе транзакции.</span><span class="sxs-lookup"><span data-stu-id="fb9a8-121">Don't do any work on the transaction.</span></span> <span data-ttu-id="fb9a8-122">Вызовите ROLLBACK TRAN для отката транзакции.</span><span class="sxs-lookup"><span data-stu-id="fb9a8-122">Call ROLLBACK TRAN to roll back the transaction.</span></span> <span data-ttu-id="fb9a8-123">Дополнительные сведения см. в разделе [In-Memory OLTP (оптимизация в памяти)](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="fb9a8-123">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb9a8-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="fb9a8-124">See Also</span></span>  
 [<span data-ttu-id="fb9a8-125">Включение и отключение групп доступности AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fb9a8-125">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../../database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server.md)  
  
  
