---
title: MSSQLSERVER_9001 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9001 (Database Engine error)
ms.assetid: a54de936-90c6-4845-aa96-29d32f154601
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0e61894d0d071fbdb36dcfb77895c46c61d0bbd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735277"
---
# <a name="mssqlserver_9001"></a><span data-ttu-id="90565-102">MSSQLSERVER_9001</span><span class="sxs-lookup"><span data-stu-id="90565-102">MSSQLSERVER_9001</span></span>
    
## <a name="details"></a><span data-ttu-id="90565-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="90565-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="90565-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="90565-104">Product Name</span></span>|<span data-ttu-id="90565-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="90565-105">SQL Server</span></span>|  
|<span data-ttu-id="90565-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="90565-106">Event ID</span></span>|<span data-ttu-id="90565-107">9001</span><span class="sxs-lookup"><span data-stu-id="90565-107">9001</span></span>|  
|<span data-ttu-id="90565-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="90565-108">Event Source</span></span>|<span data-ttu-id="90565-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="90565-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="90565-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="90565-110">Component</span></span>|<span data-ttu-id="90565-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="90565-111">SQLEngine</span></span>|  
|<span data-ttu-id="90565-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="90565-112">Symbolic Name</span></span>|<span data-ttu-id="90565-113">LOG_NOT_AVAIL</span><span class="sxs-lookup"><span data-stu-id="90565-113">LOG_NOT_AVAIL</span></span>|  
|<span data-ttu-id="90565-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="90565-114">Message Text</span></span>|<span data-ttu-id="90565-115">Журнал для базы данных «%.\*ls» недоступен.</span><span class="sxs-lookup"><span data-stu-id="90565-115">The log for database '%.\*ls' is not available.</span></span> <span data-ttu-id="90565-116">Проверьте журнал событий на наличие сообщений о связанных ошибках.</span><span class="sxs-lookup"><span data-stu-id="90565-116">Check the event log for related error messages.</span></span> <span data-ttu-id="90565-117">Устраните все ошибки и заново запустите базу данных.</span><span class="sxs-lookup"><span data-stu-id="90565-117">Resolve any errors and restart the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="90565-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="90565-118">Explanation</span></span>  
 <span data-ttu-id="90565-119">Журнал базы данных переведен в режим «вне сети».</span><span class="sxs-lookup"><span data-stu-id="90565-119">The database log was taken offline.</span></span> <span data-ttu-id="90565-120">Обычно это означает серьезный сбой и необходимость перезапуска базы данных.</span><span class="sxs-lookup"><span data-stu-id="90565-120">Usually this signifies a catastrophic failure that requires the database to restart.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="90565-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="90565-121">User Action</span></span>  
 <span data-ttu-id="90565-122">Найдите остальные ошибки и перезапустите экземпляр SQL Server, если он еще не перезапустился самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="90565-122">Diagnose other errors and restart the instance of SQL Server if it has not already restarted itself.</span></span>  
  
  
