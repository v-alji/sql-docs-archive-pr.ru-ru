---
title: Использование типов больших значений | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- large value data types
- SQLNCLI, large value types
- SQL Server Native Client, large value types
- data access [SQL Server Native Client], large value types
- SQL Server Native Client ODBC driver, large value data types
- SQL Server Native Client OLE DB provider, large value data types
ms.assetid: 4a58b05c-8848-44bb-8704-f9f409efa5af
author: rothja
ms.author: jroth
ms.openlocfilehash: 8a2e93ee36eb4bfadf18c5b78f552380d1c94266
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666540"
---
# <a name="using-large-value-types"></a><span data-ttu-id="62b3a-102">Использование типов больших значений</span><span class="sxs-lookup"><span data-stu-id="62b3a-102">Using Large Value Types</span></span>
  <span data-ttu-id="62b3a-103">До выхода [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] работа с типами данных больших значений требовала особой обработки.</span><span class="sxs-lookup"><span data-stu-id="62b3a-103">Before [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], working with large value data types required special handling.</span></span> <span data-ttu-id="62b3a-104">Типы данных больших значений — это типы, размер которых превышает максимальный размер строки в 8 КБ.</span><span class="sxs-lookup"><span data-stu-id="62b3a-104">Large value data types are those that exceed the maximum row size of 8 KB.</span></span> [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]<span data-ttu-id="62b3a-105">введен описатель **Max** для типов данных **varchar**, **nvarchar** и **varbinary** , чтобы обеспечить хранение значений размером до 2 ^ 31-1 байт.</span><span class="sxs-lookup"><span data-stu-id="62b3a-105">introduced a **max** specifier for **varchar**, **nvarchar** and **varbinary** data types to allow storage of values as large as 2^31 -1 bytes.</span></span> <span data-ttu-id="62b3a-106">Столбцы и [!INCLUDE[tsql](../../../includes/tsql-md.md)] переменные таблицы могут указывать типы данных **varchar (max)**, **nvarchar (max)** или **varbinary (max)** .</span><span class="sxs-lookup"><span data-stu-id="62b3a-106">Table columns and [!INCLUDE[tsql](../../../includes/tsql-md.md)] variables may specify **varchar(max)**, **nvarchar(max)** or **varbinary(max)** data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62b3a-107">Типы больших значений могут иметь максимальный размер от 1 до 8 КБ или они могут быть указаны как неограниченные.</span><span class="sxs-lookup"><span data-stu-id="62b3a-107">Large value data types can have a maximum size between 1 and 8 KB, or they can be specified as unlimited.</span></span>  
  
 <span data-ttu-id="62b3a-108">Ранее только типы данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]**text**, **ntext** и **image** могли достигать такой длины.</span><span class="sxs-lookup"><span data-stu-id="62b3a-108">Previously, only [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types such as **text**, **ntext** and **image** could attain such lengths.</span></span> <span data-ttu-id="62b3a-109">Спецификатор **Max** для **varchar**, **nvarchar** и **varbinary** сделал эти типы данных избыточными.</span><span class="sxs-lookup"><span data-stu-id="62b3a-109">The **max** specifier for **varchar**, **nvarchar** and **varbinary** made these data types redundant.</span></span> <span data-ttu-id="62b3a-110">Однако поскольку типы данных большой длины до сих пор доступны, большинство интерфейсов к компонентам доступа к данным OLE DB и ODBC остаются теми же.</span><span class="sxs-lookup"><span data-stu-id="62b3a-110">However, because long data types are still available, most of the interfaces to the OLE DB and ODBC data access components will remain the same.</span></span> <span data-ttu-id="62b3a-111">Для обратной совместимости с более ранними версиями флаг DBCOLUMNFLAGS_ISLONG в поставщике OLE DB для собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и флаг SQL_LONGVARCHAR в драйвере ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] до сих пор используются.</span><span class="sxs-lookup"><span data-stu-id="62b3a-111">For backward compatibility with prior releases, the DBCOLUMNFLAGS_ISLONG flag in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, and the SQL_LONGVARCHAR in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver remain in use.</span></span> <span data-ttu-id="62b3a-112">Поставщики и драйверы, предназначенные для [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] и более поздних версий, продолжают использовать эти термины для новых типов при задании неограниченной максимальной длины.</span><span class="sxs-lookup"><span data-stu-id="62b3a-112">Providers and drivers written against [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] and later continue to use these terms for the new types when set to unlimited maximum length.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62b3a-113">Типы данных **varchar(max)**, **nvarchar(max)** и **varbinary(max)** можно также указывать в качестве типов входных и выходных параметров хранимых процедур, типов возвращаемых значений функций или в функциях [CAST и CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="62b3a-113">You can also specify **varchar(max)**, **nvarchar(max)**, and **varbinary(max)** data types as input and output parameter types of stored procedures, function return types, or in [CAST and CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql) functions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62b3a-114">При репликации данных может потребоваться настроить [параметр конфигурации сервера max text repl size](../../../database-engine/configure-windows/configure-the-max-text-repl-size-server-configuration-option.md) равным-1.</span><span class="sxs-lookup"><span data-stu-id="62b3a-114">If replicating data you may need to configure the [max text repl size server configuration option](../../../database-engine/configure-windows/configure-the-max-text-repl-size-server-configuration-option.md) to -1.</span></span>  
  
