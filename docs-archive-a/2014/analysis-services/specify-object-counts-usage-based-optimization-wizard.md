---
title: Указание счетчиков объектов (мастер оптимизации с учетом использования) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.storagedesignwizard.calculatingobjectcounts.f1
ms.assetid: 306c7c25-ae24-4852-ab8c-c82f68a4bc1f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 862be19f12308def815a280dba04f42f0cbe6878
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666769"
---
# <a name="specify-object-counts-usage-based-optimization-wizard"></a><span data-ttu-id="421e0-102">Задание счетчиков объектов (мастер оптимизации с учетом использования)</span><span class="sxs-lookup"><span data-stu-id="421e0-102">Specify Object Counts (Usage-Based Optimization Wizard)</span></span>
  <span data-ttu-id="421e0-103">Для автоматического вычисления количества объектов в кубе или ввода оценочного числа вручную используется страница **Определение счетчиков объектов** .</span><span class="sxs-lookup"><span data-stu-id="421e0-103">Use the **Specify Object Counts** page to automatically calculate the count of objects in the cube or to manually enter estimated counts.</span></span> <span data-ttu-id="421e0-104">С помощью счетчиков объектов мастер оптимизации с учетом использования оценивает требования к хранилищу.</span><span class="sxs-lookup"><span data-stu-id="421e0-104">The Usage-Based Optimization Wizard uses the object counts to estimate storage requirements.</span></span>  
  
## <a name="options"></a><span data-ttu-id="421e0-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="421e0-105">Options</span></span>  
 <span data-ttu-id="421e0-106">**Объекты куба**</span><span class="sxs-lookup"><span data-stu-id="421e0-106">**Cube Objects**</span></span>  
 <span data-ttu-id="421e0-107">Выводит измерения и атрибуты куба.</span><span class="sxs-lookup"><span data-stu-id="421e0-107">Displays the dimensions and attributes in the cube.</span></span> <span data-ttu-id="421e0-108">Отображаются только те атрибуты, свойство которых не имеет `AggregationUsage` значение None на странице **Анализ использования статистической обработки** мастера, так как это единственные атрибуты, требующие указания счетчиков.</span><span class="sxs-lookup"><span data-stu-id="421e0-108">Only the attributes that do not have their `AggregationUsage` property set to None in the **Review Aggregation Usage** page of the wizard are shown because those are the only attributes that need counts specified.</span></span>  
  
 <span data-ttu-id="421e0-109">**Оценочное число**</span><span class="sxs-lookup"><span data-stu-id="421e0-109">**Estimated count**</span></span>  
 <span data-ttu-id="421e0-110">Выводит оценочное число строк группы мер и оценочное число элементов атрибута в измерениях базы данных.</span><span class="sxs-lookup"><span data-stu-id="421e0-110">Displays the estimated number of rows in the measure group and the estimated attribute member counts in the database dimensions.</span></span> <span data-ttu-id="421e0-111">Значения оценочного числа можно ввести вручную или вычислить.</span><span class="sxs-lookup"><span data-stu-id="421e0-111">You can type a value to use as the estimated count or you can calculate the estimated count values.</span></span> <span data-ttu-id="421e0-112">Чтобы вычислить значения этих чисел, введите в это поле 0 и нажмите кнопку **Подсчет**.</span><span class="sxs-lookup"><span data-stu-id="421e0-112">To calculate the count values, type 0 in the field and then click **Count**.</span></span> <span data-ttu-id="421e0-113">Поля, где уже отображаются оценочные числа, не обновляются.</span><span class="sxs-lookup"><span data-stu-id="421e0-113">Fields that already display a count are not updated.</span></span>  
  
 <span data-ttu-id="421e0-114">**Количество секций**</span><span class="sxs-lookup"><span data-stu-id="421e0-114">**Partition count**</span></span>  
 <span data-ttu-id="421e0-115">Введите оценочное количество строк группы мер и оценочное количество элементов атрибута в секциях (необязательно).</span><span class="sxs-lookup"><span data-stu-id="421e0-115">(Optional) Type the estimated number of rows in the measure group and the estimated attribute member counts in the partitions.</span></span>  
  
 <span data-ttu-id="421e0-116">**Count**</span><span class="sxs-lookup"><span data-stu-id="421e0-116">**Count**</span></span>  
 <span data-ttu-id="421e0-117">Вычисляет и повторно заполняет значения в столбце **Оценочное число** для всех пустых полей.</span><span class="sxs-lookup"><span data-stu-id="421e0-117">Calculates and repopulates the values in the **Estimated count** column for all empty fields.</span></span> <span data-ttu-id="421e0-118">Поля, где уже отображаются оценочные числа, не обновляются.</span><span class="sxs-lookup"><span data-stu-id="421e0-118">Fields that already display a count are not updated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="421e0-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="421e0-119">See Also</span></span>  
 <span data-ttu-id="421e0-120">[Справка F1 мастера статистических схем](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="421e0-120">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="421e0-121">Analysis Services мастера &#40;многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="421e0-121">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
