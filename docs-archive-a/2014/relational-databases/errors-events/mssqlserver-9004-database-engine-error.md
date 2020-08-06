---
title: MSSQLSERVER_9004 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9004 (Database Engine error)
ms.assetid: b528bb49-340c-4a81-9c8d-cefce6562f16
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 910665b4349e5b13c5abb4fd687dcf0c6fc122cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658756"
---
# <a name="mssqlserver_9004"></a><span data-ttu-id="dbc3e-102">MSSQLSERVER_9004</span><span class="sxs-lookup"><span data-stu-id="dbc3e-102">MSSQLSERVER_9004</span></span>
    
## <a name="details"></a><span data-ttu-id="dbc3e-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="dbc3e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dbc3e-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="dbc3e-104">Product Name</span></span>|<span data-ttu-id="dbc3e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="dbc3e-105">SQL Server</span></span>|  
|<span data-ttu-id="dbc3e-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="dbc3e-106">Event ID</span></span>|<span data-ttu-id="dbc3e-107">9004</span><span class="sxs-lookup"><span data-stu-id="dbc3e-107">9004</span></span>|  
|<span data-ttu-id="dbc3e-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="dbc3e-108">Event Source</span></span>|<span data-ttu-id="dbc3e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="dbc3e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="dbc3e-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="dbc3e-110">Component</span></span>|<span data-ttu-id="dbc3e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="dbc3e-111">SQLEngine</span></span>|  
|<span data-ttu-id="dbc3e-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="dbc3e-112">Symbolic Name</span></span>|<span data-ttu-id="dbc3e-113">LOG_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="dbc3e-113">LOG_CORRUPT</span></span>|  
|<span data-ttu-id="dbc3e-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="dbc3e-114">Message Text</span></span>|<span data-ttu-id="dbc3e-115">Произошла ошибка при обработке журнала для базы данных "%.\*ls".</span><span class="sxs-lookup"><span data-stu-id="dbc3e-115">An error occurred while processing the log for database '%.\*ls'.</span></span>  <span data-ttu-id="dbc3e-116">Если возможно, восстановите из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="dbc3e-116">If possible, restore from backup.</span></span> <span data-ttu-id="dbc3e-117">Если резервная копия недоступна, возможно, понадобится перестроить журнал.</span><span class="sxs-lookup"><span data-stu-id="dbc3e-117">If a backup is not available, it might be necessary to rebuild the log.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dbc3e-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="dbc3e-118">Explanation</span></span>  
 <span data-ttu-id="dbc3e-119">Во время обработки журнала возникла ошибка при выполнении операции отката, восстановления или репликации.</span><span class="sxs-lookup"><span data-stu-id="dbc3e-119">An error was encountered while processing the log during rollback, recovery, or replication.</span></span> <span data-ttu-id="dbc3e-120">Это может указывать либо на обнаруженную операционной системой ошибку, либо на ошибку внутренней согласованности, обнаруженную [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dbc3e-120">This could indicate an error detected by the operating system-or an internal consistency error detected by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dbc3e-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="dbc3e-121">User Action</span></span>  
 <span data-ttu-id="dbc3e-122">Одно из следующих действий исправит эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="dbc3e-122">One of the following actions will correct this error:</span></span>  
  
-   <span data-ttu-id="dbc3e-123">Восстановление из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="dbc3e-123">Restore from a backup.</span></span>  
  
-   <span data-ttu-id="dbc3e-124">Перестроение журнала.</span><span class="sxs-lookup"><span data-stu-id="dbc3e-124">Rebuild the log.</span></span>  
  
 <span data-ttu-id="dbc3e-125">Также проверьте системные события и журналы ошибок для определения неполадок в системе, которые могут являться причиной проблемы.</span><span class="sxs-lookup"><span data-stu-id="dbc3e-125">Also, check system event and error logs to identify issues within the system that may have caused the problem.</span></span>  
  
  
