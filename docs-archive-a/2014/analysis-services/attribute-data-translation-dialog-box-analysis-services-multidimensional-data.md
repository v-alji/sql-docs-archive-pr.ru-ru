---
title: Диалоговое окно «Перевод данных атрибута» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.dimensionstoragesettings.f1
helpviewer_keywords:
- Attribute Data Translation dialog box
ms.assetid: bed286de-1e9b-49de-b09e-3cd076aba152
author: minewiskan
ms.author: owend
ms.openlocfilehash: b61022ec2cb8726fc034e13a0d63e432df6ec151
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656887"
---
# <a name="attribute-data-translation-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="9c036-102">Диалоговое окно «Перевод данных атрибута» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="9c036-102">Attribute Data Translation Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="9c036-103">Диалоговое окно **Перевод данных атрибута** используется для задания столбца, содержащего данные заголовка перевода, а также значения параметров сортировки и порядка сортировки, которые должны быть применены к переведенным данным.</span><span class="sxs-lookup"><span data-stu-id="9c036-103">Use the **Attribute Data Translation** dialog box to set the column that contains the translation caption data, as well as the collation and sort order to be used with the translated data.</span></span> <span data-ttu-id="9c036-104">Диалоговое окно **Перевод данных атрибута** может отображаться следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9c036-104">You can display the **Attribute Data Translation** dialog box by:</span></span>  
  
-   <span data-ttu-id="9c036-105">Щелчком **Создать столбец заголовков** или **Редактировать столбец заголовков** на **Панели инструментов** вкладки **Переводы** компонента **Конструктор измерений**.</span><span class="sxs-lookup"><span data-stu-id="9c036-105">Clicking **New caption column** or **Edit caption column** from the **Toolbar** pane on the **Translations** tab of **Dimension Designer**.</span></span>  
  
