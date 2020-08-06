---
title: Улучшения функций даты и времени (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- date/time [OLE DB]
- OLE DB, date/time improvements
ms.assetid: 71614aaf-0fa4-4fe0-b522-68e2e0b66f43
author: rothja
ms.author: jroth
ms.openlocfilehash: 16bb9e98691aea829eb71a16ddabddb371d7bcf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739860"
---
# <a name="date-and-time-improvements-ole-db"></a><span data-ttu-id="901bf-102">Улучшения функций даты и времени (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="901bf-102">Date and Time Improvements (OLE DB)</span></span>
  <span data-ttu-id="901bf-103">В [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] добавлены новые типы данных даты-времени.</span><span class="sxs-lookup"><span data-stu-id="901bf-103">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] introduces new date and time data types.</span></span> <span data-ttu-id="901bf-104">В этом разделе описывается, как эти новые типы предоставляются как расширения в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственном клиенте.</span><span class="sxs-lookup"><span data-stu-id="901bf-104">This section describes how these new types are exposed as extensions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="901bf-105">Общие сведения о [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддержке собственного клиента для новых типов данных даты и времени см. в разделе [улучшения даты и времени](../native-client/features/date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="901bf-105">For an overview of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client support for the new date and time data types, see [Date and Time Improvements](../native-client/features/date-and-time-improvements.md).</span></span> <span data-ttu-id="901bf-106">Пример их использования см. в статье [Использование улучшенных функций даты и времени (OLE DB)](../native-client-ole-db-how-to/use-enhanced-date-and-time-features-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="901bf-106">For a sample, see [Use Enhanced Date and Time Features &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-enhanced-date-and-time-features-ole-db.md).</span></span>  
  
 <span data-ttu-id="901bf-107">Общие сведения о типах данных даты и времени вы найдете в разделе документации [datetime (Transact-SQL)](/sql/t-sql/data-types/datetime-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="901bf-107">For more general information about date and time data types, see [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="901bf-108">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="901bf-108">In This Section</span></span>  
 [<span data-ttu-id="901bf-109">Улучшения поддержки типов данных даты и времени OLE DB</span><span class="sxs-lookup"><span data-stu-id="901bf-109">Data Type Support for OLE DB Date and Time Improvements</span></span>](../../relational-databases/native-client-ole-db-date-time/data-type-support-for-ole-db-date-and-time-improvements.md)  
 <span data-ttu-id="901bf-110">Предоставляет сведения о типах OLE DB ( [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client), поддерживающих [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] типы данных даты и времени.</span><span class="sxs-lookup"><span data-stu-id="901bf-110">Provides information about OLE DB ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client) types that support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date and time data types.</span></span>  
  
 [<span data-ttu-id="901bf-111">Метаданные (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="901bf-111">Metadata &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/metadata-ole-db.md)  
 <span data-ttu-id="901bf-112">Содержит сведения о структуре DBBINDING,, `ICommandWithParameters::GetParameterInfo` , `ICommandWithParameters::SetParameterInfo` `IColumnsRowset::GetColumnsRowset` и I `ColumnsInfo::GetColumnInfo` . Также содержит сведения об обновлениях OLE DB наборах строк схемы.</span><span class="sxs-lookup"><span data-stu-id="901bf-112">Contains information about the DBBINDING structure, `ICommandWithParameters::GetParameterInfo`, `ICommandWithParameters::SetParameterInfo`, `IColumnsRowset::GetColumnsRowset`, and I`ColumnsInfo::GetColumnInfo`. Also provides information about updates to OLE DB schema rowsets.</span></span>  
  
 [<span data-ttu-id="901bf-113">Привязки и преобразования &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="901bf-113">Bindings and Conversions &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client-ole-db-date-time/conversions-ole-db.md)  
 <span data-ttu-id="901bf-114">Описывает правила преобразования существующих и новых типов данных между сервером и клиентом.</span><span class="sxs-lookup"><span data-stu-id="901bf-114">Describes the rules for conversion between server and client for both existing and new date types.</span></span>  
  
 [<span data-ttu-id="901bf-115">Изменения в ходе операции копирования для расширенных типов даты и времени &#40;OLE DB и ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="901bf-115">Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;</span></span>](../../relational-databases/native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md)  
 <span data-ttu-id="901bf-116">Описываются новые возможности даты-времени для поддержки операций массового копирования.</span><span class="sxs-lookup"><span data-stu-id="901bf-116">Describes date/time enhancements to support bulk copy operations.</span></span>  
  
 [<span data-ttu-id="901bf-117">Новые возможности поддержки API OLE DB для функций даты и времени</span><span class="sxs-lookup"><span data-stu-id="901bf-117">OLE DB API Support for Date and Time Enhancements</span></span>](ole-db-api-support-for-date-and-time-enhancements.md)  
 <span data-ttu-id="901bf-118">Описывает API-интерфейсы OLE DB, поддерживающие расширенные возможности типов даты-времени.</span><span class="sxs-lookup"><span data-stu-id="901bf-118">Describes the OLE DB APIs that support enhanced date/time features.</span></span>  
  
 [<span data-ttu-id="901bf-119">Сравнимость для IRowsetFind</span><span class="sxs-lookup"><span data-stu-id="901bf-119">Comparability for IRowsetFind</span></span>](../../relational-databases/native-client-ole-db-date-time/comparability-for-irowsetfind.md)  
 <span data-ttu-id="901bf-120">Описывает типы даты-времени и интерфейс `IRowsetFind`.</span><span class="sxs-lookup"><span data-stu-id="901bf-120">Describes date/time types and `IRowsetFind`.</span></span>  
  
 [<span data-ttu-id="901bf-121">Новые функции даты и времени с предыдущими версиями SQL Server &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="901bf-121">New Date and Time Features with Previous SQL Server Versions &#40;OLE DB&#41;</span></span>](new-date-and-time-features-with-previous-sql-server-versions-ole-db.md)  
 <span data-ttu-id="901bf-122">Описывает ожидаемое поведение клиентского приложения, использующего улучшение типы даты и времени, при соединении со старыми версиями [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], а также поведение клиента, скомпилированного со старой версией собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], который отправляет команды на сервер, поддерживающий расширенные возможности даты и времени.</span><span class="sxs-lookup"><span data-stu-id="901bf-122">Describes the expected behavior when a client application that uses enhanced date and time features communicates with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and when a client compiled with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sends commands to a server that supports enhanced date and time features.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="901bf-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="901bf-123">See Also</span></span>  
 [<span data-ttu-id="901bf-124">SQL Server Native Client (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="901bf-124">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
