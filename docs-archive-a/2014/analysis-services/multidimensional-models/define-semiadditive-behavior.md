---
title: Определить полуаддитивный режим | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- semiadditive
- Business Intelligence enhancements [Analysis Services], semiadditive behavior
- measures [Analysis Services], semiadditive
ms.assetid: b25726bc-728b-4601-ad87-9015c39dc615
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9c2028c350046fdcc9f98bcd0f0612d6a91ccabb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664601"
---
# <a name="define-semiadditive-behavior"></a><span data-ttu-id="5295b-102">Определение полуаддитивного режима</span><span class="sxs-lookup"><span data-stu-id="5295b-102">Define Semiadditive Behavior</span></span>
  <span data-ttu-id="5295b-103">Во многих бизнес-сценариях широко распространены полуаддитивные меры, которые не используют статистическое вычисление единообразно для всех измерений.</span><span class="sxs-lookup"><span data-stu-id="5295b-103">Semiadditive measures, which do not uniformly aggregate across all dimensions, are very common in many business scenarios.</span></span> <span data-ttu-id="5295b-104">Со временем данная проблема затрагивает все кубы, основанные на моментальных снимках балансов.</span><span class="sxs-lookup"><span data-stu-id="5295b-104">Every cube that is based on snapshots of balances over time exhibits this problem.</span></span> <span data-ttu-id="5295b-105">Такие моментальные снимки можно найти в приложениях, связанных с ценными бумагами, балансом счета, бюджетированием, персоналом, страховыми полисами и требованиями, и многими другими областями коммерческой деятельности.</span><span class="sxs-lookup"><span data-stu-id="5295b-105">You can find these snapshots in applications dealing with securities, account balances, budgeting, human resources, insurance policies and claims, and many other business domains.</span></span>  
  
 <span data-ttu-id="5295b-106">Для определения метода статистического вычисления для отдельных мер или элементов атрибута типа учетной записи добавьте к кубу полуаддитивный режим.</span><span class="sxs-lookup"><span data-stu-id="5295b-106">Add semiadditive behavior to a cube to define an aggregation method for individual measures or members of the account type attribute.</span></span> <span data-ttu-id="5295b-107">Если в кубе содержится измерение счетов, то полуаддитивный режим можно добавлять автоматически на основании типа учетной записи.</span><span class="sxs-lookup"><span data-stu-id="5295b-107">If the cube contains an account dimension, you can automatically set semiadditive behavior based on the account type.</span></span>  
  
 <span data-ttu-id="5295b-108">Чтобы добавить полуаддитивный режим, откройте куб в конструкторе кубов и выберите команду **Добавить бизнес-аналитику** в меню «Куб».</span><span class="sxs-lookup"><span data-stu-id="5295b-108">To add semiadditive behavior, open a cube in Cube Designer and choose **Add Business Intelligence** from the Cube menu.</span></span> <span data-ttu-id="5295b-109">В мастере бизнес-аналитики выберите параметр **Определить полуаддитивный режим** на странице **Выбор расширения** .</span><span class="sxs-lookup"><span data-stu-id="5295b-109">In the Business Intelligence Wizard, select the **Define semiadditive behavior** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="5295b-110">Данный мастер затем проведет пользователя по шагам, определяющим меры, работающие в полуаддитивном режиме.</span><span class="sxs-lookup"><span data-stu-id="5295b-110">This wizard then guides you through the steps of identifying which measures have semiadditive behavior.</span></span>  
  
 <span data-ttu-id="5295b-111">За исключением режима LastChild, который доступен в выпуске Standard Edition, полуаддитивные режимы доступны только в бизнес-аналитике или в выпуске Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="5295b-111">With the exception of LastChild which is available in the standard edition, semi-additive behaviors are only available in the business intelligence or enterprise editions.</span></span>  
  
## <a name="define-semiadditive-behavior"></a><span data-ttu-id="5295b-112">Определение полуаддитивного режима</span><span class="sxs-lookup"><span data-stu-id="5295b-112">Define Semiadditive Behavior</span></span>  
 <span data-ttu-id="5295b-113">На странице **Определение полуаддитивного режима** мастера выберите способ определения полуаддитивности, выбрав один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="5295b-113">On the **Define Semiadditive Behavior** page of the wizard, you select how to define semiadditivity by selecting one of the following options:</span></span>  
  
 <span data-ttu-id="5295b-114">**Отключить полуаддитивный режим**</span><span class="sxs-lookup"><span data-stu-id="5295b-114">**Turn off semiadditive behavior**</span></span>  
 <span data-ttu-id="5295b-115">Удаляет полуаддитивный режим из куба, в котором полуаддитивный режим был ранее определен.</span><span class="sxs-lookup"><span data-stu-id="5295b-115">Removes semiadditive behavior from a cube in which semiadditive behavior was previously defined.</span></span> <span data-ttu-id="5295b-116">Данный выбор восстанавливает для показателя значение `SUM`, если для меры установлено значение, соответствующее любому из следующих типов статистической функции.</span><span class="sxs-lookup"><span data-stu-id="5295b-116">This selection resets a measure to `SUM` if it is set to any of the following aggregation function types:</span></span>  
  
