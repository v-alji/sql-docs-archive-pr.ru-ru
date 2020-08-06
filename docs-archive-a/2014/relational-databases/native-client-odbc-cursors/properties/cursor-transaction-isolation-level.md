---
title: Уровень изоляции транзакций курсора | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- isolation levels [ODBC]
- ODBC applications, row versioning
- cursors [ODBC], isolation levels
- ODBC cursors, isolation levels
- row versioning [SQL Server], ODBC
ms.assetid: 0c6663a4-5a25-44aa-8fe4-e35af9bf4a83
author: rothja
ms.author: jroth
ms.openlocfilehash: 30f3dc8a9136a7cbe1d5897cb0bcc9fff8c35ab2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738363"
---
# <a name="cursor-transaction-isolation-level"></a><span data-ttu-id="1cb03-102">Уровень изоляции транзакций курсора</span><span class="sxs-lookup"><span data-stu-id="1cb03-102">Cursor Transaction Isolation Level</span></span>
  <span data-ttu-id="1cb03-103">Режим полной блокировки курсоров основывается на взаимодействии между атрибутами параллелизма и уровнем изоляции транзакций, установленным клиентом.</span><span class="sxs-lookup"><span data-stu-id="1cb03-103">The complete locking behavior of cursors is based on an interaction between concurrency attributes and the transaction isolation level set by the client.</span></span> <span data-ttu-id="1cb03-104">Клиенты ODBC устанавливают уровень изоляции транзакции с помощью [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) SQL_ATTR_TXN_ISOLATION или атрибутов SQL_COPT_SS_TXN_ISOLATION.</span><span class="sxs-lookup"><span data-stu-id="1cb03-104">ODBC clients set the transaction isolation level using the [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) SQL_ATTR_TXN_ISOLATION or SQL_COPT_SS_TXN_ISOLATION attributes.</span></span> <span data-ttu-id="1cb03-105">Режим блокировки специфической среды курсора определяется комбинацией режимов блокировки параллелизма и параметров уровня изоляции транзакции.</span><span class="sxs-lookup"><span data-stu-id="1cb03-105">The locking behavior of a specific cursor environment is determined by combining the locking behaviors of the concurrency and transaction isolation level options.</span></span>  
  
 <span data-ttu-id="1cb03-106">Драйвер ODBC для собственного клиента поддерживает следующие уровни изоляции транзакций курсора [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="1cb03-106">The following cursor transaction isolation levels are supported by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver:</span></span>  
  
-   <span data-ttu-id="1cb03-107">Зафиксированная операция чтения (SQL_TXN_READ_COMMITTED)</span><span class="sxs-lookup"><span data-stu-id="1cb03-107">Read committed (SQL_TXN_READ_COMMITTED)</span></span>  
  
-   <span data-ttu-id="1cb03-108">Незафиксированная операция чтения (SQL_TXN_READ_COMMITTED)</span><span class="sxs-lookup"><span data-stu-id="1cb03-108">Read uncommitted (SQL_TXN_READ_UNCOMMITTED)</span></span>  
  
-   <span data-ttu-id="1cb03-109">Операция чтения с возможностью повторения (SQL_TXN_REPEATABLE_READ)</span><span class="sxs-lookup"><span data-stu-id="1cb03-109">Repeatable read (SQL_TXN_REPEATABLE_READ)</span></span>  
  
-   <span data-ttu-id="1cb03-110">Сериализуемый (SQL_TXN_SERIALIZABLE)</span><span class="sxs-lookup"><span data-stu-id="1cb03-110">Serializable (SQL_TXN_SERIALIZABLE)</span></span>  
  
-   <span data-ttu-id="1cb03-111">Моментальный снимок (SQL_TXN_SS_SNAPSHOT)</span><span class="sxs-lookup"><span data-stu-id="1cb03-111">Snapshot (SQL_TXN_SS_SNAPSHOT)</span></span>  
  
 <span data-ttu-id="1cb03-112">Обратите внимание, что API ODBC указывает дополнительные уровни изоляции транзакций, но они не поддерживаются [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] или [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] драйвером ODBC для собственного клиента.</span><span class="sxs-lookup"><span data-stu-id="1cb03-112">Note that the ODBC API specifies additional transaction isolation levels, but these are not supported by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cb03-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="1cb03-113">See Also</span></span>  
 [<span data-ttu-id="1cb03-114">Свойства курсора</span><span class="sxs-lookup"><span data-stu-id="1cb03-114">Cursor Properties</span></span>](cursor-properties.md)  
  
  
