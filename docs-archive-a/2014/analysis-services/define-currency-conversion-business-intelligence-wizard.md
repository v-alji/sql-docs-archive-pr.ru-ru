---
title: Определение конвертации валют (мастер бизнес-аналитики) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.currencyconversion.existingscriptpage.f1
ms.assetid: 37dd65b7-9d8d-44ad-b316-96a92c622472
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1c60b6ad6964060164e273004f59604fef6574a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654584"
---
# <a name="define-currency-conversion-business-intelligence-wizard"></a><span data-ttu-id="ad066-102">Определение конвертации валюты (мастер бизнес-аналитики)</span><span class="sxs-lookup"><span data-stu-id="ad066-102">Define Currency Conversion (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="ad066-103">Страница **Определение конвертации валют** используется для просмотра скриптов многомерных выражений, содержащих функцию конвертации валюты, которая сформирована мастером бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="ad066-103">Use the **Define Currency Conversion** page to review the Multidimensional Expressions (MDX) script that contains the currency conversion functionality generated by the Business Intelligence Wizard.</span></span> <span data-ttu-id="ad066-104">После этого скрипт многомерных выражений, сформированный мастером, можно использовать для замены или дополнения ранее определенной функции конвертации валюты в скрипте многомерных выражений куба.</span><span class="sxs-lookup"><span data-stu-id="ad066-104">You can then use this wizard-generated MDX script to either overwrite or append the previously-defined currency conversion functionality in the cube's MDX script.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ad066-105">Данная страница отображается, только если мастер бизнес-аналитики обнаруживает по крайней мере одну предварительно определенную конвертацию валюты в скрипте многомерных выражений для куба.</span><span class="sxs-lookup"><span data-stu-id="ad066-105">This page will appear only if the Business Intelligence Wizard detects at least one previously-defined currency conversion in the MDX script for the cube.</span></span> <span data-ttu-id="ad066-106">В скрипте многомерных выражений для куба конвертации валют выделяются следующими комментариями:</span><span class="sxs-lookup"><span data-stu-id="ad066-106">In the MDX script for a cube, currency conversions are framed with the following comments:</span></span>  
>   
>  `//<Currency conversion>`  
>   
>  `...`  
>   
>  `[MDX statements for the currency conversion]`  
>   
>  `...`  
>   
>  `//</Currency conversion>`  
>   
>  <span data-ttu-id="ad066-107">При изменении или удалении этих комментариев мастер бизнес-аналитики может быть неспособен обнаружить предварительно определенную конвертацию валюты.</span><span class="sxs-lookup"><span data-stu-id="ad066-107">If you change or remove these comments, the Business Intelligence Wizard may not be able to detect any previously-defined currency conversion.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ad066-108">Варианты</span><span class="sxs-lookup"><span data-stu-id="ad066-108">Options</span></span>  
 <span data-ttu-id="ad066-109">**Новый скрипт конвертации валюты**</span><span class="sxs-lookup"><span data-stu-id="ad066-109">**New currency conversion script**</span></span>  
 <span data-ttu-id="ad066-110">Отображает скрипт многомерных выражений, сформированный в текущем сеансе мастера бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="ad066-110">Displays the MDX script generated by the current Business Intelligence Wizard session.</span></span>  
  
 <span data-ttu-id="ad066-111">**Перезаписать существующий скрипт конвертации валюты**</span><span class="sxs-lookup"><span data-stu-id="ad066-111">**Overwrite existing currency conversion script**</span></span>  
 <span data-ttu-id="ad066-112">Выберите, чтобы заменить скрипт многомерных выражений, отображаемый в окне **Существующий скрипт конвертации валюты** , скриптом многомерных выражений, отображаемым в окне **Новый скрипт конвертации валюты**.</span><span class="sxs-lookup"><span data-stu-id="ad066-112">Select to overwrite the MDX script displayed in **Existing currency conversion script** with the MDX script displayed in **New currency conversion script**.</span></span>  
  
 <span data-ttu-id="ad066-113">**Добавить после**</span><span class="sxs-lookup"><span data-stu-id="ad066-113">**Append after**</span></span>  
 <span data-ttu-id="ad066-114">Выберите для добавления скрипта многомерных выражений, отображаемого в окне **Новый скрипт конвертации валюты** , к концу скрипта многомерных выражений, отображаемого в окне **Существующий скрипт конвертации валюты**.</span><span class="sxs-lookup"><span data-stu-id="ad066-114">Select to append the MDX script displayed in **New currency conversion script** to the end of the MDX script displayed in **Existing currency conversion script**.</span></span> <span data-ttu-id="ad066-115">Добавленный скрипт отобразится в виде нового раздела.</span><span class="sxs-lookup"><span data-stu-id="ad066-115">The appended script appears as a new section.</span></span>  
  
 <span data-ttu-id="ad066-116">**Существующий скрипт конвертации валюты**</span><span class="sxs-lookup"><span data-stu-id="ad066-116">**Existing currency conversion script**</span></span>  
 <span data-ttu-id="ad066-117">Выберите раздел существующего скрипта многомерных выражений, содержащий ранее определенную функцию конвертации валюты, который необходимо заменить или дополнить.</span><span class="sxs-lookup"><span data-stu-id="ad066-117">Select the section of the existing MDX script that contains the previously-defined currency conversion functionality to be overwritten or appended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad066-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="ad066-118">See Also</span></span>  
 <span data-ttu-id="ad066-119">[Справка F1 мастера бизнес-аналитики](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="ad066-119">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="ad066-120">[Конструктор кубов &#40;Analysis Services многомерных данных&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="ad066-120">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="ad066-121">Конструктор измерений &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ad066-121">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  