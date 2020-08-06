---
title: Настройка пакета для использования транзакций | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Integration Services], configuring packages to use
ms.assetid: 8bf14957-27b4-456b-81d9-e1a0e0ca94b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f469c2439deb2d16ac9046a1628e82c34e39b31d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729721"
---
# <a name="configure-a-package-to-use-transactions"></a><span data-ttu-id="eafe6-102">Настройка пакета для использования транзакций</span><span class="sxs-lookup"><span data-stu-id="eafe6-102">Configure a Package to Use Transactions</span></span>
  <span data-ttu-id="eafe6-103">Существуют два режима настройки пакета для использования транзакций.</span><span class="sxs-lookup"><span data-stu-id="eafe6-103">When you configure a package to use transactions, you have two options:</span></span>  
  
-   <span data-ttu-id="eafe6-104">Одна транзакция на пакет.</span><span class="sxs-lookup"><span data-stu-id="eafe6-104">Have a single transaction for the package.</span></span> <span data-ttu-id="eafe6-105">В этом случае *инициирует* транзакцию сам пакет, а индивидуальные задачи и контейнеры пакета участвуют в этой одиночной транзакции.</span><span class="sxs-lookup"><span data-stu-id="eafe6-105">In this case, it is the package itself that *initiates* this transaction, whereas individual tasks and containers in the package participate in this single transaction.</span></span>  
  
-   <span data-ttu-id="eafe6-106">Несколько транзакций на пакет.</span><span class="sxs-lookup"><span data-stu-id="eafe6-106">Have multiple transactions in the package.</span></span> <span data-ttu-id="eafe6-107">В этом случае пакет поддерживает транзакции, но в действительности инициируют эти транзакции индивидуальные задачи и контейнеры пакета.</span><span class="sxs-lookup"><span data-stu-id="eafe6-107">In this case, the package supports transactions, but individual tasks and containers in the package actually initiate the transactions.</span></span>  
  
 <span data-ttu-id="eafe6-108">В следующих двух процедурах описывается настройка в каждом из режимов.</span><span class="sxs-lookup"><span data-stu-id="eafe6-108">The following procedures describe how to configure both options.</span></span>  
  
## <a name="configuring-a-single-transaction"></a><span data-ttu-id="eafe6-109">Настройка варианта с одиночной транзакцией</span><span class="sxs-lookup"><span data-stu-id="eafe6-109">Configuring a Single Transaction</span></span>  
 <span data-ttu-id="eafe6-110">В этом режиме инициирует одиночную транзакцию сам пакет.</span><span class="sxs-lookup"><span data-stu-id="eafe6-110">In this option, the package itself initiates a single transaction.</span></span> <span data-ttu-id="eafe6-111">Настройте пакет для инициации этой транзакции, задав для свойства TransactionOption пакета значение `Required` .</span><span class="sxs-lookup"><span data-stu-id="eafe6-111">You configure the package to initiate this transaction by setting the TransactionOption property of the package to `Required`.</span></span>  
  
 <span data-ttu-id="eafe6-112">Далее, прикрепите к этой одиночной транзакции конкретные задачи и контейнеры.</span><span class="sxs-lookup"><span data-stu-id="eafe6-112">Next, you enlist specific tasks and containers in this single transaction.</span></span> <span data-ttu-id="eafe6-113">Чтобы прикрепить задачу или контейнер в транзакции, задайте для свойства TransactionOption этой задачи или контейнера значение `Supported` .</span><span class="sxs-lookup"><span data-stu-id="eafe6-113">To enlist a task or container in a transaction, you set the TransactionOption property of that task or container to `Supported`.</span></span>  
  
#### <a name="to-configure-a-package-to-use-a-single-transaction"></a><span data-ttu-id="eafe6-114">Настройка пакета для использования одиночной транзакции</span><span class="sxs-lookup"><span data-stu-id="eafe6-114">To configure a package to use a single transaction</span></span>  
  
1.  <span data-ttu-id="eafe6-115">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] с пакетом, который необходимо настроить на использование транзакции.</span><span class="sxs-lookup"><span data-stu-id="eafe6-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to configure to use a transaction.</span></span>  
  
2.  <span data-ttu-id="eafe6-116">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="eafe6-116">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="eafe6-117">Перейдите на вкладку **Поток управления** .</span><span class="sxs-lookup"><span data-stu-id="eafe6-117">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="eafe6-118">Щелкните правой кнопкой мыши в области конструктора потока управления и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="eafe6-118">Right-click anywhere in the background of the control flow design surface, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="eafe6-119">В окне **Свойства** задайте для свойства TransactionOption значение `Required` .</span><span class="sxs-lookup"><span data-stu-id="eafe6-119">In the **Properties** window, set the TransactionOption property to `Required`.</span></span>  
  
6.  <span data-ttu-id="eafe6-120">Чтобы зарегистрировать задачу или контейнер в транзакции, щелкните их правой кнопкой мыши в рабочей области конструирования на вкладке **Поток управления** , а затем выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="eafe6-120">On the design surface of the **ControlFlow** tab, right-click the task or the container that you want to enroll in the transaction, and then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="eafe6-121">В окне **Свойства** задайте для свойства TransactionOption значение `Supported` .</span><span class="sxs-lookup"><span data-stu-id="eafe6-121">In the **Properties** window, set the TransactionOption property to `Supported`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eafe6-122">Чтобы прикрепить соединение к транзакции, зарегистрируйте в транзакции задачи, использующие это соединение.</span><span class="sxs-lookup"><span data-stu-id="eafe6-122">To enlist a connection in a transaction, enroll the tasks that use the connection in the transaction.</span></span> <span data-ttu-id="eafe6-123">Дополнительные сведения см. в разделе [Соединения в службах Integration Services (SSIS)](connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="eafe6-123">For more information, see [Integration Services &#40;SSIS&#41; Connections](connection-manager/integration-services-ssis-connections.md).</span></span>  
  
