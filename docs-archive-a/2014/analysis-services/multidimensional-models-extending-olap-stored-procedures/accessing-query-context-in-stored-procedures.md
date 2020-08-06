---
title: Доступ к контексту запроса в хранимых процедурах | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- execution context [Analysis Services]
- stored procedures [Analysis Services], query context
- Context object
- query context [Analysis Services]
ms.assetid: bdc7dad8-2f22-4265-aba4-a3a451527840
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9da8ddb223ed03c0208fe524ea5cd7195a039c97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727437"
---
# <a name="accessing-query-context-in-stored-procedures"></a><span data-ttu-id="dfb75-102">Доступ к контексту запросов в хранимых процедурах</span><span class="sxs-lookup"><span data-stu-id="dfb75-102">Accessing Query Context in Stored Procedures</span></span>
  <span data-ttu-id="dfb75-103">Контекст выполнения хранимой процедуры доступен в рамках кода хранимой процедуры как объект `Context` модели объектов сервера ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="dfb75-103">The execution context of a stored procedure is available within the code of the stored procedure as the `Context` object of the ADOMD.NET server object model.</span></span> <span data-ttu-id="dfb75-104">Этот контекст доступен только для чтения и не может быть изменен хранимой процедурой.</span><span class="sxs-lookup"><span data-stu-id="dfb75-104">This is a read-only context and cannot be modified by the stored procedure.</span></span> <span data-ttu-id="dfb75-105">На этом объекте доступны следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="dfb75-105">The following properties are available on this object.</span></span>  
  
|<span data-ttu-id="dfb75-106">Свойство</span><span class="sxs-lookup"><span data-stu-id="dfb75-106">Property</span></span>|<span data-ttu-id="dfb75-107">Type</span><span class="sxs-lookup"><span data-stu-id="dfb75-107">Type</span></span>|<span data-ttu-id="dfb75-108">Описание</span><span class="sxs-lookup"><span data-stu-id="dfb75-108">Description</span></span>|  
|--------------|----------|-----------------|  
|<span data-ttu-id="dfb75-109">**CurrentCube**</span><span class="sxs-lookup"><span data-stu-id="dfb75-109">**CurrentCube**</span></span>|<span data-ttu-id="dfb75-110">Куб</span><span class="sxs-lookup"><span data-stu-id="dfb75-110">Cube</span></span>|<span data-ttu-id="dfb75-111">Куб для текущего контекста запросов.</span><span class="sxs-lookup"><span data-stu-id="dfb75-111">The cube for the current query context.</span></span>|  
|<span data-ttu-id="dfb75-112">**CurrentDatabaseName**</span><span class="sxs-lookup"><span data-stu-id="dfb75-112">**CurrentDatabaseName**</span></span>|<span data-ttu-id="dfb75-113">Строка</span><span class="sxs-lookup"><span data-stu-id="dfb75-113">String</span></span>|<span data-ttu-id="dfb75-114">Идентификатор текущей базы данных.</span><span class="sxs-lookup"><span data-stu-id="dfb75-114">The identifier of the current database.</span></span>|  
|<span data-ttu-id="dfb75-115">**CurrentConnection**</span><span class="sxs-lookup"><span data-stu-id="dfb75-115">**CurrentConnection**</span></span>|<span data-ttu-id="dfb75-116">Соединение</span><span class="sxs-lookup"><span data-stu-id="dfb75-116">Connection</span></span>|<span data-ttu-id="dfb75-117">Ссылка на объект подключения в текущем контексте.</span><span class="sxs-lookup"><span data-stu-id="dfb75-117">A reference to the connection object in the current context.</span></span>|  
|<span data-ttu-id="dfb75-118">**Успех**</span><span class="sxs-lookup"><span data-stu-id="dfb75-118">**Pass**</span></span>|<span data-ttu-id="dfb75-119">Целое число</span><span class="sxs-lookup"><span data-stu-id="dfb75-119">Integer</span></span>|<span data-ttu-id="dfb75-120">Номера прохода для текущего контекста.</span><span class="sxs-lookup"><span data-stu-id="dfb75-120">The pass number for the current context.</span></span>|  
  
 <span data-ttu-id="dfb75-121">Объект `Context` существует, когда модель объектов многомерных выражений используется в хранимой процедуре.</span><span class="sxs-lookup"><span data-stu-id="dfb75-121">The `Context` object exists when the Multidimensional Expressions (MDX) object model is used in a stored procedure.</span></span> <span data-ttu-id="dfb75-122">Он не доступен, когда модель объектов многомерных выражений используется на клиенте.</span><span class="sxs-lookup"><span data-stu-id="dfb75-122">It is not available when the MDX object model is used on a client.</span></span> <span data-ttu-id="dfb75-123">Объект `Context` не передается явным образом хранимой процедуре и не возвращается ею.</span><span class="sxs-lookup"><span data-stu-id="dfb75-123">The `Context` object is not explicitly passed to or returned by the stored procedure.</span></span> <span data-ttu-id="dfb75-124">Он доступен во время выполнения хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="dfb75-124">It is available during the execution of the stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfb75-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="dfb75-125">See Also</span></span>  
 <span data-ttu-id="dfb75-126">[Управление сборками многомерной модели](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="dfb75-126">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="dfb75-127">Определение хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="dfb75-127">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
