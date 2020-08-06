---
title: Выполнение распределенных транзакций | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- MS DTC, performing distributed transactions
- SQL Server Native Client ODBC driver, transactions
- distributed transactions [ODBC]
- transactions [ODBC]
- ODBC, transactions
ms.assetid: 2c17fba0-7a3c-453c-91b7-f801e7b39ccb
author: rothja
ms.author: jroth
ms.openlocfilehash: 9ec23fd1883749e35e67f888e26bdf031ccf7fb8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657069"
---
# <a name="performing-distributed-transactions"></a><span data-ttu-id="a1e4d-102">Выполнение распределенных транзакций</span><span class="sxs-lookup"><span data-stu-id="a1e4d-102">Performing Distributed Transactions</span></span>
  <span data-ttu-id="a1e4d-103">С помощью координатора распределенных транзакций (Майкрософт) (MS DTC) приложения могут распространять транзакции на два или более экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1e4d-103">The Microsoft Distributed Transaction Coordinator (MS DTC) allows applications to extend transactions across two or more instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a1e4d-104">Он также позволяет приложениям участвовать в транзакциях, выполняющихся под управлением диспетчеров транзакций, которые соответствуют стандарту Open Group DTP XA.</span><span class="sxs-lookup"><span data-stu-id="a1e4d-104">It also allows applications to participate in transactions managed by transaction managers that comply with the Open Group DTP XA standard.</span></span>  
  
 <span data-ttu-id="a1e4d-105">Обычно все команды управления транзакциями отправляются на сервер через драйвер ODBC собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1e4d-105">Normally, all transaction management commands are sent through the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver to the server.</span></span> <span data-ttu-id="a1e4d-106">Приложение запускает транзакцию, вызывая [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) с отключенным режимом автоматической фиксации.</span><span class="sxs-lookup"><span data-stu-id="a1e4d-106">The application starts a transaction by calling [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) with the autocommit mode turned off.</span></span> <span data-ttu-id="a1e4d-107">Затем приложение выполняет обновления, составляющие транзакцию, и вызывает [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) с параметром SQL_COMMIT или SQL_ROLLBACK.</span><span class="sxs-lookup"><span data-stu-id="a1e4d-107">The application then performs the updates comprising the transaction and calls [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) with either the SQL_COMMIT or SQL_ROLLBACK option.</span></span>  
  
 <span data-ttu-id="a1e4d-108">Однако при использовании MS DTC диспетчер транзакций координатор MS DTC перестает использовать **SQLEndTran**.</span><span class="sxs-lookup"><span data-stu-id="a1e4d-108">When using MS DTC, however, MS DTC becomes the transaction manager and the application no longer uses **SQLEndTran**.</span></span>  
  
 <span data-ttu-id="a1e4d-109">В случае прикрепления к одной распределенной транзакции, а затем ко второй драйвер ODBC Native Client [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] покидает исходную распределенную транзакцию и прикрепляется к новой транзакции.</span><span class="sxs-lookup"><span data-stu-id="a1e4d-109">When enlisted in a distributed transaction, and then enlist in a second distributed transaction, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver defects from the original distributed transaction and enlists in the new transaction.</span></span> <span data-ttu-id="a1e4d-110">Дополнительные сведения см. в [справочнике программиста по DTC](https://msdn.microsoft.com/library/ms686108\(VS.85\).aspx).</span><span class="sxs-lookup"><span data-stu-id="a1e4d-110">For more information, see [DTC Programmer's Reference](https://msdn.microsoft.com/library/ms686108\(VS.85\).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1e4d-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="a1e4d-111">See Also</span></span>  
 [<span data-ttu-id="a1e4d-112">Выполнение транзакций &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a1e4d-112">Performing Transactions &#40;ODBC&#41;</span></span>](../../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
  
