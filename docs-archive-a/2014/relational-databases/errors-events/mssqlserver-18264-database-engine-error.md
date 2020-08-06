---
title: MSSQLSERVER_18264 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18264 (Database Engine error)
ms.assetid: 3050fc56-2be5-43cf-916b-50a3ac5f89aa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3edfeb82601e254c02df87cc4a978b9ab5e653e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665363"
---
# <a name="mssqlserver_18264"></a><span data-ttu-id="11d3e-102">MSSQLSERVER_18264</span><span class="sxs-lookup"><span data-stu-id="11d3e-102">MSSQLSERVER_18264</span></span>
    
## <a name="details"></a><span data-ttu-id="11d3e-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="11d3e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="11d3e-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="11d3e-104">Product Name</span></span>|<span data-ttu-id="11d3e-105">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="11d3e-105">Microsoft SQL Server</span></span>|  
|<span data-ttu-id="11d3e-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="11d3e-106">Event ID</span></span>|<span data-ttu-id="11d3e-107">18264</span><span class="sxs-lookup"><span data-stu-id="11d3e-107">18264</span></span>|  
|<span data-ttu-id="11d3e-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="11d3e-108">Event Source</span></span>|<span data-ttu-id="11d3e-109">MSSQLENGINE</span><span class="sxs-lookup"><span data-stu-id="11d3e-109">MSSQLENGINE</span></span>|  
|<span data-ttu-id="11d3e-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="11d3e-110">Component</span></span>|<span data-ttu-id="11d3e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="11d3e-111">SQLEngine</span></span>|  
|<span data-ttu-id="11d3e-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="11d3e-112">Symbolic Name</span></span>|<span data-ttu-id="11d3e-113">STRMIO_DBDUMP</span><span class="sxs-lookup"><span data-stu-id="11d3e-113">STRMIO_DBDUMP</span></span>|  
|<span data-ttu-id="11d3e-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="11d3e-114">Message Text</span></span>|<span data-ttu-id="11d3e-115">Выполнено резервное копирование базы данных.</span><span class="sxs-lookup"><span data-stu-id="11d3e-115">Database backed up.</span></span> <span data-ttu-id="11d3e-116">База данных: %s, дата (время) создания: % s(%s), страниц в дампе: %d, первый номер LSN: %s, последний номер LSN: %s, число устройств хранения: %d, сведения об устройствах: (%s).</span><span class="sxs-lookup"><span data-stu-id="11d3e-116">Database: %s, creation date(time): %s(%s), pages dumped: %d, first LSN: %s, last LSN: %s, number of dump devices: %d, device information: (%s).</span></span> <span data-ttu-id="11d3e-117">Это информационное сообщение.</span><span class="sxs-lookup"><span data-stu-id="11d3e-117">This is an informational message only.</span></span> <span data-ttu-id="11d3e-118">Вмешательство пользователя не требуется.</span><span class="sxs-lookup"><span data-stu-id="11d3e-118">No user action is required.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="11d3e-119">Объяснение</span><span class="sxs-lookup"><span data-stu-id="11d3e-119">Explanation</span></span>  
 <span data-ttu-id="11d3e-120">По умолчанию после каждого успешного создания резервной копии это информационное сообщение добавляется к журналу регистрации ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и к журналу системных событий.</span><span class="sxs-lookup"><span data-stu-id="11d3e-120">By default, every successful backup adds this informational message to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and the system event log.</span></span> <span data-ttu-id="11d3e-121">Если резервные копии журнала транзакций создаются очень часто, эти сообщения могут быстро накапливаться, создавая весьма крупные журналы регистрации ошибок, из-за чего возникают затруднения при поиске других сообщений.</span><span class="sxs-lookup"><span data-stu-id="11d3e-121">If you very frequently back up the transaction log, these messages can accumulate quickly, creating very large error logs that can make finding other messages difficult.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="11d3e-122">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="11d3e-122">User Action</span></span>  
 <span data-ttu-id="11d3e-123">Вы можете отключить эти записи журнала в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью флага трассировки **3226**.</span><span class="sxs-lookup"><span data-stu-id="11d3e-123">You can suppress these log entries by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trace flag **3226**.</span></span> <span data-ttu-id="11d3e-124">Включение этого флага трассировки может потребоваться, если резервное копирование журналов выполняется часто и если ни один из применяемых скриптов не зависит от указанных записей.</span><span class="sxs-lookup"><span data-stu-id="11d3e-124">Enabling this trace flag is useful if you are running frequent log backups and if none of your scripts depend on those entries.</span></span>  
  
 <span data-ttu-id="11d3e-125">Сведения об использовании флагов трассировки см. в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="11d3e-125">For information about using trace flags, see SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11d3e-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="11d3e-126">See Also</span></span>  
 [<span data-ttu-id="11d3e-127">Флаги трассировки (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="11d3e-127">Trace Flags &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql)  
  
  
