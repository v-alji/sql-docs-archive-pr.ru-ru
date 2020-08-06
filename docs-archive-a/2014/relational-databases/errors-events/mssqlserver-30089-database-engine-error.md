---
title: MSSQLSERVER_30089 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9992 (Database Engine error)
ms.assetid: 188e5bde-6865-4740-a2b2-582be8f55c77
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d0b9c71ea620174f993ae87befed8a21bb3d0bfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664250"
---
# <a name="mssqlserver_30089"></a><span data-ttu-id="6b1ce-102">MSSQLSERVER_30089</span><span class="sxs-lookup"><span data-stu-id="6b1ce-102">MSSQLSERVER_30089</span></span>
    
## <a name="details"></a><span data-ttu-id="6b1ce-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="6b1ce-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6b1ce-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="6b1ce-104">Product Name</span></span>|<span data-ttu-id="6b1ce-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6b1ce-105">SQL Server</span></span>|  
|<span data-ttu-id="6b1ce-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6b1ce-106">Event ID</span></span>|<span data-ttu-id="6b1ce-107">30089</span><span class="sxs-lookup"><span data-stu-id="6b1ce-107">30089</span></span>|  
|<span data-ttu-id="6b1ce-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="6b1ce-108">Event Source</span></span>|<span data-ttu-id="6b1ce-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6b1ce-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6b1ce-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="6b1ce-110">Component</span></span>|<span data-ttu-id="6b1ce-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6b1ce-111">SQLEngine</span></span>|  
|<span data-ttu-id="6b1ce-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="6b1ce-112">Symbolic Name</span></span>|<span data-ttu-id="6b1ce-113">IFTS_FDHOST_TERMINATEDABNORMAL</span><span class="sxs-lookup"><span data-stu-id="6b1ce-113">IFTS_FDHOST_TERMINATEDABNORMAL</span></span>|  
|<span data-ttu-id="6b1ce-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="6b1ce-114">Message Text</span></span>|<span data-ttu-id="6b1ce-115">Процесс узла управляющей программы полнотекстовой фильтрации (FDHost) завершился аварийно.</span><span class="sxs-lookup"><span data-stu-id="6b1ce-115">The fulltext filter daemon host (FDHost) process has stopped abnormally.</span></span> <span data-ttu-id="6b1ce-116">Причиной этого может быть неустранимая ошибка при полнотекстовом индексировании или обработке запроса, вызванная неверной настройкой или ошибкой в работе лингвистического компонента — средства разбиения по словам, парадигматического модуля или фильтра.</span><span class="sxs-lookup"><span data-stu-id="6b1ce-116">This can occur if an incorrectly configured or malfunctioning linguistic component, such as a wordbreaker, stemmer or filter has caused an irrecoverable error during full-text indexing or query processing.</span></span> <span data-ttu-id="6b1ce-117">Процесс будет перезапущен автоматически.</span><span class="sxs-lookup"><span data-stu-id="6b1ce-117">The process will be restarted automatically.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6b1ce-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="6b1ce-118">Explanation</span></span>  
 <span data-ttu-id="6b1ce-119">На узле управляющей программы полнотекстовой фильтрации обнаружена какая-то проблема, которая привела к принудительному аварийному останову.</span><span class="sxs-lookup"><span data-stu-id="6b1ce-119">The full-text filter daemon host has encountered some problem that has forced it to stop abnormally.</span></span> <span data-ttu-id="6b1ce-120">Причиной проблемы может оказаться неправильно отформатированный документ, ошибка в фильтре или разделителе слов, а также нарушение в работе управляющей программы фильтрации.</span><span class="sxs-lookup"><span data-stu-id="6b1ce-120">The cause of the problem could be a badly formatted document, a bug in the filter or word-breaker, or a problem in filter daemon.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6b1ce-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="6b1ce-121">User Action</span></span>  
 <span data-ttu-id="6b1ce-122">Как правило, работа управляющей программы после подобной ошибки восстанавливается.</span><span class="sxs-lookup"><span data-stu-id="6b1ce-122">Typically, the daemon will recover from the error.</span></span> <span data-ttu-id="6b1ce-123">Если же в процессе выполнения управляющей программы снова и снова происходит неуспешное завершение, необходимо устранение неполадок.</span><span class="sxs-lookup"><span data-stu-id="6b1ce-123">If it is consistently failing, troubleshooting is necessary.</span></span> <span data-ttu-id="6b1ce-124">Для выявления причин проблемы попробуйте выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6b1ce-124">Try the following to isolate the issue:</span></span>  
  
1.  <span data-ttu-id="6b1ce-125">Если недавно установлен новый лингвистический компонент, удалите его из системы.</span><span class="sxs-lookup"><span data-stu-id="6b1ce-125">If a new linguistic component has been installed recently, remove it from the system.</span></span>  
  
2.  <span data-ttu-id="6b1ce-126">Просмотрите журнал сканирования, чтобы выявить какой-либо из новых документов, для которого не удалось провести полнотекстовую индексацию, и удалите его.</span><span class="sxs-lookup"><span data-stu-id="6b1ce-126">Look at the crawl log to identify any new document that failed to be full-text indexed, and remove it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b1ce-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="6b1ce-127">See Also</span></span>  
 <span data-ttu-id="6b1ce-128">[sp_help_fulltext_system_components &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6b1ce-128">[sp_help_fulltext_system_components &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span></span>  
 <span data-ttu-id="6b1ce-129">[Настройка средств разбиения по словам и парадигматические модули для поиска и управление ими](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span><span class="sxs-lookup"><span data-stu-id="6b1ce-129">[Configure and Manage Word Breakers and Stemmers for Search](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span></span>  
 [<span data-ttu-id="6b1ce-130">Настройка и управление фильтрами для поиска</span><span class="sxs-lookup"><span data-stu-id="6b1ce-130">Configure and Manage Filters for Search</span></span>](../search/configure-and-manage-filters-for-search.md)  
  
  
