---
title: Диалоговое окно «Анализ влияния» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.process.impactanalysisdialog.f1
ms.assetid: 208268eb-4e14-44db-9c64-6f74b776adb6
author: minewiskan
ms.author: owend
ms.openlocfilehash: e47ab806b9bd10afc812113b69fe0849437068b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728929"
---
# <a name="impact-analysis-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="62cf5-102">Диалоговое окно «Анализ влияния» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="62cf5-102">Impact Analysis Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="62cf5-103">В диалоговом окне **Анализ влияния** в средах [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] и [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] можно определить и возможную обработку зависимых объектов при обработке объектов, заданных в диалоговом окне **Обработка** .</span><span class="sxs-lookup"><span data-stu-id="62cf5-103">Use the **Impact Analysis** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to identify and optionally process dependent objects that are affected if the objects listed in the **Process** dialog box are processed.</span></span> <span data-ttu-id="62cf5-104">Отрыть диалоговое окно **Анализ влияния** можно, нажав кнопку **Анализ влияния** в диалоговом окне **Обработка** .</span><span class="sxs-lookup"><span data-stu-id="62cf5-104">You can display the **Impact Analysis** dialog box by clicking **Impact Analysis** from the **Process** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62cf5-105">Объект может появляться более одного раза, если он задействован несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="62cf5-105">An object appears more than once if it is affected in more than one way.</span></span>  
  
## <a name="options"></a><span data-ttu-id="62cf5-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="62cf5-106">Options</span></span>  
 <span data-ttu-id="62cf5-107">**Список объектов**</span><span class="sxs-lookup"><span data-stu-id="62cf5-107">**Object list**</span></span>  
 <span data-ttu-id="62cf5-108">Выводит в сетке список зависимых объектов.</span><span class="sxs-lookup"><span data-stu-id="62cf5-108">Displays a list of dependent objects in a grid.</span></span> <span data-ttu-id="62cf5-109">Сетка содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="62cf5-109">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="62cf5-110">**Имени объекта**</span><span class="sxs-lookup"><span data-stu-id="62cf5-110">**Object Name**</span></span>  
 <span data-ttu-id="62cf5-111">Выводит имя зависимого объекта, который, возможно, нужно обработать.</span><span class="sxs-lookup"><span data-stu-id="62cf5-111">Displays the name of the dependent object that may need to be processed.</span></span> <span data-ttu-id="62cf5-112">Значок слева от имени указывает тип объекта.</span><span class="sxs-lookup"><span data-stu-id="62cf5-112">The icon to the left of the name indicates the object type.</span></span>  
  
 <span data-ttu-id="62cf5-113">**Тип**</span><span class="sxs-lookup"><span data-stu-id="62cf5-113">**Type**</span></span>  
 <span data-ttu-id="62cf5-114">Выводит тип зависимого объекта, который, возможно, нужно обработать.</span><span class="sxs-lookup"><span data-stu-id="62cf5-114">Displays the type of dependent object that may need to be processed.</span></span>  
  
 <span data-ttu-id="62cf5-115">**Тип воздействия**</span><span class="sxs-lookup"><span data-stu-id="62cf5-115">**Impact Type**</span></span>  
 <span data-ttu-id="62cf5-116">Отображает эффект, который обработка объектов в диалоговом окне **Обработка** оказывает на данный зависимый объект.</span><span class="sxs-lookup"><span data-stu-id="62cf5-116">Displays the effect that processing the objects in the **Process** dialog box has on the dependent object.</span></span> <span data-ttu-id="62cf5-117">Следующая таблица содержит список возможных эффектов от обработки и примечания, приводит ли это к предупреждению или ошибке.</span><span class="sxs-lookup"><span data-stu-id="62cf5-117">The following table lists the possible effects of processing and notes whether each one results in a warning or an error.</span></span>  
  
|<span data-ttu-id="62cf5-118">Последствия</span><span class="sxs-lookup"><span data-stu-id="62cf5-118">Impact</span></span>|<span data-ttu-id="62cf5-119">Сообщение</span><span class="sxs-lookup"><span data-stu-id="62cf5-119">Message</span></span>|  
|------------|-------------|  
|<span data-ttu-id="62cf5-120">Объект будет очищен (не обработан).</span><span class="sxs-lookup"><span data-stu-id="62cf5-120">Object will be cleared (unprocessed)</span></span>|<span data-ttu-id="62cf5-121">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="62cf5-121">Warning</span></span>|  
|<span data-ttu-id="62cf5-122">Объект может быть недопустимым.</span><span class="sxs-lookup"><span data-stu-id="62cf5-122">Object would be invalid</span></span>|<span data-ttu-id="62cf5-123">Ошибка</span><span class="sxs-lookup"><span data-stu-id="62cf5-123">Error</span></span>|  
|<span data-ttu-id="62cf5-124">Статистическая функция будет удалена.</span><span class="sxs-lookup"><span data-stu-id="62cf5-124">Aggregation would be dropped</span></span>|<span data-ttu-id="62cf5-125">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="62cf5-125">Warning</span></span>|  
|<span data-ttu-id="62cf5-126">Гибкая статистическая функция будет удалена.</span><span class="sxs-lookup"><span data-stu-id="62cf5-126">Flexible aggregation would be dropped</span></span>|<span data-ttu-id="62cf5-127">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="62cf5-127">Warning</span></span>|  
|<span data-ttu-id="62cf5-128">Индексы будут удалены.</span><span class="sxs-lookup"><span data-stu-id="62cf5-128">Indexes will be dropped</span></span>|<span data-ttu-id="62cf5-129">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="62cf5-129">Warning</span></span>|  
|<span data-ttu-id="62cf5-130">Объект, не являющийся потомком, будет обработан.</span><span class="sxs-lookup"><span data-stu-id="62cf5-130">Non-child object will be processed</span></span>|<span data-ttu-id="62cf5-131">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="62cf5-131">Warning</span></span>|  
  
 <span data-ttu-id="62cf5-132">**Обработать объект**</span><span class="sxs-lookup"><span data-stu-id="62cf5-132">**Process Object**</span></span>  
 <span data-ttu-id="62cf5-133">Выберите зависимые объекты, которые нужно обработать в данной операции обработки.</span><span class="sxs-lookup"><span data-stu-id="62cf5-133">Select the dependent objects that you want to process with the processing operation.</span></span> <span data-ttu-id="62cf5-134">Невыбранные зависимые объекты должны быть обработаны после завершения операции обработки.</span><span class="sxs-lookup"><span data-stu-id="62cf5-134">Dependent objects that are not selected must be processed after the processing operation is finished.</span></span> <span data-ttu-id="62cf5-135">В противном случае их нельзя будет использовать.</span><span class="sxs-lookup"><span data-stu-id="62cf5-135">Otherwise, they cannot be used.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62cf5-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="62cf5-136">See Also</span></span>  
 <span data-ttu-id="62cf5-137">[Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="62cf5-137">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="62cf5-138">Диалоговое окно "обработка" &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="62cf5-138">Process Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](process-dialog-box-analysis-services-multidimensional-data.md)  
  
  
