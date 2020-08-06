---
title: MSSQLSERVER_905 | Документация Майкрософт
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 905 (Database Engine error)
ms.assetid: c828bb2e-e554-4f81-b76c-2b3740d2b944
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7dd3c8c5a287e2d123e2a9d1430ecd49b27f29f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658755"
---
# <a name="mssqlserver_905"></a><span data-ttu-id="97301-102">MSSQLSERVER_905</span><span class="sxs-lookup"><span data-stu-id="97301-102">MSSQLSERVER_905</span></span>
    
## <a name="details"></a><span data-ttu-id="97301-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="97301-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="97301-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="97301-104">Product Name</span></span>|<span data-ttu-id="97301-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="97301-105">SQL Server</span></span>|  
|<span data-ttu-id="97301-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="97301-106">Event ID</span></span>|<span data-ttu-id="97301-107">905</span><span class="sxs-lookup"><span data-stu-id="97301-107">905</span></span>|  
|<span data-ttu-id="97301-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="97301-108">Event Source</span></span>|<span data-ttu-id="97301-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="97301-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="97301-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="97301-110">Component</span></span>|<span data-ttu-id="97301-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="97301-111">SQLEngine</span></span>|  
|<span data-ttu-id="97301-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="97301-112">Symbolic Name</span></span>|<span data-ttu-id="97301-113">DBSTARTUP_EE_PARTITIONING</span><span class="sxs-lookup"><span data-stu-id="97301-113">DBSTARTUP_EE_PARTITIONING</span></span>|  
|<span data-ttu-id="97301-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="97301-114">Message Text</span></span>|<span data-ttu-id="97301-115">Невозможно запустить базу данных "%.\*ls" в этом выпуске SQL Server, так как она содержит функцию секционирования "%.\*ls".</span><span class="sxs-lookup"><span data-stu-id="97301-115">Database '%.\*ls' cannot be started in this edition of SQL Server because it contains a partition function '%.\*ls'.</span></span> <span data-ttu-id="97301-116">Секционирование поддерживается только в выпуске SQL Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="97301-116">Only Enterprise edition of SQL Server supports partitioning.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="97301-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="97301-117">Explanation</span></span>  
 <span data-ttu-id="97301-118">База данных содержит одну или несколько секционированных таблиц или индексов.</span><span class="sxs-lookup"><span data-stu-id="97301-118">The database contains one or more partitioned tables or indexes.</span></span> <span data-ttu-id="97301-119">В этом выпуске [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не может использоваться секционирование.</span><span class="sxs-lookup"><span data-stu-id="97301-119">This edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot use partitioning.</span></span> <span data-ttu-id="97301-120">Поэтому правильный запуск базы данных невозможен.</span><span class="sxs-lookup"><span data-stu-id="97301-120">Therefore, the database cannot be started correctly.</span></span> <span data-ttu-id="97301-121">Секционированные таблицы и индексы доступны не в каждом выпуске [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97301-121">Partitioned tables and indexes are not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="97301-122">Перечень функций, поддерживаемых в разных выпусках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], см. в разделе [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="97301-122">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="97301-123">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="97301-123">User Action</span></span>  
 <span data-ttu-id="97301-124">Отсоедините базу данных при помощи хранимой процедуры sp_detach_db.</span><span class="sxs-lookup"><span data-stu-id="97301-124">Detach the database by using the sp_detach_db stored procedure.</span></span> <span data-ttu-id="97301-125">Если необходимо, переместите файлы, а затем подключите базу данных к экземпляру поддерживаемого выпуска [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при помощи инструкции CREATE DATABASE с параметром FOR ATTACH или FOR ATTACH_REBUILD_LOG.</span><span class="sxs-lookup"><span data-stu-id="97301-125">Move the files if it is needed, and then attach the database to an instance of a supported [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] edition by using the CREATE DATABASE with the FOR ATTACH or FOR ATTACH_REBUILD_LOG option.</span></span> <span data-ttu-id="97301-126">Отмените секционирование на всех таблицах и удалите функции секционирования.</span><span class="sxs-lookup"><span data-stu-id="97301-126">Disable partitioning on all tables and remove the partitioning functions.</span></span> <span data-ttu-id="97301-127">Снова отсоедините базу данных и повторно присоедините ее к текущему серверу.</span><span class="sxs-lookup"><span data-stu-id="97301-127">Detach the database again, and reattach the database to the current server.</span></span>  
  
  
