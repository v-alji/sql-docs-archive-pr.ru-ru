---
title: SQLGetConnectAttr | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetConnectAttr function
ms.assetid: 26e4e69a-44fd-45e3-b47a-ae39184f041b
author: rothja
ms.author: jroth
ms.openlocfilehash: f82a0fb71103e811b36280f9722c160791023e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654263"
---
# <a name="sqlgetconnectattr"></a><span data-ttu-id="3e195-102">SQLGetConnectAttr</span><span class="sxs-lookup"><span data-stu-id="3e195-102">SQLGetConnectAttr</span></span>
  <span data-ttu-id="3e195-103">Драйвер ODBC собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] определяет характерные для драйвера атрибуты соединения.</span><span class="sxs-lookup"><span data-stu-id="3e195-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver defines driver-specific connection attributes.</span></span> <span data-ttu-id="3e195-104">Некоторые атрибуты доступны для `SQLGetConnectAttr` , а функция используется для сообщения о текущих параметрах.</span><span class="sxs-lookup"><span data-stu-id="3e195-104">Some of the attributes are available to `SQLGetConnectAttr`, and the function is used to report their current settings.</span></span> <span data-ttu-id="3e195-105">Нельзя быть уверенным в правильности значений этих атрибутов, сообщаемых функцией, до тех пор, пока не будет установлено соединение или атрибут не будет задан при помощи функции [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="3e195-105">The values reported for these attributes are not guaranteed until after a connection has been made or the attribute has been set using [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
 <span data-ttu-id="3e195-106">В этом разделе приведены атрибуты режима только для чтения.</span><span class="sxs-lookup"><span data-stu-id="3e195-106">This topic lists the read only attributes.</span></span> <span data-ttu-id="3e195-107">Сведения о других атрибутах подключения, относящихся к драйверу поставщика ODBC собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , см. в разделе [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="3e195-107">For information about the other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver-specific connection attributes, see [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
## <a name="sql_copt_ss_connection_dead"></a><span data-ttu-id="3e195-108">SQL_COPT_SS_CONNECTION_DEAD</span><span class="sxs-lookup"><span data-stu-id="3e195-108">SQL_COPT_SS_CONNECTION_DEAD</span></span>  
 <span data-ttu-id="3e195-109">Атрибут SQL_COPT_SS_CONNECTION_DEAD сообщает серверу данные о состоянии соединения.</span><span class="sxs-lookup"><span data-stu-id="3e195-109">The SQL_COPT_SS_CONNECTION_DEAD attribute reports the state of a connection to a server.</span></span> <span data-ttu-id="3e195-110">Для определения текущего состояния соединения драйвер запрашивает сеть.</span><span class="sxs-lookup"><span data-stu-id="3e195-110">The driver queries the network for the current state of the connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e195-111">Стандартный атрибут соединения ODBC SQL_ATTR_CONNECTION_DEAD возвращает последнее по времени состояние соединения.</span><span class="sxs-lookup"><span data-stu-id="3e195-111">The standard ODBC connection attribute SQL_ATTR_CONNECTION_DEAD returns the most recent state of the connection.</span></span> <span data-ttu-id="3e195-112">Может оказаться так, что это состояние соединения будет отличаться от текущего.</span><span class="sxs-lookup"><span data-stu-id="3e195-112">This might not be the current connection state.</span></span>  
  
|<span data-ttu-id="3e195-113">Значение</span><span class="sxs-lookup"><span data-stu-id="3e195-113">Value</span></span>|<span data-ttu-id="3e195-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3e195-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3e195-115">SQL_CD_TRUE</span><span class="sxs-lookup"><span data-stu-id="3e195-115">SQL_CD_TRUE</span></span>|<span data-ttu-id="3e195-116">Соединение с сервером потеряно.</span><span class="sxs-lookup"><span data-stu-id="3e195-116">The connection to the server has been lost.</span></span>|  
|<span data-ttu-id="3e195-117">SQL_CD_FALSE</span><span class="sxs-lookup"><span data-stu-id="3e195-117">SQL_CD_FALSE</span></span>|<span data-ttu-id="3e195-118">Соединение открыто и доступно для обработки инструкций.</span><span class="sxs-lookup"><span data-stu-id="3e195-118">The connection is open and available for statement processing.</span></span>|  
  
## <a name="sql_copt_ss_client_connection_id"></a><span data-ttu-id="3e195-119">SQL_COPT_SS_CLIENT_CONNECTION_ID</span><span class="sxs-lookup"><span data-stu-id="3e195-119">SQL_COPT_SS_CLIENT_CONNECTION_ID</span></span>  
 <span data-ttu-id="3e195-120">Атрибут SQL_COPT_SS_CLIENT_CONNECTION_ID извлекает идентификатор соединения клиента, по которому затем производится поиск и обнаружение следующих данных.</span><span class="sxs-lookup"><span data-stu-id="3e195-120">The SQL_COPT_SS_CLIENT_CONNECTION_ID attribute retrieves the client connection ID, which can then be used to locate:</span></span>  
  
-   <span data-ttu-id="3e195-121">Диагностические сведения в журнале XEvents, если он включен.</span><span class="sxs-lookup"><span data-stu-id="3e195-121">Diagnostic information in the XEvents log, when enabled.</span></span>  
  
-   <span data-ttu-id="3e195-122">Сведения об ошибке соединения в кольцевом буфере соединения.</span><span class="sxs-lookup"><span data-stu-id="3e195-122">Connection error information in the connection ring buffer.</span></span>  
  
-   <span data-ttu-id="3e195-123">Диагностические сведения в журналах отслеживания доступа к данным, если они включены.</span><span class="sxs-lookup"><span data-stu-id="3e195-123">Diagnostic information in the data access tracing logs, when enabled.</span></span>  
  
 <span data-ttu-id="3e195-124">Дополнительные сведения см. [в разделе доступ к диагностическим сведениям в журнале расширенных событий](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span><span class="sxs-lookup"><span data-stu-id="3e195-124">For more information, see [Accessing Diagnostic Information in the Extended Events Log](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span></span>  
  
|<span data-ttu-id="3e195-125">Значение</span><span class="sxs-lookup"><span data-stu-id="3e195-125">Value</span></span>|<span data-ttu-id="3e195-126">Описание</span><span class="sxs-lookup"><span data-stu-id="3e195-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3e195-127">SQL_ERROR</span><span class="sxs-lookup"><span data-stu-id="3e195-127">SQL_ERROR</span></span>|<span data-ttu-id="3e195-128">Ошибка соединения</span><span class="sxs-lookup"><span data-stu-id="3e195-128">The connection failed.</span></span>|  
|<span data-ttu-id="3e195-129">SQL_SUCCESS</span><span class="sxs-lookup"><span data-stu-id="3e195-129">SQL_SUCCESS</span></span>|<span data-ttu-id="3e195-130">Подключение выполнено успешно.</span><span class="sxs-lookup"><span data-stu-id="3e195-130">The connection succeeded.</span></span> <span data-ttu-id="3e195-131">Идентификатор соединения клиента будет находиться в выходном буфере.</span><span class="sxs-lookup"><span data-stu-id="3e195-131">The client connection ID will be found in the output buffer.</span></span>|  
  
## <a name="sql_copt_ss_perf_data"></a><span data-ttu-id="3e195-132">SQL_COPT_SS_PERF_DATA</span><span class="sxs-lookup"><span data-stu-id="3e195-132">SQL_COPT_SS_PERF_DATA</span></span>  
 <span data-ttu-id="3e195-133">Атрибут SQL_COPT_SS_PERF_DATA возвращает указатель на структуру SQLPERF, содержащую текущую статистику производительности драйвера.</span><span class="sxs-lookup"><span data-stu-id="3e195-133">The SQL_COPT_SS_PERF_DATA attribute returns a pointer to a SQLPERF structure containing the current driver performance statistics.</span></span> <span data-ttu-id="3e195-134">`SQLGetConnectAttr`Возвращает значение NULL, если ведение журнала производительности не включено.</span><span class="sxs-lookup"><span data-stu-id="3e195-134">`SQLGetConnectAttr` will return NULL if performance logging is not enabled.</span></span> <span data-ttu-id="3e195-135">Драйвер не обновляет статистику в структуре SQLPERF динамически.</span><span class="sxs-lookup"><span data-stu-id="3e195-135">The statistics in the SQLPERF structure are not dynamically updated by the driver.</span></span> <span data-ttu-id="3e195-136">Вызывайте `SQLGetConnectAttr` каждый раз, когда необходимо обновить статистику производительности.</span><span class="sxs-lookup"><span data-stu-id="3e195-136">Call `SQLGetConnectAttr` each time the performance statistics need to be refreshed.</span></span>  
  
|<span data-ttu-id="3e195-137">Значение</span><span class="sxs-lookup"><span data-stu-id="3e195-137">Value</span></span>|<span data-ttu-id="3e195-138">Описание</span><span class="sxs-lookup"><span data-stu-id="3e195-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3e195-139">NULL</span><span class="sxs-lookup"><span data-stu-id="3e195-139">NULL</span></span>|<span data-ttu-id="3e195-140">Ведение журнала производительности не включено.</span><span class="sxs-lookup"><span data-stu-id="3e195-140">Performance logging is not enabled.</span></span>|  
|<span data-ttu-id="3e195-141">Любое другое значение</span><span class="sxs-lookup"><span data-stu-id="3e195-141">Any other value</span></span>|<span data-ttu-id="3e195-142">Указатель на структуру SQLPERF.</span><span class="sxs-lookup"><span data-stu-id="3e195-142">A pointer to a SQLPERF structure.</span></span>|  
  
## <a name="sql_copt_ss_perf_query"></a><span data-ttu-id="3e195-143">SQL_COPT_SS_PERF_QUERY</span><span class="sxs-lookup"><span data-stu-id="3e195-143">SQL_COPT_SS_PERF_QUERY</span></span>  
 <span data-ttu-id="3e195-144">Если запись в журнал данных о длительных запросах включена, то атрибут SQL_COPT_SS_PERF_QUERY возвращает значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="3e195-144">The SQL_COPT_SS_PERF_QUERY attribute returns TRUE if logging of long running queries is enabled.</span></span> <span data-ttu-id="3e195-145">Если запись в журнал данных о запросах неактивна, этот атрибут возвращает значение FALSE.</span><span class="sxs-lookup"><span data-stu-id="3e195-145">The request returns FALSE if query logging is not active.</span></span>  
  
## <a name="sql_copt_ss_user_data"></a><span data-ttu-id="3e195-146">SQL_COPT_SS_USER_DATA</span><span class="sxs-lookup"><span data-stu-id="3e195-146">SQL_COPT_SS_USER_DATA</span></span>  
 <span data-ttu-id="3e195-147">Атрибут SQL_COPT_SS_USER_DATA извлекает указатель на данные пользователя.</span><span class="sxs-lookup"><span data-stu-id="3e195-147">The SQL_COPT_SS_USER_DATA attribute retrieves the user-data pointer.</span></span> <span data-ttu-id="3e195-148">Пользовательские данные хранятся в принадлежащей клиенту памяти и записываются отдельно для каждого соединения.</span><span class="sxs-lookup"><span data-stu-id="3e195-148">User data is stored in client-owned memory and recorded per connection.</span></span> <span data-ttu-id="3e195-149">Если указатель на данные пользователя на задан, что соответствует значению SQL_UD_NOTSET, то возвращается указатель NULL.</span><span class="sxs-lookup"><span data-stu-id="3e195-149">If the user-data pointer has not been set, SQL_UD_NOTSET, a NULL pointer, is returned.</span></span>  
  
|<span data-ttu-id="3e195-150">Значение</span><span class="sxs-lookup"><span data-stu-id="3e195-150">Value</span></span>|<span data-ttu-id="3e195-151">Описание</span><span class="sxs-lookup"><span data-stu-id="3e195-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3e195-152">SQL_UD_NOTSET</span><span class="sxs-lookup"><span data-stu-id="3e195-152">SQL_UD_NOTSET</span></span>|<span data-ttu-id="3e195-153">Указатель на данные пользователя не задан.</span><span class="sxs-lookup"><span data-stu-id="3e195-153">No user-data pointer is set.</span></span>|  
|<span data-ttu-id="3e195-154">Любое другое значение</span><span class="sxs-lookup"><span data-stu-id="3e195-154">Any other value</span></span>|<span data-ttu-id="3e195-155">Указатель на данные пользователя.</span><span class="sxs-lookup"><span data-stu-id="3e195-155">A pointer to the user data.</span></span>|  
  
## <a name="sqlgetconnectattr-support-for-service-principal-names-spns"></a><span data-ttu-id="3e195-156">Поддержка функции SQLGetConnectAttr для имен участников-служб (SPN)</span><span class="sxs-lookup"><span data-stu-id="3e195-156">SQLGetConnectAttr Support for Service Principal Names (SPNs)</span></span>  
 <span data-ttu-id="3e195-157">SQLGetConnectAttr можно использовать для запроса значения новых атрибутов соединения SQL_COPT_SS_SERVER_SPN, SQL_COPT_SS_FAILOVER_PARTNER_SPN, SQL_COPT_SS_MUTUALLY_AUTHENTICATED и SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD.</span><span class="sxs-lookup"><span data-stu-id="3e195-157">SQLGetConnectAttr can be used to query the value of the new connection attributes SQL_COPT_SS_SERVER_SPN, SQL_COPT_SS_FAILOVER_PARTNER_SPN, SQL_COPT_SS_MUTUALLY_AUTHENTICATED, and SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD.</span></span> <span data-ttu-id="3e195-158">(SQLGetConnectOption также можно использовать для запроса этих значений.)</span><span class="sxs-lookup"><span data-stu-id="3e195-158">(SQLGetConnectOption can also be used to query these values.)</span></span>  
  
 <span data-ttu-id="3e195-159">Атрибут SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD доступен только для открытых соединений, в которых используется проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="3e195-159">SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD is only available for open connections that use Windows Authentication.</span></span>  
  
 <span data-ttu-id="3e195-160">Если атрибут SQL_COPT_SS_SERVER_SPN или SQL_COPT_SS_FAILOVER_PARTNER еще не задан, возвращается значение по умолчанию (пустая строка).</span><span class="sxs-lookup"><span data-stu-id="3e195-160">If SQL_COPT_SS_SERVER_SPN or SQL_COPT_SS_FAILOVER_PARTNER has not been set, the default value (an empty string) is returned.</span></span>  
  
 <span data-ttu-id="3e195-161">Дополнительные сведения о SPN см. [в статье имена субъектов-служб &#40;имен участников-служб&#41; в клиентских подключениях &#40;&#41;ODBC ](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="3e195-161">For more information about SPNs, see [Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e195-162">См. также:</span><span class="sxs-lookup"><span data-stu-id="3e195-162">See Also</span></span>  
 <span data-ttu-id="3e195-163">[Функция SQLGetConnectAttr](https://go.microsoft.com/fwlink/?LinkId=59347) </span><span class="sxs-lookup"><span data-stu-id="3e195-163">[SQLGetConnectAttr Function](https://go.microsoft.com/fwlink/?LinkId=59347) </span></span>  
 <span data-ttu-id="3e195-164">[Сведения о реализации API ODBC](odbc-api-implementation-details.md) </span><span class="sxs-lookup"><span data-stu-id="3e195-164">[ODBC API Implementation Details](odbc-api-implementation-details.md) </span></span>  
 <span data-ttu-id="3e195-165">[Настройка QUOTED_IDENTIFIER &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-quoted-identifier-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e195-165">[SET QUOTED_IDENTIFIER &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-quoted-identifier-transact-sql) </span></span>  
 <span data-ttu-id="3e195-166">[SET ANSI_NULLS (Transact-SQL)](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e195-166">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span></span>  
 <span data-ttu-id="3e195-167">[SET ANSI_PADDING (Transact-SQL)](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e195-167">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span></span>  
 [<span data-ttu-id="3e195-168">SET ANSI_WARNINGS (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3e195-168">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-ansi-warnings-transact-sql)  
  
  
