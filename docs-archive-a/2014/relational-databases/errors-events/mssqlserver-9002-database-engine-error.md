---
title: MSSQLSERVER_9002 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9002 (Database Engine error)
ms.assetid: 2e50841f-2b99-45f4-aec5-aa4add70cbeb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b40fe70db8849d09f9296a06cbeed65a9c71e5a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666068"
---
# <a name="mssqlserver_9002"></a><span data-ttu-id="ded16-102">MSSQLSERVER_9002</span><span class="sxs-lookup"><span data-stu-id="ded16-102">MSSQLSERVER_9002</span></span>
    
## <a name="details"></a><span data-ttu-id="ded16-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="ded16-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ded16-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="ded16-104">Product Name</span></span>|<span data-ttu-id="ded16-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ded16-105">SQL Server</span></span>|  
|<span data-ttu-id="ded16-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ded16-106">Event ID</span></span>|<span data-ttu-id="ded16-107">9002</span><span class="sxs-lookup"><span data-stu-id="ded16-107">9002</span></span>|  
|<span data-ttu-id="ded16-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="ded16-108">Event Source</span></span>|<span data-ttu-id="ded16-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ded16-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ded16-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="ded16-110">Component</span></span>|<span data-ttu-id="ded16-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ded16-111">SQLEngine</span></span>|  
|<span data-ttu-id="ded16-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="ded16-112">Symbolic Name</span></span>|<span data-ttu-id="ded16-113">LOG_IS_FULL</span><span class="sxs-lookup"><span data-stu-id="ded16-113">LOG_IS_FULL</span></span>|  
|<span data-ttu-id="ded16-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="ded16-114">Message Text</span></span>|<span data-ttu-id="ded16-115">Журнал транзакций для базы данных «%.\*ls» заполнен.</span><span class="sxs-lookup"><span data-stu-id="ded16-115">The transaction log for database '%.\*ls' is full.</span></span> <span data-ttu-id="ded16-116">Чтобы выяснить, почему пространство журнала не может быть использовано повторно, см. столбец log_reuse_wait_desc в представлении каталога sys.databases.</span><span class="sxs-lookup"><span data-stu-id="ded16-116">To find out why space in the log cannot be reused, see the log_reuse_wait_desc column in sys.databases.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ded16-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="ded16-117">Explanation</span></span>  
 <span data-ttu-id="ded16-118">Недостаточно места в журнале базы данных.</span><span class="sxs-lookup"><span data-stu-id="ded16-118">The database log is out of space.</span></span> <span data-ttu-id="ded16-119">Столбец **log_reuse_wait_desc** в представлении каталога **sys.databases** показывает, почему пространство журнала не может использоваться повторно.</span><span class="sxs-lookup"><span data-stu-id="ded16-119">The **log_reuse_wait_desc** column in **sys.databases** describes why space in the log cannot be reused.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ded16-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="ded16-120">User Action</span></span>  
 <span data-ttu-id="ded16-121">Используя представление каталога **sys.databases**, определите, почему журнал полон, и исправьте неполадку.</span><span class="sxs-lookup"><span data-stu-id="ded16-121">Use **sys.databases** to determine why the log is full and then correct the condition.</span></span> <span data-ttu-id="ded16-122">Дополнительные сведения см. в разделе «Устранение неполадок в полном журнале транзакций (ошибка 9002)» электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ded16-122">For more information, see "Troubleshooting a Full Transaction Log (Error 9002)" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ded16-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="ded16-123">See Also</span></span>  
 <span data-ttu-id="ded16-124">[Устранение неполадок при переполнении журнала транзакций (ошибка SQL Server 9002)](../logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md) </span><span class="sxs-lookup"><span data-stu-id="ded16-124">[Troubleshoot a Full Transaction Log &#40;SQL Server Error 9002&#41;](../logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md) </span></span>  
 [<span data-ttu-id="ded16-125">sys.databases (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ded16-125">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