## <a name="sql-server-native-client-ole-db-provider"></a><span data-ttu-id="62b3a-115">Поставщик OLE DB для собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="62b3a-115">SQL Server Native Client OLE DB Provider</span></span>  
 <span data-ttu-id="62b3a-116">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента предоставляет типы **varchar (max)**, **varbinary (max)** и **nvarchar (max)** как DBTYPE_STR, DBTYPE_BYTES и DBTYPE_WSTR соответственно.</span><span class="sxs-lookup"><span data-stu-id="62b3a-116">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **varchar(max)**, **varbinary(max)**, and **nvarchar(max)** types as DBTYPE_STR, DBTYPE_BYTES, and DBTYPE_WSTR, respectively.</span></span>  
  
 <span data-ttu-id="62b3a-117">Типы данных **varchar(max)**, **varbinary(max)** и **nvarchar(max)** в столбцах с размером **max**, установленным в неограниченное значение, представляются как ISLONG через основные наборы строк схемы OLE DB и интерфейсы, возвращающие типы столбцов.</span><span class="sxs-lookup"><span data-stu-id="62b3a-117">The data types **varchar(max)**, **varbinary(max)**, and **nvarchar(max)** in columns with the **max** size set to unlimited are represented as an ISLONG through the core OLE DB schema rowsets and interfaces returning column data types.</span></span>  
  
 <span data-ttu-id="62b3a-118">Реализация **IAccessor** объекта команды была изменена, чтобы разрешить привязку как DBTYPE_IUNKNOWN.</span><span class="sxs-lookup"><span data-stu-id="62b3a-118">The command object's **IAccessor** implementation has been changed to allow binding as DBTYPE_IUNKNOWN.</span></span> <span data-ttu-id="62b3a-119">Если потребитель указывает DBTYPE_IUNKNOWN и задает для *pObject* значение NULL, то поставщик возвратит потребителю интерфейс **ISequentialStream**, чтобы потребитель мог направить данные **varchar(max)**, **nvarchar(max)** или **varbinary(max)** из выходных переменных.</span><span class="sxs-lookup"><span data-stu-id="62b3a-119">If the consumer specifies DBTYPE_IUNKNOWN and sets *pObject* to null, the provider will return the **ISequentialStream** interface to the consumer so that the consumer can stream **varchar(max)**, **nvarchar(max)**, or **varbinary(max)** data out of output variables.</span></span>  
  
 <span data-ttu-id="62b3a-120">Поток значений выходных параметров возвращается после любых результирующих строк.</span><span class="sxs-lookup"><span data-stu-id="62b3a-120">Streamed output parameter values are returned after any result rows.</span></span> <span data-ttu-id="62b3a-121">Если приложение пытается перейти к следующему результирующему набору, вызывая метод **IMultipleResults::GetResult** и не используя все возвращаемые значения выходных параметров, то возвращается DB_E_OBJECTOPEN.</span><span class="sxs-lookup"><span data-stu-id="62b3a-121">If the application attempts to move on to the next result set by calling **IMultipleResults::GetResult** without consuming all the returned output parameter values, DB_E_OBJECTOPEN will be returned.</span></span>  
  
 <span data-ttu-id="62b3a-122">Для поддержки потоковой передачи [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента требует, чтобы параметры переменной длины были доступны в последовательном порядке.</span><span class="sxs-lookup"><span data-stu-id="62b3a-122">In order to support streaming, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider requires variable length parameters to be accessed in sequential order.</span></span> <span data-ttu-id="62b3a-123">Это означает, что для свойства DBPROP_ACCESSORDER необходимо задавать либо значение DBPROPVAL_AO_SEQUENTIALSTORAGEOBJECTS, либо значение DBPROPVAL_AO_SEQUENTIAL каждый раз, когда столбцы **varchar(max)**, **nvarchchar(max)** или **varbinary(max)** либо выходные параметры привязываются к типу DBTYPE_IUNKNOWN.</span><span class="sxs-lookup"><span data-stu-id="62b3a-123">This means that DBPROP_ACCESSORDER must be set to either DBPROPVAL_AO_SEQUENTIALSTORAGEOBJECTS or DBPROPVAL_AO_SEQUENTIAL whenever **varchar(max)**, **nvarchchar(max)**, or **varbinary(max)** columns or output parameters are bound to DBTYPE_IUNKNOWN.</span></span> <span data-ttu-id="62b3a-124">Если не следовать этому ограничению на порядок доступа, то вызов метода **IRowset::GetData** завершится с ошибкой DBSTATUS_E_UNAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="62b3a-124">Calls to **IRowset::GetData** will fail with DBSTATUS_E_UNAVAILABLE if this access order restriction is not adhered to.</span></span> <span data-ttu-id="62b3a-125">Это ограничение не применяется, если нет выходных привязок с использованием типа DBTYPE_IUNKNOWN.</span><span class="sxs-lookup"><span data-stu-id="62b3a-125">This restriction does not apply when there are no output bindings using DBTYPE_IUNKNOWN.</span></span>  
  
 <span data-ttu-id="62b3a-126">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента также поддерживает привязку выходных параметров в качестве DBTYPE_IUNKNOWN для типов данных больших значений, чтобы упростить сценарии, в которых хранимая процедура возвращает типы больших значений в качестве возвращаемых значений, предоставляемых как DBTYPE_IUNKNOWN клиенту.</span><span class="sxs-lookup"><span data-stu-id="62b3a-126">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider also supports binding output parameters as DBTYPE_IUNKNOWN for large value data types to facilitate scenarios where a stored procedure returns large value types as return values that are exposed as DBTYPE_IUNKNOWN to the client.</span></span>  
  
 <span data-ttu-id="62b3a-127">Работать с этими типами приложение может следующими способами.</span><span class="sxs-lookup"><span data-stu-id="62b3a-127">To work with these types, an application has the following options:</span></span>  
  
-   <span data-ttu-id="62b3a-128">Привязать как тип, имеющий поддерживаемые привязки к базовому типу столбца (например: для nvarchar(max) выполните привязку, указав тип, который можно привязать к типу nvarchar).</span><span class="sxs-lookup"><span data-stu-id="62b3a-128">Bind as a type that has supported bindings with the base type of the column (eg for nvarchar(max), bind as a type that can be bound to nvarchar).</span></span> <span data-ttu-id="62b3a-129">Если буфер недостаточно большой, то происходит усечение, точно так же, как и для базового типа, хотя большие значения в данный момент доступны.</span><span class="sxs-lookup"><span data-stu-id="62b3a-129">If the buffer is not big enough truncation will occur, exactly as for the base type, albeit that larger values are now available.</span></span>  
  
-   <span data-ttu-id="62b3a-130">Привязать как тип, имеющий поддерживаемые преобразования в базовый тип столбца, и также указать тип DBTYPE_BYREF.</span><span class="sxs-lookup"><span data-stu-id="62b3a-130">Bind as a type that has supported conversions with the base type of the column and also specify DBTYPE_BYREF.</span></span>  
  
-   <span data-ttu-id="62b3a-131">Выполните привязку, указав тип DBTYPE_IUNKNOWN, и используйте потоковую передачу.</span><span class="sxs-lookup"><span data-stu-id="62b3a-131">Bind as DBTYPE_IUNKNOWN and use streaming.</span></span>  
  
 <span data-ttu-id="62b3a-132">При создании отчета о максимальном размере столбца [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] поставщик собственного клиента OLE DB будет сообщать:</span><span class="sxs-lookup"><span data-stu-id="62b3a-132">When reporting the maximum size of a column, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider will report:</span></span>  
  
-   <span data-ttu-id="62b3a-133">Определенный максимальный размер, например, 2000 для столбца **varchar (** 2000 **)** или</span><span class="sxs-lookup"><span data-stu-id="62b3a-133">The defined maximum size, which for example, is 2000 for a **varchar(** 2000 **)** column, or</span></span>  
  
-   <span data-ttu-id="62b3a-134">значение "unlimited", если столбец **varchar(max)** равен ~0.</span><span class="sxs-lookup"><span data-stu-id="62b3a-134">The value "unlimited" which in the case of a **varchar(max)** column equals ~0.</span></span> <span data-ttu-id="62b3a-135">Это значение устанавливается для свойства метаданных DBCOLUMN_COLUMNSIZE.</span><span class="sxs-lookup"><span data-stu-id="62b3a-135">This value is set for the DBCOLUMN_COLUMNSIZE metadata property.</span></span>  
  
 <span data-ttu-id="62b3a-136">К столбцу **varchar(max)** будут применены стандартные правила преобразования. Это значит, что любое преобразование, допустимое для столбца **varchar(** 2000 **)**, также допустимо для столбца **varchar(max)**.</span><span class="sxs-lookup"><span data-stu-id="62b3a-136">The standard conversion rules will apply to a **varchar(max)** column, meaning that any conversion that is valid for a **varchar(** 2000 **)** column will also be valid for a **varchar(max)** column.</span></span> <span data-ttu-id="62b3a-137">То же относится к столбцам **nvarchar(max)** и **varbinary(max)**.</span><span class="sxs-lookup"><span data-stu-id="62b3a-137">The same is true for **nvarchar(max)** and **varbinary(max)** columns.</span></span>  
  
 <span data-ttu-id="62b3a-138">При получении типов больших значений наиболее эффективным подходом является привязка как типа DBTYPE_IUNKNOWN и задание для свойства DBPROP_ACCESSORDER набора строк значения DBPROPVAL_AO_SEQUENTIALSTORAGEOBJECTS.</span><span class="sxs-lookup"><span data-stu-id="62b3a-138">When retrieving large value types, the most efficient approach is to bind as DBTYPE_IUNKNOWN and set the rowset property DBPROP_ACCESSORDER to DBPROPVAL_AO_SEQUENTIALSTORAGEOBJECTS.</span></span> <span data-ttu-id="62b3a-139">Это вызовет передачу значения в потоке напрямую из сети без промежуточной буферизации, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="62b3a-139">This will cause the value to be streamed directly from the network with no intermediate buffering, as in the following example:</span></span>  
  
```  
#define UNICODE  
#define _UNICODE  
#define DBINITCONSTANTS  
#define INITGUID  
#define OLEDBVER 0x0250  // To include the correct interfaces.  
  
#include <stdio.h>  
#include <tchar.h>  
#include <stddef.h>  
#include <iostream>  
  
using std::cout;  
using std::endl;  
  
#include <windows.h>  
  
#include <oledb.h>  
#include "sqlncli.h"  
#include <oledberr.h>  
  
#define CHKHR_GOTO(hr, errMsg, Label) \  
   if (FAILED(hr)) \  
   { \  
      cout << errMsg << endl; \  
      goto Label; \  
   }  
  
#define MAX_COL_SIZE 8000  
  
// ROUNDUP on all platforms pointers must be aligned properly.  
#define ROUNDUP_AMOUNT 8  
#define ROUNDUP_(size,amount) (((ULONG)(size)+((amount)-1))&~((amount)-1))  
#define ROUNDUP(size) ROUNDUP_(size, ROUNDUP_AMOUNT)  
  
HRESULT InitializeAndEstablishConnection(IDBInitialize** ppIDBInitialize);  
void UnInitializeConnection(IDBInitialize* pIDBInitialize);  
HRESULT CreateAndSetCommand(IDBInitialize* pIDBInitialize, ICommandText** ppICommandText);  
HRESULT ProcessResultSet(IRowset* pIRowset);  
  
void DisplayTime()  
{  
   SYSTEMTIME st;  
   GetSystemTime(&st);  
   cout<< st.wHour << ":" << st.wMinute << ":" << st.wSecond << "." << st.wMilliseconds << endl;  
}  
  
void main()  
{  
   HRESULT hr;  
   IDBInitialize* pIDBInitialize = NULL;  
   ICommandText* pICommandText = NULL;  
   IMultipleResults* pIMultipleResults = NULL;  
   IRowset* pIRowset = NULL;  
  
   hr = InitializeAndEstablishConnection(&pIDBInitialize);  
   CHKHR_GOTO(hr, L"Failed to establish connection.", _ExitMain);  
  
   hr = CreateAndSetCommand(pIDBInitialize, &pICommandText);  
   CHKHR_GOTO(hr, L"Failed to set up command object.", _ExitMain);  
  
   DisplayTime();  
  
   hr = pICommandText->Execute(NULL,   
      IID_IMultipleResults,   
      NULL,   
      NULL,   
     (IUnknown **) &pIMultipleResults);  
  
   CHKHR_GOTO(hr, L"Failed to execute command.", _ExitMain);  
  
   while (1)  
   {  
      hr = pIMultipleResults->GetResult(  
         NULL,   
         DBRESULTFLAG_DEFAULT,   
         IID_IRowset,   
         NULL,   
         (IUnknown**)&pIRowset);  
  
   CHKHR_GOTO(hr, L"Failed to obtain a results from MR object.", _ExitMain);  
  
   if (hr == DB_S_NORESULT)  
      break;  
  
      if (pIRowset)  
      {  
         hr = ProcessResultSet(pIRowset);   
         CHKHR_GOTO(hr, L"Failed to process the current Rowset.", _ExitMain);  
  
         pIRowset->Release();  
         pIRowset = NULL;  
      }  
   }  
  
   DisplayTime();  
  
_ExitMain:  
  
   if (pIRowset)  
   {  
      pIRowset->Release();  
      pIRowset = NULL;  
   }  
  
   if (pIMultipleResults)  
   {  
      pIMultipleResults->Release();  
      pIMultipleResults = NULL;  
   }  
  
   if (pICommandText)  
   {  
      pICommandText->Release();  
      pICommandText = NULL;  
   }  
  
   UnInitializeConnection(pIDBInitialize);  
   return;  
};  
  
HRESULT InitializeAndEstablishConnection(IDBInitialize** ppIDBInitialize)  
{  
   HRESULT hr;  
   IDBInitialize* pIDBInitialize = NULL;  
   IDBProperties* pIDBProperties = NULL;  
  
   const int NUM_DBINIT_PROPS = 3;  
   const wchar_t* const g_wszServer = L".";  
   const wchar_t* const g_wszCatalog = L"AdventureWorks";  
   const wchar_t* const g_wszSecurity = L"SSPI";  
  
   DBPROPSET rgdbPropSetInit[1];  
   DBPROP rgdbPropInit [NUM_DBINIT_PROPS];  
  
   *ppIDBInitialize = NULL;  
   hr = CoInitialize(NULL);  
   CHKHR_GOTO(hr, L"Failed to initialize COM.", _ExitInitialize);  
  
   hr = CoCreateInstance(CLSID_SQLNCLI11,   
      NULL,   
      CLSCTX_INPROC_SERVER,  
      IID_IDBInitialize,   
      (void**)&pIDBInitialize);  
  
   CHKHR_GOTO(hr, L"Failed to create SQLNCLI11 DataSource object.", _ExitInitialize);  
  
   for(int idxProp = 0; idxProp < NUM_DBINIT_PROPS; idxProp++)   
   {  
      VariantInit(&rgdbPropInit[idxProp].vValue);  
   }  
  
   rgdbPropInit[0].dwPropertyID = DBPROP_INIT_DATASOURCE;  
   rgdbPropInit[0].vValue.vt = VT_BSTR;  
   rgdbPropInit[0].vValue.bstrVal= SysAllocString(g_wszServer);  
   rgdbPropInit[0].dwOptions = DBPROPOPTIONS_REQUIRED;  
   rgdbPropInit[0].colid = DB_NULLID;  
  
   if (rgdbPropInit[0].vValue.bstrVal == NULL)  
   {  
      hr = E_OUTOFMEMORY;  
      goto _ExitInitialize;  
   }  
  
   rgdbPropInit[1].dwPropertyID = DBPROP_INIT_CATALOG;  
   rgdbPropInit[1].vValue.vt = VT_BSTR;  
   rgdbPropInit[1].vValue.bstrVal= SysAllocString(g_wszCatalog);  
   rgdbPropInit[1].dwOptions = DBPROPOPTIONS_REQUIRED;  
   rgdbPropInit[1].colid = DB_NULLID;  
  
   if (rgdbPropInit[1].vValue.bstrVal == NULL)  
   {  
      hr = E_OUTOFMEMORY;  
      goto _ExitInitialize;  
   }  
  
   rgdbPropInit[2].dwPropertyID = DBPROP_AUTH_INTEGRATED;  
   rgdbPropInit[2].vValue.vt = VT_BSTR;  
   rgdbPropInit[2].vValue.bstrVal= SysAllocString(g_wszSecurity);  
   rgdbPropInit[2].dwOptions = DBPROPOPTIONS_REQUIRED;  
   rgdbPropInit[2].colid = DB_NULLID;  
  
   if (rgdbPropInit[2].vValue.bstrVal == NULL)  
   {  
      hr = E_OUTOFMEMORY;  
      goto _ExitInitialize;  
   }  
  
   rgdbPropSetInit[0].guidPropertySet = DBPROPSET_DBINIT;  
   rgdbPropSetInit[0].cProperties = NUM_DBINIT_PROPS;  
   rgdbPropSetInit[0].rgProperties = rgdbPropInit;  
  
   hr = pIDBInitialize->QueryInterface(IID_IDBProperties, (void **)&pIDBProperties);  
   CHKHR_GOTO(hr, L"Failed to QI DataSource object for IDBProperties.", _ExitInitialize);  
  
   hr = pIDBProperties->SetProperties(1, rgdbPropSetInit);   
   CHKHR_GOTO(hr, L"Failed to set DataSource object Properties.", _ExitInitialize);  
  
   pIDBProperties->Release();  
   pIDBProperties = NULL;  
  
   hr = pIDBInitialize->Initialize();  
   CHKHR_GOTO(hr, L"Failed to establish connection with the server.", _ExitInitialize);  
  
_ExitInitialize:  
  
   if (pIDBProperties)  
   {  
      pIDBProperties->Release();  
      pIDBProperties = NULL;  
   }  
  
   if (FAILED(hr))  
   {  
      if (pIDBInitialize)  
      {  
         pIDBInitialize->Release();  
         pIDBInitialize = NULL;  
      }  
   }  
  
   *ppIDBInitialize = pIDBInitialize;  
   return hr;  
}  
  
void UnInitializeConnection(IDBInitialize* pIDBInitialize)  
{  
   if (pIDBInitialize)  
   {  
      pIDBInitialize->Uninitialize();  
      pIDBInitialize->Release();  
      pIDBInitialize = NULL;  
   }  
   CoUninitialize();  
}  
  
HRESULT CreateAndSetCommand(IDBInitialize* pIDBInitialize, ICommandText** ppICommandText)  
{  
   HRESULT hr;  
   IDBCreateSession* pIDBCreateSession = NULL;  
   IDBCreateCommand* pIDBCreateCommand = NULL;  
   ICommandText* pICommandText = NULL;  
   ICommandProperties* pICommandProperties = NULL;  
   DBPROPSET rgCmdPropSet[1];  
   DBPROP rgCmdProperties[1];  
  
const wchar_t* const g_wCmdString = L"declare @x xml, @y nvarchar(max); select @x = (SELECT * FROM Sales.SalesOrderHeader FOR XML AUTO); select @x;";  
  
   *ppICommandText = NULL;  
  
   if (!pIDBInitialize)  
   {  
      hr = E_FAIL;  
      goto _ExitCreateAndSetCommand;  
   }  
  
   hr = pIDBInitialize->QueryInterface(IID_IDBCreateSession, (void**) &pIDBCreateSession);  
   CHKHR_GOTO(hr, L"Failed to obtain IDBCreateSession interface from DSO.", _ExitCreateAndSetCommand);  
  
   hr = pIDBCreateSession->CreateSession(  
      NULL,   
      IID_IDBCreateCommand,   
      (IUnknown**) &pIDBCreateCommand);  
  
   CHKHR_GOTO(hr, L"Failed to Create a Session for command execution.", _ExitCreateAndSetCommand);  
  
   hr = pIDBCreateCommand->CreateCommand(  
      NULL,   
      IID_ICommandText,   
      (IUnknown**)&pICommandText);  
  
   CHKHR_GOTO(hr, L"Failed to Create a Command object.", _ExitCreateAndSetCommand);  
  
   hr = pICommandText->SetCommandText(DBGUID_DBSQL, g_wCmdString);  
   CHKHR_GOTO(hr, L"Failed to Set Command Text.", _ExitCreateAndSetCommand);  
  
   hr = pICommandText->QueryInterface(IID_ICommandProperties, (void**) &pICommandProperties);  
   CHKHR_GOTO(hr, L"Failed to obtain ICommandProperties interface from the command object.", _ExitCreateAndSetCommand);  
  
   rgCmdProperties[0].dwPropertyID = DBPROP_ACCESSORDER;  
   rgCmdProperties[0].vValue.vt = VT_I4;  
   rgCmdProperties[0].vValue.lVal = DBPROPVAL_AO_SEQUENTIAL;  
   rgCmdProperties[0].dwOptions = DBPROPOPTIONS_REQUIRED;  
   rgCmdProperties[0].colid = DB_NULLID;  
  
   rgCmdPropSet[0].guidPropertySet = DBPROPSET_ROWSET;  
   rgCmdPropSet[0].cProperties = 1;  
   rgCmdPropSet[0].rgProperties = rgCmdProperties;  
  
   hr = pICommandProperties->SetProperties(1, rgCmdPropSet);   
   CHKHR_GOTO(hr, L"Failed to Set Command object Properties.", _ExitCreateAndSetCommand);  
  
_ExitCreateAndSetCommand:  
  
   if (pICommandProperties)  
   {  
      pICommandProperties->Release();  
      pICommandProperties = NULL;  
   }  
  
   if (pIDBCreateCommand)  
   {  
      pIDBCreateCommand->Release();  
      pIDBCreateCommand = NULL;  
   }  
  
   if (pIDBCreateSession)  
   {  
      pIDBCreateSession->Release();  
      pIDBCreateSession = NULL;  
   }  
  
   if (FAILED(hr))  
   {  
      if (pICommandText)  
      {  
         pICommandText->Release();  
         pICommandText = NULL;  
      }  
   }  
  
   *ppICommandText = pICommandText;  
   return hr;  
}  
  
HRESULT ProcessResultSet(IRowset* pIRowset)  
{  
   HRESULT hr;  
  
   IColumnsInfo* pIColumnsInfo = NULL;  
   DBCOLUMNINFO* pDBColumnInfo = NULL;  
   ULONG lNumCols = 0;  
   wchar_t* pStringsBuffer = NULL;  
  
   DBBINDING* pBindings = NULL;  
   DBOBJECT dbobj;  
   ULONG idxBinding;  
   IAccessor* pIAccessor = NULL;  
   HACCESSOR hAccessor = DB_NULL_HACCESSOR;  
   HROW hRows[1] = {DB_NULL_HROW};  
   HROW* pRow = &hRows[0];  
   BYTE* pBuffer = NULL;  
  
   ULONG lNumRowsRetrieved;  
   DBLENGTH dwOffset = 0;  
  
   hr = pIRowset->QueryInterface(IID_IColumnsInfo, (void **)&pIColumnsInfo);  
   CHKHR_GOTO(hr, L"Failed to QI Rowset for IColumnsInfo.", _ExitProcessResultSet);  
  
   hr = pIColumnsInfo->GetColumnInfo(&lNumCols, &pDBColumnInfo, &pStringsBuffer);  
   CHKHR_GOTO(hr, L"Failed to obtain Column Information.", _ExitProcessResultSet);  
  
   pBindings = new DBBINDING[lNumCols];  
  
   if (!pBindings)  
   {  
      hr = E_OUTOFMEMORY;  
      goto _ExitProcessResultSet;  
   }  
  
   memset(pBindings, 0, sizeof(DBBINDING) * lNumCols);  
  
   dbobj.dwFlags = STGM_READ;  
   dbobj.iid = IID_ISequentialStream;  
  
   for (idxBinding = 0; idxBinding < lNumCols; idxBinding++)   
   {  
      pBindings[idxBinding].iOrdinal = idxBinding + 1;  
      pBindings[idxBinding].obStatus = dwOffset;  
      pBindings[idxBinding].obLength = dwOffset + sizeof(DBSTATUS);  
      pBindings[idxBinding].obValue = dwOffset + sizeof(DBSTATUS) + sizeof(DBLENGTH);  
  
      pBindings[idxBinding].pTypeInfo = NULL;  
      pBindings[idxBinding].pBindExt = NULL;  
      pBindings[idxBinding].dwPart = DBPART_VALUE | DBPART_LENGTH | DBPART_STATUS;  
      pBindings[idxBinding].dwMemOwner = DBMEMOWNER_CLIENTOWNED;  
      pBindings[idxBinding].eParamIO = DBPARAMIO_NOTPARAM;  
      pBindings[idxBinding].bPrecision = pDBColumnInfo[idxBinding].bPrecision;  
      pBindings[idxBinding].bScale = pDBColumnInfo[idxBinding].bScale;  
  
      pBindings[idxBinding].cbMaxLen = 0;  
      pBindings[idxBinding].wType = DBTYPE_WSTR;  
  
   // Determine the maximum number of bytes required in our buffer to  
   // contain the Unicode string representation of the provider's native  
   // data type, including room for the NULL-termination character  
   switch( pDBColumnInfo[idxBinding].wType )  
   {  
      case DBTYPE_NULL:  
      case DBTYPE_EMPTY:  
      case DBTYPE_I1:  
      case DBTYPE_I2:  
      case DBTYPE_I4:  
      case DBTYPE_UI1:  
      case DBTYPE_UI2:  
      case DBTYPE_UI4:  
      case DBTYPE_R4:  
      case DBTYPE_BOOL:  
      case DBTYPE_I8:  
      case DBTYPE_UI8:  
      case DBTYPE_R8:  
      case DBTYPE_CY:  
      case DBTYPE_ERROR:  
      // When the above types are converted to a string, they  
      // will all fit into 25 characters, so use that plus space  
      // for the NULL-terminator.  
  
      pBindings[idxBinding].cbMaxLen = (25 + 1) * sizeof(WCHAR);  
      break;  
  
      case DBTYPE_DECIMAL:  
      case DBTYPE_NUMERIC:  
      case DBTYPE_DATE:  
      case DBTYPE_DBDATE:  
      case DBTYPE_DBTIMESTAMP:  
      case DBTYPE_GUID:  
      // Converted to a string, the above types will all fit into  
      // 50 characters, so use that plus space for the terminator.  
  
      pBindings[idxBinding].cbMaxLen = (50 + 1) * sizeof(WCHAR);  
      break;  
  
      case DBTYPE_BYTES:  
      // In converting DBTYPE_BYTES to a string, each byte  
      // becomes two characters (e.g. 0xFF -> "FF"), so we  
      // will use double the maximum size of the column plus  
      // include space for the NULL-terminator.  
  
      pBindings[idxBinding].cbMaxLen = (pDBColumnInfo[idxBinding].ulColumnSize * 2 + 1) * sizeof(WCHAR);  
      break;  
  
      case DBTYPE_STR:  
      case DBTYPE_WSTR:  
      case DBTYPE_BSTR:  
      // Going from a string to our string representation,  
      // we can just take the maximum size of the column,  
      // a count of characters, and include space for the  
      // terminator, which is not included in the column size.  
  
      pBindings[idxBinding].cbMaxLen = (pDBColumnInfo[idxBinding].ulColumnSize + 1) * sizeof(WCHAR);  
      break;  
  
      default:  
      // For any other type, we will simply use our maximum  
      // column buffer size, since the display size of these  
      // columns may be variable (e.g. DBTYPE_VARIANT) or  
      // unknown (e.g. provider-specific types).  
      pBindings[idxBinding].cbMaxLen = MAX_COL_SIZE;  
      break;  
   }  
  
   // If the provider's native data type for this column is  
   // DBTYPE_IUNKNOWN or this is a BLOB column and the user  
   // has requested that we bind BLOB columns as ISequentialStream  
   // objects, bind this column as an ISequentialStream object if  
   // the provider supports our creating another ISequentialStream  
   // binding.  
   if(pDBColumnInfo[idxBinding].dwFlags & DBCOLUMNFLAGS_ISLONG)  
   {  
      pBindings[idxBinding].wType = DBTYPE_IUNKNOWN;  
  
      pBindings[idxBinding].cbMaxLen = sizeof(ISequentialStream*);  
  
      pBindings[idxBinding].pObject = (DBOBJECT *)CoTaskMemAlloc(sizeof(DBOBJECT));  
  
      if (!pBindings[idxBinding].pObject)  
      {  
         hr = E_OUTOFMEMORY;  
         goto _ExitProcessResultSet;  
      }  
  
      // Direct the provider to create an ISequentialStream  
      // object over the data for this column.  
      pBindings[idxBinding].pObject->iid = IID_ISequentialStream;  
  
      // We want read access on the ISequentialStream  
      // object that the provider will create for us  
      pBindings[idxBinding].pObject->dwFlags = STGM_READ;  
      }  
  
      // Ensure that the bound maximum length is no more than the  
      // maximum column size in bytes that we've defined.  
      pBindings[idxBinding].cbMaxLen = min(pBindings[idxBinding].cbMaxLen, MAX_COL_SIZE);  
  
      // Update the offset past the end of this column's data, so  
      // that the next column will begin in the correct place in  
      // the buffer.  
      dwOffset = pBindings[idxBinding].cbMaxLen + pBindings[idxBinding].obValue;  
  
      // Ensure that the data for the next column will be correctly  
      // aligned for all platforms, or, if we're done with columns,  
      // that if we allocate space for multiple rows that the data  
      // for every row is correctly aligned.  
      dwOffset = ROUNDUP(dwOffset);  
   }  
  
   hr = pIRowset->QueryInterface(IID_IAccessor, (void **) &pIAccessor);  
   CHKHR_GOTO(hr, L"Failed to obtain Accessor interface", _ExitProcessResultSet);  
  
   hr = pIAccessor->CreateAccessor(DBACCESSOR_ROWDATA,  
      lNumCols,  
      pBindings,  
      0,  
      &hAccessor,  
      NULL);  
  
   CHKHR_GOTO(hr, L"Failed to create Accessor", _ExitProcessResultSet);  
   for (idxBinding = 0; idxBinding < lNumCols; idxBinding++)   
   {  
      cout << pDBColumnInfo[idxBinding].pwszName << endl;  
   }  
  
   lNumRowsRetrieved = 0;  
  
   hr = pIRowset->GetNextRows(  
      NULL,  
      0,  
      1,  
      &lNumRowsRetrieved,  
      &pRow);  
  
   CHKHR_GOTO(hr, L"Failed to fetch a row from the rowset", _ExitProcessResultSet);  
  
   pBuffer = new BYTE[sizeof(DBSTATUS) + sizeof(DBLENGTH) + sizeof(IUnknown*)];  
  
   if (!pBuffer)  
   {  
      hr = E_OUTOFMEMORY;  
      goto _ExitProcessResultSet;  
   }  
  
   while(lNumRowsRetrieved && hr != DB_S_ENDOFROWSET)   
   {  
      memset(pBuffer, 0, sizeof(DBSTATUS) + sizeof(DBLENGTH) + sizeof(IUnknown*));  
  
      hr = pIRowset->GetData(hRows[0], hAccessor, pBuffer);  
      CHKHR_GOTO(hr, L"Failed to obtain row data", _ExitProcessResultSet);  
  
      for (idxBinding = 0; idxBinding < lNumCols; idxBinding++)  
      {  
         if (pBindings[idxBinding].wType == DBTYPE_IUNKNOWN)  
         {  
            BYTE pbBuff[3000];  
            ULONG cbNeeded = sizeof(pbBuff)/sizeof(BYTE);  
            ULONG cbRead;  
            ULONG cbReadTotal = 0;  
            ISequentialStream* pISequentialStream = NULL;  
  
            IUnknown* pIUnknown = *((IUnknown**)(pBuffer + pBindings[idxBinding].obValue));  
            pIUnknown->QueryInterface(IID_ISequentialStream, (void**)&pISequentialStream);  
  
            do  
            {  
               hr = pISequentialStream->Read(pbBuff, cbNeeded, &cbRead);  
               cbReadTotal += cbRead;  
            }  
            while (SUCCEEDED(hr) && hr != S_FALSE && cbRead == cbNeeded);  
  
               cout << "Total Bytes Read: " << cbReadTotal << endl;  
  
               pISequentialStream->Release();  
               pISequentialStream = NULL;  
               pIUnknown->Release();  
               pIUnknown = NULL;  
            }  
         }  
  
         pIRowset->ReleaseRows(1, pRow, NULL, NULL, NULL);  
  
         hr = pIRowset->GetNextRows(NULL,  
            0,  
            1,  
            &lNumRowsRetrieved,  
            &pRow);  
  
         CHKHR_GOTO(hr, L"Failed to fetch a row from the rowset.", _ExitProcessResultSet);  
   }  
  
_ExitProcessResultSet:  
  
   pIRowset->ReleaseRows(1, pRow, NULL, NULL, NULL);  
   delete [] pBuffer;  
  
   if (pIAccessor)  
   {  
      if (hAccessor != DB_NULL_HACCESSOR)  
      {  
         pIAccessor->ReleaseAccessor(hAccessor, NULL);  
      }  
  
      pIAccessor->Release();  
      pIAccessor = NULL;  
   }  
  
   if (pBindings)  
   {  
      for (idxBinding = 0; idxBinding < lNumCols; idxBinding++)  
      {  
         if (pBindings[idxBinding].pObject)  
         CoTaskMemFree(pBindings[idxBinding].pObject);  
      }  
   }  
  
   delete [] pBindings;  
  
   CoTaskMemFree(pDBColumnInfo);  
   CoTaskMemFree(pStringsBuffer);  
  
   if (pIColumnsInfo)  
   {  
      pIColumnsInfo->Release();  
      pIColumnsInfo = NULL;  
   }  
  
   return hr;  
}  
```  
  
 <span data-ttu-id="62b3a-140">Дополнительные сведения о том, как [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента предоставляет типы данных больших значений, см. в разделе [большие двоичные объекты и OLE](../../native-client-ole-db-blobs/blobs-and-ole-objects.md).</span><span class="sxs-lookup"><span data-stu-id="62b3a-140">For more information about how the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes large value data types, see [BLOBs and OLE Objects](../../native-client-ole-db-blobs/blobs-and-ole-objects.md).</span></span>  
  
## <a name="sql-server-native-client-odbc-driver"></a><span data-ttu-id="62b3a-141">Драйвер ODBC для собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="62b3a-141">SQL Server Native Client ODBC Driver</span></span>  
 <span data-ttu-id="62b3a-142">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента предоставляет типы **varchar (max)**, **varbinary (max)** и **nvarchar (max)** как SQL_VARCHAR, SQL_VARBINARY и SQL_WVARCHAR в функциях API ODBC, которые принимают или возвращают типы данных ODBC SQL.</span><span class="sxs-lookup"><span data-stu-id="62b3a-142">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver exposes the **varchar(max)**, **varbinary(max)** and **nvarchar(max)** types as SQL_VARCHAR, SQL_VARBINARY, and SQL_WVARCHAR in ODBC API functions that accept or return ODBC SQL data types.</span></span>  
  
 <span data-ttu-id="62b3a-143">Сообщая максимальный размер столбца, драйвер сообщает:</span><span class="sxs-lookup"><span data-stu-id="62b3a-143">When reporting the maximum size of a column, the driver will report either:</span></span>  
  
-   <span data-ttu-id="62b3a-144">Определенный максимальный размер, например, 2000 для столбца **varchar (2000)** или</span><span class="sxs-lookup"><span data-stu-id="62b3a-144">The defined maximum size, which for example, is 2000 for a **varchar(2000)** column, or</span></span>  
  
-   <span data-ttu-id="62b3a-145">Значение "unlimited", которое в случае со столбцом **varchar (max)** равно 0.</span><span class="sxs-lookup"><span data-stu-id="62b3a-145">The value "unlimited" which in the case of a **varchar(max)** column equals 0.</span></span>  
  
 <span data-ttu-id="62b3a-146">Стандартные правила преобразования применяются к столбцу типа **varchar (max)** , что означает, что любое преобразование, допустимое для столбца **varchar (** 2000 **)** , также будет допустимым для столбца **varchar (max)** .</span><span class="sxs-lookup"><span data-stu-id="62b3a-146">The standard conversion rules apply to a **varchar(max)** column, meaning that any conversion that is valid for a **varchar(** 2000 **)** column will also be valid for a **varchar(max)** column.</span></span> <span data-ttu-id="62b3a-147">То же относится к столбцам **nvarchar(max)** и **varbinary(max)**.</span><span class="sxs-lookup"><span data-stu-id="62b3a-147">The same is true for **nvarchar(max)** and **varbinary(max)** columns.</span></span>  
  
 <span data-ttu-id="62b3a-148">Ниже приведен список функций ODBC API, которые были улучшены для работы с типами больших значений:</span><span class="sxs-lookup"><span data-stu-id="62b3a-148">The following is a list of the ODBC API functions that have been enhanced to work with large value data types:</span></span>  
  
-   [<span data-ttu-id="62b3a-149">SQLBindCol</span><span class="sxs-lookup"><span data-stu-id="62b3a-149">SQLBindCol</span></span>](../../native-client-odbc-api/sqlbindcol.md)  
  
-   [<span data-ttu-id="62b3a-150">SQLBindParameter</span><span class="sxs-lookup"><span data-stu-id="62b3a-150">SQLBindParameter</span></span>](../../native-client-odbc-api/sqlbindparameter.md)  
  
-   [<span data-ttu-id="62b3a-151">SQLColAttribute</span><span class="sxs-lookup"><span data-stu-id="62b3a-151">SQLColAttribute</span></span>](../../native-client-odbc-api/sqlcolattribute.md)  
  
-   [<span data-ttu-id="62b3a-152">SQLColumns</span><span class="sxs-lookup"><span data-stu-id="62b3a-152">SQLColumns</span></span>](../../native-client-odbc-api/sqlcolumns.md)  
  
-   [<span data-ttu-id="62b3a-153">SQLDescribeCol</span><span class="sxs-lookup"><span data-stu-id="62b3a-153">SQLDescribeCol</span></span>](../../native-client-odbc-api/sqldescribecol.md)  
  
-   [<span data-ttu-id="62b3a-154">SQLDescribeParam</span><span class="sxs-lookup"><span data-stu-id="62b3a-154">SQLDescribeParam</span></span>](../../native-client-odbc-api/sqldescribeparam.md)  
  
-   [<span data-ttu-id="62b3a-155">SQLGetData</span><span class="sxs-lookup"><span data-stu-id="62b3a-155">SQLGetData</span></span>](../../native-client-odbc-api/sqlgetdata.md)  
  
-   [<span data-ttu-id="62b3a-156">SQLGetTypeInfo</span><span class="sxs-lookup"><span data-stu-id="62b3a-156">SQLGetTypeInfo</span></span>](../../native-client-odbc-api/sqlgettypeinfo.md)  
  
## <a name="see-also"></a><span data-ttu-id="62b3a-157">См. также:</span><span class="sxs-lookup"><span data-stu-id="62b3a-157">See Also</span></span>  
 [<span data-ttu-id="62b3a-158">Компоненты собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="62b3a-158">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
