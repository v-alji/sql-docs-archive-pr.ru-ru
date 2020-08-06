---
title: Изменение параметров пула ресурсов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, resource pool alter
- resource pools [SQL Server], alter
ms.assetid: 49438285-a011-4dac-bd4f-f35cd90fda61
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2183cceaaf8a3e183d96c154075f9a922942c2c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730461"
---
# <a name="change-resource-pool-settings"></a><span data-ttu-id="282a5-102">Изменение параметров пула ресурсов</span><span class="sxs-lookup"><span data-stu-id="282a5-102">Change Resource Pool Settings</span></span>
  <span data-ttu-id="282a5-103">Можно изменить параметры пула ресурсов в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="282a5-103">You can change resource pool settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="282a5-104">**Перед началом работы**  [ограничения](#LimitationsRestrictions), [разрешения](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="282a5-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="282a5-105">**Изменение параметров для пула ресурсов с использованием:**  [среды SQL Server Management Studio](#ChgRPProp), [Transact-SQL](#ChgRPTSQL)</span><span class="sxs-lookup"><span data-stu-id="282a5-105">**To change the settings for a resource pool, using:**  [SQL Server Management Studio](#ChgRPProp), [Transact-SQL](#ChgRPTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="282a5-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="282a5-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="282a5-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="282a5-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="282a5-108">Максимальный процент использования ЦП должен быть больше минимального или равен ему.</span><span class="sxs-lookup"><span data-stu-id="282a5-108">The maximum CPU percentage must be equal to or higher than the minimum CPU percentage.</span></span> <span data-ttu-id="282a5-109">Максимальный процент использования памяти должен быть больше минимального или равен ему.</span><span class="sxs-lookup"><span data-stu-id="282a5-109">The maximum memory percentage must be equal to or higher than the minimum memory percentage.</span></span>  
  
 <span data-ttu-id="282a5-110">Сумма значений минимальных процентов использования ЦП и минимальных процентов использования памяти для всех пулов ресурсов не должна превышать 100.</span><span class="sxs-lookup"><span data-stu-id="282a5-110">The sums of the minimum CPU percentages and minimum memory percentages for all resource pools must not exceed 100.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="282a5-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="282a5-111">Permissions</span></span>  
 <span data-ttu-id="282a5-112">Для изменения параметров пула ресурсов требуется разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="282a5-112">Changing resource pool settings requires CONTROL SERVER permission.</span></span>  
  
##  <a name="change-resource-pool-settings-using-sql-server-management-studio"></a><a name="ChgRPProp"></a> <span data-ttu-id="282a5-113">Изменение параметров пула ресурсов в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="282a5-113">Change Resource Pool Settings Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="282a5-114">**Изменение параметров пула ресурсов с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="282a5-114">**To change resource pool settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="282a5-115">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]откройте обозреватель объектов и рекурсивно разверните узел **Управление** вплоть до узла **Пулы ресурсов**.</span><span class="sxs-lookup"><span data-stu-id="282a5-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Pools**.</span></span>  
  
2.  <span data-ttu-id="282a5-116">Щелкните правой кнопкой мыши пул ресурсов, подлежащий изменению, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="282a5-116">Right-click the resource pool to be modified, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="282a5-117">На странице **Свойства регулятора ресурсов** выберите строку, относящуюся к пулу ресурсов, в сетке **Пулы ресурсов** , если она не выделена автоматически.</span><span class="sxs-lookup"><span data-stu-id="282a5-117">In the **Resource Governor Properties** page, select the row for the resource pool in the **Resource pools** grid if it is not automatically selected.</span></span>  
  
4.  <span data-ttu-id="282a5-118">Щелкните или дважды щелкните ячейки в строке, подлежащие изменению, и введите новые значения.</span><span class="sxs-lookup"><span data-stu-id="282a5-118">Click or double-click the cells in the row to be changed, and enter the new values.</span></span>  
  
5.  <span data-ttu-id="282a5-119">Чтобы сохранить изменения, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="282a5-119">To save the changes, click **OK**</span></span>  
  
##  <a name="change-resource-pool-settings-using-transact-sql"></a><a name="ChgRPTSQL"></a> <span data-ttu-id="282a5-120">Изменение параметров пула ресурсов с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="282a5-120">Change Resource Pool Settings Using Transact-SQL</span></span>  
 <span data-ttu-id="282a5-121">**Изменение параметров пула ресурсов с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="282a5-121">**To change resource pool settings by using [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span></span>  
  
1.  <span data-ttu-id="282a5-122">Выполните инструкцию `ALTER RESOURCE POOL`, указав значения свойств, которые необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="282a5-122">Run the `ALTER RESOURCE POOL` statement specifying the property values to be changed.</span></span>  
  
2.  <span data-ttu-id="282a5-123">Выполните инструкцию **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="282a5-123">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="282a5-124">Пример (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="282a5-124">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="282a5-125">В следующем примере показано изменение значения параметра максимального процента использования ЦП для пула ресурсов с именем `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="282a5-125">The following example changes the max CPU percentage setting for the resource pool named `poolAdhoc`.</span></span>  
  
```  
ALTER RESOURCE POOL poolAdhoc  
WITH (MAX_CPU_PERCENT = 25);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="282a5-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="282a5-126">See Also</span></span>  
 <span data-ttu-id="282a5-127">[регулятор ресурсов](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="282a5-127">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="282a5-128">[Активация регулятора ресурсов](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="282a5-128">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="282a5-129">[Создание пула ресурсов](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="282a5-129">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="282a5-130">[Удаление пула ресурсов](delete-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="282a5-130">[Delete a Resource Pool](delete-a-resource-pool.md) </span></span>  
 <span data-ttu-id="282a5-131">[Группа рабочей нагрузки регулятора ресурсов](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="282a5-131">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="282a5-132">[Функция-классификатор регулятора ресурсов](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="282a5-132">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="282a5-133">[ALTER RESOURCE POOL (Transact-SQL)](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="282a5-133">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="282a5-134">ALTER RESOURCE GOVERNOR (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="282a5-134">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
