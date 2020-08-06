---
title: MSSQLSERVER_2511 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2511 (Database Engine error)
ms.assetid: 9a00c0ed-eb4b-4fae-8016-192396006c37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 23e91b0d64140329639cf57f3a336cd2eab8e4e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731633"
---
# <a name="mssqlserver_2511"></a><span data-ttu-id="4d569-102">MSSQLSERVER_2511</span><span class="sxs-lookup"><span data-stu-id="4d569-102">MSSQLSERVER_2511</span></span>
    
## <a name="details"></a><span data-ttu-id="4d569-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="4d569-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4d569-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="4d569-104">Product Name</span></span>|<span data-ttu-id="4d569-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4d569-105">SQL Server</span></span>|  
|<span data-ttu-id="4d569-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="4d569-106">Event ID</span></span>|<span data-ttu-id="4d569-107">2511</span><span class="sxs-lookup"><span data-stu-id="4d569-107">2511</span></span>|  
|<span data-ttu-id="4d569-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="4d569-108">Event Source</span></span>|<span data-ttu-id="4d569-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4d569-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4d569-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="4d569-110">Component</span></span>|<span data-ttu-id="4d569-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4d569-111">SQLEngine</span></span>|  
|<span data-ttu-id="4d569-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="4d569-112">Symbolic Name</span></span>|<span data-ttu-id="4d569-113">DBCC_KEYS_OUT_OF_ORDER</span><span class="sxs-lookup"><span data-stu-id="4d569-113">DBCC_KEYS_OUT_OF_ORDER</span></span>|  
|<span data-ttu-id="4d569-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="4d569-114">Message Text</span></span>|<span data-ttu-id="4d569-115">Ошибка таблицы: идентификатор объекта %d, идентификатор индекса %d, идентификатор секции %I64d, идентификатор единицы распределения %I64d (тип %.\*ls).</span><span class="sxs-lookup"><span data-stu-id="4d569-115">Table error: Object ID %d, index ID %d, partition ID %I64d, alloc unit ID %I64d (type %.\*ls).</span></span> <span data-ttu-id="4d569-116">Нарушен порядок следования ключей на странице %S_PGID, слоты %d и %d.</span><span class="sxs-lookup"><span data-stu-id="4d569-116">Keys out of order on page %S_PGID, slots %d and %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4d569-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="4d569-117">Explanation</span></span>  
 <span data-ttu-id="4d569-118">В указанном индексе были обнаружены неупорядоченные ключи.</span><span class="sxs-lookup"><span data-stu-id="4d569-118">Out-of-order keys were detected in the specified index.</span></span> <span data-ttu-id="4d569-119">Страница, на которой содержатся эти ключи, может быть повреждена.</span><span class="sxs-lookup"><span data-stu-id="4d569-119">The page in which the keys are contained may be corrupted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4d569-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="4d569-120">User Action</span></span>  
 <span data-ttu-id="4d569-121">Перестройте указанный индекс с помощью инструкции ALTER INDEX REBUILD.</span><span class="sxs-lookup"><span data-stu-id="4d569-121">Rebuild the specified index by using the ALTER INDEX REBUILD statement.</span></span>  
  
  
