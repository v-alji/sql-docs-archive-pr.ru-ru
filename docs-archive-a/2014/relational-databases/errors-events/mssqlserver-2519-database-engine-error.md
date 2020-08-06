---
title: MSSQLSERVER_2519 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2519 (Database Engine error)
ms.assetid: 8dc6ad98-5db8-4c88-8dea-6d455e63b839
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c8577b07586553f4b03714cd31451ac755faf824
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655243"
---
# <a name="mssqlserver_2519"></a><span data-ttu-id="bdb0d-102">MSSQLSERVER_2519</span><span class="sxs-lookup"><span data-stu-id="bdb0d-102">MSSQLSERVER_2519</span></span>
    
## <a name="details"></a><span data-ttu-id="bdb0d-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="bdb0d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bdb0d-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="bdb0d-104">Product Name</span></span>|<span data-ttu-id="bdb0d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bdb0d-105">SQL Server</span></span>|  
|<span data-ttu-id="bdb0d-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="bdb0d-106">Event ID</span></span>|<span data-ttu-id="bdb0d-107">2519</span><span class="sxs-lookup"><span data-stu-id="bdb0d-107">2519</span></span>|  
|<span data-ttu-id="bdb0d-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="bdb0d-108">Event Source</span></span>|<span data-ttu-id="bdb0d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bdb0d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bdb0d-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="bdb0d-110">Component</span></span>|<span data-ttu-id="bdb0d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bdb0d-111">SQLEngine</span></span>|  
|<span data-ttu-id="bdb0d-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="bdb0d-112">Symbolic Name</span></span>|<span data-ttu-id="bdb0d-113">DBCC_NO_EXPRESSION_EVALUATOR</span><span class="sxs-lookup"><span data-stu-id="bdb0d-113">DBCC_NO_EXPRESSION_EVALUATOR</span></span>|  
|<span data-ttu-id="bdb0d-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="bdb0d-114">Message Text</span></span>|<span data-ttu-id="bdb0d-115">Вычисляемые столбцы и определяемые пользователем типы нельзя проверить для объекта с идентификатором O_ID (объект «O_NAME»), поскольку нельзя инициализировать внутреннее средство оценки выражений.</span><span class="sxs-lookup"><span data-stu-id="bdb0d-115">Computed columns and user-defined types cannot be checked for object ID O_ID (object "O_NAME") because the internal expression evaluator could not be initialized.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bdb0d-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="bdb0d-116">Explanation</span></span>  
 <span data-ttu-id="bdb0d-117">Это информационное сообщение указывает на то, что обработчик запросов не может предоставить для DBCC внутренний объект, который позволил бы оценить значения вычисляемых столбцов и определяемых пользователем типов среды CLR.</span><span class="sxs-lookup"><span data-stu-id="bdb0d-117">This informational message indicates that the query processor could not provide DBCC with an internal object to allow for the evaluation of computed columns and common language runtime (CLR) user-defined types.</span></span> <span data-ttu-id="bdb0d-118">Это означает, что не будет проверяться правильность вычисляемых столбцов и определяемых пользователем типов CLR, и они не будут использоваться при проверке командой DBCC согласованности между индексами и базовыми таблицами.</span><span class="sxs-lookup"><span data-stu-id="bdb0d-118">This means that computed columns and CLR user-defined types will not be checked for correctness or be used when DBCC checks the consistency between indexes and base tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bdb0d-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="bdb0d-119">User Action</span></span>  
 <span data-ttu-id="bdb0d-120">None</span><span class="sxs-lookup"><span data-stu-id="bdb0d-120">None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdb0d-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="bdb0d-121">See Also</span></span>  
 [<span data-ttu-id="bdb0d-122">MSSQLSERVER_2518</span><span class="sxs-lookup"><span data-stu-id="bdb0d-122">MSSQLSERVER_2518</span></span>](mssqlserver-2518-database-engine-error.md)  
  
  
