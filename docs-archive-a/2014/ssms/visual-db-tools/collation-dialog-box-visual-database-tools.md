---
title: Диалоговое окно "Параметры сортировки" (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.definecolumncollation
- vdtsql.chm:65561
ms.assetid: e4020f79-7abf-4839-b9b2-984ef7049817
author: stevestein
ms.author: sstein
ms.openlocfilehash: d551b2ae7ca27250c144afedf13038efd78ad6ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669209"
---
# <a name="collation-dialog-box-visual-database-tools"></a><span data-ttu-id="27bcb-102">Диалоговое окно «Параметры сортировки» (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="27bcb-102">Collation Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="27bcb-103">Это диалоговое окно позволяет указать параметры сортировки для столбца.</span><span class="sxs-lookup"><span data-stu-id="27bcb-103">This dialog box lets you specify a collation sequence for the column.</span></span> <span data-ttu-id="27bcb-104">Параметры сортировки столбца используются во всех операциях, сравнивающих значение столбца с другим столбцом или значением константы.</span><span class="sxs-lookup"><span data-stu-id="27bcb-104">A column's collation sequence is used in any operation that compares values of the column to another column or to constant values.</span></span> <span data-ttu-id="27bcb-105">Он также воздействует на некоторые символьные функции, например SUBSTRING или CHARINDEX.</span><span class="sxs-lookup"><span data-stu-id="27bcb-105">It also affects the behavior of some string functions, such as SUBSTRING and CHARINDEX.</span></span> <span data-ttu-id="27bcb-106">Подробный список воздействий параметров сортировки для столбца см. в документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27bcb-106">For a complete list of the effects of a column's collation setting, see the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentation.</span></span>  
  
 <span data-ttu-id="27bcb-107">Оно отображается:</span><span class="sxs-lookup"><span data-stu-id="27bcb-107">This dialog box appears:</span></span>  
  
-   <span data-ttu-id="27bcb-108">Если введено недопустимое имя параметров сортировки в поле **Параметры сортировки** на вкладке **Свойства столбца** .</span><span class="sxs-lookup"><span data-stu-id="27bcb-108">If you enter an invalid collation name in the **Collation** field on the **Column Properties** tab.</span></span>  
  
-   <span data-ttu-id="27bcb-109">Если перейти в поле **Параметры сортировки** на вкладке **Свойства столбца**, а затем нажать кнопку с многоточием ( **...** ) справа от него.</span><span class="sxs-lookup"><span data-stu-id="27bcb-109">If you click in the **Collation** field on the **Column Properties** tab, and then click the ellipsis button (**...**) to the right of the field.</span></span>  
  
## <a name="options"></a><span data-ttu-id="27bcb-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="27bcb-110">Options</span></span>  
 <span data-ttu-id="27bcb-111">**Параметры сортировки SQL**</span><span class="sxs-lookup"><span data-stu-id="27bcb-111">**SQL Collation**</span></span>  
 <span data-ttu-id="27bcb-112">Выберите из раскрывающегося списка один из параметров сортировки, определяемых [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27bcb-112">Choose among the collation sequences defined by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the drop-down list.</span></span>  
  
 <span data-ttu-id="27bcb-113">**Параметры сортировки Windows**</span><span class="sxs-lookup"><span data-stu-id="27bcb-113">**Windows Collation**</span></span>  
 <span data-ttu-id="27bcb-114">Выберите из раскрывающегося списка один из параметров сортировки, определенных в Windows.</span><span class="sxs-lookup"><span data-stu-id="27bcb-114">Choose among the collation sequences defined by Windows from the drop-down list.</span></span>  
  
 <span data-ttu-id="27bcb-115">**Двоичная сортировка**</span><span class="sxs-lookup"><span data-stu-id="27bcb-115">**Binary Sort**</span></span>  
 <span data-ttu-id="27bcb-116">Использовать при сравнении двоичные коды символов.</span><span class="sxs-lookup"><span data-stu-id="27bcb-116">Use the binary codes of character values for comparisons.</span></span> <span data-ttu-id="27bcb-117">При выборе этого значения некоторые параметры сравнения символов станут недоступны.</span><span class="sxs-lookup"><span data-stu-id="27bcb-117">If you select this option, certain alphabetic comparison options become unavailable.</span></span> <span data-ttu-id="27bcb-118">(Например, станет недоступно сравнение без учета регистра, так как символы в верхнем и нижнем регистрах имеют разные двоичных коды.)</span><span class="sxs-lookup"><span data-stu-id="27bcb-118">For example, case-insensitive comparisons become unavailable because uppercase letters and lowercase letters have different binary encodings.</span></span> <span data-ttu-id="27bcb-119">Применяется только при выборе значения **Параметры сортировки Windows**.</span><span class="sxs-lookup"><span data-stu-id="27bcb-119">Applies only if you select **Windows collation**.</span></span>  
  
 <span data-ttu-id="27bcb-120">**Словарная сортировка**</span><span class="sxs-lookup"><span data-stu-id="27bcb-120">**Dictionary Sort**</span></span>  
 <span data-ttu-id="27bcb-121">Использовать параметры алфавитного сравнения.</span><span class="sxs-lookup"><span data-stu-id="27bcb-121">Use alphabetic comparison options.</span></span> <span data-ttu-id="27bcb-122">Применяется только при выборе значения **Параметры сортировки Windows**.</span><span class="sxs-lookup"><span data-stu-id="27bcb-122">Applies only if you select **Windows collation**.</span></span> <span data-ttu-id="27bcb-123">Параметры алфавитного сравнения:</span><span class="sxs-lookup"><span data-stu-id="27bcb-123">The alphabetic comparisons options are:</span></span>  
  
-   <span data-ttu-id="27bcb-124">**С учетом регистра** . Выберите, если при сравнении необходимо, чтобы прописные и строчные буквы были не эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="27bcb-124">**Case Sensitive** Select this if you want comparisons to consider uppercase and lowercase letters to be unequal.</span></span>  
  
-   <span data-ttu-id="27bcb-125">**С учетом диакритических знаков** . Выберите, если при сравнении необходимо, чтобы буквы с диакритическими знаками и без них были не эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="27bcb-125">**Accent Sensitive** Select this if you want comparisons to consider accented and unaccented letters to be unequal.</span></span> <span data-ttu-id="27bcb-126">При выборе этого параметра в операции сравнения будет считаться, что символы с разными диакритическими знаками также не эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="27bcb-126">If you select this, comparisons will also consider differently accented letters to be unequal.</span></span>  
  
-   <span data-ttu-id="27bcb-127">**С учетом типа японской азбуки** . Выберите этот параметр, если необходимо, чтобы символы в японских азбуках хирагана и катакана были не эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="27bcb-127">**Kana Sensitive** Select this if you want comparisons to consider katakana and hiragana Japanese syllables to be unequal.</span></span>  
  
-   <span data-ttu-id="27bcb-128">**С учетом ширины** . Выберите этот параметр, если при сравнении необходимо, чтобы полуширинные и полноширинные символы были не эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="27bcb-128">**Width Sensitive** Select this if you want comparisons to consider half-width and full-width characters to be unequal.</span></span>  
  
 <span data-ttu-id="27bcb-129">**Кнопка «Восстановить значения по умолчанию»**</span><span class="sxs-lookup"><span data-stu-id="27bcb-129">**Restore Default Button**</span></span>  
 <span data-ttu-id="27bcb-130">Применить для данного столбца параметры сортировки по умолчанию для базы данных.</span><span class="sxs-lookup"><span data-stu-id="27bcb-130">Apply the default collation sequence for the database to the column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27bcb-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="27bcb-131">See Also</span></span>  
 [<span data-ttu-id="27bcb-132">Работа со столбцами в статистических запросах (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="27bcb-132">Work with Columns in Aggregate Queries &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
