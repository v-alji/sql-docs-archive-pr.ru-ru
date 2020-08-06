---
title: Создание группы рабочей нагрузки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, workload group create
- workload groups [SQL Server], create
ms.assetid: 072868ec-ceff-4db6-941b-281af731a067
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 144bcef57b3d6e191b03b1539e9e7382a9085c93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658186"
---
# <a name="create-a-workload-group"></a><span data-ttu-id="eea23-102">Создание группы рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="eea23-102">Create a Workload Group</span></span>
  <span data-ttu-id="eea23-103">Группы рабочей нагрузки можно создавать в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eea23-103">You can create a workload group by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="eea23-104">**Перед началом работы**  [ограничения](#LimitationsRestrictions), [разрешения](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="eea23-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="eea23-105">**Создание группы рабочей нагрузки с использованием:**  [среды SQL Server Management Studio](#CreWGProp), [Transact-SQL](#CreWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="eea23-105">**To create a workload group, using:**  [SQL Server Management Studio](#CreWGProp), [Transact-SQL](#CreWGTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="eea23-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="eea23-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="eea23-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="eea23-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="eea23-108">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span><span class="sxs-lookup"><span data-stu-id="eea23-108">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span></span>  
  
 <span data-ttu-id="eea23-109">Объем памяти, затрачиваемой на создание индекса в невыровненной секционированной таблице, пропорционален количеству секций, охватываемых индексом.</span><span class="sxs-lookup"><span data-stu-id="eea23-109">The memory consumed by index creation on a non-aligned partitioned table is proportional to the number of partitions involved.</span></span> <span data-ttu-id="eea23-110">Если общий объем необходимой памяти превышает лимит для каждого запроса (REQUEST_MAX_MEMORY_GRANT_PERCENT), установленный параметром для группы рабочей нагрузки, то создание этого индекса может завершиться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="eea23-110">If the total required memory exceeds the per-query limit, (REQUEST_MAX_MEMORY_GRANT_PERCENT) imposed by the workload group setting, this index creation may fail.</span></span> <span data-ttu-id="eea23-111">Для обеспечения совместимости с версией SQL Server 2005 группа рабочей нагрузки по умолчанию позволяет запросу превысить лимит для каждого запроса с учетом минимального объема памяти, необходимого при запуске, поэтому пользователь может запустить тот же процесс создания индекса в группе рабочей нагрузки по умолчанию, если в пуле ресурсов по умолчанию достаточно памяти, настроенной для выполнения такого запроса.</span><span class="sxs-lookup"><span data-stu-id="eea23-111">Because the default workload group allows a query to exceed the per-query limit with the minimum required memory to start for SQL Server 2005 compatibility, the user may be able to run the same index creation in the default workload group, if the default resource pool has enough total memory configured to run such a query.</span></span>  
  
 <span data-ttu-id="eea23-112">Разрешено создание индексов для использования большего объема памяти рабочей области, чем было указано изначально, в целях повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="eea23-112">Index creation is allowed to use more memory workspace than initially granted for performance.</span></span> <span data-ttu-id="eea23-113">Эта специальная обработка поддерживается регулятором ресурсов, однако изначально предоставленная память и любая дополнительная выделенная память ограничены настройками группы рабочей нагрузки и пула ресурсов.</span><span class="sxs-lookup"><span data-stu-id="eea23-113">This special handling is supported by Resource Governor, however, the initial grant and any additional memory grant are limited by the workload group and resource pool settings.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="eea23-114">Permissions</span><span class="sxs-lookup"><span data-stu-id="eea23-114">Permissions</span></span>  
 <span data-ttu-id="eea23-115">Для создания группы рабочей нагрузки требуется разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="eea23-115">Creating a workload group requires CONTROL SERVER permission.</span></span>  
  
##  <a name="create-a-workload-group-using-sql-server-management-studio"></a><a name="CreWGProp"></a> <span data-ttu-id="eea23-116">Создание группы рабочей нагрузки в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eea23-116">Create a Workload Group Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="eea23-117">**Создание группы рабочей нагрузки с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="eea23-117">**To create a workload group by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="eea23-118">В обозревателе объектов рекурсивно разверните узел **Управление** вплоть до узла «Пул ресурсов», содержащего группу рабочей нагрузки, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="eea23-118">In Object Explorer, recursively expand the **Management** node down to and including the resource pool that contains the workload group to be modified.</span></span>  
  
2.  <span data-ttu-id="eea23-119">Щелкните правой кнопкой мыши папку **Группы рабочей нагрузки** и выберите команду **Создать группу рабочей нагрузки**.</span><span class="sxs-lookup"><span data-stu-id="eea23-119">Right-click the **Workload Groups** folder, and then click **New Workload Group**.</span></span>  
  
3.  <span data-ttu-id="eea23-120">Убедитесь в том, что в сетке **Пулы ресурсов** выделен подсветкой пул ресурсов, в который должна быть добавлена группа рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="eea23-120">In the **Resource pools** grid, ensure the resource pool where you want to add the workload group is highlighted.</span></span>  
  
4.  <span data-ttu-id="eea23-121">В сетке **Группы рабочей нагрузки для пула ресурсов** будет присутствовать новая строка с пустым именем и значениями по умолчанию в других столбцах.</span><span class="sxs-lookup"><span data-stu-id="eea23-121">The **Workload groups for resource pool** grid will have a new line with a blank name and default values in the other columns.</span></span>  
  
5.  <span data-ttu-id="eea23-122">Щелкните ячейку **Имя** и введите имя для группы рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="eea23-122">Click the **Name** cell and enter a name for the workload group.</span></span>  
  
6.  <span data-ttu-id="eea23-123">Щелкните или дважды щелкните все прочие ячейки в строке, для которых необходимо задать параметры, отличные от применяемых по умолчанию, и введите новые значения.</span><span class="sxs-lookup"><span data-stu-id="eea23-123">Click or double-click any other cells in the row you want to change from their default settings, and enter the new values.</span></span>  
  
7.  <span data-ttu-id="eea23-124">Чтобы сохранить изменения, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eea23-124">To save the changes, click **OK**</span></span>  
  
##  <a name="create-a-workload-group-using-transact-sql"></a><a name="CreWGTSQL"></a> <span data-ttu-id="eea23-125">Создание группы рабочей нагрузки с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eea23-125">Create a Workload Group Using Transact-SQL</span></span>  
 <span data-ttu-id="eea23-126">**Создание группы рабочей нагрузки с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="eea23-126">**To create a workload group by using [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span></span>  
  
1.  <span data-ttu-id="eea23-127">Выполните инструкцию CREATE WORKLOAD GROUP, указав значения свойств, которые необходимо установить.</span><span class="sxs-lookup"><span data-stu-id="eea23-127">Run the CREATE WORKLOAD GROUP statement specifying the property values to be set.</span></span>  
  
2.  <span data-ttu-id="eea23-128">Выполните инструкцию ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="eea23-128">Run the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="eea23-129">Пример (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="eea23-129">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="eea23-130">В следующем примере создается группа рабочей нагрузки с именем `groupAdhoc` , которая находится в пуле ресурсов с именем `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="eea23-130">The following example creates a workload group named `groupAdhoc` in the resource pool named `poolAdhoc`.</span></span>  
  
```  
CREATE WORKLOAD GROUP groupAdhoc  
USING poolAdhoc;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="eea23-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="eea23-131">See Also</span></span>  
 <span data-ttu-id="eea23-132">[регулятор ресурсов](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="eea23-132">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="eea23-133">[Активация регулятора ресурсов](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="eea23-133">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="eea23-134">[Создание пула ресурсов](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="eea23-134">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="eea23-135">[Изменение параметров группы рабочей нагрузки](change-workload-group-settings.md) </span><span class="sxs-lookup"><span data-stu-id="eea23-135">[Change Workload Group Settings](change-workload-group-settings.md) </span></span>  
 <span data-ttu-id="eea23-136">[Создание и проверка определяемой пользователем функции-классификатора](create-and-test-a-classifier-user-defined-function.md) </span><span class="sxs-lookup"><span data-stu-id="eea23-136">[Create and Test a Classifier User-Defined Function](create-and-test-a-classifier-user-defined-function.md) </span></span>  
 <span data-ttu-id="eea23-137">[CREATE WORKLOAD GROUP (Transact-SQL)](/sql/t-sql/statements/create-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="eea23-137">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span></span>  
 [<span data-ttu-id="eea23-138">ALTER RESOURCE GOVERNOR (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="eea23-138">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
