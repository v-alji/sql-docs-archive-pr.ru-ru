---
title: MSSQLSERVER_1793 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: 808db1d0-acc1-41d0-9287-8a5455001a02
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 54172adb957c3cbc1dbc221d1cae2a583830a1cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731669"
---
# <a name="mssqlserver_1793"></a><span data-ttu-id="4834b-102">MSSQLSERVER_1793</span><span class="sxs-lookup"><span data-stu-id="4834b-102">MSSQLSERVER_1793</span></span>
    
## <a name="details"></a><span data-ttu-id="4834b-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="4834b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4834b-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="4834b-104">Product Name</span></span>|<span data-ttu-id="4834b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4834b-105">SQL Server</span></span>|  
|<span data-ttu-id="4834b-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="4834b-106">Event ID</span></span>|<span data-ttu-id="4834b-107">1793</span><span class="sxs-lookup"><span data-stu-id="4834b-107">1793</span></span>|  
|<span data-ttu-id="4834b-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="4834b-108">Event Source</span></span>|<span data-ttu-id="4834b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4834b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4834b-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="4834b-110">Component</span></span>|<span data-ttu-id="4834b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4834b-111">SQLEngine</span></span>|  
|<span data-ttu-id="4834b-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="4834b-112">Symbolic Name</span></span>|<span data-ttu-id="4834b-113">FILESTREAM_BASEDATA_NEED_SAME_PARTITION</span><span class="sxs-lookup"><span data-stu-id="4834b-113">FILESTREAM_BASEDATA_NEED_SAME_PARTITION</span></span>|  
|<span data-ttu-id="4834b-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="4834b-114">Message Text</span></span>|<span data-ttu-id="4834b-115">Не удается удалить «%.\*ls», поскольку для данных FILESTREAM не указана схема секционирования.</span><span class="sxs-lookup"><span data-stu-id="4834b-115">Cannot drop index '%.\*ls' since a partition scheme is not specified for FILESTREAM data.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4834b-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="4834b-116">Explanation</span></span>  
 <span data-ttu-id="4834b-117">Это сообщение возникает при попытке удалить кластеризованный индекс для таблицы, которая содержит данные FILESTREAM, указав предложение **MOVE TO** для базовых данных, но не указав предложение **FILESTREAM_ON** для данных FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="4834b-117">This message occurs when you try to drop a clustered index on a table that contains FILESTREAM data, and you specify a **MOVE TO** clause for the base data, but you do not specify a **FILESTREAM_ON** clause for the FILESTREAM data.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4834b-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="4834b-118">User Action</span></span>  
 <span data-ttu-id="4834b-119">При удалении кластеризованного индекса для таблицы, которая содержит данные FILESTREAM, используйте один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="4834b-119">When dropping a clustered index on a table that contains FILESTREAM data, use one of the following options:</span></span>  
  
-   <span data-ttu-id="4834b-120">Укажите оба предложения: **MOVE TO** для базовых данных и **FILESTREAM_ON** для данных FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="4834b-120">Specify both a **MOVE TO** clause for the base data and a **FILESTREAM_ON** clause for the FILESTREAM data.</span></span>  
  
-   <span data-ttu-id="4834b-121">Не указывайте ни одно из предложений **MOVE TO** для базовых данных или **FILESTREAM_ON** для данных FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="4834b-121">Do not specify either a **MOVE TO** clause for the base data or a **FILESTREAM_ON** clause for the FILESTREAM data.</span></span>  
  
 <span data-ttu-id="4834b-122">Следующий пример заканчивается ошибкой, потому что схема секционирования указана для базовых данных, но не указана для данных FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="4834b-122">The following example fails because a partition scheme is specified for the base data, but is not specified for the FILESTREAM data.</span></span>  
  
```sql  
DROP INDEX [<clustered_index_name>] ON [<table_name>]   
WITH ( ONLINE = OFF, MOVE TO [PRIMARY] )  
GO  
```  
  
 <span data-ttu-id="4834b-123">Следующий пример завершается успешно, так как для базовых данных указано предложение **MOVE TO**, а для данных FILESTREAM — предложение **FILESTREAM_ON**.</span><span class="sxs-lookup"><span data-stu-id="4834b-123">The following example succeeds because both a **MOVE TO** clause for the base data and a **FILESTREAM_ON** clause for the FILESTREAM data are specified.</span></span>  
  
```sql  
DROP INDEX [<clustered_index_name>] ON [<table_name>]   
WITH ( ONLINE = OFF, MOVE TO [PRIMARY], filestream_on 'default' )  
GO  
```  
  
 <span data-ttu-id="4834b-124">Следующий пример также завершается успешно, так как не указано ни одно из предложений: **MOVE TO** для базовых данных или **FILESTREAM_ON** для данных FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="4834b-124">The following example also succeeds because neither a **MOVE TO** clause for the base data nor a **FILESTREAM_ON** clause for the FILESTREAM data is specified.</span></span>  
  
```sql  
DROP INDEX [<clustered_index_name>] ON [<table_name>]   
WITH ( ONLINE = OFF )  
GO  
```  
  
  