-   <span data-ttu-id="9c036-106">Щелкнуть правой кнопкой мыши панель **Подробности перевода** на вкладке **Переводы\*\*\*\*конструктора измерений** и выбрать команду **Создать столбец заголовков** или **Изменить столбец заголовков**.</span><span class="sxs-lookup"><span data-stu-id="9c036-106">Right-clicking the **Translation Details** pane on the **Translations** tab of **Dimension Designer** and selecting **New caption column** or **Edit caption column**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9c036-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="9c036-107">Options</span></span>  
 <span data-ttu-id="9c036-108">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="9c036-108">**Attribute**</span></span>  
 <span data-ttu-id="9c036-109">Отображает выбранный атрибут.</span><span class="sxs-lookup"><span data-stu-id="9c036-109">Displays the selected attribute.</span></span>  
  
 <span data-ttu-id="9c036-110">**Язык**</span><span class="sxs-lookup"><span data-stu-id="9c036-110">**Language**</span></span>  
 <span data-ttu-id="9c036-111">Отображает выбранный язык.</span><span class="sxs-lookup"><span data-stu-id="9c036-111">Displays the selected language.</span></span>  
  
 <span data-ttu-id="9c036-112">**Переведенный заголовок**</span><span class="sxs-lookup"><span data-stu-id="9c036-112">**Translated caption**</span></span>  
 <span data-ttu-id="9c036-113">Устанавливается текущий переведенный заголовок для выбранного атрибута.</span><span class="sxs-lookup"><span data-stu-id="9c036-113">Sets the current translated caption for the selected attribute.</span></span>  
  
 <span data-ttu-id="9c036-114">**Столбцы перевода**</span><span class="sxs-lookup"><span data-stu-id="9c036-114">**Translation columns**</span></span>  
 <span data-ttu-id="9c036-115">Задает столбец, в котором сохраняются данные заголовка перевода.</span><span class="sxs-lookup"><span data-stu-id="9c036-115">Sets the column where the translation caption data is stored.</span></span> <span data-ttu-id="9c036-116">Может быть выбран только один столбец.</span><span class="sxs-lookup"><span data-stu-id="9c036-116">Only one column can be selected.</span></span> <span data-ttu-id="9c036-117">Отображаются все связанные таблицы, на которые имеются ссылки из первичной таблицы измерения.</span><span class="sxs-lookup"><span data-stu-id="9c036-117">All related tables that are referred to by the primary dimension table will be displayed.</span></span>  
  
 <span data-ttu-id="9c036-118">**Обозначение параметров сортировки**</span><span class="sxs-lookup"><span data-stu-id="9c036-118">**Collation designator**</span></span>  
 <span data-ttu-id="9c036-119">Устанавливает обозначение параметров сортировки для выбранного атрибута.</span><span class="sxs-lookup"><span data-stu-id="9c036-119">Sets the collation designator for the selected attribute.</span></span> <span data-ttu-id="9c036-120">По умолчанию выбираются текущие параметры сортировки Windows.</span><span class="sxs-lookup"><span data-stu-id="9c036-120">By default, the current Windows collation is selected.</span></span> <span data-ttu-id="9c036-121">Для выбора из имеющихся параметров сортировки щелкните стрелку вниз.</span><span class="sxs-lookup"><span data-stu-id="9c036-121">Click the down arrow to select from the available collations.</span></span>  
  
 <span data-ttu-id="9c036-122">**Двоичный**</span><span class="sxs-lookup"><span data-stu-id="9c036-122">**Binary**</span></span>  
 <span data-ttu-id="9c036-123">Выберите этот параметр для сортировки и сравнения данных на основе двоичных шаблонов, определенных для каждого символа.</span><span class="sxs-lookup"><span data-stu-id="9c036-123">Select this option to sort and compare data based on the bit patterns defined for each character.</span></span> <span data-ttu-id="9c036-124">Двоичный порядок сортировки учитывает регистр, то есть нижний регистр предшествует верхнему, а также учитывает диакритические знаки.</span><span class="sxs-lookup"><span data-stu-id="9c036-124">Binary sort order is case-sensitive, that is, lowercase precedes uppercase, and accent-sensitive.</span></span> <span data-ttu-id="9c036-125">Это самый быстрый порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="9c036-125">This is the fastest sorting order.</span></span>  
  
 <span data-ttu-id="9c036-126">Если данный параметр не выбран, службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] используют правила сортировки и сравнения, как описано в словарях для соответствующего языка или алфавита.</span><span class="sxs-lookup"><span data-stu-id="9c036-126">If this option is not selected, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] follows sorting and comparison rules as defined in dictionaries for the associated language or alphabet.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9c036-127">Если данный параметр выбран, параметры **С учетом регистра**, **С учетом диакритических знаков**, **С учетом типа японской азбуки**и **С учетом ширины** отключены.</span><span class="sxs-lookup"><span data-stu-id="9c036-127">If this option is selected, the **Case sensitive**, **Accent sensitive**, **Kana sensitive**, and **Width sensitive** options are disabled.</span></span>  
  
 <span data-ttu-id="9c036-128">**С учетом регистра**</span><span class="sxs-lookup"><span data-stu-id="9c036-128">**Case sensitive**</span></span>  
 <span data-ttu-id="9c036-129">Выберите этот параметр для сортировки и сравнения данных на основе словарных правил для соответствующего языка или алфавита, а также для различия букв верхнего и нижнего регистров.</span><span class="sxs-lookup"><span data-stu-id="9c036-129">Select this option to sort and compare data based on the dictionary rules provided for the associated language or alphabet, and to distinguish between uppercase and lowercase letters.</span></span>  
  
 <span data-ttu-id="9c036-130">Если этот параметр не выбран, службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] не различают буквы верхнего и нижнего регистра.</span><span class="sxs-lookup"><span data-stu-id="9c036-130">If not selected, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considers the uppercase and lowercase versions of letters to be equal.</span></span> [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]<span data-ttu-id="9c036-131">не определяет, сортируются ли строчные буквы по нижнему или верхнему регистру в соответствии с прописными буквами, если не выбрано значение **с учетом регистра** .</span><span class="sxs-lookup"><span data-stu-id="9c036-131">does not define whether lowercase letters sort lower or higher in relation to uppercase letters when **Case-sensitive** is not selected.</span></span>  
  
 <span data-ttu-id="9c036-132">**Учитывать диакритические знаки**</span><span class="sxs-lookup"><span data-stu-id="9c036-132">**Accent sensitive**</span></span>  
 <span data-ttu-id="9c036-133">Выберите этот параметр для сортировки и сравнения данных на основе словарных правил для соответствующего языка или алфавита и для различения символов с диакритическими знаками и без них.</span><span class="sxs-lookup"><span data-stu-id="9c036-133">Select this option to sort and compare data based on the dictionary rules provided for the associated language or alphabet, and to distinguish between accented and unaccented characters.</span></span> <span data-ttu-id="9c036-134">Например, «a» не равно «á».</span><span class="sxs-lookup"><span data-stu-id="9c036-134">For example, 'a' is not equal to 'á'.</span></span>  
  
 <span data-ttu-id="9c036-135">Если этот параметр не выбран, службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] рассматривают символы с диакритическими знаками и без них как одинаковые.</span><span class="sxs-lookup"><span data-stu-id="9c036-135">If not selected, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considers the accented and unaccented versions of letters to be equal.</span></span>  
  
 <span data-ttu-id="9c036-136">**С учетом типа японской азбуки**</span><span class="sxs-lookup"><span data-stu-id="9c036-136">**Kana sensitive**</span></span>  
 <span data-ttu-id="9c036-137">Выберите этот параметр для сортировки и сравнения данных на основе словарных правил для соответствующего языка или алфавита, а также для различия двух типов японской азбуки: хирагана и катакана.</span><span class="sxs-lookup"><span data-stu-id="9c036-137">Select this option to sort and compare data based on the dictionary rules provided for the associated language or alphabet, and to distinguish between the two types of Japanese kana characters: Hiragana and Katakana.</span></span>  
  
 <span data-ttu-id="9c036-138">Если этот параметр не выбран, службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] рассматривают символы этих азбук как одинаковые.</span><span class="sxs-lookup"><span data-stu-id="9c036-138">If not selected, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considers Hiragana and Katakana characters to be equal.</span></span>  
  
 <span data-ttu-id="9c036-139">**С учетом ширины**</span><span class="sxs-lookup"><span data-stu-id="9c036-139">**Width sensitive**</span></span>  
 <span data-ttu-id="9c036-140">Выберите этот параметр для сортировки и сравнения данных на основе словарных правил для соответствующего языка или алфавита, а также для различия однобайтового символа (с половиной ширины) и того же символа, представленного двумя байтами (с полной шириной).</span><span class="sxs-lookup"><span data-stu-id="9c036-140">Select this option to sort and compare data based on the dictionary rules provided for the associated language or alphabet, and to distinguish between a single-byte character (half-width) and the same character when represented as a double-byte character (full-width).</span></span>  
  
 <span data-ttu-id="9c036-141">Если этот параметр не выбран, службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] рассматривают символы в однобайтном и двухбайтном представлении как одинаковые.</span><span class="sxs-lookup"><span data-stu-id="9c036-141">If not selected, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] considers the single-byte and double-byte representation of the same character to be equal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c036-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="9c036-142">See Also</span></span>  
 <span data-ttu-id="9c036-143">[Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="9c036-143">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="9c036-144">Сведения о переводе &#40;вкладка Переводы, конструктор измерений&#41; &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="9c036-144">Translation Details &#40;Translations Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](translation-details-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
