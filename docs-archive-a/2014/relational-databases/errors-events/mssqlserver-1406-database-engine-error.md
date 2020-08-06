---
title: MSSQLSERVER_1406 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1406 (Database Engine error)
ms.assetid: 915f97de-9b74-41f8-8bd5-b2d061416718
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: adaa0084b875f720c477189e0e8e085af124f4cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734114"
---
# <a name="mssqlserver_1406"></a><span data-ttu-id="113e3-102">MSSQLSERVER_1406</span><span class="sxs-lookup"><span data-stu-id="113e3-102">MSSQLSERVER_1406</span></span>
    
## <a name="details"></a><span data-ttu-id="113e3-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="113e3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="113e3-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="113e3-104">Product Name</span></span>|<span data-ttu-id="113e3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="113e3-105">SQL Server</span></span>|  
|<span data-ttu-id="113e3-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="113e3-106">Event ID</span></span>|<span data-ttu-id="113e3-107">1406</span><span class="sxs-lookup"><span data-stu-id="113e3-107">1406</span></span>|  
|<span data-ttu-id="113e3-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="113e3-108">Event Source</span></span>|<span data-ttu-id="113e3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="113e3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="113e3-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="113e3-110">Component</span></span>|<span data-ttu-id="113e3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="113e3-111">SQLEngine</span></span>|  
|<span data-ttu-id="113e3-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="113e3-112">Symbolic Name</span></span>|<span data-ttu-id="113e3-113">DBM_BADSTATEFORFORCESERVICE</span><span class="sxs-lookup"><span data-stu-id="113e3-113">DBM_BADSTATEFORFORCESERVICE</span></span>|  
|<span data-ttu-id="113e3-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="113e3-114">Message Text</span></span>|<span data-ttu-id="113e3-115">Не удалось безопасно принудительно запустить службу.</span><span class="sxs-lookup"><span data-stu-id="113e3-115">Unable to force service safely.</span></span> <span data-ttu-id="113e3-116">Отключите зеркальное отображение и восстановите базу данных «%.\*ls», чтобы получить доступ.</span><span class="sxs-lookup"><span data-stu-id="113e3-116">Remove database mirroring and recover database "%.\*ls" to gain access.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="113e3-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="113e3-117">Explanation</span></span>  
 <span data-ttu-id="113e3-118">Компоненту [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] не удается принудительно запустить службу, так как состояние зеркального отображения не гарантирует, что процесс принудительного запуска службы будет выполнен правильно.</span><span class="sxs-lookup"><span data-stu-id="113e3-118">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] cannot force service because the mirroring state cannot guarantee that the force service process would work correctly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="113e3-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="113e3-119">User Action</span></span>  
 <span data-ttu-id="113e3-120">Отключите зеркальное отображение базы данных.</span><span class="sxs-lookup"><span data-stu-id="113e3-120">Remove database mirroring.</span></span> <span data-ttu-id="113e3-121">После этого можно восстановить зеркальную базу данных, чтобы получить к ней доступ.</span><span class="sxs-lookup"><span data-stu-id="113e3-121">You can then recover the mirror database to gain access to it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="113e3-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="113e3-122">See Also</span></span>  
 <span data-ttu-id="113e3-123">[Принудительный запуск службы в сеансе зеркального отображения базы данных (Transact-SQL)](../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="113e3-123">[Force Service in a Database Mirroring Session &#40;Transact-SQL&#41;](../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md) </span></span>  
 [<span data-ttu-id="113e3-124">Удаление зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="113e3-124">Removing Database Mirroring &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/database-mirroring-sql-server.md)  
  
  
