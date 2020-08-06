---
title: Другие подписчики, отличные от подписчиков SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- non-SQL Server Subscribers, other types
ms.assetid: 96b8beb9-38e8-4ce4-97ca-c0f8656b73b4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3849ca717e82bcf1bed5769190c9f898209a454a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654160"
---
# <a name="other-non-sql-server-subscribers"></a><span data-ttu-id="4ca8c-102">Другие подписчики, отличные от SQL Server</span><span class="sxs-lookup"><span data-stu-id="4ca8c-102">Other Non-SQL Server Subscribers</span></span>
  <span data-ttu-id="4ca8c-103"> Список подписчиков, не относящихся к [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и поддерживаемых [!INCLUDE[msCoName](../../../includes/msconame-md.md)], см. в разделе [Подписчики, отличные от подписчиков SQL Server](non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="4ca8c-103">For a list of non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers supported by [!INCLUDE[msCoName](../../../includes/msconame-md.md)], see [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span></span> <span data-ttu-id="4ca8c-104">В данном разделе содержатся сведения о требованиях к драйверам ODBC и поставщикам OLE DB.</span><span class="sxs-lookup"><span data-stu-id="4ca8c-104">This topic includes information about requirements for ODBC drivers and OLE DB providers.</span></span>  
  
## <a name="odbc-driver-requirements"></a><span data-ttu-id="4ca8c-105">Требования к драйверам ODBC</span><span class="sxs-lookup"><span data-stu-id="4ca8c-105">ODBC Driver Requirements</span></span>  
 <span data-ttu-id="4ca8c-106">Драйвер ODBC:</span><span class="sxs-lookup"><span data-stu-id="4ca8c-106">The ODBC driver:</span></span>  
  
-   <span data-ttu-id="4ca8c-107">Должен соответствовать уровню 1 ODBC.</span><span class="sxs-lookup"><span data-stu-id="4ca8c-107">Must be ODBC level-1 compliant.</span></span>  
  
-   <span data-ttu-id="4ca8c-108">Должен быть поточно-защищенным и предназначаться для процессорной архитектуры (Intel или Alpha) и платформы (32-разрядной или 64-разрядной), на которой выполняется распространитель [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ca8c-108">Must be thread-safe, and for the processor architecture (Intel or Alpha) and platform (32 bit or 64 bit) on which the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Distributor runs.</span></span>  
  
-   <span data-ttu-id="4ca8c-109">Должен поддерживать транзакции.</span><span class="sxs-lookup"><span data-stu-id="4ca8c-109">Must be transaction capable.</span></span>  
  
-   <span data-ttu-id="4ca8c-110">Должен поддерживать язык описания данных (Data Definition Language, DDL).</span><span class="sxs-lookup"><span data-stu-id="4ca8c-110">Must support the Data Definition Language (DDL).</span></span>  
  
-   <span data-ttu-id="4ca8c-111">Не может быть доступным только для чтения.</span><span class="sxs-lookup"><span data-stu-id="4ca8c-111">Cannot be read-only.</span></span>  
  
-   <span data-ttu-id="4ca8c-112">Должен поддерживать длинные имена таблиц, такие, как **MSreplication_subscriptions**.</span><span class="sxs-lookup"><span data-stu-id="4ca8c-112">Must support long table names such as **MSreplication_subscriptions**.</span></span>  
  
## <a name="replicating-using-ole-db-interfaces"></a><span data-ttu-id="4ca8c-113">Репликация при помощи интерфейсов OLE DB</span><span class="sxs-lookup"><span data-stu-id="4ca8c-113">Replicating Using OLE DB Interfaces</span></span>  
 <span data-ttu-id="4ca8c-114">Поставщики OLE DB должны поддерживать эти объекты для репликации транзакций:</span><span class="sxs-lookup"><span data-stu-id="4ca8c-114">OLE DB providers must support these objects for transactional replication:</span></span>  
  
-   <span data-ttu-id="4ca8c-115">объект**DataSource**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-115">**DataSource** object</span></span>  
  
-   <span data-ttu-id="4ca8c-116">объект**Session**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-116">**Session** object</span></span>  
  
-   <span data-ttu-id="4ca8c-117">объект**Command**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-117">**Command** object</span></span>  
  
-   <span data-ttu-id="4ca8c-118">объект**Rowset**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-118">**Rowset** object</span></span>  
  
-   <span data-ttu-id="4ca8c-119">объект**Error**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-119">**Error** object</span></span>  
  
### <a name="datasource-object-interfaces"></a><span data-ttu-id="4ca8c-120">Интерфейсы объекта DataSource</span><span class="sxs-lookup"><span data-stu-id="4ca8c-120">DataSource Object Interfaces</span></span>  
 <span data-ttu-id="4ca8c-121">Необходимы следующие интерфейсы для подключения к источнику данных:</span><span class="sxs-lookup"><span data-stu-id="4ca8c-121">The following interfaces are required to connect to a data source:</span></span>  
  
-   `IDBInitialize`  
  
-   `IDBCreateSession`  
  
-   `IDBProperties`  
  
 <span data-ttu-id="4ca8c-122">Если поставщик поддерживает интерфейс **IDBInfo**, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] использует интерфейс для получения сведений, таких как символ-идентификатор в кавычках, максимальная длина инструкции SQL, а также максимальное число символов в именах таблиц и столбцов.</span><span class="sxs-lookup"><span data-stu-id="4ca8c-122">If the provider supports the **IDBInfo** interface, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uses the interface to retrieve information such as the quoted identifier character, maximum SQL statement length, and maximum number of characters in table and column names.</span></span>  
  
### <a name="session-object-interfaces"></a><span data-ttu-id="4ca8c-123">Интерфейсы объекта Session</span><span class="sxs-lookup"><span data-stu-id="4ca8c-123">Session Object Interfaces</span></span>  
 <span data-ttu-id="4ca8c-124">Требуются следующие интерфейсы:</span><span class="sxs-lookup"><span data-stu-id="4ca8c-124">The following interfaces are required:</span></span>  
  
-   <span data-ttu-id="4ca8c-125">**IDBCreateCommand**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-125">**IDBCreateCommand**</span></span>  
  
-   <span data-ttu-id="4ca8c-126">**ITransaction**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-126">**ITransaction**</span></span>  
  
-   <span data-ttu-id="4ca8c-127">**ITransactionLocal**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-127">**ITransactionLocal**</span></span>  
  
-   <span data-ttu-id="4ca8c-128">**IDBSchemaRowset**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-128">**IDBSchemaRowset**</span></span>  
  
### <a name="command-object-interfaces"></a><span data-ttu-id="4ca8c-129">Интерфейсы объекта Command</span><span class="sxs-lookup"><span data-stu-id="4ca8c-129">Command Object Interfaces</span></span>  
 <span data-ttu-id="4ca8c-130">Требуются следующие интерфейсы:</span><span class="sxs-lookup"><span data-stu-id="4ca8c-130">The following interfaces are required:</span></span>  
  
-   <span data-ttu-id="4ca8c-131">**ICommand**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-131">**ICommand**</span></span>  
  
-   <span data-ttu-id="4ca8c-132">**ICommandProperties**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-132">**ICommandProperties**</span></span>  
  
-   <span data-ttu-id="4ca8c-133">**ICommandText**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-133">**ICommandText**</span></span>  
  
-   <span data-ttu-id="4ca8c-134">**ICommandPrepare**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-134">**ICommandPrepare**</span></span>  
  
-   <span data-ttu-id="4ca8c-135">**IColumnsInfo**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-135">**IColumnsInfo**</span></span>  
  
-   <span data-ttu-id="4ca8c-136">**IAccessor**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-136">**IAccessor**</span></span>  
  
-   <span data-ttu-id="4ca8c-137">**ICommandWithParameters**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-137">**ICommandWithParameters**</span></span>  
  
 <span data-ttu-id="4ca8c-138">**IAccessor** необходим для создания методов доступа к параметрам.</span><span class="sxs-lookup"><span data-stu-id="4ca8c-138">**IAccessor** is necessary to create parameter accessors.</span></span> <span data-ttu-id="4ca8c-139">Если поставщик поддерживает **иколумнровсет**, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] использует этот интерфейс для определения того, является ли столбец столбцом идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="4ca8c-139">If the provider supports **IColumnRowset**, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uses that interface to determine whether a column is an identity column.</span></span>  
  
### <a name="rowset-object-interfaces"></a><span data-ttu-id="4ca8c-140">Интерфейсы объекта Rowset</span><span class="sxs-lookup"><span data-stu-id="4ca8c-140">Rowset Object Interfaces</span></span>  
 <span data-ttu-id="4ca8c-141">Требуются следующие интерфейсы:</span><span class="sxs-lookup"><span data-stu-id="4ca8c-141">The following interfaces are required:</span></span>  
  
-   <span data-ttu-id="4ca8c-142">**IRowset**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-142">**IRowset**</span></span>  
  
-   <span data-ttu-id="4ca8c-143">**IAccessor**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-143">**IAccessor**</span></span>  
  
-   <span data-ttu-id="4ca8c-144">**IColumnsInfo**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-144">**IColumnsInfo**</span></span>  
  
 <span data-ttu-id="4ca8c-145">Приложение должно открыть набор строк в реплицированной таблице, которая создается в базе данных подписки.</span><span class="sxs-lookup"><span data-stu-id="4ca8c-145">An application should open a rowset on a replicated table that is created in the subscription database.</span></span> <span data-ttu-id="4ca8c-146">Интерфейсы**IColumnsInfo** и **IAccessor** необходимы для доступа к данным в наборе строк.</span><span class="sxs-lookup"><span data-stu-id="4ca8c-146">**IColumnsInfo** and **IAccessor** are needed to access data in the rowset.</span></span>  
  
### <a name="error-object-interfaces"></a><span data-ttu-id="4ca8c-147">Интерфейсы объекта Error</span><span class="sxs-lookup"><span data-stu-id="4ca8c-147">Error Object Interfaces</span></span>  
 <span data-ttu-id="4ca8c-148">Используйте следующие интерфейсы для управления ошибками:</span><span class="sxs-lookup"><span data-stu-id="4ca8c-148">Use the following interfaces to manage errors:</span></span>  
  
-   <span data-ttu-id="4ca8c-149">**IErrorRecords**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-149">**IErrorRecords**</span></span>  
  
-   <span data-ttu-id="4ca8c-150">**IErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="4ca8c-150">**IErrorInfo**</span></span>  
  
 <span data-ttu-id="4ca8c-151">Используйте интерфейс **ISQLErrorInfo** , если он поддерживается поставщиком OLE DB.</span><span class="sxs-lookup"><span data-stu-id="4ca8c-151">Use **ISQLErrorInfo** if it is supported by the OLE DB provider.</span></span>  
  
 <span data-ttu-id="4ca8c-152">Дополнительные сведения о поставщике OLE DB см. в документации, поставляемой с используемым поставщиком OLE DB.</span><span class="sxs-lookup"><span data-stu-id="4ca8c-152">For more information about the OLE DB provider, see the documentation supplied with your OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca8c-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="4ca8c-153">See Also</span></span>  
 [<span data-ttu-id="4ca8c-154">Подписчики, отличные от подписчиков SQL Server</span><span class="sxs-lookup"><span data-stu-id="4ca8c-154">Non-SQL Server Subscribers</span></span>](non-sql-server-subscribers.md)  
  
  
