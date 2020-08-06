---
title: MSSQLSERVER_7308 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7308 (Database Engine error)
- single-threaded apartment mode
ms.assetid: cca9eab9-afb9-463d-abfd-0802257e2c99
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9978f35ebe41eeda1470220772f87e83ab1ad942
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664235"
---
# <a name="mssqlserver_7308"></a><span data-ttu-id="d2518-102">MSSQLSERVER_7308</span><span class="sxs-lookup"><span data-stu-id="d2518-102">MSSQLSERVER_7308</span></span>
    
## <a name="details"></a><span data-ttu-id="d2518-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="d2518-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d2518-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="d2518-104">Product Name</span></span>|<span data-ttu-id="d2518-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d2518-105">SQL Server</span></span>|  
|<span data-ttu-id="d2518-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="d2518-106">Event ID</span></span>|<span data-ttu-id="d2518-107">7308</span><span class="sxs-lookup"><span data-stu-id="d2518-107">7308</span></span>|  
|<span data-ttu-id="d2518-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="d2518-108">Event Source</span></span>|<span data-ttu-id="d2518-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d2518-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d2518-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="d2518-110">Component</span></span>|<span data-ttu-id="d2518-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d2518-111">SQLEngine</span></span>|  
|<span data-ttu-id="d2518-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="d2518-112">Symbolic Name</span></span>|<span data-ttu-id="d2518-113">RMT_STA_DISABLED</span><span class="sxs-lookup"><span data-stu-id="d2518-113">RMT_STA_DISABLED</span></span>|  
|<span data-ttu-id="d2518-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="d2518-114">Message Text</span></span>|<span data-ttu-id="d2518-115">Поставщик OLE DB '%ls' не может быть использован для распределенных запросов, так как он настроен для запуска в потоке контейнера с одним потоком.</span><span class="sxs-lookup"><span data-stu-id="d2518-115">OLE DB provider '%ls' cannot be used for distributed queries because the provider is configured to run in single-threaded apartment mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d2518-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="d2518-116">Explanation</span></span>  
 <span data-ttu-id="d2518-117">Использован поставщик OLE DB, настроенный для запуска в потоке контейнера с одним потоком (STA).</span><span class="sxs-lookup"><span data-stu-id="d2518-117">You have used an OLE DB provider that is configured to run in single-threaded apartment (STA) mode.</span></span> <span data-ttu-id="d2518-118">Поставщики OLE DB, которые работают в потоке контейнера с одним потоком (STA), не могут быть использованы для распределенных запросов.</span><span class="sxs-lookup"><span data-stu-id="d2518-118">OLE DB providers that run in single-threaded apartment (STA) mode cannot be used for distributed queries.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d2518-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="d2518-119">User Action</span></span>  
 <span data-ttu-id="d2518-120">Чтобы устранить эту ошибку, настройте поставщик для запуска в потоке контейнера с несколькими потоками (MTA).</span><span class="sxs-lookup"><span data-stu-id="d2518-120">To resolve this error, configure the provider to run in multithreaded apartment (MTA) mode.</span></span> <span data-ttu-id="d2518-121">Если поставщик не поддерживает несколько потоков и не может быть обновлен до версии, совместимой с MTA, рассмотрите возможность настройки поставщика для внепроцессного выполнения.</span><span class="sxs-lookup"><span data-stu-id="d2518-121">If the provider does not support MTA, and the provider cannot be upgraded to a version that supports MTA, consider configuring the provider to run out-of-process.</span></span> <span data-ttu-id="d2518-122">Информацию о том, поддерживает ли поставщик режим MTA и может ли он выполняться внепроцессно, можно получить у соответствующего разработчика.</span><span class="sxs-lookup"><span data-stu-id="d2518-122">The provider vendor should be able to tell you if the provider supports MTA or running out-of-process.</span></span>  
  
  
