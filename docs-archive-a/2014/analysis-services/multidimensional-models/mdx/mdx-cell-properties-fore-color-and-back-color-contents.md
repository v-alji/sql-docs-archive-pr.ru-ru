---
title: FORE_COLOR и BACK_COLOR содержимое (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- FORE_COLOR contents
- backgrounds [MDX]
- cells [MDX]
- colors [MDX]
- storing cell color information
- cell backgrounds
- BACK_COLOR contents
ms.assetid: ff8f40cb-2ac4-4fc2-9761-7f1b14c17c8c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 748754ec3c90bb44392d7acb7de8f815be24086e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737043"
---
# <a name="fore_color-and-back_color-contents-mdx"></a><span data-ttu-id="0d7cf-102">Свойства ячеек FORE_COLOR и BACK_COLOR (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="0d7cf-102">FORE_COLOR and BACK_COLOR Contents (MDX)</span></span>
  <span data-ttu-id="0d7cf-103">Свойства ячеек `FORE_COLOR` и `BACK_COLOR` хранят сведения о цвете соответственно текста и фона ячеек в формате операционной системы Microsoft Windows RGB (красный-зеленый-синий).</span><span class="sxs-lookup"><span data-stu-id="0d7cf-103">The `FORE_COLOR` and `BACK_COLOR` cell properties store color information for the text and the background of a cell, respectively, in the Microsoft Windows operating system red-green-blue (RGB) format.</span></span>  
  
 <span data-ttu-id="0d7cf-104">Допустимый диапазон обычных RGB-цветов: от нуля (0) до 16777215 (&H00FFFFFF).</span><span class="sxs-lookup"><span data-stu-id="0d7cf-104">The valid range for an ordinary RGB color is zero (0) to 16,777,215 (&H00FFFFFF).</span></span> <span data-ttu-id="0d7cf-105">Старший байт числа в этом диапазоне всегда равен 0, следующие 3 байта (в порядке старшинства) определяют интенсивность красного, зеленого и синего компонентов соответственно.</span><span class="sxs-lookup"><span data-stu-id="0d7cf-105">The high byte of a number in this range always equals 0; the lower 3 bytes, from least to most significant byte, determine the amount of red, green, and blue, respectively.</span></span> <span data-ttu-id="0d7cf-106">Интенсивность красного, зеленого и синего компонентов выражается числом от 0 до 255 (&HFF).</span><span class="sxs-lookup"><span data-stu-id="0d7cf-106">The red, green, and blue components are each represented by a number between 0 and 255 (&HFF).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d7cf-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="0d7cf-107">See Also</span></span>  
 [<span data-ttu-id="0d7cf-108">Использование свойств ячеек (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="0d7cf-108">Using Cell Properties &#40;MDX&#41;</span></span>](mdx-cell-properties-using-cell-properties.md)  
  
  
