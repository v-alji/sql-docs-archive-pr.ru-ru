---
title: SQLDriverConnect | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLDriverConnect function
ms.assetid: a1e38e2c-3a97-42d1-9c45-a0ca3282ffd1
author: rothja
ms.author: jroth
ms.openlocfilehash: 40691dfb381883b59155607fb56f4933820e3e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736311"
---
# <a name="sqldriverconnect"></a><span data-ttu-id="9e3c3-102">SQLDriverConnect</span><span class="sxs-lookup"><span data-stu-id="9e3c3-102">SQLDriverConnect</span></span>
  <span data-ttu-id="9e3c3-103">Драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] определяет атрибуты соединения, которые заменяют или расширяют ключевые слова строки соединения.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver defines connection attributes that either replace or enhance connection-string keywords.</span></span> <span data-ttu-id="9e3c3-104">Некоторые ключевые слова строки соединения имеют значения по умолчанию, заданные в драйвере ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e3c3-104">Several connection-string keywords have default values specified by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
 <span data-ttu-id="9e3c3-105">Список ключевых слов, доступных в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвере ODBC для собственного клиента, см. в разделе [Использование ключевых слов строки подключения с SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="9e3c3-105">For a list of the keywords available in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, see [Using Connection String Keywords with SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="9e3c3-106">Дополнительные сведения об [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] атрибутах подключения и поведении драйверов по умолчанию см. в разделе [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="9e3c3-106">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection attributes and driver default behaviors, see [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
 <span data-ttu-id="9e3c3-107">Описание ключевых слов строки подключения, допустимых для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственного клиента, см. в разделе [Использование ключевых слов строки подключения с SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="9e3c3-107">For a discussion of connection string keywords that are valid for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, see [Using Connection String Keywords with SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="9e3c3-108">Если параметр `SQLDriverConnect` *DriverCompletion* имеет значение SQL_DRIVER_PROMPT, SQL_DRIVER_COMPLETE или SQL_DRIVER_COMPLETE_REQUIRED, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента получает значения ключевых слов из отображаемого диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-108">When the `SQLDriverConnect`*DriverCompletion* parameter value is SQL_DRIVER_PROMPT, SQL_DRIVER_COMPLETE, or SQL_DRIVER_COMPLETE_REQUIRED, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver retrieves keyword values from the displayed dialog box.</span></span> <span data-ttu-id="9e3c3-109">Если значение ключевого слова передается в строке соединения и пользователь не изменил значение в диалоговом окне, драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] использует значение из строки соединения.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-109">If the keyword value is passed in the connection string and the user does not alter the value for the keyword in the dialog box, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver uses the value from the connection string.</span></span> <span data-ttu-id="9e3c3-110">Если значение не определено в строке соединения, а пользователь не присваивает его в диалоговом окне, драйвер использует значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-110">If the value is not set in the connection string and the user makes no assignment in the dialog box, the driver uses the default.</span></span>  
  
 <span data-ttu-id="9e3c3-111">`SQLDriverConnect`необходимо предоставить допустимый *WindowHandle* , если любое значение *DriverCompletion* требует (или может требовать) Отображение диалогового окна подключения драйвера.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-111">`SQLDriverConnect` must be given a valid *WindowHandle* when any *DriverCompletion* value requires (or could require) the display of the driver's connection dialog box.</span></span> <span data-ttu-id="9e3c3-112">Недопустимый дескриптор возвращает ошибку SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-112">An invalid handle returns SQL_ERROR.</span></span>  
  
 <span data-ttu-id="9e3c3-113">Укажите ключевое слово DRIVER или DSN.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-113">Specify either the DRIVER or DSN keywords.</span></span> <span data-ttu-id="9e3c3-114">Драйвер ODBC использует крайнее левое из этих ключевых слов и пропускает другое, если указаны оба.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-114">ODBC states that a driver uses the leftmost of these two keywords and ignores the other if both are specified.</span></span> <span data-ttu-id="9e3c3-115">Если параметр DRIVER указан или является крайним левым из двух параметров, а `SQLDriverConnect` значение параметра *DriverCompletion* — SQL_DRIVER_NOPROMPT, требуется ключевое слово Server и соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-115">If DRIVER is specified, or is the leftmost of the two, and the `SQLDriverConnect`*DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT, the SERVER keyword and an appropriate value are required.</span></span>  
  
 <span data-ttu-id="9e3c3-116">Если задано значение SQL_DRIVER_NOPROMPT, необходимо указать ключевые слова проверки подлинности пользователя вместе с их значениями.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-116">When SQL_DRIVER_NOPROMPT is specified, user authentication keywords must be present with values.</span></span> <span data-ttu-id="9e3c3-117">Драйвер обеспечивает наличие строки «Trusted_Connection=yes» или обоих ключевых слов UID и PWD.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-117">The driver ensures that either the string "Trusted_Connection=yes" or both the UID and PWD keywords are present.</span></span>  
  
 <span data-ttu-id="9e3c3-118">Если значение параметра *DriverCompletion* равно SQL_DRIVER_NOPROMPT или SQL_DRIVER_COMPLETE_REQUIRED, а язык или база данных поступают из строки подключения и либо являются недопустимыми, и `SQLDriverConnect` возвращает SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-118">If the *DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT or SQL_DRIVER_COMPLETE_REQUIRED and the language or database comes from the connection string and either is invalid, `SQLDriverConnect` returns SQL_ERROR.</span></span>  
  
 <span data-ttu-id="9e3c3-119">Если значение параметра *DriverCompletion* равно SQL_DRIVER_NOPROMPT или SQL_DRIVER_COMPLETE_REQUIRED и язык или база данных поступают из определений источника данных ODBC и либо являются недопустимыми, `SQLDriverConnect` использует язык по умолчанию или базу данных для указанного идентификатора пользователя и возвращает SQL_SUCCESS_WITH_INFO.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-119">If the *DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT or SQL_DRIVER_COMPLETE_REQUIRED and the language or database comes from the ODBC data source definitions and either is invalid, `SQLDriverConnect` uses the default language or database for the specified user ID and returns SQL_SUCCESS_WITH_INFO.</span></span>  
  
 <span data-ttu-id="9e3c3-120">Если значение параметра *DriverCompletion* равно SQL_DRIVER_COMPLETE или SQL_DRIVER_PROMPT и если язык или база данных являются недопустимыми, повторно `SQLDriverConnect` отображает диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-120">If the *DriverCompletion* parameter value is SQL_DRIVER_COMPLETE or SQL_DRIVER_PROMPT and if the language or database is invalid, `SQLDriverConnect` redisplays the dialog box.</span></span>  
  
## <a name="sqldriverconnect-support-for-high-availability-disaster-recovery"></a><span data-ttu-id="9e3c3-121">Поддержка высокого уровня доступности и аварийного восстановления SQLDriverConnect</span><span class="sxs-lookup"><span data-stu-id="9e3c3-121">SQLDriverConnect Support for High Availability, Disaster Recovery</span></span>  
 <span data-ttu-id="9e3c3-122">Дополнительные сведения об использовании `SQLDriverConnect` для подключения к [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] кластеру см. в разделе [Поддержка высокой доступности и аварийного восстановления в SQL Server Native Client](../native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="9e3c3-122">For more information about using `SQLDriverConnect` to connect to a [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] cluster, see [SQL Server Native Client Support for High Availability, Disaster Recovery](../native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md).</span></span>  
  
## <a name="sqldriverconnect-support-for-service-principal-names-spns"></a><span data-ttu-id="9e3c3-123">Поддержка SQLDriverConnect для имен участников-служб (SPN)</span><span class="sxs-lookup"><span data-stu-id="9e3c3-123">SQLDriverConnect Support for Service Principal Names (SPNs)</span></span>  
 <span data-ttu-id="9e3c3-124">Склддриверконнект будет использовать диалоговое окно входа ODBC боксвхен, в котором включен запрос.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-124">SQLDDriverConnect will use the ODBC Login dialog boxwhen prompting is enabled.</span></span> <span data-ttu-id="9e3c3-125">Это позволяет ввести имена участников-служб как для основного сервера, так и для его партнера по обеспечению отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-125">This allows SPNs to be entered for both the principal server and its failover partner.</span></span>  
  
 <span data-ttu-id="9e3c3-126">SQLDriverConnect примет новые ключевые слова строки подключения `ServerSPN` и и `FailoverPartnerSPN` будет распознавать новые атрибуты соединения SQL_COPT_SS_SERVER_SPN и SQL_COPT_SS_FAILOVER_PARTNER_SPN.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-126">SQLDriverConnect will accept the new connection string keywords `ServerSPN` and `FailoverPartnerSPN`, and will recognize the new connection attributes SQL_COPT_SS_SERVER_SPN and SQL_COPT_SS_FAILOVER_PARTNER_SPN.</span></span>  
  
 <span data-ttu-id="9e3c3-127">Если значение атрибута соединения задано более одного раза, приоритет получает программно установленное значение, а не значение в DSN или строке соединения.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-127">When a connection attribute value is specified more than once, a value that is set programmatically takes precedence over the value in a DSN and a value in a connection string.</span></span> <span data-ttu-id="9e3c3-128">Значение DSN имеет приоритет над значением в строке соединения.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-128">A value in a DSN takes precedence over a value in a connection string.</span></span>  
  
 <span data-ttu-id="9e3c3-129">При открытии соединения собственный клиент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] задает SQL_COPT_SS_MUTUALLY_AUTHENTICATED и SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD метод проверки подлинности, используемый для открытия соединения.</span><span class="sxs-lookup"><span data-stu-id="9e3c3-129">When a connection is opened, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sets SQL_COPT_SS_MUTUALLY_AUTHENTICATED and SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD to the authentication method used to open the connection.</span></span>  
  
 <span data-ttu-id="9e3c3-130">Дополнительные сведения о SPN см. [в статье имена субъектов-служб &#40;имен участников-служб&#41; в клиентских подключениях &#40;&#41;ODBC ](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="9e3c3-130">For more information about SPNs, see [Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="9e3c3-131">Примеры</span><span class="sxs-lookup"><span data-stu-id="9e3c3-131">Examples</span></span>  
 <span data-ttu-id="9e3c3-132">Следующий вызов иллюстрирует наименьший объем данных, необходимых для `SQLDriverConnect` :</span><span class="sxs-lookup"><span data-stu-id="9e3c3-132">The following call illustrates the least amount of data required for `SQLDriverConnect`:</span></span>  
  
```  
SQLDriverConnect(hdbc, hwnd,  
    (SQLTCHAR*) TEXT("DRIVER={SQL Server Native Client 10};"), SQL_NTS, szOutConn,  
    MAX_CONN_OUT, &cbOutConn, SQL_DRIVER_COMPLETE);  
```  
  
 <span data-ttu-id="9e3c3-133">Следующие строки подключения иллюстрируют минимальные необходимые данные, если значение параметра *DriverCompletion* равно SQL_DRIVER_NOPROMPT:</span><span class="sxs-lookup"><span data-stu-id="9e3c3-133">The following connection strings illustrate minimum required data when the *DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT:</span></span>  
  
```  
"DSN=Human Resources;Trusted_Connection=yes"  
  
"FILEDSN=HR_FDSN;Trusted_Connection=yes"  
  
"DRIVER={SQL Server Native Client 10};SERVER=(local);Trusted_Connection=yes"  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e3c3-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="9e3c3-134">See Also</span></span>  
 <span data-ttu-id="9e3c3-135">[Функция SQLDriverConnect](https://go.microsoft.com/fwlink/?LinkId=59340) </span><span class="sxs-lookup"><span data-stu-id="9e3c3-135">[SQLDriverConnect Function](https://go.microsoft.com/fwlink/?LinkId=59340) </span></span>  
 <span data-ttu-id="9e3c3-136">[Сведения о реализации API ODBC](odbc-api-implementation-details.md) </span><span class="sxs-lookup"><span data-stu-id="9e3c3-136">[ODBC API Implementation Details](odbc-api-implementation-details.md) </span></span>  
 <span data-ttu-id="9e3c3-137">[SET ANSI_NULLS (Transact-SQL)](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9e3c3-137">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span></span>  
 <span data-ttu-id="9e3c3-138">[SET ANSI_PADDING (Transact-SQL)](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9e3c3-138">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span></span>  
 [<span data-ttu-id="9e3c3-139">SET ANSI_WARNINGS (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9e3c3-139">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-ansi-warnings-transact-sql)  
  
  
