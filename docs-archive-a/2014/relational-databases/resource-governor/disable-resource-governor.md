---
title: Отключение регулятора ресурсов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, disabling
ms.assetid: 2c2d2db0-34a5-4f50-b783-17693e3ce3f1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 172f01bdde0f792cd9ed72ad371e5811b8de8885
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731477"
---
# <a name="disable-resource-governor"></a><span data-ttu-id="789b6-102">Отключение регулятора ресурсов</span><span class="sxs-lookup"><span data-stu-id="789b6-102">Disable Resource Governor</span></span>
  <span data-ttu-id="789b6-103">Регулятор ресурсов можно отключить в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или с помощью Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="789b6-103">You can disable the Resource Governor by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="789b6-104">**Перед началом работы**  [ограничения](#LimitationsRestrictions), [разрешения](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="789b6-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="789b6-105">**Отключение Resource Governor с использованием:**  [обозревателя объектов](#RGOffObjEx), [свойств Resource Governor](#RGOffProp), [Transact-SQL](#RGOffTSQL)</span><span class="sxs-lookup"><span data-stu-id="789b6-105">**To disable Resource Governorn, using:**  [Object Explorer](#RGOffObjEx), [Resource Governor Properties](#RGOffProp), [Transact-SQL](#RGOffTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="789b6-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="789b6-106">Before You Begin</span></span>  
 <span data-ttu-id="789b6-107">В результате отключения регулятора ресурсов происходит следующее.</span><span class="sxs-lookup"><span data-stu-id="789b6-107">Disabling the Resource Governor has the following results:</span></span>  
  
-   <span data-ttu-id="789b6-108">Функция-классификатор не выполняется.</span><span class="sxs-lookup"><span data-stu-id="789b6-108">The classifier function is not run.</span></span>  
  
-   <span data-ttu-id="789b6-109">Все новые соединения в результате классификации автоматически попадают в группу рабочей нагрузки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="789b6-109">All new connections are automatically classified into the default workload group.</span></span>  
  
-   <span data-ttu-id="789b6-110">Инициированные системой запросы попадают во внутреннюю группу рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="789b6-110">System-initiated requests are classified into the internal workload group.</span></span>  
  
-   <span data-ttu-id="789b6-111">Все существующие параметры групп рабочей нагрузки и пулов ресурсов сбрасываются в значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="789b6-111">All existing workload group and resource pool settings are reset to their default values.</span></span> <span data-ttu-id="789b6-112">В этом случае при достижении ограничений не возникает никаких событий.</span><span class="sxs-lookup"><span data-stu-id="789b6-112">In this case, no events are fired when limits are reached.</span></span>  
  
-   <span data-ttu-id="789b6-113">Обычное наблюдение за системой не затрагивается.</span><span class="sxs-lookup"><span data-stu-id="789b6-113">Normal system monitoring is not affected.</span></span>  
  
-   <span data-ttu-id="789b6-114">Изменения конфигурации можно вносить, но эти изменения не вступят в силу, пока не будет включен регулятор ресурсов.</span><span class="sxs-lookup"><span data-stu-id="789b6-114">Configuration changes can be made, but the changes do not take effect until the Resource Governor is enabled.</span></span>  
  
-   <span data-ttu-id="789b6-115">После перезапуска SQL Server регулятор ресурсов не будет загружать конфигурацию, а вместо этого будет иметь только применяемые по умолчанию внутренние группы рабочей нагрузки и пулы ресурсов.</span><span class="sxs-lookup"><span data-stu-id="789b6-115">Upon restarting SQL Server, the Resource Governor will not load its configuration, but instead will have only the default and internal workload groups and resource pools.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="789b6-116">Ограничения</span><span class="sxs-lookup"><span data-stu-id="789b6-116">Limitations and Restrictions</span></span>  
 <span data-ttu-id="789b6-117">В пользовательской транзакции регулятор ресурсов нельзя отключить с помощью инструкции `ALTER RESOURCE GOVERNOR`.</span><span class="sxs-lookup"><span data-stu-id="789b6-117">You cannot use the `ALTER RESOURCE GOVERNOR` statement to disable Resource Governor when in a user transaction.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="789b6-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="789b6-118">Permissions</span></span>  
 <span data-ttu-id="789b6-119">Для отключения регулятора ресурсов требуется разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="789b6-119">Disabling the Resource Governor requires CONTROL SERVER permission.</span></span>  
  
##  <a name="disable-resource-governor-using-object-explorer"></a><a name="RGOffObjEx"></a> <span data-ttu-id="789b6-120">Отключение регулятора ресурсов с помощью обозревателя объектов</span><span class="sxs-lookup"><span data-stu-id="789b6-120">Disable Resource Governor Using Object Explorer</span></span>  
 <span data-ttu-id="789b6-121">**Отключение регулятора ресурсов с помощью обозревателя объектов**</span><span class="sxs-lookup"><span data-stu-id="789b6-121">**To disable the Resource Governor by using Object Explorer**</span></span>  
  
1.  <span data-ttu-id="789b6-122">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]откройте обозреватель объектов и рекурсивно разверните узел **Управление** вплоть до узла **Регулятор ресурсов**.</span><span class="sxs-lookup"><span data-stu-id="789b6-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="789b6-123">Щелкните элемент **Resource Governor**правой кнопкой мыши и выберите команду **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="789b6-123">Right-click **Resource Governor**, and then click **Disable**.</span></span>  
  
