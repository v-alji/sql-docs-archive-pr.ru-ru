---
title: Улучшения даты и времени (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- date/time [ODBC]
- ODBC, date/time improvements
ms.assetid: e31d5ca5-2103-498f-954c-1ee93e217186
author: rothja
ms.author: jroth
ms.openlocfilehash: 6ce8f906fc1949a80bfa8e5a541ecf1e83878775
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664158"
---
# <a name="date-and-time-improvements-odbc"></a><span data-ttu-id="2c5bb-102">Улучшения функций даты и времени (ODBC)</span><span class="sxs-lookup"><span data-stu-id="2c5bb-102">Date and Time Improvements (ODBC)</span></span>
  <span data-ttu-id="2c5bb-103">В [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] добавлены новые типы данных даты и времени.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-103">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] introduced new date and time data types.</span></span> <span data-ttu-id="2c5bb-104">В этом разделе описывается, как эти новые типы предоставляются как расширения в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственном клиенте.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-104">This section describes how these new types are exposed as extensions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="2c5bb-105">Общие сведения о [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддержке собственного клиента для новых типов данных даты и времени см. в разделе [улучшения даты и времени](../native-client/features/date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="2c5bb-105">For an overview of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client support for the new date and time data types, see [Date and Time Improvements](../native-client/features/date-and-time-improvements.md).</span></span> <span data-ttu-id="2c5bb-106">Пример, демонстрирующий поддержку даты и времени ODBC, см. в разделе [Использование типов даты и времени](../native-client-odbc-how-to/use-date-and-time-types.md).</span><span class="sxs-lookup"><span data-stu-id="2c5bb-106">For a sample demonstrating ODBC date/time support, see [Use Date and Time Types](../native-client-odbc-how-to/use-date-and-time-types.md).</span></span>  
  
 <span data-ttu-id="2c5bb-107">Общие сведения о типах данных даты и времени вы найдете в разделе документации [datetime (Transact-SQL)](/sql/t-sql/data-types/datetime-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2c5bb-107">For more general information about date and time data types, see [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2c5bb-108">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="2c5bb-108">In This Section</span></span>  
 [<span data-ttu-id="2c5bb-109">Поддержка типов данных для улучшений функций даты и времени ODBC</span><span class="sxs-lookup"><span data-stu-id="2c5bb-109">Data Type Support for ODBC Date and Time Improvements</span></span>](../../relational-databases/native-client-odbc-date-time/data-type-support-for-odbc-date-and-time-improvements.md)  
 <span data-ttu-id="2c5bb-110">Содержит сведения о типах ODBC, которые поддерживают типы данных даты-времени [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c5bb-110">Provides information about ODBC types that support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date and time data types.</span></span>  
  
 [<span data-ttu-id="2c5bb-111">Метаданные &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="2c5bb-111">Metadata &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/metadata-odbc.md)  
 <span data-ttu-id="2c5bb-112">Описывает сведения, возвращенные в полях дескрипторов параметра реализации (IPD) и строки реализации (IRD), а также метаданные столбца, возвращенные `SQLColumns` и `SQLProcedureColumns`.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-112">Describes information returned in the implementation parameter descriptor (IPD) and implementation row descriptor (IRD) fields, as well as column metadata returned by `SQLColumns` and `SQLProcedureColumns`.</span></span> <span data-ttu-id="2c5bb-113">Также описывает метаданные типов данных, возвращенные `SQLGetTypeInfo`.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-113">Also describes data type metadata returned by `SQLGetTypeInfo`.</span></span>  
  
 [<span data-ttu-id="2c5bb-114">Преобразования типов данных DateTime &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="2c5bb-114">datetime Data Type Conversions &#40;ODBC&#41;</span></span>](datetime-data-type-conversions-odbc.md)  
 <span data-ttu-id="2c5bb-115">Описывает, как выполнять преобразование между значениями типа datetime и datetimeoffset.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-115">Describes how to convert between datetime and datetimeoffset values.</span></span>  
  
 [<span data-ttu-id="2c5bb-116">Поддержка sql_variant для типов даты и времени</span><span class="sxs-lookup"><span data-stu-id="2c5bb-116">sql_variant Support for Date and Time Types</span></span>](sql-variant-support-for-date-and-time-types.md)  
 <span data-ttu-id="2c5bb-117">Описывает функцию SQL_VARIANT, поддерживающую улучшенные возможности типов данных даты-времени.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-117">Describes SQL_VARIANT function support for enhanced date and time functionality.</span></span>  
  
 [<span data-ttu-id="2c5bb-118">Изменения в ходе операции копирования для расширенных типов даты и времени &#40;OLE DB и ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="2c5bb-118">Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;</span></span>](../../relational-databases/native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md)  
 <span data-ttu-id="2c5bb-119">Описываются новые возможности даты-времени для поддержки операций массового копирования.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-119">Describes date/time enhancements to support bulk copy operations.</span></span>  
  
 [<span data-ttu-id="2c5bb-120">Улучшенное поведение типов даты и времени с предыдущими версиями SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="2c5bb-120">Enhanced Date and Time Type Behavior with Previous SQL Server Versions &#40;ODBC&#41;</span></span>](enhanced-date-and-time-type-behavior-with-previous-sql-server-versions-odbc.md)  
 <span data-ttu-id="2c5bb-121">Описывает ожидаемое поведение при соединении клиентского приложения, использующего улучшенные возможности типов данных даты-времени со старой версией [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], и при отправке клиентом, скомпилированным с помощью старой версии собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], команд на сервер, который поддерживает улучшенные возможности по работе с данными в формате даты-времени.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-121">Describes the expected behavior when a client application using enhanced date and time features communicates with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and when a client compiled with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sends commands to a server that supports enhanced date and time features.</span></span>  
  
 [<span data-ttu-id="2c5bb-122">Поддержка API-интерфейса ODBC для улучшенных функций даты и времени</span><span class="sxs-lookup"><span data-stu-id="2c5bb-122">ODBC API Support for Enhanced Date and Time Features</span></span>](odbc-api-support-for-enhanced-date-and-time-features.md)  
 <span data-ttu-id="2c5bb-123">Перечисляет функции ODBC, поддерживающие улучшенные возможности даты и времени.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-123">Lists the ODBC functions that support enhanced date and time functionality.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c5bb-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="2c5bb-124">See Also</span></span>  
 [<span data-ttu-id="2c5bb-125">SQL Server Native Client (ODBC)</span><span class="sxs-lookup"><span data-stu-id="2c5bb-125">SQL Server Native Client &#40;ODBC&#41;</span></span>](../../relational-databases/native-client/odbc/sql-server-native-client-odbc.md)  
  
  
