---
title: Определение логики операций со счетами (мастер бизнес-аналитики) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.acctintelligence.mapaccounttype.f1
ms.assetid: fe4c204b-1031-4ac4-9916-8052ce2301cc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 17b8136e79097cd502d6b239ba6867c4e678c70f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728961"
---
# <a name="define-account-intelligence-business-intelligence-wizard"></a><span data-ttu-id="d87fe-102">Определение логики операций со счетами (мастер бизнес-аналитики)</span><span class="sxs-lookup"><span data-stu-id="d87fe-102">Define Account Intelligence (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="d87fe-103">Используйте страницу **Определение логики операций со счетами** для сопоставления типов записей, определенных в экземпляре служб [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , с типами записей, заданных таблицей-источником в источнике данных, поставляющем данные для измерения счетов.</span><span class="sxs-lookup"><span data-stu-id="d87fe-103">Use the **Define Account Intelligence** page to map account types defined on the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance to account types defined by a source table in the data source that supplies the data for the account dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d87fe-104"> Эта страница появится, если атрибут измерения будет сопоставлен **типу счета** на странице **Настройка атрибутов измерения** .</span><span class="sxs-lookup"><span data-stu-id="d87fe-104">This page will appear if a dimension attribute was mapped to the **Account Type** attribute type on the **Configure Dimension Attributes** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d87fe-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="d87fe-105">Options</span></span>  
 <span data-ttu-id="d87fe-106">**Типы счетов исходной таблицы**</span><span class="sxs-lookup"><span data-stu-id="d87fe-106">**Source Table Account Types**</span></span>  
 <span data-ttu-id="d87fe-107">Отображает значения, которые содержатся в атрибуте измерения, назначенном типу атрибута **Тип счета** на странице **Настройка атрибутов измерения** .</span><span class="sxs-lookup"><span data-stu-id="d87fe-107">Displays the values that are contained in the dimension attribute assigned to the **Account Type** attribute type on the **Configure Dimension Attributes** page.</span></span>  
  
 <span data-ttu-id="d87fe-108">**Встроенные типы счетов**</span><span class="sxs-lookup"><span data-stu-id="d87fe-108">**Built-In Account Types**</span></span>  
 <span data-ttu-id="d87fe-109">Выберите тип счета, определенный в экземпляре служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , который соответствует типам счетов записей таблицы-источника.</span><span class="sxs-lookup"><span data-stu-id="d87fe-109">Select the account type defined on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that maps to the account types in the source table.</span></span>  
  
 <span data-ttu-id="d87fe-110">Следующая таблица содержит список типов счетов, определенных в экземпляре служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d87fe-110">The following table lists the account types that are defined on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span>  
  
|<span data-ttu-id="d87fe-111">Значение</span><span class="sxs-lookup"><span data-stu-id="d87fe-111">Value</span></span>|<span data-ttu-id="d87fe-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d87fe-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d87fe-113">**Ресурс**</span><span class="sxs-lookup"><span data-stu-id="d87fe-113">**Asset**</span></span>|<span data-ttu-id="d87fe-114">Ценность вещей, находящихся в собственности в заданное время.</span><span class="sxs-lookup"><span data-stu-id="d87fe-114">Value of things owned at a specific time.</span></span>|  
|<span data-ttu-id="d87fe-115">**Balance**</span><span class="sxs-lookup"><span data-stu-id="d87fe-115">**Balance**</span></span>|<span data-ttu-id="d87fe-116">Итоговое количество чего-либо в заданное время.</span><span class="sxs-lookup"><span data-stu-id="d87fe-116">Count of something at a specific time.</span></span>|  
|<span data-ttu-id="d87fe-117">**Расход**</span><span class="sxs-lookup"><span data-stu-id="d87fe-117">**Expense**</span></span>|<span data-ttu-id="d87fe-118">Ценность потраченного.</span><span class="sxs-lookup"><span data-stu-id="d87fe-118">Value of things spent.</span></span>|  
|<span data-ttu-id="d87fe-119">**Поток**</span><span class="sxs-lookup"><span data-stu-id="d87fe-119">**Flow**</span></span>|<span data-ttu-id="d87fe-120">Подсчет приращений элементов.</span><span class="sxs-lookup"><span data-stu-id="d87fe-120">Incremental count of things.</span></span>|  
|<span data-ttu-id="d87fe-121">**Доходы**</span><span class="sxs-lookup"><span data-stu-id="d87fe-121">**Income**</span></span>|<span data-ttu-id="d87fe-122">Ценность полученного.</span><span class="sxs-lookup"><span data-stu-id="d87fe-122">Value of things received.</span></span>|  
|<span data-ttu-id="d87fe-123">**Обязательство**</span><span class="sxs-lookup"><span data-stu-id="d87fe-123">**Liability**</span></span>|<span data-ttu-id="d87fe-124">Ценность подлежащего возврату в заданное время.</span><span class="sxs-lookup"><span data-stu-id="d87fe-124">Value of things owed at a specific time.</span></span>|  
|<span data-ttu-id="d87fe-125">**Статистические**</span><span class="sxs-lookup"><span data-stu-id="d87fe-125">**Statistical**</span></span>|<span data-ttu-id="d87fe-126">Вычисленное соотношение или количество некоторой величины, не подлежащей статистической обработке.</span><span class="sxs-lookup"><span data-stu-id="d87fe-126">Calculated ratio of something, or count of something that does not aggregate.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d87fe-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="d87fe-127">See Also</span></span>  
 <span data-ttu-id="d87fe-128">[Справка F1 мастера бизнес-аналитики](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="d87fe-128">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="d87fe-129">[Конструктор кубов &#40;Analysis Services многомерных данных&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="d87fe-129">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="d87fe-130">Конструктор измерений &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="d87fe-130">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
