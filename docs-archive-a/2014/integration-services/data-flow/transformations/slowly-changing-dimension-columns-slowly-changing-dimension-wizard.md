---
title: Столбцы медленно изменяющихся измерений (мастер медленно изменяющихся измерений) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.scdsupport.f1
ms.assetid: 36de99d5-5368-48e0-b876-17e9c6862c6c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6283887cbddb9844e0ac769281184f588dc2a94d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728509"
---
# <a name="slowly-changing-dimension-columns-slowly-changing-dimension-wizard"></a><span data-ttu-id="79305-102">Столбцы медленно меняющихся измерений (мастер медленно изменяющихся измерений)</span><span class="sxs-lookup"><span data-stu-id="79305-102">Slowly Changing Dimension Columns (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="79305-103">Диалоговое окно **Столбцы медленно меняющихся измерений** используется для выбора типа изменения для каждого столбца медленно меняющихся измерений.</span><span class="sxs-lookup"><span data-stu-id="79305-103">Use the **Slowly Changing Dimensions Columns** dialog box to select a change type for each slowly changing dimension column.</span></span>  
  
 <span data-ttu-id="79305-104">Дополнительные сведения о работе этого мастера см. в разделе [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="79305-104">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="79305-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="79305-105">Options</span></span>  
 <span data-ttu-id="79305-106">**Столбцы измерений**</span><span class="sxs-lookup"><span data-stu-id="79305-106">**Dimension Columns**</span></span>  
 <span data-ttu-id="79305-107">Выберите столбец измерения из списка.</span><span class="sxs-lookup"><span data-stu-id="79305-107">Select a dimension column from the list.</span></span>  
  
 <span data-ttu-id="79305-108">**Тип изменения**</span><span class="sxs-lookup"><span data-stu-id="79305-108">**Change Type**</span></span>  
 <span data-ttu-id="79305-109">Выберите пункт **Атрибут неизменности**или один из двух типов изменяющихся атрибутов.</span><span class="sxs-lookup"><span data-stu-id="79305-109">Select a **Fixed Attribute**, or select one of the two types of changing attributes.</span></span> <span data-ttu-id="79305-110">Используйте пункт **Атрибут неизменности** , когда значение в столбце не должно изменяться; службы [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] тогда будут воспринимать изменения как ошибки.</span><span class="sxs-lookup"><span data-stu-id="79305-110">Use **Fixed Attribute** when the value in a column should not change; [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] then treats changes as errors.</span></span> <span data-ttu-id="79305-111">Используйте **Изменяемый атрибут** для замены существующих значений измененными значениями.</span><span class="sxs-lookup"><span data-stu-id="79305-111">Use **Changing Attribute** to overwrite existing values with changed values.</span></span> <span data-ttu-id="79305-112">Используйте **Атрибут c предысторией** для сохранения измененных значений в новых записях с пометкой предыдущих записей как устаревших.</span><span class="sxs-lookup"><span data-stu-id="79305-112">Use **Historical Attribute** to save changed values in new records, while marking previous records as outdated.</span></span>  
  
 <span data-ttu-id="79305-113">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="79305-113">**Remove**</span></span>  
 <span data-ttu-id="79305-114">Выберите столбец измерения и удалите его из списка сопоставленных столбцов, нажав кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="79305-114">Select a dimension column, and remove it from the list of mapped columns by clicking **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79305-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="79305-115">See Also</span></span>  
 [<span data-ttu-id="79305-116">Настройка выходов с помощью мастера медленно изменяющихся измерений</span><span class="sxs-lookup"><span data-stu-id="79305-116">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
