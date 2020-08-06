---
title: Перемещение группы рабочей нагрузки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.rg.properties_moveworkloadgroup.f1
helpviewer_keywords:
- workload groups [SQL Server], move
- Resource Governor, workload group move
ms.assetid: f2068636-6e53-486a-a6fc-c12de2a38424
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7f73b48f0ec2255760b4ee55acfaf91dc02af7cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731469"
---
# <a name="move-a-workload-group"></a><span data-ttu-id="40623-102">Перемещение группы рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="40623-102">Move a Workload Group</span></span>
  <span data-ttu-id="40623-103">Группу рабочей нагрузки регулятора ресурсов можно переместить в другой пул ресурсов в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или с помощью Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="40623-103">You can move a Resource Governor workload group to a different resource pool by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="40623-104">**Перед началом работы**  [ограничения](#LimitationsRestrictions), [разрешения](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="40623-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="40623-105">**Перемещение группы рабочей нагрузки с использованием:**  [среды SQL Server Management Studio](#MoveWGSSMS), [Transact-SQL](#MoveWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="40623-105">**To move a workload group, using:**  [SQL Server Management Studio](#MoveWGSSMS), [Transact-SQL](#MoveWGTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="40623-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="40623-106">Before You Begin</span></span>  
 <span data-ttu-id="40623-107">Перемещение группы рабочей нагрузки становится невозможным, если имеется ожидающая выполнения операция настройки регулятора ресурсов.</span><span class="sxs-lookup"><span data-stu-id="40623-107">You cannot move a workload group if there is a pending Resource Governor configuration operation.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="40623-108">Ограничения</span><span class="sxs-lookup"><span data-stu-id="40623-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="40623-109">Перемещение группы рабочей нагрузки становится невозможным, если имеется ожидающая выполнения операция настройки регулятора ресурсов.</span><span class="sxs-lookup"><span data-stu-id="40623-109">You cannot move a workload group if there is a pending Resource Governor configuration operation.</span></span> <span data-ttu-id="40623-110">Чтобы выяснить, находится ли конфигурация в состоянии ожидания, выполните запрос к динамическому административному представлению [sys.dm_resource_governor_configuration (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql), получив текущее состояние is_configuration_pending.</span><span class="sxs-lookup"><span data-stu-id="40623-110">You can determine whether there is a configuration pending by querying the [sys.dm_resource_governor_configuration &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) dynamic management view to get the current status of is_configuration_pending.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="40623-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="40623-111">Permissions</span></span>  
 <span data-ttu-id="40623-112">Для перемещения группы рабочей нагрузки требуется разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="40623-112">Moving a workload group requires CONTROL SERVER permission.</span></span>  
  
##  <a name="move-a-workload-group-using-sql-server-management-studio"></a><a name="MoveWGSSMS"></a> <span data-ttu-id="40623-113">Перемещение группы рабочей нагрузки с использованием среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="40623-113">Move a Workload Group Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="40623-114">**Перемещение группы рабочей нагрузки в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="40623-114">**To move a workload group by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**</span></span>  
  
1.  <span data-ttu-id="40623-115">В обозревателе объектов рекурсивно разверните узел **Управление** вплоть до узла **Регулятор ресурсов**.</span><span class="sxs-lookup"><span data-stu-id="40623-115">In Object Explorer, recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="40623-116">Щелкните правой кнопкой мыши **Регулятор ресурсов** и выберите пункт **Свойства**, после чего откроется страница **Свойства регулятора ресурсов** .</span><span class="sxs-lookup"><span data-stu-id="40623-116">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="40623-117">В окне **Пулы ресурсов** щелкните пул ресурсов, содержащий группу рабочей нагрузки, которая должна быть перемещена.</span><span class="sxs-lookup"><span data-stu-id="40623-117">In the **Resource Pools** window, click the resource pool containing the workload group to be moved.</span></span> <span data-ttu-id="40623-118">Теперь в окне **Группы рабочей нагрузки** появятся списки групп рабочей нагрузки в этом пуле ресурсов.</span><span class="sxs-lookup"><span data-stu-id="40623-118">The **Workload Groups** window now lists the workload groups in that resource pool.</span></span>  
  
4.  <span data-ttu-id="40623-119">Чтобы переместить группу рабочей нагрузки, выделите соответствующую ей строку, щелкните правой кнопкой мыши указатель в начале строки и выберите команду **Переместить** , укажите новое расположение и нажмите кнопку **Переместить**.</span><span class="sxs-lookup"><span data-stu-id="40623-119">In the **Workload Groups** window, right-click the right arrow to the left of the workload group to be moved, and click **Move to**.</span></span> <span data-ttu-id="40623-120">Будет отображено окно **Перемещение группы рабочей нагрузки** .</span><span class="sxs-lookup"><span data-stu-id="40623-120">This displays a **Move Workload Group** window.</span></span>  
  
5.  <span data-ttu-id="40623-121">Доступные пулы ресурсов отображаются в окне.</span><span class="sxs-lookup"><span data-stu-id="40623-121">Available resource pools are displayed in the window.</span></span> <span data-ttu-id="40623-122">Щелкните имя пула ресурсов, в который нужно перенести группу рабочей нагрузки, а затем нажмите кнопку **ОК** , чтобы выполнить это действие.</span><span class="sxs-lookup"><span data-stu-id="40623-122">Click the name of the resource pool that you want to move the workload group to, and then click **OK** to carry out this action.</span></span>  
  
6.  <span data-ttu-id="40623-123">Действие не завершено, пока не будет нажата кнопка **ОК**.</span><span class="sxs-lookup"><span data-stu-id="40623-123">This action is not completed until after you click **OK**.</span></span> <span data-ttu-id="40623-124">При нажатии кнопки **ОК**выполняется инструкция ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="40623-124">When you click **OK**, the ALTER RESOURCE GOVERNOR RECONFIGURE statement is executed.</span></span>  
  
7.  <span data-ttu-id="40623-125">Если операция создания или изменения конфигурации пула ресурсов или группы рабочей нагрузки завершилась неуспешно, под заголовком страницы свойств будет отображено сводное сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="40623-125">If the create or reconfigure operation fails for the resource pool or workload group, a summary error message appears below the title of the property page.</span></span> <span data-ttu-id="40623-126">Чтобы просмотреть подробное сообщение об ошибке, щелкните стрелку вниз рядом с ним.</span><span class="sxs-lookup"><span data-stu-id="40623-126">To see a detailed error message, click the down arrow on the error message.</span></span>  
  
##  <a name="move-a-workload-group-using-transact-sql"></a><a name="MoveWGTSQL"></a> <span data-ttu-id="40623-127">Перемещение группы рабочей нагрузки с использованием Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="40623-127">Move a Workload Group Using Transact-SQL</span></span>  
 <span data-ttu-id="40623-128">**Перемещение группы рабочей нагрузки с использованием Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="40623-128">**To move a workload group by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="40623-129">Выполните инструкцию `ALTER WORKLOAD GROUP`, указав имя группы рабочей нагрузки для перемещения, и пул ресурсов, в который она должна быть перемещена.</span><span class="sxs-lookup"><span data-stu-id="40623-129">Run the `ALTER WORKLOAD GROUP` statement specifying the name of the workload group to be moved and the resource pool to which it should be moved.</span></span>  
  
2.  <span data-ttu-id="40623-130">Выполните инструкцию **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="40623-130">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="40623-131">Пример (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="40623-131">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="40623-132">В следующем примере показано, как переместить группу рабочей нагрузки с именем `groupAdhoc` в пул ресурсов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="40623-132">The following example moves a workload group named `groupAdhoc` to the default resource pool.</span></span>  
  
```  
ALTER WORKLOAD GROUP groupAdhoc  
USING [default];  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="40623-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="40623-133">See Also</span></span>  
 <span data-ttu-id="40623-134">[регулятор ресурсов](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="40623-134">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="40623-135">[Активация регулятора ресурсов](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="40623-135">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="40623-136">[Создание пула ресурсов](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="40623-136">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="40623-137">[Создание группы рабочей нагрузки](create-a-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="40623-137">[Create a Workload Group](create-a-workload-group.md) </span></span>  
 <span data-ttu-id="40623-138">[ALTER WORKLOAD GROUP (Transact-SQL)](/sql/t-sql/statements/alter-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="40623-138">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span></span>  
 [<span data-ttu-id="40623-139">ALTER RESOURCE GOVERNOR (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="40623-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
