---
title: Использование координатор распределенных транзакций Майкрософт (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- MS DTC, using
ms.assetid: 12a275e1-8c7e-436d-8a4e-b7bee853b35c
author: rothja
ms.author: jroth
ms.openlocfilehash: f7b7da33066a9f4edd01037738ed91155340e6ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658694"
---
# <a name="use-microsoft-distributed-transaction-coordinator-odbc"></a><span data-ttu-id="beb8f-102">Использование координатора распределенных транзакции Майкрософт (ODBC)</span><span class="sxs-lookup"><span data-stu-id="beb8f-102">Use Microsoft Distributed Transaction Coordinator (ODBC)</span></span>
    
### <a name="to-update-two-or-more-sql-servers-by-using-ms-dtc"></a><span data-ttu-id="beb8f-103">Обновление двух и более экземпляров SQL Server с помощью координатора распределенных транзакций (MS DTC)</span><span class="sxs-lookup"><span data-stu-id="beb8f-103">To update two or more SQL Servers by using MS DTC</span></span>  
  
1.  <span data-ttu-id="beb8f-104">Подключитесь к координатору распределенных транзакций (MS DTC), используя функцию DtcGetTransactionManager MS DTC OLE.</span><span class="sxs-lookup"><span data-stu-id="beb8f-104">Connect to MS DTC by using the MS DTC OLE DtcGetTransactionManager function.</span></span> <span data-ttu-id="beb8f-105">Дополнительные сведения о координаторе распределенных транзакций (MS DTC) см. в разделе «Координатор распределенных транзакций (Майкрософт)».</span><span class="sxs-lookup"><span data-stu-id="beb8f-105">For information about MS DTC, see Microsoft Distributed Transaction Coordinator.</span></span>  
  
2.  <span data-ttu-id="beb8f-106">Вызывайте SQL Дриверконнект один раз для каждого устанавливаемого соединения Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="beb8f-106">Call SQL DriverConnect once for each Microsoft SQL Server connection you want to establish.</span></span>  
  
3.  <span data-ttu-id="beb8f-107">Вызовите функцию MS DTC OLE ITransactionDispenser::BeginTransaction, чтобы начать транзакцию координатора распределенных транзакций (MS DTC) и получить объект Transaction, представляющий транзакцию.</span><span class="sxs-lookup"><span data-stu-id="beb8f-107">Call the MS DTC OLE ITransactionDispenser::BeginTransaction function to begin an MS DTC transaction and obtain a Transaction object that represents the transaction.</span></span>  
  
4.  <span data-ttu-id="beb8f-108">Вызовите функцию [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) один или несколько раз для каждого из соединений ODBC, которые необходимо прикрепить к транзакции MS DTC.</span><span class="sxs-lookup"><span data-stu-id="beb8f-108">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) one or more times for each ODBC connection you want to enlist in the MS DTC transaction.</span></span> <span data-ttu-id="beb8f-109">Второй параметр [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) должен иметь значение SQL_ATTR_ENLIST_IN_DTC, а третий параметр должен быть объектом Transaction (полученным на шаге 3).</span><span class="sxs-lookup"><span data-stu-id="beb8f-109">[SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) second parameter must be SQL_ATTR_ENLIST_IN_DTC and third parameter must be the Transaction object (obtained in Step 3).</span></span>  
  
5.  <span data-ttu-id="beb8f-110">Вызовите [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) по одному разу для каждого экземпляра SQL Server, который нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="beb8f-110">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) once for each SQL Server you want to update.</span></span>  
  
6.  <span data-ttu-id="beb8f-111">Вызовите функцию MS DTC OLE ITransaction::Commit, чтобы зафиксировать транзакцию MS DTC.</span><span class="sxs-lookup"><span data-stu-id="beb8f-111">Call the MS DTC OLE ITransaction::Commit function to commit the MS DTC transaction.</span></span> <span data-ttu-id="beb8f-112">Объект Transaction более не действителен.</span><span class="sxs-lookup"><span data-stu-id="beb8f-112">The Transaction object is no longer valid.</span></span>  
  
 <span data-ttu-id="beb8f-113">Чтобы выполнить ряд транзакций MS DTC, повторите шаги с 3 по 6.</span><span class="sxs-lookup"><span data-stu-id="beb8f-113">To perform a series of MS DTC transactions, repeat Steps 3 through 6.</span></span>  
  
 <span data-ttu-id="beb8f-114">Чтобы освободить ссылку на объект Transaction, вызовите функцию MS DTC OLE ITransaction::Return.</span><span class="sxs-lookup"><span data-stu-id="beb8f-114">To release the reference to the Transaction object, call the MS DTC OLE ITransaction::Return function.</span></span>  
  
 <span data-ttu-id="beb8f-115">Чтобы использовать соединение ODBC с транзакцией распределенного координатора транзакций (MS DTC), а затем использовать то же соединение с транзакцией локального SQL Server, вызовите функцию [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) с параметром SQL_DTC_DONE.</span><span class="sxs-lookup"><span data-stu-id="beb8f-115">To use an ODBC connection with an MS DTC transaction, and then use the same connection with a local SQL Server transaction, call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_DTC_DONE.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="beb8f-116">Можно также вызывать [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) и [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) по очереди для каждого экземпляра SQL Server, а не вызывать их описанным выше в шагах 4 и 5 способом.</span><span class="sxs-lookup"><span data-stu-id="beb8f-116">You can also call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) and [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) in turn for each SQL Server instead of calling them as suggested earlier in Steps 4 and 5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beb8f-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="beb8f-117">See Also</span></span>  
 [<span data-ttu-id="beb8f-118">Выполнение транзакций &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="beb8f-118">Performing Transactions &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
  
