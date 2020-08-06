---
title: MSSQLSERVER_21892 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21892 (Database Engine error)
ms.assetid: 199818e8-28f4-440e-ad85-7bea88f51153
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5fd3bfa1213f0569293991d6bd759619c6e7b596
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740022"
---
# <a name="mssqlserver_21892"></a><span data-ttu-id="8b073-102">MSSQLSERVER_21892</span><span class="sxs-lookup"><span data-stu-id="8b073-102">MSSQLSERVER_21892</span></span>
    
## <a name="details"></a><span data-ttu-id="8b073-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="8b073-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8b073-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="8b073-104">Product Name</span></span>|<span data-ttu-id="8b073-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8b073-105">SQL Server</span></span>|  
|<span data-ttu-id="8b073-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="8b073-106">Event ID</span></span>|<span data-ttu-id="8b073-107">21892</span><span class="sxs-lookup"><span data-stu-id="8b073-107">21892</span></span>|  
|<span data-ttu-id="8b073-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="8b073-108">Event Source</span></span>|<span data-ttu-id="8b073-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8b073-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8b073-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="8b073-110">Component</span></span>|<span data-ttu-id="8b073-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8b073-111">SQLEngine</span></span>|  
|<span data-ttu-id="8b073-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="8b073-112">Symbolic Name</span></span>|<span data-ttu-id="8b073-113">SQLErrorNum21892</span><span class="sxs-lookup"><span data-stu-id="8b073-113">SQLErrorNum21892</span></span>|  
|<span data-ttu-id="8b073-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="8b073-114">Message Text</span></span>|<span data-ttu-id="8b073-115">Невозможно запросить имена серверов реплик-членов в представлении sys.availability_replicas первичной реплики группы доступности, связанной с именем виртуальной сети " %s" : ошибка = %d, сообщение об ошибке = %s',</span><span class="sxs-lookup"><span data-stu-id="8b073-115">Unable to query sys.availability_replicas at the availability group primary associated with virtual network name '%s' for the server names of the member replicas: error = %d, error message = %s.',</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8b073-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="8b073-116">Explanation</span></span>  
 <span data-ttu-id="8b073-117">`sp_validate_replica_hosts_as_publishers` выполняет запрос к текущей первичной реплике группы доступности, связанной с перенаправленным издателем, чтобы определить, на каких экземплярах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] размещены реплики-члены.</span><span class="sxs-lookup"><span data-stu-id="8b073-117">`sp_validate_replica_hosts_as_publishers` queries the current primary of the availability group associated with the redirected publisher, to determine the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that host the member replicas.</span></span>  <span data-ttu-id="8b073-118">Если выполнить этот запрос не удается, возвращается ошибка 21892.</span><span class="sxs-lookup"><span data-stu-id="8b073-118">When this query fails, error 21892 is returned.</span></span>  
  
 <span data-ttu-id="8b073-119">`sp_validate_replica_hosts_as_publishers` обычно вызывается при первом использовании временно связанного сервера, поэтому проблемы с подключением, вероятнее всего, в первую очередь проявятся при вызове `sp_validate_replica_hosts_as_publishers`.</span><span class="sxs-lookup"><span data-stu-id="8b073-119">`sp_validate_replica_hosts_as_publishers` is typically on of the first use of the temporary linked server, so if there are connectivity problems they are likely to appear first with `sp_validate_replica_hosts_as_publishers`.</span></span> <span data-ttu-id="8b073-120">В отличие от `sp_validate_redirected_publisher`, связанный сервер, используемый `sp_validate_replica_hosts_as_publishers`, всегда использует учетные данные вызывающей стороны при соединении с любым из узлов реплик группы доступности.</span><span class="sxs-lookup"><span data-stu-id="8b073-120">Unlike `sp_validate_redirected_publisher`, the linked server used by `sp_validate_replica_hosts_as_publishers` always uses the credentials of the caller when connecting to any of the availability group replica hosts.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8b073-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="8b073-121">User Action</span></span>  
 <span data-ttu-id="8b073-122">При запуске этой хранимой процедуры убедитесь, что имя входа, используемое при выполнении, действительно на всех репликах.</span><span class="sxs-lookup"><span data-stu-id="8b073-122">When running this stored procedure, made certain that you run from a login that is valid on all of the replicas.</span></span> <span data-ttu-id="8b073-123">У имени входа должны быть достаточные права на авторизацию для выполнения запросов к таблицам метаданных группы доступности, а также к таблицам метаданных подписки на реплике базы данных издателя.</span><span class="sxs-lookup"><span data-stu-id="8b073-123">The login will require sufficient authorization to query availability group metadata tables as well as to query the subscription metadata tables in the publisher database replica.</span></span>  
  
 <span data-ttu-id="8b073-124">Просмотрите исходное сообщение об ошибке, на которое указывает ссылка, чтобы определить причину ошибки и соответствующие действия по ее исправлению.</span><span class="sxs-lookup"><span data-stu-id="8b073-124">Examine the original referenced error to determine the cause of the failure and appropriate corrective action.</span></span>  
  
  
