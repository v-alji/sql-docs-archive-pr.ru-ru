---
title: Конфигурация ошибок (диалоговое окно «Структура интеллектуального анализа данных») (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.miningstructuredialog.general.f1
ms.assetid: d9aa028b-bad9-49c7-a81c-c2150e4dd481
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5eb41da36400271a9b058ecf275d26bd22d3ee53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669145"
---
# <a name="error-configuration-mining-structure-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="39c47-102">Конфигурация ошибок (диалоговое окно «Структура интеллектуального анализа данных») (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="39c47-102">Error Configuration (Mining Structure Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="39c47-103">Страница **Конфигурация ошибок** диалогового окна **Свойства структуры интеллектуального анализа данных** среды **SQL Server Management Studio** используется для задания свойств конфигурации ошибок структуры интеллектуального анализа данных в базе данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="39c47-103">Use the **Error Configuration** page of the **Mining Structure Properties** dialog box in **SQL Server Management Studio** to set the error configuration properties of a mining structure in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="39c47-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="39c47-104">Options</span></span>  
 <span data-ttu-id="39c47-105">**Использовать конфигурацию ошибок по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="39c47-105">**Use default error configuration**</span></span>  
 <span data-ttu-id="39c47-106">Выберите этот параметр, чтобы использовать конфигурацию ошибок по умолчанию для объектов в операциях обработки.</span><span class="sxs-lookup"><span data-stu-id="39c47-106">Select to use the default error configuration for objects in the processing operation.</span></span>  
  
 <span data-ttu-id="39c47-107">**Действие при возникновении ошибки ключа**</span><span class="sxs-lookup"><span data-stu-id="39c47-107">**Key error action**</span></span>  
 <span data-ttu-id="39c47-108">Выберите одно из следующих действий, происходящее при обнаружении нового ключа, который невозможно найти, во время обработки.</span><span class="sxs-lookup"><span data-stu-id="39c47-108">Choose one of the following actions that occur when a new key is encountered during processing that cannot be looked up:</span></span>  
  
-   <span data-ttu-id="39c47-109">**Преобразовать в неизвестный тип** — проводит статистическую обработку данных для записи в неизвестный тип.</span><span class="sxs-lookup"><span data-stu-id="39c47-109">**Convert to unknown** aggregates the information for the record into the unknown member.</span></span>  
  
-   <span data-ttu-id="39c47-110">**Отменить запись** — исключает данные для записи из процесса обработки вместе с объектом.</span><span class="sxs-lookup"><span data-stu-id="39c47-110">**Discard record** excludes the information for the record from being processed with the object.</span></span>  
  
 <span data-ttu-id="39c47-111">**Игнорировать счетчик ошибок**</span><span class="sxs-lookup"><span data-stu-id="39c47-111">**Ignore errors count**</span></span>  
 <span data-ttu-id="39c47-112">Нажмите для игнорирования всех ошибок во время обработки.</span><span class="sxs-lookup"><span data-stu-id="39c47-112">Click to ignore any errors that occur when processing.</span></span>  
  
 <span data-ttu-id="39c47-113">**Остановить при возникновении ошибки**</span><span class="sxs-lookup"><span data-stu-id="39c47-113">**Stop on error**</span></span>  
 <span data-ttu-id="39c47-114">Нажмите для остановки обработки при возникновении ошибок.</span><span class="sxs-lookup"><span data-stu-id="39c47-114">Click to stop processing when errors occur.</span></span> <span data-ttu-id="39c47-115">Этот режим включает режимы **Количество ошибок** и **Действие при возникновении ошибки** .</span><span class="sxs-lookup"><span data-stu-id="39c47-115">This option enables the **Number of errors** and the **On error action** options.</span></span>  
  
 <span data-ttu-id="39c47-116">**Количество ошибок**</span><span class="sxs-lookup"><span data-stu-id="39c47-116">**Number of errors**</span></span>  
 <span data-ttu-id="39c47-117">Введите количество ошибок, которые будут проигнорированы до остановки процесса.</span><span class="sxs-lookup"><span data-stu-id="39c47-117">Type the number of errors that are ignored before processing stops.</span></span>  
  
 <span data-ttu-id="39c47-118">**Действие при возникновении ошибки**</span><span class="sxs-lookup"><span data-stu-id="39c47-118">**On error action**</span></span>  
 <span data-ttu-id="39c47-119">Выберите одно из следующих действий для выполнения, когда количество ошибок превышает значение, указанное в параметре **Количество ошибок**.</span><span class="sxs-lookup"><span data-stu-id="39c47-119">Choose one of the following actions to be taken when the number of errors exceeds the value in **Number of errors**:</span></span>  
  
-   <span data-ttu-id="39c47-120">**Остановить обработку** — завершает операцию обработки.</span><span class="sxs-lookup"><span data-stu-id="39c47-120">**Stop processing** ends the processing operation.</span></span>  
  
-   <span data-ttu-id="39c47-121">**Остановить ведение журнала** — останавливает запись журнала ошибок, но не прекращает обработку.</span><span class="sxs-lookup"><span data-stu-id="39c47-121">**Stop logging** stops logging errors, but continues the processing operation.</span></span>  
  
 <span data-ttu-id="39c47-122">**Ключ не найден**</span><span class="sxs-lookup"><span data-stu-id="39c47-122">**Key not found**</span></span>  
 <span data-ttu-id="39c47-123">Укажите одно из следующих действий, которое должно быть предпринято, если во время обработки объекта ключ не найден.</span><span class="sxs-lookup"><span data-stu-id="39c47-123">Specify one of the following actions to be taken when a key is not found when an object is processed:</span></span>  
  
-   <span data-ttu-id="39c47-124">**Ignore Error** игнорирует ошибку</span><span class="sxs-lookup"><span data-stu-id="39c47-124">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="39c47-125">**Отчет и продолжение** сообщают об ошибке и продолжают операцию обработки</span><span class="sxs-lookup"><span data-stu-id="39c47-125">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="39c47-126">**Создать отчет и остановить выполнение** — вывести сообщение об ошибке и остановить операцию обработки.</span><span class="sxs-lookup"><span data-stu-id="39c47-126">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="39c47-127">**Дублирующийся ключ**</span><span class="sxs-lookup"><span data-stu-id="39c47-127">**Duplicate key**</span></span>  
 <span data-ttu-id="39c47-128">Укажите одно из следующих действий, которое должно предприниматься, если во время обработки объекта обнаружен повторяющийся ключ.</span><span class="sxs-lookup"><span data-stu-id="39c47-128">Specify one of the following actions to be taken if a duplicate key is found when an object is processed:</span></span>  
  
-   <span data-ttu-id="39c47-129">**Ignore Error** игнорирует ошибку</span><span class="sxs-lookup"><span data-stu-id="39c47-129">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="39c47-130">**Отчет и продолжение** сообщают об ошибке и продолжают операцию обработки</span><span class="sxs-lookup"><span data-stu-id="39c47-130">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="39c47-131">**Создать отчет и остановить выполнение** — вывести сообщение об ошибке и остановить операцию обработки.</span><span class="sxs-lookup"><span data-stu-id="39c47-131">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="39c47-132">**Ключ NULL преобразован в неизвестный**</span><span class="sxs-lookup"><span data-stu-id="39c47-132">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="39c47-133">Укажите одно из следующих действий, которое должно предприниматься, если во время обработки объекта ключ NULL элемента добавляется к неизвестному элементу.</span><span class="sxs-lookup"><span data-stu-id="39c47-133">Specify one of the following actions to be taken when a null member key is added to the unknown member when an object is processed.</span></span>  
  
-   <span data-ttu-id="39c47-134">**Ignore Error** игнорирует ошибку</span><span class="sxs-lookup"><span data-stu-id="39c47-134">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="39c47-135">**Отчет и продолжение** сообщают об ошибке и продолжают операцию обработки</span><span class="sxs-lookup"><span data-stu-id="39c47-135">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="39c47-136">**Создать отчет и остановить выполнение** — вывести сообщение об ошибке и остановить операцию обработки.</span><span class="sxs-lookup"><span data-stu-id="39c47-136">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="39c47-137">**Ключ NULL не разрешен**</span><span class="sxs-lookup"><span data-stu-id="39c47-137">**Null key not allowed**</span></span>  
 <span data-ttu-id="39c47-138">Укажите одно из следующих действий, которое должно быть предпринято, если во время обработки объекта найден недопустимый ключ NULL.</span><span class="sxs-lookup"><span data-stu-id="39c47-138">Specify one of the following actions to be taken when a null key is found, but not allowed, when an object is processed.</span></span>  
  
-   <span data-ttu-id="39c47-139">**Ignore Error** игнорирует ошибку</span><span class="sxs-lookup"><span data-stu-id="39c47-139">**Ignore error** ignores the error</span></span>  
  
-   <span data-ttu-id="39c47-140">**Отчет и продолжение** сообщают об ошибке и продолжают операцию обработки</span><span class="sxs-lookup"><span data-stu-id="39c47-140">**Report and continue** reports the error and continues the processing operation</span></span>  
  
-   <span data-ttu-id="39c47-141">**Создать отчет и остановить выполнение** — вывести сообщение об ошибке и остановить операцию обработки.</span><span class="sxs-lookup"><span data-stu-id="39c47-141">**Report and stop** reports the error and stops the processing operation.</span></span>  
  
 <span data-ttu-id="39c47-142">**Путь к журналу ошибок**</span><span class="sxs-lookup"><span data-stu-id="39c47-142">**Error log path**</span></span>  
 <span data-ttu-id="39c47-143">Введите полный путь и имя файла журнала ошибок.</span><span class="sxs-lookup"><span data-stu-id="39c47-143">Type the full path and file name for the error log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39c47-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="39c47-144">See Also</span></span>  
 <span data-ttu-id="39c47-145">[Диалоговое окно "Свойства структуры интеллектуального анализа данных &#40;Analysis Services"&#41;интеллектуального анализа](mining-structure-properties-dialog-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="39c47-145">[Mining Structure Properties Dialog &#40;Analysis Services - Data Mining&#41;](mining-structure-properties-dialog-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="39c47-146">Диалоговое окно «Общие &#40;структуры интеллектуального анализа данных»&#41; &#40;Analysis Services —&#41;интеллектуального анализа</span><span class="sxs-lookup"><span data-stu-id="39c47-146">General &#40;Mining Structure Dialog Box&#41; &#40;Analysis Services - Data Mining&#41;</span></span>](general-mining-structure-dialog-box-analysis-services-data-mining.md)  
  
  
