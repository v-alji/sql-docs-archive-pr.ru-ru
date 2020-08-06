---
title: Диалоговое окно «Изменение параметров» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.process.batchsettingsdialog.f1
ms.assetid: 0041e042-d7ce-48f9-a690-a6dc65471ff3
author: minewiskan
ms.author: owend
ms.openlocfilehash: e2649195e3aff4e17d378e54c4b1d656361dfe3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657420"
---
# <a name="change-settings-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="6a6ba-102">Диалоговое окно «Изменение настроек» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="6a6ba-102">Change Settings Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="6a6ba-103">В диалоговом окне **Изменение настроек** в средах [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] и [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] можно изменить настройки обработки объектов, перечисленных в диалоговом окне **Обработка** .</span><span class="sxs-lookup"><span data-stu-id="6a6ba-103">Use the **Change Settings** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to change the settings that govern the processing of objects listed in the **Process** dialog box.</span></span> <span data-ttu-id="6a6ba-104">Открыть диалоговое окно **Изменить установки** можно, щелкнув **Изменить установки** в диалоговом окне **Обработка** .</span><span class="sxs-lookup"><span data-stu-id="6a6ba-104">You can display the **Change Settings** dialog box by clicking **Change Settings** on the **Process** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6a6ba-105"> Настройки, указанные в этом диалоговом окне, переопределяют настройки по умолчанию, унаследованные из базы данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] для объектов, перечисленных в диалоговом окне **Обработка** .</span><span class="sxs-lookup"><span data-stu-id="6a6ba-105">Settings specified in this dialog box override default settings inherited from the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database for the objects listed in the **Process** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6a6ba-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="6a6ba-106">Options</span></span>  
 <span data-ttu-id="6a6ba-107">**Параметры обработки**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-107">**Processing options**</span></span>  
 <span data-ttu-id="6a6ba-108">Используйте эту вкладку для изменения параметров порядка обработки, таблицы обратной записи и объектов, изменяемых при обработке.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-108">Use this tab to modify settings related to the processing order, writeback table, and affected objects for the processing operation.</span></span> <span data-ttu-id="6a6ba-109">Вкладка содержит следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-109">The tab contains the following options:</span></span>  
  
 <span data-ttu-id="6a6ba-110">**Parallel**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-110">**Parallel**</span></span>  
 <span data-ttu-id="6a6ba-111">Выберите этот параметр для параллельной обработки объектов.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-111">Click to process the objects in parallel.</span></span>  
  
 <span data-ttu-id="6a6ba-112">**Максимальное число параллельных задач**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-112">**Maximum parallel tasks**</span></span>  
 <span data-ttu-id="6a6ba-113">Задайте максимальное число задач, выполняемых при обработке параллельно, или выберите режим **Разрешить серверу принять решение** , чтобы службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] выбрали оптимальное число параллельных задач.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-113">Select the maximum number of tasks to execute in parallel by the processing operation, or choose **Let the server decide** to allow [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to select an optimal number of parallel tasks.</span></span>  
  
 <span data-ttu-id="6a6ba-114">**Последовательные**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-114">**Sequential**</span></span>  
 <span data-ttu-id="6a6ba-115">Выберите этот параметр для последовательной обработки объектов.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-115">Click to process the objects sequentially.</span></span>  
  
 <span data-ttu-id="6a6ba-116">**Режим транзакции**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-116">**Transaction mode**</span></span>  
 <span data-ttu-id="6a6ba-117">Выберите режим транзакции, используемый при последовательной обработке объектов.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-117">Choose the transaction mode that is used when objects are processed in sequential order:</span></span>  
  
-   <span data-ttu-id="6a6ba-118">**Одна транзакция** — обработка всех объектов в одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-118">**One Transaction** processes all objects in the same transaction.</span></span>  
  
-   <span data-ttu-id="6a6ba-119">**Отдельные транзакции** — обработка всех объектов, включая зависимые, в отдельных транзакциях.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-119">**Separate Transactions** processes all objects, including dependent objects, in separate transactions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6a6ba-120"> Данный параметр доступен, только если выбран режим **Последовательно** .</span><span class="sxs-lookup"><span data-stu-id="6a6ba-120">This option is enabled only if **Sequential** is selected.</span></span>  
  
 <span data-ttu-id="6a6ba-121">**Параметр таблицы обратной записи**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-121">**Writeback table option**</span></span>  
 <span data-ttu-id="6a6ba-122">Выберите режим работы с таблицей обратной записи.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-122">Choose the option used to manage a writeback table:</span></span>  
  
-   <span data-ttu-id="6a6ba-123">**Создать** — создает таблицу обратной записи, если она не существует.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-123">**Create** creates a writeback table if it does not exist.</span></span> <span data-ttu-id="6a6ba-124">Если таблица обратной записи уже существует, происходит ошибка.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-124">An error occurs if a writeback table already exists.</span></span>  
  
