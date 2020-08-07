---
title: MSSQLSERVER_21871 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21871 (Database Engine error)
ms.assetid: d3215378-9282-444f-a18b-00b96fd0133d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f26211da21829a0a898dfb36ff9fefd453c7ad44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731642"
---
# <a name="mssqlserver_21871"></a><span data-ttu-id="5eaf1-102">MSSQLSERVER_21871</span><span class="sxs-lookup"><span data-stu-id="5eaf1-102">MSSQLSERVER_21871</span></span>
    
## <a name="details"></a><span data-ttu-id="5eaf1-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="5eaf1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5eaf1-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="5eaf1-104">Product Name</span></span>|<span data-ttu-id="5eaf1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5eaf1-105">SQL Server</span></span>|  
|<span data-ttu-id="5eaf1-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="5eaf1-106">Event ID</span></span>|<span data-ttu-id="5eaf1-107">21871</span><span class="sxs-lookup"><span data-stu-id="5eaf1-107">21871</span></span>|  
|<span data-ttu-id="5eaf1-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="5eaf1-108">Event Source</span></span>|<span data-ttu-id="5eaf1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5eaf1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5eaf1-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="5eaf1-110">Component</span></span>|<span data-ttu-id="5eaf1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5eaf1-111">SQLEngine</span></span>|  
|<span data-ttu-id="5eaf1-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="5eaf1-112">Symbolic Name</span></span>|<span data-ttu-id="5eaf1-113">SQLErrorNum21871</span><span class="sxs-lookup"><span data-stu-id="5eaf1-113">SQLErrorNum21871</span></span>|  
|<span data-ttu-id="5eaf1-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="5eaf1-114">Message Text</span></span>|<span data-ttu-id="5eaf1-115">Издатель %s базы данных %s не перенаправлен.</span><span class="sxs-lookup"><span data-stu-id="5eaf1-115">Publisher %s of database %s has not been redirected.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5eaf1-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="5eaf1-116">Explanation</span></span>  
 <span data-ttu-id="5eaf1-117">`sp_validate_replica_hosts_as_publishers` проверяет таблицу MSredirected_publishers в базе данных распространителя, пытаясь найти запись идентифицированного издателя и базы данных издателя.</span><span class="sxs-lookup"><span data-stu-id="5eaf1-117">`sp_validate_replica_hosts_as_publishers` checks the table MSredirected_publishers in the distribution database for an entry for the identified publisher and publisher database.</span></span>  <span data-ttu-id="5eaf1-118">`sp_validate_replica_hosts_as_publishers` возвращает ошибку 21871, если запись не будет найдена.</span><span class="sxs-lookup"><span data-stu-id="5eaf1-118">`sp_validate_replica_hosts_as_publishers` returns error 21871 when no entry is found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5eaf1-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="5eaf1-119">User Action</span></span>  
 <span data-ttu-id="5eaf1-120">`sp_validate_replica_hosts_as_publishers` относится только к перенаправляемым издателям.</span><span class="sxs-lookup"><span data-stu-id="5eaf1-120">`sp_validate_replica_hosts_as_publishers` is only relevant for redirected publishers.</span></span> <span data-ttu-id="5eaf1-121">Если база данных издателя является членом группы доступности, воспользуйтесь хранимой процедурой `sp_redirect_publisher`, чтобы связать издателя и базу данных издателя с именем прослушивателя группы доступности соответствующей группы доступности.</span><span class="sxs-lookup"><span data-stu-id="5eaf1-121">If the publisher database is a member of an availability group, use the stored procedure `sp_redirect_publisher` to associate the publisher and publisher database with the Availability Group Listener Name of the availability group.</span></span>  
  
  
