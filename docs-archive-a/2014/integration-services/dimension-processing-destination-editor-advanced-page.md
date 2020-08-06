---
title: Редактор назначения «Обработка измерений» (страница «Дополнительно») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimprocessingtransformation.advanced.f1
helpviewer_keywords:
- Dimension Processing Destination Editor
ms.assetid: 2b30835a-2680-4d98-89a4-4f17e29e3818
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5be80cbbfb6871594d7481ccc0f9444d014885e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667820"
---
# <a name="dimension-processing-destination-editor-advanced-page"></a><span data-ttu-id="ca9c9-102">Редактор назначения обработки измерений (страница «Дополнительно»)</span><span class="sxs-lookup"><span data-stu-id="ca9c9-102">Dimension Processing Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="ca9c9-103">Используйте страницу **Дополнительно** диалогового окна **Редактор назначения обработки измерений** для настройки обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-103">Use the **Advanced** page of the **Dimension Processing Destination Editor** dialog box to configure error handling.</span></span>  
  
 <span data-ttu-id="ca9c9-104">Дополнительные сведения о назначении обработки измерений см. в разделе [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="ca9c9-104">To learn more about the Dimension Processing destination, see [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ca9c9-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="ca9c9-105">Options</span></span>  
 <span data-ttu-id="ca9c9-106">**Использовать конфигурацию ошибок по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-106">**Use default error configuration.**</span></span>  
 <span data-ttu-id="ca9c9-107">Укажите, нужно ли использовать обработку ошибок в службах [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-107">Specify whether to use the default [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] error handling.</span></span> <span data-ttu-id="ca9c9-108">Значение по умолчанию — `True`.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-108">By default, this value is `True`.</span></span>  
  
 <span data-ttu-id="ca9c9-109">**Действие при возникновении ошибки ключа**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-109">**Key error action**</span></span>  
 <span data-ttu-id="ca9c9-110">Укажите способ обработки записей с недопустимыми ключевыми значениями.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-110">Specify how to handle records that have unacceptable key values.</span></span>  
  
|<span data-ttu-id="ca9c9-111">Значение</span><span class="sxs-lookup"><span data-stu-id="ca9c9-111">Value</span></span>|<span data-ttu-id="ca9c9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ca9c9-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ca9c9-113">**ConvertToUnknown**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-113">**ConvertToUnknown**</span></span>|<span data-ttu-id="ca9c9-114">Преобразует недопустимое ключевое значение в значение `UnknownMember`.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-114">Convert the unacceptable key value to the `UnknownMember` value.</span></span>|  
|<span data-ttu-id="ca9c9-115">**DiscardRecord**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-115">**DiscardRecord**</span></span>|<span data-ttu-id="ca9c9-116">Удаляет запись.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-116">Discard the record.</span></span>|  
  
 <span data-ttu-id="ca9c9-117">**Пропускать ошибки**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-117">**Ignore errors**</span></span>  
 <span data-ttu-id="ca9c9-118">Указывает, что ошибки должны пропускаться.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-118">Specify that errors should be ignored.</span></span>  
  
 <span data-ttu-id="ca9c9-119">**Остановить при возникновении ошибки**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-119">**Stop on error**</span></span>  
 <span data-ttu-id="ca9c9-120">Указывает, что в случае ошибки обработка должна прерываться.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-120">Specify that processing should stop when an error occurs.</span></span>  
  
 <span data-ttu-id="ca9c9-121">**Количество ошибок**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-121">**Number of errors**</span></span>  
 <span data-ttu-id="ca9c9-122">Выберите порог ошибок, при котором обработка должна прерываться, если выбран режим **Остановить при возникновении ошибок**.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-122">Specify the error threshold at which processing should stop, if you have selected **Stop on errors**.</span></span>  
  
 <span data-ttu-id="ca9c9-123">**Действие при возникновении ошибки**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-123">**On error action**</span></span>  
 <span data-ttu-id="ca9c9-124">Если был выбран параметр **Остановить при возникновении ошибок**, укажите действие, которое нужно выполнить при достижении порога ошибок.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-124">Specify the action to take when the error threshold is reached, if you have selected **Stop on errors**.</span></span>  
  
|<span data-ttu-id="ca9c9-125">Значение</span><span class="sxs-lookup"><span data-stu-id="ca9c9-125">Value</span></span>|<span data-ttu-id="ca9c9-126">Описание</span><span class="sxs-lookup"><span data-stu-id="ca9c9-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ca9c9-127">**StopProcessing**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-127">**StopProcessing**</span></span>|<span data-ttu-id="ca9c9-128">Останавливает обработку.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-128">Stop processing.</span></span>|  
|<span data-ttu-id="ca9c9-129">**StopLogging**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-129">**StopLogging**</span></span>|<span data-ttu-id="ca9c9-130">Останавливает ведение журнала ошибок.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-130">Stop logging errors.</span></span>|  
  
 <span data-ttu-id="ca9c9-131">**Ключ не найден**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-131">**Key not found**</span></span>  
 <span data-ttu-id="ca9c9-132">Укажите действие при ошибке «Ключ не найден».</span><span class="sxs-lookup"><span data-stu-id="ca9c9-132">Specify the action to take for a key not found error.</span></span> <span data-ttu-id="ca9c9-133">По умолчанию, присваивается значение **Сообщить и продолжить**.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-133">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="ca9c9-134">Значение</span><span class="sxs-lookup"><span data-stu-id="ca9c9-134">Value</span></span>|<span data-ttu-id="ca9c9-135">Описание</span><span class="sxs-lookup"><span data-stu-id="ca9c9-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ca9c9-136">**Пропустить ошибку**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-136">**IgnoreError**</span></span>|<span data-ttu-id="ca9c9-137">Пропустить ошибку и продолжить обработку.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-137">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="ca9c9-138">**Сообщить и продолжить**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-138">**ReportAndContinue**</span></span>|<span data-ttu-id="ca9c9-139">Сообщить об ошибке и продолжить обработку.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-139">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="ca9c9-140">**Сообщить и остановиться**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-140">**ReportAndStop**</span></span>|<span data-ttu-id="ca9c9-141">Сообщить об ошибке и остановить обработку.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-141">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="ca9c9-142">**Дублирующийся ключ**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-142">**Duplicate key**</span></span>  
 <span data-ttu-id="ca9c9-143">Указывает действие при ошибке «Повторяющийся ключ».</span><span class="sxs-lookup"><span data-stu-id="ca9c9-143">Specify the action to take for a duplicate key error.</span></span> <span data-ttu-id="ca9c9-144">По умолчанию, присваивается значение **Пропустить ошибку**.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-144">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="ca9c9-145">Значение</span><span class="sxs-lookup"><span data-stu-id="ca9c9-145">Value</span></span>|<span data-ttu-id="ca9c9-146">Описание</span><span class="sxs-lookup"><span data-stu-id="ca9c9-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ca9c9-147">**Пропустить ошибку**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-147">**IgnoreError**</span></span>|<span data-ttu-id="ca9c9-148">Пропустить ошибку и продолжить обработку.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-148">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="ca9c9-149">**Сообщить и продолжить**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-149">**ReportAndContinue**</span></span>|<span data-ttu-id="ca9c9-150">Сообщить об ошибке и продолжить обработку.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-150">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="ca9c9-151">**Сообщить и остановиться**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-151">**ReportAndStop**</span></span>|<span data-ttu-id="ca9c9-152">Сообщить об ошибке и остановить обработку.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-152">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="ca9c9-153">**Ключ NULL преобразован в неизвестный**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-153">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="ca9c9-154">Задает действие, когда ключ NULL преобразован в значение `UnknownMember`.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-154">Specify the action to take when a null key has been converted to the `UnknownMember` value.</span></span> <span data-ttu-id="ca9c9-155">По умолчанию, присваивается значение **Пропустить ошибку**.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-155">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="ca9c9-156">Значение</span><span class="sxs-lookup"><span data-stu-id="ca9c9-156">Value</span></span>|<span data-ttu-id="ca9c9-157">Описание</span><span class="sxs-lookup"><span data-stu-id="ca9c9-157">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ca9c9-158">**Пропустить ошибку**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-158">**IgnoreError**</span></span>|<span data-ttu-id="ca9c9-159">Пропустить ошибку и продолжить обработку.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-159">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="ca9c9-160">**Сообщить и продолжить**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-160">**ReportAndContinue**</span></span>|<span data-ttu-id="ca9c9-161">Сообщить об ошибке и продолжить обработку.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-161">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="ca9c9-162">**Сообщить и остановиться**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-162">**ReportAndStop**</span></span>|<span data-ttu-id="ca9c9-163">Сообщить об ошибке и остановить обработку.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-163">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="ca9c9-164">**Ключ NULL не разрешен**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-164">**Null key not allowed**</span></span>  
 <span data-ttu-id="ca9c9-165">Указывает действие при обнаружении ключа NULL в случае запрета ключей NULL.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-165">Specify the action to take when null keys are not allowed and a null key is encountered.</span></span> <span data-ttu-id="ca9c9-166">По умолчанию, присваивается значение **Сообщить и продолжить**.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-166">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="ca9c9-167">Значение</span><span class="sxs-lookup"><span data-stu-id="ca9c9-167">Value</span></span>|<span data-ttu-id="ca9c9-168">Описание</span><span class="sxs-lookup"><span data-stu-id="ca9c9-168">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ca9c9-169">**Пропустить ошибку**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-169">**IgnoreError**</span></span>|<span data-ttu-id="ca9c9-170">Пропустить ошибку и продолжить обработку.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-170">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="ca9c9-171">**Сообщить и продолжить**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-171">**ReportAndContinue**</span></span>|<span data-ttu-id="ca9c9-172">Сообщить об ошибке и продолжить обработку.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-172">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="ca9c9-173">**Сообщить и остановиться**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-173">**ReportAndStop**</span></span>|<span data-ttu-id="ca9c9-174">Сообщить об ошибке и остановить обработку.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-174">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="ca9c9-175">**Путь к журналу ошибок**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-175">**Error log path**</span></span>  
 <span data-ttu-id="ca9c9-176">Введите путь к журналу ошибок или нажмите кнопку **Обзор(...)** для выбора назначения.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-176">Type the path of the error log, or click the **browse(...)** button to select a destination.</span></span>  
  
 <span data-ttu-id="ca9c9-177">**Обзор (...)**</span><span class="sxs-lookup"><span data-stu-id="ca9c9-177">**Browse (...)**</span></span>  
 <span data-ttu-id="ca9c9-178">Укажите путь к журналу ошибок.</span><span class="sxs-lookup"><span data-stu-id="ca9c9-178">Select a path for the error log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca9c9-179">См. также:</span><span class="sxs-lookup"><span data-stu-id="ca9c9-179">See Also</span></span>  
 <span data-ttu-id="ca9c9-180">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ca9c9-180">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="ca9c9-181">[Редактор назначения «Обработка измерений» &#40;страница «Диспетчер соединений»&#41;](../../2014/integration-services/dimension-processing-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="ca9c9-181">[Dimension Processing Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/dimension-processing-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="ca9c9-182">Редактор назначения "Обработка измерения" (страница "Сопоставления")</span><span class="sxs-lookup"><span data-stu-id="ca9c9-182">Dimension Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md)  
  
  
