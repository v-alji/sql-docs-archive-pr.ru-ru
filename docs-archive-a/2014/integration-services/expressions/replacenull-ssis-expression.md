---
title: REPLACENULL (выражение служб SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 70db7832-b5a0-4db5-a8ad-42ad8630d8e8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f10bb6ef6102076fe7b1cc236461e2358ad96372
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732821"
---
# <a name="replacenull-ssis-expression"></a><span data-ttu-id="f711e-102">REPLACENULL (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="f711e-102">REPLACENULL (SSIS Expression)</span></span>
  <span data-ttu-id="f711e-103">Возвращает значение второго параметра выражения, если значение первого параметра равно NULL. В противном случае возвращает значение первого выражения.</span><span class="sxs-lookup"><span data-stu-id="f711e-103">Returns the value of second expression parameter if the value of first expression parameter is NULL; otherwise, returns the value of first expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f711e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f711e-104">Syntax</span></span>  
  
```vb  
REPLACENULL(expression 1,expression 2)  
```  
  
## <a name="arguments"></a><span data-ttu-id="f711e-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f711e-105">Arguments</span></span>  
 <span data-ttu-id="f711e-106">*выражение 1*</span><span class="sxs-lookup"><span data-stu-id="f711e-106">*expression 1*</span></span>  
 <span data-ttu-id="f711e-107">Результат этого выражения проверяется на соответствие значению NULL.</span><span class="sxs-lookup"><span data-stu-id="f711e-107">The result of this expression is checked against NULL.</span></span>  
  
 <span data-ttu-id="f711e-108">*выражение 2*</span><span class="sxs-lookup"><span data-stu-id="f711e-108">*expression 2*</span></span>  
 <span data-ttu-id="f711e-109">Результат этого выражения возвращается, если значением первого выражения является NULL.</span><span class="sxs-lookup"><span data-stu-id="f711e-109">The result of this expression is returned if the first expression evaluates to NULL.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="f711e-110">Типы результата</span><span class="sxs-lookup"><span data-stu-id="f711e-110">Result Types</span></span>  
 <span data-ttu-id="f711e-111">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="f711e-111">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f711e-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="f711e-112">Remarks</span></span>  
  
-   <span data-ttu-id="f711e-113">Длина *expression 2* может быть нулевой.</span><span class="sxs-lookup"><span data-stu-id="f711e-113">The length of *expression 2* may be zero.</span></span>  
  
-   <span data-ttu-id="f711e-114">Функция REPLACENULL возвращает NULL, если значение любого из аргументов равно NULL.</span><span class="sxs-lookup"><span data-stu-id="f711e-114">REPLACENULL returns a null result if any argument is null.</span></span>  
  
-   <span data-ttu-id="f711e-115">Столбцы типа BLOB (DT_TEXT, DT_NTEXT, DT_IMAGE) не поддерживаются ни для одного из параметров.</span><span class="sxs-lookup"><span data-stu-id="f711e-115">BLOB columns (DT_TEXT, DT_NTEXT, DT_IMAGE) are not supported for either parameter.</span></span>  
  
-   <span data-ttu-id="f711e-116">Предполагается, что два выражения будут иметь одинаковый возвращаемый тип.</span><span class="sxs-lookup"><span data-stu-id="f711e-116">The two expressions are expected to have the same return type.</span></span> <span data-ttu-id="f711e-117">Если это не так, то функция попытается преобразовать второе выражение в возвращаемый тип первого выражения, что может привести к возникновению ошибки, если типы данных несовместимы.</span><span class="sxs-lookup"><span data-stu-id="f711e-117">If they do not, the function attempts to cast the 2nd expression to the return type of the 1st expression, which may result in an error if the data types are incompatible.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="f711e-118">Примеры выражений</span><span class="sxs-lookup"><span data-stu-id="f711e-118">Expression Examples</span></span>  
 <span data-ttu-id="f711e-119">В следующем примере все значения NULL в столбце базы данных заменяются строкой (1900-01-01).</span><span class="sxs-lookup"><span data-stu-id="f711e-119">The following example replaces any NULL value in a database column with a string (1900-01-01).</span></span> <span data-ttu-id="f711e-120">Эта функция применяется сугубо в стандартных шаблонах производных столбцов, где значения NULL необходимо заменить другими значениями.</span><span class="sxs-lookup"><span data-stu-id="f711e-120">This function is especially used in common Derived Column patterns where you want to replace NULL values with something else.</span></span>  
  
```  
REPLACENULL(MyColumn, "1900-01-01")  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f711e-121">Следующий пример демонстрирует, как это было выполнено в [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)]/[!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f711e-121">The following example shows how it was done in [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)]/[!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)].</span></span>  
  
```  
(DT_DBTIMESTAMP) (ISNULL(MyColumn) ? "1900-01-01" : MyColumn)   
```  
  
  
