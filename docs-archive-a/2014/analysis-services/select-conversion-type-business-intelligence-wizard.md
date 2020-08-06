---
title: Выбор типа конвертации валют (мастер бизнес-аналитики) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.currencyconversion.conversiontype.f1
ms.assetid: 2c664138-e8a1-4c47-8e7d-ee01c57e4692
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1f83fdf566b52a5fe79bea7a4a676274423d1091
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656603"
---
# <a name="select-conversion-type-business-intelligence-wizard"></a><span data-ttu-id="6cb9c-102">Выбор типа конвертации валют (мастер бизнес-аналитики)</span><span class="sxs-lookup"><span data-stu-id="6cb9c-102">Select Conversion Type (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="6cb9c-103">Используйте страницу **Выбор типа конвертации валют** для определения связи между локальной и отчетной валютой в транзакциях, хранимых в нескольких валютах.</span><span class="sxs-lookup"><span data-stu-id="6cb9c-103">Use the **Select Conversion Type** page to define the relationship between local currencies and reporting currencies for transactions stored in multiple currencies.</span></span> <span data-ttu-id="6cb9c-104">Местная валюта — это валюта, в формате которой хранятся транзакции для мер, выбранных на странице **Выбор мер** .</span><span class="sxs-lookup"><span data-stu-id="6cb9c-104">A local currency is the currency in which the transactions for measures selected in the **Select Measures** page are stored.</span></span> <span data-ttu-id="6cb9c-105">Отчетная валюта представляет собой валюту, в которую преобразуются транзакции, выбранные на странице **Выбор мер** .</span><span class="sxs-lookup"><span data-stu-id="6cb9c-105">A reporting currency is the currency in which the transactions selected in the **Select Measures** page are translated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6cb9c-106">Эта страница не выводится на экран, если мастер бизнес-аналитики был запущен из конструктора измерений, а также если щелкнуть правой кнопкой мыши измерение в обозревателе решений в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cb9c-106">This page does not appear if the Business Intelligence Wizard was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="6cb9c-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="6cb9c-107">Options</span></span>  
 <span data-ttu-id="6cb9c-108">**«Многие ко многим»**</span><span class="sxs-lookup"><span data-stu-id="6cb9c-108">**Many-to-many**</span></span>  
 <span data-ttu-id="6cb9c-109">Хранит транзакции в локальной валюте.</span><span class="sxs-lookup"><span data-stu-id="6cb9c-109">Stores transactions using local currencies.</span></span> <span data-ttu-id="6cb9c-110">Функция конвертирования валют преобразует эти транзакции в основную валюту, заданную на странице **Установка параметров преобразования валют** , а затем в одну или несколько отчетных валют.</span><span class="sxs-lookup"><span data-stu-id="6cb9c-110">The currency conversion functionality converts such transactions into the pivot currency specified in the **Set Currency Conversion Options** page, and then to one or more other reporting currencies.</span></span>  
  
 <span data-ttu-id="6cb9c-111">Например, в качестве основной валюты может быть установлен доллар США (USD), а в таблице фактов хранятся транзакции в евро (EUR), австралийских долларах (AUD) и мексиканских песо (MXN).</span><span class="sxs-lookup"><span data-stu-id="6cb9c-111">For example, the pivot currency can be set to United States dollars (USD), and the fact table stores transactions in euros (EUR), Australian dollars (AUD), and Mexican pesos (MXN).</span></span> <span data-ttu-id="6cb9c-112">При выборе этого параметра данные транзакции преобразуются из локальных валют в основную, а затем преобразованные транзакции повторно преобразуются из основной валюты в валюты отчета.</span><span class="sxs-lookup"><span data-stu-id="6cb9c-112">Selecting this option converts these transactions from their specified local currencies to the pivot currency, and then the converted transactions are converted again from the pivot currency to the specified reporting currencies.</span></span> <span data-ttu-id="6cb9c-113">Таким образом, транзакции могут храниться в заданных локальных валютах и просматриваться либо в основной валюте, либо в любой из валют для отчета, указанных на странице **Выбор валюты для отчетов** .</span><span class="sxs-lookup"><span data-stu-id="6cb9c-113">The result is that transactions can be stored in the specified local currencies and viewed either in the specified pivot currency or in any one of the reporting currencies specified in the **Specify Reporting Currencies** page.</span></span>  
  
 <span data-ttu-id="6cb9c-114">**«многие к одному»**</span><span class="sxs-lookup"><span data-stu-id="6cb9c-114">**Many-to-one**</span></span>  
 <span data-ttu-id="6cb9c-115">Хранит транзакции в локальной валюте.</span><span class="sxs-lookup"><span data-stu-id="6cb9c-115">Stores transactions using local currencies.</span></span> <span data-ttu-id="6cb9c-116">Функция конвертирования валют преобразует эти транзакции в основную валюту, заданную на странице **Установка параметров преобразования валют** .</span><span class="sxs-lookup"><span data-stu-id="6cb9c-116">The currency conversion functionality converts such transactions into the pivot currency specified in the **Set Currency Conversion Options** page.</span></span> <span data-ttu-id="6cb9c-117">Основная валюта выступает в качестве единственной определенной отчетной валюты.</span><span class="sxs-lookup"><span data-stu-id="6cb9c-117">The pivot currency serves as the only specified reporting currency.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6cb9c-118">Если выбран этот параметр, страница **Выбор валюты для отчетов** не отображается.</span><span class="sxs-lookup"><span data-stu-id="6cb9c-118">If this option is selected, the **Specify Reporting Currencies** page does not appear.</span></span>  
  
 <span data-ttu-id="6cb9c-119">Например, в качестве основной валюты может быть установлен доллар США (USD), а в таблице фактов хранятся транзакции в евро (EUR), австралийских долларах (AUD) и мексиканских песо (MXN).</span><span class="sxs-lookup"><span data-stu-id="6cb9c-119">For example, the pivot currency can be set to United States dollars (USD), and the fact table stores transactions in euros (EUR), Australian dollars (AUD), and Mexican pesos (MXN).</span></span> <span data-ttu-id="6cb9c-120">При выборе этого параметра данные транзакции преобразуются из локальных валют в основную.</span><span class="sxs-lookup"><span data-stu-id="6cb9c-120">Selecting this option converts these transactions from their specified local currencies to the pivot currency.</span></span> <span data-ttu-id="6cb9c-121">Таким образом, транзакции могут храниться в заданных локальных валютах и просматриваться в указанной основной валюте.</span><span class="sxs-lookup"><span data-stu-id="6cb9c-121">The result is that transactions can be stored in the specified local currencies and viewed in the specified pivot currency.</span></span>  
  
 <span data-ttu-id="6cb9c-122">**«Один ко многим»**</span><span class="sxs-lookup"><span data-stu-id="6cb9c-122">**One-to-many**</span></span>  
 <span data-ttu-id="6cb9c-123">Сохраните транзакции с использованием основной валюты, заданной на странице **Установка параметров преобразования валют** , а затем в одну или несколько отчетных валют.</span><span class="sxs-lookup"><span data-stu-id="6cb9c-123">Store transactions using the pivot currency specified in the **Set Currency Conversion Options** page, and then to one or more other reporting currencies.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6cb9c-124">Если выбран этот параметр, страница **Определение ссылки на местную валюту** не отображается.</span><span class="sxs-lookup"><span data-stu-id="6cb9c-124">If this option is selected, the **Define Local Currency Reference** page does not appear.</span></span>  
  
 <span data-ttu-id="6cb9c-125">Например, в качестве основной валюты может быть установлен доллар США (USD), и в таблице фактов хранятся транзакции в долларах США.</span><span class="sxs-lookup"><span data-stu-id="6cb9c-125">For example, the pivot currency can be set to United States dollars (USD), and the fact table stores transactions in USD.</span></span> <span data-ttu-id="6cb9c-126">При выборе этого параметра данные транзакции преобразуются из основной валюты в заданные отчетные валюты.</span><span class="sxs-lookup"><span data-stu-id="6cb9c-126">Selecting this option converts these transactions from the pivot currency to the specified reporting currencies.</span></span> <span data-ttu-id="6cb9c-127">Таким образом, транзакции могут храниться в заданной основной валюте и просматриваться либо в основной, либо в любой из отчетных валют, указанных на странице **Выбор валюты для отчетов** .</span><span class="sxs-lookup"><span data-stu-id="6cb9c-127">The result is that transactions can be stored in the specified pivot currency and viewed either in the specified pivot currency or in any one of the reporting currencies specified in the **Specify Reporting Currencies** page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cb9c-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="6cb9c-128">See Also</span></span>  
 <span data-ttu-id="6cb9c-129">[Справка F1 мастера бизнес-аналитики](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="6cb9c-129">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="6cb9c-130">[Конструктор кубов &#40;Analysis Services многомерных данных&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="6cb9c-130">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="6cb9c-131">Конструктор измерений &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="6cb9c-131">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