-   <span data-ttu-id="6a6ba-125">**Всегда создавать** — создает таблицу обратной записи, если она не существует, или перезаписывает существующую таблицу обратной записи.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-125">**Create always** creates a writeback table if it does not exist, or overwrites the existing writeback table if it does exist.</span></span>  
  
-   <span data-ttu-id="6a6ba-126">**Использовать существующие** — использовать существующие таблицы обратной записи, если они существуют.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-126">**Use existing** uses the existing writeback table if it exists.</span></span> <span data-ttu-id="6a6ba-127">Если таблица обратной записи не существует, происходит ошибка.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-127">An error occurs if a writeback table does not exist.</span></span>  
  
 <span data-ttu-id="6a6ba-128">**Обработать затронутые объекты**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-128">**Process affected objects**</span></span>  
 <span data-ttu-id="6a6ba-129">Выберите этот режим для включения и обработки объектов, зависящих от объектов, включенных в обработку.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-129">Select to include and process objects that depend on objects included in the processing operation.</span></span>  
  
 <span data-ttu-id="6a6ba-130">**Ошибки ключа измерения**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-130">**Dimension key errors**</span></span>  
 <span data-ttu-id="6a6ba-131">Эта вкладка позволяет изменять параметры конфигурации ошибок для процесса обработки.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-131">Use this tab to modify settings related to the error configuration for the processing operation.</span></span> <span data-ttu-id="6a6ba-132">Вкладка содержит следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-132">The tab contains the following options:</span></span>  
  
 <span data-ttu-id="6a6ba-133">**Использовать конфигурацию ошибок по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-133">**Use default error configuration**</span></span>  
 <span data-ttu-id="6a6ba-134">Выберите этот параметр, чтобы использовать конфигурацию ошибок по умолчанию для объектов в операциях обработки.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-134">Select to use the default error configuration for objects in the processing operation.</span></span>  
  
 <span data-ttu-id="6a6ba-135">**Использовать пользовательскую конфигурацию ошибок**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-135">**Use custom error configuration**</span></span>  
 <span data-ttu-id="6a6ba-136">Выбрать для определения конфигурации при сбое для объектов в процессе обработки.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-136">Select to define the error configuration for objects in the processing operation.</span></span>  
  
 <span data-ttu-id="6a6ba-137">**Действие при возникновении ошибки ключа**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-137">**Key error action**</span></span>  
 <span data-ttu-id="6a6ba-138">Выберите одно из следующих действий, происходящее при обнаружении нового ключа, который невозможно найти, во время обработки.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-138">Choose one of the following actions that occur when a new key is encountered during processing that cannot be looked up:</span></span>  
  
-   <span data-ttu-id="6a6ba-139">**Преобразовать в неизвестный тип** — проводит статистическую обработку данных для записи в неизвестный тип.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-139">**Convert to unknown** aggregates the information for the record into the unknown member.</span></span>  
  
-   <span data-ttu-id="6a6ba-140">**Отменить запись** — исключает данные для записи из процесса обработки вместе с объектом.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-140">**Discard record** excludes the information for the record from being processed with the object.</span></span>  
  
 <span data-ttu-id="6a6ba-141">**Игнорировать счетчик ошибок**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-141">**Ignore errors count**</span></span>  
 <span data-ttu-id="6a6ba-142">Нажмите для игнорирования всех ошибок во время обработки.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-142">Click to ignore any errors that occur when processing.</span></span>  
  
 <span data-ttu-id="6a6ba-143">**Остановить при возникновении ошибки**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-143">**Stop on error**</span></span>  
 <span data-ttu-id="6a6ba-144">Нажмите для остановки обработки при возникновении ошибок.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-144">Click to stop processing when errors occur.</span></span> <span data-ttu-id="6a6ba-145">Этот режим включает режимы **Количество ошибок** и **Действие при возникновении ошибки** .</span><span class="sxs-lookup"><span data-stu-id="6a6ba-145">This option enables the **Number of errors** and the **On error action** options.</span></span>  
  
 <span data-ttu-id="6a6ba-146">**Количество ошибок**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-146">**Number of errors**</span></span>  
 <span data-ttu-id="6a6ba-147">Введите количество ошибок, которые будут проигнорированы до остановки процесса.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-147">Type the number of errors that are ignored before processing stops.</span></span>  
  
 <span data-ttu-id="6a6ba-148">**Действие при возникновении ошибки**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-148">**On error action**</span></span>  
 <span data-ttu-id="6a6ba-149">Выберите одно из следующих действий для выполнения, когда количество ошибок превышает значение, указанное в параметре **Количество ошибок**.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-149">Choose one of the following actions to be taken when the number of errors exceeds the value in **Number of errors**:</span></span>  
  
-   <span data-ttu-id="6a6ba-150">**Остановить обработку** — завершает операцию обработки.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-150">**Stop processing** ends the processing operation.</span></span>  
  
