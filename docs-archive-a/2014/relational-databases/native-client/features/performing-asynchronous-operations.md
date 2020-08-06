---
title: Выполнение асинхронных операций | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- initialization [SQL Server Native Client]
- database connections [SQL Server Native Client]
- data access [SQL Server Native Client], asynchronous operations
- connections [SQL Server Native Client]
- asynchronous operations [SQL Server Native Client]
- rowsets [SQL Server], initializing
- SQLNCLI, asynchronous operations
- SQL Server Native Client, asynchronous operations
ms.assetid: 8fbd84b4-69cb-4708-9f0f-bbdf69029bcc
author: rothja
ms.author: jroth
ms.openlocfilehash: 4f7e8f4481923cd7da537f921248865d4fff7280
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730582"
---
# <a name="performing-asynchronous-operations"></a><span data-ttu-id="b3e7b-102">Выполнение асинхронных операций</span><span class="sxs-lookup"><span data-stu-id="b3e7b-102">Performing Asynchronous Operations</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="b3e7b-103">позволяет приложениям выполнять асинхронные операции с базой данных.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-103">allows applications to perform asynchronous database operations.</span></span> <span data-ttu-id="b3e7b-104">Асинхронная обработка позволяет выполнять возврат из методов немедленно, не блокируя вызывающий поток.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-104">Asynchronous processing enables methods to return immediately without blocking on the calling thread.</span></span> <span data-ttu-id="b3e7b-105">Это позволяет использовать значительную часть мощности и гибкости многопотоковой обработки, и разработчику при этом не требуется явно создавать потоки или обрабатывать синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-105">This allows much of the power and flexibility of multithreading, without requiring the developer to explicitly create threads or handle synchronization.</span></span> <span data-ttu-id="b3e7b-106">Приложения запрашивают асинхронную обработку при инициализации подключения к базе данных или при инициализации результата выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-106">Applications request asynchronous processing when initializing a database connection, or when initializing the result from the execution of a command.</span></span>  
  
