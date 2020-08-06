---
title: MSSQLSERVER_21889 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21889 (Database Engine error)
ms.assetid: ae199540-7986-4cc2-b782-cd22793236d3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c152a542550d7b81af880545f526037baeb4644e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734097"
---
# <a name="mssqlserver_21889"></a><span data-ttu-id="a2cdf-102">MSSQLSERVER_21889</span><span class="sxs-lookup"><span data-stu-id="a2cdf-102">MSSQLSERVER_21889</span></span>
    
## <a name="details"></a><span data-ttu-id="a2cdf-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="a2cdf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a2cdf-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="a2cdf-104">Product Name</span></span>|<span data-ttu-id="a2cdf-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a2cdf-105">SQL Server</span></span>|  
|<span data-ttu-id="a2cdf-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a2cdf-106">Event ID</span></span>|<span data-ttu-id="a2cdf-107">21889</span><span class="sxs-lookup"><span data-stu-id="a2cdf-107">21889</span></span>|  
|<span data-ttu-id="a2cdf-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="a2cdf-108">Event Source</span></span>|<span data-ttu-id="a2cdf-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a2cdf-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a2cdf-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="a2cdf-110">Component</span></span>|<span data-ttu-id="a2cdf-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a2cdf-111">SQLEngine</span></span>|  
|<span data-ttu-id="a2cdf-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="a2cdf-112">Symbolic Name</span></span>|<span data-ttu-id="a2cdf-113">SQLErrorNum21889</span><span class="sxs-lookup"><span data-stu-id="a2cdf-113">SQLErrorNum21889</span></span>|  
|<span data-ttu-id="a2cdf-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a2cdf-114">Message Text</span></span>|<span data-ttu-id="a2cdf-115">Экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] «%s» не является издателем репликации.</span><span class="sxs-lookup"><span data-stu-id="a2cdf-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance '%s' is not a replication publisher.</span></span> <span data-ttu-id="a2cdf-116">Запустите хранимую процедуру `sp_adddistributor` на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] «%s» с распространителем «%s», чтобы разрешить размещение на данном экземпляре базы данных публикации «%s».</span><span class="sxs-lookup"><span data-stu-id="a2cdf-116">Run `sp_adddistributor` on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance '%s' with distributor '%s' in order to enable the instance to host the publishing database '%s'.</span></span> <span data-ttu-id="a2cdf-117">Убедитесь, что указаны те же имя входа и пароль, что и на исходном издателе.</span><span class="sxs-lookup"><span data-stu-id="a2cdf-117">Make certain to specify the same login and password as that used for the original publisher.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a2cdf-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="a2cdf-118">Explanation</span></span>  
 <span data-ttu-id="a2cdf-119">Для размещения базы данных издателя экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должен быть издателем репликации.</span><span class="sxs-lookup"><span data-stu-id="a2cdf-119">In order to host the publisher database, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be a replication publisher.</span></span> <span data-ttu-id="a2cdf-120">`sp_validate_redirected_publisher` вызывает `sp_helpdistributor` на удаленном сервере, чтобы определить, является ли сервер издателем репликации.</span><span class="sxs-lookup"><span data-stu-id="a2cdf-120">`sp_validate_redirected_publisher` calls `sp_helpdistributor` at the remote server to determine whether the server is a replication publisher.</span></span> <span data-ttu-id="a2cdf-121">Эта ошибка возвращается, если при выполнении хранимой процедуры `sp_helpdistributor` целевой экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не является издателем репликации.</span><span class="sxs-lookup"><span data-stu-id="a2cdf-121">This error is returned when execution of the stored procedure `sp_helpdistributor` indicates that the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not a replication publisher.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a2cdf-122">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a2cdf-122">User Action</span></span>  
 <span data-ttu-id="a2cdf-123">Выполните `sp_adddistributor` на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], на котором расположена база данных издателя.</span><span class="sxs-lookup"><span data-stu-id="a2cdf-123">Execute `sp_adddistributor` at the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the publisher database.</span></span> <span data-ttu-id="a2cdf-124">При запуске `sp_adddistributor` правильно укажите распространителя.</span><span class="sxs-lookup"><span data-stu-id="a2cdf-124">When running `sp_adddistributor`, specify the correct distributor.</span></span> <span data-ttu-id="a2cdf-125">Используйте то же значение для *@password* параметра, которое использовалось при `sp_adddistributor` первоначальном запуске на распространителе.</span><span class="sxs-lookup"><span data-stu-id="a2cdf-125">Use the same value for the *@password* parameter as that used when `sp_adddistributor` was initially run at the distributor.</span></span>  
  
  
