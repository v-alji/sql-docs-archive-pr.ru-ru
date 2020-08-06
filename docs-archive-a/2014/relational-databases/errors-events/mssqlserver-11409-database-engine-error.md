---
title: MSSQLSERVER_11409 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 11409 (Database Engine error)
ms.assetid: 99b71a1c-a72d-4ca9-9d00-4230c9042ba5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e4249e13a3530f69978c78f2e2ca6e4583eed46a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655251"
---
# <a name="mssqlserver_11409"></a><span data-ttu-id="44916-102">MSSQLSERVER_11409</span><span class="sxs-lookup"><span data-stu-id="44916-102">MSSQLSERVER_11409</span></span>
    
## <a name="details"></a><span data-ttu-id="44916-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="44916-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="44916-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="44916-104">Product Name</span></span>|<span data-ttu-id="44916-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="44916-105">SQL Server</span></span>|  
|<span data-ttu-id="44916-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="44916-106">Event ID</span></span>|<span data-ttu-id="44916-107">11409</span><span class="sxs-lookup"><span data-stu-id="44916-107">11409</span></span>|  
|<span data-ttu-id="44916-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="44916-108">Event Source</span></span>|<span data-ttu-id="44916-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="44916-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="44916-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="44916-110">Component</span></span>|<span data-ttu-id="44916-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="44916-111">SQLEngine</span></span>|  
|<span data-ttu-id="44916-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="44916-112">Symbolic Name</span></span>|<span data-ttu-id="44916-113">ALTERCOL_COLSET_DROP</span><span class="sxs-lookup"><span data-stu-id="44916-113">ALTERCOL_COLSET_DROP</span></span>|  
|<span data-ttu-id="44916-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="44916-114">Message Text</span></span>|<span data-ttu-id="44916-115">Не удалось удалить набор столбцов "%.\*ls" в таблице "%.\*ls", поскольку таблица содержит больше 1025 столбцов.</span><span class="sxs-lookup"><span data-stu-id="44916-115">Cannot drop column set '%.\*ls' in table '%.\*ls' because the table contains more than 1025 columns.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="44916-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="44916-116">Explanation</span></span>  
 <span data-ttu-id="44916-117">Таблицы могут содержать максимум 1024 столбца, которые не определены как разреженные или вычисляемые.</span><span class="sxs-lookup"><span data-stu-id="44916-117">Tables can contain a maximum of 1024 columns that are not designated as sparse, or computed.</span></span> <span data-ttu-id="44916-118">Если наличие разреженных столбцов становится причиной превышения 1024 столбцов в таблице, для таблицы должен быть определен набор столбцов.</span><span class="sxs-lookup"><span data-stu-id="44916-118">When sparse columns cause the table to exceed 1024 columns, a column set must be defined for the table.</span></span> <span data-ttu-id="44916-119">В указанной таблице больше 1024 столбцов и предпринята попытка удалить набор столбцов.</span><span class="sxs-lookup"><span data-stu-id="44916-119">The table referenced has more than 1024 columns and you have attempted to remove the column set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="44916-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="44916-120">User Action</span></span>  
 <span data-ttu-id="44916-121">Текущий состав столбцов в таблице таков, что требует сохранения набора столбцов.</span><span class="sxs-lookup"><span data-stu-id="44916-121">With the current columns in the table, you must retain the column set.</span></span>  
  
 <span data-ttu-id="44916-122">Чтобы удалить набор столбцов, сначала удаляйте из таблицы столбцы, пока их количество не станет меньше или равно 1024 столбцам.</span><span class="sxs-lookup"><span data-stu-id="44916-122">To remove the column set, first remove columns from the table, until you have no more than 1024 columns.</span></span> <span data-ttu-id="44916-123">После этого можно удалить набор столбцов.</span><span class="sxs-lookup"><span data-stu-id="44916-123">Then, you can remove the column set.</span></span>  
  
  
