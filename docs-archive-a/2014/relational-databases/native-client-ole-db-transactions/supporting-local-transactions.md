---
title: Поддержка локальных транзакций | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- autocommit mode
- transactions [OLE DB]
- ITransactionLocal interface
- SQL Server Native Client OLE DB provider, transactions
- local transactions [OLE DB]
ms.assetid: 78f2e5fc-b6fb-4eda-9f71-991a4d6c4902
author: rothja
ms.author: jroth
ms.openlocfilehash: a9bc11a038e56517aa42619117c371c1319b9ffe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667043"
---
# <a name="supporting-local-transactions"></a><span data-ttu-id="cac71-102">Поддержка локальных транзакций</span><span class="sxs-lookup"><span data-stu-id="cac71-102">Supporting Local Transactions</span></span>
  <span data-ttu-id="cac71-103">Сеанс разделяет область действия транзакции для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственного клиента OLE DB локальной транзакции поставщика.</span><span class="sxs-lookup"><span data-stu-id="cac71-103">A session delimits transaction scope for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider local transaction.</span></span> <span data-ttu-id="cac71-104">Если, в направлении потребителя, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента отправляет запрос к подключенному экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , запрос создает единицу работы для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщика собственного клиента OLE DB.</span><span class="sxs-lookup"><span data-stu-id="cac71-104">When, at the direction of a consumer, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider submits a request to a connected instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the request constitutes a unit of work for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="cac71-105">Локальные транзакции всегда заключают одну или несколько единиц работы на один [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственный клиент OLE DBного сеанса поставщика.</span><span class="sxs-lookup"><span data-stu-id="cac71-105">Local transactions always wrap one or more units of work on a single [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider session.</span></span>  
  
 <span data-ttu-id="cac71-106">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]При использовании режима автоматической фиксации поставщика OLE DB собственного клиента по умолчанию одна единица работы рассматривается как область локальной транзакции.</span><span class="sxs-lookup"><span data-stu-id="cac71-106">Using the default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider autocommit mode, a single unit of work is treated as the scope of a local transaction.</span></span> <span data-ttu-id="cac71-107">В локальной транзакции участвует только одна единица работы.</span><span class="sxs-lookup"><span data-stu-id="cac71-107">Only one unit participates in the local transaction.</span></span> <span data-ttu-id="cac71-108">При создании сеанса [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента начинает транзакцию для сеанса.</span><span class="sxs-lookup"><span data-stu-id="cac71-108">When a session is created, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider begins a transaction for the session.</span></span> <span data-ttu-id="cac71-109">При успешном завершении единицы работы выполненная работа фиксируется.</span><span class="sxs-lookup"><span data-stu-id="cac71-109">Upon successful completion of a work unit, the work is committed.</span></span> <span data-ttu-id="cac71-110">При сбое выполняется откат всей начатой работы; потребителю сообщается об ошибке.</span><span class="sxs-lookup"><span data-stu-id="cac71-110">On failure, any work begun is rolled back and the error is reported to the consumer.</span></span> <span data-ttu-id="cac71-111">В любом случае [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента начинает новую локальную транзакцию для сеанса, чтобы вся работа выполнялась в рамках транзакции.</span><span class="sxs-lookup"><span data-stu-id="cac71-111">In either case, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider begins a new local transaction for the session so that all work is conducted within a transaction.</span></span>  
  
 <span data-ttu-id="cac71-112">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Потребитель поставщика OLE DB собственного клиента может направить более точный контроль над областью локальной транзакции с помощью интерфейса **ITransactionLocal** .</span><span class="sxs-lookup"><span data-stu-id="cac71-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer can direct more precise control over local transaction scope by using the **ITransactionLocal** interface.</span></span> <span data-ttu-id="cac71-113">Если сеанс потребителя инициирует транзакцию, все рабочие единицы сеанса между точкой начала транзакции и последующими неизбежными вызовами методов **Commit** или **Abort** рассматриваются как единая операция.</span><span class="sxs-lookup"><span data-stu-id="cac71-113">When a consumer session initiates a transaction, all session work units between the transaction start point and the eventual **Commit** or **Abort** method calls are treated as an atomic unit.</span></span> <span data-ttu-id="cac71-114">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента неявным образом начинает транзакцию, когда она направляется потребителю.</span><span class="sxs-lookup"><span data-stu-id="cac71-114">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implicitly begins a transaction when directed to do so by the consumer.</span></span> <span data-ttu-id="cac71-115">Если потребитель не запрашивает хранения, сеанс восстанавливает режим родительской транзакции. Как правило, это режим автозавершения.</span><span class="sxs-lookup"><span data-stu-id="cac71-115">If the consumer does not request retention, the session reverts to parent transaction-level behavior, most commonly autocommit mode.</span></span>  
  
 <span data-ttu-id="cac71-116">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента поддерживает параметры **ITransactionLocal:: StartTransaction** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="cac71-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **ITransactionLocal::StartTransaction** parameters as follows.</span></span>  
  
|<span data-ttu-id="cac71-117">Параметр</span><span class="sxs-lookup"><span data-stu-id="cac71-117">Parameter</span></span>|<span data-ttu-id="cac71-118">Описание</span><span class="sxs-lookup"><span data-stu-id="cac71-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cac71-119">*isoLevel*[in]</span><span class="sxs-lookup"><span data-stu-id="cac71-119">*isoLevel*[in]</span></span>|<span data-ttu-id="cac71-120">Уровень изоляции, который должен использоваться с этой транзакцией.</span><span class="sxs-lookup"><span data-stu-id="cac71-120">The isolation level to be used with this transaction.</span></span> <span data-ttu-id="cac71-121">В локальных транзакциях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик собственного клиента OLE DB поддерживает следующие действия:</span><span class="sxs-lookup"><span data-stu-id="cac71-121">In local transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports the following:</span></span><br /><br /> <span data-ttu-id="cac71-122">— ISOLATIONLEVEL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="cac71-122">-   ISOLATIONLEVEL_UNSPECIFIED</span></span><br /><span data-ttu-id="cac71-123">— ISOLATIONLEVEL_CHAOS</span><span class="sxs-lookup"><span data-stu-id="cac71-123">-   ISOLATIONLEVEL_CHAOS</span></span><br /><span data-ttu-id="cac71-124">— ISOLATIONLEVEL_READUNCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="cac71-124">-   ISOLATIONLEVEL_READUNCOMMITTED</span></span><br /><span data-ttu-id="cac71-125">— ISOLATIONLEVEL_READCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="cac71-125">-   ISOLATIONLEVEL_READCOMMITTED</span></span><br /><span data-ttu-id="cac71-126">— ISOLATIONLEVEL_REPEATABLEREAD</span><span class="sxs-lookup"><span data-stu-id="cac71-126">-   ISOLATIONLEVEL_REPEATABLEREAD</span></span><br /><span data-ttu-id="cac71-127">— ISOLATIONLEVEL_CURSORSTABILITY</span><span class="sxs-lookup"><span data-stu-id="cac71-127">-   ISOLATIONLEVEL_CURSORSTABILITY</span></span><br /><span data-ttu-id="cac71-128">— ISOLATIONLEVEL_REPEATABLEREAD</span><span class="sxs-lookup"><span data-stu-id="cac71-128">-   ISOLATIONLEVEL_REPEATABLEREAD</span></span><br /><span data-ttu-id="cac71-129">— ISOLATIONLEVEL_SERIALIZABLE</span><span class="sxs-lookup"><span data-stu-id="cac71-129">-   ISOLATIONLEVEL_SERIALIZABLE</span></span><br /><span data-ttu-id="cac71-130">— ISOLATIONLEVEL_ISOLATED</span><span class="sxs-lookup"><span data-stu-id="cac71-130">-   ISOLATIONLEVEL_ISOLATED</span></span><br /><span data-ttu-id="cac71-131">-ISOLATIONLEVEL_SNAPSHOT **Примечание.** начиная с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] версии, ISOLATIONLEVEL_SNAPSHOT является допустимым для аргумента *isoLevel* , независимо от того, включено ли управление версиями для базы данных.</span><span class="sxs-lookup"><span data-stu-id="cac71-131">-   ISOLATIONLEVEL_SNAPSHOT **Note:**  Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], ISOLATIONLEVEL_SNAPSHOT is valid for the *isoLevel* argument whether or not versioning is enabled for the database.</span></span> <span data-ttu-id="cac71-132">Однако произойдет ошибка, если пользователь попытается выполнить инструкцию, когда управление версиями не включено, а база данных предназначена не только для чтения.</span><span class="sxs-lookup"><span data-stu-id="cac71-132">However, an error will occur if the user attempts to execute a statement and versioning is not enabled and/or the database is not read-only.</span></span> <span data-ttu-id="cac71-133">Кроме того, ошибка XACT_E_ISOLATIONLEVEL возникнет, если для *isoLevel* задано значение ISOLATIONLEVEL_SNAPSHOT при соединении с версией [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ранее [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cac71-133">In addition, the error XACT_E_ISOLATIONLEVEL will occur if ISOLATIONLEVEL_SNAPSHOT is specified as the *isoLevel* when connected to a version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>|  
|<span data-ttu-id="cac71-134">*isoFlags*[in]</span><span class="sxs-lookup"><span data-stu-id="cac71-134">*isoFlags*[in]</span></span>|<span data-ttu-id="cac71-135">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента возвращает ошибку для любого значения, отличного от нуля.</span><span class="sxs-lookup"><span data-stu-id="cac71-135">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns an error for any value other than zero.</span></span>|  
|<span data-ttu-id="cac71-136">*pOtherOptions*[in]</span><span class="sxs-lookup"><span data-stu-id="cac71-136">*pOtherOptions*[in]</span></span>|<span data-ttu-id="cac71-137">Если значение не равно NULL, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента запрашивает объект параметров из интерфейса.</span><span class="sxs-lookup"><span data-stu-id="cac71-137">If not NULL, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider requests the options object from the interface.</span></span> <span data-ttu-id="cac71-138">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента возвращает XACT_E_NOTIMEOUT, если элемент *ултимеаут* объекта параметров не равен нулю.</span><span class="sxs-lookup"><span data-stu-id="cac71-138">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTIMEOUT if the options object's *ulTimeout* member is not zero.</span></span> <span data-ttu-id="cac71-139">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента игнорирует значение элемента *сздескриптион* .</span><span class="sxs-lookup"><span data-stu-id="cac71-139">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider ignores the value of the *szDescription* member.</span></span>|  
|<span data-ttu-id="cac71-140">*pulTransactionLevel*[out]</span><span class="sxs-lookup"><span data-stu-id="cac71-140">*pulTransactionLevel*[out]</span></span>|<span data-ttu-id="cac71-141">Если значение не равно NULL, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента возвращает вложенный уровень транзакции.</span><span class="sxs-lookup"><span data-stu-id="cac71-141">If not NULL, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns the nested level of the transaction.</span></span>|  
  
 <span data-ttu-id="cac71-142">Для локальных транзакций [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента реализует параметры **ITransaction:: Abort** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="cac71-142">For local transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements **ITransaction::Abort** parameters as follows.</span></span>  
  
|<span data-ttu-id="cac71-143">Параметр</span><span class="sxs-lookup"><span data-stu-id="cac71-143">Parameter</span></span>|<span data-ttu-id="cac71-144">Описание</span><span class="sxs-lookup"><span data-stu-id="cac71-144">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cac71-145">*pboidReason*[in]</span><span class="sxs-lookup"><span data-stu-id="cac71-145">*pboidReason*[in]</span></span>|<span data-ttu-id="cac71-146">При установке не учитывается.</span><span class="sxs-lookup"><span data-stu-id="cac71-146">Ignored if set.</span></span> <span data-ttu-id="cac71-147">Может иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="cac71-147">Can safely be NULL.</span></span>|  
|<span data-ttu-id="cac71-148">*fRetaining*[in]</span><span class="sxs-lookup"><span data-stu-id="cac71-148">*fRetaining*[in]</span></span>|<span data-ttu-id="cac71-149">Если задано значение TRUE, то для сеанса неявным образом запускается новая транзакция.</span><span class="sxs-lookup"><span data-stu-id="cac71-149">When TRUE, a new transaction is implicitly begun for the session.</span></span> <span data-ttu-id="cac71-150">Эта транзакция должна быть зафиксирована или завершена объектом-получателем.</span><span class="sxs-lookup"><span data-stu-id="cac71-150">The transaction must be committed or terminated by the consumer.</span></span> <span data-ttu-id="cac71-151">Если значение равно "FALSE", [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента возвращается в режим автоматической фиксации для сеанса.</span><span class="sxs-lookup"><span data-stu-id="cac71-151">When FALSE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider reverts to autocommit mode for the session.</span></span>|  
|<span data-ttu-id="cac71-152">*fAsync*[in]</span><span class="sxs-lookup"><span data-stu-id="cac71-152">*fAsync*[in]</span></span>|<span data-ttu-id="cac71-153">Асинхронное прерывание не поддерживается [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщиком собственного клиента OLE DB.</span><span class="sxs-lookup"><span data-stu-id="cac71-153">Asynchronous abort is not supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="cac71-154">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента возвращает XACT_E_NOTSUPPORTED, если значение не равно false.</span><span class="sxs-lookup"><span data-stu-id="cac71-154">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTSUPPORTED if the value is not FALSE.</span></span>|  
  
 <span data-ttu-id="cac71-155">Для локальных транзакций [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик собственного клиента OLE DB реализует параметры **ITransaction:: Commit** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="cac71-155">For local transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements **ITransaction::Commit** parameters as follows.</span></span>  
  
|<span data-ttu-id="cac71-156">Параметр</span><span class="sxs-lookup"><span data-stu-id="cac71-156">Parameter</span></span>|<span data-ttu-id="cac71-157">Описание</span><span class="sxs-lookup"><span data-stu-id="cac71-157">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cac71-158">*fRetaining*[in]</span><span class="sxs-lookup"><span data-stu-id="cac71-158">*fRetaining*[in]</span></span>|<span data-ttu-id="cac71-159">Если задано значение TRUE, то для сеанса неявным образом запускается новая транзакция.</span><span class="sxs-lookup"><span data-stu-id="cac71-159">When TRUE, a new transaction is implicitly begun for the session.</span></span> <span data-ttu-id="cac71-160">Эта транзакция должна быть зафиксирована или завершена объектом-получателем.</span><span class="sxs-lookup"><span data-stu-id="cac71-160">The transaction must be committed or terminated by the consumer.</span></span> <span data-ttu-id="cac71-161">Если значение равно "FALSE", [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента возвращается в режим автоматической фиксации для сеанса.</span><span class="sxs-lookup"><span data-stu-id="cac71-161">When FALSE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider reverts to autocommit mode for the session.</span></span>|  
|<span data-ttu-id="cac71-162">*grfTC*[in]</span><span class="sxs-lookup"><span data-stu-id="cac71-162">*grfTC*[in]</span></span>|<span data-ttu-id="cac71-163">Асинхронные и одноэтапные возвраты не поддерживаются [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщиком собственного клиента OLE DB.</span><span class="sxs-lookup"><span data-stu-id="cac71-163">Asynchronous and phase one returns are not supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="cac71-164">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента возвращает XACT_E_NOTSUPPORTED для любого значения, кроме XACTTC_SYNC.</span><span class="sxs-lookup"><span data-stu-id="cac71-164">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTSUPPORTED for any value other than XACTTC_SYNC.</span></span>|  
|<span data-ttu-id="cac71-165">*grfRM*[in]</span><span class="sxs-lookup"><span data-stu-id="cac71-165">*grfRM*[in]</span></span>|<span data-ttu-id="cac71-166">Должно быть равно 0.</span><span class="sxs-lookup"><span data-stu-id="cac71-166">Must be 0.</span></span>|  
  
 <span data-ttu-id="cac71-167">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Наборы строк поставщика собственного клиента OLE DB в сеансе сохраняются в локальной операции фиксации или прерывания на основе значений свойств набора строк DBPROP_ABORTPRESERVE и DBPROP_COMMITPRESERVE.</span><span class="sxs-lookup"><span data-stu-id="cac71-167">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets on the session are preserved on a local commit or abort operation based on the values of the rowset properties DBPROP_ABORTPRESERVE and DBPROP_COMMITPRESERVE.</span></span> <span data-ttu-id="cac71-168">По умолчанию эти свойства VARIANT_FALSE и все [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] наборы строк поставщика собственного клиента OLE DB в сеансе теряются после операции прерывания или фиксации.</span><span class="sxs-lookup"><span data-stu-id="cac71-168">By default, these properties are both VARIANT_FALSE and all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets on the session are lost following an abort or commit operation.</span></span>  
  
 <span data-ttu-id="cac71-169">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента не реализует интерфейс **итрансактионобжект** .</span><span class="sxs-lookup"><span data-stu-id="cac71-169">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not implement the **ITransactionObject** interface.</span></span> <span data-ttu-id="cac71-170">При попытке потребителя получить ссылку на интерфейс возвращается E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="cac71-170">A consumer attempt to retrieve a reference on the interface returns E_NOINTERFACE.</span></span>  
  
 <span data-ttu-id="cac71-171">В этом примере используется интерфейс **ITransactionLocal**.</span><span class="sxs-lookup"><span data-stu-id="cac71-171">This example uses **ITransactionLocal**.</span></span>  
  
```  
// Interfaces used in the example.  
IDBCreateSession*   pIDBCreateSession   = NULL;  
ITransaction*       pITransaction       = NULL;  
IDBCreateCommand*   pIDBCreateCommand   = NULL;  
IRowset*            pIRowset            = NULL;  
  
HRESULT             hr;  
  
// Get the command creation and local transaction interfaces for the  
// session.  
if (FAILED(hr = pIDBCreateSession->CreateSession(NULL,  
     IID_IDBCreateCommand, (IUnknown**) &pIDBCreateCommand)))  
    {  
    // Process error from session creation. Release any references and  
    // return.  
    }  
  
if (FAILED(hr = pIDBCreateCommand->QueryInterface(IID_ITransactionLocal,  
    (void**) &pITransaction)))  
    {  
    // Process error. Release any references and return.  
    }  
  
// Start the local transaction.  
if (FAILED(hr = ((ITransactionLocal*) pITransaction)->StartTransaction(  
    ISOLATIONLEVEL_REPEATABLEREAD, 0, NULL, NULL)))  
    {  
    // Process error from StartTransaction. Release any references and  
    // return.  
    }  
  
// Get data into a rowset, then update the data. Functions are not  
// illustrated in this example.  
if (FAILED(hr = ExecuteCommand(pIDBCreateCommand, &pIRowset)))  
    {  
    // Release any references and return.  
    }  
  
// If rowset data update fails, then terminate the transaction, else  
// commit. The example doesn't retain the rowset.  
if (FAILED(hr = UpdateDataInRowset(pIRowset, bDelayedUpdate)))  
    {  
    // Get error from update, then terminate.  
    pITransaction->Abort(NULL, FALSE, FALSE);  
    }  
else  
    {  
    if (FAILED(hr = pITransaction->Commit(FALSE, XACTTC_SYNC, 0)))  
        {  
        // Get error from failed commit.  
        }  
    }  
  
if (FAILED(hr))  
    {  
    // Update of data or commit failed. Release any references and  
    // return.  
    }  
  
// Release any references and continue.  
```  
  
## <a name="see-also"></a><span data-ttu-id="cac71-172">См. также:</span><span class="sxs-lookup"><span data-stu-id="cac71-172">See Also</span></span>  
 <span data-ttu-id="cac71-173">[Транзакции](transactions.md) </span><span class="sxs-lookup"><span data-stu-id="cac71-173">[Transactions](transactions.md) </span></span>  
 [<span data-ttu-id="cac71-174">Работа с изоляцией моментального снимка</span><span class="sxs-lookup"><span data-stu-id="cac71-174">Working with Snapshot Isolation</span></span>](../native-client/features/working-with-snapshot-isolation.md)  
  
  
