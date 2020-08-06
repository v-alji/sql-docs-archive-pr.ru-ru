---
title: MSSQL_ENG014121 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014121 error
ms.assetid: c8595854-cce1-4566-ad64-d565555caded
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 04d4cbdd2197745d2d795814d88c4f7bc28eb90e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654187"
---
# <a name="mssql_eng014121"></a><span data-ttu-id="a2a24-102">MSSQL_ENG014121</span><span class="sxs-lookup"><span data-stu-id="a2a24-102">MSSQL_ENG014121</span></span>
    
## <a name="message-details"></a><span data-ttu-id="a2a24-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="a2a24-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a2a24-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="a2a24-104">Product Name</span></span>|<span data-ttu-id="a2a24-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a2a24-105">SQL Server</span></span>|  
|<span data-ttu-id="a2a24-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a2a24-106">Event ID</span></span>|<span data-ttu-id="a2a24-107">14121</span><span class="sxs-lookup"><span data-stu-id="a2a24-107">14121</span></span>|  
|<span data-ttu-id="a2a24-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="a2a24-108">Event Source</span></span>|<span data-ttu-id="a2a24-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a2a24-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a2a24-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="a2a24-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="a2a24-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="a2a24-111">Symbolic Name</span></span>||  
|<span data-ttu-id="a2a24-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a2a24-112">Message Text</span></span>|<span data-ttu-id="a2a24-113">Не удалось удалить распространитель "%s".</span><span class="sxs-lookup"><span data-stu-id="a2a24-113">Could not drop the Distributor '%s'.</span></span> <span data-ttu-id="a2a24-114">С этим распространителем связаны базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="a2a24-114">This Distributor has associated distribution databases.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a2a24-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="a2a24-115">Explanation</span></span>  
 <span data-ttu-id="a2a24-116">Экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , настроенный как распространитель, не может быть удален из роли распространителя, т. к. имеются базы данных распространителя, связанные с этим экземпляром.</span><span class="sxs-lookup"><span data-stu-id="a2a24-116">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is configured as a Distributor cannot be removed from the role of Distributor because there are distribution databases associated with the instance.</span></span> <span data-ttu-id="a2a24-117">Эта ошибка возникает при попытке удалить базу данных распространителя, связанную с одним или несколькими издателями.</span><span class="sxs-lookup"><span data-stu-id="a2a24-117">This error occurs if you attempt to drop a distribution database that is associated with one or more Publishers.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a2a24-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a2a24-118">User Action</span></span>  
 <span data-ttu-id="a2a24-119">Чтобы найти имена издателей и баз данных, связанных с конкретным распространителем, выполните хранимую процедуру [sp_helpdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpdistpublisher-transact-sql) из любой базы данных в этом распространителе.</span><span class="sxs-lookup"><span data-stu-id="a2a24-119">To find the names of any Publishers and distribution databases associated with this Distributor, execute [sp_helpdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpdistpublisher-transact-sql) from any database on the Distributor.</span></span>  
  
 <span data-ttu-id="a2a24-120">Выполните хранимую процедуру [sp_dropdistributiondb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) для всех баз данных, связанных с этим распространителем.</span><span class="sxs-lookup"><span data-stu-id="a2a24-120">Execute [sp_dropdistributiondb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) for any distribution databases associated with this Distributor.</span></span> <span data-ttu-id="a2a24-121">После того, как будут удалены все связи баз данных распространителя, распространение можно будет отключить.</span><span class="sxs-lookup"><span data-stu-id="a2a24-121">After all distribution database associations are removed, you can disable distribution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2a24-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="a2a24-122">See Also</span></span>  
 <span data-ttu-id="a2a24-123">[Справочник по ошибкам и событиям (репликация)](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="a2a24-123">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="a2a24-124">Настройка распространения</span><span class="sxs-lookup"><span data-stu-id="a2a24-124">Configure Distribution</span></span>](configure-distribution.md)  
  
  
