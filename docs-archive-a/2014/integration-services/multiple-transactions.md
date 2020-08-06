---
title: Несколько транзакций | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Integration Services], multiple
- multiple transactions
ms.assetid: c3664a94-be89-40c0-a3a0-84b74a7fedbe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5ff909c92a23c965047edc0fcf278e17e4c76d94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664316"
---
# <a name="multiple-transactions"></a><span data-ttu-id="3f74a-102">Множественные транзакции</span><span class="sxs-lookup"><span data-stu-id="3f74a-102">Multiple Transactions</span></span>
  <span data-ttu-id="3f74a-103">В одном пакете служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] может содержаться несколько самостоятельных транзакций.</span><span class="sxs-lookup"><span data-stu-id="3f74a-103">It is possible for a package to include unrelated transactions in an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="3f74a-104">Каждый раз, когда контейнер в середине иерархии вложенных контейнеров не поддерживает транзакции, контейнеры выше и ниже по иерархии начинают отдельные транзакции, если настроены для поддержки транзакций.</span><span class="sxs-lookup"><span data-stu-id="3f74a-104">Any time a container in the middle of a nested container hierarchy does not support transactions, the containers above or below it in the hierarchy start separate transactions if they are configured to support transactions.</span></span> <span data-ttu-id="3f74a-105">Транзакции фиксируются или откатываются, начиная с самой глубокой задачи в иерархии вложенных контейнеров пакета.</span><span class="sxs-lookup"><span data-stu-id="3f74a-105">The transactions commit or roll back in order from the innermost task in the nested container hierarchy to the package.</span></span> <span data-ttu-id="3f74a-106">Однако после фиксации вложенной транзакции она не откатывается, если внешняя транзакция прервана.</span><span class="sxs-lookup"><span data-stu-id="3f74a-106">However, after the inner transaction commits, it does not roll back if an outer transaction is aborted.</span></span>

## <a name="illustration-of-multiple-transactions"></a><span data-ttu-id="3f74a-107">Иллюстрация множественных транзакций</span><span class="sxs-lookup"><span data-stu-id="3f74a-107">Illustration of Multiple Transactions</span></span>
 <span data-ttu-id="3f74a-108">Например, пакет включает контейнер последовательности, содержащий два контейнера «цикл по каждому элементу», и каждый контейнер включает две задачи «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="3f74a-108">For example, a package has a Sequence container that holds two Foreach Loop containers, and each container include two Execute SQL tasks.</span></span> <span data-ttu-id="3f74a-109">Контейнеры «цикл по каждому элементу» не поддерживают транзакции, а контейнер последовательности и задача «Выполнение SQL» поддерживают.</span><span class="sxs-lookup"><span data-stu-id="3f74a-109">The Sequence container supports transactions, the Foreach Loop containers do not, and the Execute SQL tasks do.</span></span> <span data-ttu-id="3f74a-110">В данном примере каждая задача «Выполнение SQL» будет выполнять свою собственную транзакцию и не будет подвергаться откату в случае, если транзакция в задаче последовательности окажется прерванной.</span><span class="sxs-lookup"><span data-stu-id="3f74a-110">In this example, each Execute SQL task would start its own transaction and would not roll back if the transaction on the Sequence task was aborted.</span></span>

 <span data-ttu-id="3f74a-111">Свойства TransactionOption контейнера последовательности, контейнера "цикл по каждому элементу" и задач "Выполнение SQL" установлены следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3f74a-111">The TransactionOption properties of the Sequence container, Foreach Loop container and the Execute SQL tasks are set as follows:</span></span>

-   <span data-ttu-id="3f74a-112">Свойство TransactionOption контейнера последовательности установлено в значение **Required**.</span><span class="sxs-lookup"><span data-stu-id="3f74a-112">The TransactionOption property of the Sequence container is set to **Required**.</span></span>

-   <span data-ttu-id="3f74a-113">Свойства TransactionOption контейнеров "цикл по каждому элементу" установлены в значения **NotSupported**.</span><span class="sxs-lookup"><span data-stu-id="3f74a-113">The TransactionOption properties of the Foreach Loop containers are set to **NotSupported**.</span></span>

-   <span data-ttu-id="3f74a-114">Свойство TransactionOption задач Execute SQL установлено в значение **Required**.</span><span class="sxs-lookup"><span data-stu-id="3f74a-114">The TransactionOption properties of the Execute SQL tasks are set to **Required**.</span></span>

 <span data-ttu-id="3f74a-115">На следующей диаграмме показаны пять несвязанных транзакций в пакете.</span><span class="sxs-lookup"><span data-stu-id="3f74a-115">The following diagram shows the five unrelated transactions in the package.</span></span> <span data-ttu-id="3f74a-116">Одна транзакция была начата контейнером последовательности, а четыре других — задачами «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="3f74a-116">One transaction is started by the Sequence container and four transactions are started by the Execute SQL tasks.</span></span>

 <span data-ttu-id="3f74a-117">![Реализация множественных транзакций](media/mw-dts-trans2.gif "Реализация множественных транзакций")</span><span class="sxs-lookup"><span data-stu-id="3f74a-117">![Implementation of multiple transactions](media/mw-dts-trans2.gif "Implementation of multiple transactions")</span></span>

## <a name="related-tasks"></a><span data-ttu-id="3f74a-118">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="3f74a-118">Related Tasks</span></span>
 [<span data-ttu-id="3f74a-119">Настройка пакета для использования транзакций</span><span class="sxs-lookup"><span data-stu-id="3f74a-119">Configure a Package to Use Transactions</span></span>](../relational-databases/native-client-ole-db-transactions/transactions.md)


