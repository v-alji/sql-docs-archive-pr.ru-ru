---
title: Редактор преобразования "процентная выборка" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.percentagesamplingtransformation.f1
helpviewer_keywords:
- Percentage Sampling Transformation Editor
ms.assetid: 2c40d804-26a3-4d35-809b-bc923d83d451
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c4dbd96ab952b6c88bdaa7bf56a0a2f1b3585c57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655806"
---
# <a name="percentage-sampling-transformation-editor"></a><span data-ttu-id="0a868-102">редактор преобразования «Процентная выборка»</span><span class="sxs-lookup"><span data-stu-id="0a868-102">Percentage Sampling Transformation Editor</span></span>
  <span data-ttu-id="0a868-103">Используйте диалоговое окно **Редактор преобразования «Процентная выборка»** для выборки части входных данных по заданному проценту строк.</span><span class="sxs-lookup"><span data-stu-id="0a868-103">Use the **Percentage Sampling Transformation Editor** dialog box to split part of an input into a sample using a specified percentage of rows.</span></span> <span data-ttu-id="0a868-104">Это преобразование разделяет входные данные на два отдельных вывода.</span><span class="sxs-lookup"><span data-stu-id="0a868-104">This transformation divides the input into two separate outputs.</span></span>  
  
 <span data-ttu-id="0a868-105">Дополнительные сведения о преобразовании «Процентная выборка» см. в разделе [Percentage Sampling Transformation](data-flow/transformations/percentage-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="0a868-105">To learn more about the percentage sampling transformation, see [Percentage Sampling Transformation](data-flow/transformations/percentage-sampling-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="0a868-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="0a868-106">Options</span></span>  
 <span data-ttu-id="0a868-107">**Процент строк**</span><span class="sxs-lookup"><span data-stu-id="0a868-107">**Percentage of rows**</span></span>  
 <span data-ttu-id="0a868-108">Задает процент строк во входных данных для использования в качестве выборки.</span><span class="sxs-lookup"><span data-stu-id="0a868-108">Specify the percentage of rows in the input to use as a sample.</span></span>  
  
 <span data-ttu-id="0a868-109">Значение этого свойства можно задать с помощью выражения свойства.</span><span class="sxs-lookup"><span data-stu-id="0a868-109">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="0a868-110">**Имя выхода выборки**</span><span class="sxs-lookup"><span data-stu-id="0a868-110">**Sample output name**</span></span>  
 <span data-ttu-id="0a868-111">Задайте уникальное имя выхода, содержащего строки выборки.</span><span class="sxs-lookup"><span data-stu-id="0a868-111">Provide a unique name for the output that will include the sampled rows.</span></span> <span data-ttu-id="0a868-112">Это имя будет отображаться в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a868-112">The name provided will be displayed within the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="0a868-113">**Имя вывода невыбранных элементов**</span><span class="sxs-lookup"><span data-stu-id="0a868-113">**Unselected output name**</span></span>  
 <span data-ttu-id="0a868-114">Задает уникальное имя выхода, который содержит строки, исключенные из выборки.</span><span class="sxs-lookup"><span data-stu-id="0a868-114">Provide a unique name for the output that will contain the rows excluded from the sampling.</span></span> <span data-ttu-id="0a868-115">Это имя будет отображаться в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a868-115">The name provided will be displayed within the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="0a868-116">**Использовать следующее начальное значение**</span><span class="sxs-lookup"><span data-stu-id="0a868-116">**Use the following random seed**</span></span>  
 <span data-ttu-id="0a868-117">Задайте начальное значение выборки для генератора случайных чисел, который преобразование использует для создания выборки.</span><span class="sxs-lookup"><span data-stu-id="0a868-117">Specify the sampling seed for the random number generator that the transformation uses to create a sample.</span></span> <span data-ttu-id="0a868-118">Рекомендуется только для разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="0a868-118">This is only recommended for development and testing.</span></span> <span data-ttu-id="0a868-119">Если начальное значение выборки не задано, преобразование использует счетчик тактов Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="0a868-119">The transformation uses the Microsoft Windows tick count if a random seed is not specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a868-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="0a868-120">See Also</span></span>  
 <span data-ttu-id="0a868-121">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="0a868-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="0a868-122">Преобразование "Выборка строк"</span><span class="sxs-lookup"><span data-stu-id="0a868-122">Row Sampling Transformation</span></span>](data-flow/transformations/row-sampling-transformation.md)  
  
  