-   <span data-ttu-id="5295b-117">By Account</span><span class="sxs-lookup"><span data-stu-id="5295b-117">By Account</span></span>  
  
-   <span data-ttu-id="5295b-118">Average of Children</span><span class="sxs-lookup"><span data-stu-id="5295b-118">Average of Children</span></span>  
  
-   <span data-ttu-id="5295b-119">First Child</span><span class="sxs-lookup"><span data-stu-id="5295b-119">First Child</span></span>  
  
-   <span data-ttu-id="5295b-120">Last Child</span><span class="sxs-lookup"><span data-stu-id="5295b-120">Last Child</span></span>  
  
-   <span data-ttu-id="5295b-121">Last Nonempty Child</span><span class="sxs-lookup"><span data-stu-id="5295b-121">Last Nonempty Child</span></span>  
  
-   <span data-ttu-id="5295b-122">First Nonempty Child</span><span class="sxs-lookup"><span data-stu-id="5295b-122">First Nonempty Child</span></span>  
  
-   <span data-ttu-id="5295b-123">Нет</span><span class="sxs-lookup"><span data-stu-id="5295b-123">None</span></span>  
  
 <span data-ttu-id="5295b-124">Этот параметр не изменяет меры с помощью обычной статистической функции: `Sum` , `Min` , `Max` , `Count` или `Distinct``Count` .</span><span class="sxs-lookup"><span data-stu-id="5295b-124">This option does not change measures with a regular aggregation function: `Sum`, `Min`, `Max`, `Count`, or `Distinct``Count`.</span></span>  
  
 <span data-ttu-id="5295b-125">**Мастер обнаружил измерение счетов "учетная запись", которое содержит полуаддитивные элементы. Сервер будет выполнять статистическую обработку элементов этого измерения в соответствии с полуаддитивный поведением, заданным для каждого типа учетной записи.**</span><span class="sxs-lookup"><span data-stu-id="5295b-125">**The wizard has detected the 'Account" account dimension, which contains semiadditive members. The server will aggregate members of this dimension according to the semiadditive behavior specified for each account type.**</span></span>  
 <span data-ttu-id="5295b-126">Приводит к тому, что система установит все меры из групп мер, измеренных измерением типа «Счет» статистической функцией «By Account», а сервер будет собирать члены измерения согласно полуаддитивному поведению, заданному для каждого счетного типа.</span><span class="sxs-lookup"><span data-stu-id="5295b-126">Causes the system to set all measures from a measure group dimensioned by an Account type dimension to the By Account aggregation function and the server will aggregate members of the dimension according to the semiadditive behavior specified for each account type.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5295b-127">Данный параметр будет выбран по умолчанию, если мастер определит измерение типа «Учетная запись».</span><span class="sxs-lookup"><span data-stu-id="5295b-127">This option is selected by default if the wizard detects an Account type dimension.</span></span>  
  
 <span data-ttu-id="5295b-128">**Определение полуаддитивного режима для отдельных мер**</span><span class="sxs-lookup"><span data-stu-id="5295b-128">**Define semiadditive behavior for individual measures**</span></span>  
 <span data-ttu-id="5295b-129">Позволяет выбрать полуаддитивный режим каждой меры в отдельности.</span><span class="sxs-lookup"><span data-stu-id="5295b-129">Selects the semiadditive behavior of each measure individually.</span></span> <span data-ttu-id="5295b-130">Значение по умолчанию равно `SUM` (полностью аддитивное).</span><span class="sxs-lookup"><span data-stu-id="5295b-130">The default setting is `SUM` (fully additive).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5295b-131">Данный параметр выбирается по умолчанию, если мастер не определяет измерение типа «Учетная запись».</span><span class="sxs-lookup"><span data-stu-id="5295b-131">This option is selected by default if the wizard does not detect an Account type dimension.</span></span>  
  
 <span data-ttu-id="5295b-132">Для каждой меры можно выбирать любой из типов полуаддитивных функций, описанных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="5295b-132">For each measure, you can select from the types of semiadditive functionality described in the following table.</span></span>  
  
