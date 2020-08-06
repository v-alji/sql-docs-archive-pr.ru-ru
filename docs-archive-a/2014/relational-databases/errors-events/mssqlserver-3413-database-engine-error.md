---
title: MSSQLSERVER_3413 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3413 (Database Engine error)
ms.assetid: 3fa07637-ba93-4633-aaf2-ade7d18bc487
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a5d59ea61cff7051c3e1163a463c29443c553923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667121"
---
# <a name="mssqlserver_3413"></a><span data-ttu-id="5cf77-102">MSSQLSERVER_3413</span><span class="sxs-lookup"><span data-stu-id="5cf77-102">MSSQLSERVER_3413</span></span>
    
## <a name="details"></a><span data-ttu-id="5cf77-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="5cf77-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5cf77-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="5cf77-104">Product Name</span></span>|<span data-ttu-id="5cf77-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5cf77-105">SQL Server</span></span>|  
|<span data-ttu-id="5cf77-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="5cf77-106">Event ID</span></span>|<span data-ttu-id="5cf77-107">3413</span><span class="sxs-lookup"><span data-stu-id="5cf77-107">3413</span></span>|  
|<span data-ttu-id="5cf77-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="5cf77-108">Event Source</span></span>|<span data-ttu-id="5cf77-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5cf77-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5cf77-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="5cf77-110">Component</span></span>|<span data-ttu-id="5cf77-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5cf77-111">SQLEngine</span></span>|  
|<span data-ttu-id="5cf77-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="5cf77-112">Symbolic Name</span></span>|<span data-ttu-id="5cf77-113">MARKDB</span><span class="sxs-lookup"><span data-stu-id="5cf77-113">MARKDB</span></span>|  
|<span data-ttu-id="5cf77-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="5cf77-114">Message Text</span></span>|<span data-ttu-id="5cf77-115">Идентификатор базы данных %d.</span><span class="sxs-lookup"><span data-stu-id="5cf77-115">Database ID %d.</span></span> <span data-ttu-id="5cf77-116">Не удалось пометить базу данных как подозрительную.</span><span class="sxs-lookup"><span data-stu-id="5cf77-116">Could not mark database as suspect.</span></span> <span data-ttu-id="5cf77-117">Не удалось выполнить просмотр Getnext NC по sys.databases.database_id.</span><span class="sxs-lookup"><span data-stu-id="5cf77-117">Getnext NC scan on sys.databases.database_id failed.</span></span> <span data-ttu-id="5cf77-118">Просмотрите предыдущие ошибки в журнале ошибок для определения причины и устраните выявленные проблемы.</span><span class="sxs-lookup"><span data-stu-id="5cf77-118">Refer to previous errors in the error log to identify the cause and correct any associated problems.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5cf77-119">Объяснение</span><span class="sxs-lookup"><span data-stu-id="5cf77-119">Explanation</span></span>  
 <span data-ttu-id="5cf77-120">При попытке пометить в каталоге пользовательскую базу данных признаком SUSPECT произошел непредвиденный сбой.</span><span class="sxs-lookup"><span data-stu-id="5cf77-120">There was an unexpected failure while trying to mark a user database as SUSPECT in the catalog.</span></span> <span data-ttu-id="5cf77-121">Состояние SUSPECT установлено не будет.</span><span class="sxs-lookup"><span data-stu-id="5cf77-121">The SUSPECT state will not be persisted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5cf77-122">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="5cf77-122">User Action</span></span>  
 <span data-ttu-id="5cf77-123">Для исправления этой неполадки см. предыдущие ошибки.</span><span class="sxs-lookup"><span data-stu-id="5cf77-123">See previous errors and correct the problem.</span></span>  
  
  
