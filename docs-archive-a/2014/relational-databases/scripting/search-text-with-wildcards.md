---
title: Поиск текста с символами-шаблонами
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- vswildcardsbuilder
helpviewer_keywords:
- searches [SQL Server Management Studio], wildcards
- Query Editor [SQL Server Management Studio], wildcard searches
- wildcard options [SQL Server Management Studio]
ms.assetid: 449600f8-cc87-4b3f-878a-59c158a88a40
author: rothja
ms.author: jroth
ms.openlocfilehash: cc4e24c3dce73e46350b0c106429c42ab5f0edb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668739"
---
# <a name="search-text-with-wildcards"></a><span data-ttu-id="84cad-102">Поиск текста с символами-шаблонами</span><span class="sxs-lookup"><span data-stu-id="84cad-102">Search Text with Wildcards</span></span>
  <span data-ttu-id="84cad-103">С помощью приведенных ниже выражений можно заменять символы либо цифры в поле **Найти** в диалоговом окне [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]Найти и заменить**в**.</span><span class="sxs-lookup"><span data-stu-id="84cad-103">The following expressions can replace characters or digits in the **Find what** field of the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Find and Replace** dialog box.</span></span>  
  
#### <a name="to-search-using-wildcards"></a><span data-ttu-id="84cad-104">Осуществление поиска с шаблонами</span><span class="sxs-lookup"><span data-stu-id="84cad-104">To search using wildcards</span></span>  
  
1.  <span data-ttu-id="84cad-105">Чтобы включить использование шаблонов в поле **Найти** во время операций «Быстрый поиск», **Найти в файлах**, **Быстрая замена**или **Заменить в файлах** , выберите **Использовать** в области **Параметры поиска** , а затем установите флажок **Подстановочные знаки**.</span><span class="sxs-lookup"><span data-stu-id="84cad-105">To enable the use of wildcards in the **Find what** field during Quick Find, **Find in Files**, **Quick Replace**, or **Replace in Files** operations, select the **Use** option under **Find Options** and then choose **Wildcards**.</span></span>  
  
2.  <span data-ttu-id="84cad-106">В этом случае становится доступной треугольная кнопка **Список ссылок** , расположенная рядом с полем **Найти** .</span><span class="sxs-lookup"><span data-stu-id="84cad-106">The triangular **Reference List** button next to the **Find what** field then becomes available.</span></span> <span data-ttu-id="84cad-107">Нажмите эту кнопку, чтобы отобразить список доступных шаблонов.</span><span class="sxs-lookup"><span data-stu-id="84cad-107">Click this button to display a list of the available wildcards.</span></span> <span data-ttu-id="84cad-108">При выборе любого элемента в **Списке подстановки**он будет вставлен в строку **Найти** .</span><span class="sxs-lookup"><span data-stu-id="84cad-108">When you choose any item from the **Reference List**, it is inserted into the **Find what** string.</span></span>  
  
 <span data-ttu-id="84cad-109">Следующая таблица содержит описание шаблонов, доступных через **Список подстановки**.</span><span class="sxs-lookup"><span data-stu-id="84cad-109">The following table describes the wildcards available in the **Reference List**.</span></span>  
  
|<span data-ttu-id="84cad-110">Выражение</span><span class="sxs-lookup"><span data-stu-id="84cad-110">Expression</span></span>|<span data-ttu-id="84cad-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84cad-111">Syntax</span></span>|<span data-ttu-id="84cad-112">Description</span><span class="sxs-lookup"><span data-stu-id="84cad-112">Description</span></span>|  
|----------------|------------|-----------------|  
|<span data-ttu-id="84cad-113">Любой отдельный символ</span><span class="sxs-lookup"><span data-stu-id="84cad-113">Any single character</span></span>|<span data-ttu-id="84cad-114">?</span><span class="sxs-lookup"><span data-stu-id="84cad-114">?</span></span>|<span data-ttu-id="84cad-115">Соответствует любому отдельному символу.</span><span class="sxs-lookup"><span data-stu-id="84cad-115">Matches any single character.</span></span>|  
|<span data-ttu-id="84cad-116">Любая отдельная цифра</span><span class="sxs-lookup"><span data-stu-id="84cad-116">Any single digit</span></span>|#|<span data-ttu-id="84cad-117">Соответствует любой отдельной цифре.</span><span class="sxs-lookup"><span data-stu-id="84cad-117">Matches any single digit.</span></span> <span data-ttu-id="84cad-118">Например, выражение 7# соответствует числам, начинающимся с 7 и содержащим еще одну цифру, например 71, но не 17.</span><span class="sxs-lookup"><span data-stu-id="84cad-118">For example, 7# matches numbers that include 7 followed by another number, such as 71, but not 17.</span></span>|  
|<span data-ttu-id="84cad-119">Символы вне набора</span><span class="sxs-lookup"><span data-stu-id="84cad-119">Characters not in set</span></span>|<span data-ttu-id="84cad-120">[!</span><span class="sxs-lookup"><span data-stu-id="84cad-120">[!</span></span> <span data-ttu-id="84cad-121">]</span><span class="sxs-lookup"><span data-stu-id="84cad-121">]</span></span>|<span data-ttu-id="84cad-122">Соответствует любому символу, кроме заданных в наборе.</span><span class="sxs-lookup"><span data-stu-id="84cad-122">Matches any one character that is not specified in the set.</span></span>|  
|<span data-ttu-id="84cad-123">Один или несколько символов</span><span class="sxs-lookup"><span data-stu-id="84cad-123">One or more characters</span></span>|*|<span data-ttu-id="84cad-124">Соответствует одному или нескольким символам.</span><span class="sxs-lookup"><span data-stu-id="84cad-124">Matches any one or more characters.</span></span> <span data-ttu-id="84cad-125">Например, выражение new\* соответствует любому тексту, включающему подстроку «new», например newfile.txt.</span><span class="sxs-lookup"><span data-stu-id="84cad-125">For example, new\* matches any text that includes "new", such as newfile.txt.</span></span>|  
|<span data-ttu-id="84cad-126">Набор символов</span><span class="sxs-lookup"><span data-stu-id="84cad-126">Set of characters</span></span>|<span data-ttu-id="84cad-127">[ ]</span><span class="sxs-lookup"><span data-stu-id="84cad-127">[ ]</span></span>|<span data-ttu-id="84cad-128">Соответствует любому из символов, заданных в наборе.</span><span class="sxs-lookup"><span data-stu-id="84cad-128">Matches any one of the characters specified in the set.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="84cad-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="84cad-129">See Also</span></span>  
 <span data-ttu-id="84cad-130">[Поиск и замена](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="84cad-130">[Search and Replace](search-and-replace.md) </span></span>  
 [<span data-ttu-id="84cad-131">Поиск текста с помощью регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="84cad-131">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
