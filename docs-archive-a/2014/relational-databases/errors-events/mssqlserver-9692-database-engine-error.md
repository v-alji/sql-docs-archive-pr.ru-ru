---
title: MSSQLSERVER_9692 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9692 (Database Engine error)
ms.assetid: 02399d6e-ab5e-4f30-8a3e-2bb1e8c135b5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b6ba95771aafffa5a322ffa1b7443419936addd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658748"
---
# <a name="mssqlserver_9692"></a><span data-ttu-id="628a4-102">MSSQLSERVER_9692</span><span class="sxs-lookup"><span data-stu-id="628a4-102">MSSQLSERVER_9692</span></span>
    
## <a name="details"></a><span data-ttu-id="628a4-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="628a4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="628a4-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="628a4-104">Product Name</span></span>|<span data-ttu-id="628a4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="628a4-105">SQL Server</span></span>|  
|<span data-ttu-id="628a4-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="628a4-106">Event ID</span></span>|<span data-ttu-id="628a4-107">9692</span><span class="sxs-lookup"><span data-stu-id="628a4-107">9692</span></span>|  
|<span data-ttu-id="628a4-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="628a4-108">Event Source</span></span>|<span data-ttu-id="628a4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="628a4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="628a4-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="628a4-110">Component</span></span>|<span data-ttu-id="628a4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="628a4-111">SQLEngine</span></span>|  
|<span data-ttu-id="628a4-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="628a4-112">Symbolic Name</span></span>|<span data-ttu-id="628a4-113">SB2_CANT_LISTEN_PORT_IN_USE</span><span class="sxs-lookup"><span data-stu-id="628a4-113">SB2_CANT_LISTEN_PORT_IN_USE</span></span>|  
|<span data-ttu-id="628a4-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="628a4-114">Message Text</span></span>|<span data-ttu-id="628a4-115">Транспортному протоколу %S_MSG не удается прослушать порт %d, поскольку он занят другим процессом.</span><span class="sxs-lookup"><span data-stu-id="628a4-115">The %S_MSG protocol transport cannot listen on port %d because it is in use by another process.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="628a4-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="628a4-116">Explanation</span></span>  
 <span data-ttu-id="628a4-117">Указанный TCP-порт используется другим приложением или компьютером.</span><span class="sxs-lookup"><span data-stu-id="628a4-117">Another program on the computer is using the TCP port indicated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="628a4-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="628a4-118">User Action</span></span>  
 <span data-ttu-id="628a4-119">Выполните команду `netstat -aon` , чтобы определить, какая программа использует порт.</span><span class="sxs-lookup"><span data-stu-id="628a4-119">Run `netstat -aon` to determine what program is using the port.</span></span> <span data-ttu-id="628a4-120">Закройте это приложение или укажите другой порт для компонента Service Broker.</span><span class="sxs-lookup"><span data-stu-id="628a4-120">Disable that application or specify a different port for Service Broker.</span></span>  
  
  
