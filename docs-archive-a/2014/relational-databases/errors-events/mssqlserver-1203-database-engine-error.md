---
title: MSSQLSERVER_1203 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1203 (Database Engine error)
ms.assetid: 33a35f00-98c8-46c6-b432-544b326b6117
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3cea816a60ccd1b90d849194766edebd2d64d0b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666657"
---
# <a name="mssqlserver_1203"></a><span data-ttu-id="b8ca1-102">MSSQLSERVER_1203</span><span class="sxs-lookup"><span data-stu-id="b8ca1-102">MSSQLSERVER_1203</span></span>
    
## <a name="details"></a><span data-ttu-id="b8ca1-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="b8ca1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8ca1-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="b8ca1-104">Product Name</span></span>|<span data-ttu-id="b8ca1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b8ca1-105">SQL Server</span></span>|  
|<span data-ttu-id="b8ca1-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="b8ca1-106">Event ID</span></span>|<span data-ttu-id="b8ca1-107">1203</span><span class="sxs-lookup"><span data-stu-id="b8ca1-107">1203</span></span>|  
|<span data-ttu-id="b8ca1-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="b8ca1-108">Event Source</span></span>|<span data-ttu-id="b8ca1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b8ca1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b8ca1-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="b8ca1-110">Component</span></span>|<span data-ttu-id="b8ca1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b8ca1-111">SQLEngine</span></span>|  
|<span data-ttu-id="b8ca1-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="b8ca1-112">Symbolic Name</span></span>|<span data-ttu-id="b8ca1-113">LK_NOT</span><span class="sxs-lookup"><span data-stu-id="b8ca1-113">LK_NOT</span></span>|  
|<span data-ttu-id="b8ca1-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="b8ca1-114">Message Text</span></span>|<span data-ttu-id="b8ca1-115">Идентификатор процесса %d попытался разблокировать ресурс, владельцем которого он не является: %.\*ls.</span><span class="sxs-lookup"><span data-stu-id="b8ca1-115">Process ID %d attempted to unlock a resource it does not own: %.\*ls.</span></span> <span data-ttu-id="b8ca1-116">Повторите транзакцию, поскольку эта ошибка может быть вызвана фактором времени.</span><span class="sxs-lookup"><span data-stu-id="b8ca1-116">Retry the transaction, because this error may be caused by a timing condition.</span></span> <span data-ttu-id="b8ca1-117">Если проблема остается, обратитесь к администратору баз данных.</span><span class="sxs-lookup"><span data-stu-id="b8ca1-117">If the problem persists, contact the database administrator.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b8ca1-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="b8ca1-118">Explanation</span></span>  
 <span data-ttu-id="b8ca1-119">Эта ошибка происходит, когда [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] вовлечен в некоторую деятельность, отличную от обычной завершающей очистки, и при попытке разблокировать определенную страницу обнаруживает, что она уже разблокирована.</span><span class="sxs-lookup"><span data-stu-id="b8ca1-119">This error occurs when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is engaged in some activity other than ordinary post-processing cleanup and it finds that a particular page that it is trying to unlock is already unlocked.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="b8ca1-120">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="b8ca1-120">Possible Causes</span></span>  
 <span data-ttu-id="b8ca1-121">Причина этой ошибки может быть связана с некоторыми структурными проблемами в этой базе данных.</span><span class="sxs-lookup"><span data-stu-id="b8ca1-121">The underlying cause of this error may be related to structural problems within the affected database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b8ca1-122">управляет блокировкой и освобождением страниц, чтобы обеспечить контроль параллелизма в многопользовательской среде.</span><span class="sxs-lookup"><span data-stu-id="b8ca1-122">manages the acquisition and release of pages to maintain concurrency control in the multiuser environment.</span></span> <span data-ttu-id="b8ca1-123">Этот механизм работает за счет использования различных структур внутренней блокировки, идентифицирующих страницу и тип установленной для нее блокировки.</span><span class="sxs-lookup"><span data-stu-id="b8ca1-123">This mechanism is maintained by using various internal lock structures that identify the page and the type of lock present.</span></span> <span data-ttu-id="b8ca1-124">Блокировки устанавливаются для обработки определенных страниц и сбрасываются после завершения обработки.</span><span class="sxs-lookup"><span data-stu-id="b8ca1-124">Locks are acquired for processing of affected pages and released when the processing is finished.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b8ca1-125">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="b8ca1-125">User Action</span></span>  
 <span data-ttu-id="b8ca1-126">Выполните инструкцию DBCC CHECKDB для базы данных, которой принадлежит объект.</span><span class="sxs-lookup"><span data-stu-id="b8ca1-126">Execute DBCC CHECKDB against the database in which the object belongs.</span></span> <span data-ttu-id="b8ca1-127">Если выполнение DBCC CHECKDB завершится без ошибок, попробуйте заново установить соединение и выполнить команду.</span><span class="sxs-lookup"><span data-stu-id="b8ca1-127">If DBCC CHECKDB reports no errors, try to reestablish the connection and execute the command.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b8ca1-128">Если выполнение DBCC CHECKDB с одним из предложений REPAIR не позволяет устранить неполадку с индексом, или если вы не уверены, как повлияет на данные выполнение инструкции DBCC CHECKDB с предложением REPAIR, обратитесь к основному поставщику услуг по технической поддержке.</span><span class="sxs-lookup"><span data-stu-id="b8ca1-128">If you are executing DBCC CHECKDB with one of the REPAIR clauses does not correct the index problem, or if you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider.</span></span>  
  
  
