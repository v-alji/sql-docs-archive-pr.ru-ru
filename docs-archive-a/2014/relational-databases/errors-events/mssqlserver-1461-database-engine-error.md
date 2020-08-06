---
title: MSSQLSERVER_1461 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1461 (Database Engine error)
ms.assetid: fce10907-4753-441b-b624-f28e00ed7520
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6667728b2cc134632ddc538b662d73533ee4d6ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667169"
---
# <a name="mssqlserver_1461"></a><span data-ttu-id="00514-102">MSSQLSERVER_1461</span><span class="sxs-lookup"><span data-stu-id="00514-102">MSSQLSERVER_1461</span></span>
    
## <a name="details"></a><span data-ttu-id="00514-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="00514-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="00514-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="00514-104">Product Name</span></span>|<span data-ttu-id="00514-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="00514-105">SQL Server</span></span>|  
|<span data-ttu-id="00514-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="00514-106">Event ID</span></span>|<span data-ttu-id="00514-107">1461</span><span class="sxs-lookup"><span data-stu-id="00514-107">1461</span></span>|  
|<span data-ttu-id="00514-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="00514-108">Event Source</span></span>|<span data-ttu-id="00514-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="00514-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="00514-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="00514-110">Component</span></span>|<span data-ttu-id="00514-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="00514-111">SQLEngine</span></span>|  
|<span data-ttu-id="00514-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="00514-112">Symbolic Name</span></span>|<span data-ttu-id="00514-113">DBM_SAFETY_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="00514-113">DBM_SAFETY_MISMATCH</span></span>|  
|<span data-ttu-id="00514-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="00514-114">Message Text</span></span>|<span data-ttu-id="00514-115">Обнаружены различные уровни безопасности зеркального отображения базы данных «%.\*ls» на нескольких серверах.</span><span class="sxs-lookup"><span data-stu-id="00514-115">Different database mirroring safety levels among servers were detected for database "%.\*ls".</span></span> <span data-ttu-id="00514-116">Будет использован уровень безопасности FULL.</span><span class="sxs-lookup"><span data-stu-id="00514-116">The FULL safety level will be used.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="00514-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="00514-117">Explanation</span></span>  
 <span data-ttu-id="00514-118">Соединения зеркального отображения были разорваны при изменении уровня безопасности транзакций, так как параметры безопасности транзакций не совпадали в основной и зеркальной базах данных.</span><span class="sxs-lookup"><span data-stu-id="00514-118">Mirroring connections were broken when the transaction safety level was modified because the transaction safety settings were inconsistent on the principal and mirror databases.</span></span> <span data-ttu-id="00514-119">Будет использоваться параметр безопасности по умолчанию с полной безопасностью транзакций.</span><span class="sxs-lookup"><span data-stu-id="00514-119">The default safety setting of full-transaction safety will be used.</span></span> <span data-ttu-id="00514-120">Сеанс будет выполняться в режиме высокого уровня безопасности.</span><span class="sxs-lookup"><span data-stu-id="00514-120">The session will run in high-safety mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="00514-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="00514-121">User Action</span></span>  
 <span data-ttu-id="00514-122">Чтобы выключить безопасность транзакций, повторно выполните инструкцию ALTER DATABASE *имя_базы_данных* SET PARTNER SAFETY OFF в основной базе данных.</span><span class="sxs-lookup"><span data-stu-id="00514-122">To set transaction safety off, rerun the ALTER DATABASE *database_name* SET PARTNER SAFETY OFF statement on the principal database.</span></span>  
  
  