-   <span data-ttu-id="6a6ba-151">**Остановить ведение журнала** — останавливает запись журнала ошибок, но не прекращает обработку.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-151">**Stop logging** stops logging errors, but continues the processing operation.</span></span>  
  
 <span data-ttu-id="6a6ba-152">**Ключ не найден**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-152">**Key not found**</span></span>  
 <span data-ttu-id="6a6ba-153">Укажите одно из следующих действий, которое должно быть предпринято, если во время обработки объекта ключ не найден.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-153">Specify one of the following actions to be taken when a key is not found when an object is processed:</span></span>  
  
-   <span data-ttu-id="6a6ba-154">**Пропускать ошибки** — пропускает ошибку.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-154">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="6a6ba-155">**Создать отчет и продолжить** — выводит сообщение об ошибке и продолжает обработку.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-155">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="6a6ba-156">**Создать отчет и остановить выполнение** — вывести сообщение об ошибке и остановить операцию обработки.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-156">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="6a6ba-157">**Дублирующийся ключ**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-157">**Duplicate key**</span></span>  
 <span data-ttu-id="6a6ba-158">Укажите одно из следующих действий, которое должно предприниматься, если во время обработки объекта обнаружен повторяющийся ключ.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-158">Specify one of the following actions to be taken if a duplicate key is found when an object is processed:</span></span>  
  
-   <span data-ttu-id="6a6ba-159">**Пропускать ошибки** — пропускает ошибку.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-159">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="6a6ba-160">**Создать отчет и продолжить** — выводит сообщение об ошибке и продолжает обработку.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-160">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="6a6ba-161">**Создать отчет и остановить выполнение** — вывести сообщение об ошибке и остановить операцию обработки.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-161">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="6a6ba-162">**Ключ NULL преобразован в неизвестный**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-162">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="6a6ba-163">Укажите одно из следующих действий для выполнения при добавлении ключа элемента NULL к неизвестному элементу во время обработки объекта.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-163">Specify one of the following actions to be taken when a null member key is added to the unknown member when an object is processed:</span></span>  
  
-   <span data-ttu-id="6a6ba-164">**Пропускать ошибки** — пропускает ошибку.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-164">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="6a6ba-165">**Создать отчет и продолжить** — выводит сообщение об ошибке и продолжает обработку.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-165">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="6a6ba-166">**Создать отчет и остановить выполнение** — вывести сообщение об ошибке и остановить операцию обработки.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-166">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="6a6ba-167">**Ключ NULL не разрешен**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-167">**Null key not allowed**</span></span>  
 <span data-ttu-id="6a6ba-168">Укажите одно из следующих действий для выполнения при обнаружении ключа Null, который не был разрешен, во время обработки объекта.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-168">Specify one of the following actions to be taken when a null key is found, but not allowed, when an object is processed:</span></span>  
  
-   <span data-ttu-id="6a6ba-169">**Пропускать ошибки** — пропускает ошибку.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-169">**Ignore error** ignores the error.</span></span>  
  
-   <span data-ttu-id="6a6ba-170">**Создать отчет и продолжить** — выводит сообщение об ошибке и продолжает обработку.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-170">**Report and continue** reports the error and continues the processing operation.</span></span>  
  
-   <span data-ttu-id="6a6ba-171">**Создать отчет и остановить выполнение** — вывести сообщение об ошибке и остановить операцию обработки.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-171">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="6a6ba-172">**Путь к журналу ошибок**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-172">**Error log path**</span></span>  
 <span data-ttu-id="6a6ba-173">Введите полный путь и имя файла журнала ошибок.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-173">Type the full path and file name for the error log file.</span></span>  
  
 <span data-ttu-id="6a6ba-174">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-174">**Browse**</span></span>  
 <span data-ttu-id="6a6ba-175">Выберите, чтобы открыть диалоговое окно **Открыть** , и выберите полный путь и имя файла для журнала ошибок.</span><span class="sxs-lookup"><span data-stu-id="6a6ba-175">Click to open the **Open** dialog box and select the full path and file name for the error log file.</span></span>  
  
 <span data-ttu-id="6a6ba-176">**Обработать затронутые объекты**</span><span class="sxs-lookup"><span data-stu-id="6a6ba-176">**Process affected objects**</span></span>  
 <span data-ttu-id="6a6ba-177">Выберите этот пункт, чтобы обработать объекты, зависящие от объектов, выбранных в диалоговом окне **Обработка** .</span><span class="sxs-lookup"><span data-stu-id="6a6ba-177">Click to process the objects that have a dependency on the objects selected in the **Process** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a6ba-178">См. также:</span><span class="sxs-lookup"><span data-stu-id="6a6ba-178">See Also</span></span>  
 <span data-ttu-id="6a6ba-179">[Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="6a6ba-179">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="6a6ba-180">Диалоговое окно "обработка" &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="6a6ba-180">Process Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](process-dialog-box-analysis-services-multidimensional-data.md)  
  
  