## <a name="opening-and-closing-a-database-connection"></a><span data-ttu-id="b3e7b-107">Открытие и закрытие подключения к базе данных</span><span class="sxs-lookup"><span data-stu-id="b3e7b-107">Opening and Closing a Database Connection</span></span>  
 <span data-ttu-id="b3e7b-108">При использовании [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] поставщика собственного клиента OLE DB приложения, предназначенные для асинхронной инициализации объекта источника данных, могут установить DBPROPVAL_ASYNCH_INITIALIZE бит в свойстве DBPROP_INIT_ASYNCH до вызова **IDBInitialize:: Initialize**.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-108">When using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, applications designed to initialize a data source object asynchronously can set the DBPROPVAL_ASYNCH_INITIALIZE bit in the DBPROP_INIT_ASYNCH property prior to calling **IDBInitialize::Initialize**.</span></span> <span data-ttu-id="b3e7b-109">Когда это свойство задано, поставщик обеспечивает немедленный возврат из метода **Initialize** с результатом S_OK, если операция была завершена немедленно, или DB_S_ASYNCHRONOUS, если инициализация продолжается асинхронно.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-109">When this property is set, the provider returns immediately from the call to **Initialize** with either S_OK, if the operation has completed immediately, or DB_S_ASYNCHRONOUS, if the initialization is continuing asynchronously.</span></span> <span data-ttu-id="b3e7b-110">Приложения могут запрашивать интерфейс **IDBAsynchStatus** или [метод ISSAsynchStatus](../../native-client-ole-db-interfaces/issasynchstatus-ole-db.md)для объекта источника данных, а затем вызывать **IDBAsynchStatus::** GetObject или[метод ISSAsynchStatus:: WaitForAsynchCompletion](../../native-client-ole-db-interfaces/issasynchstatus-waitforasynchcompletion-ole-db.md) для получения состояния инициализации.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-110">Applications can query for the **IDBAsynchStatus** or [ISSAsynchStatus](../../native-client-ole-db-interfaces/issasynchstatus-ole-db.md)interface on the data source object, and then call **IDBAsynchStatus::GetStatus** or[ISSAsynchStatus::WaitForAsynchCompletion](../../native-client-ole-db-interfaces/issasynchstatus-waitforasynchcompletion-ole-db.md) to get the status of the initialization.</span></span>  
  
 <span data-ttu-id="b3e7b-111">Кроме того, в набор свойств DBPROPSET_SQLSERVERROWSET добавлено свойство SSPROP_ISSAsynchStatus.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-111">In addition, the SSPROP_ISSAsynchStatus property has been added to the DBPROPSET_SQLSERVERROWSET property set.</span></span> <span data-ttu-id="b3e7b-112">Поставщики, поддерживающие интерфейс **ISSAsynchStatus**, должны реализовывать это свойство со значением VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-112">Providers that support the **ISSAsynchStatus** interface must implement this property with a value of VARIANT_TRUE.</span></span>  
  
 <span data-ttu-id="b3e7b-113">Функции **IDBAsynchStatus::Abort** и [ISSAsynchStatus::Abort](../../native-client-ole-db-interfaces/issasynchstatus-abort-ole-db.md) могут быть вызваны для отмены асинхронного вызова **Initialize**.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-113">**IDBAsynchStatus::Abort** or [ISSAsynchStatus::Abort](../../native-client-ole-db-interfaces/issasynchstatus-abort-ole-db.md) can be called to cancel the asynchronous **Initialize** call.</span></span> <span data-ttu-id="b3e7b-114">Потребитель должен явно запросить асинхронную инициализацию источника данных.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-114">The consumer must explicitly request Asynchronous Data Source Initialization.</span></span> <span data-ttu-id="b3e7b-115">В противном случае возврат из метода **IDBInitialize::Initialize** не происходит до тех пор, пока объект источника данных не будет инициализирован полностью.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-115">Otherwise, **IDBInitialize::Initialize** does not return until the data source object is completely initialized.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3e7b-116">Объекты источника данных, используемые для объединения соединений, не могут вызывать интерфейс **метод ISSAsynchStatus** в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] собственном клиенте OLE DB Provider.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-116">Data source objects used for connection pooling cannot call the **ISSAsynchStatus** interface in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="b3e7b-117">Интерфейс **ISSAsynchStatus** недоступен для объединенных в пул объектов источников данных.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-117">The **ISSAsynchStatus** interface is not exposed for pooled data source objects.</span></span>  
>   
>  <span data-ttu-id="b3e7b-118">Если приложение явно и принудительно использует ядро курсора, методы **IOpenRowset::OpenRowset** и **IMultipleResults::GetResult** не будут поддерживать асинхронную обработку.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-118">If an application explicitly forces use of the cursor engine, **IOpenRowset::OpenRowset** and **IMultipleResults::GetResult** will not support asynchronous processing.</span></span>  
>   
>  <span data-ttu-id="b3e7b-119">Кроме того, прокси-сервер удаленного взаимодействия или библиотека DLL заглушки (в MDAC 2,8) не могут вызывать интерфейс **метод ISSAsynchStatus** в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] собственном клиенте.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-119">In addition, the remoting proxy/stub dll (in MDAC 2.8) cannot call the **ISSAsynchStatus** interface in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="b3e7b-120">Интерфейс **ISSAsynchStatus** недоступен при удаленном взаимодействии.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-120">The **ISSAsynchStatus** interface is not exposed through remoting.</span></span>  
>   
>  <span data-ttu-id="b3e7b-121">Компоненты служб не поддерживают интерфейс **ISSAsynchStatus**.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-121">Service Components do not support **ISSAsynchStatus**.</span></span>  
  
