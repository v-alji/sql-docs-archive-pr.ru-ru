---
title: Создание пула ресурсов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- resource pools [SQL Server], create
- Resource Governor, resource pool create
ms.assetid: 44dd0567-a4c8-4c72-89ff-e76f6ddef344
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5abd2e60f4f9bb5290b47f95349782f8b26ad8bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668747"
---
# <a name="create-a-resource-pool"></a><span data-ttu-id="9a169-102">Создание пула ресурсов</span><span class="sxs-lookup"><span data-stu-id="9a169-102">Create a Resource Pool</span></span>
  <span data-ttu-id="9a169-103">Можно создать пул ресурсов в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a169-103">You can create a resource pool by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="9a169-104">**Перед началом работы**  [ограничения](#LimitationsRestrictions), [разрешения](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="9a169-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="9a169-105">**Создание пула ресурсов с использованием:**  [среды SQL Server Management Studio](#CreRPProp), [Transact-SQL](#CreRPTSQL)</span><span class="sxs-lookup"><span data-stu-id="9a169-105">**To create a resource pool, using:**  [SQL Server Management Studio](#CreRPProp), [Transact-SQL](#CreRPTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9a169-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="9a169-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="9a169-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="9a169-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="9a169-108">Максимальный процент использования ЦП должен быть больше минимального или равен ему.</span><span class="sxs-lookup"><span data-stu-id="9a169-108">The maximum CPU percentage must be equal to or higher than the minimum CPU percentage.</span></span> <span data-ttu-id="9a169-109">Максимальный процент использования памяти должен быть больше минимального или равен ему.</span><span class="sxs-lookup"><span data-stu-id="9a169-109">The maximum memory percentage must be equal to or higher than the minimum memory percentage.</span></span>  
  
 <span data-ttu-id="9a169-110">Сумма значений минимальных процентов использования ЦП и минимальных процентов использования памяти для всех пулов ресурсов не должна превышать 100.</span><span class="sxs-lookup"><span data-stu-id="9a169-110">The sums of the minimum CPU percentages and minimum memory percentages for all resource pools must not exceed 100.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9a169-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="9a169-111">Permissions</span></span>  
 <span data-ttu-id="9a169-112">Для создания пула ресурсов требуется разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="9a169-112">Creating a resource pool requires CONTROL SERVER permission.</span></span>  
  
##  <a name="create-a-resource-pool-using-sql-server-management-studio"></a><a name="CreRPProp"></a> <span data-ttu-id="9a169-113">Создание пула ресурсов в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9a169-113">Create a Resource Pool Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="9a169-114">**Создание пула ресурсов с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="9a169-114">**To create a resource pool by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="9a169-115">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]откройте обозреватель объектов и рекурсивно разверните узел **Управление** вплоть до узла **Регулятор ресурсов**.</span><span class="sxs-lookup"><span data-stu-id="9a169-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="9a169-116">Щелкните **Регулятор ресурсов**правой кнопкой мыши и выберите команду **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9a169-116">Right-click **Resource Governor**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="9a169-117">В сетке **Пулы ресурсов** щелкните первый столбец в пустой строке.</span><span class="sxs-lookup"><span data-stu-id="9a169-117">In the **Resource pools** grid, click the first column in the empty row.</span></span> <span data-ttu-id="9a169-118">Этот столбец отмечен звездочкой (\*).</span><span class="sxs-lookup"><span data-stu-id="9a169-118">This column is labeled with an asterisk (\*).</span></span>  
  
4.  <span data-ttu-id="9a169-119">Дважды щелкните пустую ячейку в столбце **Имя** .</span><span class="sxs-lookup"><span data-stu-id="9a169-119">Double-click the empty cell in the **Name** column.</span></span> <span data-ttu-id="9a169-120">Введите имя, которое следует присвоить пулу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9a169-120">Type in the name that you want to use for the resource pool.</span></span>  
  
5.  <span data-ttu-id="9a169-121">Щелкните или дважды щелкните все прочие ячейки в строке, в которые необходимо внести изменения, и введите новые значения.</span><span class="sxs-lookup"><span data-stu-id="9a169-121">Click or double-click any other cells in the row you want to change, and enter the new values.</span></span>  
  
6.  <span data-ttu-id="9a169-122">Чтобы сохранить изменения, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9a169-122">To save the changes, click **OK**</span></span>  
  
##  <a name="create-a-resource-pool-using-transact-sql"></a><a name="CreRPTSQL"></a> <span data-ttu-id="9a169-123">Создание пула ресурсов с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9a169-123">Create a Resource Pool Using Transact-SQL</span></span>  
 <span data-ttu-id="9a169-124">**Создание пула ресурсов с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="9a169-124">**To create a resource pool by using [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span></span>  
  
1.  <span data-ttu-id="9a169-125">Выполните инструкцию `CREATE RESOURCE POOL`, указав значения свойств, которые необходимо присвоить.</span><span class="sxs-lookup"><span data-stu-id="9a169-125">Run the `CREATE RESOURCE POOL` statement specifying the property values to be set.</span></span>  
  
2.  <span data-ttu-id="9a169-126">Выполните инструкцию **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="9a169-126">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="9a169-127">Пример (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9a169-127">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="9a169-128">В следующем примере создается пул ресурсов с именем `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="9a169-128">The following example creates a resource pool named `poolAdhoc`.</span></span>  
  
```  
CREATE RESOURCE POOL poolAdhoc  
WITH (MAX_CPU_PERCENT = 20);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="9a169-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="9a169-129">See Also</span></span>  
 <span data-ttu-id="9a169-130">[регулятор ресурсов](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="9a169-130">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="9a169-131">[Активация регулятора ресурсов](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="9a169-131">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="9a169-132">[Пул ресурсов регулятора ресурсов](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="9a169-132">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="9a169-133">[Изменение параметров пула ресурсов](change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="9a169-133">[Change Resource Pool Settings](change-resource-pool-settings.md) </span></span>  
 <span data-ttu-id="9a169-134">[Удаление пула ресурсов](delete-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="9a169-134">[Delete a Resource Pool](delete-a-resource-pool.md) </span></span>  
 <span data-ttu-id="9a169-135">[Настройка регулятора ресурсов с помощью шаблона](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="9a169-135">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 <span data-ttu-id="9a169-136">[Группа рабочей нагрузки регулятора ресурсов](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="9a169-136">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="9a169-137">[Функция-классификатор регулятора ресурсов](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="9a169-137">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="9a169-138">[CREATE RESOURCE POOL (Transact-SQL)](/sql/t-sql/statements/create-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9a169-138">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="9a169-139">ALTER RESOURCE GOVERNOR (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9a169-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
