---
title: Транзакции служб Integration Services | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], transactions
- transactions [Integration Services], about transactions in packages
- tasks [Integration Services], transactions
- transactions [Integration Services]
ms.assetid: 3c78bb26-ddce-4831-a5f8-09d4f4fd53cc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5c0ee195bbcb7b9779111add4c1f2349816d5441
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664372"
---
# <a name="integration-services-transactions"></a><span data-ttu-id="93c69-102">Транзакции служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="93c69-102">Integration Services Transactions</span></span>
  <span data-ttu-id="93c69-103">Пакеты используют транзакции для связывания выполняемых в базе данных задачами операций в атомарные объекты, и, таким образом, сохраняют целостность данных.</span><span class="sxs-lookup"><span data-stu-id="93c69-103">Packages use transactions to bind the database actions that tasks perform into atomic units, and by doing this maintain data integrity.</span></span> <span data-ttu-id="93c69-104">Все типы контейнеров служб [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] (пакеты, контейнеры циклов по элементам и по каждому элементу, контейнеры последовательности, а также серверы задач, которые содержат каждую задачу) могут быть настроены для использования транзакций.</span><span class="sxs-lookup"><span data-stu-id="93c69-104">All [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] container types-packages, the For Loop, Foreach Loop, and Sequence containers, and the task hosts that encapsulate each task-can be configured to use transactions.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="93c69-105">предоставляют три параметра для настройки транзакций: **NotSupported**, **Supported**и **Required**.</span><span class="sxs-lookup"><span data-stu-id="93c69-105">provides three options for configuring transactions: **NotSupported**, **Supported**, and **Required**.</span></span>  
  
-   <span data-ttu-id="93c69-106">**Required** указывает, что контейнер запускает транзакцию, если она еще не запущена родительским контейнером.</span><span class="sxs-lookup"><span data-stu-id="93c69-106">**Required** indicates that the container starts a transaction, unless one is already started by its parent container.</span></span> <span data-ttu-id="93c69-107">Если транзакция уже существует, контейнер с ней соединяется.</span><span class="sxs-lookup"><span data-stu-id="93c69-107">If a transaction already exists, the container joins the transaction.</span></span> <span data-ttu-id="93c69-108">Например, если пакет, не настроенный для поддержки транзакций, содержит контейнер последовательности, использующий параметр **Required** , то контейнер последовательности начнет свою собственную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="93c69-108">For example, if a package that is not configured to support transactions includes a Sequence container that uses the **Required** option, the Sequence container would start its own transaction.</span></span> <span data-ttu-id="93c69-109">Если бы пакет был настроен для использования параметра **Required** , контейнер последовательности соединился бы с транзакцией пакета.</span><span class="sxs-lookup"><span data-stu-id="93c69-109">If the package were configured to use the **Required** option, the Sequence container would join the package transaction.</span></span>  
  
-   <span data-ttu-id="93c69-110">**Supported** указывает, что контейнер не запускает транзакцию, но соединяется с любой транзакцией, запущенной родительским контейнером.</span><span class="sxs-lookup"><span data-stu-id="93c69-110">**Supported** indicates that the container does not start a transaction, but joins any transaction started by its parent container.</span></span> <span data-ttu-id="93c69-111">Например, если пакет с четырьмя задачами «Выполнение SQL» запускает транзакцию и все четыре задачи используют параметр **Supported** , то обновления базы данных, выполненные задачами «Выполнение SQL», откатываются при ошибке обновления любой из этих задач.</span><span class="sxs-lookup"><span data-stu-id="93c69-111">For example, if a package with four Execute SQL tasks starts a transaction and all four tasks use the **Supported** option, the database updates performed by the Execute SQL tasks are rolled back if any task fails.</span></span> <span data-ttu-id="93c69-112">Если пакет не начинает транзакцию, четыре задачи «Выполнение SQL» не связаны транзакцией и в случае ошибки обновления базы данных одной из задач отменяются только обновления этой задачи.</span><span class="sxs-lookup"><span data-stu-id="93c69-112">If the package does not start a transaction, the four Execute SQL tasks are not bound by a transaction, and no database updates except the ones performed by the failed task are rolled back.</span></span>  
  
