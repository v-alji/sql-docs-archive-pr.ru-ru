---
title: Выделение дескрипторов и подключение к SQL Server (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- handles [ODBC]
- handles [ODBC], connection
- handles [ODBC], about handles
ms.assetid: 6172cd52-9c9a-467d-992f-def07f3f3bb1
author: rothja
ms.author: jroth
ms.openlocfilehash: 615a6dbe966b4c681e9cd4285ff55864d7a13370
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750903"
---
# <a name="allocate-handles-and-connect-to-sql-server-odbc"></a><span data-ttu-id="016f3-102">Выделение дескрипторов и соединение с SQL Server (ODBC)</span><span class="sxs-lookup"><span data-stu-id="016f3-102">Allocate Handles and Connect to SQL Server (ODBC)</span></span>
    
### <a name="to-allocate-handles-and-connect-to-sql-server"></a><span data-ttu-id="016f3-103">Выделение дескрипторов и соединение с SQL Server</span><span class="sxs-lookup"><span data-stu-id="016f3-103">To allocate handles and connect to SQL Server</span></span>  
  
1.  <span data-ttu-id="016f3-104">Включите файлы заголовка ODBC Sql.h, Sqlext.h, Sqltypes.h.</span><span class="sxs-lookup"><span data-stu-id="016f3-104">Include the ODBC header files Sql.h, Sqlext.h, Sqltypes.h.</span></span>  
  
2.  <span data-ttu-id="016f3-105">Включите зависящий от драйвера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] файл заголовка Odbcss.h.</span><span class="sxs-lookup"><span data-stu-id="016f3-105">Include the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver-specific header file, Odbcss.h.</span></span>  
  
3.  <span data-ttu-id="016f3-106">Вызовите [функцию SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) с `HandleType` SQL_HANDLE_ENV, чтобы инициализировать ODBC и выделить обработчик среды.</span><span class="sxs-lookup"><span data-stu-id="016f3-106">Call [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) with a `HandleType` of SQL_HANDLE_ENV to initialize ODBC and allocate an environment handle.</span></span>  
  
4.  <span data-ttu-id="016f3-107">Вызовите [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) , указав `Attribute` для параметра значение SQL_ATTR_ODBC_VERSION и `ValuePtr` Задайте для значение SQL_OV_ODBC3, чтобы указать, что приложение будет использовать вызовы функций формата ODBC 3. x.</span><span class="sxs-lookup"><span data-stu-id="016f3-107">Call [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) with `Attribute` set to SQL_ATTR_ODBC_VERSION and `ValuePtr` set to SQL_OV_ODBC3 to indicate the application will use ODBC 3.x-format function calls.</span></span>  
  
5.  <span data-ttu-id="016f3-108">При необходимости вызовите [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) , чтобы задать другие параметры среды, или вызовите [SQLGetEnvAttr](https://go.microsoft.com/fwlink/?LinkId=58403) , чтобы получить параметры среды.</span><span class="sxs-lookup"><span data-stu-id="016f3-108">Optionally, call [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) to set other environment options, or call [SQLGetEnvAttr](https://go.microsoft.com/fwlink/?LinkId=58403) to get environment options.</span></span>  
  
6.  <span data-ttu-id="016f3-109">Вызовите [функцию SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) с `HandleType` SQL_HANDLE_DBC, чтобы выделить маркер подключения.</span><span class="sxs-lookup"><span data-stu-id="016f3-109">Call [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) with a `HandleType` of SQL_HANDLE_DBC to allocate a connection handle.</span></span>  
  
7.  <span data-ttu-id="016f3-110">При необходимости вызовите [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) , чтобы задать параметры соединения, или вызовите [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) , чтобы получить параметры соединения.</span><span class="sxs-lookup"><span data-stu-id="016f3-110">Optionally, call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) to set connection options, or call [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) to get connection options.</span></span>  
  
8.  <span data-ttu-id="016f3-111">Вызовите SQLConnect, чтобы использовать существующий источник данных для подключения к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="016f3-111">Call SQLConnect to use an existing data source to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="016f3-112">Или</span><span class="sxs-lookup"><span data-stu-id="016f3-112">Or</span></span>  
  
     <span data-ttu-id="016f3-113">Вызовите [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) , чтобы использовать строку подключения для подключения к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="016f3-113">Call [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) to use a connection string to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="016f3-114">Минимальная строка соединения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имеет одну из двух форм:</span><span class="sxs-lookup"><span data-stu-id="016f3-114">A minimum complete [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection string has one of two forms:</span></span>  
  
    ```  
    DSN=dsn_name;Trusted_connection=yes;  
    DRIVER={SQL Server Native Client 10.0};SERVER=server;Trusted_connection=yes;  
    ```  
  
     <span data-ttu-id="016f3-115">Если строка подключения не полная, функция `SQLDriverConnect` может запросить требуемые сведения.</span><span class="sxs-lookup"><span data-stu-id="016f3-115">If the connection string is not complete, `SQLDriverConnect` can prompt for the required information.</span></span> <span data-ttu-id="016f3-116">Это определяется значением, указанным для параметра *DriverCompletion* .</span><span class="sxs-lookup"><span data-stu-id="016f3-116">This is controlled by the value specified for the *DriverCompletion* parameter.</span></span>  
  
     <span data-ttu-id="016f3-117">\- или -</span><span class="sxs-lookup"><span data-stu-id="016f3-117">\- or -</span></span>  
  
     <span data-ttu-id="016f3-118">Вызывайте [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md) несколько раз в итеративном виде для создания строки подключения и подключения к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="016f3-118">Call [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md) multiple times in an iterative fashion to build the connection string and connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
9. <span data-ttu-id="016f3-119">При необходимости вызовите [SQLGetInfo](../native-client-odbc-api/sqlgetinfo.md) , чтобы получить атрибуты и поведение драйвера для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] источника данных.</span><span class="sxs-lookup"><span data-stu-id="016f3-119">Optionally, call [SQLGetInfo](../native-client-odbc-api/sqlgetinfo.md) to get driver attributes and behavior for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source.</span></span>  
  
