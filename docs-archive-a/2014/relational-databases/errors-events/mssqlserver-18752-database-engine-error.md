---
title: MSSQLSERVER_18752 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18752 (Database Engine error)
ms.assetid: 234c58d8-7a1e-4b07-a64b-32a311527980
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a463e4019875f4a233ae2920f32bc2252376a41c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658791"
---
# <a name="mssqlserver_18752"></a><span data-ttu-id="98744-102">MSSQLSERVER_18752</span><span class="sxs-lookup"><span data-stu-id="98744-102">MSSQLSERVER_18752</span></span>
    
## <a name="details"></a><span data-ttu-id="98744-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="98744-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98744-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="98744-104">Product Name</span></span>|<span data-ttu-id="98744-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="98744-105">SQL Server</span></span>|  
|<span data-ttu-id="98744-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="98744-106">Event ID</span></span>|<span data-ttu-id="98744-107">18752</span><span class="sxs-lookup"><span data-stu-id="98744-107">18752</span></span>|  
|<span data-ttu-id="98744-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="98744-108">Event Source</span></span>|<span data-ttu-id="98744-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="98744-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="98744-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="98744-110">Component</span></span>|<span data-ttu-id="98744-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="98744-111">SQLEngine</span></span>|  
|<span data-ttu-id="98744-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="98744-112">Symbolic Name</span></span>|<span data-ttu-id="98744-113">REPL_INUSE</span><span class="sxs-lookup"><span data-stu-id="98744-113">REPL_INUSE</span></span>|  
|<span data-ttu-id="98744-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="98744-114">Message Text</span></span>|<span data-ttu-id="98744-115">К базе данных одновременно может быть подключен лишь один агент чтения журнала или процедура, относящаяся к журналу (sp_repldone, sp_replcmds и sp_replshowcmds).</span><span class="sxs-lookup"><span data-stu-id="98744-115">Only one Log Reader Agent or log-related procedure (sp_repldone, sp_replcmds, and sp_replshowcmds) can connect to a database at a time.</span></span> <span data-ttu-id="98744-116">Если выполняется процедура, относящаяся к журналу, удалите подключение, по которому выполнялась процедура, или выполните для этого подключения процедуру sp_replflush, прежде чем запустить агент чтения журнала или выполнить другую процедуру, относящуюся к журналу.</span><span class="sxs-lookup"><span data-stu-id="98744-116">If you executed a log-related procedure, drop the connection over which the procedure was executed or execute sp_replflush over that connection before starting the Log Reader Agent or executing another log-related procedure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="98744-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="98744-117">Explanation</span></span>  
 <span data-ttu-id="98744-118">К базе данных одновременно может быть подключен лишь один агент чтения журнала или одна процедура, относящаяся к журналу.</span><span class="sxs-lookup"><span data-stu-id="98744-118">Only one Log Reader agent or log-related procedure can connect to a database at a time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="98744-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="98744-119">User Action</span></span>  
 <span data-ttu-id="98744-120">Убедитесь, что в той же базе данных публикаций не запущен еще один агент чтения журнала и все активные соединения после запуска процедуры sp_replcmds или sp_repltrans, или sp_repldone либо запускают процедуру sp_replflush, либо разрываются.</span><span class="sxs-lookup"><span data-stu-id="98744-120">Make sure no other logreader is running for the same publishing database, and no other active connection had previously run sp_replcmds/sp_repltrans/sp_repldone without running sp_replflush afterwards or disconnecting.</span></span>  
  
  
