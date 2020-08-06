---
title: Основные принципы создания скриптов многомерных выражений (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cubes [Analysis Services], scripts
- calculations [Analysis Services], scripts
- MDX [Analysis Services], scripts
- scripts [MDX]
- cubes [Analysis Services], calculations
- Multidimensional Expressions [Analysis Services], scripts
ms.assetid: fdecb3ce-7c87-4bab-8000-532ba7a29f96
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2f7638339d8fc366ee384d453f6df683f3bd41f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666830"
---
# <a name="mdx-scripting-fundamentals-analysis-services"></a><span data-ttu-id="4f0a3-102">Основные принципы создания скриптов многомерных выражений (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="4f0a3-102">MDX Scripting Fundamentals (Analysis Services)</span></span>
  <span data-ttu-id="4f0a3-103">В [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] скрипты многомерных выражений состоят из одного или нескольких многомерных выражений или инструкций, заполняющих куб вычислениями.</span><span class="sxs-lookup"><span data-stu-id="4f0a3-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], a Multidimensional Expressions (MDX) script is made up of one or more MDX expressions or statements that populate a cube with calculations.</span></span>  
  
 <span data-ttu-id="4f0a3-104">Скрипт многомерных выражений определяет процесс вычислений для куба.</span><span class="sxs-lookup"><span data-stu-id="4f0a3-104">An MDX script defines the calculation process for a cube.</span></span> <span data-ttu-id="4f0a3-105">Скрипт многомерных выражений также считается частью самого куба.</span><span class="sxs-lookup"><span data-stu-id="4f0a3-105">An MDX script is also considered part of the cube itself.</span></span> <span data-ttu-id="4f0a3-106">Поэтому изменение скрипта многомерных выражений, связанного с кубом, сразу изменяет процесс вычислений для куба.</span><span class="sxs-lookup"><span data-stu-id="4f0a3-106">Therefore, changing an MDX script associated with a cube immediately changes the calculation process for the cube.</span></span>  
  
 <span data-ttu-id="4f0a3-107">Для создания скриптов многомерных выражений можно воспользоваться конструктором кубов в [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f0a3-107">To create MDX scripts, you can use Cube Designer in the [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="4f0a3-108">Дополнительные сведения см. в разделах [Определение назначений и других команд скриптов](../define-assignments-and-other-script-commands.md) и [Введение в сценарии многомерных выражений в Microsoft SQL Server 2005](https://go.microsoft.com/fwlink/?LinkId=81892).</span><span class="sxs-lookup"><span data-stu-id="4f0a3-108">For more information, see [Define Assignments and Other Script Commands](../define-assignments-and-other-script-commands.md) and [Introduction to MDX Scripting in Microsoft SQL Server 2005](https://go.microsoft.com/fwlink/?LinkId=81892).</span></span>  
  
 <span data-ttu-id="4f0a3-109">Сведения о проблемах безопасности, связанных с запросами и вычислениями MDX см. в разделе по оптимизации MDX в [SQL Server Analysis Services Performance Guide (руководстве по производительности служб SQL Server Analysis Services)](https://go.microsoft.com/fwlink/p/?LinkId=399050).</span><span class="sxs-lookup"><span data-stu-id="4f0a3-109">For performance issues related to MDX queries and calculations, see the MDX optimization section in the [SQL Server Analysis Services Performance Guide](https://go.microsoft.com/fwlink/p/?LinkId=399050).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f0a3-110">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="4f0a3-110">In This Section</span></span>  
  
|<span data-ttu-id="4f0a3-111">Раздел</span><span class="sxs-lookup"><span data-stu-id="4f0a3-111">Topic</span></span>|<span data-ttu-id="4f0a3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4f0a3-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="4f0a3-113">Базовый скрипт многомерных выражений (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="4f0a3-113">The Basic MDX Script &#40;MDX&#41;</span></span>](the-basic-mdx-script-mdx.md)|<span data-ttu-id="4f0a3-114">Подробные сведения о базовых скриптах многомерных выражений, включая описание скрипта многомерных выражений по умолчанию, предусмотренного в каждом кубе, а также описание общих принципов функционирования скриптов многомерных выражений в кубах служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f0a3-114">Details the basic MDX script, including the default MDX script provided in each cube, and how MDX scripts generally function within a cube in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="4f0a3-115">Управление областью и контекстом (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="4f0a3-115">Managing Scope and Context &#40;MDX&#41;</span></span>](managing-scope-and-context-mdx.md)|<span data-ttu-id="4f0a3-116">Использование инструкций [CALCULATE](/sql/mdx/mdx-scripting-calculate) и [SCOPE](/sql/mdx/mdx-scripting-scope) и функции [This](/sql/mdx/this-mdx) для управления контекстом и областью действия в скриптах многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="4f0a3-116">Describes how to use the [CALCULATE](/sql/mdx/mdx-scripting-calculate) statement, the [SCOPE](/sql/mdx/mdx-scripting-scope) statement, and the [This](/sql/mdx/this-mdx) function to manage context and scope within an MDX script.</span></span>|  
|[<span data-ttu-id="4f0a3-117">Переменные и параметры (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="4f0a3-117">Using Variables and Parameters &#40;MDX&#41;</span></span>](using-variables-and-parameters-mdx.md)|<span data-ttu-id="4f0a3-118">Использование переменных и параметров в скриптах многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="4f0a3-118">Describes how to use variables and parameters in an MDX script.</span></span>|  
|[<span data-ttu-id="4f0a3-119">Обработка ошибок (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="4f0a3-119">Error Handling &#40;MDX&#41;</span></span>](error-handling-mdx.md)|<span data-ttu-id="4f0a3-120">Обработка ошибок в скриптах многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="4f0a3-120">Explains error handling within an MDX script.</span></span>|  
|[<span data-ttu-id="4f0a3-121">Поддержка многомерных выражений (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="4f0a3-121">Supported MDX &#40;MDX&#41;</span></span>](supported-mdx-mdx.md)|<span data-ttu-id="4f0a3-122">Перечень операторов, инструкций и функций многомерных выражений, поддерживаемых в скриптах многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="4f0a3-122">Provides a list of supported MDX operators, statements, and functions within an MDX script.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f0a3-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="4f0a3-123">See Also</span></span>  
 [<span data-ttu-id="4f0a3-124">Справочник по языку многомерных выражений (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="4f0a3-124">MDX Language Reference &#40;MDX&#41;</span></span>](/sql/mdx/mdx-language-reference-mdx)  
  
  
