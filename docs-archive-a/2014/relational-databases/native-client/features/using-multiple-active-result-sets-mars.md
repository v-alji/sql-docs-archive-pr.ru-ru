---
title: Использование режима MARS | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, MARS
- SQLNCLI, MARS
- data access [SQL Server Native Client], MARS
- Multiple Active Result Sets
- SQL Server Native Client, MARS
- MARS [SQL Server]
- SQL Server Native Client ODBC driver, MARS
ms.assetid: ecfd9c6b-7d29-41d8-af2e-89d7fb9a1d83
author: rothja
ms.author: jroth
ms.openlocfilehash: 7119048df3de23b1cfc5d6c8fb41672d82be14f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666537"
---
# <a name="using-multiple-active-result-sets-mars"></a><span data-ttu-id="31ff5-102">Использование режима MARS</span><span class="sxs-lookup"><span data-stu-id="31ff5-102">Using Multiple Active Result Sets (MARS)</span></span>
  <span data-ttu-id="31ff5-103">В [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] была предусмотрена возможность работы с несколькими активными результирующими наборами (режим MARS) в приложениях, которые обращаются к компоненту [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31ff5-103">[!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] introduced support for multiple active result sets (MARS) in applications accessing the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span> <span data-ttu-id="31ff5-104">В более ранних версиях [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] приложения баз данных не могли поддерживать несколько активных инструкций во время соединения.</span><span class="sxs-lookup"><span data-stu-id="31ff5-104">In earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], database applications could not maintain multiple active statements on a connection.</span></span> <span data-ttu-id="31ff5-105">При использовании результирующих наборов [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], применяемых по умолчанию, приложение должно было обработать или отменить все результирующие наборы из одного пакета и только после этого приступать к обработке любого другого пакета данного соединения.</span><span class="sxs-lookup"><span data-stu-id="31ff5-105">When using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default result sets, the application had to process or cancel all result sets from one batch before it could execute any other batch on that connection.</span></span> <span data-ttu-id="31ff5-106">В версии [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] был реализован новый атрибут соединения, который позволяет приложениям сохранять более одного ожидающего выполнения запроса в расчете на соединение и, в частности, иметь более одного применяемого по умолчанию активного результирующего набора в расчете на одно соединение.</span><span class="sxs-lookup"><span data-stu-id="31ff5-106">[!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] introduced a new connection attribute that allows applications to have more than one pending request per connection, and in particular, to have more than one active default result set per connection.</span></span>  
  
 <span data-ttu-id="31ff5-107">Режим MARS упрощает проектирование приложений за счет использования следующих функций.</span><span class="sxs-lookup"><span data-stu-id="31ff5-107">MARS simplifies application design with the following new capabilities:</span></span>  
  
-   <span data-ttu-id="31ff5-108">У приложений может быть открыто несколько применяемых по умолчанию результирующих наборов; при этом приложения могут по очереди считывать из них данные.</span><span class="sxs-lookup"><span data-stu-id="31ff5-108">Applications can have multiple default result sets open and can interleave reading from them.</span></span>  
  
-   <span data-ttu-id="31ff5-109">Когда применяемые по умолчанию результирующие наборы открыты, приложения могут выполнять другие инструкции (например: INSERT, UPDATE, DELETE и вызовы хранимых процедур).</span><span class="sxs-lookup"><span data-stu-id="31ff5-109">Applications can execute other statements (for example, INSERT, UPDATE, DELETE, and stored procedure calls) while default result sets are open.</span></span>  
  
 <span data-ttu-id="31ff5-110">При работе с приложениями, предусматривающими функционирование в режиме MARS, полезно руководствоваться следующими рекомендациями.</span><span class="sxs-lookup"><span data-stu-id="31ff5-110">Applications using MARS will find the following guidelines beneficial:</span></span>  
  
-   <span data-ttu-id="31ff5-111">Результирующие наборы по умолчанию следует использовать с имеющими небольшой период жизни или с короткими результирующими наборами, сформированными при помощи одной инструкции SQL (SELECT, DML with OUTPUT, RECEIVE, READ TEXT и т. д.).</span><span class="sxs-lookup"><span data-stu-id="31ff5-111">Default results sets should be used for short lived or short result sets generated by single SQL statements (SELECT, DML with OUTPUT, RECEIVE, READ TEXT, and so on).</span></span>  
  
-   <span data-ttu-id="31ff5-112">Серверные курсоры нужно использовать с имеющими более длительный период жизни или с более крупными результирующими наборами, сформированными при помощи одной инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="31ff5-112">Server cursors should be used for longer lived or large result sets generated by single SQL statements.</span></span>  
  
-   <span data-ttu-id="31ff5-113">Результаты нужно всегда прочитывать до конца на предмет наличия в них процедурных запросов, вне зависимости от того, возвращают ли они результаты, и на предмет наличия в них пакетов, возвращающих несколько результатов.</span><span class="sxs-lookup"><span data-stu-id="31ff5-113">Always read to the end of results for procedural requests regardless of whether they return results or not, and for batches that return multiple results.</span></span>  
  
-   <span data-ttu-id="31ff5-114">По возможности для изменения свойств соединений и для управления транзакциями следует использовать не инструкции [!INCLUDE[tsql](../../../includes/tsql-md.md)], а вызовы API.</span><span class="sxs-lookup"><span data-stu-id="31ff5-114">Wherever possible, use API calls to change connection properties and manage transactions in preference to [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements.</span></span>  
  
-   <span data-ttu-id="31ff5-115">При работе в режиме MARS в ситуациях, когда выполняются параллельные пакеты, ограниченные областью сеанса олицетворения не допускаются.</span><span class="sxs-lookup"><span data-stu-id="31ff5-115">In MARS, session-scoped impersonation is prohibited while concurrent batches are running.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31ff5-116">По умолчанию функции режима MARS не активированы.</span><span class="sxs-lookup"><span data-stu-id="31ff5-116">By default, MARS functionality is not enabled.</span></span> <span data-ttu-id="31ff5-117">Чтобы использовать режим MARS при подключении [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] к собственному клиенту [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], необходимо явно задействовать его внутри строки соединения.</span><span class="sxs-lookup"><span data-stu-id="31ff5-117">To use MARS when connecting to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, you must specifically enable it within a connection string.</span></span> <span data-ttu-id="31ff5-118">Дополнительные сведения см. в подразделах «Поставщик OLE DB для собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]» и «Драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]» далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="31ff5-118">For more information, see the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver sections, later in this topic.</span></span>  
  
 <span data-ttu-id="31ff5-119">Собственный клиент [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] не ограничивает число активных инструкций в соединении.</span><span class="sxs-lookup"><span data-stu-id="31ff5-119">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client does not limit the number of active statements on a connection.</span></span>  
  
 <span data-ttu-id="31ff5-120">Типичные приложения, которые обходятся одновременным выполнением не более чем одного пакета из нескольких инструкций или одной хранимой процедуры, лучше запускать в режиме MARS; при этом они не обязательно должны понимать, как именно реализован режим MARS.</span><span class="sxs-lookup"><span data-stu-id="31ff5-120">Typical applications which do not need to have more than a single multistatement batch or stored procedure executing at the same time will benefit from MARS without having to understand how MARS is implemented.</span></span> <span data-ttu-id="31ff5-121">Однако приложения с более сложными требованиями должны принимать это во внимание.</span><span class="sxs-lookup"><span data-stu-id="31ff5-121">However, applications with more complex requirements do need to take account of this.</span></span>  
  
 <span data-ttu-id="31ff5-122">Режим MARS дает возможность поочередно выполнять несколько запросов с использованием одного соединения.</span><span class="sxs-lookup"><span data-stu-id="31ff5-122">MARS enables the interleaved execution of multiple requests within a single connection.</span></span> <span data-ttu-id="31ff5-123">Иначе говоря, существует возможность выполнения пакета с одновременным выполнением других запросов.</span><span class="sxs-lookup"><span data-stu-id="31ff5-123">That is, it allows a batch to run, and within its execution, it allows other requests to execute.</span></span> <span data-ttu-id="31ff5-124">Впрочем, надо отметить, что режим MARS определяется в терминах чередования, а не в терминах параллельного выполнения.</span><span class="sxs-lookup"><span data-stu-id="31ff5-124">Note, however, that MARS is defined in terms of interleaving, not in terms of parallel execution.</span></span>  
  
 <span data-ttu-id="31ff5-125">Инфраструктура режима MARS предоставляет возможность поочередного выполнения нескольких пакетов, хотя выполнение может переключаться лишь в четко определенных пунктах.</span><span class="sxs-lookup"><span data-stu-id="31ff5-125">The MARS infrastructure allows multiple batches to execute in an interleaved fashion, though execution can only be switched at well defined points.</span></span> <span data-ttu-id="31ff5-126">Кроме того, почти все инструкции должны выполняться атомарным образом внутри пакета.</span><span class="sxs-lookup"><span data-stu-id="31ff5-126">In addition, most statements must run atomically within a batch.</span></span> <span data-ttu-id="31ff5-127">Инструкции, которые возвращают строки клиенту, которые иногда называют *точками*получения, могут чередовать выполнение до завершения, пока строки отправляются клиенту, например:</span><span class="sxs-lookup"><span data-stu-id="31ff5-127">Statements which return rows to the client, which are sometimes referred to as *yield points*, are allowed to interleave execution before completion while rows are being sent to the client, for example:</span></span>  
  
-   <span data-ttu-id="31ff5-128">SELECT</span><span class="sxs-lookup"><span data-stu-id="31ff5-128">SELECT</span></span>  
  
-   <span data-ttu-id="31ff5-129">FETCH</span><span class="sxs-lookup"><span data-stu-id="31ff5-129">FETCH</span></span>  
  
-   <span data-ttu-id="31ff5-130">RECEIVE</span><span class="sxs-lookup"><span data-stu-id="31ff5-130">RECEIVE</span></span>  
  
 <span data-ttu-id="31ff5-131">Все иные инструкции, выполняемые как часть хранимой процедуры или пакета, должны выполняться до конца, и только после этого выполнение может быть передано другим запросам MARS.</span><span class="sxs-lookup"><span data-stu-id="31ff5-131">Any other statements that are executed as part of a stored procedure or batch must run to completion before execution can be switched to other MARS requests.</span></span>  
  
 <span data-ttu-id="31ff5-132">Точный порядок чередования выполнения пакетов определяется рядом факторов, поэтому предугадать точную последовательность выполнения содержащих точки выхода команд из нескольких пакетов затруднительно.</span><span class="sxs-lookup"><span data-stu-id="31ff5-132">The exact manner in which batches interleave execution is influenced by a number of factors, and it is difficult to predict the exact sequence in which commands from multiple batches that contain yield points will be executed.</span></span> <span data-ttu-id="31ff5-133">Необходимо проявлять осторожность, чтобы избегать нежелательных побочных эффектов, которые вызываются поочередным выполнением подобных сложных пакетов.</span><span class="sxs-lookup"><span data-stu-id="31ff5-133">Be careful to avoid unwanted side effects due to interleaved execution of such complex batches.</span></span>  
  
 <span data-ttu-id="31ff5-134">Вы сможете избежать проблем, если при управлении состоянием соединений (SET, USE) и транзакциями (BEGIN TRAN, COMMIT, ROLLBACK) будете использовать вызовы API, а не инструкции [!INCLUDE[tsql](../../../includes/tsql-md.md)], если не будете включать эти инструкции в пакеты из нескольких инструкций, также содержащие точки выхода, и если будете сериализовать выполнение таких пакетов посредством использования либо отмены всех результатов.</span><span class="sxs-lookup"><span data-stu-id="31ff5-134">Avoid problems by using API calls rather than [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements to manage connection state (SET, USE) and transactions (BEGIN TRAN, COMMIT, ROLLBACK) by not including these statements in multi-statement batches that also contain yield points, and by serializing execution of such batches by consuming or canceling all results.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31ff5-135">Пакет хранимых процедур, начинающий ручную или неявную транзакцию с активированным режимом MARS, должен завершать транзакцию до выхода пакета.</span><span class="sxs-lookup"><span data-stu-id="31ff5-135">A batch or stored procedure which starts a manual or implicit transaction when MARS is enabled must complete the transaction before the batch exits.</span></span> <span data-ttu-id="31ff5-136">В противном случае по завершении выполнения пакета [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] осуществляет откат всех изменений, внесенных транзакцией.</span><span class="sxs-lookup"><span data-stu-id="31ff5-136">If it does not, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] rolls back all changes made by the transaction when the batch finishes.</span></span> <span data-ttu-id="31ff5-137">Такая транзакция управляется [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] как транзакция контекста пакета.</span><span class="sxs-lookup"><span data-stu-id="31ff5-137">Such a transaction is managed by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as a batch-scoped transaction.</span></span> <span data-ttu-id="31ff5-138">Это новый тип транзакции, реализованный в [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] с тем, чтобы существующие верно выполняемые хранимые процедуры можно было использовать в режиме MARS.</span><span class="sxs-lookup"><span data-stu-id="31ff5-138">This is a new type of transaction introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] to enable existing well-behaved stored procedures to be used when MARS is enabled.</span></span> <span data-ttu-id="31ff5-139">Дополнительные сведения о транзакциях контекста пакета см. в статье [Инструкции Transact-SQL](/sql/t-sql/language-elements/transactions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="31ff5-139">For more information about batch-scoped transactions, see [Transaction Statements &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transactions-transact-sql).</span></span>  
  
 <span data-ttu-id="31ff5-140">Пример использования режима MARS из ADO см. в разделе [Использование ADO с SQL Server Native Client](../applications/using-ado-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="31ff5-140">For an example of using MARS from ADO, see [Using ADO with SQL Server Native Client](../applications/using-ado-with-sql-server-native-client.md).</span></span>  
  
## <a name="sql-server-native-client-ole-db-provider"></a><span data-ttu-id="31ff5-141">Поставщик OLE DB для собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="31ff5-141">SQL Server Native Client OLE DB Provider</span></span>  
 <span data-ttu-id="31ff5-142">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента поддерживает режим MARS с помощью добавления свойства инициализации источника данных SSPROP_INIT_MARSCONNECTION, реализованного в наборе свойств DBPROPSET_SQLSERVERDBINIT.</span><span class="sxs-lookup"><span data-stu-id="31ff5-142">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports MARS through the addition of the SSPROP_INIT_MARSCONNECTION data source initialization property, which is implemented in the DBPROPSET_SQLSERVERDBINIT property set.</span></span> <span data-ttu-id="31ff5-143">Кроме того, добавлено новое ключевое слово для строки соединения — `MarsConn`.</span><span class="sxs-lookup"><span data-stu-id="31ff5-143">In addition, a new connection string keyword, `MarsConn`, as been added.</span></span> <span data-ttu-id="31ff5-144">Оно принимает значения `true` или `false`; по умолчанию применяется значение `false`.</span><span class="sxs-lookup"><span data-stu-id="31ff5-144">It accepts `true` or `false` values; `false` is the default.</span></span>  
  
 <span data-ttu-id="31ff5-145">Для свойства источника данных DBPROP_MULTIPLECONNECTIONS по умолчанию применяется значение VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="31ff5-145">The data source property DBPROP_MULTIPLECONNECTIONS defaults to VARIANT_TRUE.</span></span> <span data-ttu-id="31ff5-146">Это значит, что поставщик создаст несколько соединений для поддержки ряда параллельных объектов команд и наборов строк.</span><span class="sxs-lookup"><span data-stu-id="31ff5-146">This means the provider will spawn multiple connections in order to support multiple concurrent command and rowset objects.</span></span> <span data-ttu-id="31ff5-147">Если включен режим MARS, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] собственный клиент может поддерживать несколько объектов команд и наборов строк в одном соединении, поэтому MULTIPLE_CONNECTIONS по умолчанию имеет значение VARIANT_FALSE.</span><span class="sxs-lookup"><span data-stu-id="31ff5-147">When MARS is enabled, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client can support multiple command and rowset objects on a single connection, so MULTIPLE_CONNECTIONS is set to VARIANT_FALSE by default.</span></span>  
  
 <span data-ttu-id="31ff5-148">Дополнительные сведения об улучшениях, появившихся в наборе свойств DBPROPSET_SQLSERVERDBINIT, см. в статье [Initialization and Authorization Properties](../../native-client-ole-db-data-source-objects/initialization-and-authorization-properties.md) (Свойства инициализации и авторизации).</span><span class="sxs-lookup"><span data-stu-id="31ff5-148">For more information about enhancements made to the DBPROPSET_SQLSERVERDBINIT property set, see [Initialization and Authorization Properties](../../native-client-ole-db-data-source-objects/initialization-and-authorization-properties.md).</span></span>  
  
### <a name="sql-server-native-client-ole-db-provider-example"></a><span data-ttu-id="31ff5-149">Пример поставщика OLE DB для собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="31ff5-149">SQL Server Native Client OLE DB Provider Example</span></span>  
 <span data-ttu-id="31ff5-150">В этом примере объект источника данных создается с помощью [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] собственного поставщика OLE DB, а режим MARS включается с помощью свойства DBPROPSET_SQLSERVERDBINIT, установленного перед созданием объекта Session.</span><span class="sxs-lookup"><span data-stu-id="31ff5-150">In this example, a data source object is created using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native OLE DB provider, and MARS is enabled using the DBPROPSET_SQLSERVERDBINIT property set before the session object is created.</span></span>  
  
```  
#include <sqlncli.h>  
  
IDBInitialize *pIDBInitialize = NULL;  
IDBCreateSession *pIDBCreateSession = NULL;  
IDBProperties *pIDBProperties = NULL;  
  
// Create the data source object.  
hr = CoCreateInstance(CLSID_SQLNCLI10, NULL,  
   CLSCTX_INPROC_SERVER,  
   IID_IDBInitialize,   
    (void**)&pIDBInitialize);  
  
hr = pIDBInitialize->QueryInterface(IID_IDBProperties, (void**)&pIDBProperties);  
  
// Set the MARS property.  
DBPROP rgPropMARS;  
  
// The following is necessary since MARS is off by default.  
rgPropMARS.dwPropertyID = SSPROP_INIT_MARSCONNECTION;  
rgPropMARS.dwOptions = DBPROPOPTIONS_REQUIRED;  
rgPropMARS.dwStatus = DBPROPSTATUS_OK;  
rgPropMARS.colid = DB_NULLID;  
V_VT(&(rgPropMARS.vValue)) = VT_BOOL;  
V_BOOL(&(rgPropMARS.vValue)) = VARIANT_TRUE;  
  
// Create the structure containing the properties.  
DBPROPSET PropSet;  
PropSet.rgProperties = &rgPropMARS;  
PropSet.cProperties = 1;  
PropSet.guidPropertySet = DBPROPSET_SQLSERVERDBINIT;  
  
// Get an IDBProperties pointer and set the initialization properties.  
pIDBProperties->SetProperties(1, &PropSet);  
pIDBProperties->Release();  
  
// Initialize the data source object.  
hr = pIDBInitialize->Initialize();  
  
//Create a session object from a data source object.  
IOpenRowset * pIOpenRowset = NULL;  
hr = IDBInitialize->QueryInterface(IID_IDBCreateSession, (void**)&pIDBCreateSession));  
hr = pIDBCreateSession->CreateSession(  
   NULL,             // pUnkOuter  
   IID_IOpenRowset,  // riid  
  &pIOpenRowset ));  // ppSession  
  
// Create a rowset with a firehose mode cursor.  
IRowset *pIRowset = NULL;  
DBPROP rgRowsetProperties[2];  
  
// To get a firehose mode cursor request a   
// forward only read only rowset.  
rgRowsetProperties[0].dwPropertyID = DBPROP_IRowsetLocate;  
rgRowsetProperties[0].dwOptions = DBPROPOPTIONS_REQUIRED;  
rgRowsetProperties[0].dwStatus = DBPROPSTATUS_OK;  
rgRowsetProperties[0].colid = DB_NULLID;  
VariantInit(&(rgRowsetProperties[0].vValue));  
rgRowsetProperties[0].vValue.vt = VARIANT_BOOL;  
rgRowsetProperties[0].vValue.boolVal = VARIANT_FALSE;  
  
rgRowsetProperties[1].dwPropertyID = DBPROP_IRowsetChange;  
rgRowsetProperties[1].dwOptions = DBPROPOPTIONS_REQUIRED;  
rgRowsetProperties[1].dwStatus = DBPROPSTATUS_OK;  
rgRowsetProperties[1].colid = DB_NULLID;  
VariantInit(&(rgRowsetProperties[1].vValue));  
rgRowsetProperties[1].vValue.vt = VARIANT_BOOL;  
rgRowsetProperties[1].vValue.boolVal = VARIANT_FALSE;  
  
DBPROPSET rgRowsetPropSet[1];  
rgRowsetPropSet[0].rgProperties = rgRowsetProperties  
rgRowsetPropSet[0].cProperties = 2  
rgRowsetPropSet[0].guidPropertySet = DBPROPSET_ROWSET;  
  
hr = pIOpenRowset->OpenRowset (NULL,  
   &TableID,  
   NULL,  
   IID_IRowset,  
   1,  
   rgRowsetPropSet  
   (IUnknown**)&pIRowset);  
```  
  
## <a name="sql-server-native-client-odbc-driver"></a><span data-ttu-id="31ff5-151">Драйвер ODBC для собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="31ff5-151">SQL Server Native Client ODBC Driver</span></span>  
 <span data-ttu-id="31ff5-152">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента поддерживает режим MARS посредством дополнений к функциям [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) и [SQLGetConnectAttr](../../native-client-odbc-api/sqlgetconnectattr.md) .</span><span class="sxs-lookup"><span data-stu-id="31ff5-152">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports MARS through additions to the [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) and [SQLGetConnectAttr](../../native-client-odbc-api/sqlgetconnectattr.md) functions.</span></span> <span data-ttu-id="31ff5-153">Добавление SQL_COPT_SS_MARS_ENABLED выполнено, чтобы принять значение SQL_MARS_ENABLED_YES или SQL_MARS_ENABLED_NO; по умолчанию принимается значение SQL_MARS_ENABLED_NO.</span><span class="sxs-lookup"><span data-stu-id="31ff5-153">SQL_COPT_SS_MARS_ENABLED has been added to accept either SQL_MARS_ENABLED_YES or SQL_MARS_ENABLED_NO, with SQL_MARS_ENABLED_NO being the default.</span></span> <span data-ttu-id="31ff5-154">Кроме того, добавлено новое ключевое слово для строки соединения — `Mars_Connection`.</span><span class="sxs-lookup"><span data-stu-id="31ff5-154">In addition, a new connection string keyword, `Mars_Connection`, as been added.</span></span> <span data-ttu-id="31ff5-155">Оно принимает значения «да» или «нет»; по умолчанию принимается значение «нет».</span><span class="sxs-lookup"><span data-stu-id="31ff5-155">It accepts "yes" or "no" values; "no" is the default.</span></span>  
  
### <a name="sql-server-native-client-odbc-driver-example"></a><span data-ttu-id="31ff5-156">Пример драйвера ODBC для собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="31ff5-156">SQL Server Native Client ODBC Driver Example</span></span>  
 <span data-ttu-id="31ff5-157">В этом примере функция **SQLSetConnectAttr** используется для включения режима MARS перед вызовом функции **SQLDriverConnect** для подключения базы данных.</span><span class="sxs-lookup"><span data-stu-id="31ff5-157">In this example, the **SQLSetConnectAttr** function is used to enable MARS before calling the **SQLDriverConnect** function to connect the database.</span></span> <span data-ttu-id="31ff5-158">После установки соединения вызываются две функции **SQLExecDirect** для создания двух отдельных результирующих наборов в одном соединении.</span><span class="sxs-lookup"><span data-stu-id="31ff5-158">Once the connection is made, two **SQLExecDirect** functions are called to create two separate result sets on the same connection.</span></span>  
  
```  
#include <sqlncli.h>  
  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_MARS_ENABLED, SQL_MARS_ENABLED_YES, SQL_IS_UINTEGER);  
SQLDriverConnect(hdbc, hwnd,   
   "DRIVER=SQL Server Native Client 10.0;  
   SERVER=(local);trusted_connection=yes;", SQL_NTS, szOutConn,   
   MAX_CONN_OUT, &cbOutConn, SQL_DRIVER_COMPLETE);  
  
SQLAllocHandle(SQL_HANDLE_STMT, hdbc, &hstmt1);  
SQLAllocHandle(SQL_HANDLE_STMT, hdbc, &hstmt2);  
  
// The 2nd execute would have failed with connection busy error if  
// MARS were not enabled.  
SQLExecDirect(hstmt1, L"SELECT * FROM Authors", SQL_NTS);  
SQLExecDirect(hstmt2, L"SELECT * FROM Titles", SQL_NTS);  
  
// Result set processing can interleave.  
SQLFetch(hstmt1);  
SQLFetch(hstmt2);  
```  
  
## <a name="see-also"></a><span data-ttu-id="31ff5-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="31ff5-159">See Also</span></span>  
 <span data-ttu-id="31ff5-160">[Компоненты собственного клиента SQL Server](sql-server-native-client-features.md) </span><span class="sxs-lookup"><span data-stu-id="31ff5-160">[SQL Server Native Client Features](sql-server-native-client-features.md) </span></span>  
 [<span data-ttu-id="31ff5-161">Использование результирующих наборов по умолчанию в SQL Server</span><span class="sxs-lookup"><span data-stu-id="31ff5-161">Using SQL Server Default Result Sets</span></span>](../../native-client-odbc-cursors/implementation/using-sql-server-default-result-sets.md)  
  
  