## <a name="execution-and-rowset-initialization"></a><span data-ttu-id="b3e7b-122">Выполнение и инициализация наборов строк</span><span class="sxs-lookup"><span data-stu-id="b3e7b-122">Execution and Rowset Initialization</span></span>  
 <span data-ttu-id="b3e7b-123">Приложения, способные асинхронно открывать результаты выполнения команд, могут установить бит DBPROPVAL_ASYNCH_INITIALIZE в свойстве DBPROP_ROWSET_ASYNCH.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-123">Applications designed to asynchronously open the result from the execution of a command can set the DBPROPVAL_ASYNCH_INITIALIZE bit in the DBPROP_ROWSET_ASYNCH property.</span></span> <span data-ttu-id="b3e7b-124">Если задать этот бит перед вызовом **IDBInitialize::Initialize**, **ICommand::Execute**, **IOpenRowset::OpenRowset** или **IMultipleResults::GetResult**, значение аргумента *riid* должно быть IID_IDBAsynchStatus, IID_ISSAsynchStatus или IID_IUnknown.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-124">When setting this bit prior to calling **IDBInitialize::Initialize**, **ICommand::Execute**, **IOpenRowset::OpenRowset** or **IMultipleResults::GetResult**, the *riid* argument must be set to IID_IDBAsynchStatus, IID_ISSAsynchStatus, or IID_IUnknown.</span></span>  
  
 <span data-ttu-id="b3e7b-125">Метод возвращается немедленно с результатом S_OK, если инициализация набора строк завершается немедленно, или с результатом DB_S_ASYNCHRONOUS, если инициализация набора строк продолжается асинхронно, а параметр *ppRowset* указывает запрошенный интерфейс для набора строк.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-125">The method returns immediately with S_OK if the rowset initialization completes immediately, or with DB_S_ASYNCHRONOUS if the rowset continues initializing asynchronously, with *ppRowset* set to the requested interface on the rowset.</span></span> <span data-ttu-id="b3e7b-126">Для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] поставщика OLE DB собственного клиента этот интерфейс может быть только **IDBAsynchStatus** или **метод ISSAsynchStatus**.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-126">For the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, this interface can only be **IDBAsynchStatus** or **ISSAsynchStatus**.</span></span> <span data-ttu-id="b3e7b-127">Пока набор строк не инициализирован полностью, этот интерфейс действует, как если бы он был приостановлен, и при вызове метода **QueryInterface** для получения интерфейсов, отличных от **IID_IDBAsynchStatus** или **IID_ISSAsynchStatus**, может быть возращена ошибка E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-127">Until the rowset is fully initialized, this interface behaves as if it were in a suspended state, and calling **QueryInterface** for interfaces other than **IID_IDBAsynchStatus** or **IID_ISSAsynchStatus** may return E_NOINTERFACE.</span></span> <span data-ttu-id="b3e7b-128">Если потребитель явно не запросил асинхронную обработку, набор строк инициализируется синхронно.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-128">Unless the consumer explicitly requests asynchronous processing, the rowset is initialized synchronously.</span></span> <span data-ttu-id="b3e7b-129">Все запрашиваемые интерфейсы доступны, когда метод **IDBAsynchStaus::GetStatus** или **ISSAsynchStatus::WaitForAsynchCompletion** возвращается с указанием того, что асинхронная операция завершена.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-129">All requested interfaces are available when **IDBAsynchStaus::GetStatus** or **ISSAsynchStatus::WaitForAsynchCompletion** returns with the indication that asynchronous operation is complete.</span></span> <span data-ttu-id="b3e7b-130">Это не обязательно означает, что набор строк заполнен, но он завершен и полностью функционален.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-130">This does not necessarily mean that the rowset is fully populated, but it is complete and fully functional.</span></span>  
  
 <span data-ttu-id="b3e7b-131">Если выполненная команда не возвращает набор строк, она все равно возвращается немедленно с объектом, поддерживающим **IDBAsynchStatus**.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-131">If the executed command does not return a rowset, it still returns immediately with an object that supports **IDBAsynchStatus**.</span></span>  
  
 <span data-ttu-id="b3e7b-132">Если требуется получить несколько результатов асинхронного выполнения команды, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-132">If you need to get multiple results from asynchronous command execution, you should:</span></span>  
  
