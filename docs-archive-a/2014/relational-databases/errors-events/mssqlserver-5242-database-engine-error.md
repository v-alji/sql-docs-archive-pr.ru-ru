---
title: MSSQLSERVER_5242 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5242 (Database Engine error)
ms.assetid: 712b1a10-2f87-41df-a111-1ed9f14102d4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c979d0a788e80cf5c7e1ab9b9a1ca8eccc0eea19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658768"
---
# <a name="mssqlserver_5242"></a><span data-ttu-id="af922-102">MSSQLSERVER_5242</span><span class="sxs-lookup"><span data-stu-id="af922-102">MSSQLSERVER_5242</span></span>
    
## <a name="details"></a><span data-ttu-id="af922-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="af922-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="af922-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="af922-104">Product Name</span></span>|<span data-ttu-id="af922-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="af922-105">SQL Server</span></span>|  
|<span data-ttu-id="af922-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="af922-106">Event ID</span></span>|<span data-ttu-id="af922-107">5242</span><span class="sxs-lookup"><span data-stu-id="af922-107">5242</span></span>|  
|<span data-ttu-id="af922-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="af922-108">Event Source</span></span>|<span data-ttu-id="af922-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="af922-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="af922-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="af922-110">Component</span></span>|<span data-ttu-id="af922-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="af922-111">SQLEngine</span></span>|  
|<span data-ttu-id="af922-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="af922-112">Symbolic Name</span></span>||  
|<span data-ttu-id="af922-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="af922-113">Message Text</span></span>|<span data-ttu-id="af922-114">В ходе выполнения внутренней операции в базе данных «%.\*ls» (идентификатор: %d) на странице %S_PGID была обнаружена несогласованность.</span><span class="sxs-lookup"><span data-stu-id="af922-114">An inconsistency was detected during an internal operation in database '%.\*ls'(ID:%d) on page %S_PGID.</span></span> <span data-ttu-id="af922-115">Обратитесь в службу технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="af922-115">Please contact technical support.</span></span> <span data-ttu-id="af922-116">Номер ссылки %ld.</span><span class="sxs-lookup"><span data-stu-id="af922-116">Reference number %ld.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="af922-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="af922-117">Explanation</span></span>  
 <span data-ttu-id="af922-118">На странице базы данных возникла несогласованность, на которую указывает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="af922-118">A structural inconsistency occurred on the database page that is referenced in the error message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af922-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="af922-119">See Also</span></span>  
 <span data-ttu-id="af922-120">[DBCC CHECKDB &#40;&#41;Transact-SQL](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="af922-120">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 [<span data-ttu-id="af922-121">Файлы и файловые группы базы данных</span><span class="sxs-lookup"><span data-stu-id="af922-121">Database Files and Filegroups</span></span>](../databases/database-files-and-filegroups.md)  
  
  