|<span data-ttu-id="5295b-133">Полуаддитивная функция</span><span class="sxs-lookup"><span data-stu-id="5295b-133">Semiadditive function</span></span>|<span data-ttu-id="5295b-134">Описание</span><span class="sxs-lookup"><span data-stu-id="5295b-134">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="5295b-135">Average of Children</span><span class="sxs-lookup"><span data-stu-id="5295b-135">Average of Children</span></span>|<span data-ttu-id="5295b-136">Статистическая схема элемента представляет собой среднее его потомков.</span><span class="sxs-lookup"><span data-stu-id="5295b-136">The aggregation of a member is the average of its children.</span></span>|  
|<span data-ttu-id="5295b-137">ByAccount</span><span class="sxs-lookup"><span data-stu-id="5295b-137">ByAccount</span></span>|<span data-ttu-id="5295b-138">Система читает полуаддитивное поведение, заданное для счетного типа.</span><span class="sxs-lookup"><span data-stu-id="5295b-138">The system reads the semiadditive behavior specified for the account type.</span></span>|  
|<span data-ttu-id="5295b-139">Count</span><span class="sxs-lookup"><span data-stu-id="5295b-139">Count</span></span>|<span data-ttu-id="5295b-140">Статистическая схема представляет собой число элементов.</span><span class="sxs-lookup"><span data-stu-id="5295b-140">The aggregation is a count of members.</span></span>|  
|<span data-ttu-id="5295b-141">Количество различных</span><span class="sxs-lookup"><span data-stu-id="5295b-141">Distinct Count</span></span>|<span data-ttu-id="5295b-142">Статистическая схема представляет собой число уникальных элементов.</span><span class="sxs-lookup"><span data-stu-id="5295b-142">The aggregation is a count of unique members.</span></span>|  
|<span data-ttu-id="5295b-143">First Child</span><span class="sxs-lookup"><span data-stu-id="5295b-143">First Child</span></span>|<span data-ttu-id="5295b-144">Значение элемента вычисляется как значение его первого потомка в соответствии с измерением времени.</span><span class="sxs-lookup"><span data-stu-id="5295b-144">The member value is evaluated as the value of its first child along the time dimension.</span></span>|  
|<span data-ttu-id="5295b-145">FirstNonEmpty</span><span class="sxs-lookup"><span data-stu-id="5295b-145">FirstNonEmpty</span></span>|<span data-ttu-id="5295b-146">Значение элемента вычисляется как значение его первого потомка в соответствии с измерением времени, содержащим данные.</span><span class="sxs-lookup"><span data-stu-id="5295b-146">The member value is evaluated as the value of its first child along the time dimension that contains data.</span></span>|  
|<span data-ttu-id="5295b-147">LastChild</span><span class="sxs-lookup"><span data-stu-id="5295b-147">LastChild</span></span>|<span data-ttu-id="5295b-148">Значение элемента вычисляется как значение его последнего потомка в соответствии с измерением времени.</span><span class="sxs-lookup"><span data-stu-id="5295b-148">The member value is evaluated as the value of its last child along the time dimension.</span></span>|  
|<span data-ttu-id="5295b-149">LastNonEmpty</span><span class="sxs-lookup"><span data-stu-id="5295b-149">LastNonEmpty</span></span>|<span data-ttu-id="5295b-150">Значение элемента вычисляется как значение его последнего потомка в соответствии с измерением времени, содержащим данные.</span><span class="sxs-lookup"><span data-stu-id="5295b-150">The member value is evaluated as the value of its last child along the time dimension that contains data.</span></span>|  
|<span data-ttu-id="5295b-151">Максимум</span><span class="sxs-lookup"><span data-stu-id="5295b-151">Max</span></span>|<span data-ttu-id="5295b-152">Применяется стандартная максимальная статистическая функция.</span><span class="sxs-lookup"><span data-stu-id="5295b-152">The standard maximum aggregation function is applied.</span></span>|  
|<span data-ttu-id="5295b-153">Минимум</span><span class="sxs-lookup"><span data-stu-id="5295b-153">Min</span></span>|<span data-ttu-id="5295b-154">Применяется стандартная минимальная статистическая функция.</span><span class="sxs-lookup"><span data-stu-id="5295b-154">The standard minimum aggregation function is applied.</span></span>|  
|<span data-ttu-id="5295b-155">Нет</span><span class="sxs-lookup"><span data-stu-id="5295b-155">None</span></span>|<span data-ttu-id="5295b-156">Статистическая схема не применяется.</span><span class="sxs-lookup"><span data-stu-id="5295b-156">No aggregation is applied.</span></span>|  
|<span data-ttu-id="5295b-157">Sum</span><span class="sxs-lookup"><span data-stu-id="5295b-157">Sum</span></span>|<span data-ttu-id="5295b-158">Применяется стандартная функция суммирования.</span><span class="sxs-lookup"><span data-stu-id="5295b-158">The standard summation function is applied.</span></span>|  
  
 <span data-ttu-id="5295b-159">После завершения работы с мастером любой существующий полуаддитивный режим будет заменен.</span><span class="sxs-lookup"><span data-stu-id="5295b-159">Any existing semiadditive behavior is overwritten when you complete the wizard.</span></span>  
  
  
