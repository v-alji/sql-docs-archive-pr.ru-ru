---
title: Диалоговое окно "Создание нового условия" или "Открытие условия", страница "Общие" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.condition.f1
ms.assetid: 106954bf-e4ba-412b-9c1a-907d06153dcd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 72e4a77df553ac8e97609e82bd51c8fd93b64b23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668821"
---
# <a name="create-new-condition-or-open-condition-dialog-box-general-page"></a><span data-ttu-id="12635-102">Диалоговое окно «Создание нового условия» или «Открытие условия», страница «Общие»</span><span class="sxs-lookup"><span data-stu-id="12635-102">Create New Condition or Open Condition Dialog Box, General Page</span></span>
  <span data-ttu-id="12635-103">С помощью этого диалогового окна можно создать или изменить условие управления на основе политик.</span><span class="sxs-lookup"><span data-stu-id="12635-103">Use this dialog box to create or change a Policy-Based Management condition.</span></span> <span data-ttu-id="12635-104">Условие — это логическое выражение, задающее набор допустимых состояний для управляемой цели управления на основе политик по отношению к аспектам.</span><span class="sxs-lookup"><span data-stu-id="12635-104">A condition is a Boolean expression that specifies a set of allowed states of a Policy-Based Management managed target with regard to facets.</span></span> <span data-ttu-id="12635-105">Свойства, которые можно выбрать в поле **Выражение/поле** , зависят от используемого аспекта.</span><span class="sxs-lookup"><span data-stu-id="12635-105">The properties that can be selected in the **Expression/Field** box depend upon the facet that is used.</span></span> <span data-ttu-id="12635-106">Дополнительные сведения о связи условий с аспектами и политиками см. в статье [Администрирование серверов с помощью управления на основе политик](administer-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="12635-106">For more information about how conditions relate to facets and policies, see [Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="12635-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="12635-107">Options</span></span>  
 <span data-ttu-id="12635-108">**имя**;</span><span class="sxs-lookup"><span data-stu-id="12635-108">**Name**</span></span>  
 <span data-ttu-id="12635-109">Введите имя для нового условия.</span><span class="sxs-lookup"><span data-stu-id="12635-109">For a new condition, type the new condition name.</span></span> <span data-ttu-id="12635-110">Если условие уже существует, отображается его имя.</span><span class="sxs-lookup"><span data-stu-id="12635-110">For an existing condition, the name is displayed.</span></span>  
  
 <span data-ttu-id="12635-111">**Аспект**</span><span class="sxs-lookup"><span data-stu-id="12635-111">**Facet**</span></span>  
 <span data-ttu-id="12635-112">Аспект, используемый данным условием.</span><span class="sxs-lookup"><span data-stu-id="12635-112">The facet used by this condition.</span></span>  
  
 <span data-ttu-id="12635-113">**AndOr**</span><span class="sxs-lookup"><span data-stu-id="12635-113">**AndOr**</span></span>  
 <span data-ttu-id="12635-114">Если было создано несколько выражений, показывает, соединяются ли они с помощью оператора **And** или оператора **Or**.</span><span class="sxs-lookup"><span data-stu-id="12635-114">When you add multiple expressions, indicates whether the expressions should be joined by using **And** or **Or**.</span></span> <span data-ttu-id="12635-115">Если существует только одно выражение, то поле остается пустым.</span><span class="sxs-lookup"><span data-stu-id="12635-115">Remains blank when there is only one expression.</span></span>  
  
 <span data-ttu-id="12635-116">**Поле**</span><span class="sxs-lookup"><span data-stu-id="12635-116">**Field**</span></span>  
 <span data-ttu-id="12635-117">Каждый аспект отображает одно или несколько настраиваемых свойств.</span><span class="sxs-lookup"><span data-stu-id="12635-117">Each facet exposes one or more properties that can be set.</span></span> <span data-ttu-id="12635-118">Выберите в списке доступных свойств одно из свойств, чтобы создать выражение для данного условия.</span><span class="sxs-lookup"><span data-stu-id="12635-118">In the field box, select a property from the list of available properties to create an expression for this condition.</span></span>  
  
 <span data-ttu-id="12635-119">**Оператор**</span><span class="sxs-lookup"><span data-stu-id="12635-119">**Operator**</span></span>  
 <span data-ttu-id="12635-120">Выберите оператор сравнения для этого выражения.</span><span class="sxs-lookup"><span data-stu-id="12635-120">Select a comparison operator for this expression.</span></span> <span data-ttu-id="12635-121">Доступны следующие операторы: =, !=, >, >=, <, <=, [NOT]LIKE, [NOT]IN.</span><span class="sxs-lookup"><span data-stu-id="12635-121">Operators are as follows: =, !=, >, >=, <, <=, [NOT]LIKE, [NOT]IN.</span></span> <span data-ttu-id="12635-122">Для некоторых свойств доступны не все операторы.</span><span class="sxs-lookup"><span data-stu-id="12635-122">Not all operators are available for some properties.</span></span>  
  
 <span data-ttu-id="12635-123">**Значение**</span><span class="sxs-lookup"><span data-stu-id="12635-123">**Value**</span></span>  
 <span data-ttu-id="12635-124">Установленное значение для данного выражения.</span><span class="sxs-lookup"><span data-stu-id="12635-124">The value setting for this expression.</span></span> <span data-ttu-id="12635-125">Доступные значения зависят от аспекта.</span><span class="sxs-lookup"><span data-stu-id="12635-125">The allowed values depend on the facet.</span></span> <span data-ttu-id="12635-126">Значения могут быть истинными или ложными, строковыми или числовыми.</span><span class="sxs-lookup"><span data-stu-id="12635-126">Values can be TRUE/FALSE, string, or numeric.</span></span> <span data-ttu-id="12635-127">Строковые значения необходимо заключать в одинарные кавычки, например **'AdventureWorks'**.</span><span class="sxs-lookup"><span data-stu-id="12635-127">String values must be enclosed in single quotation marks, for example: **'AdventureWorks'**.</span></span> <span data-ttu-id="12635-128">Для некоторых свойств доступны не все операторы.</span><span class="sxs-lookup"><span data-stu-id="12635-128">Not all operators are available for some properties.</span></span>  
  
## <a name="group-clauses"></a><span data-ttu-id="12635-129">Предложения группы</span><span class="sxs-lookup"><span data-stu-id="12635-129">Group Clauses</span></span>  
 <span data-ttu-id="12635-130">Предложения можно группировать, чтобы они действовали как единый блок отдельно от остального запроса. Это аналогично размещению скобок вокруг выражения в математической формуле или логическом выражении.</span><span class="sxs-lookup"><span data-stu-id="12635-130">Clauses can be grouped to operate as a single unit separate from the rest of the query, just like putting parentheses around an expression in a mathematical equation or logic statement.</span></span> <span data-ttu-id="12635-131">Группирование предложений полезно при построении сложных запросов.</span><span class="sxs-lookup"><span data-stu-id="12635-131">Grouping clauses is useful when you are building complex queries.</span></span>  
  
 <span data-ttu-id="12635-132">**Группирование предложений**</span><span class="sxs-lookup"><span data-stu-id="12635-132">**To group clauses**</span></span>  
  
-   <span data-ttu-id="12635-133">Нажмите клавишу SHIFT или CTRL, а затем щелкните несколько предложений, чтобы выбрать диапазон.</span><span class="sxs-lookup"><span data-stu-id="12635-133">Press the SHIFT or CTRL keys, and then click two or more clauses to select a range.</span></span> <span data-ttu-id="12635-134">Щелкните правой кнопкой мыши выделенную область и выберите пункт **Предложения группы**.</span><span class="sxs-lookup"><span data-stu-id="12635-134">Right-click the selected area, and then click **Group Clauses**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12635-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="12635-135">See Also</span></span>  
 [<span data-ttu-id="12635-136">Администрирование серверов с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="12635-136">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
