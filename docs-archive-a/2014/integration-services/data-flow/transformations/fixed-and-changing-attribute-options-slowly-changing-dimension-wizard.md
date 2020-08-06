---
title: Параметры атрибутов неизменности и изменяемых атрибутов (мастер медленно изменяющихся измерений) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.attriboption.f1
ms.assetid: c841345c-7d03-452f-9379-1c8c464f029c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: df654cd97b343179828ebd94dea40eacc90e003d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656490"
---
# <a name="fixed-and-changing-attribute-options-slowly-changing-dimension-wizard"></a><span data-ttu-id="68df4-102">Параметры атрибутов неизменности и изменяемых атрибутов (мастер медленно изменяющихся измерений)</span><span class="sxs-lookup"><span data-stu-id="68df4-102">Fixed and Changing Attribute Options (Slowly Changing Dimension Wizard</span></span>
  <span data-ttu-id="68df4-103">В диалоговом окне **Параметры атрибутов неизменности и изменяемых атрибутов** можно определить реакцию на изменения фиксированных и изменяемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="68df4-103">Use the **Fixed and Changing Attribute Options** dialog box to specify how to respond to changes in fixed and changing attributes.</span></span>  
  
 <span data-ttu-id="68df4-104">Дополнительные сведения о работе этого мастера см. в разделе [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="68df4-104">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="68df4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="68df4-105">Options</span></span>  
 <span data-ttu-id="68df4-106">**Атрибуты неизменности**</span><span class="sxs-lookup"><span data-stu-id="68df4-106">**Fixed attributes**</span></span>  
 <span data-ttu-id="68df4-107">Для атрибутов неизменности определяет, должна ли задача закончиться неудачей, если обнаружено изменение в атрибуте неизменности.</span><span class="sxs-lookup"><span data-stu-id="68df4-107">For fixed attributes, indicate whether the task should fail if a change is detected in a fixed attribute.</span></span>  
  
 <span data-ttu-id="68df4-108">**Изменяемые атрибуты**</span><span class="sxs-lookup"><span data-stu-id="68df4-108">**Changing attributes**</span></span>  
 <span data-ttu-id="68df4-109">Для изменяемых атрибутов определяет, должна ли задача изменить все устаревшие записи или записи с истекшим сроком действия, в дополнение к текущим, при обнаружении изменения в изменяемом атрибуте.</span><span class="sxs-lookup"><span data-stu-id="68df4-109">For changing attributes, indicate whether the task should change outdated or expired records, in addition to current records, when a change is detected in a changing attribute.</span></span> <span data-ttu-id="68df4-110">Записью с истекшим сроком действия является та, которая была заменена более новой записью в результате изменения атрибута с предысторией (изменение типа 2).</span><span class="sxs-lookup"><span data-stu-id="68df4-110">An expired record is a record that has been replaced with a newer record by a change in a historical attribute (a Type 2 change).</span></span> <span data-ttu-id="68df4-111">Выбор этого параметра может наложить дополнительные требования к обработке в многомерном объекте, созданном в реляционном хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="68df4-111">Selecting this option may impose additional processing requirements on a multidimensional object constructed on the relational data warehouse.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68df4-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="68df4-112">See Also</span></span>  
 [<span data-ttu-id="68df4-113">Настройка выходов с помощью мастера медленно изменяющихся измерений</span><span class="sxs-lookup"><span data-stu-id="68df4-113">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