##  <a name="disable-resource-governor-using-resource-governor-properties"></a><a name="RGOffProp"></a> <span data-ttu-id="789b6-124">Отключение регулятора ресурсов с помощью свойств регулятора ресурсов</span><span class="sxs-lookup"><span data-stu-id="789b6-124">Disable Resource Governor Using Resource Governor Properties</span></span>  
 <span data-ttu-id="789b6-125">**Отключение регулятора ресурсов с помощью страницы «Свойства регулятора ресурсов»**</span><span class="sxs-lookup"><span data-stu-id="789b6-125">**To disable the Resource Governor by using the Resource Governor Properties page**</span></span>  
  
1.  <span data-ttu-id="789b6-126">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]откройте обозреватель объектов и рекурсивно разверните узел **Управление** вплоть до узла **Регулятор ресурсов**.</span><span class="sxs-lookup"><span data-stu-id="789b6-126">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="789b6-127">Щелкните правой кнопкой мыши **Регулятор ресурсов** и выберите пункт **Свойства**, после чего откроется страница **Свойства регулятора ресурсов** .</span><span class="sxs-lookup"><span data-stu-id="789b6-127">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="789b6-128">Щелкните флажок **Включить регулятор ресурсов** , убедитесь в том, что этот флажок не выбран, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="789b6-128">Click the **Enable Resource Governor** check box, ensure that the box is not selected, and then click **OK**.</span></span>  
  
##  <a name="disable-resource-governor-using-transact-sql"></a><a name="RGOffTSQL"></a> <span data-ttu-id="789b6-129">Отключение регулятора ресурсов с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="789b6-129">Disable Resource Governor Using Transact-SQL</span></span>  
 <span data-ttu-id="789b6-130">**Отключение регулятора ресурсов с помощью Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="789b6-130">**To disable the Resource Governor by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="789b6-131">Выполните инструкцию **ALTER RESOURCE GOVERNOR DISABLE** .</span><span class="sxs-lookup"><span data-stu-id="789b6-131">Run the **ALTER RESOURCE GOVERNOR DISABLE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="789b6-132">Пример (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="789b6-132">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="789b6-133">В следующем примере показано включение регулятора ресурсов.</span><span class="sxs-lookup"><span data-stu-id="789b6-133">The following example enables the Resource Governor.</span></span>  
  
```  
ALTER RESOURCE GOVERNOR DISABLE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="789b6-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="789b6-134">See Also</span></span>  
 <span data-ttu-id="789b6-135">[регулятор ресурсов](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="789b6-135">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="789b6-136">[Активация регулятора ресурсов](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="789b6-136">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="789b6-137">[Пул ресурсов регулятора ресурсов](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="789b6-137">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="789b6-138">[Группа рабочей нагрузки регулятора ресурсов](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="789b6-138">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="789b6-139">[Функция-классификатор регулятора ресурсов](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="789b6-139">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 [<span data-ttu-id="789b6-140">ALTER RESOURCE GOVERNOR (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="789b6-140">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
