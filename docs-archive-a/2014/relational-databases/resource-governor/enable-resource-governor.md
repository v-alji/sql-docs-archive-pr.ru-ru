---
title: Включение регулятора ресурсов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, enabling
ms.assetid: 4d17af53-cf11-4ce4-aab4-deda94a49836
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7b1b0f780457aa5a4d26cbb463c9f31a94185f0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731473"
---
# <a name="enable-resource-governor"></a><span data-ttu-id="08ed1-102">Активация регулятора ресурсов</span><span class="sxs-lookup"><span data-stu-id="08ed1-102">Enable Resource Governor</span></span>
  <span data-ttu-id="08ed1-103">Регулятор ресурсов отключен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08ed1-103">The Resource Governor is turned off by default.</span></span> <span data-ttu-id="08ed1-104">Регулятор ресурсов можно включить с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="08ed1-104">You can enable the Resource Governor by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="08ed1-105">**Перед началом работы**  [ограничения](#LimitationsRestrictions), [разрешения](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="08ed1-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="08ed1-106">**Включение Resource Governor с использованием:**  [обозревателя объектов](#RGOnObjEx), [свойств Resource Governor](#RGOnProp), [Transact-SQL](#RGOnTSQL)</span><span class="sxs-lookup"><span data-stu-id="08ed1-106">**To enable Resource Governorn, using:**  [Object Explorer](#RGOnObjEx), [Resource Governor Properties](#RGOnProp), [Transact-SQL](#RGOnTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="08ed1-107">Перед началом</span><span class="sxs-lookup"><span data-stu-id="08ed1-107">Before You Begin</span></span>  
 <span data-ttu-id="08ed1-108">В результате включения регулятора ресурсов произойдет следующее.</span><span class="sxs-lookup"><span data-stu-id="08ed1-108">Enabling the resource governor has the following results:</span></span>  
  
-   <span data-ttu-id="08ed1-109">Будет выполнена функция-классификатор для новых соединений, что позволит связать их рабочую нагрузку с определенными группами рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="08ed1-109">The classifier function is run for new connections so that their workloads can be assigned to workload groups.</span></span>  
  
-   <span data-ttu-id="08ed1-110">Ограничения ресурсов, заданные в конфигурации регулятора ресурсов, будут соблюдены и применены.</span><span class="sxs-lookup"><span data-stu-id="08ed1-110">The resource limits that are specified in the Resource Governor configuration are honored and enforced.</span></span>  
  
-   <span data-ttu-id="08ed1-111">Запросы, которые существовали до включения регулятора ресурсов, будут испытывать воздействие всех изменений конфигурации, которые были внесены, пока регулятор ресурсов был отключен.</span><span class="sxs-lookup"><span data-stu-id="08ed1-111">Requests that existed before enabling Resource Governor are affected by any configuration changes that were made when the Resource Governor was disabled.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="08ed1-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="08ed1-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="08ed1-113">В ходе пользовательской транзакции нельзя использовать инструкцию `ALTER RESOURCE GOVERNOR` для включения регулятора ресурсов.</span><span class="sxs-lookup"><span data-stu-id="08ed1-113">You cannot use the `ALTER RESOURCE GOVERNOR` statement to enable Resource Governor when in a user transaction.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="08ed1-114">Permissions</span><span class="sxs-lookup"><span data-stu-id="08ed1-114">Permissions</span></span>  
 <span data-ttu-id="08ed1-115">Для включения регулятора ресурсов требуется разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="08ed1-115">Enabling the Resource Governor requires CONTROL SERVER permission.</span></span>  
  
##  <a name="enable-resource-governor-using-object-explorer"></a><a name="RGOnObjEx"></a> <span data-ttu-id="08ed1-116">Включение регулятора ресурсов с использованием обозревателя объектов</span><span class="sxs-lookup"><span data-stu-id="08ed1-116">Enable Resource Governor Using Object Explorer</span></span>  
 <span data-ttu-id="08ed1-117">**Включение регулятора ресурсов с помощью обозревателя объектов**</span><span class="sxs-lookup"><span data-stu-id="08ed1-117">**To enable the Resource Governor by using Object Explorer**</span></span>  
  
1.  <span data-ttu-id="08ed1-118">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]откройте обозреватель объектов и рекурсивно разверните узел **Управление** вплоть до узла **Регулятор ресурсов**.</span><span class="sxs-lookup"><span data-stu-id="08ed1-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="08ed1-119">Щелкните элемент **Resource Governor**правой кнопкой мыши и выберите команду **Включить**.</span><span class="sxs-lookup"><span data-stu-id="08ed1-119">Right-click **Resource Governor**, and then click **Enable**.</span></span>  
  
##  <a name="enable-resource-governor-using-resource-governor-properties"></a><a name="RGOnProp"></a> <span data-ttu-id="08ed1-120">Включение регулятора ресурсов с применением свойств регулятора ресурсов</span><span class="sxs-lookup"><span data-stu-id="08ed1-120">Enable Resource Governor Using Resource Governor Properties</span></span>  
 <span data-ttu-id="08ed1-121">**Включение регулятора ресурсов с использованием страницы свойств регулятора ресурсов**</span><span class="sxs-lookup"><span data-stu-id="08ed1-121">**To enable the Resource Governor by using the Resource Governor Properties page**</span></span>  
  
1.  <span data-ttu-id="08ed1-122">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]откройте обозреватель объектов и рекурсивно разверните узел **Управление** вплоть до узла **Регулятор ресурсов**.</span><span class="sxs-lookup"><span data-stu-id="08ed1-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="08ed1-123">Щелкните правой кнопкой мыши **Регулятор ресурсов** и выберите пункт **Свойства**, после чего откроется страница **Свойства регулятора ресурсов** .</span><span class="sxs-lookup"><span data-stu-id="08ed1-123">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="08ed1-124">Установите флажок **Включить регулятор ресурсов** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="08ed1-124">Click the **Enable Resource Governor** check box, and then click **OK**.</span></span>  
  
##  <a name="enable-resource-governor-using-transact-sql"></a><a name="RGOnTSQL"></a> <span data-ttu-id="08ed1-125">Включение регулятора ресурсов с применением Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="08ed1-125">Enable Resource Governor Using Transact-SQL</span></span>  
 <span data-ttu-id="08ed1-126">**Включение регулятора ресурсов с применением Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="08ed1-126">**To enable the Resource Governor by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="08ed1-127">Выполните инструкцию **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="08ed1-127">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="08ed1-128">Пример (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="08ed1-128">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="08ed1-129">В следующем примере показано включение регулятора ресурсов.</span><span class="sxs-lookup"><span data-stu-id="08ed1-129">The following example enables the Resource Governor.</span></span>  
  
```  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="08ed1-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="08ed1-130">See Also</span></span>  
 <span data-ttu-id="08ed1-131">[регулятор ресурсов](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="08ed1-131">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="08ed1-132">[Отключение регулятора ресурсов](disable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="08ed1-132">[Disable Resource Governor](disable-resource-governor.md) </span></span>  
 <span data-ttu-id="08ed1-133">[Пул ресурсов регулятора ресурсов](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="08ed1-133">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="08ed1-134">[Группа рабочей нагрузки регулятора ресурсов](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="08ed1-134">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="08ed1-135">[Функция-классификатор регулятора ресурсов](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="08ed1-135">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 [<span data-ttu-id="08ed1-136">ALTER RESOURCE GOVERNOR (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="08ed1-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