-   <span data-ttu-id="93c69-113">**NotSupported** указывает, что контейнер не начинает транзакцию и не соединяется с существующей транзакцией.</span><span class="sxs-lookup"><span data-stu-id="93c69-113">**NotSupported** indicates that the container does not start a transaction or join an existing transaction.</span></span> <span data-ttu-id="93c69-114">Транзакция, запущенная родительским контейнером, не влияет на дочерние контейнеры, которые не были настроены на поддержку транзакций.</span><span class="sxs-lookup"><span data-stu-id="93c69-114">A transaction started by a parent container does not affect child containers that have been configured to not support transactions.</span></span> <span data-ttu-id="93c69-115">Например, если пакет был настроен на запуск транзакции, а контейнер «цикл по элементам» в пакете использует параметр **NotSupported** , то в случае неудачи откат каких-либо задач в контейнере «цикл по элементам» невозможен.</span><span class="sxs-lookup"><span data-stu-id="93c69-115">For example, if a package is configured to start a transaction and a For Loop container in the package uses the **NotSupported** option, none of the tasks in the For Loop can roll back if they fail.</span></span>  
  
 <span data-ttu-id="93c69-116">Настройка транзакций происходит с помощью свойства контейнера TransactionOption.</span><span class="sxs-lookup"><span data-stu-id="93c69-116">You configure transactions by setting the TransactionOption property on the container.</span></span> <span data-ttu-id="93c69-117">Установить это свойство можно в окне **Свойства** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]или программным путем.</span><span class="sxs-lookup"><span data-stu-id="93c69-117">You can set this property by using the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], or you can set the property programmatically.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93c69-118">Cвойствo `TransactionOption` влияет на то, применяется ли значение свойства `IsolationLevel`, запрашиваемого контейнером.</span><span class="sxs-lookup"><span data-stu-id="93c69-118">The `TransactionOption` property influences whether or not the value of the `IsolationLevel` property requested by a container is applied.</span></span> <span data-ttu-id="93c69-119">Дополнительные сведения см. в описании `IsolationLevel` свойства в разделе [Установка свойств пакета](set-package-properties.md).</span><span class="sxs-lookup"><span data-stu-id="93c69-119">For more information, see the description of the `IsolationLevel` property in the topic, [Setting Package Properties](set-package-properties.md).</span></span>  
  
### <a name="to-configure-a-package-to-use-transactions"></a><span data-ttu-id="93c69-120">Настройка пакета на использование транзакций</span><span class="sxs-lookup"><span data-stu-id="93c69-120">To configure a package to use transactions</span></span>  
  
-   [<span data-ttu-id="93c69-121">Настройка пакета для использования транзакций</span><span class="sxs-lookup"><span data-stu-id="93c69-121">Configure a Package to Use Transactions</span></span>](../relational-databases/native-client-ole-db-transactions/transactions.md)  
  
## <a name="external-resources"></a><span data-ttu-id="93c69-122">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="93c69-122">External Resources</span></span>  
  
-   <span data-ttu-id="93c69-123">Запись в блоге, [Как использовать транзакции в службах SQL Server Integration Services SSIS](https://go.microsoft.com/fwlink/?LinkId=157783), на сайте www.mssqltips.com</span><span class="sxs-lookup"><span data-stu-id="93c69-123">Blog entry, [How to Use Transactions in SQL Server Integration Services SSIS](https://go.microsoft.com/fwlink/?LinkId=157783), on www.mssqltips.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93c69-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="93c69-124">See Also</span></span>  
 <span data-ttu-id="93c69-125">[Унаследованные транзакции](../../2014/integration-services/inherited-transactions.md) </span><span class="sxs-lookup"><span data-stu-id="93c69-125">[Inherited Transactions](../../2014/integration-services/inherited-transactions.md) </span></span>  
 [<span data-ttu-id="93c69-126">Множественные транзакции</span><span class="sxs-lookup"><span data-stu-id="93c69-126">Multiple Transactions</span></span>](../../2014/integration-services/multiple-transactions.md)  
  
  
