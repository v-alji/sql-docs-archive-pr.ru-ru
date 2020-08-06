---
title: Редактор преобразования «Выборка строк» (страница «выборка») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.ROWSAMPLINGTRANSFORMATION.COLUMNS.F1
- sql12.dts.designer.rowsamplingtransformation.f1
helpviewer_keywords:
- Row Sampling Transformation Editor
ms.assetid: 544c7709-6de0-4c08-bda3-759985be9a05
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 26d0c0439e548172225f02220d8f6814a1168ea9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729581"
---
# <a name="row-sampling-transformation-editor-sampling-page"></a><span data-ttu-id="39242-102">Редактор преобразования «Выборка строк» (страница выборки)</span><span class="sxs-lookup"><span data-stu-id="39242-102">Row Sampling Transformation Editor (Sampling Page)</span></span>
  <span data-ttu-id="39242-103">Диалоговое окно **Редактор преобразования «Выборка строк»** используется для деления на части входных данных в выборке, используя указанное количество строк.</span><span class="sxs-lookup"><span data-stu-id="39242-103">Use the **Row Sampling Transformation Editor** dialog box to split a portion of an input into a sample using a specified number of rows.</span></span> <span data-ttu-id="39242-104">Это преобразование разделяет входные данные на два отдельных вывода.</span><span class="sxs-lookup"><span data-stu-id="39242-104">This transformation divides the input into two separate outputs.</span></span>  
  
 <span data-ttu-id="39242-105">Дополнительные сведения о преобразовании «Выборка строк» см. в разделе [Row Sampling Transformation](data-flow/transformations/row-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="39242-105">To learn more about the Row Sampling transformation, see [Row Sampling Transformation](data-flow/transformations/row-sampling-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="39242-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="39242-106">Options</span></span>  
 <span data-ttu-id="39242-107">**Число строк**</span><span class="sxs-lookup"><span data-stu-id="39242-107">**Number of rows**</span></span>  
 <span data-ttu-id="39242-108">Задайте количество строк из входных данных для использования в качестве выборки.</span><span class="sxs-lookup"><span data-stu-id="39242-108">Specify the number of rows from the input to use as a sample.</span></span>  
  
 <span data-ttu-id="39242-109">Значение этого свойства можно задать с помощью выражения свойства.</span><span class="sxs-lookup"><span data-stu-id="39242-109">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="39242-110">**Имя выхода выборки**</span><span class="sxs-lookup"><span data-stu-id="39242-110">**Sample output name**</span></span>  
 <span data-ttu-id="39242-111">Задайте уникальное имя выхода, содержащего строки выборки.</span><span class="sxs-lookup"><span data-stu-id="39242-111">Provide a unique name for the output that will include the sampled rows.</span></span> <span data-ttu-id="39242-112">Указанное имя будет отображаться в конструкторе служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="39242-112">The name provided will be displayed within SSIS Designer.</span></span>  
  
 <span data-ttu-id="39242-113">**Имя вывода невыбранных элементов**</span><span class="sxs-lookup"><span data-stu-id="39242-113">**Unselected output name**</span></span>  
 <span data-ttu-id="39242-114">Задает уникальное имя выхода, который содержит строки, исключенные из выборки.</span><span class="sxs-lookup"><span data-stu-id="39242-114">Provide a unique name for the output that will contain the rows excluded from the sampling.</span></span> <span data-ttu-id="39242-115">Указанное имя будет отображаться в конструкторе служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="39242-115">The name provided will be displayed within SSIS Designer.</span></span>  
  
 <span data-ttu-id="39242-116">**Использовать следующее начальное значение**</span><span class="sxs-lookup"><span data-stu-id="39242-116">**Use the following random seed**</span></span>  
 <span data-ttu-id="39242-117">Задайте начальное значение выборки для генератора случайных чисел, который преобразование использует для создания выборки.</span><span class="sxs-lookup"><span data-stu-id="39242-117">Specify the sampling seed for the random number generator that the transformation uses to create a sample.</span></span> <span data-ttu-id="39242-118">Рекомендуется только для разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="39242-118">This is only recommended for development and testing.</span></span> <span data-ttu-id="39242-119">Если начальное значение выборки не задано, преобразование использует счетчик сигналов времени Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="39242-119">The transformation uses the Microsoft Windows tick count as a seed if a random seed is not specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39242-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="39242-120">See Also</span></span>  
 <span data-ttu-id="39242-121">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="39242-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="39242-122">Преобразование "Процентная выборка"</span><span class="sxs-lookup"><span data-stu-id="39242-122">Percentage Sampling Transformation</span></span>](data-flow/transformations/percentage-sampling-transformation.md)  
  
  
