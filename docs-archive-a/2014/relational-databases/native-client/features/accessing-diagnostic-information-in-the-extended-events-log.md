---
title: Доступ к диагностическим сведениям в журнале расширенных событий | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: aaa180c2-5e1a-4534-a125-507c647186ab
author: rothja
ms.author: jroth
ms.openlocfilehash: 5148683d464f06e8a4f52cc924baaacac9102b12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730613"
---
# <a name="accessing-diagnostic-information-in-the-extended-events-log"></a><span data-ttu-id="cb2bd-102">Доступ к диагностическим сведениям в журнале расширенных событий</span><span class="sxs-lookup"><span data-stu-id="cb2bd-102">Accessing Diagnostic Information in the Extended Events Log</span></span>
  <span data-ttu-id="cb2bd-103">Начиная с версии [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], Native Client [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и отслеживание доступа к данным ([Трассировка доступа к данным](https://go.microsoft.com/fwlink/?LinkId=125805)) обновлены. Упрощено получение диагностических сведений об ошибках подключения из кольцевого буфера соединений и сведений о производительности приложений из журнала расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-103">Beginning in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and data access tracing ([Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805)) have been updated to make it easier to get diagnostic information about connection failures from the connectivity ring buffer and application performance information from the extended events log.</span></span>  
  
 <span data-ttu-id="cb2bd-104">Дополнительные сведения о чтении журнала расширенных событий см. в разделе [View Event Session Data](../../../database-engine/view-event-session-data.md).</span><span class="sxs-lookup"><span data-stu-id="cb2bd-104">For information about reading the extended events log, see [View Event Session Data](../../../database-engine/view-event-session-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cb2bd-105">Эта функция предназначена только для диагностики и устранения неполадок; она может оказаться неприменимой для целей аудита или обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-105">This feature is intended only for troubleshooting and diagnostic purposes and may not be suitable for auditing or security purposes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb2bd-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="cb2bd-106">Remarks</span></span>  
 <span data-ttu-id="cb2bd-107">Для операций подключения собственный клиент [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] будет отправлять идентификатор подключения клиента.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-107">For connection operations, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client will send a client connection ID.</span></span> <span data-ttu-id="cb2bd-108">В случае сбоя подключения можно получить доступ к кольцевому буферу подключения ([Устранение неполадок подключения в SQL Server 2008 с помощью кольцевого буфера подключения](https://go.microsoft.com/fwlink/?LinkId=207752)), найти `ClientConnectionID` поле и получить диагностические сведения об ошибке подключения.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-108">If the connection fails, you can access the connectivity ring buffer ([Connectivity troubleshooting in SQL Server 2008 with the Connectivity Ring Buffer](https://go.microsoft.com/fwlink/?LinkId=207752)) and find the `ClientConnectionID` field and get diagnostic information about the connection failure.</span></span> <span data-ttu-id="cb2bd-109">Идентификаторы подключений клиентов регистрируются в кольцевом буфере только при возникновении ошибки.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-109">Client connection IDs are logged in the ring buffer only if an error occurs.</span></span> <span data-ttu-id="cb2bd-110">(Если подключение завершилось сбоем до отправки предварительного пакета входа, то идентификатор подключения клиента не формируется.) Идентификатор клиентского соединения — это 16-байтовый идентификатор GUID.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-110">(If a connection fails before sending the prelogin packet, a client connection ID will not be generated.) The client connection ID is a 16-byte GUID.</span></span> <span data-ttu-id="cb2bd-111">Идентификатор подключения клиента также можно найти в расположении вывода расширенных событий, если действие `client_connection_id` добавляется к событиям в сеансе расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-111">You can also find the client connection ID in the extended events output target, if the `client_connection_id` action is added to events in an extended events session.</span></span> <span data-ttu-id="cb2bd-112">Если необходима дополнительная помощь в диагностике, то можно включить отслеживание доступа к данным и повторно выполнить команду соединения, а затем отследить в поле `ClientConnectionID` в трассировке доступа к данным операцию, завершившуюся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-112">You can enable data access tracing and rerun the connection command and observe the `ClientConnectionID` field in the data access trace for a failed operation, if you need further diagnostic assistance.</span></span>  
  
 <span data-ttu-id="cb2bd-113">Если вы используете ODBC в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] собственном клиенте и соединение выполняется, можно получить идентификатор подключения клиента с помощью `SQL_COPT_SS_CLIENT_CONNECTION_ID` атрибута с [SQLGetConnectAttr](../../native-client-odbc-api/sqlgetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="cb2bd-113">If you are using ODBC in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and a connection succeeds, you can get the client connection ID by using the `SQL_COPT_SS_CLIENT_CONNECTION_ID` attribute with [SQLGetConnectAttr](../../native-client-odbc-api/sqlgetconnectattr.md).</span></span>  
  
 <span data-ttu-id="cb2bd-114">Собственный клиент [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] также отправляет идентификатор активности конкретного потока.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-114">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client also sends a thread-specific activity ID.</span></span> <span data-ttu-id="cb2bd-115">Идентификатор активности регистрируется в сеансах расширенных событий, если сеанс запущен со включенным параметром TRACK_CAUSAILITY.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-115">The activity ID is captured in the extended events sessions if the sessions are started with the TRACK_CAUSAILITY option enabled.</span></span> <span data-ttu-id="cb2bd-116">Если возникли проблемы производительности, связанные с активным соединением, то можно получить идентификатор активности из трассировки доступа клиента к данным (поле `ActivityID`) и найти идентификатор активности в выходных данных расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-116">For performance issues with an active connection, you can get the activity ID from the client's data access trace (`ActivityID` field) and then locate the activity ID in the extended events output.</span></span> <span data-ttu-id="cb2bd-117">Идентификатор активности в расширенном событии — это 16-байтовый идентификатор GUID (не совпадающий с идентификатором GUID подключения клиента), к которому добавлен четырехбайтовый номер последовательности.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-117">The activity ID in the extended events is a 16-byte GUID (not the same as the GUID for the client connection ID) appended with a four-byte sequence number.</span></span> <span data-ttu-id="cb2bd-118">Номер последовательности представляет порядок запроса в потоке и указывает относительный порядок пакетных инструкций и инструкций RPC для данного потока.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-118">The sequence number represents the order of a request within a thread and indicates the relative ordering of batch and RPC statements for the thread.</span></span> <span data-ttu-id="cb2bd-119">Идентификатор `ActivityID` также может отправляться для пакетных инструкций SQL и запросов RPC, если отслеживание доступа к данным включено, а 18-й бит слова конфигурации отслеживания доступа к данным установлен.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-119">The `ActivityID` is optionally sent for SQL batch statements and RPC requests when data access tracing is enabled on and the 18th bit in the data access tracing configuration word is turned ON.</span></span>  
  
 <span data-ttu-id="cb2bd-120">В следующем образце код [!INCLUDE[tsql](../../../includes/tsql-md.md)] служит для запуска сеанса расширенных событий, который будет сохраняться в кольцевом буфере и регистрировать идентификаторы активности, отправляемые с клиента при выполнении операций RPC и пакетных операций.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-120">The following is a sample that uses [!INCLUDE[tsql](../../../includes/tsql-md.md)] to start an extended events session that will be stored in a ring buffer and will record the activity ID sent from a client on RPC and batch operations.</span></span>  
  
```  
create event session MySession on server   
add event connectivity_ring_buffer_recorded,   
add event sql_statement_starting (action (client_connection_id)),   
add event sql_statement_completed (action (client_connection_id)),   
add event rpc_starting (action (client_connection_id)),   
add event rpc_completed (action (client_connection_id))  
add target ring_buffer with (track_causality=on)  
  
```  
  
## <a name="control-file"></a><span data-ttu-id="cb2bd-121">Управляющий файл</span><span class="sxs-lookup"><span data-stu-id="cb2bd-121">Control File</span></span>  
 <span data-ttu-id="cb2bd-122">В [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]управляющий файл собственного клиента SQL Server (ctrl.guid.snac11) содержит следующие данные:</span><span class="sxs-lookup"><span data-stu-id="cb2bd-122">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], the contents of the SQL Server Native  Client control file (ctrl.guid.snac11) is:</span></span>  
  
```  
{8B98D3F2-3CC6-0B9C-6651-9649CCE5C752}  0x00000000  0   MSDADIAG.ETW  
{2DA81B52-908E-7DB6-EF81-76856BB47C4F}  0xFFFFFFFF  0   SQLNCLI11.1  
```  
  
## <a name="mof-file"></a><span data-ttu-id="cb2bd-123">MOF-файл</span><span class="sxs-lookup"><span data-stu-id="cb2bd-123">MOF File</span></span>  
 <span data-ttu-id="cb2bd-124">В [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]MOF-файл собственного клиента SQL Server содержит следующие данные:</span><span class="sxs-lookup"><span data-stu-id="cb2bd-124">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], the contents of the SQL Server Native  Client mof file is:</span></span>  
  
```  
#pragma classflags("forceupdate")  
#pragma namespace ("\\\\.\\Root\\WMI")  
  
/////////////////////////////////////////////////////////////////////////////  
//  
//  MSDADIAG.ETW  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW"),  
 Guid("{8B98D3F2-3CC6-0B9C-6651-9649CCE5C752}"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW : EventTrace  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW"),  
 Guid("{8B98D3F3-3CC6-0B9C-6651-9649CCE5C752}"),  
 DisplayName("msdadiag"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW_Trace : Bid2Etw_MSDADIAG_ETW  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW formatted output (A)"),  
 EventType(17),  
 EventTypeName("TextA"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW_Trace_TextA : Bid2Etw_MSDADIAG_ETW_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringA"),  
     extension("RString"),  
     read  
    ]  
    object msgStr;  
};  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW formatted output (W)"),  
 EventType(18),  
 EventTypeName("TextW"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW_Trace_TextW : Bid2Etw_MSDADIAG_ETW_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringW"),  
     extension("RWString"),  
     read  
    ]  
    object msgStr;  
};  
  
/////////////////////////////////////////////////////////////////////////////  
//  
//  SQLNCLI11.1  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1"),  
 Guid("{2DA81B52-908E-7DB6-EF81-76856BB47C4F}"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1 : EventTrace  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1"),  
 Guid("{2DA81B53-908E-7DB6-EF81-76856BB47C4F}"),  
 DisplayName("SQLNCLI11.1"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1_Trace : Bid2Etw_SQLNCLI11_1  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1 formatted output (A)"),  
 EventType(17),  
 EventTypeName("TextA"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1_Trace_TextA : Bid2Etw_SQLNCLI11_1_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringA"),  
     extension("RString"),  
     read  
    ]  
    object msgStr;  
};  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1 formatted output (W)"),  
 EventType(18),  
 EventTypeName("TextW"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1_Trace_TextW : Bid2Etw_SQLNCLI11_1_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringW"),  
     extension("RWString"),  
     read  
    ]  
    object msgStr;  
};  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb2bd-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="cb2bd-125">See Also</span></span>  
 [<span data-ttu-id="cb2bd-126">Обработка ошибок и сообщений</span><span class="sxs-lookup"><span data-stu-id="cb2bd-126">Handling Errors and Messages</span></span>](../../native-client-odbc-error-messages/handling-errors-and-messages.md)  
  
  
