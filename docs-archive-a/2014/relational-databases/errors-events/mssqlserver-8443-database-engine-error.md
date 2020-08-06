---
title: MSSQLSERVER_8443 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8443 (Database Engine error)
ms.assetid: a3541b9c-b1a8-4280-add1-275f08696b62
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ae02cc0d9e5661f4069884c22bf6eea0697bd2d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735278"
---
# <a name="mssqlserver_8443"></a><span data-ttu-id="55e5c-102">MSSQLSERVER_8443</span><span class="sxs-lookup"><span data-stu-id="55e5c-102">MSSQLSERVER_8443</span></span>
    
## <a name="details"></a><span data-ttu-id="55e5c-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="55e5c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="55e5c-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="55e5c-104">Product Name</span></span>|<span data-ttu-id="55e5c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="55e5c-105">SQL Server</span></span>|  
|<span data-ttu-id="55e5c-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="55e5c-106">Event ID</span></span>|<span data-ttu-id="55e5c-107">8443</span><span class="sxs-lookup"><span data-stu-id="55e5c-107">8443</span></span>|  
|<span data-ttu-id="55e5c-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="55e5c-108">Event Source</span></span>|<span data-ttu-id="55e5c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="55e5c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="55e5c-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="55e5c-110">Component</span></span>|<span data-ttu-id="55e5c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="55e5c-111">SQLEngine</span></span>|  
|<span data-ttu-id="55e5c-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="55e5c-112">Symbolic Name</span></span>|<span data-ttu-id="55e5c-113">SB_DIALOG_WO_CONV_GROUP</span><span class="sxs-lookup"><span data-stu-id="55e5c-113">SB_DIALOG_WO_CONV_GROUP</span></span>|  
|<span data-ttu-id="55e5c-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="55e5c-114">Message Text</span></span>|<span data-ttu-id="55e5c-115">Диалог с идентификатором "%.\*ls" и инициатором %d указывает на несуществующую группу сообщений "%.\*ls".</span><span class="sxs-lookup"><span data-stu-id="55e5c-115">The conversation with ID '%.\*ls' and initiator %d references a missing conversation group '%.\*ls'.</span></span> <span data-ttu-id="55e5c-116">Запустите DBCC CHECKDB для анализа и восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="55e5c-116">Run DBCC CHECKDB to analyze and repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="55e5c-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="55e5c-117">Explanation</span></span>  
 <span data-ttu-id="55e5c-118">Для группы сообщений слой метаданных возвратил значение NULL.</span><span class="sxs-lookup"><span data-stu-id="55e5c-118">The metadata layer returned NULL for the conversation group.</span></span> <span data-ttu-id="55e5c-119">База данных каким-то образом повреждена.</span><span class="sxs-lookup"><span data-stu-id="55e5c-119">The database has been corrupted in some way.</span></span> <span data-ttu-id="55e5c-120">Одним из возможных источников повреждений является ошибка жесткого диска.</span><span class="sxs-lookup"><span data-stu-id="55e5c-120">One possible source of corruption is a disk error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="55e5c-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="55e5c-121">User Action</span></span>  
 <span data-ttu-id="55e5c-122">Запустите DBCC CHECKDB в режиме исправлений для восстановления базы данных до согласованного состояния.</span><span class="sxs-lookup"><span data-stu-id="55e5c-122">Run DBCC CHECKDB in repair mode to bring the database back into a consistent state.</span></span> <span data-ttu-id="55e5c-123">При восстановлении согласованности возможно удаление сообщений.</span><span class="sxs-lookup"><span data-stu-id="55e5c-123">It may delete messages if necessary to restore consistency.</span></span> <span data-ttu-id="55e5c-124">Изучите журналы ошибок системы, чтобы понять, не возникла ли эта ошибка в результате другой неисправности в системе.</span><span class="sxs-lookup"><span data-stu-id="55e5c-124">Investigate system error logs to see if this error was caused by another failure in the system.</span></span>  
  
  
