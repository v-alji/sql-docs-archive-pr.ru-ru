---
title: Удаление пула ресурсов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, resource pool delete
- resource pools [SQL Server], delete
ms.assetid: 3bdd348b-6582-4ffa-80ef-d49e50596ce5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a67b0e2262fa3007597091b6087cc937bb0f3276
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731478"
---
# <a name="delete-a-resource-pool"></a><span data-ttu-id="22fb3-102">Удаление пула ресурсов</span><span class="sxs-lookup"><span data-stu-id="22fb3-102">Delete a Resource Pool</span></span>
  <span data-ttu-id="22fb3-103">Регулятор ресурсов можно удалить в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или с помощью Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="22fb3-103">You can delete a resource pool by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="22fb3-104">**Перед началом работы**  [ограничения](#LimitationsRestrictions), [разрешения](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="22fb3-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="22fb3-105">**Удаление пула ресурсов с использованием:** [среды SQL Server Management Studio](#DelRPSSMS), [Transact-SQL](#DelRPTSQL)</span><span class="sxs-lookup"><span data-stu-id="22fb3-105">**To delete a resource pool, using:** [SQL Server Management Studio](#DelRPSSMS), [Transact-SQL](#DelRPTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="22fb3-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="22fb3-106">Before You Begin</span></span>  
 <span data-ttu-id="22fb3-107">Пул ресурсов нельзя удалить, если он содержит группы рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="22fb3-107">You cannot delete a resource pool if it contains workload groups.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="22fb3-108">Ограничения</span><span class="sxs-lookup"><span data-stu-id="22fb3-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="22fb3-109">Нельзя удалять пулы регулятора ресурсов по умолчанию или внутренние пулы ресурсов.</span><span class="sxs-lookup"><span data-stu-id="22fb3-109">You cannot delete the Resource Governor default or internal resource pools.</span></span> <span data-ttu-id="22fb3-110">Пул ресурсов нельзя удалить, если он содержит группы рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="22fb3-110">You cannot delete a resource pool if it contains workload groups.</span></span> <span data-ttu-id="22fb3-111">Дополнительные сведения см. в статье [Delete a Workload Group](delete-a-workload-group.md).</span><span class="sxs-lookup"><span data-stu-id="22fb3-111">For more information, see [Delete a Workload Group](delete-a-workload-group.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="22fb3-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="22fb3-112">Permissions</span></span>  
 <span data-ttu-id="22fb3-113">Для удаления пула ресурсов требуется разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="22fb3-113">Deleting a resource pool requires CONTROL SERVER permission.</span></span>  
  
##  <a name="delete-a-resource-pool-using-object-explorer"></a><a name="DelRPSSMS"></a> <span data-ttu-id="22fb3-114">Удаление пула ресурсов с помощью обозревателя объектов</span><span class="sxs-lookup"><span data-stu-id="22fb3-114">Delete a Resource Pool Using Object Explorer</span></span>  
 <span data-ttu-id="22fb3-115">**Удаление пула ресурсов в среде SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="22fb3-115">**To delete a resource pool by using SQL Server Management Studio**</span></span>  
  
1.  <span data-ttu-id="22fb3-116">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]откройте обозреватель объектов и рекурсивно разверните узел **Управление** вплоть до узла **Регулятор ресурсов**.</span><span class="sxs-lookup"><span data-stu-id="22fb3-116">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="22fb3-117">Щелкните правой кнопкой мыши пул ресурсов, который необходимо удалить, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="22fb3-117">Right-click the resource pool to be deleted, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="22fb3-118">В окне **Удаление объекта** этот пул ресурсов будет указан в списке **Объект для удаления** .</span><span class="sxs-lookup"><span data-stu-id="22fb3-118">In the **Delete Object** window, the resource pool is listed in the **Object to be deleted** list.</span></span> <span data-ttu-id="22fb3-119">Чтобы удалить пул ресурсов, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="22fb3-119">To delete the resource pool, click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="22fb3-120">Если удаляемый пул ресурсов содержит группы рабочей нагрузки, удалить его не удастся.</span><span class="sxs-lookup"><span data-stu-id="22fb3-120">If the resource pool that you are trying to delete contains a workload group, this action will fail.</span></span>  
  
##  <a name="delete-a-resource-pool-using-transact-sql"></a><a name="DelRPTSQL"></a> <span data-ttu-id="22fb3-121">Удаление пула ресурсов с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="22fb3-121">Delete a Resource Pool Using Transact-SQL</span></span>  
 <span data-ttu-id="22fb3-122">**Удаление пула ресурсов с помощью Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="22fb3-122">**To delete a resource pool by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="22fb3-123">Выполните инструкцию `DROP RESOURCE POOL`, указав имя пула ресурсов, который необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="22fb3-123">Run the `DROP RESOURCE POOL` statement specifying the name of the resource pool to delete.</span></span>  
  
2.  <span data-ttu-id="22fb3-124">Выполните инструкцию **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="22fb3-124">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="22fb3-125">Пример (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="22fb3-125">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="22fb3-126">В следующем примере удаляется группа рабочей нагрузки с именем `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="22fb3-126">The following example drops a workload group named `poolAdhoc`.</span></span>  
  
```  
DROP RESOURCE POOL poolAdhoc;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="22fb3-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="22fb3-127">See Also</span></span>  
 <span data-ttu-id="22fb3-128">[регулятор ресурсов](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="22fb3-128">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="22fb3-129">[Пул ресурсов регулятора ресурсов](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="22fb3-129">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="22fb3-130">[Создание пула ресурсов](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="22fb3-130">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="22fb3-131">[Изменение параметров пула ресурсов](change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="22fb3-131">[Change Resource Pool Settings](change-resource-pool-settings.md) </span></span>  
 <span data-ttu-id="22fb3-132">[Группа рабочей нагрузки регулятора ресурсов](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="22fb3-132">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="22fb3-133">[Функция-классификатор регулятора ресурсов](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="22fb3-133">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="22fb3-134">[DROP WORKLOAD GROUP (Transact-SQL)](/sql/t-sql/statements/drop-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="22fb3-134">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="22fb3-135">[DROP RESOURCE POOL (Transact-SQL)](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="22fb3-135">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="22fb3-136">ALTER RESOURCE GOVERNOR (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="22fb3-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