8.  <span data-ttu-id="eafe6-124">Повторите шаги 6 и 7 для каждой задачи и контейнера, которые должны быть зарегистрированы в транзакции.</span><span class="sxs-lookup"><span data-stu-id="eafe6-124">Repeat steps 6 and 7 for each task and container that you want to enroll in the transaction.</span></span>  
  
## <a name="configuring-multiple-transactions"></a><span data-ttu-id="eafe6-125">Настройка варианта с множественными транзакциями</span><span class="sxs-lookup"><span data-stu-id="eafe6-125">Configuring Multiple Transactions</span></span>  
 <span data-ttu-id="eafe6-126">В этом режиме пакет сам по себе поддерживает транзакции, но не запускает их.</span><span class="sxs-lookup"><span data-stu-id="eafe6-126">In this option, the package itself supports transactions but does not start a transaction.</span></span> <span data-ttu-id="eafe6-127">Настройте пакет для поддержки транзакций, задав для свойства TransactionOption пакета значение `Supported` .</span><span class="sxs-lookup"><span data-stu-id="eafe6-127">You configure the package to support transactions by setting the TransactionOption property of the package to `Supported`.</span></span>  
  
 <span data-ttu-id="eafe6-128">Далее настройте задачи и контейнеры пакета, которые должны инициировать транзакции или участвовать в них.</span><span class="sxs-lookup"><span data-stu-id="eafe6-128">Next, you configure the desired tasks and containers inside the package to initiate or participate in transactions.</span></span> <span data-ttu-id="eafe6-129">Чтобы настроить задачу или контейнер для инициации транзакции, задайте для свойства TransactionOption этой задачи или контейнера значение `Required` .</span><span class="sxs-lookup"><span data-stu-id="eafe6-129">To configure a task or container to initiate a transaction, you set the TransactionOption property of that task or container to `Required`.</span></span>  
  
#### <a name="to-configure-a-package-to-use-multiple-transactions"></a><span data-ttu-id="eafe6-130">Настройка пакета для использования множественных транзакций</span><span class="sxs-lookup"><span data-stu-id="eafe6-130">To configure a package to use multiple transactions</span></span>  
  
1.  <span data-ttu-id="eafe6-131">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий пакет, который нужно настроить для использования транзакций.</span><span class="sxs-lookup"><span data-stu-id="eafe6-131">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to configure to use transaction.s</span></span>  
  
2.  <span data-ttu-id="eafe6-132">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="eafe6-132">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="eafe6-133">Перейдите на вкладку **Поток управления** .</span><span class="sxs-lookup"><span data-stu-id="eafe6-133">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="eafe6-134">Щелкните правой кнопкой мыши в области конструктора потока управления и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="eafe6-134">Right-click anywhere in the background of the control flow design surface, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="eafe6-135">В окне **Свойства** задайте для свойства TransactionOption значение `Supported` .</span><span class="sxs-lookup"><span data-stu-id="eafe6-135">In the **Properties** window, set the TransactionOption property to `Supported`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eafe6-136">Пакет поддерживает транзакции, но транзакции запускаются задачами или контейнерами в пакете.</span><span class="sxs-lookup"><span data-stu-id="eafe6-136">The package supports transactions, but the transactions are started by task or containers in the package.</span></span>  
  
6.  <span data-ttu-id="eafe6-137">В рабочей области конструирования на вкладке **Поток управления** щелкните правой кнопкой мыши задачу или контейнер в пакете, для которого необходимо начать транзакцию, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="eafe6-137">On the design surface of the **ControlFlow** tab, right-click the task or the container in the package for which you want to start a transaction, and then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="eafe6-138">В окне **Свойства** задайте для свойства TransactionOption значение `Required` .</span><span class="sxs-lookup"><span data-stu-id="eafe6-138">In the **Properties** window, set the TransactionOption property to `Required`.</span></span>  
  
8.  <span data-ttu-id="eafe6-139">Если транзакция начата контейнером, щелкните правой кнопкой мыши задачу или контейнер, которые необходимо зарегистрировать в транзакции, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="eafe6-139">If a transaction is started by a container, right-click the task or the container that you want to enroll in the transaction, and then click **Properties**.</span></span>  
  
9. <span data-ttu-id="eafe6-140">В окне **Свойства** задайте для свойства TransactionOption значение `Supported` .</span><span class="sxs-lookup"><span data-stu-id="eafe6-140">In the **Properties** window, set the TransactionOption property to `Supported`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eafe6-141">Чтобы прикрепить соединение к транзакции, зарегистрируйте в транзакции задачи, использующие это соединение.</span><span class="sxs-lookup"><span data-stu-id="eafe6-141">To enlist a connection in a transaction, enroll the tasks that use the connection in the transaction.</span></span> <span data-ttu-id="eafe6-142">Дополнительные сведения см. в разделе [Соединения в службах Integration Services (SSIS)](connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="eafe6-142">For more information, see [Integration Services &#40;SSIS&#41; Connections](connection-manager/integration-services-ssis-connections.md).</span></span>  
  
10. <span data-ttu-id="eafe6-143">Повторите шаги с 6 по 9 для каждой задачи и контейнера, которые запускают транзакцию.</span><span class="sxs-lookup"><span data-stu-id="eafe6-143">Repeat steps 6 through 9 for each task and container that starts a transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eafe6-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="eafe6-144">See Also</span></span>  
 [<span data-ttu-id="eafe6-145">Транзакции служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="eafe6-145">Integration Services Transactions</span></span>](integration-services-transactions.md)  
  
  
