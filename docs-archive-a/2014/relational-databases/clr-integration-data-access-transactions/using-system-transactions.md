---
title: Использование System. Transactions | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- TransactionScope class
- Dispose method
- System.Transactions namespace
ms.assetid: 79656ce5-ce46-4c5e-9540-cf9869bd774b
author: rothja
ms.author: jroth
ms.openlocfilehash: 277edd75ea0437dc532ed5672e3c7b8a0569af8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751183"
---
# <a name="using-systemtransactions"></a><span data-ttu-id="fcc23-102">Использование System.Transactions</span><span class="sxs-lookup"><span data-stu-id="fcc23-102">Using System.Transactions</span></span>
  <span data-ttu-id="fcc23-103">Пространство имен `System.Transactions` предоставляет новую платформу транзакций, полностью интегрированную с ADO.NET и со средой CLR [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcc23-103">The `System.Transactions` namespace provides a transaction framework that is fully integrated with ADO.NET and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] common language runtime (CLR) integration.</span></span> <span data-ttu-id="fcc23-104">Класс `System.Transactions.TransactionScope` делает блок кода транзакционным, неявно прикрепляя соединения к распределенной транзакции.</span><span class="sxs-lookup"><span data-stu-id="fcc23-104">The `System.Transactions.TransactionScope` class makes a code block transactional by implicitly enlisting connections in a distributed transaction.</span></span> <span data-ttu-id="fcc23-105">В конце блока `Complete`, перед тем, как выйти из него, необходимо вызвать метод `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="fcc23-105">You must call the `Complete` method at the end of the code block marked by the `TransactionScope`.</span></span> <span data-ttu-id="fcc23-106">Когда выполнение программы покидает блок кода, вызывается метод `Dispose`, что вызывает прерывание транзакции, если не поддерживается метод `Complete`.</span><span class="sxs-lookup"><span data-stu-id="fcc23-106">The `Dispose` method is invoked when program execution leaves a code block, causing the transaction to be discontinued if the `Complete` method is not called.</span></span> <span data-ttu-id="fcc23-107">При возникновении исключения, в результате которого исполнение кода выходит за пределы области действия, транзакция считается неподдерживаемой.</span><span class="sxs-lookup"><span data-stu-id="fcc23-107">If an exception has been thrown that causes the code to leave scope, the transaction is considered to be discontinued.</span></span>  
  
 <span data-ttu-id="fcc23-108">Рекомендуется использовать блок `using`, чтобы гарантировать вызов метода `Dispose` для объекта `TransactionScope` при выходе из блока `using`.</span><span class="sxs-lookup"><span data-stu-id="fcc23-108">We recommend that you employ a `using` block to ensure that the `Dispose` method is called on the `TransactionScope` object when the `using` block is exited.</span></span> <span data-ttu-id="fcc23-109">Неудачная попытка зафиксировать или откатить незавершенные транзакции может значительно снизить производительность, поскольку время ожидания по умолчанию для объекта `TransactionScope` составляет одну минуту.</span><span class="sxs-lookup"><span data-stu-id="fcc23-109">Failure to commit or roll back pending transactions can seriously degrade performance because the default time-out for the `TransactionScope` is one minute.</span></span> <span data-ttu-id="fcc23-110">Если инструкция `using` не используется, необходимо явно выполнить все действия в блоке `Try` и вызвать метод `Dispose` в блоке `Finally`.</span><span class="sxs-lookup"><span data-stu-id="fcc23-110">If you do not use a `using` statement, you must perform all work in a `Try` block and explicitly call the `Dispose` method in the `Finally` block.</span></span>  
  
 <span data-ttu-id="fcc23-111">Если в объекте `TransactionScope` возникает исключение, транзакция помечается как несогласованная и прерывается.</span><span class="sxs-lookup"><span data-stu-id="fcc23-111">If an exception occurs within the `TransactionScope`, the transaction is marked as inconsistent and is abandoned.</span></span> <span data-ttu-id="fcc23-112">При удалении объекта `TransactionScope` будет произведен ее откат.</span><span class="sxs-lookup"><span data-stu-id="fcc23-112">It is rolled back when the `TransactionScope` is disposed.</span></span> <span data-ttu-id="fcc23-113">Если исключений не возникает, то участвующие транзакции будут зафиксированы.</span><span class="sxs-lookup"><span data-stu-id="fcc23-113">If no exception occurs, participating transactions commit.</span></span>  
  
 <span data-ttu-id="fcc23-114">Объект `TransactionScope` следует использовать только при осуществлении доступа к локальным и удаленным источникам данных или внешним диспетчерам ресурсов.</span><span class="sxs-lookup"><span data-stu-id="fcc23-114">`TransactionScope` should be used only when local and remote data sources or external resource managers are being accessed.</span></span> <span data-ttu-id="fcc23-115">Причина этого в том, что блок `TransactionScope` всегда вызывает повышение уровня транзакции, даже если его используют только внутри контекстного соединения.</span><span class="sxs-lookup"><span data-stu-id="fcc23-115">This is because `TransactionScope` always causes transactions to promote, even if it is being used only within a context connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fcc23-116">Класс `TransactionScope` создает транзакцию с уровнем изоляции `System.Transactions.Transaction.IsolationLevel`, равным `Serializable` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fcc23-116">The `TransactionScope` class creates a transaction with a `System.Transactions.Transaction.IsolationLevel` of `Serializable` by default.</span></span> <span data-ttu-id="fcc23-117">В зависимости от приложения уровень изоляции можно понижать во избежание большого количества состязаний данных в приложении.</span><span class="sxs-lookup"><span data-stu-id="fcc23-117">Depending on your application, you might want to consider lowering the isolation level to avoid high contention in your application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fcc23-118">В рамках распределенных транзакций рекомендуется выполнять только операции обновления, вставки и удаления на удаленных серверах, поскольку они потребляют значительные ресурсы базы данных.</span><span class="sxs-lookup"><span data-stu-id="fcc23-118">We recommend that you perform only updates, inserts, and deletes within distributed transactions against remote servers because they consume significant database resources.</span></span> <span data-ttu-id="fcc23-119">Если операция будет выполняться на локальном сервере, использовать распределенную транзакцию не нужно, поскольку достаточно локальной.</span><span class="sxs-lookup"><span data-stu-id="fcc23-119">If the operation is going to be performed on the local server, a distributed transaction is not necessary and a local transaction will suffice.</span></span> <span data-ttu-id="fcc23-120">Инструкции SELECT могут без необходимости блокировать ресурсы базы данных, и в некоторых случаях для выборки может потребоваться использование транзакций.</span><span class="sxs-lookup"><span data-stu-id="fcc23-120">SELECT statements may lock database resources unnecessarily, and in some scenarios it may be necessary to use transactions for selects.</span></span> <span data-ttu-id="fcc23-121">Любые не связанные с базой данных действия должны выполняться за пределами области транзакции, если только в ней не задействованы другие диспетчеры ресурсов транзакций.</span><span class="sxs-lookup"><span data-stu-id="fcc23-121">Any non-database work should be done outside of the scope of the transaction, unless it involves other transacted resource managers.</span></span> <span data-ttu-id="fcc23-122">Хотя исключение в области транзакции препятствует фиксации транзакции, класс `TransactionScope` не имеет возможности отката каких-либо изменений, внесенных кодом за пределами области самой транзакции.</span><span class="sxs-lookup"><span data-stu-id="fcc23-122">Although an exception within the scope of the transaction prevents the transaction from committing, the `TransactionScope` class has no provision for rolling back any changes your code has made outside of the scope of the transaction itself.</span></span> <span data-ttu-id="fcc23-123">При необходимости предпринять какие-либо действия при откате транзакции следует написать собственную реализацию интерфейса `System.Transactions.IEnlistmentNotification` и явно прикрепить его к транзакции.</span><span class="sxs-lookup"><span data-stu-id="fcc23-123">If you need to take some action when the transaction is rolled back, you must write your own implementation of the `System.Transactions.IEnlistmentNotification` interface, and explicitly enlist in the transaction.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcc23-124">Пример</span><span class="sxs-lookup"><span data-stu-id="fcc23-124">Example</span></span>  
 <span data-ttu-id="fcc23-125">Для работы с `System.Transactions` необходима ссылка на файл System.Transactions.dll.</span><span class="sxs-lookup"><span data-stu-id="fcc23-125">To work with `System.Transactions`, you must have a reference to the System.Transactions.dll file.</span></span>  
  
 <span data-ttu-id="fcc23-126">В приведенном примере программного кода демонстрируется создание транзакции, уровень которой может быть повышен в двух разных экземплярах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcc23-126">The following code demonstrates how to create a transaction that can be promoted against two different instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fcc23-127">Эти экземпляры представлены двумя различными объектами `System.Data.SqlClient.SqlConnection`, обернутыми в блок `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="fcc23-127">These instances are represented by two different `System.Data.SqlClient.SqlConnection` objects, which are wrapped in a `TransactionScope` block.</span></span> <span data-ttu-id="fcc23-128">В коде создается блок `TransactionScope` с инструкцией `using` и открывается первое соединение, которое автоматически прикрепляет транзакцию к блоку `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="fcc23-128">The code creates the `TransactionScope` block with a `using` statement, and opens the first connection, which automatically enlists it in the `TransactionScope`.</span></span> <span data-ttu-id="fcc23-129">Изначально транзакция прикрепляется как упрощенная, а не полностью распределенная транзакция.</span><span class="sxs-lookup"><span data-stu-id="fcc23-129">The transaction is initially enlisted as a lightweight transaction, not a full distributed transaction.</span></span> <span data-ttu-id="fcc23-130">В коде предполагается существование условных операторов, которые для краткости опущены.</span><span class="sxs-lookup"><span data-stu-id="fcc23-130">The code assumes the existence of conditional logic (which has been omitted for brevity).</span></span> <span data-ttu-id="fcc23-131">При необходимости открывается второе соединение и также прикрепляется к блоку `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="fcc23-131">It opens the second connection only if it is needed, enlisting it in the `TransactionScope`.</span></span> <span data-ttu-id="fcc23-132">При открытии второго соединения транзакция автоматически повышается до полностью распределенной.</span><span class="sxs-lookup"><span data-stu-id="fcc23-132">When the connection is opened, the transaction is automatically promoted to a full distributed transaction.</span></span> <span data-ttu-id="fcc23-133">Затем в программе вызывается метод `TransactionScope.Complete`, который фиксирует транзакцию.</span><span class="sxs-lookup"><span data-stu-id="fcc23-133">The code then invokes `TransactionScope.Complete`, which commits the transaction.</span></span> <span data-ttu-id="fcc23-134">При выходе из инструкций `using` для соединений эти соединения закрываются.</span><span class="sxs-lookup"><span data-stu-id="fcc23-134">The code disposes of the two connections when exiting the `using` statements for the connections.</span></span> <span data-ttu-id="fcc23-135">При завершении блока `TransactionScope.Dispose` объекта `TransactionScope` в примере кода автоматически вызывается метод `using` класса `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="fcc23-135">The `TransactionScope.Dispose` method for the `TransactionScope` is automatically called at the termination of the `using` block for the `TransactionScope`.</span></span> <span data-ttu-id="fcc23-136">Если в любой точке блока `TransactionScope` возникло исключение, метод `Complete` вызван не будет и при удалении объекта `TransactionScope` будет произведен откат распределенной транзакции.</span><span class="sxs-lookup"><span data-stu-id="fcc23-136">If an exception has been thrown at any point in the `TransactionScope` block, `Complete` does not get called, and the distributed transaction will roll back when the `TransactionScope` is disposed.</span></span>  
  
 <span data-ttu-id="fcc23-137">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fcc23-137">Visual Basic</span></span>  
  
```  
Using transScope As New TransactionScope()  
    Using connection1 As New SqlConnection(connectString1)  
        ' Opening connection1 automatically enlists it in the   
        ' TransactionScope as a lightweight transaction.  
        connection1.Open()  
  
        ' Do work in the first connection.  
  
        ' Assumes conditional logic in place where the second  
        ' connection will only be opened as needed.  
        Using connection2 As New SqlConnection(connectString2)  
            ' Open the second connection, which enlists the   
            ' second connection and promotes the transaction to  
            ' a full distributed transaction.  
            connection2.Open()  
  
            ' Do work in the second connection.  
  
        End Using  
    End Using  
  
    ' Commit the transaction.  
    transScope.Complete()  
End Using  
```  
  
 <span data-ttu-id="fcc23-138">C#</span><span class="sxs-lookup"><span data-stu-id="fcc23-138">C#</span></span>  
  
```  
using (TransactionScope transScope = new TransactionScope())  
{  
    using (SqlConnection connection1 = new   
       SqlConnection(connectString1))  
    {  
        // Opening connection1 automatically enlists it in the   
        // TransactionScope as a lightweight transaction.  
        connection1.Open();  
  
        // Do work in the first connection.  
  
        // Assumes conditional logic in place where the second  
        // connection will only be opened as needed.  
        using (SqlConnection connection2 = new   
            SqlConnection(connectString2))  
        {  
            // Open the second connection, which enlists the   
            // second connection and promotes the transaction to  
            // a full distributed transaction.   
            connection2.Open();  
  
            // Do work in the second connection.  
        }  
    }  
    //  The Complete method commits the transaction.  
    transScope.Complete();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="fcc23-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="fcc23-139">See Also</span></span>  
 [<span data-ttu-id="fcc23-140">Интеграция со средой CLR и транзакции</span><span class="sxs-lookup"><span data-stu-id="fcc23-140">CLR Integration and Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
  
  
