---
title: REVERSE (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- REVERSE function
- reverse character expressions
ms.assetid: bcebcc55-7247-4896-8f53-4d582d58cfb4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2ace136eed0abcb9df7b25d9370c46d7556c1d48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732814"
---
# <a name="reverse-ssis-expression"></a><span data-ttu-id="7bf47-102">REVERSE (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="7bf47-102">REVERSE (SSIS Expression)</span></span>
  <span data-ttu-id="7bf47-103">Возвращает символьное выражение в обратном порядке.</span><span class="sxs-lookup"><span data-stu-id="7bf47-103">Returns a character expression in reverse order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bf47-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7bf47-104">Syntax</span></span>  
  
```  
  
REVERSE(character_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="7bf47-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="7bf47-105">Arguments</span></span>  
 <span data-ttu-id="7bf47-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="7bf47-106">*character_expression*</span></span>  
 <span data-ttu-id="7bf47-107">Символьное выражение, в котором требуется поменять порядок символов на обратный.</span><span class="sxs-lookup"><span data-stu-id="7bf47-107">Is a character expression to be reversed.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7bf47-108">Типы результата</span><span class="sxs-lookup"><span data-stu-id="7bf47-108">Result Types</span></span>  
 <span data-ttu-id="7bf47-109">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="7bf47-109">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bf47-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="7bf47-110">Remarks</span></span>  
 <span data-ttu-id="7bf47-111">Аргумент *character_expression* должен иметь тип данных DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="7bf47-111">The *character_expression* argument must have the DT_WSTR data type.</span></span>  
  
 <span data-ttu-id="7bf47-112">Функция TOKEN возвращает значение NULL, если строка *character_expression* имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="7bf47-112">REVERSE returns a null result if *character_expression* is null.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="7bf47-113">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="7bf47-113">Expression Examples</span></span>  
 <span data-ttu-id="7bf47-114">В данном примере используется строковый литерал.</span><span class="sxs-lookup"><span data-stu-id="7bf47-114">This example uses a string literal.</span></span> <span data-ttu-id="7bf47-115">Возвращаемый результат: «ekiB niatnuoM».</span><span class="sxs-lookup"><span data-stu-id="7bf47-115">The return result is "ekiB niatnuoM".</span></span>  
  
```  
REVERSE("Mountain Bike")  
```  
  
 <span data-ttu-id="7bf47-116">В данном примере используется переменная.</span><span class="sxs-lookup"><span data-stu-id="7bf47-116">This example uses a variable.</span></span> <span data-ttu-id="7bf47-117">Если переменная **Name** содержит выражение «Touring Bike», будет возвращен результат «ekiB gniruoT».</span><span class="sxs-lookup"><span data-stu-id="7bf47-117">If **Name** contains Touring Bike, the return result is "ekiB gniruoT".</span></span>  
  
```  
REVERSE(@Name)  
```  
  
## <a name="see-also"></a><span data-ttu-id="7bf47-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="7bf47-118">See Also</span></span>  
 [<span data-ttu-id="7bf47-119">Функции (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="7bf47-119">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
