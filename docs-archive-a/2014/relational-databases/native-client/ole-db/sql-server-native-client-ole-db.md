---
title: SQL Server Native Client (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, about SQL Server Native Client OLE DB provider
- OLE DB, SQL Server Native Client OLE DB provider
- data access [SQL Server Native Client], OLE DB
- SQLNCLI, OLE DB
- OLE DB
- SQL Server Native Client OLE DB provider
- SQL Server Native Client, OLE DB
ms.assetid: da846da4-ec19-4a4f-81fb-7d5a2b2bf80a
author: rothja
ms.author: jroth
ms.openlocfilehash: 46b948eb1d075edc6000849dcb2d18ea372809d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658226"
---
# <a name="sql-server-native-client-ole-db"></a><span data-ttu-id="db88c-102">Собственный клиент SQL Server (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="db88c-102">SQL Server Native Client (OLE DB)</span></span>
  <span data-ttu-id="db88c-103">Поставщик OLE DB для собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] — это низкоуровневый API-интерфейс COM, используемый для доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="db88c-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is a low-level COM API that is used for accessing data.</span></span> <span data-ttu-id="db88c-104">Поставщик OLE DB для собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] рекомендуется для разработки средств, программ и низкоуровневых компонентов, требующих высокой производительности.</span><span class="sxs-lookup"><span data-stu-id="db88c-104">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is recommended for developing tools, utilities, or low-level components that need high performance.</span></span> <span data-ttu-id="db88c-105">Поставщик OLE DB для собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] — собственный, высокопроизводительный поставщик, который напрямую обращается к протоколу потока табличных данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db88c-105">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is a native, high performance provider that accesses the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Tabular Data Stream (TDS) protocol directly.</span></span>  
  
 <span data-ttu-id="db88c-106">Собственный клиент [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] обеспечивает поддержку OLE DB для приложений, соединяющихся с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db88c-106">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client provides OLE DB support to applications connecting to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="db88c-107">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента — это поставщик, соответствующий OLE DB версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="db88c-107">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is an OLE DB version 2.0-compliant provider.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="db88c-108">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="db88c-108">In This Section</span></span>  
  
-   [<span data-ttu-id="db88c-109">Создание приложения поставщика OLE DB для собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="db88c-109">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](../../native-client-ole-db-provider/creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
-   [<span data-ttu-id="db88c-110">Объекты источников данных (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="db88c-110">Data Source Objects &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-data-source-objects/data-source-objects-ole-db.md)  
  
-   [<span data-ttu-id="db88c-111">Команды</span><span class="sxs-lookup"><span data-stu-id="db88c-111">Commands</span></span>](../../native-client-ole-db-commands/commands.md)  
  
-   [<span data-ttu-id="db88c-112">Наборы строк</span><span class="sxs-lookup"><span data-stu-id="db88c-112">Rowsets</span></span>](../../native-client-ole-db-rowsets/rowsets.md)  
  
-   [<span data-ttu-id="db88c-113">Хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="db88c-113">Stored Procedures</span></span>](stored-procedures.md)  
  
-   [<span data-ttu-id="db88c-114">Большие двоичные объекты и объекты OLE</span><span class="sxs-lookup"><span data-stu-id="db88c-114">BLOBs and OLE Objects</span></span>](../../native-client-ole-db-blobs/blobs-and-ole-objects.md)  
  
-   [<span data-ttu-id="db88c-115">Таблицы и индексы</span><span class="sxs-lookup"><span data-stu-id="db88c-115">Tables and Indexes</span></span>](../../native-client-ole-db-tables-indexes/tables-and-indexes.md)  
  
-   [<span data-ttu-id="db88c-116">Типы данных (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="db88c-116">Data Types &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-data-types/data-types-ole-db.md)  
  
-   [<span data-ttu-id="db88c-117">Поддержка набора строк схемы &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="db88c-117">Schema Rowset Support &#40;OLE DB&#41;</span></span>](schema-rowset-support-ole-db.md)  
  
-   [<span data-ttu-id="db88c-118">Возвращающие табличные значения параметры &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="db88c-118">Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md)  
  
-   [<span data-ttu-id="db88c-119">Улучшения функций даты и времени &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="db88c-119">Date and Time Improvements &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-date-time/date-and-time-improvements-ole-db.md)  
  
-   [<span data-ttu-id="db88c-120">Большие определяемые пользователем типы данных CLR &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="db88c-120">Large CLR User-Defined Types &#40;OLE DB&#41;</span></span>](large-clr-user-defined-types-ole-db.md)  
  
-   [<span data-ttu-id="db88c-121">Поддержка FILESTREAM &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="db88c-121">FILESTREAM Support &#40;OLE DB&#41;</span></span>](filestream-support-ole-db.md)  
  
-   [<span data-ttu-id="db88c-122">Транзакции</span><span class="sxs-lookup"><span data-stu-id="db88c-122">Transactions</span></span>](../../native-client-ole-db-transactions/transactions.md)  
  
-   [<span data-ttu-id="db88c-123">ошибки</span><span class="sxs-lookup"><span data-stu-id="db88c-123">Errors</span></span>](../../native-client-ole-db-errors/errors.md)  
  
-   [<span data-ttu-id="db88c-124">Имена участника-службы (SPN) в клиентских соединениях (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="db88c-124">Service Principal Names &#40;SPNs&#41; in Client Connections &#40;OLE DB&#41;</span></span>](service-principal-names-spns-in-client-connections-ole-db.md)  
  
-   [<span data-ttu-id="db88c-125">Поддержка разреженных столбцов &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="db88c-125">Sparse Columns Support &#40;OLE DB&#41;</span></span>](sparse-columns-support-ole-db.md)  
  
-   [<span data-ttu-id="db88c-126">Справочник по SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="db88c-126">SQL Server Native Client &#40;OLE DB&#41; Reference</span></span>](../../native-client-ole-db-interfaces/sql-server-native-client-ole-db-interfaces.md)  
  
-   [<span data-ttu-id="db88c-127">Инструкции по OLE DB</span><span class="sxs-lookup"><span data-stu-id="db88c-127">OLE DB How-to Topics</span></span>](../../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
## <a name="see-also"></a><span data-ttu-id="db88c-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="db88c-128">See Also</span></span>  
 [<span data-ttu-id="db88c-129">Программирование собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="db88c-129">SQL Server Native Client Programming</span></span>](../sql-server-native-client-programming.md)  
  
  
