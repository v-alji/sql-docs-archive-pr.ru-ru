---
title: Редактор назначения обработки секций (страница "Дополнительно") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.advanced.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: 2039ee0f-069d-479d-90b2-2a12481b1162
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 12845ecd644eabd949ea37fbb18ba6cc9cf342f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655811"
---
# <a name="partition-processing-destination-editor-advanced-page"></a><span data-ttu-id="4d653-102">Редактор назначения обработки секций (страница «Дополнительно»)</span><span class="sxs-lookup"><span data-stu-id="4d653-102">Partition Processing Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="4d653-103">Страница **Дополнительно** диалогового окна **Редактор назначения обработки секций** позволяет настроить обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="4d653-103">Use the **Advanced** page of the **Partition Processing Destination Editor** dialog box to configure error handling.</span></span>  
  
 <span data-ttu-id="4d653-104">Дополнительные сведения о назначении для обработки секции см. в разделе [Partition Processing Destination](data-flow/partition-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="4d653-104">To learn more about the Partition Processing destination, see [Partition Processing Destination](data-flow/partition-processing-destination.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d653-105">Описанные здесь задачи не применимы к табличным моделям служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="4d653-105">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="4d653-106">Нельзя связать входные столбцы со столбцами секционирования для табличных моделей.</span><span class="sxs-lookup"><span data-stu-id="4d653-106">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="4d653-107">Вместо этого для обработки секции следует использовать задачу выполнения DDL [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="4d653-107">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4d653-108">Варианты</span><span class="sxs-lookup"><span data-stu-id="4d653-108">Options</span></span>  
 <span data-ttu-id="4d653-109">**Использовать конфигурацию ошибок по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="4d653-109">**Use default error configuration.**</span></span>  
 <span data-ttu-id="4d653-110">Укажите, нужно ли использовать обработку ошибок в службах [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4d653-110">Specify whether to use the default [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] error handling.</span></span> <span data-ttu-id="4d653-111">Значение по умолчанию — `True`.</span><span class="sxs-lookup"><span data-stu-id="4d653-111">By default, this value is `True`.</span></span>  
  
 <span data-ttu-id="4d653-112">**Действие при возникновении ошибки ключа**</span><span class="sxs-lookup"><span data-stu-id="4d653-112">**Key error action**</span></span>  
 <span data-ttu-id="4d653-113">Укажите способ обработки записей с недопустимыми ключевыми значениями.</span><span class="sxs-lookup"><span data-stu-id="4d653-113">Specify how to handle records that have unacceptable key values.</span></span>  
  
|<span data-ttu-id="4d653-114">Значение</span><span class="sxs-lookup"><span data-stu-id="4d653-114">Value</span></span>|<span data-ttu-id="4d653-115">Описание</span><span class="sxs-lookup"><span data-stu-id="4d653-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4d653-116">**ConvertToUnknown**</span><span class="sxs-lookup"><span data-stu-id="4d653-116">**ConvertToUnknown**</span></span>|<span data-ttu-id="4d653-117">Преобразовать неприемлемое значение ключа в значение Unknown.</span><span class="sxs-lookup"><span data-stu-id="4d653-117">Convert the unacceptable key value to the Unknown value.</span></span>|  
|<span data-ttu-id="4d653-118">**DiscardRecord**</span><span class="sxs-lookup"><span data-stu-id="4d653-118">**DiscardRecord**</span></span>|<span data-ttu-id="4d653-119">Удаляет запись.</span><span class="sxs-lookup"><span data-stu-id="4d653-119">Discard the record.</span></span>|  
  
 <span data-ttu-id="4d653-120">**Пропускать ошибки**</span><span class="sxs-lookup"><span data-stu-id="4d653-120">**Ignore errors**</span></span>  
 <span data-ttu-id="4d653-121">Указывает, что ошибки должны пропускаться.</span><span class="sxs-lookup"><span data-stu-id="4d653-121">Specify that errors should be ignored.</span></span>  
  
 <span data-ttu-id="4d653-122">**Остановить при возникновении ошибки**</span><span class="sxs-lookup"><span data-stu-id="4d653-122">**Stop on error**</span></span>  
 <span data-ttu-id="4d653-123">Указывает, что в случае ошибки обработка должна прерываться.</span><span class="sxs-lookup"><span data-stu-id="4d653-123">Specify that processing should stop when an error occurs.</span></span>  
  
 <span data-ttu-id="4d653-124">**Количество ошибок**</span><span class="sxs-lookup"><span data-stu-id="4d653-124">**Number of errors**</span></span>  
 <span data-ttu-id="4d653-125">Выберите порог ошибок, при достижении которого обработка должна закончиться, если выбран режим **Остановить при возникновении ошибки**.</span><span class="sxs-lookup"><span data-stu-id="4d653-125">Specify the error threshold at which processing should stop, if you have selected **Stop on error**.</span></span>  
  
 <span data-ttu-id="4d653-126">**Действие при возникновении ошибки**</span><span class="sxs-lookup"><span data-stu-id="4d653-126">**On error action**</span></span>  
 <span data-ttu-id="4d653-127">Если был выбран режим **Остановить при возникновении ошибки**, укажите действие, которое нужно выполнить при достижении порога ошибок.</span><span class="sxs-lookup"><span data-stu-id="4d653-127">Specify the action to take when the error threshold is reached, if you have selected **Stop on error**.</span></span>  
  
|<span data-ttu-id="4d653-128">Значение</span><span class="sxs-lookup"><span data-stu-id="4d653-128">Value</span></span>|<span data-ttu-id="4d653-129">Описание</span><span class="sxs-lookup"><span data-stu-id="4d653-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4d653-130">**StopProcessing**</span><span class="sxs-lookup"><span data-stu-id="4d653-130">**StopProcessing**</span></span>|<span data-ttu-id="4d653-131">Останавливает обработку.</span><span class="sxs-lookup"><span data-stu-id="4d653-131">Stop processing.</span></span>|  
|<span data-ttu-id="4d653-132">**StopLogging**</span><span class="sxs-lookup"><span data-stu-id="4d653-132">**StopLogging**</span></span>|<span data-ttu-id="4d653-133">Останавливает ведение журнала ошибок.</span><span class="sxs-lookup"><span data-stu-id="4d653-133">Stop logging errors.</span></span>|  
  
 <span data-ttu-id="4d653-134">**Ключ не найден**</span><span class="sxs-lookup"><span data-stu-id="4d653-134">**Key not found**</span></span>  
 <span data-ttu-id="4d653-135">Укажите действие при ошибке «Ключ не найден».</span><span class="sxs-lookup"><span data-stu-id="4d653-135">Specify the action to take for a key not found error.</span></span> <span data-ttu-id="4d653-136">По умолчанию, присваивается значение **Сообщить и продолжить**.</span><span class="sxs-lookup"><span data-stu-id="4d653-136">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="4d653-137">Значение</span><span class="sxs-lookup"><span data-stu-id="4d653-137">Value</span></span>|<span data-ttu-id="4d653-138">Описание</span><span class="sxs-lookup"><span data-stu-id="4d653-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4d653-139">**Пропустить ошибку**</span><span class="sxs-lookup"><span data-stu-id="4d653-139">**IgnoreError**</span></span>|<span data-ttu-id="4d653-140">Пропустить ошибку и продолжить обработку.</span><span class="sxs-lookup"><span data-stu-id="4d653-140">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="4d653-141">**Сообщить и продолжить**</span><span class="sxs-lookup"><span data-stu-id="4d653-141">**ReportAndContinue**</span></span>|<span data-ttu-id="4d653-142">Сообщить об ошибке и продолжить обработку.</span><span class="sxs-lookup"><span data-stu-id="4d653-142">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="4d653-143">**Сообщить и остановиться**</span><span class="sxs-lookup"><span data-stu-id="4d653-143">**ReportAndStop**</span></span>|<span data-ttu-id="4d653-144">Сообщить об ошибке и остановить обработку.</span><span class="sxs-lookup"><span data-stu-id="4d653-144">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="4d653-145">**Дублирующийся ключ**</span><span class="sxs-lookup"><span data-stu-id="4d653-145">**Duplicate key**</span></span>  
 <span data-ttu-id="4d653-146">Указывает действие при ошибке «Повторяющийся ключ».</span><span class="sxs-lookup"><span data-stu-id="4d653-146">Specify the action to take for a duplicate key error.</span></span> <span data-ttu-id="4d653-147">По умолчанию, присваивается значение **Пропустить ошибку**.</span><span class="sxs-lookup"><span data-stu-id="4d653-147">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="4d653-148">Значение</span><span class="sxs-lookup"><span data-stu-id="4d653-148">Value</span></span>|<span data-ttu-id="4d653-149">Описание</span><span class="sxs-lookup"><span data-stu-id="4d653-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4d653-150">**Пропустить ошибку**</span><span class="sxs-lookup"><span data-stu-id="4d653-150">**IgnoreError**</span></span>|<span data-ttu-id="4d653-151">Пропустить ошибку и продолжить обработку.</span><span class="sxs-lookup"><span data-stu-id="4d653-151">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="4d653-152">**Сообщить и продолжить**</span><span class="sxs-lookup"><span data-stu-id="4d653-152">**ReportAndContinue**</span></span>|<span data-ttu-id="4d653-153">Сообщить об ошибке и продолжить обработку.</span><span class="sxs-lookup"><span data-stu-id="4d653-153">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="4d653-154">**Сообщить и остановиться**</span><span class="sxs-lookup"><span data-stu-id="4d653-154">**ReportAndStop**</span></span>|<span data-ttu-id="4d653-155">Сообщить об ошибке и остановить обработку.</span><span class="sxs-lookup"><span data-stu-id="4d653-155">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="4d653-156">**Ключ NULL преобразован в неизвестный**</span><span class="sxs-lookup"><span data-stu-id="4d653-156">**Null key converted to unknown**</span></span>  
 <span data-ttu-id="4d653-157">Выберите действие для ситуации, когда ключ NULL был преобразован в значение Unknown.</span><span class="sxs-lookup"><span data-stu-id="4d653-157">Specify the action to take when a null key has been converted to the Unknown value.</span></span> <span data-ttu-id="4d653-158">По умолчанию, присваивается значение **Пропустить ошибку**.</span><span class="sxs-lookup"><span data-stu-id="4d653-158">By default, this value is **IgnoreError**.</span></span>  
  
|<span data-ttu-id="4d653-159">Значение</span><span class="sxs-lookup"><span data-stu-id="4d653-159">Value</span></span>|<span data-ttu-id="4d653-160">Описание</span><span class="sxs-lookup"><span data-stu-id="4d653-160">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4d653-161">**Пропустить ошибку**</span><span class="sxs-lookup"><span data-stu-id="4d653-161">**IgnoreError**</span></span>|<span data-ttu-id="4d653-162">Пропустить ошибку и продолжить обработку.</span><span class="sxs-lookup"><span data-stu-id="4d653-162">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="4d653-163">**Сообщить и продолжить**</span><span class="sxs-lookup"><span data-stu-id="4d653-163">**ReportAndContinue**</span></span>|<span data-ttu-id="4d653-164">Сообщить об ошибке и продолжить обработку.</span><span class="sxs-lookup"><span data-stu-id="4d653-164">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="4d653-165">**Сообщить и остановиться**</span><span class="sxs-lookup"><span data-stu-id="4d653-165">**ReportAndStop**</span></span>|<span data-ttu-id="4d653-166">Сообщить об ошибке и остановить обработку.</span><span class="sxs-lookup"><span data-stu-id="4d653-166">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="4d653-167">**Ключ NULL не разрешен**</span><span class="sxs-lookup"><span data-stu-id="4d653-167">**Null key not allowed**</span></span>  
 <span data-ttu-id="4d653-168">Указывает действие при обнаружении ключа NULL в случае запрета ключей NULL.</span><span class="sxs-lookup"><span data-stu-id="4d653-168">Specify the action to take when null keys are not allowed and a null key is encountered.</span></span> <span data-ttu-id="4d653-169">По умолчанию, присваивается значение **Сообщить и продолжить**.</span><span class="sxs-lookup"><span data-stu-id="4d653-169">By default, this value is **ReportAndContinue**.</span></span>  
  
|<span data-ttu-id="4d653-170">Значение</span><span class="sxs-lookup"><span data-stu-id="4d653-170">Value</span></span>|<span data-ttu-id="4d653-171">Описание</span><span class="sxs-lookup"><span data-stu-id="4d653-171">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4d653-172">**Пропустить ошибку**</span><span class="sxs-lookup"><span data-stu-id="4d653-172">**IgnoreError**</span></span>|<span data-ttu-id="4d653-173">Пропустить ошибку и продолжить обработку.</span><span class="sxs-lookup"><span data-stu-id="4d653-173">Ignore the error and continue processing.</span></span>|  
|<span data-ttu-id="4d653-174">**Сообщить и продолжить**</span><span class="sxs-lookup"><span data-stu-id="4d653-174">**ReportAndContinue**</span></span>|<span data-ttu-id="4d653-175">Сообщить об ошибке и продолжить обработку.</span><span class="sxs-lookup"><span data-stu-id="4d653-175">Report the error and continue processing.</span></span>|  
|<span data-ttu-id="4d653-176">**Сообщить и остановиться**</span><span class="sxs-lookup"><span data-stu-id="4d653-176">**ReportAndStop**</span></span>|<span data-ttu-id="4d653-177">Сообщить об ошибке и остановить обработку.</span><span class="sxs-lookup"><span data-stu-id="4d653-177">Report the error and stop processing.</span></span>|  
  
 <span data-ttu-id="4d653-178">**Путь к журналу ошибок**</span><span class="sxs-lookup"><span data-stu-id="4d653-178">**Error log path**</span></span>  
 <span data-ttu-id="4d653-179">Введите путь для журнала ошибок или выберите место назначения, нажав кнопку обзора **(...)** .</span><span class="sxs-lookup"><span data-stu-id="4d653-179">Type the path for the error log, or select a destination by using the browse **(...)** button.</span></span>  
  
 <span data-ttu-id="4d653-180">**Обзор (...)**</span><span class="sxs-lookup"><span data-stu-id="4d653-180">**Browse (...)**</span></span>  
 <span data-ttu-id="4d653-181">Укажите путь к журналу ошибок.</span><span class="sxs-lookup"><span data-stu-id="4d653-181">Select a path for the error log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d653-182">См. также:</span><span class="sxs-lookup"><span data-stu-id="4d653-182">See Also</span></span>  
 <span data-ttu-id="4d653-183">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="4d653-183">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="4d653-184">Редактор назначения "Обработка секций" (страница "Сопоставления")</span><span class="sxs-lookup"><span data-stu-id="4d653-184">Partition Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md)  
  
  
