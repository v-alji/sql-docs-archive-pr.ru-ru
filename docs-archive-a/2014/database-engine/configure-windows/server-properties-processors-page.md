---
title: Свойства сервера (страница "Процессоры") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.processor.f1
ms.assetid: cc1581a2-492b-41f0-bda5-17909b65c4f7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c4d241f01de7ac961832e77bb09483cff275deb6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665105"
---
# <a name="server-properties-processors-page"></a><span data-ttu-id="b6418-102">Свойства сервера (страница «Процессоры»)</span><span class="sxs-lookup"><span data-stu-id="b6418-102">Server Properties (Processors Page)</span></span>
  <span data-ttu-id="b6418-103">Используйте эту страницу, чтобы просмотреть или изменить параметры процессоров.</span><span class="sxs-lookup"><span data-stu-id="b6418-103">Use this page to view or modify your processor options.</span></span> <span data-ttu-id="b6418-104">Настройки соответствия процессоров доступны только в случае, если в системе установлено более одного процессора.</span><span class="sxs-lookup"><span data-stu-id="b6418-104">Processor affinity settings are only enabled when more than one processor is installed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b6418-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b6418-105">Options</span></span>  
 <span data-ttu-id="b6418-106">**Соответствие процессоров**</span><span class="sxs-lookup"><span data-stu-id="b6418-106">**Processor Affinity**</span></span>  
 <span data-ttu-id="b6418-107">Связывает процессоры с определенными потоками, чтобы устранить чрезмерную нагрузку на процессоры и уменьшить количество переходов потоков между процессорами.</span><span class="sxs-lookup"><span data-stu-id="b6418-107">Assigns processors to specific threads to eliminating processor reloads and reduce thread migration across processors.</span></span> <span data-ttu-id="b6418-108">Дополнительные сведения см. в разделе [Параметр конфигурации сервера "affinity mask"](affinity-mask-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="b6418-108">For more information, see [affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="b6418-109">**Привязка ввода-вывода**</span><span class="sxs-lookup"><span data-stu-id="b6418-109">**I/O Affinity**</span></span>  
 <span data-ttu-id="b6418-110">Связывает операции дискового ввода-вывода [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с определенным подмножеством ЦП.</span><span class="sxs-lookup"><span data-stu-id="b6418-110">Binds [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disk I/Os to a specified subset of CPUs.</span></span> <span data-ttu-id="b6418-111">Дополнительные сведения см. в разделе [Параметр конфигурации сервера "affinity Input-Output mask"](affinity-input-output-mask-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="b6418-111">For more information, see [affinity Input-Output mask Server Configuration Option](affinity-input-output-mask-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="b6418-112">**Автоматически устанавливать маску соответствия для всех процессоров**</span><span class="sxs-lookup"><span data-stu-id="b6418-112">**Automatically set processor affinity mask for all processors**</span></span>  
 <span data-ttu-id="b6418-113">Позволяет [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] устанавливать соответствие процессоров.</span><span class="sxs-lookup"><span data-stu-id="b6418-113">Allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to set the processor affinity.</span></span>  
  
 <span data-ttu-id="b6418-114">**Автоматически устанавливать маску схожести ввода-вывода для всех процессоров**</span><span class="sxs-lookup"><span data-stu-id="b6418-114">**Automatically set I/O affinity mask for all processors**</span></span>  
 <span data-ttu-id="b6418-115">Позволяет [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] устанавливать привязку ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="b6418-115">Allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to set the I/O affinity.</span></span>  
  
 <span data-ttu-id="b6418-116">**Максимальное число потоков исполнителя.**</span><span class="sxs-lookup"><span data-stu-id="b6418-116">**Maximum worker threads**</span></span>  
 <span data-ttu-id="b6418-117">Значение 0 позволяет [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] устанавливать количество потоков исполнителя динамически.</span><span class="sxs-lookup"><span data-stu-id="b6418-117">0 allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to dynamically set the number of worker threads.</span></span> <span data-ttu-id="b6418-118">Эта настройка является наиболее подходящей для большинства систем.</span><span class="sxs-lookup"><span data-stu-id="b6418-118">This setting is best for most systems.</span></span> <span data-ttu-id="b6418-119">Однако в зависимости от конфигурации системы, присвоение этому параметру определенного значения иногда улучшает производительность.</span><span class="sxs-lookup"><span data-stu-id="b6418-119">However, depending on your system configuration, setting this option to a specific value sometimes improves performance.</span></span> <span data-ttu-id="b6418-120">Дополнительные сведения см. в статье [Настройка параметра конфигурации сервера max worker threads](configure-the-max-worker-threads-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="b6418-120">For more information, see [Configure the max worker threads Server Configuration Option](configure-the-max-worker-threads-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="b6418-121">**Повысить приоритет SQL Server**</span><span class="sxs-lookup"><span data-stu-id="b6418-121">**Boost SQL Server priority**</span></span>  
 <span data-ttu-id="b6418-122">Указывает, следует ли [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выставить более высокий приоритет планирования [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows по сравнению с другими процессами на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="b6418-122">Specifies whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should run at a higher [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows scheduling priority than other processes on the same computer.</span></span> <span data-ttu-id="b6418-123">Дополнительные сведения см. в статье [Настройка параметра конфигурации сервера priority boost](configure-the-priority-boost-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="b6418-123">For more information, see [Configure the priority boost Server Configuration Option](configure-the-priority-boost-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="b6418-124">**Использовать волокна Windows (использование упрощенных пулов)**</span><span class="sxs-lookup"><span data-stu-id="b6418-124">**Use Windows fibers (lightweight pooling)**</span></span>  
 <span data-ttu-id="b6418-125">Использовать легковесные потоки (волокна) Windows вместо обычных потоков для службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6418-125">Use Windows fibers instead of threads for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="b6418-126">Обратите внимание на то, что такая возможность доступна только в Windows 2003 Server Edition.</span><span class="sxs-lookup"><span data-stu-id="b6418-126">Note that this is only available in Windows 2003 Server Edition.</span></span> <span data-ttu-id="b6418-127">Дополнительные сведения см. в разделе [Параметр конфигурации сервера «использование упрощенных пулов»](lightweight-pooling-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="b6418-127">For more information, see [lightweight pooling Server Configuration Option](lightweight-pooling-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="b6418-128">**Настроенные значения**</span><span class="sxs-lookup"><span data-stu-id="b6418-128">**Configured Values**</span></span>  
 <span data-ttu-id="b6418-129">Отображает настроенные значения для параметров на этой панели.</span><span class="sxs-lookup"><span data-stu-id="b6418-129">Displays the configured values for the options on this pane.</span></span> <span data-ttu-id="b6418-130">В случае изменения этих значений выберите пункт **Текущие значения** и посмотрите, вступили ли в силу внесенные изменения.</span><span class="sxs-lookup"><span data-stu-id="b6418-130">If you change these values, click **Running Values** to see whether the changes have taken effect.</span></span> <span data-ttu-id="b6418-131">В противном случае первым должен быть перезапущен экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6418-131">If they have not, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be restarted first.</span></span>  
  
 <span data-ttu-id="b6418-132">**Текущие значения**</span><span class="sxs-lookup"><span data-stu-id="b6418-132">**Running Values**</span></span>  
 <span data-ttu-id="b6418-133">Просмотр текущих значений для параметров на этой панели.</span><span class="sxs-lookup"><span data-stu-id="b6418-133">View the currently running values for the options on this pane.</span></span> <span data-ttu-id="b6418-134">Эти значения доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b6418-134">These values are read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6418-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="b6418-135">See Also</span></span>  
 [<span data-ttu-id="b6418-136">Параметры конфигурации сервера (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b6418-136">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
