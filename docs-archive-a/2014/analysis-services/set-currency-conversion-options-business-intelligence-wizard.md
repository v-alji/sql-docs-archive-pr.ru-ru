---
title: Установка параметров конвертации валюты (мастер бизнес-аналитики) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.currencyconversion.calculationsettings.f1
ms.assetid: a49d4e1f-bdda-4a83-ab4f-ce8c500e1d6d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 61877deb0bc422d65f977e3fc9de3e678f7d8477
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736908"
---
# <a name="set-currency-conversion-options-business-intelligence-wizard"></a><span data-ttu-id="d2a59-102">Установка параметров конвертации валюты (мастер бизнес-аналитики)</span><span class="sxs-lookup"><span data-stu-id="d2a59-102">Set Currency Conversion Options (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="d2a59-103">Страница **Установка параметров конвертации валюты** используется для установки вычислений конвертации валют для группы мер, содержащих курсы обмена валют.</span><span class="sxs-lookup"><span data-stu-id="d2a59-103">Use the **Set Currency Conversion** page to define currency conversion calculations for a measure group that contains exchange rates.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2a59-104">Эта страница не выводится на экран, если мастер бизнес-аналитики был запущен из конструктора измерений, а также если щелкнуть правой кнопкой мыши измерение в обозревателе решений в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2a59-104">This page does not appear if the Business Intelligence Wizard was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="d2a59-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="d2a59-105">Options</span></span>  
 <span data-ttu-id="d2a59-106">**Выберите группу мер, которая содержит обменные курсы**</span><span class="sxs-lookup"><span data-stu-id="d2a59-106">**Select the measure group that contains exchange rates**</span></span>  
 <span data-ttu-id="d2a59-107">Выберите группу мер, содержащих курсы обмена валют, на которую должны ссылаться вычисления конвертации валют.</span><span class="sxs-lookup"><span data-stu-id="d2a59-107">Select the measure group that contains the exchange rates that the currency conversion calculations should reference.</span></span>  
  
 <span data-ttu-id="d2a59-108">**Укажите основную валюту**</span><span class="sxs-lookup"><span data-stu-id="d2a59-108">**Specify the pivot currency**</span></span>  
 <span data-ttu-id="d2a59-109">Выберите элемент, служащий основной валютой для группы мер.</span><span class="sxs-lookup"><span data-stu-id="d2a59-109">Select the member that serves as the pivot currency for the measure group.</span></span>  
  
 <span data-ttu-id="d2a59-110">**Укажите способ введения обменных курсов (выберите валюту образца)**</span><span class="sxs-lookup"><span data-stu-id="d2a59-110">**Select how you entered your exchange rates (select a sample currency)**</span></span>  
 <span data-ttu-id="d2a59-111">Выберите элемент, представляющий валюту образца, из измерения валют для изменения текста для X единиц в основной валюте за 1 единицу в валюте образца и X единиц в валюте образца за 1 единицу в основной валюте, чтобы понятнее отобразить направление курса обмена валют.</span><span class="sxs-lookup"><span data-stu-id="d2a59-111">Select a member representing a sample currency from the currency dimension to change the text for the X pivot currency per 1 sample currency and X sample currency per 1 pivot currency options to better display the exchange rate direction.</span></span>  
  
 <span data-ttu-id="d2a59-112">**X единиц в основной валюте за 1 единицу в валюте образца**</span><span class="sxs-lookup"><span data-stu-id="d2a59-112">**X pivot currency per 1 sample currency**</span></span>  
 <span data-ttu-id="d2a59-113">Выберите для указания того, что курс обмена валют в группе мер представляет собой множитель для заданной основной валюты.</span><span class="sxs-lookup"><span data-stu-id="d2a59-113">Select to indicate that the exchange rates in the rate measure group represent a multiplier for the specified pivot currency.</span></span>  
  
 <span data-ttu-id="d2a59-114">**X единиц в валюте образца за 1 единицу в основной валюте**</span><span class="sxs-lookup"><span data-stu-id="d2a59-114">**X sample currency per 1 pivot currency**</span></span>  
 <span data-ttu-id="d2a59-115">Выберите для указания того, что курс обмена валют в группе мер представляет собой множитель для заданной валюты образца.</span><span class="sxs-lookup"><span data-stu-id="d2a59-115">Select to indicate that the exchange rates in the rate measure group represent a multiplier for the specified sample currency.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2a59-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="d2a59-116">See Also</span></span>  
 <span data-ttu-id="d2a59-117">[Справка F1 мастера бизнес-аналитики](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="d2a59-117">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="d2a59-118">[Конструктор кубов &#40;Analysis Services многомерных данных&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="d2a59-118">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="d2a59-119">Конструктор измерений &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="d2a59-119">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
