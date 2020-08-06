---
title: Изменение параметров группы рабочей нагрузки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- workload groups [SQL Server], alter
- Resource Governor, workload group alter
ms.assetid: 73b6109c-2ad0-4915-b11b-d40d5a0fdc25
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 579aad71d32a629d75f1eecd76e7dacfe32d94f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654141"
---
# <a name="change-workload-group-settings"></a><span data-ttu-id="ac6eb-102">Изменение параметров группы рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="ac6eb-102">Change Workload Group Settings</span></span>
  <span data-ttu-id="ac6eb-103">Параметры группы рабочей нагрузки можно изменить с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac6eb-103">You can change workload group settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="ac6eb-104">**Перед началом работы**  [ограничения](#LimitationsRestrictions), [разрешения](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="ac6eb-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="ac6eb-105">**Изменение параметров для группы рабочей нагрузки с использованием:**  [среды SQL Server Management Studio](#ChgWGProp), [Transact-SQL](#ChgWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="ac6eb-105">**To change the settings for a workload group, using:**  [SQL Server Management Studio](#ChgWGProp), [Transact-SQL](#ChgWGTSQL)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="ac6eb-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="ac6eb-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="ac6eb-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="ac6eb-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="ac6eb-108">Можно изменить параметры группы рабочей нагрузки по умолчанию и групп рабочей нагрузки, определяемых пользователем.</span><span class="sxs-lookup"><span data-stu-id="ac6eb-108">You can change the settings of the default workload group and user-defined workload groups.</span></span>  
  
 <span data-ttu-id="ac6eb-109">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span><span class="sxs-lookup"><span data-stu-id="ac6eb-109">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span></span>  
  
 <span data-ttu-id="ac6eb-110">Объем памяти, затрачиваемой на создание индекса в невыровненной секционированной таблице, пропорционален количеству секций, охватываемых индексом.</span><span class="sxs-lookup"><span data-stu-id="ac6eb-110">The memory consumed by index creation on a non-aligned partitioned table is proportional to the number of partitions involved.</span></span> <span data-ttu-id="ac6eb-111">Если общий объем необходимой памяти превышает лимит для каждого запроса (REQUEST_MAX_MEMORY_GRANT_PERCENT), установленный параметром для группы рабочей нагрузки, то создание этого индекса может завершиться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ac6eb-111">If the total required memory exceeds the per-query limit, (REQUEST_MAX_MEMORY_GRANT_PERCENT) imposed by the workload group setting, this index creation may fail.</span></span> <span data-ttu-id="ac6eb-112">Для обеспечения совместимости с версией SQL Server 2005 группа рабочей нагрузки по умолчанию позволяет запросу превысить лимит для каждого запроса с учетом минимального объема памяти, необходимого при запуске, поэтому пользователь может запустить тот же процесс создания индекса в группе рабочей нагрузки по умолчанию, если в пуле ресурсов по умолчанию достаточно памяти, настроенной для выполнения такого запроса.</span><span class="sxs-lookup"><span data-stu-id="ac6eb-112">Because the default workload group allows a query to exceed the per-query limit with the minimum required memory to start for SQL Server 2005 compatibility, the user may be able to run the same index creation in the default workload group, if the default resource pool has enough total memory configured to run such a query.</span></span>  
  
 <span data-ttu-id="ac6eb-113">Разрешено создание индексов для использования большего объема памяти рабочей области, чем было указано изначально, в целях повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="ac6eb-113">Index creation is allowed to use more memory workspace than initially granted for performance.</span></span> <span data-ttu-id="ac6eb-114">Эта специальная обработка поддерживается регулятором ресурсов, однако изначально предоставленная память и любая дополнительная выделенная память ограничены настройками группы рабочей нагрузки и пула ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ac6eb-114">This special handling is supported by Resource Governor, however, the initial grant and any additional memory grant are limited by the workload group and resource pool settings.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ac6eb-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="ac6eb-115">Permissions</span></span>  
 <span data-ttu-id="ac6eb-116">Для изменения параметров группы рабочей нагрузки требуется разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="ac6eb-116">Changing workload group settings requires CONTROL SERVER permission.</span></span>  
  
##  <a name="change-workload-group-settings-using-sql-server-management-studio"></a><a name="ChgWGProp"></a> <span data-ttu-id="ac6eb-117">Изменение параметров группы рабочей нагрузки с использованием среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ac6eb-117">Change Workload Group Settings Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="ac6eb-118">**Изменение параметров группы рабочей нагрузки с использованием среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="ac6eb-118">**To change workload group settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="ac6eb-119">В обозревателе объектов рекурсивно разверните узел **Управление** вплоть до и включая папку **Группы рабочей нагрузки** , которая включает группу рабочей нагрузки, подлежащую изменению.</span><span class="sxs-lookup"><span data-stu-id="ac6eb-119">In Object Explorer, recursively expand the **Management** node down to and including the **Workload Groups** folder that contains the workload group to be modified.</span></span>  
  
2.  <span data-ttu-id="ac6eb-120">Щелкните правой кнопкой мыши группу рабочей нагрузки, подлежащую изменению, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ac6eb-120">Right-click the workload group to be modified, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="ac6eb-121">На странице **Свойства регулятора ресурсов** выберите строку для группы рабочей нагрузки в сетке **Группы рабочей нагрузки для пула ресурсов** , если она не выделена автоматически.</span><span class="sxs-lookup"><span data-stu-id="ac6eb-121">In the **Resource Governor Properties** page, select the row for the workload group in the **Workload groups for resource pool** grid if it is not automatically selected.</span></span>  
  
4.  <span data-ttu-id="ac6eb-122">Щелкните или дважды щелкните ячейки в строке, подлежащие изменению, и введите новые значения.</span><span class="sxs-lookup"><span data-stu-id="ac6eb-122">Click or double-click the cells in the row to be changed, and enter the new values.</span></span>  
  
5.  <span data-ttu-id="ac6eb-123">Чтобы сохранить изменения, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ac6eb-123">To save the changes, click **OK**</span></span>  
  
##  <a name="change-workload-group-settings-using-transact-sql"></a><a name="ChgWGTSQL"></a> <span data-ttu-id="ac6eb-124">Изменение параметров группы рабочей нагрузки с использованием Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ac6eb-124">Change Workload Group Settings Using Transact-SQL</span></span>  
 <span data-ttu-id="ac6eb-125">**Изменение параметров группы рабочей нагрузки с использованием Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ac6eb-125">**To change workload group settings by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="ac6eb-126">Выполните инструкцию ALTER WORKLOAD GROUP, указав значения свойств, которые необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="ac6eb-126">Run the ALTER WORKLOAD GROUP statement specifying the property values to be changed.</span></span>  
  
2.  <span data-ttu-id="ac6eb-127">Выполните инструкцию ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="ac6eb-127">Run the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="ac6eb-128">Пример (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ac6eb-128">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="ac6eb-129">В следующем примере изменяется значение параметра максимального объема выделенной памяти в процентах для группы рабочей нагрузки с именем `groupAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="ac6eb-129">The following example changes the max memory grant percent setting for the workload group named `groupAdhoc`.</span></span>  
  
```  
ALTER WORKLOAD GROUP groupAdhoc  
WITH (REQUEST_MAX_MEMORY_GRANT_PERCENT = 30);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac6eb-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="ac6eb-130">See Also</span></span>  
 <span data-ttu-id="ac6eb-131">[регулятор ресурсов](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="ac6eb-131">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="ac6eb-132">[Создание группы рабочей нагрузки](create-a-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="ac6eb-132">[Create a Workload Group](create-a-workload-group.md) </span></span>  
 <span data-ttu-id="ac6eb-133">[Создание пула ресурсов](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="ac6eb-133">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="ac6eb-134">[Изменение параметров пула ресурсов](change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="ac6eb-134">[Change Resource Pool Settings](change-resource-pool-settings.md) </span></span>  
 <span data-ttu-id="ac6eb-135">[ALTER WORKLOAD GROUP (Transact-SQL)](/sql/t-sql/statements/alter-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ac6eb-135">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="ac6eb-136">[ALTER RESOURCE POOL (Transact-SQL)](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ac6eb-136">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="ac6eb-137">ALTER RESOURCE GOVERNOR (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ac6eb-137">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
