---
title: Определение счетчиков объектов (мастер статистических схем) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.storagedesignwizard.calculatingobjectcounts.f1
ms.assetid: 305d9d79-d1ab-4704-a7b5-3283842b3996
author: minewiskan
ms.author: owend
ms.openlocfilehash: c66b972395f86746b2d08df234db8aa0c71d03fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665602"
---
# <a name="specify-object-counts-aggregation-design-wizard"></a><span data-ttu-id="507b8-102">Определение счетчиков объектов (мастер статистических схем)</span><span class="sxs-lookup"><span data-stu-id="507b8-102">Specify Object Counts (Aggregation Design Wizard)</span></span>
  <span data-ttu-id="507b8-103">Для автоматического вычисления количества объектов в кубе или ввода оценочного числа вручную используется страница **Определение счетчиков объектов** .</span><span class="sxs-lookup"><span data-stu-id="507b8-103">Use the **Specify Object Counts** page to automatically calculate the count of objects in the cube or to manually enter estimated counts.</span></span> <span data-ttu-id="507b8-104">С помощью счетчиков объектов мастер статистических схем оценивает требования к хранилищу.</span><span class="sxs-lookup"><span data-stu-id="507b8-104">The Aggregation Design Wizard uses the object counts to estimate storage requirements.</span></span>  
  
## <a name="options"></a><span data-ttu-id="507b8-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="507b8-105">Options</span></span>  
 <span data-ttu-id="507b8-106">**Объекты куба**</span><span class="sxs-lookup"><span data-stu-id="507b8-106">**Cube Objects**</span></span>  
 <span data-ttu-id="507b8-107">Выводит измерения и атрибуты куба.</span><span class="sxs-lookup"><span data-stu-id="507b8-107">Displays the dimensions and attributes in the cube.</span></span> <span data-ttu-id="507b8-108">Показаны только те атрибуты, свойства которых не `AggregationUsage` заданы на `None` странице **Анализ использования статистической обработки** мастера, поскольку это единственные атрибуты, требующие указания счетчиков.</span><span class="sxs-lookup"><span data-stu-id="507b8-108">Only the attributes that do not have their `AggregationUsage` property set to `None` in the **Review Aggregation Usage** page of the wizard are shown, because those are the only attributes that require the counts to be specified.</span></span>  
  
 <span data-ttu-id="507b8-109">**Оценочное число**</span><span class="sxs-lookup"><span data-stu-id="507b8-109">**Estimated count**</span></span>  
 <span data-ttu-id="507b8-110">Выводит оценочное число строк группы мер и оценочное число элементов атрибута в измерениях базы данных.</span><span class="sxs-lookup"><span data-stu-id="507b8-110">Displays the estimated number of rows in the measure group and the estimated attribute member counts in the database dimensions.</span></span> <span data-ttu-id="507b8-111">Значения оценочного числа можно ввести вручную или вычислить.</span><span class="sxs-lookup"><span data-stu-id="507b8-111">You can type a value to use as the estimated count or you can calculate the estimated count values.</span></span> <span data-ttu-id="507b8-112">Чтобы вычислить значения счетчиков, введите `0` в поле и нажмите кнопку **количество**.</span><span class="sxs-lookup"><span data-stu-id="507b8-112">To calculate the count values, type `0` in the field and then click **Count**.</span></span> <span data-ttu-id="507b8-113">Поля, где уже отображаются оценочные числа, не обновляются.</span><span class="sxs-lookup"><span data-stu-id="507b8-113">Fields that already display a count are not updated.</span></span>  
  
 <span data-ttu-id="507b8-114">**Количество секций**</span><span class="sxs-lookup"><span data-stu-id="507b8-114">**Partition count**</span></span>  
 <span data-ttu-id="507b8-115">Введите оценочное число строк группы мер и оценочное число элементов атрибута в секциях (необязательно).</span><span class="sxs-lookup"><span data-stu-id="507b8-115">(Optional) Type the estimated number of rows in the measure group and type the estimated attribute member counts in the partitions.</span></span>  
  
 <span data-ttu-id="507b8-116">**Count**</span><span class="sxs-lookup"><span data-stu-id="507b8-116">**Count**</span></span>  
 <span data-ttu-id="507b8-117">Вычисляет и повторно заполняет значения в столбце **Оценочное число** для всех пустых полей.</span><span class="sxs-lookup"><span data-stu-id="507b8-117">Calculates and repopulates the values in the **Estimated count** column for all empty fields.</span></span> <span data-ttu-id="507b8-118">Поля, где уже отображаются оценочные числа, не обновляются.</span><span class="sxs-lookup"><span data-stu-id="507b8-118">Fields that already display a count are not updated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="507b8-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="507b8-119">See Also</span></span>  
 <span data-ttu-id="507b8-120">[Справка F1 мастера статистических схем](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="507b8-120">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="507b8-121">Analysis Services мастера &#40;многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="507b8-121">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
