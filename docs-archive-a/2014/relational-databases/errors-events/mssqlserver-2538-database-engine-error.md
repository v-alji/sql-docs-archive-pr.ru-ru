---
title: MSSQLSERVER_2538 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2538 (Database Engine error)
ms.assetid: 0a0f7d79-f1ba-4749-8804-fb660cca3492
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9f4ae886a6fd0abee2f7aa22c6a234c0a6c2d040
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667130"
---
# <a name="mssqlserver_2538"></a><span data-ttu-id="af51d-102">MSSQLSERVER_2538</span><span class="sxs-lookup"><span data-stu-id="af51d-102">MSSQLSERVER_2538</span></span>
    
## <a name="details"></a><span data-ttu-id="af51d-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="af51d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="af51d-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="af51d-104">Product Name</span></span>|<span data-ttu-id="af51d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="af51d-105">SQL Server</span></span>|  
|<span data-ttu-id="af51d-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="af51d-106">Event ID</span></span>|<span data-ttu-id="af51d-107">2538</span><span class="sxs-lookup"><span data-stu-id="af51d-107">2538</span></span>|  
|<span data-ttu-id="af51d-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="af51d-108">Event Source</span></span>|<span data-ttu-id="af51d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="af51d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="af51d-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="af51d-110">Component</span></span>|<span data-ttu-id="af51d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="af51d-111">SQLEngine</span></span>|  
|<span data-ttu-id="af51d-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="af51d-112">Symbolic Name</span></span>|<span data-ttu-id="af51d-113">DBCC_ALLOCATION_SUMMARY_PER_FILE</span><span class="sxs-lookup"><span data-stu-id="af51d-113">DBCC_ALLOCATION_SUMMARY_PER_FILE</span></span>|  
|<span data-ttu-id="af51d-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="af51d-114">Message Text</span></span>|<span data-ttu-id="af51d-115">Файл FILE.</span><span class="sxs-lookup"><span data-stu-id="af51d-115">File FILE.</span></span> <span data-ttu-id="af51d-116">Число экстентов = EXTENTS, использованных страниц = USED_PAGES, зарезервированных страниц = RESERVED_PAGES.</span><span class="sxs-lookup"><span data-stu-id="af51d-116">Number of extents = EXTENTS, used pages = USED_PAGES, reserved pages = RESERVED_PAGES.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="af51d-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="af51d-117">Explanation</span></span>  
 <span data-ttu-id="af51d-118">Эти сведения являются частью выходных данных команды DBCC CHECKALLOC.</span><span class="sxs-lookup"><span data-stu-id="af51d-118">This information is part of the output from the DBCC CHECKALLOC command.</span></span> <span data-ttu-id="af51d-119">Это сведения являются сводкой для каждого файла о размещенных экстентах, использованных и зарезервированных страницах указанной базы данных.</span><span class="sxs-lookup"><span data-stu-id="af51d-119">This information is the per-file summary of allocated extents, used pages, and reserved pages for the specified database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="af51d-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="af51d-120">User Action</span></span>  
 <span data-ttu-id="af51d-121">None</span><span class="sxs-lookup"><span data-stu-id="af51d-121">None</span></span>  
  
  