-   <span data-ttu-id="b3e7b-133">Установите бит DBPROPVAL_ASYNCH_INITIALIZE свойства DBPROP_ROWSET_ASYNCH перед выполнением команды.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-133">Set the DBPROPVAL_ASYNCH_INITIALIZE bit of the DBPROP_ROWSET_ASYNCH property, before executing the command.</span></span>  
  
-   <span data-ttu-id="b3e7b-134">Вызовите метод **ICommand::Execute** и запросите интерфейс **IMultipleResults**.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-134">Call **ICommand::Execute**, and request **IMultipleResults**.</span></span>  
  
 <span data-ttu-id="b3e7b-135">Интерфейсы **IDBAsynchStatus** и **ISSAsynchStatus** могут быть получены путем запроса интерфейса множественных результатов с помощью метода **QueryInterface**.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-135">The **IDBAsynchStatus** and **ISSAsynchStatus** interfaces can then be obtained by querying the multiple results interface using **QueryInterface**.</span></span>  
  
 <span data-ttu-id="b3e7b-136">После завершения выполнения команды **IMultipleResults** можно использовать как нормальную, с одним исключением из синхронного случая: DB_S_ASYNCHRONOUS может быть возвращено, в этом случае **IDBAsynchStatus** или **метод ISSAsynchStatus** можно использовать для определения момента завершения операции.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-136">When the command has finished executing, **IMultipleResults** can be used as normal, with one exception from the synchronous case: DB_S_ASYNCHRONOUS may be returned, in which case **IDBAsynchStatus** or **ISSAsynchStatus** can be used to determine when the operation is complete.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b3e7b-137">Примеры</span><span class="sxs-lookup"><span data-stu-id="b3e7b-137">Examples</span></span>  
 <span data-ttu-id="b3e7b-138">В следующем примере приложение вызывает неблокирующий метод, выполняет некоторую другую обработку, а затем возвращает результаты процессу.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-138">In the following example, the application calls a non-blocking method, does some other processing, and then returns to process the results.</span></span> <span data-ttu-id="b3e7b-139">Интерфейс **ISSAsynchStatus::WaitForAsynchCompletion** ожидает объект внутреннего события, пока не будет завершена асинхронно выполняющаяся операция или пока не истечет время, указанное в параметре *dwMilisecTimeOut*.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-139">**ISSAsynchStatus::WaitForAsynchCompletion** waits on the internal event object until the asynchronously executing operation is done or the amount of time specified by *dwMilisecTimeOut* is passed.</span></span>  
  
```  
// Set the DBPROPVAL_ASYNCH_INITIALIZE bit in the   
// DBPROP_ROWSET_ASYNCH property before calling Execute().  
  
DBPROPSET CmdPropset[1];  
DBPROP CmdProperties[1];  
  
CmdPropset[0].rgProperties = CmdProperties;  
CmdPropset[0].cProperties = 1;  
CmdPropset[0].guidPropertySet = DBPROPSET_ROWSET;  
  
// Set asynch mode for command.  
CmdProperties[0].dwPropertyID = DBPROP_ROWSET_ASYNCH;  
CmdProperties[0].vValue.vt = VT_I4;  
CmdProperties[0].vValue.lVal = DBPROPVAL_ASYNCH_INITIALIZE;  
CmdProperties[0].dwOptions = DBPROPOPTIONS_REQUIRED;  
  
hr = pICommandProps->SetProperties(1, CmdPropset);  
  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_ISSAsynchStatus,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pISSAsynchStatus);  
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   // Do some work here...  
  
   hr = pISSAsynchStatus->WaitForAsynchCompletion(dwMilisecTimeOut);  
   if ( hr == S_OK)  
   {  
      hr = pISSAsynchStatus->QueryInterface(IID_IRowset, (void**)&pRowset);  
      pISSAsynchStatus->Release();  
   }  
}  
```  
  
 <span data-ttu-id="b3e7b-140">Метод **ISSAsynchStatus::WaitForAsynchCompletion** ожидает объект внутреннего события, пока не будет завершена асинхронно выполняющаяся операция или пока не будет передано значение *dwMilisecTimeOut*.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-140">**ISSAsynchStatus::WaitForAsynchCompletion** waits on the internal event object until the asynchronously executing operation is done or the *dwMilisecTimeOut* value is passed.</span></span>  
  
 <span data-ttu-id="b3e7b-141">В следующем примере показана асинхронная обработка с несколькими результирующими наборами.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-141">The following example shows asynchronous processing with multiple result sets:</span></span>  
  
