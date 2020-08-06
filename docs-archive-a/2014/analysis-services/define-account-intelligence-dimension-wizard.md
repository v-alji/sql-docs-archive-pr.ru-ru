---
title: Определение логики операций со счетами (мастер измерений) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.accountintelligencetypemapping.f1
ms.assetid: cbcff072-3a7e-4e98-858f-1b4265461561
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90871e2299d1531db1b678b1f4b16ddd7f1db767
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666271"
---
# <a name="define-account-intelligence-dimension-wizard"></a><span data-ttu-id="9132f-102">Определение логики операций со счетами (мастер измерений)</span><span class="sxs-lookup"><span data-stu-id="9132f-102">Define Account Intelligence (Dimension Wizard)</span></span>
  <span data-ttu-id="9132f-103">Используйте страницу **Определение логики операций со счетами** , чтобы сопоставить типы счетов, определенные в экземпляре служб [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , с типами счетов, определенных в атрибуте измерения, связанном в измерении с типом атрибута **Тип счета** .</span><span class="sxs-lookup"><span data-stu-id="9132f-103">Use the **Define Account Intelligence** page to map account types defined on the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance to account types defined in the dimension attribute associated with the **Account Type** attribute type in the dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9132f-104"> Эта страница отображается, только если был выбран пункт **Стандартное измерение** на странице **Выбор типа измерения** и атрибут измерения был сопоставлен с типом атрибута **Тип счета** на странице **Определение типа измерения** .</span><span class="sxs-lookup"><span data-stu-id="9132f-104">This page is displayed only if you selected **Standard dimension** on the **Select the Dimension Type** page and if you mapped a dimension attribute to the **Account Type** attribute type on the **Specify Dimension Type** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9132f-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="9132f-105">Options</span></span>  
 <span data-ttu-id="9132f-106">**Типы счетов исходной таблицы**</span><span class="sxs-lookup"><span data-stu-id="9132f-106">**Source Table Account Types**</span></span>  
 <span data-ttu-id="9132f-107">Отображает значения, содержащиеся в атрибуте измерения, присвоенном типу атрибута **Тип счета** на странице **Определение ключа и типа измерения** .</span><span class="sxs-lookup"><span data-stu-id="9132f-107">Displays the values contained in the dimension attribute assigned to the **Account Type** attribute type in the **Specify Dimension Key and Type** page.</span></span>  
  
 <span data-ttu-id="9132f-108">**Встроенные типы счетов**</span><span class="sxs-lookup"><span data-stu-id="9132f-108">**Built-In Account Types**</span></span>  
 <span data-ttu-id="9132f-109">Выберите тип счета, определенный в экземпляре служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , который соответствует типам счетов записей таблицы-источника.</span><span class="sxs-lookup"><span data-stu-id="9132f-109">Select the account type defined on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that maps to the account types in the source table.</span></span>  
  
 <span data-ttu-id="9132f-110">Следующая таблица содержит список типов счетов, определенных в экземпляре служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9132f-110">The following table lists the account types that are defined on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span>  
  
|<span data-ttu-id="9132f-111">Значение</span><span class="sxs-lookup"><span data-stu-id="9132f-111">Value</span></span>|<span data-ttu-id="9132f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9132f-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9132f-113">**Ресурс**</span><span class="sxs-lookup"><span data-stu-id="9132f-113">**Asset**</span></span>|<span data-ttu-id="9132f-114">Ценность вещей, находящихся в собственности в заданное время.</span><span class="sxs-lookup"><span data-stu-id="9132f-114">Value of things owned at a specific time.</span></span>|  
|<span data-ttu-id="9132f-115">**Balance**</span><span class="sxs-lookup"><span data-stu-id="9132f-115">**Balance**</span></span>|<span data-ttu-id="9132f-116">Итоговое количество чего-либо в заданное время.</span><span class="sxs-lookup"><span data-stu-id="9132f-116">Count of something at a specific time.</span></span>|  
|<span data-ttu-id="9132f-117">**Расход**</span><span class="sxs-lookup"><span data-stu-id="9132f-117">**Expense**</span></span>|<span data-ttu-id="9132f-118">Ценность потраченного.</span><span class="sxs-lookup"><span data-stu-id="9132f-118">Value of things spent.</span></span>|  
|<span data-ttu-id="9132f-119">**Поток**</span><span class="sxs-lookup"><span data-stu-id="9132f-119">**Flow**</span></span>|<span data-ttu-id="9132f-120">Подсчет приращений элементов.</span><span class="sxs-lookup"><span data-stu-id="9132f-120">Incremental count of things.</span></span>|  
|<span data-ttu-id="9132f-121">**Доходы**</span><span class="sxs-lookup"><span data-stu-id="9132f-121">**Income**</span></span>|<span data-ttu-id="9132f-122">Ценность полученного.</span><span class="sxs-lookup"><span data-stu-id="9132f-122">Value of things received.</span></span>|  
|<span data-ttu-id="9132f-123">**Обязательство**</span><span class="sxs-lookup"><span data-stu-id="9132f-123">**Liability**</span></span>|<span data-ttu-id="9132f-124">Ценность подлежащего возврату в заданное время.</span><span class="sxs-lookup"><span data-stu-id="9132f-124">Value of things owed at a specific time.</span></span>|  
|<span data-ttu-id="9132f-125">**Статистические**</span><span class="sxs-lookup"><span data-stu-id="9132f-125">**Statistical**</span></span>|<span data-ttu-id="9132f-126">Вычисленное соотношение или количество некоторой величины, не подлежащей статистической обработке.</span><span class="sxs-lookup"><span data-stu-id="9132f-126">Calculated ratio of something, or count of something that does not aggregate.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9132f-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="9132f-127">See Also</span></span>  
 <span data-ttu-id="9132f-128">[Справка F1 мастера измерений](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="9132f-128">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="9132f-129">[Измерения &#40;Analysis Services многомерных данных&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="9132f-129">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="9132f-130">Измерения в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="9132f-130">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
