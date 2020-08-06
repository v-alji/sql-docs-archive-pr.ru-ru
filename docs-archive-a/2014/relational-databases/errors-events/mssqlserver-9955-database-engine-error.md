---
title: MSSQLSERVER_9955 | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9955 (Database Engine error)
ms.assetid: 77f30570-7790-4747-b372-eac71c036e19
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 56b9f9b4b7923f8973bd7167c3c1bf77e92300c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658737"
---
# <a name="mssqlserver_9955"></a><span data-ttu-id="1614b-102">MSSQLSERVER_9955</span><span class="sxs-lookup"><span data-stu-id="1614b-102">MSSQLSERVER_9955</span></span>
    
## <a name="details"></a><span data-ttu-id="1614b-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="1614b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1614b-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="1614b-104">Product Name</span></span>|<span data-ttu-id="1614b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1614b-105">SQL Server</span></span>|  
|<span data-ttu-id="1614b-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="1614b-106">Event ID</span></span>|<span data-ttu-id="1614b-107">9955</span><span class="sxs-lookup"><span data-stu-id="1614b-107">9955</span></span>|  
|<span data-ttu-id="1614b-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="1614b-108">Event Source</span></span>|<span data-ttu-id="1614b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1614b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1614b-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="1614b-110">Component</span></span>|<span data-ttu-id="1614b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1614b-111">SQLEngine</span></span>|  
|<span data-ttu-id="1614b-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="1614b-112">Symbolic Name</span></span>|<span data-ttu-id="1614b-113">FTXT2_MSSEARCHACCESSDENY</span><span class="sxs-lookup"><span data-stu-id="1614b-113">FTXT2_MSSEARCHACCESSDENY</span></span>|  
|<span data-ttu-id="1614b-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="1614b-114">Message Text</span></span>|<span data-ttu-id="1614b-115">SQL Server не удалось создать именованный канал "%ls" для обмена данными с управляющей программой полнотекстовой фильтрации (ошибка Windows: %d).</span><span class="sxs-lookup"><span data-stu-id="1614b-115">SQL Server failed to create named pipe '%ls' to communicate with the full-text filter daemon (Windows error: %d).</span></span> <span data-ttu-id="1614b-116">Именованный канал для процесса узла управляющей программы фильтрации уже существует, системе не хватает ресурсов или не удалось найти идентификатор безопасности для ее группы учетной записи.</span><span class="sxs-lookup"><span data-stu-id="1614b-116">Either a named pipe already exists for a filter daemon host process, the system is low on resources, or the security identification number (SID) lookup for the filter daemon account group failed.</span></span> <span data-ttu-id="1614b-117">чтобы решить эту проблему, завершите все запущенные процессы управляющей программы полнотекстовой фильтрации и при необходимости измените конфигурацию учетной записи службы запуска этой программы.</span><span class="sxs-lookup"><span data-stu-id="1614b-117">To resolve this error, terminate any running full-text filter daemon processes, and if necessary reconfigure the full-text daemon launcher service account.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1614b-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="1614b-118">Explanation</span></span>  
 <span data-ttu-id="1614b-119">Это сообщение возникло потому, что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удалось создать именованный канал для обмена данными с управляющей программой полнотекстовой фильтрации.</span><span class="sxs-lookup"><span data-stu-id="1614b-119">This message occurs because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failed to create a named pipe to communicate with the full-text filter daemon.</span></span> <span data-ttu-id="1614b-120">Именованный канал для процесса узла управляющей программы фильтрации уже существует, системе не хватает ресурсов или не удалось найти идентификатор безопасности для ее группы учетной записи.</span><span class="sxs-lookup"><span data-stu-id="1614b-120">Either a named pipe already exists for a filter daemon host process, the system is low on resources, or the security identification number (SID) lookup for the filter daemon account group failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1614b-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="1614b-121">User Action</span></span>  
 <span data-ttu-id="1614b-122">Чтобы устранить эту ошибку, завершите все запущенные процессы управляющей программы полнотекстовой фильтрации и при необходимости измените конфигурацию учетной записи этой программы с помощью диспетчера конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1614b-122">To resolve this error, terminate any running full-text filter daemon processes, and if necessary reconfigure the full-text daemon host account by using the SQL Server Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1614b-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="1614b-123">See Also</span></span>  
 <span data-ttu-id="1614b-124">[Диспетчер конфигурации SQL Server](../sql-server-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="1614b-124">[SQL Server Configuration Manager](../sql-server-configuration-manager.md) </span></span>  
 <span data-ttu-id="1614b-125">[Настройка учетной записи службы для средства запуска управляющей программы полнотекстовой фильтрации](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span><span class="sxs-lookup"><span data-stu-id="1614b-125">[Set the Service Account for the Full-text Filter Daemon Launcher](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span></span>  
 [<span data-ttu-id="1614b-126">Полнотекстовый поиск</span><span class="sxs-lookup"><span data-stu-id="1614b-126">Full-Text Search</span></span>](../search/full-text-search.md)  
  
  
