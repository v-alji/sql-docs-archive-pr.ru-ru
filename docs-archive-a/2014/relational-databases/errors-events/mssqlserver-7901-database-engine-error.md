---
title: MSSQLSERVER_7901 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7901 (Database Engine error)
ms.assetid: 2d0d19b9-947b-4474-9ff8-7e03019ab93d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fae6e55cbe7170f795aff85400da2c5cdaef780a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664230"
---
# <a name="mssqlserver_7901"></a><span data-ttu-id="91764-102">MSSQLSERVER_7901</span><span class="sxs-lookup"><span data-stu-id="91764-102">MSSQLSERVER_7901</span></span>
    
## <a name="details"></a><span data-ttu-id="91764-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="91764-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="91764-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="91764-104">Product Name</span></span>|<span data-ttu-id="91764-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="91764-105">SQL Server</span></span>|  
|<span data-ttu-id="91764-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="91764-106">Event ID</span></span>|<span data-ttu-id="91764-107">7901</span><span class="sxs-lookup"><span data-stu-id="91764-107">7901</span></span>|  
|<span data-ttu-id="91764-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="91764-108">Event Source</span></span>|<span data-ttu-id="91764-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="91764-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="91764-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="91764-110">Component</span></span>|<span data-ttu-id="91764-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="91764-111">SQLEngine</span></span>|  
|<span data-ttu-id="91764-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="91764-112">Symbolic Name</span></span>|<span data-ttu-id="91764-113">DBCC2_DATABASE_IN_EMERGENCY_MODE</span><span class="sxs-lookup"><span data-stu-id="91764-113">DBCC2_DATABASE_IN_EMERGENCY_MODE</span></span>|  
|<span data-ttu-id="91764-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="91764-114">Message Text</span></span>|<span data-ttu-id="91764-115">Инструкция восстановления не была обработана.</span><span class="sxs-lookup"><span data-stu-id="91764-115">The repair statement was not processed.</span></span> <span data-ttu-id="91764-116">Данный уровень восстановления не поддерживается, если база данных находится в аварийном режиме.</span><span class="sxs-lookup"><span data-stu-id="91764-116">This level of repair is not supported when the database is in emergency mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="91764-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="91764-117">Explanation</span></span>  
 <span data-ttu-id="91764-118">База данных находится в аварийном режиме, но был задан уровень восстановления, отличный от REPAIR_ALLOW_DATA_LOSS.</span><span class="sxs-lookup"><span data-stu-id="91764-118">The database is in emergency mode and a repair level other than REPAIR_ALLOW_DATA_LOSS has been specified.</span></span> <span data-ttu-id="91764-119">Восстановление не может выполняться в аварийном режиме, если не задан уровень REPAIR_ALLOW_DATA_LOSS.</span><span class="sxs-lookup"><span data-stu-id="91764-119">Repairs cannot be made in emergency mode unless REPAIR_ALLOW_DATA_LOSS is specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="91764-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="91764-120">User Action</span></span>  
 <span data-ttu-id="91764-121">Повторно выполните команду с параметром REPAIR_ALLOW_DATA_LOSS.</span><span class="sxs-lookup"><span data-stu-id="91764-121">Rerun the command and specify the REPAIR_ALLOW_DATA_LOSS option.</span></span>  
  
  
