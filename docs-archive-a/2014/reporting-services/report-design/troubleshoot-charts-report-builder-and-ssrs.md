---
title: Устранение неполадок с диаграммами (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 3a327ffa-3b69-40d6-8015-cc01cfae9161
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b931b50545ba2b8d7c4c06cc5c48d6415a05470a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733606"
---
# <a name="troubleshoot-charts-report-builder-and-ssrs"></a><span data-ttu-id="91d85-102">Устранение неполадок с диаграммами (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="91d85-102">Troubleshoot Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="91d85-103">При работе с диаграммами могут возникать следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="91d85-103">These issues can be helpful when working with charts.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="why-does-my-chart-count-not-sum-the-values-on-the-value-axis"></a><span data-ttu-id="91d85-104">Почему в диаграмме выполняется подсчет, а не суммирование значений по оси значений?</span><span class="sxs-lookup"><span data-stu-id="91d85-104">Why does my chart count, not sum, the values on the value axis?</span></span>  
 <span data-ttu-id="91d85-105">Для верного отображения многих типов диаграмм требуются числовые значения по оси значений (обычно это ось Y).</span><span class="sxs-lookup"><span data-stu-id="91d85-105">Most chart types require numeric values along the value axis, which is typically the y-axis, in order to draw correctly.</span></span> <span data-ttu-id="91d85-106">Если поле значения имеет тип `String`, диаграмме не удастся отобразить числовые значения, даже если поля содержат числа.</span><span class="sxs-lookup"><span data-stu-id="91d85-106">If the data type of your value field is `String`, the chart cannot display a numeric value, even if there are numerals in the fields.</span></span> <span data-ttu-id="91d85-107">Вместо этого диаграмма отображает общее число строк, содержащих значение в этом поле.</span><span class="sxs-lookup"><span data-stu-id="91d85-107">Instead, the chart displays a count of the total number of rows that contain a value in that field.</span></span> <span data-ttu-id="91d85-108">Чтобы избежать подобного поведения, убедитесь, что поля, используемые для рядов значений, имеют числовые типы данных, а не являются строками, содержащими числа.</span><span class="sxs-lookup"><span data-stu-id="91d85-108">To avoid this behavior, make sure that the fields that you use for value series have numeric data types, as opposed to strings that contain formatted numbers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91d85-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="91d85-109">See Also</span></span>  
 [<span data-ttu-id="91d85-110">Диаграммы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="91d85-110">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
