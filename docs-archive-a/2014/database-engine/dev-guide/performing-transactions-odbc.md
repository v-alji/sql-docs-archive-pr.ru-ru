---
title: Выполнение транзакций (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, transactions
- transactions [ODBC]
- ODBC, transactions
ms.assetid: f431191a-5762-4f0b-85bb-ac99aff29724
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8abc09c9395225dd653a072fd6c25dadce0849b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750135"
---
# <a name="performing-transactions-odbc"></a><span data-ttu-id="443e9-102">Выполнение транзакций (ODBC)</span><span class="sxs-lookup"><span data-stu-id="443e9-102">Performing Transactions (ODBC)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="443e9-103">и драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживают функции управления транзакциями ODBC API.</span><span class="sxs-lookup"><span data-stu-id="443e9-103">and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver support the ODBC API transaction management functions.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="443e9-104">обеспечивает полную поддержку локальных транзакций на отдельном сервере.</span><span class="sxs-lookup"><span data-stu-id="443e9-104">offers full support for local transactions on an individual server.</span></span> <span data-ttu-id="443e9-105">Драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] использует эти функции для поддержки функций ODBC API, которые управляют транзакциями.</span><span class="sxs-lookup"><span data-stu-id="443e9-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver uses these features to support the ODBC API functions that manage transactions.</span></span>  
  
 <span data-ttu-id="443e9-106">С помощью координатора распределенных транзакций (Майкрософт) драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может принимать участие в распределенных транзакциях, объединяющих несколько серверов.</span><span class="sxs-lookup"><span data-stu-id="443e9-106">Through the use of the Microsoft Distributed Transaction Coordinator (MS DTC), the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver can participate in distributed transactions spanning multiple servers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="443e9-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="443e9-107">In This Section</span></span>  
  
-   [<span data-ttu-id="443e9-108">Транзакции в ODBC</span><span class="sxs-lookup"><span data-stu-id="443e9-108">Transactions in ODBC</span></span>](../../relational-databases/native-client/odbc/performing-transactions-in-odbc.md)  
  
-   [<span data-ttu-id="443e9-109">Выполнение распределенных транзакций</span><span class="sxs-lookup"><span data-stu-id="443e9-109">Performing Distributed Transactions</span></span>](../../relational-databases/native-client-ole-db-transactions/transactions.md)  
  
  
