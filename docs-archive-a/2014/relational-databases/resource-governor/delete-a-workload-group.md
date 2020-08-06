---
title: Удаление группы рабочей нагрузки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- workload groups [SQL Server], delete
- Resource Governor, workload group delete
ms.assetid: d5902c46-5c28-4ac1-8b56-cb4ca2b072d0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 801a731db6c5b31bc479d1a3f6079c45ad9a7c04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731486"
---
# <a name="delete-a-workload-group"></a><span data-ttu-id="aab36-102">Удаление группы рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="aab36-102">Delete a Workload Group</span></span>
  <span data-ttu-id="aab36-103">Группу рабочей нагрузки или пул ресурсов можно удалить в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] либо с помощью Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="aab36-103">You can delete a workload group or resource pool by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="aab36-104">**Перед началом работы**  [ограничения](#LimitationsRestrictions), [разрешения](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="aab36-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="aab36-105">**Удаление группы рабочей нагрузки с помощью**:  [обозревателя объектов](#DelWGObjEx), [свойств Resource Governor](#DelWGRGProp), [Transact-SQL](#DelWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="aab36-105">**To delete a workload group, using:**  [Object Explorer](#DelWGObjEx), [Resource Governor Properties](#DelWGRGProp), [Transact-SQL](#DelWGTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="aab36-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="aab36-106">Before You Begin</span></span>  
 <span data-ttu-id="aab36-107">Группу рабочей нагрузки нельзя удалить, если она содержит активные сеансы.</span><span class="sxs-lookup"><span data-stu-id="aab36-107">You cannot delete a workload group if it contains active sessions.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="aab36-108">Ограничения</span><span class="sxs-lookup"><span data-stu-id="aab36-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="aab36-109">Если группа рабочей нагрузки содержит активные сеансы, то удалить или переместить ее в другой пул ресурсов путем вызова инструкции ALTER RESOURCE GOVERNOR RECONFIGURE для применения изменений не удастся.</span><span class="sxs-lookup"><span data-stu-id="aab36-109">If a workload group contains active sessions, deleting or moving the workload group to a different resource pool will fail when the ALTER RESOURCE GOVERNOR RECONFIGURE statement is called to apply the change.</span></span> <span data-ttu-id="aab36-110">Во избежание этой проблемы можно предпринять одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="aab36-110">To avoid this problem, you can take one of the following actions:</span></span>  
  
-   <span data-ttu-id="aab36-111">Подождать, пока все сеансы затронутых групп завершатся, и заново выполнить инструкцию ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="aab36-111">Wait until all the sessions from the affected group have disconnected, and then rerun the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span>  
  
-   <span data-ttu-id="aab36-112">Явно остановить сеанс в затронутой группе, используя команду KILL, и затем заново выполнить инструкцию ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="aab36-112">Explicitly stop sessions in the affected group by using the KILL command, and then rerun the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span> <span data-ttu-id="aab36-113">Если сеансы не следует прерывать принудительно, то используется кнопка **Удалить** , но перед этим необходимо остановить активные сеансы, повторно создать группу с первоначальным именем и переместить ее в первоначальный пул ресурсов.</span><span class="sxs-lookup"><span data-stu-id="aab36-113">If you decide that you do not want to explicitly stop sessions after you use **Delete** but before you stop active sessions, re-create the group by using the original name and move the group to the original resource pool.</span></span>  
  
-   <span data-ttu-id="aab36-114">Перезапустите сервер.</span><span class="sxs-lookup"><span data-stu-id="aab36-114">Restart the server.</span></span> <span data-ttu-id="aab36-115">После завершения процесса перезапуска удаленная группа не будет создана, а перемещенная группа будет использовать новое назначение пула ресурсов.</span><span class="sxs-lookup"><span data-stu-id="aab36-115">After the restart process is completed, the deleted group will not be created, and a moved group will use the new resource pool assignment.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="aab36-116">Permissions</span><span class="sxs-lookup"><span data-stu-id="aab36-116">Permissions</span></span>  
 <span data-ttu-id="aab36-117">Для удаления группы рабочей нагрузки требуется разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="aab36-117">Deleting a workload group requires CONTROL SERVER permission.</span></span>  
  
##  <a name="delete-a-workload-group-using-object-explorer"></a><a name="DelWGObjEx"></a> <span data-ttu-id="aab36-118">Удаление группы рабочей нагрузки с помощью обозревателя объектов</span><span class="sxs-lookup"><span data-stu-id="aab36-118">Delete a Workload Group Using Object Explorer</span></span>  
 <span data-ttu-id="aab36-119">**Удаление группы рабочей нагрузки с помощью обозревателя объектов**</span><span class="sxs-lookup"><span data-stu-id="aab36-119">**To delete a workload group by using Object Explorer**</span></span>  
  
1.  <span data-ttu-id="aab36-120">В среде[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]откройте обозреватель объектов и рекурсивно разверните узел **Управление** вплоть до узла **Пулы ресурсов**.</span><span class="sxs-lookup"><span data-stu-id="aab36-120">In[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Pools**.</span></span>  
  
2.  <span data-ttu-id="aab36-121">Рекурсивно разверните узел **Пулы ресурсов** вплоть до узла **Группы рабочей нагрузки** в пуле ресурсов, содержащем группу рабочей нагрузки, которая подлежит удалению.</span><span class="sxs-lookup"><span data-stu-id="aab36-121">Recursively expand **Resource Pools** down to and including the **Workload Groups** node in the resource pool that contains the workload group to be deleted.</span></span>  
  
3.  <span data-ttu-id="aab36-122">Правой кнопкой мыши щелкните группу рабочей нагрузки и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="aab36-122">Right-click the workload group, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="aab36-123">В окне **Удаление объекта** эта группа рабочей нагрузки будет указана в списке **Объект для удаления** .</span><span class="sxs-lookup"><span data-stu-id="aab36-123">In the **Delete Object** window, the workload group is listed in the **Object to be deleted** list.</span></span> <span data-ttu-id="aab36-124">Чтобы удалить группу рабочей нагрузки, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="aab36-124">To delete the workload group, click **OK**.</span></span>  
  
##  <a name="delete-a-workload-group-using-resource-governor-properties"></a><a name="DelWGRGProp"></a> <span data-ttu-id="aab36-125">Удаление группы рабочей нагрузки с помощью свойств регулятора ресурсов</span><span class="sxs-lookup"><span data-stu-id="aab36-125">Delete a Workload Group Using Resource Governor Properties</span></span>  
 <span data-ttu-id="aab36-126">**Удаление группы рабочей нагрузки на странице «Свойства регулятора ресурсов»**</span><span class="sxs-lookup"><span data-stu-id="aab36-126">**To delete a workload group by using the Resource Governor Properties page**</span></span>  
  
1.  <span data-ttu-id="aab36-127">В обозревателе объектов разверните узел **Управление** и далее узлы, включая узел **Пулы ресурсов**.</span><span class="sxs-lookup"><span data-stu-id="aab36-127">In Object Explorer, recursively expand the **Management** node down to and including **Resource Pools**.</span></span>  
  
2.  <span data-ttu-id="aab36-128">Щелкните правой кнопкой мыши пул ресурсов, который содержит группу рабочей нагрузки, подлежащую удалению, а затем выберите команду **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="aab36-128">Right-click the resource pool that contains the workload group to be deleted, and then click **Properties**.</span></span> <span data-ttu-id="aab36-129">Открывается страница **Свойства регулятора ресурсов** .</span><span class="sxs-lookup"><span data-stu-id="aab36-129">This opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="aab36-130">В окне **Группы рабочей нагрузки для пула ресурсов** щелкните строку, которая относится к группе рабочей нагрузки, подлежащей удалению, затем щелкните правой кнопкой мыши стрелку вправо в начало строки и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="aab36-130">In the **Workload groups for resource pool** window, click the line for the workload group to be deleted, then right-click the right arrow on the left side of the line, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="aab36-131">Чтобы удалить группу рабочей нагрузки, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="aab36-131">To delete the workload group, click **OK**.</span></span>  
  
##  <a name="delete-a-workload-group-using-transact-sql"></a><a name="DelWGTSQL"></a> <span data-ttu-id="aab36-132">Удаление группы рабочей нагрузки с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aab36-132">Delete a Workload Group Using Transact-SQL</span></span>  
 <span data-ttu-id="aab36-133">**Удаление группы рабочей нагрузки с помощью Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="aab36-133">**To delete a workload group by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="aab36-134">Выполните инструкцию `DROP WORKLOAD GROUP`, указав имя группы рабочей нагрузки, подлежащей удалению.</span><span class="sxs-lookup"><span data-stu-id="aab36-134">Run the `DROP WORKLOAD GROUP` statement specifying the name of the workload group to delete.</span></span>  
  
2.  <span data-ttu-id="aab36-135">Перед выполнением инструкции `ALTER RESOURCE GOVERNOR RECONFIGURE` убедитесь, что в удаляемой группе рабочей нагрузки нет активных запросов.</span><span class="sxs-lookup"><span data-stu-id="aab36-135">Before you issue the `ALTER RESOURCE GOVERNOR RECONFIGURE` statement, verify that there are no active requests in the workload group being deleted.</span></span> <span data-ttu-id="aab36-136">Если активные запросы есть, то инструкция `ALTER RESOURCE GOVERNOR` не будет выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="aab36-136">If there are active requests, `ALTER RESOURCE GOVERNOR` will fail.</span></span> <span data-ttu-id="aab36-137">Во избежание этой ошибки можно предпринять одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="aab36-137">To avoid this issue, you can take one of the following actions:</span></span>  
  
    -   <span data-ttu-id="aab36-138">Дождитесь отсоединения всех сеансов от группы рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="aab36-138">Wait until all the sessions from the workload group have disconnected.</span></span>  
  
    -   <span data-ttu-id="aab36-139">Явным образом остановите сеансы в группе рабочей нагрузки с помощью команды `KILL`.</span><span class="sxs-lookup"><span data-stu-id="aab36-139">Explicitly stop sessions in the workload group by using the `KILL` command.</span></span>  
  
    -   <span data-ttu-id="aab36-140">Перезапустите сервер.</span><span class="sxs-lookup"><span data-stu-id="aab36-140">Restart the server.</span></span> <span data-ttu-id="aab36-141">Группа рабочей нагрузки не будет создана повторно.</span><span class="sxs-lookup"><span data-stu-id="aab36-141">The workload group will not be re-created.</span></span>  
  
    -   <span data-ttu-id="aab36-142">Если при выполнении сценария с инструкцией `DROP WORKLOAD GROUP` решено не останавливать сеанс явным образом для применения изменений, то можно создать группу заново с тем же именем, которое она имела до объявления оператора DROP, а затем переместить группу в исходный пул ресурсов.</span><span class="sxs-lookup"><span data-stu-id="aab36-142">In a scenario in which you have issued the `DROP WORKLOAD GROUP` statement but decide that you do not want to explicitly stop sessions to apply the change, you can re-create the group by using the same name that it had before you issued the DROP statement, and then move the group to the original resource pool.</span></span>  
  
3.  <span data-ttu-id="aab36-143">Выполните `ALTER RESOURCE GOVERNOR RECONFIGURE` инструкцию.</span><span class="sxs-lookup"><span data-stu-id="aab36-143">Run the `ALTER RESOURCE GOVERNOR RECONFIGURE` statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="aab36-144">Пример (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="aab36-144">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="aab36-145">В следующем примере удаляется группа рабочей нагрузки с именем `groupAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="aab36-145">The following example drops a workload group named `groupAdhoc`.</span></span>  
  
```  
DROP WORKLOAD GROUP groupAdhoc;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="aab36-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="aab36-146">See Also</span></span>  
 <span data-ttu-id="aab36-147">[регулятор ресурсов](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="aab36-147">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="aab36-148">[Создание пула ресурсов](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="aab36-148">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="aab36-149">[Создание группы рабочей нагрузки](create-a-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="aab36-149">[Create a Workload Group](create-a-workload-group.md) </span></span>  
 <span data-ttu-id="aab36-150">[Удаление пула ресурсов](delete-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="aab36-150">[Delete a Resource Pool](delete-a-resource-pool.md) </span></span>  
 <span data-ttu-id="aab36-151">[DROP WORKLOAD GROUP (Transact-SQL)](/sql/t-sql/statements/drop-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aab36-151">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="aab36-152">[DROP RESOURCE POOL (Transact-SQL)](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aab36-152">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="aab36-153">ALTER RESOURCE GOVERNOR (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="aab36-153">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
