---
title: SQL Server Native Client компонентов | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- MDAC [SQL Server]
- SQL Server Native Client ODBC driver, about SQL Server Native Client ODBC driver
- SQLNCLI, about SQL Server Native Client
- data access [SQL Server Native Client], features
ms.assetid: 7bb32865-5afb-41ab-98b4-3fa545ee8953
author: rothja
ms.author: jroth
ms.openlocfilehash: bb4ba07f84848f754519f8f4fa1c3e56485e85a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657078"
---
# <a name="sql-server-native-client-features"></a><span data-ttu-id="bfdce-102">Компоненты собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="bfdce-102">SQL Server Native Client Features</span></span>
  <span data-ttu-id="bfdce-103">Помимо возможностей компонентов доступа к данным WDAC (ранее MDAC), в собственном клиенте [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] реализовано множество других функций, позволяющих пользоваться функциональностью [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfdce-103">In addition to exposing features of the Windows (formerly Microsoft) Data Access Components (WDAC), [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client also implements many other features to expose [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bfdce-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="bfdce-104">In This Section</span></span>  
 [<span data-ttu-id="bfdce-105">Изменение поведения драйвера ODBC при обработке преобразования символов</span><span class="sxs-lookup"><span data-stu-id="bfdce-105">ODBC Driver Behavior Change When Handling Character Conversions</span></span>](odbc-driver-behavior-change-when-handling-character-conversions.md)  
 <span data-ttu-id="bfdce-106">Описание изменения поведения, реализованного с версии Native Client [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2012.</span><span class="sxs-lookup"><span data-stu-id="bfdce-106">Discusses a change of behavior beginning in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2012 Native Client.</span></span>  
  
 [<span data-ttu-id="bfdce-107">Использование зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="bfdce-107">Using Database Mirroring</span></span>](using-database-mirroring.md)  
 <span data-ttu-id="bfdce-108">Описывает, как [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] собственный клиент поддерживает использование зеркальных баз данных, то есть возможность сохранения копии или зеркала [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] базы данных на резервном сервере.</span><span class="sxs-lookup"><span data-stu-id="bfdce-108">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports the use of mirrored databases, which is the ability to keep a copy, or mirror, of a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database on a standby server.</span></span>  
  
 [<span data-ttu-id="bfdce-109">Выполнение асинхронных операций</span><span class="sxs-lookup"><span data-stu-id="bfdce-109">Performing Asynchronous Operations</span></span>](performing-asynchronous-operations.md)  
 <span data-ttu-id="bfdce-110">Обсуждение поддержки собственным клиентом [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] асинхронных операций, то есть способности немедленно возвращать управление, не блокируя вызывающий поток.</span><span class="sxs-lookup"><span data-stu-id="bfdce-110">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports asynchronous operations, which is the ability to return immediately without blocking on the calling thread.</span></span>  
  
 [<span data-ttu-id="bfdce-111">Использование множественных активных результирующих наборов (MARS)</span><span class="sxs-lookup"><span data-stu-id="bfdce-111">Using Multiple Active Result Sets &#40;MARS&#41;</span></span>](using-multiple-active-result-sets-mars.md)  
 <span data-ttu-id="bfdce-112">Обсуждение поддержки собственным клиентом [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] режима MARS.</span><span class="sxs-lookup"><span data-stu-id="bfdce-112">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports multiple active result sets (MARS).</span></span> <span data-ttu-id="bfdce-113">Режим MARS позволяет выполнять и получать несколько результирующих наборов через одно подключение к базе данных.</span><span class="sxs-lookup"><span data-stu-id="bfdce-113">MARS enables you to execute and receive multiple result sets using a single database connection</span></span>  
  
 [<span data-ttu-id="bfdce-114">Использование типов данных XML</span><span class="sxs-lookup"><span data-stu-id="bfdce-114">Using XML Data Types</span></span>](using-xml-data-types.md)  
 <span data-ttu-id="bfdce-115">Обсуждение поддержки собственным клиентом [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] типа данных XML (представляющего собой тип данных на основе XML), который можно использовать как тип столбца, переменной, параметра или значения, возвращаемого функцией.</span><span class="sxs-lookup"><span data-stu-id="bfdce-115">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports the XML data type, which is a XML-based data type that can be used as a column type, variable type, parameter type, or function return type.</span></span>  
  
 [<span data-ttu-id="bfdce-116">Использование определяемых пользователем типов данных</span><span class="sxs-lookup"><span data-stu-id="bfdce-116">Using User-Defined Types</span></span>](using-user-defined-types.md)  
 <span data-ttu-id="bfdce-117">Описывает, как [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] собственный клиент поддерживает определяемые пользователем типы, которые расширяют систему типов SQL, позволяя сохранять объекты и пользовательские структуры данных в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] базе данных.</span><span class="sxs-lookup"><span data-stu-id="bfdce-117">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports User-Defined Types (UDT), which extends the SQL type system by allowing you to store objects and custom data structures in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>  
  
 [<span data-ttu-id="bfdce-118">Использование типов больших значений</span><span class="sxs-lookup"><span data-stu-id="bfdce-118">Using Large Value Types</span></span>](using-large-value-types.md)  
 <span data-ttu-id="bfdce-119">Обсуждение поддержки собственным клиентом [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] типов данных больших значений, то есть типов данных больших объектов (LOB).</span><span class="sxs-lookup"><span data-stu-id="bfdce-119">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports large value data types, which are large object data types (LOB).</span></span>  
  
 [<span data-ttu-id="bfdce-120">Смена пароля программным способом</span><span class="sxs-lookup"><span data-stu-id="bfdce-120">Changing Passwords Programmatically</span></span>](changing-passwords-programmatically.md)  
 <span data-ttu-id="bfdce-121">Обсуждение поддержки собственным клиентом [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] управления истекшими паролями с возможностью сменить пароль на клиенте без вмешательства администратора.</span><span class="sxs-lookup"><span data-stu-id="bfdce-121">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports the handling of expired passwords so that passwords can now be changed on the client without administrator involvement.</span></span>  
  
 [<span data-ttu-id="bfdce-122">Работа с изоляцией моментального снимка</span><span class="sxs-lookup"><span data-stu-id="bfdce-122">Working with Snapshot Isolation</span></span>](working-with-snapshot-isolation.md)  
 <span data-ttu-id="bfdce-123">Обсуждение поддержки собственным клиентом [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] расширений управления версиями строк, предназначенных для улучшения производительности путем исключения сценариев блокировки модулей чтения или записи.</span><span class="sxs-lookup"><span data-stu-id="bfdce-123">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports the enhancement to row versioning that improves database performance by avoiding reader-writer blocking scenarios.</span></span>  
  
 [<span data-ttu-id="bfdce-124">Работа с уведомлениями запросов</span><span class="sxs-lookup"><span data-stu-id="bfdce-124">Working with Query Notifications</span></span>](working-with-query-notifications.md)  
 <span data-ttu-id="bfdce-125">Обсуждение поддержки собственным клиентом [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] уведомления потребителя об изменении набора строк.</span><span class="sxs-lookup"><span data-stu-id="bfdce-125">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports consumer notification on rowset modification.</span></span>  
  
 [<span data-ttu-id="bfdce-126">Выполнение операций массового копирования</span><span class="sxs-lookup"><span data-stu-id="bfdce-126">Performing Bulk Copy Operations</span></span>](performing-bulk-copy-operations.md)  
 <span data-ttu-id="bfdce-127">Описывает, как [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] собственный клиент поддерживает операции с массовым копированием, которые позволяют передавать большие объемы данных в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] таблицу или представление или из нее.</span><span class="sxs-lookup"><span data-stu-id="bfdce-127">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports bulk copy operations that allow the transfer of large amounts of data into or out of a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] table or view.</span></span>  
  
 [<span data-ttu-id="bfdce-128">Использование шифрования без проверки</span><span class="sxs-lookup"><span data-stu-id="bfdce-128">Using Encryption Without Validation</span></span>](using-encryption-without-validation.md)  
 <span data-ttu-id="bfdce-129">Обсуждение использования собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] для шифрования данных, передаваемых на сервер, без проверки сертификата.</span><span class="sxs-lookup"><span data-stu-id="bfdce-129">Discusses how to use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client to encrypt data sent to the server without validating the certificate.</span></span>  
  
 [<span data-ttu-id="bfdce-130">Возвращающие табличное значение параметры &#40;SQL Server Native Client&#41;</span><span class="sxs-lookup"><span data-stu-id="bfdce-130">Table-Valued Parameters &#40;SQL Server Native Client&#41;</span></span>](table-valued-parameters-sql-server-native-client.md)  
 <span data-ttu-id="bfdce-131">Обсуждение поддержки собственным клиентом [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] возвращающих табличные значения параметров.</span><span class="sxs-lookup"><span data-stu-id="bfdce-131">Discusses [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client support for the table-valued parameters.</span></span>  
  
 [<span data-ttu-id="bfdce-132">Большие определяемые пользователем типы данных CLR</span><span class="sxs-lookup"><span data-stu-id="bfdce-132">Large CLR User-Defined Types</span></span>](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md)  
 <span data-ttu-id="bfdce-133">Обсуждение поддержки определяемых пользователем типов данных среды CLR.</span><span class="sxs-lookup"><span data-stu-id="bfdce-133">Discusses support for large common language runtime (CLR) user-defined types (UDTs).</span></span>  
  
 [<span data-ttu-id="bfdce-134">Поддержка FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="bfdce-134">FILESTREAM Support</span></span>](filestream-support.md)  
 <span data-ttu-id="bfdce-135">Обсуждается [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] поддержка собственного клиента для расширенного компонента FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="bfdce-135">Discusses [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client support for the enhanced FILESTREAM feature.</span></span>  
  
 [<span data-ttu-id="bfdce-136">Поддержка имени участника-службы (SPN) в клиентских соединениях</span><span class="sxs-lookup"><span data-stu-id="bfdce-136">Service Principal Name &#40;SPN&#41; Support in Client Connections</span></span>](service-principal-name-spn-support-in-client-connections.md)  
 <span data-ttu-id="bfdce-137">Обсуждение расширенной поддержки имен участника-службы (SPN) для проведения взаимной проверки подлинности по всем протоколам.</span><span class="sxs-lookup"><span data-stu-id="bfdce-137">Discusses how support for service principal names (SPNs) has been extended to enable mutual authentication across all protocols.</span></span>  
  
 [<span data-ttu-id="bfdce-138">Поддержка разреженных столбцов в собственном клиенте SQL Server</span><span class="sxs-lookup"><span data-stu-id="bfdce-138">Sparse Columns Support in SQL Server Native Client</span></span>](sparse-columns-support-in-sql-server-native-client.md)  
 <span data-ttu-id="bfdce-139">Обсуждение поддержки собственным клиентом [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] разреженных столбцов.</span><span class="sxs-lookup"><span data-stu-id="bfdce-139">Discusses [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client support for sparse columns.</span></span>  
  
 [<span data-ttu-id="bfdce-140">Улучшения функций даты и времени</span><span class="sxs-lookup"><span data-stu-id="bfdce-140">Date and Time Improvements</span></span>](date-and-time-improvements.md)  
 <span data-ttu-id="bfdce-141">Обсуждение поддержки новых типов данных даты и времени, добавленной в собственный клиент [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfdce-141">Discusses support added to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client for the date and time data types.</span></span>  
  
 [<span data-ttu-id="bfdce-142">Обнаружение метаданных</span><span class="sxs-lookup"><span data-stu-id="bfdce-142">Metadata Discovery</span></span>](metadata-discovery.md)  
 <span data-ttu-id="bfdce-143">Обсуждение улучшений в механизме обнаружения метаданных, внесенных в [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfdce-143">Discusses metadata discovery improvements that were made in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span></span>  
  
 [<span data-ttu-id="bfdce-144">Поддержка UTF-16 в собственном клиенте SQL Server версии 11.0</span><span class="sxs-lookup"><span data-stu-id="bfdce-144">UTF-16 Support in SQL Server Native Client 11.0</span></span>](utf-16-support-in-sql-server-native-client-11-0.md)  
 <span data-ttu-id="bfdce-145">Рассматривает изменение поведения, появившееся в [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfdce-145">Discusses a behavior change introduced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span></span> <span data-ttu-id="bfdce-146">Если при привязке результата столбца или выходного параметра указывается буфер фиксированной длины, а символ `wchar`, записываемый в буфер перед завершающим символом, является старшим символом суррогатной пары, а следующий символ `wchar` является младшим символом суррогатной пары, то клиент Native Client [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] не добавит в буфер старший символ суррогатной пары.</span><span class="sxs-lookup"><span data-stu-id="bfdce-146">If you supply a fixed-length buffer when binding a column result or output parameter and if the `wchar` character written into the buffer before the terminating character is a high surrogate code point of a surrogate pair, and if the next `wchar` character is a low surrogate code point, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client will not add the high surrogate code point to the buffer.</span></span>  
  
 [<span data-ttu-id="bfdce-147">Поддержка высокого уровня доступности и аварийного восстановления собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="bfdce-147">SQL Server Native Client Support for High Availability, Disaster Recovery</span></span>](sql-server-native-client-support-for-high-availability-disaster-recovery.md)  
 <span data-ttu-id="bfdce-148">Описывается настройка приложения для использования функций высокого уровня доступности и аварийного восстановления, появившихся в [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfdce-148">Discusses how your application can be configured to take advantage of the high-availability, disaster recovery features added in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span></span>  
  
 [<span data-ttu-id="bfdce-149">Доступ к диагностическим сведениям в журнале расширенных событий</span><span class="sxs-lookup"><span data-stu-id="bfdce-149">Accessing Diagnostic Information in the Extended Events Log</span></span>](accessing-diagnostic-information-in-the-extended-events-log.md)  
 <span data-ttu-id="bfdce-150">Описывает улучшения, реализованные в клиенте [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, и функции отслеживания данных, которые дают доступ к диагностическим данным в кольцевом буфере и журналах XEvents.</span><span class="sxs-lookup"><span data-stu-id="bfdce-150">Discusses enhancements to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and data tracing that gives you access to diagnostic information in the ring buffer and XEvents log.</span></span>  
  
 [<span data-ttu-id="bfdce-151">Поддержка SQL Server Native Client для LocalDB</span><span class="sxs-lookup"><span data-stu-id="bfdce-151">SQL Server Native Client Support for LocalDB</span></span>](sql-server-native-client-support-for-localdb.md)  
 <span data-ttu-id="bfdce-152">Обсуждение поддержки клиентом Native Client [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] улучшенной функции LocalDB.</span><span class="sxs-lookup"><span data-stu-id="bfdce-152">Discusses [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client support for the LocalDB feature.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfdce-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="bfdce-153">See Also</span></span>  
 <span data-ttu-id="bfdce-154">[SQL Server Native Client программирование](../sql-server-native-client-programming.md) </span><span class="sxs-lookup"><span data-stu-id="bfdce-154">[SQL Server Native Client Programming](../sql-server-native-client-programming.md) </span></span>  
 <span data-ttu-id="bfdce-155">[Разделы руководства по ODBC](../../native-client-odbc-how-to/odbc-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="bfdce-155">[ODBC How-to Topics](../../native-client-odbc-how-to/odbc-how-to-topics.md) </span></span>  
 <span data-ttu-id="bfdce-156">[OLE DB инструкций](../../native-client-ole-db-how-to/ole-db-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="bfdce-156">[OLE DB How-to Topics](../../native-client-ole-db-how-to/ole-db-how-to-topics.md) </span></span>  
 [<span data-ttu-id="bfdce-157">Установка собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="bfdce-157">Installing SQL Server Native Client</span></span>](../applications/installing-sql-server-native-client.md)  
  
  