```  
DBPROP CmdProperties[1];  
  
// Set asynch mode for command.  
CmdProperties[0].dwPropertyID = DBPROP_ROWSET_ASYNCH;  
CmdProperties[0].vValue.vt = VT_I4;  
CmdProperties[0].vValue.lVal = DBPROPVAL_ASYNCH_INITIALIZE;  
  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_IMultipleResults,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pIMultipleResults);  
  
// Use GetResults for ISSAsynchStatus.  
hr = pIMultipleResults->GetResult(IID_ISSAsynchStatus, (void **) &pISSAsynchStatus);  
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   // Do some work here...  
  
   hr = pISSAsynchStatus->WaitForAsynchCompletion(dwMilisecTimeOut);  
   if (hr == S_OK)  
   {  
      hr = pISSAsynchStatus->QueryInterface(IID_IRowset, (void**)&pRowset);  
      pISSAsynchStatus->Release();  
   }  
}  
```  
  
 <span data-ttu-id="b3e7b-142">Чтобы предотвратить блокировку, клиент может проверить состояние выполняющейся асинхронной операции, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-142">To prevent blocking, the client can check the status of a running asynchronous operation, as in the following example:</span></span>  
  
```  
// Set the DBPROPVAL_ASYNCH_INITIALIZE bit in the   
// DBPROP_ROWSET_ASYNCH property before calling Execute().  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_ISSAsynchStatus,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pISSAsynchStatus);   
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   do{  
      // Do some work...  
      hr = pISSAsynchStatus->GetStatus(DB_NULL_HCHAPTER, DBASYNCHOP_OPEN, NULL, NULL, &ulAsynchPhase, NULL);  
   }while (DBASYNCHPHASE_COMPLETE != ulAsynchPhase)  
   if SUCCEEDED(hr)  
   {  
      hr = pISSAsynchStatus->QueryInterface(IID_IRowset, (void**)&pRowset);  
   }  
   pIDBAsynchStatus->Release();  
}  
```  
  
 <span data-ttu-id="b3e7b-143">В следующем примере показано, как можно отменить выполняющуюся в настоящее время асинхронную операцию.</span><span class="sxs-lookup"><span data-stu-id="b3e7b-143">The following example demonstrates how you can cancel the currently running asynchronous operation:</span></span>  
  
```  
// Set the DBPROPVAL_ASYNCH_INITIALIZE bit in the   
// DBPROP_ROWSET_ASYNCH property before calling Execute().  
hr = pICommand->Execute(  
   pUnkOuter,  
   IID_ISSAsynchStatus,  
   pParams,  
   pcRowsAffected,  
   (IUnknown**)&pISSAsynchStatus);  
  
if (hr == DB_S_ASYNCHRONOUS)  
{  
   // Do some work...  
   hr = pISSAsynchStatus->Abort(DB_NULL_HCHAPTER, DBASYNCHOP_OPEN);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3e7b-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="b3e7b-144">See Also</span></span>  
 <span data-ttu-id="b3e7b-145">[Компоненты собственного клиента SQL Server](sql-server-native-client-features.md) </span><span class="sxs-lookup"><span data-stu-id="b3e7b-145">[SQL Server Native Client Features](sql-server-native-client-features.md) </span></span>  
 <span data-ttu-id="b3e7b-146">[Свойства и поведение наборов строк](../../native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span><span class="sxs-lookup"><span data-stu-id="b3e7b-146">[Rowset Properties and Behaviors](../../native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span></span>  
 [<span data-ttu-id="b3e7b-147">ISSAsynchStatus (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="b3e7b-147">ISSAsynchStatus &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-interfaces/issasynchstatus-ole-db.md)  
  
  
