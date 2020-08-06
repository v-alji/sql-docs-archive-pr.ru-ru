---
title: Параметры атрибутов с предысторией (мастер медленно изменяющихся измерений) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.histattriboption.f1
ms.assetid: a176ec66-ec39-4c99-99d1-c1afa8450e1e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fad005d6b8f80973abeb47dd881ef02b669d7b27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667327"
---
# <a name="historical-attribute-options-slowly-changing-dimension-wizard"></a><span data-ttu-id="a72ea-102">Параметры атрибутов с предысторией (мастер медленно изменяющихся измерений)</span><span class="sxs-lookup"><span data-stu-id="a72ea-102">Historical Attribute Options (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="a72ea-103">Диалоговое окно **Параметры атрибутов с предысторией** используется для просмотра атрибутов с предысторией по дате начала и окончания, а также для записи атрибутов с предысторией в специально предназначенный для этого столбец.</span><span class="sxs-lookup"><span data-stu-id="a72ea-103">Use the **Historical Attributes Options** dialog box to show historical attributes by start and end dates, or to record historical attributes in a column specially created for this purpose.</span></span>  
  
 <span data-ttu-id="a72ea-104">Дополнительные сведения о работе этого мастера см. в разделе [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="a72ea-104">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a72ea-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a72ea-105">Options</span></span>  
 <span data-ttu-id="a72ea-106">**Использовать общий столбец для вывода текущих и устаревших записей**</span><span class="sxs-lookup"><span data-stu-id="a72ea-106">**Use a single column to show current and expired records**</span></span>  
 <span data-ttu-id="a72ea-107">Если выбрано отображение состояния атрибутов с предысторией в одном столбце, можно выбрать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="a72ea-107">If you choose to use a single column to record the status of historical attributes, the following options are available:</span></span>  
  
|<span data-ttu-id="a72ea-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="a72ea-108">Option</span></span>|<span data-ttu-id="a72ea-109">Description</span><span class="sxs-lookup"><span data-stu-id="a72ea-109">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a72ea-110">**Столбец, указывающий текущую запись**</span><span class="sxs-lookup"><span data-stu-id="a72ea-110">**Column to indicate current record**</span></span>|<span data-ttu-id="a72ea-111">Выберите столбец, в котором указывается текущая запись.</span><span class="sxs-lookup"><span data-stu-id="a72ea-111">Select a column in which to indicate the current record.</span></span>|  
|<span data-ttu-id="a72ea-112">**Значение на момент актуальности**</span><span class="sxs-lookup"><span data-stu-id="a72ea-112">**Value when current**</span></span>|<span data-ttu-id="a72ea-113">Чтобы узнать, является ли запись текущей, выберите **True** или **Текущие** .</span><span class="sxs-lookup"><span data-stu-id="a72ea-113">Use either **True** or **Current** to show whether the record is current.</span></span>|  
|<span data-ttu-id="a72ea-114">**Значение для устаревшей записи**</span><span class="sxs-lookup"><span data-stu-id="a72ea-114">**Expiration value**</span></span>|<span data-ttu-id="a72ea-115">Чтобы узнать, содержит ли запись значение предыстории, выберите **False** или **Устаревшие** .</span><span class="sxs-lookup"><span data-stu-id="a72ea-115">Use either **False** or **Expired** to show whether the record is a historical value.</span></span>|  
  
 <span data-ttu-id="a72ea-116">**Использовать данные о дате начала и окончания событий для идентификации текущих и устаревших записей**</span><span class="sxs-lookup"><span data-stu-id="a72ea-116">**Use start and end dates to identify current and expired records**</span></span>  
 <span data-ttu-id="a72ea-117">Таблица измерения для этого параметра должна включать в себя столбец дат.</span><span class="sxs-lookup"><span data-stu-id="a72ea-117">The dimension table for this option must include a date column.</span></span> <span data-ttu-id="a72ea-118">Если выбрано отображение атрибутов с предысторией по датам начала и окончания, можно выбрать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="a72ea-118">If you choose to show historical attributes by start and end dates, the following options are available:</span></span>  
  
|<span data-ttu-id="a72ea-119">Параметр</span><span class="sxs-lookup"><span data-stu-id="a72ea-119">Option</span></span>|<span data-ttu-id="a72ea-120">Description</span><span class="sxs-lookup"><span data-stu-id="a72ea-120">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a72ea-121">**Столбец, содержащий дату начала события**</span><span class="sxs-lookup"><span data-stu-id="a72ea-121">**Start date column**</span></span>|<span data-ttu-id="a72ea-122">Выберите в таблице измерения столбец, в котором находится дата начала.</span><span class="sxs-lookup"><span data-stu-id="a72ea-122">Select the column in the dimension table to contain the start date.</span></span>|  
|<span data-ttu-id="a72ea-123">**Столбец, содержащий дату окончания события**</span><span class="sxs-lookup"><span data-stu-id="a72ea-123">**End date column**</span></span>|<span data-ttu-id="a72ea-124">Выберите в таблице измерения столбец, в котором находится дата окончания.</span><span class="sxs-lookup"><span data-stu-id="a72ea-124">Select the column in the dimension table to contain the end date.</span></span>|  
|<span data-ttu-id="a72ea-125">**Переменная для установки значений даты**</span><span class="sxs-lookup"><span data-stu-id="a72ea-125">**Variable to set date values**</span></span>|<span data-ttu-id="a72ea-126">Выберите переменную даты из списка.</span><span class="sxs-lookup"><span data-stu-id="a72ea-126">Select a date variable from the list.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a72ea-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="a72ea-127">See Also</span></span>  
 [<span data-ttu-id="a72ea-128">Настройка выходов с помощью мастера медленно изменяющихся измерений</span><span class="sxs-lookup"><span data-stu-id="a72ea-128">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
