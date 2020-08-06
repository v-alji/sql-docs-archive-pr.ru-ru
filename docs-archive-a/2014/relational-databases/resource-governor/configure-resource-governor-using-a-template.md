---
title: Настройка регулятора ресурсов с помощью шаблона | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, templates
ms.assetid: f342dec2-d1d6-483e-b44e-98eb7d168b5e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 62edb23cf55a953cb0fef54f002f8eaaa16f58ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667685"
---
# <a name="configure-resource-governor-using-a-template"></a><span data-ttu-id="ceb14-102">Настройка регулятора ресурсов с помощью шаблона</span><span class="sxs-lookup"><span data-stu-id="ceb14-102">Configure Resource Governor Using a Template</span></span>
  <span data-ttu-id="ceb14-103">Можно настроить регулятор ресурсов с помощью шаблона, имеющегося в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ceb14-103">You can configure Resource Governor by using a template that is provided in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="ceb14-104">**Перед началом работы**  [Разрешения](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="ceb14-104">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="ceb14-105">**Создание группы рабочей нагрузки с использованием:** [шаблона](#ConfRGTemplate)</span><span class="sxs-lookup"><span data-stu-id="ceb14-105">**To create a workload group, using:**  [a template](#ConfRGTemplate)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ceb14-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="ceb14-106">Before You Begin</span></span>  
 <span data-ttu-id="ceb14-107">С помощью дополнительных шагов можно открыть и изменить шаблон, который создает пул ресурсов и группу рабочей нагрузки для этого пула.</span><span class="sxs-lookup"><span data-stu-id="ceb14-107">Use the following steps to open and modify a template that creates a resource pool and a workload group for the pool.</span></span> <span data-ttu-id="ceb14-108">Кроме того, данный шаблон позволяет создавать определяемую пользователем функцию-классификатор, направляющую новые соединения либо в группу по умолчанию, либо в пользовательскую группу рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="ceb14-108">In addition, this template enables you to create a classifier user-defined function that routes new connections to either the default group or the workload group that you create.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ceb14-109">Permissions</span><span class="sxs-lookup"><span data-stu-id="ceb14-109">Permissions</span></span>  
 <span data-ttu-id="ceb14-110">Для выполнения инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] регулятора ресурсов, содержащихся в шаблоне, требуется разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="ceb14-110">The resource governor [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the template require CONTROL SERVER permission.</span></span>  
  
##  <a name="configure-resource-governor-using-a-template"></a><a name="ConfRGTemplate"></a> <span data-ttu-id="ceb14-111">Настройка регулятора ресурсов с помощью шаблона</span><span class="sxs-lookup"><span data-stu-id="ceb14-111">Configure Resource Governor Using a Template</span></span>  
 <span data-ttu-id="ceb14-112">**Настройка регулятора ресурсов с помощью шаблона в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="ceb14-112">**To configure resource governor by using a template in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="ceb14-113">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]в меню **Вид** выберите пункт **Обозреватель шаблонов**.</span><span class="sxs-lookup"><span data-stu-id="ceb14-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="ceb14-114">В **Обозревателе шаблонов**разверните **Регулятор ресурсов**, затем дважды щелкните значок **Настройка регулятора ресурсов**.</span><span class="sxs-lookup"><span data-stu-id="ceb14-114">In **Template Explorer**, expand **Resource Governor**, and then double-click **Configure Resource Governor**.</span></span>  
  
3.  <span data-ttu-id="ceb14-115">В разделе **Подключение к компоненту Database Engine**введите необходимые сведения и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ceb14-115">In **Connect to Database Engine**, enter the required information, and then click **OK**.</span></span> <span data-ttu-id="ceb14-116">В составе редактора запросов поставляется шаблон Configure Resource Governor.sql.</span><span class="sxs-lookup"><span data-stu-id="ceb14-116">The template Configure Resource Governor.sql is provided in the Query Editor.</span></span> <span data-ttu-id="ceb14-117">С помощью этого шаблона можно создать и настроить пул ресурсов, группу рабочей нагрузки и функцию-классификатор.</span><span class="sxs-lookup"><span data-stu-id="ceb14-117">Use this template to create and configure a resource pool, a workload group, and a classifier function.</span></span>  
  
4.  <span data-ttu-id="ceb14-118">Чтобы изменить значения в шаблоне, нажмите сочетание клавиш CTRL+SHIFT+M.</span><span class="sxs-lookup"><span data-stu-id="ceb14-118">To change the values in the template, press CTRL+SHIFT+M.</span></span> <span data-ttu-id="ceb14-119">В окне **Задание значений для параметров шаблона** введите необходимые значения.</span><span class="sxs-lookup"><span data-stu-id="ceb14-119">In the **Specify Values for Template Parameters** window, enter the values that you want to use.</span></span>  
  
5.  <span data-ttu-id="ceb14-120">Чтобы сохранить изменения, внесенные в шаблон, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ceb14-120">To save the changes that you make to the template, click **OK**.</span></span>  
  
6.  <span data-ttu-id="ceb14-121">Чтобы запустить запрос, нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="ceb14-121">To run the query, click **Execute**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceb14-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="ceb14-122">See Also</span></span>  
 <span data-ttu-id="ceb14-123">[регулятор ресурсов](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="ceb14-123">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="ceb14-124">[Активация регулятора ресурсов](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="ceb14-124">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="ceb14-125">[Пул ресурсов регулятора ресурсов](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="ceb14-125">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="ceb14-126">[Группа рабочей нагрузки регулятора ресурсов](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="ceb14-126">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="ceb14-127">[Функция-классификатор регулятора ресурсов](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="ceb14-127">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="ceb14-128">[Просмотр свойств регулятора ресурсов](view-resource-governor-properties.md) </span><span class="sxs-lookup"><span data-stu-id="ceb14-128">[View Resource Governor Properties](view-resource-governor-properties.md) </span></span>  
 <span data-ttu-id="ceb14-129">[CREATE RESOURCE POOL (Transact-SQL)](/sql/t-sql/statements/create-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ceb14-129">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="ceb14-130">[CREATE WORKLOAD GROUP (Transact-SQL)](/sql/t-sql/statements/create-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ceb14-130">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="ceb14-131">[CREATE FUNCTION (Transact-SQL)](/sql/t-sql/statements/create-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ceb14-131">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span></span>  
 [<span data-ttu-id="ceb14-132">ALTER RESOURCE GOVERNOR (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ceb14-132">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
