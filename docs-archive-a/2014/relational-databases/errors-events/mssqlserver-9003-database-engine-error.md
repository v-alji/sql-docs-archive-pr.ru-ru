---
title: MSSQLSERVER_9003 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9003 (Database Engine error)
ms.assetid: 7fdfb391-5c6f-428b-b434-6c3d0b30fd7b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6f67e4184ea54be6bcd5c2a74d3c0e0711b702f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666067"
---
# <a name="mssqlserver_9003"></a><span data-ttu-id="6271e-102">MSSQLSERVER_9003</span><span class="sxs-lookup"><span data-stu-id="6271e-102">MSSQLSERVER_9003</span></span>
    
## <a name="details"></a><span data-ttu-id="6271e-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="6271e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6271e-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="6271e-104">Product Name</span></span>|<span data-ttu-id="6271e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6271e-105">SQL Server</span></span>|  
|<span data-ttu-id="6271e-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6271e-106">Event ID</span></span>|<span data-ttu-id="6271e-107">9003</span><span class="sxs-lookup"><span data-stu-id="6271e-107">9003</span></span>|  
|<span data-ttu-id="6271e-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="6271e-108">Event Source</span></span>|<span data-ttu-id="6271e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6271e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6271e-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="6271e-110">Component</span></span>|<span data-ttu-id="6271e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6271e-111">SQLEngine</span></span>|  
|<span data-ttu-id="6271e-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="6271e-112">Symbolic Name</span></span>|<span data-ttu-id="6271e-113">LOG_INVALID_LSN</span><span class="sxs-lookup"><span data-stu-id="6271e-113">LOG_INVALID_LSN</span></span>|  
|<span data-ttu-id="6271e-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="6271e-114">Message Text</span></span>|<span data-ttu-id="6271e-115">Передан недопустимый номер %S_LSN для просмотра журнала в базе данных «%.\*ls».</span><span class="sxs-lookup"><span data-stu-id="6271e-115">The log scan number %S_LSN passed to log scan in database '%.\*ls' is not valid.</span></span> <span data-ttu-id="6271e-116">Эта ошибка может свидетельствовать о повреждении данных или о том, что файл журнала (LDF) не соответствует файлу данных (MDF).</span><span class="sxs-lookup"><span data-stu-id="6271e-116">This error may indicate data corruption or that the log file (.ldf) does not match the data file (.mdf).</span></span> <span data-ttu-id="6271e-117">Если она возникла во время репликации, повторно создайте публикацию.</span><span class="sxs-lookup"><span data-stu-id="6271e-117">If this error occurred during replication, re-create the publication.</span></span> <span data-ttu-id="6271e-118">В противном случае, если ошибка приводит к сбою при загрузке, произведите восстановление из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="6271e-118">Otherwise, restore from backup if the problem results in a failure during startup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6271e-119">Объяснение</span><span class="sxs-lookup"><span data-stu-id="6271e-119">Explanation</span></span>  
 <span data-ttu-id="6271e-120">Компонент передал менеджеру журнала базы данных недопустимый регистрационный номер транзакции в журнале.</span><span class="sxs-lookup"><span data-stu-id="6271e-120">A component passed an invalid log sequence number to the log manager for the database.</span></span> <span data-ttu-id="6271e-121">Это может быть вызвано проблемами репликации, повреждением данных или несоответствием между первичным файлом данных и файлом журнала.</span><span class="sxs-lookup"><span data-stu-id="6271e-121">This could be replication, corruption, or an inconsistency between the primary data file and the log.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6271e-122">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="6271e-122">User Action</span></span>  
 <span data-ttu-id="6271e-123">Если эта ошибка возникла во время репликации, повторно создайте публикацию.</span><span class="sxs-lookup"><span data-stu-id="6271e-123">If this occurred during replication, recreate the publication.</span></span> <span data-ttu-id="6271e-124">В противном случае выполните восстановление из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="6271e-124">Otherwise, restore from backup.</span></span>  
  
  
