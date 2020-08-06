---
title: Выбор участников (мастер бизнес-аналитики) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.currencyconversion.memberconversion.f1
ms.assetid: 1a147461-d594-41e7-a41d-09d2d003e1e0
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd5f184e0d9670725609531b6d0a101f8e7f8647
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657341"
---
# <a name="select-members-business-intelligence-wizard"></a><span data-ttu-id="1004b-102">Выбор элементов (мастер бизнес-аналитики)</span><span class="sxs-lookup"><span data-stu-id="1004b-102">Select Members (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="1004b-103">Страница **Выбор элементов** определяет, к каким элементам мастер бизнес-аналитики должен применять функции конвертирования валют, указанные на странице **Установка параметров конвертации валют** .</span><span class="sxs-lookup"><span data-stu-id="1004b-103">Use the **Select Members** page to determine to which members the Business Intelligence Wizard should apply the currency conversion functionality specified on the **Set Currency Conversion Options** page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1004b-104">Эта страница не выводится на экран, если мастер бизнес-аналитики был запущен из конструктора измерений, а также если щелкнуть правой кнопкой мыши измерение в обозревателе решений в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1004b-104">This page does not appear if the Business Intelligence Wizard was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="1004b-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="1004b-105">Options</span></span>  
 <span data-ttu-id="1004b-106">**Измерение мер**</span><span class="sxs-lookup"><span data-stu-id="1004b-106">**Measures dimension**</span></span>  
 <span data-ttu-id="1004b-107">Выберите для применения функции конвертации валют к одной или более мер в данном кубе.</span><span class="sxs-lookup"><span data-stu-id="1004b-107">Select to apply the currency conversion functionality to one or more measures in the cube.</span></span>  
  
 <span data-ttu-id="1004b-108">В случае выбора в сетке отображаются параметры, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="1004b-108">If selected, the grid displays the options listed in the following table.</span></span>  
  
|<span data-ttu-id="1004b-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="1004b-109">Option</span></span>|<span data-ttu-id="1004b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="1004b-110">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1004b-111">**Типы встроенных мер**</span><span class="sxs-lookup"><span data-stu-id="1004b-111">**Built-in Measure Types**</span></span>|<span data-ttu-id="1004b-112">Выберите для включения функции конвертации валют для указанной меры.</span><span class="sxs-lookup"><span data-stu-id="1004b-112">Select to include currency conversion functionality for the specified measure.</span></span>|  
|<span data-ttu-id="1004b-113">**Мерам**</span><span class="sxs-lookup"><span data-stu-id="1004b-113">**Measures**</span></span>|<span data-ttu-id="1004b-114">Выберите меру из группы мер, содержащей курсы обмена, для использования при преобразовании меры, выбранной в поле **Типы встроенных мер** .</span><span class="sxs-lookup"><span data-stu-id="1004b-114">Select the measure from the rate measure group that contains the exchange rate to use when the measure selected in **Built-in Measure Types** is converted.</span></span>|  
  
 <span data-ttu-id="1004b-115">**Иерархия счетов**</span><span class="sxs-lookup"><span data-stu-id="1004b-115">**Account hierarchy**</span></span>  
 <span data-ttu-id="1004b-116">Выберите для применения функции конвертации валют к одному или нескольким элементам иерархии измерения счетов, включенного в данный куб.</span><span class="sxs-lookup"><span data-stu-id="1004b-116">Select to apply the currency conversion functionality to one or more members in the account hierarchy of the account dimension included in the cube.</span></span> <span data-ttu-id="1004b-117">Иерархия учетных записей — это иерархия в измерении счетов, `Type` свойство которой имеет значение *Account*.</span><span class="sxs-lookup"><span data-stu-id="1004b-117">The account hierarchy is the hierarchy within the account dimension whose `Type` property is set to *Account*.</span></span>  
  
 <span data-ttu-id="1004b-118">В случае выбора в сетке отображаются параметры, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="1004b-118">If selected, the grid displays the options listed in the following table.</span></span>  
  
|<span data-ttu-id="1004b-119">Параметр</span><span class="sxs-lookup"><span data-stu-id="1004b-119">Option</span></span>|<span data-ttu-id="1004b-120">Описание</span><span class="sxs-lookup"><span data-stu-id="1004b-120">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1004b-121">**Элемент счета**</span><span class="sxs-lookup"><span data-stu-id="1004b-121">**Account Member**</span></span>|<span data-ttu-id="1004b-122">Выберите для включения функции конвертации валют для указанного элемента иерархии учетных записей.</span><span class="sxs-lookup"><span data-stu-id="1004b-122">Select to include currency conversion functionality for the specified member of the account hierarchy.</span></span>|  
|<span data-ttu-id="1004b-123">**Мерам**</span><span class="sxs-lookup"><span data-stu-id="1004b-123">**Measures**</span></span>|<span data-ttu-id="1004b-124">Выберите меру из группы мер, содержащей курсы обмена, для использования при преобразовании элемента, выбранного в поле **Элемент счета** .</span><span class="sxs-lookup"><span data-stu-id="1004b-124">Select the measure from the rate measure group that contains the exchange rate to use when the measures for the member selected in **Account Member** are converted.</span></span>|  
  
 <span data-ttu-id="1004b-125">**Иерархия, основанная на типах счетов**</span><span class="sxs-lookup"><span data-stu-id="1004b-125">**Account hierarchy based on type**</span></span>  
 <span data-ttu-id="1004b-126">Выберите для применения функции конвертации валют ко всем элементам иерархии счета, у которых установлено свойство `Type` для указанного типа счета.</span><span class="sxs-lookup"><span data-stu-id="1004b-126">Select to apply the currency conversion functionality to all members of attributes in the account hierarchy whose `Type` property is set to a specified account type.</span></span>  
  
 <span data-ttu-id="1004b-127">В случае выбора в сетке отображаются параметры, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="1004b-127">If selected, the grid displays the options listed in the following table.</span></span>  
  
|<span data-ttu-id="1004b-128">Параметр</span><span class="sxs-lookup"><span data-stu-id="1004b-128">Option</span></span>|<span data-ttu-id="1004b-129">Описание</span><span class="sxs-lookup"><span data-stu-id="1004b-129">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1004b-130">**Тип учетной записи**</span><span class="sxs-lookup"><span data-stu-id="1004b-130">**Account Type**</span></span>|<span data-ttu-id="1004b-131">Выберите для включения функции конвертации валют для указанного типа счета.</span><span class="sxs-lookup"><span data-stu-id="1004b-131">Select to include currency conversion functionality for the specified account type.</span></span>|  
|<span data-ttu-id="1004b-132">**Мерам**</span><span class="sxs-lookup"><span data-stu-id="1004b-132">**Measures**</span></span>|<span data-ttu-id="1004b-133">Выберите меру из группы мер, содержащей курсы обмена, для использования при преобразовании типа счета, выбранного в поле **Тип счета** .</span><span class="sxs-lookup"><span data-stu-id="1004b-133">Select the measure from the rate measure group that contains the exchange rate to use when measures for the members of attributes using the account type selected in **Account Type** are converted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1004b-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="1004b-134">See Also</span></span>  
 <span data-ttu-id="1004b-135">[Справка F1 мастера бизнес-аналитики](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="1004b-135">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="1004b-136">[Конструктор кубов &#40;Analysis Services многомерных данных&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="1004b-136">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="1004b-137">Конструктор измерений &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="1004b-137">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
