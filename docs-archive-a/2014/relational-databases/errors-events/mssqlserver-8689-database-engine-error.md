---
title: MSSQLSERVER_8689 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8689 (Database Engine error)
ms.assetid: 99467a32-6576-4272-a076-b16c06933f2a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2cdca0a3cd9ce47ccb39ebeaf8fd1cd260aafbd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730689"
---
# <a name="mssqlserver_8689"></a><span data-ttu-id="cfa0e-102">MSSQLSERVER_8689</span><span class="sxs-lookup"><span data-stu-id="cfa0e-102">MSSQLSERVER_8689</span></span>
    
## <a name="details"></a><span data-ttu-id="cfa0e-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="cfa0e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cfa0e-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="cfa0e-104">Product Name</span></span>|<span data-ttu-id="cfa0e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cfa0e-105">SQL Server</span></span>|  
|<span data-ttu-id="cfa0e-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="cfa0e-106">Event ID</span></span>|<span data-ttu-id="cfa0e-107">8689</span><span class="sxs-lookup"><span data-stu-id="cfa0e-107">8689</span></span>|  
|<span data-ttu-id="cfa0e-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="cfa0e-108">Event Source</span></span>|<span data-ttu-id="cfa0e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cfa0e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cfa0e-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="cfa0e-110">Component</span></span>|<span data-ttu-id="cfa0e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cfa0e-111">SQLEngine</span></span>|  
|<span data-ttu-id="cfa0e-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="cfa0e-112">Symbolic Name</span></span>|<span data-ttu-id="cfa0e-113">USEPLAN_ERR_NO_DB</span><span class="sxs-lookup"><span data-stu-id="cfa0e-113">USEPLAN_ERR_NO_DB</span></span>|  
|<span data-ttu-id="cfa0e-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="cfa0e-114">Message Text</span></span>|<span data-ttu-id="cfa0e-115">База данных "%.\*ls", заданная в указании USE PLAN, не существует.</span><span class="sxs-lookup"><span data-stu-id="cfa0e-115">Database '%.\*ls', specified in the USE PLAN hint, does not exist.</span></span> <span data-ttu-id="cfa0e-116">Укажите существующую базу данных.</span><span class="sxs-lookup"><span data-stu-id="cfa0e-116">Specify an existing database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cfa0e-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="cfa0e-117">Explanation</span></span>  
 <span data-ttu-id="cfa0e-118">База данных, которая задана в указании USE PLAN, не существует.</span><span class="sxs-lookup"><span data-stu-id="cfa0e-118">A database that is specified in the USE PLAN hint does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cfa0e-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="cfa0e-119">User Action</span></span>  
 <span data-ttu-id="cfa0e-120">Убедитесь в том, что существуют все базы данных, которые заданы в указании USE PLAN.</span><span class="sxs-lookup"><span data-stu-id="cfa0e-120">Ensure all databases that are specified in the USE PLAN hint exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfa0e-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="cfa0e-121">See Also</span></span>  
 <span data-ttu-id="cfa0e-122">[Указания запросов (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="cfa0e-122">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="cfa0e-123">Руководства планов</span><span class="sxs-lookup"><span data-stu-id="cfa0e-123">Plan Guides</span></span>](../performance/plan-guides.md)  
  
  
