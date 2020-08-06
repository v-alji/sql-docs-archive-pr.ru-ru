---
title: Задать глобальные параметры трассировки (SQL Server Profiler) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- global trace options [SQL Server]
ms.assetid: 2854608a-c3c7-4eb8-b567-034bfec4b1a9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2f0809ae11776e1bddf42c189b86f48689ff4859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655493"
---
# <a name="set-global-trace-options-sql-server-profiler"></a><span data-ttu-id="fe100-102">установить глобальные параметры трассировки (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="fe100-102">Set Global Trace Options (SQL Server Profiler)</span></span>
  <span data-ttu-id="fe100-103">В этом разделе описывается, как настроить параметры, влияющие на все трассировки, созданные в экземпляре [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe100-103">This topic describes how to set options that apply to all traces that are created with a specific instance of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-set-global-trace-options"></a><span data-ttu-id="fe100-104">Настройка глобальных параметров трассировки</span><span class="sxs-lookup"><span data-stu-id="fe100-104">To set global trace options</span></span>  
  
1.  <span data-ttu-id="fe100-105">В меню **Сервис** выберите команду **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="fe100-105">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="fe100-106">В диалоговом окне **Общие параметры**нажмите кнопку **Выбрать шрифт**, настройте параметры отображения и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fe100-106">In the **General Options**dialog box, click **Choose Font**to modify the display options, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="fe100-107">При необходимости отметьте флажок **Начать трассировку немедленно после подключения**.</span><span class="sxs-lookup"><span data-stu-id="fe100-107">Optionally, select **Start tracing immediately after making connection**.</span></span>  
  
4.  <span data-ttu-id="fe100-108">При необходимости отметьте флажок **Обновить определение трассировки при изменении версии поставщика**.</span><span class="sxs-lookup"><span data-stu-id="fe100-108">Optionally, select **Update trace definition when provider version changes**.</span></span> <span data-ttu-id="fe100-109">Этот параметр рекомендуется использовать, поэтому он выключен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fe100-109">This option is recommended and is selected by default.</span></span> <span data-ttu-id="fe100-110">Если отмечен этот флажок, определение трассировки автоматически обновляется до текущей версии сервера, где она выполняется.</span><span class="sxs-lookup"><span data-stu-id="fe100-110">When this option is selected, the trace definition is automatically updated to the current version of the server where tracing is performed.</span></span>  
  
5.  <span data-ttu-id="fe100-111">При необходимости укажите, как сервер должен управлять переключаемыми файлами:</span><span class="sxs-lookup"><span data-stu-id="fe100-111">Optionally, specify how the server should manage rollover files:</span></span>  
  
    -   <span data-ttu-id="fe100-112">Выберите переключатель **Загружать все переключаемые файлы по порядку без дополнительных вопросов** , чтобы автоматически загружать переключаемые файлы во время воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="fe100-112">Select **Load all rollover files in sequence without prompting** to automatically load rollover files during replay.</span></span>  
  
    -   <span data-ttu-id="fe100-113">Выберите переключатель **Спрашивать перед загрузкой файлов прокрутки** , чтобы управлять переключаемыми файлами во время воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="fe100-113">Select **Prompt before loading rollover files** to control rollover files during replay.</span></span>  
  
    -   <span data-ttu-id="fe100-114">Выберите переключатель **Никогда не загружать последующие файлы прокрутки** , чтобы воспроизводить только один файл.</span><span class="sxs-lookup"><span data-stu-id="fe100-114">Select **Never load subsequent rollover files** to replay only one file at a time.</span></span>  
  
6.  <span data-ttu-id="fe100-115">При необходимости настройте параметры воспроизведения:</span><span class="sxs-lookup"><span data-stu-id="fe100-115">Optionally, set replay options:</span></span>  
  
    -   <span data-ttu-id="fe100-116">**Число потоков воспроизведения по умолчанию** позволяет управлять количеством потоков процессора, которые применяются во время воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="fe100-116">**Default number of replay threads** controls the number of processor threads to use during replay.</span></span> <span data-ttu-id="fe100-117">С увеличением количества потоков, воспроизведение выполняется быстрее, но снижается производительность сервера во время воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="fe100-117">A higher number of threads causes replay to complete faster, but causes server performance to degrade during replay.</span></span> <span data-ttu-id="fe100-118">Рекомендуется установить значение **4**.</span><span class="sxs-lookup"><span data-stu-id="fe100-118">The recommended setting is **4**.</span></span> <span data-ttu-id="fe100-119">Доступные параметры перечислены в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="fe100-119">The following table lists the available options:</span></span>  
  
        |<span data-ttu-id="fe100-120">Значение</span><span class="sxs-lookup"><span data-stu-id="fe100-120">Value</span></span>|<span data-ttu-id="fe100-121">Description</span><span class="sxs-lookup"><span data-stu-id="fe100-121">Description</span></span>|  
        |-----------|-----------------|  
        |<span data-ttu-id="fe100-122">**2**</span><span class="sxs-lookup"><span data-stu-id="fe100-122">**2**</span></span>|<span data-ttu-id="fe100-123">Минимальное значение.</span><span class="sxs-lookup"><span data-stu-id="fe100-123">Minimum value.</span></span> <span data-ttu-id="fe100-124">Для воспроизведения используется два потока.</span><span class="sxs-lookup"><span data-stu-id="fe100-124">Use two threads to replay.</span></span>|  
        |<span data-ttu-id="fe100-125">**4**</span><span class="sxs-lookup"><span data-stu-id="fe100-125">**4**</span></span>|<span data-ttu-id="fe100-126">Значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fe100-126">Default value.</span></span>|  
        |<span data-ttu-id="fe100-127">**255**</span><span class="sxs-lookup"><span data-stu-id="fe100-127">**255**</span></span>|<span data-ttu-id="fe100-128">Максимальное значение.</span><span class="sxs-lookup"><span data-stu-id="fe100-128">Maximum value.</span></span> <span data-ttu-id="fe100-129">Если установить максимальное значение, производительность других процессов ухудшится.</span><span class="sxs-lookup"><span data-stu-id="fe100-129">Setting a maximum value will impede performance for other processes.</span></span>|  
  
    -   <span data-ttu-id="fe100-130">**Интервал опроса монитора исправности по умолчанию (сек.)** определяет максимальное время в секундах, в течение которого поток воспроизведения может блокировать другие процессы.</span><span class="sxs-lookup"><span data-stu-id="fe100-130">**Default health monitor wait interval (sec)** sets the maximum amount of time that a replay thread can block another process in seconds.</span></span> <span data-ttu-id="fe100-131">Допустимые значения описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="fe100-131">The following table explains the values.</span></span>  
  
        |<span data-ttu-id="fe100-132">Значение</span><span class="sxs-lookup"><span data-stu-id="fe100-132">Value</span></span>|<span data-ttu-id="fe100-133">Description</span><span class="sxs-lookup"><span data-stu-id="fe100-133">Description</span></span>|  
        |-----------|-----------------|  
        |<span data-ttu-id="fe100-134">**0**</span><span class="sxs-lookup"><span data-stu-id="fe100-134">**0**</span></span>|<span data-ttu-id="fe100-135">Минимальное значение.</span><span class="sxs-lookup"><span data-stu-id="fe100-135">Minimum value.</span></span> <span data-ttu-id="fe100-136">Значение **0** означает, что [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] никогда не будет останавливать блокирующий процесс.</span><span class="sxs-lookup"><span data-stu-id="fe100-136">A setting of **0** means that [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] will never stop a blocking process.</span></span>|  
        |<span data-ttu-id="fe100-137">**3600**</span><span class="sxs-lookup"><span data-stu-id="fe100-137">**3600**</span></span>|<span data-ttu-id="fe100-138">Значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fe100-138">Default value.</span></span> <span data-ttu-id="fe100-139">Разрешает использовать блокирующие процессы, продолжительность которых не превышает **3600** секунд (один час).</span><span class="sxs-lookup"><span data-stu-id="fe100-139">Allow blocking processes that do not exceed **3600** seconds, or one hour.</span></span>|  
        |<span data-ttu-id="fe100-140">**86400**</span><span class="sxs-lookup"><span data-stu-id="fe100-140">**86400**</span></span>|<span data-ttu-id="fe100-141">Максимальное значение.</span><span class="sxs-lookup"><span data-stu-id="fe100-141">Maximum value.</span></span> <span data-ttu-id="fe100-142">Разрешает использовать блокирующие процессы, продолжительность которых не превышает **86400** секунд (один день).</span><span class="sxs-lookup"><span data-stu-id="fe100-142">Allow blocking processes that do not exceed **86400** seconds, or one day.</span></span>|  
  
    -   <span data-ttu-id="fe100-143">**Интервал опроса монитора исправности по умолчанию (сек.)** задает частоту опроса потоков воспроизведения для блокирующих процессов.</span><span class="sxs-lookup"><span data-stu-id="fe100-143">**Default health monitor poll interval (sec)** sets the frequency to poll replay threads for blocking processes.</span></span> <span data-ttu-id="fe100-144">Допустимые значения описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="fe100-144">The following table explains the values.</span></span>  
  
        |<span data-ttu-id="fe100-145">Значение</span><span class="sxs-lookup"><span data-stu-id="fe100-145">Value</span></span>|<span data-ttu-id="fe100-146">Description</span><span class="sxs-lookup"><span data-stu-id="fe100-146">Description</span></span>|  
        |-----------|-----------------|  
        |<span data-ttu-id="fe100-147">**1**</span><span class="sxs-lookup"><span data-stu-id="fe100-147">**1**</span></span>|<span data-ttu-id="fe100-148">Минимальное значение.</span><span class="sxs-lookup"><span data-stu-id="fe100-148">Minimum value.</span></span> <span data-ttu-id="fe100-149">Значение **1** означает, что [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] будет опрашивать блокирующие процессы один раз в секунду.</span><span class="sxs-lookup"><span data-stu-id="fe100-149">A setting of **1** means [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] will poll for blocking processes once per second.</span></span>|  
        |<span data-ttu-id="fe100-150">**60**</span><span class="sxs-lookup"><span data-stu-id="fe100-150">**60**</span></span>|<span data-ttu-id="fe100-151">Значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fe100-151">Default value.</span></span> <span data-ttu-id="fe100-152">Опрос блокирующих процессов выполняется один раз в минуту.</span><span class="sxs-lookup"><span data-stu-id="fe100-152">Poll for blocking processes once per minute.</span></span>|  
        |<span data-ttu-id="fe100-153">**86400**</span><span class="sxs-lookup"><span data-stu-id="fe100-153">**86400**</span></span>|<span data-ttu-id="fe100-154">Максимальное значение.</span><span class="sxs-lookup"><span data-stu-id="fe100-154">Maximum value.</span></span> <span data-ttu-id="fe100-155">Блокирующие процессы опрашиваются один раз в **86400** секунд (один день).</span><span class="sxs-lookup"><span data-stu-id="fe100-155">Poll for blocking processes once per **86400** seconds, or one day.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fe100-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="fe100-156">See Also</span></span>  
 <span data-ttu-id="fe100-157">[Задание значений по умолчанию для отображения трассировки (приложение SQL Server Profiler)](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="fe100-157">[Set Trace Display Defaults &#40;SQL Server Profiler&#41;](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="fe100-158">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="fe100-158">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
