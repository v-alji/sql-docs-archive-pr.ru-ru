---
title: Перечислимые константы в выражениях свойств | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- enumerators [Integration Services]
- packages [Integration Services], expressions
- dynamic properties
- updating package properties
- enumerated constants [Integration Services]
- property expressions [Integration Services]
ms.assetid: a4418315-38e2-4ad3-8784-576163b25d6f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9cb4ae32bf564e98d8cfc843e9497b15222fa79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732862"
---
# <a name="enumerated-constants-in-property-expressions"></a><span data-ttu-id="86146-102">Констант-перечислителей в выражениях свойств</span><span class="sxs-lookup"><span data-stu-id="86146-102">Enumerated Constants in Property Expressions</span></span>
  <span data-ttu-id="86146-103">Если выражения свойств включают в себя значения из списка элементов-перечислителей, эти выражения должны использовать числовое значение элементов-перечислителей вместо понятного имени элемента.</span><span class="sxs-lookup"><span data-stu-id="86146-103">If property expressions include values from an enumerator member list, the expression must use the numeric value of the enumerator member instead of the friendly name of the member.</span></span> <span data-ttu-id="86146-104">Например, если выражение устанавливает свойство `LoggingMode`, необходимо использовать числовое значение 2 вместо понятного имени «Запрещено».</span><span class="sxs-lookup"><span data-stu-id="86146-104">For example, if an expression sets the `LoggingMode` property then you must use the numeric value 2 instead of the friendly name Disabled.</span></span>  
  
 <span data-ttu-id="86146-105">Этот раздел приводит список числовых значений, эквивалентных понятным именам перечислителей, элементы которых, как правило, используются в выражениях свойств.</span><span class="sxs-lookup"><span data-stu-id="86146-105">This topic lists only the numeric values equivalent to friendly names of enumerators whose members are commonly used in property expressions.</span></span> <span data-ttu-id="86146-106">Объектная модель служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] включает много дополнительных перечислителей, которые используются при программировании объектной модели для программного построения пакетов или при создании кода элементов пользовательских пакетов, таких как задачи и компоненты потоков данных.</span><span class="sxs-lookup"><span data-stu-id="86146-106">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model includes many additional enumerators that you use when you program the object model to build packages programmatically or code custom package elements such as tasks and data flow components.</span></span>  
  
 <span data-ttu-id="86146-107">В дополнение к пользовательским свойствам пакетов и объектов пакетов окно свойств в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] включает набор свойств, которые доступны пакетам, задачам, контейнерам последовательности, «цикл по элементам» и «цикл по каждому элементу».</span><span class="sxs-lookup"><span data-stu-id="86146-107">In addition to the custom properties for packages and package objects, the Properties window in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] includes a set of properties that are available to packages, tasks, and the Foreach Loop, For Loop, and Sequence containers.</span></span> <span data-ttu-id="86146-108">Общие свойства, которые задаются значениями из перечислителей `ForceExecutionResult` , `LoggingMode` `IsolationLevel` `Transaction Option` перечислены в разделе Общие свойства.</span><span class="sxs-lookup"><span data-stu-id="86146-108">The common properties that are set by values from enumerators-`ForceExecutionResult`, `LoggingMode`, `IsolationLevel`, and `Transaction Option`-are listed in Common Properties section.</span></span>  
  
 <span data-ttu-id="86146-109">Ниже приведены сведения о перечислителях-константах.</span><span class="sxs-lookup"><span data-stu-id="86146-109">The following sections provide information about enumerated constants:</span></span>  
  
 [<span data-ttu-id="86146-110">Пакет</span><span class="sxs-lookup"><span data-stu-id="86146-110">Package</span></span>](#Package)  
  
 [<span data-ttu-id="86146-111">Перечислители контейнера «цикл по каждому элементу»</span><span class="sxs-lookup"><span data-stu-id="86146-111">Foreach Loop Enumerators</span></span>](#Foreach)  
  
 [<span data-ttu-id="86146-112">Задачи</span><span class="sxs-lookup"><span data-stu-id="86146-112">Tasks</span></span>](#Tasks)  
  
 [<span data-ttu-id="86146-113">Задачи плана обслуживания</span><span class="sxs-lookup"><span data-stu-id="86146-113">Maintenance Plan Tasks</span></span>](#MaintenancePlanTasks)  
  
 [<span data-ttu-id="86146-114">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="86146-114">Common Properties</span></span>](#CommonProperties)  
  
##  <a name="package"></a><a name="Package"></a> <span data-ttu-id="86146-115">Пакет</span><span class="sxs-lookup"><span data-stu-id="86146-115">Package</span></span>  
 <span data-ttu-id="86146-116">В следующих таблицах приводятся списки понятных имен и эквивалентных числовых значений для свойств пакетов, которые устанавливаются с использованием значений перечислителей.</span><span class="sxs-lookup"><span data-stu-id="86146-116">The following tables lists the friendly names and the numeric value equivalents for properties of packages that you set by using values from an enumerator.</span></span>  
  
 <span data-ttu-id="86146-117">`PackageType`свойство задается с помощью значений из `DTSPackageType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-117">`PackageType` property-Set by using values from the `DTSPackageType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-118">Понятное имя в перечислении DTSPackageType</span><span class="sxs-lookup"><span data-stu-id="86146-118">Friendly name in DTSPackageType</span></span>|<span data-ttu-id="86146-119">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-119">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="86146-120">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="86146-120">Default</span></span>|<span data-ttu-id="86146-121">0</span><span class="sxs-lookup"><span data-stu-id="86146-121">0</span></span>|  
|<span data-ttu-id="86146-122">DTSWizard</span><span class="sxs-lookup"><span data-stu-id="86146-122">DTSWizard</span></span>|<span data-ttu-id="86146-123">1</span><span class="sxs-lookup"><span data-stu-id="86146-123">1</span></span>|  
|<span data-ttu-id="86146-124">DTSDesigner</span><span class="sxs-lookup"><span data-stu-id="86146-124">DTSDesigner</span></span>|<span data-ttu-id="86146-125">2</span><span class="sxs-lookup"><span data-stu-id="86146-125">2</span></span>|  
|<span data-ttu-id="86146-126">SQLReplication</span><span class="sxs-lookup"><span data-stu-id="86146-126">SQLReplication</span></span>|<span data-ttu-id="86146-127">3</span><span class="sxs-lookup"><span data-stu-id="86146-127">3</span></span>|  
|<span data-ttu-id="86146-128">DTSDesigner100</span><span class="sxs-lookup"><span data-stu-id="86146-128">DTSDesigner100</span></span>|<span data-ttu-id="86146-129">5</span><span class="sxs-lookup"><span data-stu-id="86146-129">5</span></span>|  
|<span data-ttu-id="86146-130">SQLDBMaint</span><span class="sxs-lookup"><span data-stu-id="86146-130">SQLDBMaint</span></span>|<span data-ttu-id="86146-131">6</span><span class="sxs-lookup"><span data-stu-id="86146-131">6</span></span>|  
  
 <span data-ttu-id="86146-132">`CheckpointUsage`свойство задается с помощью значений из `DTSCheckpointUsage` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-132">`CheckpointUsage` property-Set by using values from the `DTSCheckpointUsage` enumeration.</span></span>  
  
|<span data-ttu-id="86146-133">Понятное имя в перечислении DTSCheckpointUsage</span><span class="sxs-lookup"><span data-stu-id="86146-133">Friendly name in DTSCheckpointUsage</span></span>|<span data-ttu-id="86146-134">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-134">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="86146-135">Никогда</span><span class="sxs-lookup"><span data-stu-id="86146-135">Never</span></span>|<span data-ttu-id="86146-136">0</span><span class="sxs-lookup"><span data-stu-id="86146-136">0</span></span>|  
|<span data-ttu-id="86146-137">IfExists</span><span class="sxs-lookup"><span data-stu-id="86146-137">IfExists</span></span>|<span data-ttu-id="86146-138">1</span><span class="sxs-lookup"><span data-stu-id="86146-138">1</span></span>|  
|<span data-ttu-id="86146-139">Всегда</span><span class="sxs-lookup"><span data-stu-id="86146-139">Always</span></span>|<span data-ttu-id="86146-140">2</span><span class="sxs-lookup"><span data-stu-id="86146-140">2</span></span>|  
  
 <span data-ttu-id="86146-141">`PackagePriorityClass`свойство задается с помощью значений из `DTSPriorityClass` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-141">`PackagePriorityClass` property-Set by using values from the `DTSPriorityClass` enumeration.</span></span>  
  
|<span data-ttu-id="86146-142">Понятное имя в перечислении DTSPriorityClass</span><span class="sxs-lookup"><span data-stu-id="86146-142">Friendly name in DTSPriorityClass</span></span>|<span data-ttu-id="86146-143">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-143">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="86146-144">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="86146-144">Default</span></span>|<span data-ttu-id="86146-145">0</span><span class="sxs-lookup"><span data-stu-id="86146-145">0</span></span>|  
|<span data-ttu-id="86146-146">AboveNormal</span><span class="sxs-lookup"><span data-stu-id="86146-146">AboveNormal</span></span>|<span data-ttu-id="86146-147">1</span><span class="sxs-lookup"><span data-stu-id="86146-147">1</span></span>|  
|<span data-ttu-id="86146-148">Нормальный</span><span class="sxs-lookup"><span data-stu-id="86146-148">Normal</span></span>|<span data-ttu-id="86146-149">2</span><span class="sxs-lookup"><span data-stu-id="86146-149">2</span></span>|  
|<span data-ttu-id="86146-150">BelowNormal</span><span class="sxs-lookup"><span data-stu-id="86146-150">BelowNormal</span></span>|<span data-ttu-id="86146-151">3</span><span class="sxs-lookup"><span data-stu-id="86146-151">3</span></span>|  
|<span data-ttu-id="86146-152">Бездействие</span><span class="sxs-lookup"><span data-stu-id="86146-152">Idle</span></span>|<span data-ttu-id="86146-153">4</span><span class="sxs-lookup"><span data-stu-id="86146-153">4</span></span>|  
  
 <span data-ttu-id="86146-154">`ProtectionLevel`свойство задается с помощью значений из `DTSProtectionLevel` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-154">`ProtectionLevel` property-Set by using values from the `DTSProtectionLevel` enumeration.</span></span>  
  
|<span data-ttu-id="86146-155">Понятное имя в перечислении DTSProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="86146-155">Friendly name in DTSProtectionLevel</span></span>|<span data-ttu-id="86146-156">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-156">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="86146-157">DontSaveSensitive</span><span class="sxs-lookup"><span data-stu-id="86146-157">DontSaveSensitive</span></span>|<span data-ttu-id="86146-158">0</span><span class="sxs-lookup"><span data-stu-id="86146-158">0</span></span>|  
|<span data-ttu-id="86146-159">EncryptSensitiveWithUserKey</span><span class="sxs-lookup"><span data-stu-id="86146-159">EncryptSensitiveWithUserKey</span></span>|<span data-ttu-id="86146-160">1</span><span class="sxs-lookup"><span data-stu-id="86146-160">1</span></span>|  
|<span data-ttu-id="86146-161">EncryptSensitiveWithPassword</span><span class="sxs-lookup"><span data-stu-id="86146-161">EncryptSensitiveWithPassword</span></span>|<span data-ttu-id="86146-162">2</span><span class="sxs-lookup"><span data-stu-id="86146-162">2</span></span>|  
|<span data-ttu-id="86146-163">EncryptAllWithPassword</span><span class="sxs-lookup"><span data-stu-id="86146-163">EncryptAllWithPassword</span></span>|<span data-ttu-id="86146-164">3</span><span class="sxs-lookup"><span data-stu-id="86146-164">3</span></span>|  
|<span data-ttu-id="86146-165">EncryptAllWithUserKey</span><span class="sxs-lookup"><span data-stu-id="86146-165">EncryptAllWithUserKey</span></span>|<span data-ttu-id="86146-166">4</span><span class="sxs-lookup"><span data-stu-id="86146-166">4</span></span>|  
|<span data-ttu-id="86146-167">ServerStorage</span><span class="sxs-lookup"><span data-stu-id="86146-167">ServerStorage</span></span>|<span data-ttu-id="86146-168">5</span><span class="sxs-lookup"><span data-stu-id="86146-168">5</span></span>|  
  
##  <a name="precedence-constraints"></a><a name="PrecedenceConstraints"></a> <span data-ttu-id="86146-169">Управление очередностью</span><span class="sxs-lookup"><span data-stu-id="86146-169">Precedence Constraints</span></span>  
 <span data-ttu-id="86146-170">`EvalOp`свойство задается с помощью значений из `DTSPrecedenceEvalOp` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-170">`EvalOp` property-Set by using values from the `DTSPrecedenceEvalOp` enumeration.</span></span>  
  
|<span data-ttu-id="86146-171">Понятное имя в перечислении DTSPrecedenceEvalOp</span><span class="sxs-lookup"><span data-stu-id="86146-171">Friendly name in DTSPrecedenceEvalOp</span></span>|<span data-ttu-id="86146-172">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-172">Numeric value</span></span>|  
|------------------------------------------|-------------------|  
|<span data-ttu-id="86146-173">Выражение</span><span class="sxs-lookup"><span data-stu-id="86146-173">Expression</span></span>|<span data-ttu-id="86146-174">1</span><span class="sxs-lookup"><span data-stu-id="86146-174">1</span></span>|  
|<span data-ttu-id="86146-175">Ограничение</span><span class="sxs-lookup"><span data-stu-id="86146-175">Constraint</span></span>|<span data-ttu-id="86146-176">2</span><span class="sxs-lookup"><span data-stu-id="86146-176">2</span></span>|  
|<span data-ttu-id="86146-177">ExpressionAndConstraint</span><span class="sxs-lookup"><span data-stu-id="86146-177">ExpressionAndConstraint</span></span>|<span data-ttu-id="86146-178">3</span><span class="sxs-lookup"><span data-stu-id="86146-178">3</span></span>|  
|<span data-ttu-id="86146-179">ExpressionOrConstraint</span><span class="sxs-lookup"><span data-stu-id="86146-179">ExpressionOrConstraint</span></span>|<span data-ttu-id="86146-180">4</span><span class="sxs-lookup"><span data-stu-id="86146-180">4</span></span>|  
  
 <span data-ttu-id="86146-181">`Value`свойство задается с помощью значений из `DTSExecResult` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-181">`Value` property-Set by using values from the `DTSExecResult` enumeration.</span></span>  
  
|<span data-ttu-id="86146-182">Понятное имя</span><span class="sxs-lookup"><span data-stu-id="86146-182">Friendly Name</span></span>|<span data-ttu-id="86146-183">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-183">Numeric Value</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="86146-184">Успешно</span><span class="sxs-lookup"><span data-stu-id="86146-184">Success</span></span>|<span data-ttu-id="86146-185">0</span><span class="sxs-lookup"><span data-stu-id="86146-185">0</span></span>|  
|<span data-ttu-id="86146-186">Failure</span><span class="sxs-lookup"><span data-stu-id="86146-186">Failure</span></span>|<span data-ttu-id="86146-187">1</span><span class="sxs-lookup"><span data-stu-id="86146-187">1</span></span>|  
|<span data-ttu-id="86146-188">Completion</span><span class="sxs-lookup"><span data-stu-id="86146-188">Completion</span></span>|<span data-ttu-id="86146-189">2</span><span class="sxs-lookup"><span data-stu-id="86146-189">2</span></span>|  
|<span data-ttu-id="86146-190">Отменено</span><span class="sxs-lookup"><span data-stu-id="86146-190">Canceled</span></span>|<span data-ttu-id="86146-191">3</span><span class="sxs-lookup"><span data-stu-id="86146-191">3</span></span>|  
  
##  <a name="foreach-loop-enumerators"></a><a name="Foreach"></a> <span data-ttu-id="86146-192">Перечислители контейнера «цикл по каждому элементу»</span><span class="sxs-lookup"><span data-stu-id="86146-192">Foreach Loop Enumerators</span></span>  
 <span data-ttu-id="86146-193">Контейнер «цикл по каждому элементу» включает в себя набор перечислителей со свойствами, которые могут быть установлены с помощью выражений свойств.</span><span class="sxs-lookup"><span data-stu-id="86146-193">The Foreach Loop includes a set of enumerators with properties that can be set by property expressions.</span></span>  
  
### <a name="foreach-ado-enumerator"></a><span data-ttu-id="86146-194">Перечислитель ADO по каждой строке</span><span class="sxs-lookup"><span data-stu-id="86146-194">Foreach ADO Enumerator</span></span>  
 <span data-ttu-id="86146-195">`Type`свойство задается с помощью значений из `ADOEnumerationType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-195">`Type` property-Set by using values from the `ADOEnumerationType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-196">Понятное имя в перечислении ADOEnumerationType</span><span class="sxs-lookup"><span data-stu-id="86146-196">Friendly name in ADOEnumerationType</span></span>|<span data-ttu-id="86146-197">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-197">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="86146-198">EnumerateTables</span><span class="sxs-lookup"><span data-stu-id="86146-198">EnumerateTables</span></span>|<span data-ttu-id="86146-199">0</span><span class="sxs-lookup"><span data-stu-id="86146-199">0</span></span>|  
|<span data-ttu-id="86146-200">EnumerateAllRows</span><span class="sxs-lookup"><span data-stu-id="86146-200">EnumerateAllRows</span></span>|<span data-ttu-id="86146-201">1</span><span class="sxs-lookup"><span data-stu-id="86146-201">1</span></span>|  
|<span data-ttu-id="86146-202">EnumerateRowsInFirstTable</span><span class="sxs-lookup"><span data-stu-id="86146-202">EnumerateRowsInFirstTable</span></span>|<span data-ttu-id="86146-203">2</span><span class="sxs-lookup"><span data-stu-id="86146-203">2</span></span>|  
  
### <a name="foreach-nodelist-enumerator"></a><span data-ttu-id="86146-204">Перечислитель по набору узлов</span><span class="sxs-lookup"><span data-stu-id="86146-204">Foreach Nodelist Enumerator</span></span>  
 <span data-ttu-id="86146-205">`SourceDocumentType``InnerXPathStringSourceType`свойства, и **OuterXPathStringSourceType** задаются с помощью значений из `SourceType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-205">`SourceDocumentType`, `InnerXPathStringSourceType`, and **OuterXPathStringSourceType** properties-Set by using values from the `SourceType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-206">Понятное имя в перечислении SourceType</span><span class="sxs-lookup"><span data-stu-id="86146-206">Friendly name in SourceType</span></span>|<span data-ttu-id="86146-207">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-207">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="86146-208">FileConnection</span><span class="sxs-lookup"><span data-stu-id="86146-208">FileConnection</span></span>|<span data-ttu-id="86146-209">0</span><span class="sxs-lookup"><span data-stu-id="86146-209">0</span></span>|  
|<span data-ttu-id="86146-210">Переменная</span><span class="sxs-lookup"><span data-stu-id="86146-210">Variable</span></span>|<span data-ttu-id="86146-211">1</span><span class="sxs-lookup"><span data-stu-id="86146-211">1</span></span>|  
|<span data-ttu-id="86146-212">DirectInput</span><span class="sxs-lookup"><span data-stu-id="86146-212">DirectInput</span></span>|<span data-ttu-id="86146-213">2</span><span class="sxs-lookup"><span data-stu-id="86146-213">2</span></span>|  
  
 <span data-ttu-id="86146-214">`EnumerationType`свойство задается с помощью значений из `EnumerationType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-214">`EnumerationType` property-Set by using values from the `EnumerationType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-215">Понятное имя в перечислении EnumerationType</span><span class="sxs-lookup"><span data-stu-id="86146-215">Friendly name in EnumerationType</span></span>|<span data-ttu-id="86146-216">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-216">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="86146-217">Navigator</span><span class="sxs-lookup"><span data-stu-id="86146-217">Navigator</span></span>|<span data-ttu-id="86146-218">0</span><span class="sxs-lookup"><span data-stu-id="86146-218">0</span></span>|  
|<span data-ttu-id="86146-219">Узел</span><span class="sxs-lookup"><span data-stu-id="86146-219">Node</span></span>|<span data-ttu-id="86146-220">1</span><span class="sxs-lookup"><span data-stu-id="86146-220">1</span></span>|  
|<span data-ttu-id="86146-221">NodeText</span><span class="sxs-lookup"><span data-stu-id="86146-221">NodeText</span></span>|<span data-ttu-id="86146-222">2</span><span class="sxs-lookup"><span data-stu-id="86146-222">2</span></span>|  
|<span data-ttu-id="86146-223">ElementCollection</span><span class="sxs-lookup"><span data-stu-id="86146-223">ElementCollection</span></span>|<span data-ttu-id="86146-224">3</span><span class="sxs-lookup"><span data-stu-id="86146-224">3</span></span>|  
  
 <span data-ttu-id="86146-225">`InnerElementType`свойство задается с помощью значений из `InnerElementType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-225">`InnerElementType` property-Set by using values from the `InnerElementType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-226">Понятное имя в перечислении InnerElementType</span><span class="sxs-lookup"><span data-stu-id="86146-226">Friendly name in InnerElementType</span></span>|<span data-ttu-id="86146-227">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-227">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="86146-228">Navigator</span><span class="sxs-lookup"><span data-stu-id="86146-228">Navigator</span></span>|<span data-ttu-id="86146-229">0</span><span class="sxs-lookup"><span data-stu-id="86146-229">0</span></span>|  
|<span data-ttu-id="86146-230">Узел</span><span class="sxs-lookup"><span data-stu-id="86146-230">Node</span></span>|<span data-ttu-id="86146-231">1</span><span class="sxs-lookup"><span data-stu-id="86146-231">1</span></span>|  
|<span data-ttu-id="86146-232">NodeText</span><span class="sxs-lookup"><span data-stu-id="86146-232">NodeText</span></span>|<span data-ttu-id="86146-233">2</span><span class="sxs-lookup"><span data-stu-id="86146-233">2</span></span>|  
  
##  <a name="tasks"></a><a name="Tasks"></a> <span data-ttu-id="86146-234">Задачи</span><span class="sxs-lookup"><span data-stu-id="86146-234">Tasks</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="86146-235">включают в себя многочисленные задачи со свойствами, которые можно устанавливать с помощью выражений свойств.</span><span class="sxs-lookup"><span data-stu-id="86146-235">includes numerous tasks with properties that can be set by property expressions.</span></span>  
  
### <a name="analysis-services-execute-ddl-task"></a><span data-ttu-id="86146-236">Задача «Выполнение инструкции DDL служб Analysis Services»</span><span class="sxs-lookup"><span data-stu-id="86146-236">Analysis Services Execute DDL Task</span></span>  
 <span data-ttu-id="86146-237">`SourceType`свойство задается с помощью значений из `DDLSourceType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-237">`SourceType` property-Set by using values from the `DDLSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-238">Понятное имя в DDLSourceType</span><span class="sxs-lookup"><span data-stu-id="86146-238">Friendly name in DDLSourceType</span></span>|<span data-ttu-id="86146-239">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-239">Numeric value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="86146-240">DirectInput</span><span class="sxs-lookup"><span data-stu-id="86146-240">DirectInput</span></span>|<span data-ttu-id="86146-241">0</span><span class="sxs-lookup"><span data-stu-id="86146-241">0</span></span>|  
|<span data-ttu-id="86146-242">FileConnection</span><span class="sxs-lookup"><span data-stu-id="86146-242">FileConnection</span></span>|<span data-ttu-id="86146-243">1</span><span class="sxs-lookup"><span data-stu-id="86146-243">1</span></span>|  
|<span data-ttu-id="86146-244">Переменная</span><span class="sxs-lookup"><span data-stu-id="86146-244">Variable</span></span>|<span data-ttu-id="86146-245">2</span><span class="sxs-lookup"><span data-stu-id="86146-245">2</span></span>|  
  
### <a name="bulk-insert-task"></a><span data-ttu-id="86146-246">задача «Массовая вставка»</span><span class="sxs-lookup"><span data-stu-id="86146-246">Bulk Insert Task</span></span>  
 <span data-ttu-id="86146-247">`DataFileType`свойство задается с помощью значений из `DTSBulkInsert_DataFileType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-247">`DataFileType` property-Set by using values from the `DTSBulkInsert_DataFileType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-248">Понятное имя в перечислении DTSBulkInsert_DataFileType</span><span class="sxs-lookup"><span data-stu-id="86146-248">Friendly name in DTSBulkInsert_DataFileType</span></span>|<span data-ttu-id="86146-249">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-249">Numeric value</span></span>|  
|--------------------------------------------------|-------------------|  
|<span data-ttu-id="86146-250">DTSBulkInsert_DataFileType_Char</span><span class="sxs-lookup"><span data-stu-id="86146-250">DTSBulkInsert_DataFileType_Char</span></span>|<span data-ttu-id="86146-251">0</span><span class="sxs-lookup"><span data-stu-id="86146-251">0</span></span>|  
|<span data-ttu-id="86146-252">DTSBulkInsert_DataFileType_Native</span><span class="sxs-lookup"><span data-stu-id="86146-252">DTSBulkInsert_DataFileType_Native</span></span>|<span data-ttu-id="86146-253">1</span><span class="sxs-lookup"><span data-stu-id="86146-253">1</span></span>|  
|<span data-ttu-id="86146-254">DTSBulkInsert_DataFileType_WideChar</span><span class="sxs-lookup"><span data-stu-id="86146-254">DTSBulkInsert_DataFileType_WideChar</span></span>|<span data-ttu-id="86146-255">2</span><span class="sxs-lookup"><span data-stu-id="86146-255">2</span></span>|  
|<span data-ttu-id="86146-256">DTSBulkInsert_DataFileType_WideNative</span><span class="sxs-lookup"><span data-stu-id="86146-256">DTSBulkInsert_DataFileType_WideNative</span></span>|<span data-ttu-id="86146-257">3</span><span class="sxs-lookup"><span data-stu-id="86146-257">3</span></span>|  
  
### <a name="execute-sql-task"></a><span data-ttu-id="86146-258">Задача "Выполнение SQL"</span><span class="sxs-lookup"><span data-stu-id="86146-258">Execute SQL Task</span></span>  
 <span data-ttu-id="86146-259">`ResultSetType`свойство задается с помощью значений из `ResultSetType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-259">`ResultSetType` property-Set by using values from the `ResultSetType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-260">Понятное имя в перечислении ResultSetType</span><span class="sxs-lookup"><span data-stu-id="86146-260">Friendly name in ResultSetType</span></span>|<span data-ttu-id="86146-261">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-261">Numeric Value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="86146-262">ResultSetType_None</span><span class="sxs-lookup"><span data-stu-id="86146-262">ResultSetType_None</span></span>|<span data-ttu-id="86146-263">1</span><span class="sxs-lookup"><span data-stu-id="86146-263">1</span></span>|  
|<span data-ttu-id="86146-264">ResultSetType_SingleRow</span><span class="sxs-lookup"><span data-stu-id="86146-264">ResultSetType_SingleRow</span></span>|<span data-ttu-id="86146-265">2</span><span class="sxs-lookup"><span data-stu-id="86146-265">2</span></span>|  
|<span data-ttu-id="86146-266">ResultSetType_Rowset</span><span class="sxs-lookup"><span data-stu-id="86146-266">ResultSetType_Rowset</span></span>|<span data-ttu-id="86146-267">3</span><span class="sxs-lookup"><span data-stu-id="86146-267">3</span></span>|  
|<span data-ttu-id="86146-268">ResultSetType_XML</span><span class="sxs-lookup"><span data-stu-id="86146-268">ResultSetType_XML</span></span>|<span data-ttu-id="86146-269">4</span><span class="sxs-lookup"><span data-stu-id="86146-269">4</span></span>|  
  
 <span data-ttu-id="86146-270">`SqlStatementSourceType`свойство задается с помощью значений из `SqlStatementSourceType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-270">`SqlStatementSourceType` property-Set by using values from the `SqlStatementSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-271">Понятное имя в перечислении SqlStatementSourceType</span><span class="sxs-lookup"><span data-stu-id="86146-271">Friendly name in SqlStatementSourceType</span></span>|<span data-ttu-id="86146-272">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-272">Numeric Value</span></span>|  
|---------------------------------------------|-------------------|  
|<span data-ttu-id="86146-273">DirectInput</span><span class="sxs-lookup"><span data-stu-id="86146-273">DirectInput</span></span>|<span data-ttu-id="86146-274">1</span><span class="sxs-lookup"><span data-stu-id="86146-274">1</span></span>|  
|<span data-ttu-id="86146-275">FileConnection</span><span class="sxs-lookup"><span data-stu-id="86146-275">FileConnection</span></span>|<span data-ttu-id="86146-276">2</span><span class="sxs-lookup"><span data-stu-id="86146-276">2</span></span>|  
|<span data-ttu-id="86146-277">Переменная</span><span class="sxs-lookup"><span data-stu-id="86146-277">Variable</span></span>|<span data-ttu-id="86146-278">3</span><span class="sxs-lookup"><span data-stu-id="86146-278">3</span></span>|  
  
### <a name="file-system-task"></a><span data-ttu-id="86146-279">Задача "Файловая система"</span><span class="sxs-lookup"><span data-stu-id="86146-279">File System Task</span></span>  
 <span data-ttu-id="86146-280">`Operation`свойство задается с помощью значений из `DTSFileSystemOperation` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-280">`Operation` property-Set by using values from the `DTSFileSystemOperation` enumeration.</span></span>  
  
|<span data-ttu-id="86146-281">Понятное имя в перечислении DTSFileSystemOperation</span><span class="sxs-lookup"><span data-stu-id="86146-281">Friendly name in DTSFileSystemOperation</span></span>|<span data-ttu-id="86146-282">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-282">Numeric value</span></span>|  
|---------------------------------------------|-------------------|  
|<span data-ttu-id="86146-283">CopyFile</span><span class="sxs-lookup"><span data-stu-id="86146-283">CopyFile</span></span>|<span data-ttu-id="86146-284">0</span><span class="sxs-lookup"><span data-stu-id="86146-284">0</span></span>|  
|<span data-ttu-id="86146-285">MoveFile</span><span class="sxs-lookup"><span data-stu-id="86146-285">MoveFile</span></span>|<span data-ttu-id="86146-286">1</span><span class="sxs-lookup"><span data-stu-id="86146-286">1</span></span>|  
|<span data-ttu-id="86146-287">DeleteFile</span><span class="sxs-lookup"><span data-stu-id="86146-287">DeleteFile</span></span>|<span data-ttu-id="86146-288">2</span><span class="sxs-lookup"><span data-stu-id="86146-288">2</span></span>|  
|<span data-ttu-id="86146-289">RenameFile</span><span class="sxs-lookup"><span data-stu-id="86146-289">RenameFile</span></span>|<span data-ttu-id="86146-290">3</span><span class="sxs-lookup"><span data-stu-id="86146-290">3</span></span>|  
|<span data-ttu-id="86146-291">SetAttributes</span><span class="sxs-lookup"><span data-stu-id="86146-291">SetAttributes</span></span>|<span data-ttu-id="86146-292">4</span><span class="sxs-lookup"><span data-stu-id="86146-292">4</span></span>|  
|<span data-ttu-id="86146-293">CreateDirectory</span><span class="sxs-lookup"><span data-stu-id="86146-293">CreateDirectory</span></span>|<span data-ttu-id="86146-294">5</span><span class="sxs-lookup"><span data-stu-id="86146-294">5</span></span>|  
|<span data-ttu-id="86146-295">CopyDirectory</span><span class="sxs-lookup"><span data-stu-id="86146-295">CopyDirectory</span></span>|<span data-ttu-id="86146-296">6</span><span class="sxs-lookup"><span data-stu-id="86146-296">6</span></span>|  
|<span data-ttu-id="86146-297">MoveDirectory</span><span class="sxs-lookup"><span data-stu-id="86146-297">MoveDirectory</span></span>|<span data-ttu-id="86146-298">7</span><span class="sxs-lookup"><span data-stu-id="86146-298">7</span></span>|  
|<span data-ttu-id="86146-299">DeleteDirectory</span><span class="sxs-lookup"><span data-stu-id="86146-299">DeleteDirectory</span></span>|<span data-ttu-id="86146-300">8</span><span class="sxs-lookup"><span data-stu-id="86146-300">8</span></span>|  
|<span data-ttu-id="86146-301">DeleteDirectoryContent</span><span class="sxs-lookup"><span data-stu-id="86146-301">DeleteDirectoryContent</span></span>|<span data-ttu-id="86146-302">9</span><span class="sxs-lookup"><span data-stu-id="86146-302">9</span></span>|  
  
 <span data-ttu-id="86146-303">`Attributes`свойство задается с помощью значений из `DTSFileSystemAttributes` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-303">`Attributes` property-Set by using values from the `DTSFileSystemAttributes` enumeration.</span></span>  
  
|<span data-ttu-id="86146-304">Понятное имя в перечислении DTSFileSystemAttributes</span><span class="sxs-lookup"><span data-stu-id="86146-304">Friendly name in DTSFileSystemAttributes</span></span>|<span data-ttu-id="86146-305">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-305">Numeric value</span></span>|  
|----------------------------------------------|-------------------|  
|<span data-ttu-id="86146-306">Нормальный</span><span class="sxs-lookup"><span data-stu-id="86146-306">Normal</span></span>|<span data-ttu-id="86146-307">0</span><span class="sxs-lookup"><span data-stu-id="86146-307">0</span></span>|  
|<span data-ttu-id="86146-308">Архив</span><span class="sxs-lookup"><span data-stu-id="86146-308">Archive</span></span>|<span data-ttu-id="86146-309">1</span><span class="sxs-lookup"><span data-stu-id="86146-309">1</span></span>|  
|<span data-ttu-id="86146-310">Скрытый</span><span class="sxs-lookup"><span data-stu-id="86146-310">Hidden</span></span>|<span data-ttu-id="86146-311">2</span><span class="sxs-lookup"><span data-stu-id="86146-311">2</span></span>|  
|<span data-ttu-id="86146-312">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="86146-312">ReadOnly</span></span>|<span data-ttu-id="86146-313">4</span><span class="sxs-lookup"><span data-stu-id="86146-313">4</span></span>|  
|<span data-ttu-id="86146-314">Система</span><span class="sxs-lookup"><span data-stu-id="86146-314">System</span></span>|<span data-ttu-id="86146-315">8</span><span class="sxs-lookup"><span data-stu-id="86146-315">8</span></span>|  
  
### <a name="ftp-task"></a><span data-ttu-id="86146-316">Задача «FTP»</span><span class="sxs-lookup"><span data-stu-id="86146-316">FTP Task</span></span>  
 <span data-ttu-id="86146-317">`Operation`свойство задается с помощью значений из `DTSFTPOp` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-317">`Operation` property-Set by using values from the `DTSFTPOp` enumeration.</span></span>  
  
|<span data-ttu-id="86146-318">Понятное имя в перечислении DTSFTPOp</span><span class="sxs-lookup"><span data-stu-id="86146-318">Friendly name in DTSFTPOp</span></span>|<span data-ttu-id="86146-319">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-319">Numeric value</span></span>|  
|-------------------------------|-------------------|  
|<span data-ttu-id="86146-320">Send</span><span class="sxs-lookup"><span data-stu-id="86146-320">Send</span></span>|<span data-ttu-id="86146-321">0</span><span class="sxs-lookup"><span data-stu-id="86146-321">0</span></span>|  
|<span data-ttu-id="86146-322">Receive</span><span class="sxs-lookup"><span data-stu-id="86146-322">Receive</span></span>|<span data-ttu-id="86146-323">1</span><span class="sxs-lookup"><span data-stu-id="86146-323">1</span></span>|  
|<span data-ttu-id="86146-324">DeleteLocal</span><span class="sxs-lookup"><span data-stu-id="86146-324">DeleteLocal</span></span>|<span data-ttu-id="86146-325">2</span><span class="sxs-lookup"><span data-stu-id="86146-325">2</span></span>|  
|<span data-ttu-id="86146-326">DeleteRemote</span><span class="sxs-lookup"><span data-stu-id="86146-326">DeleteRemote</span></span>|<span data-ttu-id="86146-327">3</span><span class="sxs-lookup"><span data-stu-id="86146-327">3</span></span>|  
|<span data-ttu-id="86146-328">MakeDirLocal</span><span class="sxs-lookup"><span data-stu-id="86146-328">MakeDirLocal</span></span>|<span data-ttu-id="86146-329">4</span><span class="sxs-lookup"><span data-stu-id="86146-329">4</span></span>|  
|<span data-ttu-id="86146-330">MakeDirRemote</span><span class="sxs-lookup"><span data-stu-id="86146-330">MakeDirRemote</span></span>|<span data-ttu-id="86146-331">5</span><span class="sxs-lookup"><span data-stu-id="86146-331">5</span></span>|  
|<span data-ttu-id="86146-332">RemoveDirLocal</span><span class="sxs-lookup"><span data-stu-id="86146-332">RemoveDirLocal</span></span>|<span data-ttu-id="86146-333">6</span><span class="sxs-lookup"><span data-stu-id="86146-333">6</span></span>|  
|<span data-ttu-id="86146-334">RemoveDirRemote</span><span class="sxs-lookup"><span data-stu-id="86146-334">RemoveDirRemote</span></span>|<span data-ttu-id="86146-335">7</span><span class="sxs-lookup"><span data-stu-id="86146-335">7</span></span>|  
  
### <a name="message-queue-task"></a><span data-ttu-id="86146-336">Message Queue Task</span><span class="sxs-lookup"><span data-stu-id="86146-336">Message Queue Task</span></span>  
 <span data-ttu-id="86146-337">`MessageType`свойство задается с помощью значений из `MQMessageType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-337">`MessageType` property-Set by using values from the `MQMessageType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-338">Понятное имя в перечислении MQMessageType</span><span class="sxs-lookup"><span data-stu-id="86146-338">Friendly name in MQMessageType</span></span>|<span data-ttu-id="86146-339">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-339">Numeric value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="86146-340">DTSMQMessageType_String</span><span class="sxs-lookup"><span data-stu-id="86146-340">DTSMQMessageType_String</span></span>|<span data-ttu-id="86146-341">0</span><span class="sxs-lookup"><span data-stu-id="86146-341">0</span></span>|  
|<span data-ttu-id="86146-342">DTSMQMessageType_DataFile</span><span class="sxs-lookup"><span data-stu-id="86146-342">DTSMQMessageType_DataFile</span></span>|<span data-ttu-id="86146-343">1</span><span class="sxs-lookup"><span data-stu-id="86146-343">1</span></span>|  
|<span data-ttu-id="86146-344">DTSMQMessageType_Variables</span><span class="sxs-lookup"><span data-stu-id="86146-344">DTSMQMessageType_Variables</span></span>|<span data-ttu-id="86146-345">2</span><span class="sxs-lookup"><span data-stu-id="86146-345">2</span></span>|  
|<span data-ttu-id="86146-346">DTSMQMessagType_StringMessageToVariable</span><span class="sxs-lookup"><span data-stu-id="86146-346">DTSMQMessagType_StringMessageToVariable</span></span>|<span data-ttu-id="86146-347">3</span><span class="sxs-lookup"><span data-stu-id="86146-347">3</span></span>|  
  
 <span data-ttu-id="86146-348">`StringCompareType`свойство задается с помощью значений из `MQStringMessageCompare` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-348">`StringCompareType` property-Set by using values from the `MQStringMessageCompare` enumeration.</span></span>  
  
|<span data-ttu-id="86146-349">Понятное имя в перечислении MQStringMessageCompare</span><span class="sxs-lookup"><span data-stu-id="86146-349">Friendly name in MQStringMessageCompare</span></span>|<span data-ttu-id="86146-350">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-350">Numeric value</span></span>|  
|---------------------------------------------|-------------------|  
|<span data-ttu-id="86146-351">DTSMQStringMessageCompare_None</span><span class="sxs-lookup"><span data-stu-id="86146-351">DTSMQStringMessageCompare_None</span></span>|<span data-ttu-id="86146-352">0</span><span class="sxs-lookup"><span data-stu-id="86146-352">0</span></span>|  
|<span data-ttu-id="86146-353">DTSMQStringMessageCompare_Exact</span><span class="sxs-lookup"><span data-stu-id="86146-353">DTSMQStringMessageCompare_Exact</span></span>|<span data-ttu-id="86146-354">1</span><span class="sxs-lookup"><span data-stu-id="86146-354">1</span></span>|  
|<span data-ttu-id="86146-355">DTSMQStringMessageCompare_IgnoreCase</span><span class="sxs-lookup"><span data-stu-id="86146-355">DTSMQStringMessageCompare_IgnoreCase</span></span>|<span data-ttu-id="86146-356">2</span><span class="sxs-lookup"><span data-stu-id="86146-356">2</span></span>|  
|<span data-ttu-id="86146-357">DTSMQStringMessageCompare_Contains</span><span class="sxs-lookup"><span data-stu-id="86146-357">DTSMQStringMessageCompare_Contains</span></span>|<span data-ttu-id="86146-358">3</span><span class="sxs-lookup"><span data-stu-id="86146-358">3</span></span>|  
  
 <span data-ttu-id="86146-359">`TaskType`свойство задается с помощью значений из `MQType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-359">`TaskType` property-Set by using values from the `MQType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-360">Понятное имя в перечислении MQType</span><span class="sxs-lookup"><span data-stu-id="86146-360">Friendly name in MQType</span></span>|<span data-ttu-id="86146-361">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-361">Numeric value</span></span>|  
|-----------------------------|-------------------|  
|<span data-ttu-id="86146-362">DTSMQType_Sender</span><span class="sxs-lookup"><span data-stu-id="86146-362">DTSMQType_Sender</span></span>|<span data-ttu-id="86146-363">0</span><span class="sxs-lookup"><span data-stu-id="86146-363">0</span></span>|  
|<span data-ttu-id="86146-364">DTSMQType_Receiver</span><span class="sxs-lookup"><span data-stu-id="86146-364">DTSMQType_Receiver</span></span>|<span data-ttu-id="86146-365">1</span><span class="sxs-lookup"><span data-stu-id="86146-365">1</span></span>|  
  
### <a name="send-mail-task"></a><span data-ttu-id="86146-366">Задача «Отправка почты»</span><span class="sxs-lookup"><span data-stu-id="86146-366">Send Mail Task</span></span>  
 <span data-ttu-id="86146-367">`MessageSourceType`свойство задается с помощью значений из `SendMailMessageSourceType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-367">`MessageSourceType` property-Set by using values from the `SendMailMessageSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-368">Понятное имя в перечислении SendMailMessageSourceType</span><span class="sxs-lookup"><span data-stu-id="86146-368">Friendly Name in SendMailMessageSourceType</span></span>|<span data-ttu-id="86146-369">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-369">Numeric Value</span></span>|  
|------------------------------------------------|-------------------|  
|<span data-ttu-id="86146-370">DirectInput</span><span class="sxs-lookup"><span data-stu-id="86146-370">DirectInput</span></span>|<span data-ttu-id="86146-371">0</span><span class="sxs-lookup"><span data-stu-id="86146-371">0</span></span>|  
|<span data-ttu-id="86146-372">FileConnection</span><span class="sxs-lookup"><span data-stu-id="86146-372">FileConnection</span></span>|<span data-ttu-id="86146-373">1</span><span class="sxs-lookup"><span data-stu-id="86146-373">1</span></span>|  
|<span data-ttu-id="86146-374">Переменная</span><span class="sxs-lookup"><span data-stu-id="86146-374">Variable</span></span>|<span data-ttu-id="86146-375">2</span><span class="sxs-lookup"><span data-stu-id="86146-375">2</span></span>|  
  
 <span data-ttu-id="86146-376">`Priority`свойство задается с помощью значений из `MailPriority` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-376">`Priority` property-Set by using values from the `MailPriority` enumeration.</span></span>  
  
|<span data-ttu-id="86146-377">Понятное имя в перечислении MailPriority</span><span class="sxs-lookup"><span data-stu-id="86146-377">Friendly Name in MailPriority</span></span>|<span data-ttu-id="86146-378">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-378">Numeric Value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="86146-379">Высокий</span><span class="sxs-lookup"><span data-stu-id="86146-379">High</span></span>|<span data-ttu-id="86146-380">1</span><span class="sxs-lookup"><span data-stu-id="86146-380">1</span></span>|  
|<span data-ttu-id="86146-381">Нормальный</span><span class="sxs-lookup"><span data-stu-id="86146-381">Normal</span></span>|<span data-ttu-id="86146-382">3</span><span class="sxs-lookup"><span data-stu-id="86146-382">3</span></span>|  
|<span data-ttu-id="86146-383">Низкий</span><span class="sxs-lookup"><span data-stu-id="86146-383">Low</span></span>|<span data-ttu-id="86146-384">5</span><span class="sxs-lookup"><span data-stu-id="86146-384">5</span></span>|  
  
### <a name="transfer-database-task"></a><span data-ttu-id="86146-385">Задача «Передача базы данных»</span><span class="sxs-lookup"><span data-stu-id="86146-385">Transfer Database Task</span></span>  
 <span data-ttu-id="86146-386">`Action`свойство задается с помощью значений из `TransferAction` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-386">`Action` property-Set by using values from the `TransferAction` enumeration.</span></span>  
  
|<span data-ttu-id="86146-387">Понятное имя в перечислении TransferAction</span><span class="sxs-lookup"><span data-stu-id="86146-387">Friendly name in TransferAction</span></span>|<span data-ttu-id="86146-388">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-388">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="86146-389">Копировать</span><span class="sxs-lookup"><span data-stu-id="86146-389">Copy</span></span>|<span data-ttu-id="86146-390">0</span><span class="sxs-lookup"><span data-stu-id="86146-390">0</span></span>|  
|<span data-ttu-id="86146-391">Переместить</span><span class="sxs-lookup"><span data-stu-id="86146-391">Move</span></span>|<span data-ttu-id="86146-392">1</span><span class="sxs-lookup"><span data-stu-id="86146-392">1</span></span>|  
  
 <span data-ttu-id="86146-393">`Method`свойство задается с помощью значений из `TransferMethod` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-393">`Method` property-Set by using values from the `TransferMethod` enumeration.</span></span>  
  
|<span data-ttu-id="86146-394">Понятное имя в перечислении TransferMethod</span><span class="sxs-lookup"><span data-stu-id="86146-394">Friendly name in TransferMethod</span></span>|<span data-ttu-id="86146-395">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-395">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="86146-396">DatabaseOffline</span><span class="sxs-lookup"><span data-stu-id="86146-396">DatabaseOffline</span></span>|<span data-ttu-id="86146-397">0</span><span class="sxs-lookup"><span data-stu-id="86146-397">0</span></span>|  
|<span data-ttu-id="86146-398">DatabaseOnline</span><span class="sxs-lookup"><span data-stu-id="86146-398">DatabaseOnline</span></span>|<span data-ttu-id="86146-399">1</span><span class="sxs-lookup"><span data-stu-id="86146-399">1</span></span>|  
  
### <a name="transfer-error-messages-task"></a><span data-ttu-id="86146-400">Задача «Передача сообщений об ошибках»</span><span class="sxs-lookup"><span data-stu-id="86146-400">Transfer Error Messages Task</span></span>  
 <span data-ttu-id="86146-401">`IfObjectExists`свойство задается с помощью значений из `IfObjectExists` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-401">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="86146-402">Понятное имя в перечислении IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="86146-402">Friendly Name in IfObjectExists</span></span>|<span data-ttu-id="86146-403">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-403">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="86146-404">FailTask</span><span class="sxs-lookup"><span data-stu-id="86146-404">FailTask</span></span>|<span data-ttu-id="86146-405">0</span><span class="sxs-lookup"><span data-stu-id="86146-405">0</span></span>|  
|<span data-ttu-id="86146-406">Overwrite</span><span class="sxs-lookup"><span data-stu-id="86146-406">Overwrite</span></span>|<span data-ttu-id="86146-407">1</span><span class="sxs-lookup"><span data-stu-id="86146-407">1</span></span>|  
|<span data-ttu-id="86146-408">Skip</span><span class="sxs-lookup"><span data-stu-id="86146-408">Skip</span></span>|<span data-ttu-id="86146-409">2</span><span class="sxs-lookup"><span data-stu-id="86146-409">2</span></span>|  
  
### <a name="transfer-jobs-task"></a><span data-ttu-id="86146-410">Задача «Передача заданий»</span><span class="sxs-lookup"><span data-stu-id="86146-410">Transfer Jobs Task</span></span>  
 <span data-ttu-id="86146-411">`IfObjectExists`свойство задается с помощью значений из `IfObjectExists` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-411">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="86146-412">Понятное имя в перечислении IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="86146-412">Friendly Name in IfObjectExists</span></span>|<span data-ttu-id="86146-413">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-413">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="86146-414">FailTask</span><span class="sxs-lookup"><span data-stu-id="86146-414">FailTask</span></span>|<span data-ttu-id="86146-415">0</span><span class="sxs-lookup"><span data-stu-id="86146-415">0</span></span>|  
|<span data-ttu-id="86146-416">Overwrite</span><span class="sxs-lookup"><span data-stu-id="86146-416">Overwrite</span></span>|<span data-ttu-id="86146-417">1</span><span class="sxs-lookup"><span data-stu-id="86146-417">1</span></span>|  
|<span data-ttu-id="86146-418">Skip</span><span class="sxs-lookup"><span data-stu-id="86146-418">Skip</span></span>|<span data-ttu-id="86146-419">2</span><span class="sxs-lookup"><span data-stu-id="86146-419">2</span></span>|  
  
### <a name="transfer-logins-task"></a><span data-ttu-id="86146-420">Задача «Передача имен входа»</span><span class="sxs-lookup"><span data-stu-id="86146-420">Transfer Logins Task</span></span>  
 <span data-ttu-id="86146-421">`IfObjectExists`свойство задается с помощью значений из `IfObjectExists` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-421">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="86146-422">Понятное имя в перечислении IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="86146-422">Friendly name in IfObjectExists</span></span>|<span data-ttu-id="86146-423">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-423">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="86146-424">FailTask</span><span class="sxs-lookup"><span data-stu-id="86146-424">FailTask</span></span>|<span data-ttu-id="86146-425">0</span><span class="sxs-lookup"><span data-stu-id="86146-425">0</span></span>|  
|<span data-ttu-id="86146-426">Overwrite</span><span class="sxs-lookup"><span data-stu-id="86146-426">Overwrite</span></span>|<span data-ttu-id="86146-427">1</span><span class="sxs-lookup"><span data-stu-id="86146-427">1</span></span>|  
|<span data-ttu-id="86146-428">Skip</span><span class="sxs-lookup"><span data-stu-id="86146-428">Skip</span></span>|<span data-ttu-id="86146-429">2</span><span class="sxs-lookup"><span data-stu-id="86146-429">2</span></span>|  
  
 <span data-ttu-id="86146-430">`LoginsToTransfer`свойство задается с помощью значений из `LoginsToTransfer` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-430">`LoginsToTransfer` property-Set by using values from the `LoginsToTransfer` enumeration.</span></span>  
  
|<span data-ttu-id="86146-431">Понятное имя в перечислении LoginsToTransfer</span><span class="sxs-lookup"><span data-stu-id="86146-431">Friendly name in LoginsToTransfer</span></span>|<span data-ttu-id="86146-432">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-432">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="86146-433">AllLogins</span><span class="sxs-lookup"><span data-stu-id="86146-433">AllLogins</span></span>|<span data-ttu-id="86146-434">0</span><span class="sxs-lookup"><span data-stu-id="86146-434">0</span></span>|  
|<span data-ttu-id="86146-435">SelectedLogins</span><span class="sxs-lookup"><span data-stu-id="86146-435">SelectedLogins</span></span>|<span data-ttu-id="86146-436">1</span><span class="sxs-lookup"><span data-stu-id="86146-436">1</span></span>|  
|<span data-ttu-id="86146-437">AllLoginsFromSelectedDatabases</span><span class="sxs-lookup"><span data-stu-id="86146-437">AllLoginsFromSelectedDatabases</span></span>|<span data-ttu-id="86146-438">2</span><span class="sxs-lookup"><span data-stu-id="86146-438">2</span></span>|  
  
### <a name="transfer-master-stored-procedures-task"></a><span data-ttu-id="86146-439">Задача «Передача главных хранимых процедур»</span><span class="sxs-lookup"><span data-stu-id="86146-439">Transfer Master Stored Procedures Task</span></span>  
 <span data-ttu-id="86146-440">`IfObjectExists`свойство задается с помощью значений из `IfObjectExists` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-440">`IfObjectExists` property-Set by using values from the `IfObjectExists` enumeration.</span></span>  
  
|<span data-ttu-id="86146-441">Понятное имя в перечислении IfObjectExists</span><span class="sxs-lookup"><span data-stu-id="86146-441">Friendly name in IfObjectExists</span></span>|<span data-ttu-id="86146-442">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-442">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="86146-443">FailTask</span><span class="sxs-lookup"><span data-stu-id="86146-443">FailTask</span></span>|<span data-ttu-id="86146-444">0</span><span class="sxs-lookup"><span data-stu-id="86146-444">0</span></span>|  
|<span data-ttu-id="86146-445">Overwrite</span><span class="sxs-lookup"><span data-stu-id="86146-445">Overwrite</span></span>|<span data-ttu-id="86146-446">1</span><span class="sxs-lookup"><span data-stu-id="86146-446">1</span></span>|  
|<span data-ttu-id="86146-447">Skip</span><span class="sxs-lookup"><span data-stu-id="86146-447">Skip</span></span>|<span data-ttu-id="86146-448">2</span><span class="sxs-lookup"><span data-stu-id="86146-448">2</span></span>|  
  
### <a name="transfer-sql-server-objects-task"></a><span data-ttu-id="86146-449">Задача «Передача объектов SQL Server»</span><span class="sxs-lookup"><span data-stu-id="86146-449">Transfer SQL Server Objects Task</span></span>  
 <span data-ttu-id="86146-450">`ExistingData`свойство задается с помощью значений из `ExistingData` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-450">`ExistingData` property-Set by using values from the `ExistingData` enumeration.</span></span>  
  
|<span data-ttu-id="86146-451">Понятное имя в перечислении ExistingData</span><span class="sxs-lookup"><span data-stu-id="86146-451">Friendly name in ExistingData</span></span>|<span data-ttu-id="86146-452">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-452">Numeric Value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="86146-453">Заменить</span><span class="sxs-lookup"><span data-stu-id="86146-453">Replace</span></span>|<span data-ttu-id="86146-454">0</span><span class="sxs-lookup"><span data-stu-id="86146-454">0</span></span>|  
|<span data-ttu-id="86146-455">Append</span><span class="sxs-lookup"><span data-stu-id="86146-455">Append</span></span>|<span data-ttu-id="86146-456">1</span><span class="sxs-lookup"><span data-stu-id="86146-456">1</span></span>|  
  
### <a name="web-service-task"></a><span data-ttu-id="86146-457">Задача «Веб-служба»</span><span class="sxs-lookup"><span data-stu-id="86146-457">Web Service Task</span></span>  
 <span data-ttu-id="86146-458">`OutputType`свойство задается с помощью значений из `DTSOutputType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-458">`OutputType` property-Set by using values from the `DTSOutputType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-459">Понятное имя в перечислении DTSOutputType</span><span class="sxs-lookup"><span data-stu-id="86146-459">Friendly name in DTSOutputType</span></span>|<span data-ttu-id="86146-460">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-460">Numeric value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="86146-461">Файл</span><span class="sxs-lookup"><span data-stu-id="86146-461">File</span></span>|<span data-ttu-id="86146-462">0</span><span class="sxs-lookup"><span data-stu-id="86146-462">0</span></span>|  
|<span data-ttu-id="86146-463">Переменная</span><span class="sxs-lookup"><span data-stu-id="86146-463">Variable</span></span>|<span data-ttu-id="86146-464">1</span><span class="sxs-lookup"><span data-stu-id="86146-464">1</span></span>|  
  
### <a name="wmi-data-reader-task"></a><span data-ttu-id="86146-465">Задача «Модуль чтения данных WMI»</span><span class="sxs-lookup"><span data-stu-id="86146-465">WMI Data Reader Task</span></span>  
 <span data-ttu-id="86146-466">`OverwriteDestination`свойство задается с помощью значений из `OverwriteDestination` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-466">`OverwriteDestination` property-Set by using values from the `OverwriteDestination` enumeration.</span></span>  
  
|<span data-ttu-id="86146-467">Понятное имя в перечислении OverwriteDestination</span><span class="sxs-lookup"><span data-stu-id="86146-467">Friendly name in OverwriteDestination</span></span>|<span data-ttu-id="86146-468">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-468">Numeric value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="86146-469">OverwriteDestination</span><span class="sxs-lookup"><span data-stu-id="86146-469">OverwriteDestination</span></span>|<span data-ttu-id="86146-470">0</span><span class="sxs-lookup"><span data-stu-id="86146-470">0</span></span>|  
|<span data-ttu-id="86146-471">AppendToDestination</span><span class="sxs-lookup"><span data-stu-id="86146-471">AppendToDestination</span></span>|<span data-ttu-id="86146-472">1</span><span class="sxs-lookup"><span data-stu-id="86146-472">1</span></span>|  
|<span data-ttu-id="86146-473">KeepOriginal</span><span class="sxs-lookup"><span data-stu-id="86146-473">KeepOriginal</span></span>|<span data-ttu-id="86146-474">2</span><span class="sxs-lookup"><span data-stu-id="86146-474">2</span></span>|  
  
 <span data-ttu-id="86146-475">`OutputType`свойство задается с помощью значений из `OutputType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-475">`OutputType` property-Set by using values from the `OutputType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-476">Понятное имя в перечислении OutputType</span><span class="sxs-lookup"><span data-stu-id="86146-476">Friendly name in OutputType</span></span>|<span data-ttu-id="86146-477">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-477">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="86146-478">DataTable</span><span class="sxs-lookup"><span data-stu-id="86146-478">DataTable</span></span>|<span data-ttu-id="86146-479">0</span><span class="sxs-lookup"><span data-stu-id="86146-479">0</span></span>|  
|<span data-ttu-id="86146-480">PropertyValue</span><span class="sxs-lookup"><span data-stu-id="86146-480">PropertyValue</span></span>|<span data-ttu-id="86146-481">1</span><span class="sxs-lookup"><span data-stu-id="86146-481">1</span></span>|  
|<span data-ttu-id="86146-482">PropertyNameAndValue</span><span class="sxs-lookup"><span data-stu-id="86146-482">PropertyNameAndValue</span></span>|<span data-ttu-id="86146-483">2</span><span class="sxs-lookup"><span data-stu-id="86146-483">2</span></span>|  
  
 <span data-ttu-id="86146-484">`DestinationType`свойство задается с помощью значений из `DestinationType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-484">`DestinationType` property-Set by using values from the `DestinationType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-485">Понятное имя в перечислении DestinationType</span><span class="sxs-lookup"><span data-stu-id="86146-485">Friendly name in DestinationType</span></span>|<span data-ttu-id="86146-486">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-486">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="86146-487">FileConnection</span><span class="sxs-lookup"><span data-stu-id="86146-487">FileConnection</span></span>|<span data-ttu-id="86146-488">0</span><span class="sxs-lookup"><span data-stu-id="86146-488">0</span></span>|  
|<span data-ttu-id="86146-489">Переменная</span><span class="sxs-lookup"><span data-stu-id="86146-489">Variable</span></span>|<span data-ttu-id="86146-490">1</span><span class="sxs-lookup"><span data-stu-id="86146-490">1</span></span>|  
  
 <span data-ttu-id="86146-491">`WqlQuerySourceType`свойство задается с помощью значений из `QuerySourceType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-491">`WqlQuerySourceType` property-Set by using values from the `QuerySourceType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-492">Понятное имя в перечислении QuerySourceType</span><span class="sxs-lookup"><span data-stu-id="86146-492">Friendly Name in QuerySourceType</span></span>|<span data-ttu-id="86146-493">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-493">Numeric Value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="86146-494">FileConnection</span><span class="sxs-lookup"><span data-stu-id="86146-494">FileConnection</span></span>|<span data-ttu-id="86146-495">0</span><span class="sxs-lookup"><span data-stu-id="86146-495">0</span></span>|  
|<span data-ttu-id="86146-496">DirectInput</span><span class="sxs-lookup"><span data-stu-id="86146-496">DirectInput</span></span>|<span data-ttu-id="86146-497">1</span><span class="sxs-lookup"><span data-stu-id="86146-497">1</span></span>|  
|<span data-ttu-id="86146-498">Переменная</span><span class="sxs-lookup"><span data-stu-id="86146-498">Variable</span></span>|<span data-ttu-id="86146-499">2</span><span class="sxs-lookup"><span data-stu-id="86146-499">2</span></span>|  
  
 <span data-ttu-id="86146-500">Свойство "наблюдатель событий WMI" `ActionAtEvent` задается с помощью значений из `ActionAtEvent` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-500">WMI Event Watcher `ActionAtEvent` property-Set by using values from the `ActionAtEvent` enumeration.</span></span>  
  
|<span data-ttu-id="86146-501">Понятное имя в перечислении ActionAtEvent</span><span class="sxs-lookup"><span data-stu-id="86146-501">Friendly Name in ActionAtEvent</span></span>|<span data-ttu-id="86146-502">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-502">Numeric Value</span></span>|  
|------------------------------------|-------------------|  
|<span data-ttu-id="86146-503">LogTheEventAndFireDTSEvent</span><span class="sxs-lookup"><span data-stu-id="86146-503">LogTheEventAndFireDTSEvent</span></span>|<span data-ttu-id="86146-504">0</span><span class="sxs-lookup"><span data-stu-id="86146-504">0</span></span>|  
|<span data-ttu-id="86146-505">LogTheEvent</span><span class="sxs-lookup"><span data-stu-id="86146-505">LogTheEvent</span></span>|<span data-ttu-id="86146-506">1</span><span class="sxs-lookup"><span data-stu-id="86146-506">1</span></span>|  
  
 <span data-ttu-id="86146-507">`ActionAtTimeout`свойство задается с помощью значений из `ActionAtTimeout` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-507">`ActionAtTimeout` property-Set by using values from the `ActionAtTimeout` enumeration.</span></span>  
  
|<span data-ttu-id="86146-508">Понятное имя в перечислении ActionAtTimeout</span><span class="sxs-lookup"><span data-stu-id="86146-508">Friendly name in ActionAtTimeout</span></span>|<span data-ttu-id="86146-509">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-509">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="86146-510">LogTimeoutAndFireDTSEvent</span><span class="sxs-lookup"><span data-stu-id="86146-510">LogTimeoutAndFireDTSEvent</span></span>|<span data-ttu-id="86146-511">0</span><span class="sxs-lookup"><span data-stu-id="86146-511">0</span></span>|  
|<span data-ttu-id="86146-512">LogTimeout</span><span class="sxs-lookup"><span data-stu-id="86146-512">LogTimeout</span></span>|<span data-ttu-id="86146-513">1</span><span class="sxs-lookup"><span data-stu-id="86146-513">1</span></span>|  
  
 <span data-ttu-id="86146-514">`AfterEvent`свойство задается с помощью значений из `AfterEvent` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-514">`AfterEvent` property-Set by using values from the `AfterEvent` enumeration.</span></span>  
  
|<span data-ttu-id="86146-515">Понятное имя в перечислении AfterEvent</span><span class="sxs-lookup"><span data-stu-id="86146-515">Friendly name in AfterEvent</span></span>|<span data-ttu-id="86146-516">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-516">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="86146-517">ReturnWithSuccess</span><span class="sxs-lookup"><span data-stu-id="86146-517">ReturnWithSuccess</span></span>|<span data-ttu-id="86146-518">0</span><span class="sxs-lookup"><span data-stu-id="86146-518">0</span></span>|  
|<span data-ttu-id="86146-519">ReturnWithFailure</span><span class="sxs-lookup"><span data-stu-id="86146-519">ReturnWithFailure</span></span>|<span data-ttu-id="86146-520">1</span><span class="sxs-lookup"><span data-stu-id="86146-520">1</span></span>|  
|<span data-ttu-id="86146-521">WatchfortheEventAgain</span><span class="sxs-lookup"><span data-stu-id="86146-521">WatchfortheEventAgain</span></span>|<span data-ttu-id="86146-522">2</span><span class="sxs-lookup"><span data-stu-id="86146-522">2</span></span>|  
  
 <span data-ttu-id="86146-523">`AfterTimeout`свойство задается с помощью значений из `AfterTimeout` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-523">`AfterTimeout` property-Set by using values from the `AfterTimeout` enumeration.</span></span>  
  
|<span data-ttu-id="86146-524">Понятное имя в перечислении AfterTimeout</span><span class="sxs-lookup"><span data-stu-id="86146-524">Friendly name in AfterTimeout</span></span>|<span data-ttu-id="86146-525">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-525">Numeric value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="86146-526">ReturnWithSuccess</span><span class="sxs-lookup"><span data-stu-id="86146-526">ReturnWithSuccess</span></span>|<span data-ttu-id="86146-527">0</span><span class="sxs-lookup"><span data-stu-id="86146-527">0</span></span>|  
|<span data-ttu-id="86146-528">ReturnWithFailure</span><span class="sxs-lookup"><span data-stu-id="86146-528">ReturnWithFailure</span></span>|<span data-ttu-id="86146-529">1</span><span class="sxs-lookup"><span data-stu-id="86146-529">1</span></span>|  
|<span data-ttu-id="86146-530">WatchfortheEventAgain</span><span class="sxs-lookup"><span data-stu-id="86146-530">WatchfortheEventAgain</span></span>|<span data-ttu-id="86146-531">2</span><span class="sxs-lookup"><span data-stu-id="86146-531">2</span></span>|  
  
 <span data-ttu-id="86146-532">`WqlQuerySourceType`свойство задается с помощью значений из `QuerySourceType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-532">`WqlQuerySourceType` property-Set by using values from the `QuerySourceType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-533">Понятное имя в перечислении QuerySourceType</span><span class="sxs-lookup"><span data-stu-id="86146-533">Friendly name in QuerySourceType</span></span>|<span data-ttu-id="86146-534">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-534">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="86146-535">FileConnection</span><span class="sxs-lookup"><span data-stu-id="86146-535">FileConnection</span></span>|<span data-ttu-id="86146-536">0</span><span class="sxs-lookup"><span data-stu-id="86146-536">0</span></span>|  
|<span data-ttu-id="86146-537">DirectInput</span><span class="sxs-lookup"><span data-stu-id="86146-537">DirectInput</span></span>|<span data-ttu-id="86146-538">1</span><span class="sxs-lookup"><span data-stu-id="86146-538">1</span></span>|  
|<span data-ttu-id="86146-539">Переменная</span><span class="sxs-lookup"><span data-stu-id="86146-539">Variable</span></span>|<span data-ttu-id="86146-540">2</span><span class="sxs-lookup"><span data-stu-id="86146-540">2</span></span>|  
  
### <a name="xml-task"></a><span data-ttu-id="86146-541">Задача «XML»</span><span class="sxs-lookup"><span data-stu-id="86146-541">XML Task</span></span>  
 <span data-ttu-id="86146-542">`OperationType`свойство задается с помощью значений из `DTSXMLOperation` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-542">`OperationType` property-Set by using values from the `DTSXMLOperation` enumeration.</span></span>  
  
|<span data-ttu-id="86146-543">Понятное имя в перечислении DTSXMLOperation</span><span class="sxs-lookup"><span data-stu-id="86146-543">Friendly name in DTSXMLOperation</span></span>|<span data-ttu-id="86146-544">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-544">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="86146-545">Проверить</span><span class="sxs-lookup"><span data-stu-id="86146-545">Validate</span></span>|<span data-ttu-id="86146-546">0</span><span class="sxs-lookup"><span data-stu-id="86146-546">0</span></span>|  
|<span data-ttu-id="86146-547">XSLT</span><span class="sxs-lookup"><span data-stu-id="86146-547">XSLT</span></span>|<span data-ttu-id="86146-548">1</span><span class="sxs-lookup"><span data-stu-id="86146-548">1</span></span>|  
|<span data-ttu-id="86146-549">XPATH</span><span class="sxs-lookup"><span data-stu-id="86146-549">XPATH</span></span>|<span data-ttu-id="86146-550">2</span><span class="sxs-lookup"><span data-stu-id="86146-550">2</span></span>|  
|<span data-ttu-id="86146-551">Объединить</span><span class="sxs-lookup"><span data-stu-id="86146-551">Merge</span></span>|<span data-ttu-id="86146-552">3</span><span class="sxs-lookup"><span data-stu-id="86146-552">3</span></span>|  
|<span data-ttu-id="86146-553">Поиск различий</span><span class="sxs-lookup"><span data-stu-id="86146-553">Diff</span></span>|<span data-ttu-id="86146-554">4</span><span class="sxs-lookup"><span data-stu-id="86146-554">4</span></span>|  
|<span data-ttu-id="86146-555">Обновление</span><span class="sxs-lookup"><span data-stu-id="86146-555">Patch</span></span>|<span data-ttu-id="86146-556">5</span><span class="sxs-lookup"><span data-stu-id="86146-556">5</span></span>|  
  
 <span data-ttu-id="86146-557">`SourceType``SecondOperandType`свойства, и `XPathSourceType` задаются с помощью значений из `DTSXMLSourceType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-557">`SourceType`, `SecondOperandType`, and `XPathSourceType` properties-Set by using values from the `DTSXMLSourceType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-558">Понятное имя в перечислении DTSXMLSourceType</span><span class="sxs-lookup"><span data-stu-id="86146-558">Friendly name in DTSXMLSourceType</span></span>|<span data-ttu-id="86146-559">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-559">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="86146-560">FileConnection</span><span class="sxs-lookup"><span data-stu-id="86146-560">FileConnection</span></span>|<span data-ttu-id="86146-561">0</span><span class="sxs-lookup"><span data-stu-id="86146-561">0</span></span>|  
|<span data-ttu-id="86146-562">Переменная</span><span class="sxs-lookup"><span data-stu-id="86146-562">Variable</span></span>|<span data-ttu-id="86146-563">1</span><span class="sxs-lookup"><span data-stu-id="86146-563">1</span></span>|  
|<span data-ttu-id="86146-564">DirectInput</span><span class="sxs-lookup"><span data-stu-id="86146-564">DirectInput</span></span>|<span data-ttu-id="86146-565">2</span><span class="sxs-lookup"><span data-stu-id="86146-565">2</span></span>|  
  
 <span data-ttu-id="86146-566">`DestinationType`свойства и **диффграмдестинатионтипе** задаются с помощью значений из `DTSXMLSaveResultTo` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-566">`DestinationType` and **DiffGramDestinationType** properties-Set by using values from the `DTSXMLSaveResultTo` enumeration.</span></span>  
  
|<span data-ttu-id="86146-567">Понятное имя в перечислении DTSXMLSaveResultTo</span><span class="sxs-lookup"><span data-stu-id="86146-567">Friendly name in DTSXMLSaveResultTo</span></span>|<span data-ttu-id="86146-568">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-568">Numeric value</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="86146-569">FileConnection</span><span class="sxs-lookup"><span data-stu-id="86146-569">FileConnection</span></span>|<span data-ttu-id="86146-570">0</span><span class="sxs-lookup"><span data-stu-id="86146-570">0</span></span>|  
|<span data-ttu-id="86146-571">Переменная</span><span class="sxs-lookup"><span data-stu-id="86146-571">Variable</span></span>|<span data-ttu-id="86146-572">1</span><span class="sxs-lookup"><span data-stu-id="86146-572">1</span></span>|  
  
 <span data-ttu-id="86146-573">`ValidationType`свойство задается с помощью значений из `DTSXMLValidationType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-573">`ValidationType` property-Set by using values from the `DTSXMLValidationType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-574">Понятное имя в перечислении DTSXMLValidationType</span><span class="sxs-lookup"><span data-stu-id="86146-574">Friendly name in DTSXMLValidationType</span></span>|<span data-ttu-id="86146-575">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-575">Numeric value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="86146-576">DTD</span><span class="sxs-lookup"><span data-stu-id="86146-576">DTD</span></span>|<span data-ttu-id="86146-577">0</span><span class="sxs-lookup"><span data-stu-id="86146-577">0</span></span>|  
|<span data-ttu-id="86146-578">XSD</span><span class="sxs-lookup"><span data-stu-id="86146-578">XSD</span></span>|<span data-ttu-id="86146-579">1</span><span class="sxs-lookup"><span data-stu-id="86146-579">1</span></span>|  
  
 <span data-ttu-id="86146-580">`XPathOperation`свойство задается с помощью значений из `DTSXMLXPathOperation` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-580">`XPathOperation` property-Set by using values from the `DTSXMLXPathOperation` enumeration.</span></span>  
  
|<span data-ttu-id="86146-581">Понятное имя в перечислении DTSXMLXPathOperation</span><span class="sxs-lookup"><span data-stu-id="86146-581">Friendly name in DTSXMLXPathOperation</span></span>|<span data-ttu-id="86146-582">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-582">Numeric Value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="86146-583">Ознакомительная версия</span><span class="sxs-lookup"><span data-stu-id="86146-583">Evaluation</span></span>|<span data-ttu-id="86146-584">0</span><span class="sxs-lookup"><span data-stu-id="86146-584">0</span></span>|  
|<span data-ttu-id="86146-585">Значения</span><span class="sxs-lookup"><span data-stu-id="86146-585">Values</span></span>|<span data-ttu-id="86146-586">1</span><span class="sxs-lookup"><span data-stu-id="86146-586">1</span></span>|  
|<span data-ttu-id="86146-587">NodeList</span><span class="sxs-lookup"><span data-stu-id="86146-587">NodeList</span></span>|<span data-ttu-id="86146-588">2</span><span class="sxs-lookup"><span data-stu-id="86146-588">2</span></span>|  
  
 <span data-ttu-id="86146-589">`DiffOptions`свойство задается с помощью значений из `DTSXMLDiffOptions` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-589">`DiffOptions` property-Set by using values from the `DTSXMLDiffOptions` enumeration.</span></span> <span data-ttu-id="86146-590">Параметры в этом перечислителе взаимно не исключаемы.</span><span class="sxs-lookup"><span data-stu-id="86146-590">The options in this enumerator are not mutually exclusive.</span></span> <span data-ttu-id="86146-591">Чтобы использовать несколько параметров, предоставьте список параметров с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="86146-591">To use multiple options, provide a comma-separated list of the options to apply.</span></span>  
  
|<span data-ttu-id="86146-592">Понятное имя в перечислении DTSXMLDiffOptions</span><span class="sxs-lookup"><span data-stu-id="86146-592">Friendly name in DTSXMLDiffOptions</span></span>|<span data-ttu-id="86146-593">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-593">Numeric Value</span></span>|  
|----------------------------------------|-------------------|  
|<span data-ttu-id="86146-594">None</span><span class="sxs-lookup"><span data-stu-id="86146-594">None</span></span>|<span data-ttu-id="86146-595">0</span><span class="sxs-lookup"><span data-stu-id="86146-595">0</span></span>|  
|<span data-ttu-id="86146-596">IgnoreChildOrder</span><span class="sxs-lookup"><span data-stu-id="86146-596">IgnoreChildOrder</span></span>|<span data-ttu-id="86146-597">1</span><span class="sxs-lookup"><span data-stu-id="86146-597">1</span></span>|  
|<span data-ttu-id="86146-598">IgnoreComments</span><span class="sxs-lookup"><span data-stu-id="86146-598">IgnoreComments</span></span>|<span data-ttu-id="86146-599">2</span><span class="sxs-lookup"><span data-stu-id="86146-599">2</span></span>|  
|<span data-ttu-id="86146-600">IgnorePI</span><span class="sxs-lookup"><span data-stu-id="86146-600">IgnorePI</span></span>|<span data-ttu-id="86146-601">4</span><span class="sxs-lookup"><span data-stu-id="86146-601">4</span></span>|  
|<span data-ttu-id="86146-602">IgnoreWhitespace</span><span class="sxs-lookup"><span data-stu-id="86146-602">IgnoreWhitespace</span></span>|<span data-ttu-id="86146-603">8</span><span class="sxs-lookup"><span data-stu-id="86146-603">8</span></span>|  
|<span data-ttu-id="86146-604">IgnoreNamespaces</span><span class="sxs-lookup"><span data-stu-id="86146-604">IgnoreNamespaces</span></span>|<span data-ttu-id="86146-605">16</span><span class="sxs-lookup"><span data-stu-id="86146-605">16</span></span>|  
|<span data-ttu-id="86146-606">IgnorePrefixes</span><span class="sxs-lookup"><span data-stu-id="86146-606">IgnorePrefixes</span></span>|<span data-ttu-id="86146-607">32</span><span class="sxs-lookup"><span data-stu-id="86146-607">32</span></span>|  
|<span data-ttu-id="86146-608">IgnoreXmlDecl</span><span class="sxs-lookup"><span data-stu-id="86146-608">IgnoreXmlDecl</span></span>|<span data-ttu-id="86146-609">64</span><span class="sxs-lookup"><span data-stu-id="86146-609">64</span></span>|  
|<span data-ttu-id="86146-610">IgnoreDtd</span><span class="sxs-lookup"><span data-stu-id="86146-610">IgnoreDtd</span></span>|<span data-ttu-id="86146-611">128</span><span class="sxs-lookup"><span data-stu-id="86146-611">128</span></span>|  
  
 <span data-ttu-id="86146-612">`DiffAlgorithm`свойство задается с помощью значений из `DTSXMLDiffAlgorithm` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-612">`DiffAlgorithm` property-Set by using values from the `DTSXMLDiffAlgorithm` enumeration.</span></span>  
  
|<span data-ttu-id="86146-613">Понятное имя в перечислении DTSXMLDiffAlgorithm</span><span class="sxs-lookup"><span data-stu-id="86146-613">Friendly name in DTSXMLDiffAlgorithm</span></span>|<span data-ttu-id="86146-614">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-614">Numeric value</span></span>|  
|------------------------------------------|-------------------|  
|<span data-ttu-id="86146-615">Auto</span><span class="sxs-lookup"><span data-stu-id="86146-615">Auto</span></span>|<span data-ttu-id="86146-616">0</span><span class="sxs-lookup"><span data-stu-id="86146-616">0</span></span>|  
|<span data-ttu-id="86146-617">быстрый;</span><span class="sxs-lookup"><span data-stu-id="86146-617">Fast</span></span>|<span data-ttu-id="86146-618">1</span><span class="sxs-lookup"><span data-stu-id="86146-618">1</span></span>|  
|<span data-ttu-id="86146-619">Точный</span><span class="sxs-lookup"><span data-stu-id="86146-619">Precise</span></span>|<span data-ttu-id="86146-620">2</span><span class="sxs-lookup"><span data-stu-id="86146-620">2</span></span>|  
  
##  <a name="maintenance-plan-tasks"></a><a name="MaintenancePlanTasks"></a> <span data-ttu-id="86146-621">Задачи плана обслуживания</span><span class="sxs-lookup"><span data-stu-id="86146-621">Maintenance Plan Tasks</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="86146-622">включают в себя набор задач, выполняющих задачи SQL Server для использования в планах обслуживания, и пакеты служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="86146-622">includes a set of tasks that perform SQL Server tasks for use in maintenance plans and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="86146-623">не поддерживают работу с этими задачами программным путем, а документация по программированию не включает в себя API-документацию для этих задач и их перечислителей.</span><span class="sxs-lookup"><span data-stu-id="86146-623">does not support working with these tasks programmatically and programming reference documentation does not include API documentation of these tasks and their enumerators.</span></span>  
  
### <a name="all-maintenance-tasks"></a><span data-ttu-id="86146-624">Все задачи плана обслуживания</span><span class="sxs-lookup"><span data-stu-id="86146-624">All Maintenance Tasks</span></span>  
 <span data-ttu-id="86146-625">Все задачи плана обслуживания для установки указанных свойств используют следующие перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-625">All maintenance tasks use the following enumerations to set the specified properties.</span></span>  
  
 <span data-ttu-id="86146-626">`DatabaseSelectionType`свойство задается с помощью значений из `DatabaseSelection` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-626">`DatabaseSelectionType` property-Set by using values from the `DatabaseSelection` enumeration.</span></span>  
  
|<span data-ttu-id="86146-627">Понятное имя в перечислении DatabaseSelection</span><span class="sxs-lookup"><span data-stu-id="86146-627">Friendly name in DatabaseSelection</span></span>|<span data-ttu-id="86146-628">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-628">Numeric value</span></span>|  
|----------------------------------------|-------------------|  
|<span data-ttu-id="86146-629">None</span><span class="sxs-lookup"><span data-stu-id="86146-629">None</span></span>|<span data-ttu-id="86146-630">0</span><span class="sxs-lookup"><span data-stu-id="86146-630">0</span></span>|  
|<span data-ttu-id="86146-631">All</span><span class="sxs-lookup"><span data-stu-id="86146-631">All</span></span>|<span data-ttu-id="86146-632">1</span><span class="sxs-lookup"><span data-stu-id="86146-632">1</span></span>|  
|<span data-ttu-id="86146-633">Система</span><span class="sxs-lookup"><span data-stu-id="86146-633">System</span></span>|<span data-ttu-id="86146-634">2</span><span class="sxs-lookup"><span data-stu-id="86146-634">2</span></span>|  
|<span data-ttu-id="86146-635">Пользователь</span><span class="sxs-lookup"><span data-stu-id="86146-635">User</span></span>|<span data-ttu-id="86146-636">3</span><span class="sxs-lookup"><span data-stu-id="86146-636">3</span></span>|  
|<span data-ttu-id="86146-637">Specific</span><span class="sxs-lookup"><span data-stu-id="86146-637">Specific</span></span>|<span data-ttu-id="86146-638">4</span><span class="sxs-lookup"><span data-stu-id="86146-638">4</span></span>|  
  
 <span data-ttu-id="86146-639">`TableSelectionType`свойство задается с помощью значений из `TableSelection` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-639">`TableSelectionType` property-Set by using values from the `TableSelection` enumeration.</span></span>  
  
|<span data-ttu-id="86146-640">Понятное имя в перечислении TableSelection</span><span class="sxs-lookup"><span data-stu-id="86146-640">Friendly name in TableSelection</span></span>|<span data-ttu-id="86146-641">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-641">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="86146-642">None</span><span class="sxs-lookup"><span data-stu-id="86146-642">None</span></span>|<span data-ttu-id="86146-643">0</span><span class="sxs-lookup"><span data-stu-id="86146-643">0</span></span>|  
|<span data-ttu-id="86146-644">All</span><span class="sxs-lookup"><span data-stu-id="86146-644">All</span></span>|<span data-ttu-id="86146-645">1</span><span class="sxs-lookup"><span data-stu-id="86146-645">1</span></span>|  
|<span data-ttu-id="86146-646">Specific</span><span class="sxs-lookup"><span data-stu-id="86146-646">Specific</span></span>|<span data-ttu-id="86146-647">2</span><span class="sxs-lookup"><span data-stu-id="86146-647">2</span></span>|  
  
 <span data-ttu-id="86146-648">`ObjectTypeSelection`свойство задается с помощью значений из `ObjectType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-648">`ObjectTypeSelection` property-Set by using values from the `ObjectType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-649">Понятное имя в перечислении ObjectType</span><span class="sxs-lookup"><span data-stu-id="86146-649">Friendly name in ObjectType</span></span>|<span data-ttu-id="86146-650">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-650">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="86146-651">Таблица</span><span class="sxs-lookup"><span data-stu-id="86146-651">Table</span></span>|<span data-ttu-id="86146-652">0</span><span class="sxs-lookup"><span data-stu-id="86146-652">0</span></span>|  
|<span data-ttu-id="86146-653">Представление</span><span class="sxs-lookup"><span data-stu-id="86146-653">View</span></span>|<span data-ttu-id="86146-654">1</span><span class="sxs-lookup"><span data-stu-id="86146-654">1</span></span>|  
|<span data-ttu-id="86146-655">TableView</span><span class="sxs-lookup"><span data-stu-id="86146-655">TableView</span></span>|<span data-ttu-id="86146-656">2</span><span class="sxs-lookup"><span data-stu-id="86146-656">2</span></span>|  
  
### <a name="back-up-database-task"></a><span data-ttu-id="86146-657">Задача «Создание резервной копии базы данных»</span><span class="sxs-lookup"><span data-stu-id="86146-657">Back Up Database Task</span></span>  
 <span data-ttu-id="86146-658">`DestinationCreationType`свойство задается с помощью значений из `DestinationType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-658">`DestinationCreationType` property-Set by using values from the `DestinationType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-659">Понятное имя в перечислении DestinationType</span><span class="sxs-lookup"><span data-stu-id="86146-659">Friendly name in DestinationType</span></span>|<span data-ttu-id="86146-660">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-660">Numeric value</span></span>|  
|--------------------------------------|-------------------|  
|<span data-ttu-id="86146-661">Auto</span><span class="sxs-lookup"><span data-stu-id="86146-661">Auto</span></span>|<span data-ttu-id="86146-662">0</span><span class="sxs-lookup"><span data-stu-id="86146-662">0</span></span>|  
|<span data-ttu-id="86146-663">Вручную</span><span class="sxs-lookup"><span data-stu-id="86146-663">Manual</span></span>|<span data-ttu-id="86146-664">1</span><span class="sxs-lookup"><span data-stu-id="86146-664">1</span></span>|  
  
 <span data-ttu-id="86146-665">`ExistingBackupsAction`свойство задается с помощью значений из `ActionForExistingBackups` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-665">`ExistingBackupsAction` property-Set by using values from the `ActionForExistingBackups` enumeration.</span></span>  
  
|<span data-ttu-id="86146-666">Понятное имя в перечислении ActionForExistingBackups</span><span class="sxs-lookup"><span data-stu-id="86146-666">Friendly name in ActionForExistingBackups</span></span>|<span data-ttu-id="86146-667">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-667">Numeric value</span></span>|  
|-----------------------------------------------|-------------------|  
|<span data-ttu-id="86146-668">Append</span><span class="sxs-lookup"><span data-stu-id="86146-668">Append</span></span>|<span data-ttu-id="86146-669">0</span><span class="sxs-lookup"><span data-stu-id="86146-669">0</span></span>|  
|<span data-ttu-id="86146-670">Overwrite</span><span class="sxs-lookup"><span data-stu-id="86146-670">Overwrite</span></span>|<span data-ttu-id="86146-671">1</span><span class="sxs-lookup"><span data-stu-id="86146-671">1</span></span>|  
  
 <span data-ttu-id="86146-672">`BackupAction`свойство задается с помощью значений из `BackupTaskType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-672">`BackupAction` property-Set by using values from the `BackupTaskType` enumeration.</span></span> <span data-ttu-id="86146-673">Это свойство работает совместно со свойством `BackupIsIncremental` для определения типа резервной копии, которую создает задача.</span><span class="sxs-lookup"><span data-stu-id="86146-673">This property works with the `BackupIsIncremental` property to define the type of backup that the task performs.</span></span>  
  
|<span data-ttu-id="86146-674">Понятное имя в перечислении BackupTaskType</span><span class="sxs-lookup"><span data-stu-id="86146-674">Friendly name in BackupTaskType</span></span>|<span data-ttu-id="86146-675">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-675">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="86146-676">База данных</span><span class="sxs-lookup"><span data-stu-id="86146-676">Database</span></span>|<span data-ttu-id="86146-677">0</span><span class="sxs-lookup"><span data-stu-id="86146-677">0</span></span>|  
|<span data-ttu-id="86146-678">Файлы</span><span class="sxs-lookup"><span data-stu-id="86146-678">Files</span></span>|<span data-ttu-id="86146-679">1</span><span class="sxs-lookup"><span data-stu-id="86146-679">1</span></span>|  
|<span data-ttu-id="86146-680">Журнал</span><span class="sxs-lookup"><span data-stu-id="86146-680">Log</span></span>|<span data-ttu-id="86146-681">2</span><span class="sxs-lookup"><span data-stu-id="86146-681">2</span></span>|  
  
 <span data-ttu-id="86146-682">`BackupDevice`свойство задается с помощью значений из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] перечисления управляющих объектов (SMO) `DeviceType` .</span><span class="sxs-lookup"><span data-stu-id="86146-682">`BackupDevice` property-Set by using values from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) `DeviceType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-683">Понятное имя в перечислении DeviceType</span><span class="sxs-lookup"><span data-stu-id="86146-683">Friendly name in DeviceType</span></span>|<span data-ttu-id="86146-684">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-684">Numeric value</span></span>|  
|---------------------------------|-------------------|  
|<span data-ttu-id="86146-685">LogicalDevice</span><span class="sxs-lookup"><span data-stu-id="86146-685">LogicalDevice</span></span>|<span data-ttu-id="86146-686">0</span><span class="sxs-lookup"><span data-stu-id="86146-686">0</span></span>|  
|<span data-ttu-id="86146-687">Лента</span><span class="sxs-lookup"><span data-stu-id="86146-687">Tape</span></span>|<span data-ttu-id="86146-688">1</span><span class="sxs-lookup"><span data-stu-id="86146-688">1</span></span>|  
|<span data-ttu-id="86146-689">Файл</span><span class="sxs-lookup"><span data-stu-id="86146-689">File</span></span>|<span data-ttu-id="86146-690">2</span><span class="sxs-lookup"><span data-stu-id="86146-690">2</span></span>|  
|<span data-ttu-id="86146-691">Pipe</span><span class="sxs-lookup"><span data-stu-id="86146-691">Pipe</span></span>|<span data-ttu-id="86146-692">3</span><span class="sxs-lookup"><span data-stu-id="86146-692">3</span></span>|  
|<span data-ttu-id="86146-693">VirtualDevice</span><span class="sxs-lookup"><span data-stu-id="86146-693">VirtualDevice</span></span>|<span data-ttu-id="86146-694">4</span><span class="sxs-lookup"><span data-stu-id="86146-694">4</span></span>|  
  
### <a name="maintenance-cleanup-task"></a><span data-ttu-id="86146-695">задача «Очистка после обслуживания»</span><span class="sxs-lookup"><span data-stu-id="86146-695">Maintenance Cleanup Task</span></span>  
 <span data-ttu-id="86146-696">`FileTypeSelected`свойство задается с помощью значений из `FileType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-696">`FileTypeSelected` property-Set by using values from the `FileType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-697">Понятное имя в перечислении FileType</span><span class="sxs-lookup"><span data-stu-id="86146-697">Friendly name in FileType</span></span>|<span data-ttu-id="86146-698">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-698">Numeric value</span></span>|  
|-------------------------------|-------------------|  
|<span data-ttu-id="86146-699">FileBackup</span><span class="sxs-lookup"><span data-stu-id="86146-699">FileBackup</span></span>|<span data-ttu-id="86146-700">0</span><span class="sxs-lookup"><span data-stu-id="86146-700">0</span></span>|  
|<span data-ttu-id="86146-701">FileReport</span><span class="sxs-lookup"><span data-stu-id="86146-701">FileReport</span></span>|<span data-ttu-id="86146-702">1</span><span class="sxs-lookup"><span data-stu-id="86146-702">1</span></span>|  
  
 <span data-ttu-id="86146-703">`OlderThanTimeUnitType`свойство задается с помощью значений из `TimeUnitType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-703">`OlderThanTimeUnitType` property-Set by using values from the `TimeUnitType` enumeration.</span></span>  
  
|<span data-ttu-id="86146-704">Понятное имя в перечислении TimeUnitType</span><span class="sxs-lookup"><span data-stu-id="86146-704">Friendly Name in TimeUnitType</span></span>|<span data-ttu-id="86146-705">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-705">Numeric Value</span></span>|  
|-----------------------------------|-------------------|  
|<span data-ttu-id="86146-706">День</span><span class="sxs-lookup"><span data-stu-id="86146-706">Day</span></span>|<span data-ttu-id="86146-707">0</span><span class="sxs-lookup"><span data-stu-id="86146-707">0</span></span>|  
|<span data-ttu-id="86146-708">Неделя</span><span class="sxs-lookup"><span data-stu-id="86146-708">Week</span></span>|<span data-ttu-id="86146-709">1</span><span class="sxs-lookup"><span data-stu-id="86146-709">1</span></span>|  
|<span data-ttu-id="86146-710">Месяц</span><span class="sxs-lookup"><span data-stu-id="86146-710">Month</span></span>|<span data-ttu-id="86146-711">2</span><span class="sxs-lookup"><span data-stu-id="86146-711">2</span></span>|  
|<span data-ttu-id="86146-712">Год</span><span class="sxs-lookup"><span data-stu-id="86146-712">Year</span></span>|<span data-ttu-id="86146-713">3</span><span class="sxs-lookup"><span data-stu-id="86146-713">3</span></span>|  
  
### <a name="update-statistics-task"></a><span data-ttu-id="86146-714">Задача «Обновление статистики»</span><span class="sxs-lookup"><span data-stu-id="86146-714">Update Statistics Task</span></span>  
 <span data-ttu-id="86146-715">`UpdateType`свойство задается с помощью значений из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] перечисления управляющих объектов (SMO) `StatisticsTarget` .</span><span class="sxs-lookup"><span data-stu-id="86146-715">`UpdateType` property-Set by using values from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) `StatisticsTarget` enumeration.</span></span>  
  
|<span data-ttu-id="86146-716">Понятное имя в перечислении StatisticsTarget</span><span class="sxs-lookup"><span data-stu-id="86146-716">Friendly name in StatisticsTarget</span></span>|<span data-ttu-id="86146-717">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-717">Numeric value</span></span>|  
|---------------------------------------|-------------------|  
|<span data-ttu-id="86146-718">Столбец</span><span class="sxs-lookup"><span data-stu-id="86146-718">Column</span></span>|<span data-ttu-id="86146-719">1</span><span class="sxs-lookup"><span data-stu-id="86146-719">1</span></span>|  
|<span data-ttu-id="86146-720">Индекс</span><span class="sxs-lookup"><span data-stu-id="86146-720">Index</span></span>|<span data-ttu-id="86146-721">2</span><span class="sxs-lookup"><span data-stu-id="86146-721">2</span></span>|  
|<span data-ttu-id="86146-722">All</span><span class="sxs-lookup"><span data-stu-id="86146-722">All</span></span>|<span data-ttu-id="86146-723">3</span><span class="sxs-lookup"><span data-stu-id="86146-723">3</span></span>|  
  
##  <a name="common-properties"></a><a name="CommonProperties"></a> <span data-ttu-id="86146-724">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="86146-724">Common Properties</span></span>  
 <span data-ttu-id="86146-725">Пакеты, задачи, а также контейнеры последовательности, «цикл по каждому элементу» и «цикл по элементам» могут использовать следующие перечисления для задания специфических свойств.</span><span class="sxs-lookup"><span data-stu-id="86146-725">Packages, tasks, and the Foreach Loop, For Loop, and Sequence containers can use the following enumerations to set the specified properties.</span></span>  
  
 <span data-ttu-id="86146-726">`ForceExecutionResult`свойство задается с помощью значений из `DTSForcedExecResult` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-726">`ForceExecutionResult` property-Set by using values from the `DTSForcedExecResult` enumeration.</span></span>  
  
|<span data-ttu-id="86146-727">Понятное имя в перечислении DTSForcedExecResult</span><span class="sxs-lookup"><span data-stu-id="86146-727">Friendly name in DTSForcedExecResult</span></span>|<span data-ttu-id="86146-728">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-728">Numeric value</span></span>|  
|------------------------------------------|-------------------|  
|<span data-ttu-id="86146-729">None</span><span class="sxs-lookup"><span data-stu-id="86146-729">None</span></span>|<span data-ttu-id="86146-730">-1</span><span class="sxs-lookup"><span data-stu-id="86146-730">-1</span></span>|  
|<span data-ttu-id="86146-731">Успешно</span><span class="sxs-lookup"><span data-stu-id="86146-731">Success</span></span>|<span data-ttu-id="86146-732">0</span><span class="sxs-lookup"><span data-stu-id="86146-732">0</span></span>|  
|<span data-ttu-id="86146-733">Failure</span><span class="sxs-lookup"><span data-stu-id="86146-733">Failure</span></span>|<span data-ttu-id="86146-734">1</span><span class="sxs-lookup"><span data-stu-id="86146-734">1</span></span>|  
|<span data-ttu-id="86146-735">Completion</span><span class="sxs-lookup"><span data-stu-id="86146-735">Completion</span></span>|<span data-ttu-id="86146-736">2</span><span class="sxs-lookup"><span data-stu-id="86146-736">2</span></span>|  
  
 <span data-ttu-id="86146-737">`IsolationLevel`свойство задается `IsolationLevel` перечислением .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="86146-737">`IsolationLevel` property-Set by the .NET Framework `IsolationLevel` enumeration.</span></span> <span data-ttu-id="86146-738">Дополнительные сведения см. в документации по библиотеке классов платформы .NET Framework в [Библиотеке MSDN](https://go.microsoft.com/fwlink?LinkId=17313).</span><span class="sxs-lookup"><span data-stu-id="86146-738">For more information, see the .NET Framework Class Library in the [MSDN Library](https://go.microsoft.com/fwlink?LinkId=17313).</span></span>  
  
 <span data-ttu-id="86146-739">`LoggingMode`свойство задается с помощью значений из `DTSLoggingMode` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-739">`LoggingMode` property-Set by using values from the `DTSLoggingMode` enumeration.</span></span>  
  
|<span data-ttu-id="86146-740">Понятное имя в перечислении DTSLoggingMode</span><span class="sxs-lookup"><span data-stu-id="86146-740">Friendly name in DTSLoggingMode</span></span>|<span data-ttu-id="86146-741">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-741">Numeric value</span></span>|  
|-------------------------------------|-------------------|  
|<span data-ttu-id="86146-742">UseParentSetting</span><span class="sxs-lookup"><span data-stu-id="86146-742">UseParentSetting</span></span>|<span data-ttu-id="86146-743">0</span><span class="sxs-lookup"><span data-stu-id="86146-743">0</span></span>|  
|<span data-ttu-id="86146-744">Активировано</span><span class="sxs-lookup"><span data-stu-id="86146-744">Enabled</span></span>|<span data-ttu-id="86146-745">1</span><span class="sxs-lookup"><span data-stu-id="86146-745">1</span></span>|  
|<span data-ttu-id="86146-746">Выключено</span><span class="sxs-lookup"><span data-stu-id="86146-746">Disabled</span></span>|<span data-ttu-id="86146-747">2</span><span class="sxs-lookup"><span data-stu-id="86146-747">2</span></span>|  
  
 <span data-ttu-id="86146-748">`TransactionOption`свойство задается с помощью значений из `DTSTransactionOption` перечисления.</span><span class="sxs-lookup"><span data-stu-id="86146-748">`TransactionOption` property-Set by using values from the `DTSTransactionOption` enumeration.</span></span>  
  
|<span data-ttu-id="86146-749">Понятное имя в перечислении DTSTransactionOption</span><span class="sxs-lookup"><span data-stu-id="86146-749">Friendly name in DTSTransactionOption</span></span>|<span data-ttu-id="86146-750">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="86146-750">Numeric value</span></span>|  
|-------------------------------------------|-------------------|  
|<span data-ttu-id="86146-751">NotSupported</span><span class="sxs-lookup"><span data-stu-id="86146-751">NotSupported</span></span>|<span data-ttu-id="86146-752">0</span><span class="sxs-lookup"><span data-stu-id="86146-752">0</span></span>|  
|<span data-ttu-id="86146-753">Поддерживается</span><span class="sxs-lookup"><span data-stu-id="86146-753">Supported</span></span>|<span data-ttu-id="86146-754">1</span><span class="sxs-lookup"><span data-stu-id="86146-754">1</span></span>|  
|<span data-ttu-id="86146-755">Обязательно</span><span class="sxs-lookup"><span data-stu-id="86146-755">Required</span></span>|<span data-ttu-id="86146-756">2</span><span class="sxs-lookup"><span data-stu-id="86146-756">2</span></span>|  
  
## <a name="related-tasks"></a><span data-ttu-id="86146-757">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="86146-757">Related Tasks</span></span>  
 [<span data-ttu-id="86146-758">Добавление или изменение выражение свойства</span><span class="sxs-lookup"><span data-stu-id="86146-758">Add or Change a Property Expression</span></span>](add-or-change-a-property-expression.md)  
  
## <a name="see-also"></a><span data-ttu-id="86146-759">См. также:</span><span class="sxs-lookup"><span data-stu-id="86146-759">See Also</span></span>  
 <span data-ttu-id="86146-760">[Использование выражений свойств в пакетах](use-property-expressions-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="86146-760">[Use Property Expressions in Packages](use-property-expressions-in-packages.md) </span></span>  
 <span data-ttu-id="86146-761">[Пакеты служб Integration Services (SSIS)](../integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="86146-761">[Integration Services &#40;SSIS&#41; Packages](../integration-services-ssis-packages.md) </span></span>  
 <span data-ttu-id="86146-762">[Контейнеры служб Integration Services](../control-flow/integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="86146-762">[Integration Services Containers](../control-flow/integration-services-containers.md) </span></span>  
 <span data-ttu-id="86146-763">[Задачи служб Integration Services](../control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="86146-763">[Integration Services Tasks](../control-flow/integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="86146-764">Управление очередностью</span><span class="sxs-lookup"><span data-stu-id="86146-764">Precedence Constraints</span></span>](../control-flow/precedence-constraints.md)  
  
  