10. <span data-ttu-id="016f3-120">Выделите и используйте инструкции.</span><span class="sxs-lookup"><span data-stu-id="016f3-120">Allocate and use statements.</span></span>  
  
11. <span data-ttu-id="016f3-121">Вызовите SQLDisconnect, чтобы отключиться от [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и сделать маркер соединения доступным для нового соединения.</span><span class="sxs-lookup"><span data-stu-id="016f3-121">Call SQLDisconnect to disconnect from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and make the connection handle available for a new connection.</span></span>  
  
12. <span data-ttu-id="016f3-122">Вызовите [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) с `HandleType` SQL_HANDLE_DBC, чтобы освободить маркер подключения.</span><span class="sxs-lookup"><span data-stu-id="016f3-122">Call [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) with a `HandleType` of SQL_HANDLE_DBC to free the connection handle.</span></span>  
  
13. <span data-ttu-id="016f3-123">Для освобождения дескриптора среды вызовите функцию `SQLFreeHandle` с параметром `HandleType`, установленным в значение SQL_HANDLE_ENV.</span><span class="sxs-lookup"><span data-stu-id="016f3-123">Call `SQLFreeHandle` with a `HandleType` of SQL_HANDLE_ENV to free the environment handle.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="016f3-124">По возможности используйте аутентификацию Windows.</span><span class="sxs-lookup"><span data-stu-id="016f3-124">When possible, use Windows Authentication.</span></span> <span data-ttu-id="016f3-125">Если проверка подлинности Windows недоступна, запросите у пользователя ввод учетных данных во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="016f3-125">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="016f3-126">Избегайте хранения учетных данных в файле.</span><span class="sxs-lookup"><span data-stu-id="016f3-126">Avoid storing credentials in a file.</span></span> <span data-ttu-id="016f3-127">Если необходимо сохранить учетные данные, зашифруйте их с помощью [API-интерфейса шифрования Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="016f3-127">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
## <a name="example"></a><span data-ttu-id="016f3-128">Пример</span><span class="sxs-lookup"><span data-stu-id="016f3-128">Example</span></span>  
 <span data-ttu-id="016f3-129">В этом примере показано, как вызывать функцию `SQLDriverConnect` для соединения с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] без необходимости в существовании источника данных ODBC.</span><span class="sxs-lookup"><span data-stu-id="016f3-129">This example shows a call to `SQLDriverConnect` to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without requiring an existing ODBC data source.</span></span> <span data-ttu-id="016f3-130">Передача функции `SQLDriverConnect` незавершенной строки соединения приводит к запросу драйвера ODBC к пользователю на ввод отсутствующих сведений.</span><span class="sxs-lookup"><span data-stu-id="016f3-130">By passing an incomplete connection string to `SQLDriverConnect`, it causes the ODBC driver to prompt the user to enter the missing information.</span></span>  
  
```  
#define MAXBUFLEN   255  
  
SQLHENV      henv = SQL_NULL_HENV;  
SQLHDBC      hdbc1 = SQL_NULL_HDBC;  
SQLHSTMT      hstmt1 = SQL_NULL_HSTMT;  
  
SQLCHAR      ConnStrIn[MAXBUFLEN] =  
         "DRIVER={SQL Server Native Client 10.0};SERVER=MyServer";  
  
SQLCHAR      ConnStrOut[MAXBUFLEN];  
SQLSMALLINT   cbConnStrOut = 0;  
  
// Make connection without data source. Ask that driver   
// prompt if insufficient information. Driver returns  
// SQL_ERROR and application prompts user  
// for missing information. Window handle not needed for  
// SQL_DRIVER_NOPROMPT.  
retcode = SQLDriverConnect(hdbc1,      // Connection handle  
                  NULL,         // Window handle  
                  ConnStrIn,      // Input connect string  
                  SQL_NTS,         // Null-terminated string  
                  ConnStrOut,      // Address of output buffer  
                  MAXBUFLEN,      // Size of output buffer  
                  &cbConnStrOut,   // Address of output length  
                  SQL_DRIVER_PROMPT);  
```  
  
  
