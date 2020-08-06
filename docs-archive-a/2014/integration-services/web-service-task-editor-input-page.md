---
title: Редактор задачи «веб-служба» (страница «Вход») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.input.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 93529c88-f540-47f2-a10a-12c87318ed6f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ae876572747b9bb1088fe8b0a1c2c2fdde9f4f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667785"
---
# <a name="web-service-task-editor-input-page"></a><span data-ttu-id="43872-102">Редактор задачи «Веб-служба» (страница «Вход»)</span><span class="sxs-lookup"><span data-stu-id="43872-102">Web Service Task Editor (Input Page)</span></span>
  <span data-ttu-id="43872-103">Используйте страницу **Вход** в диалоговом окне **Редактор задачи «Веб-служба»** , чтобы указать веб-службу, веб-метод и значения, предоставляемые в качестве входных данных веб-метода.</span><span class="sxs-lookup"><span data-stu-id="43872-103">Use the **Input** page of the **Web Service Task Editor** dialog box to specify the Web Service, the Web method, and the values to provide to the Web method as input.</span></span> <span data-ttu-id="43872-104">Значения можно предоставить, либо непосредственно введя строки в столбце «Значение», либо выбрав переменные в столбце «Значение».</span><span class="sxs-lookup"><span data-stu-id="43872-104">The values can be provided either by typing strings directly in the Value column, or by selecting variables in the Value column.</span></span>  
  
 <span data-ttu-id="43872-105">Дополнительные сведения об этой задаче см. в разделе [Задача "Веб-служба"](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="43872-105">To learn about this task, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="43872-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="43872-106">Options</span></span>  
 <span data-ttu-id="43872-107">**Служба**</span><span class="sxs-lookup"><span data-stu-id="43872-107">**Service**</span></span>  
 <span data-ttu-id="43872-108">Чтобы выполнить веб-метод, выберите веб-службу из списка.</span><span class="sxs-lookup"><span data-stu-id="43872-108">Select a Web service from the list to use to execute the Web method.</span></span>  
  
 <span data-ttu-id="43872-109">**Метод**</span><span class="sxs-lookup"><span data-stu-id="43872-109">**Method**</span></span>  
 <span data-ttu-id="43872-110">Чтобы выполнить задачу, выберите веб-метод из списка.</span><span class="sxs-lookup"><span data-stu-id="43872-110">Select a Web method from the list for the task to execute.</span></span>  
  
 <span data-ttu-id="43872-111">**WebMethodDocumentation**</span><span class="sxs-lookup"><span data-stu-id="43872-111">**WebMethodDocumentation**</span></span>  
 <span data-ttu-id="43872-112">Введите описание веб-метода или нажмите кнопку обзора **(...)** , а затем введите описание в диалоговом окне **Документация веб-метода**.</span><span class="sxs-lookup"><span data-stu-id="43872-112">Type a description of Web method, or the click the browse button **(...)** and then type the description in the **Web Method Documentation** dialog box.</span></span>  
  
 <span data-ttu-id="43872-113">**имя**;</span><span class="sxs-lookup"><span data-stu-id="43872-113">**Name**</span></span>  
 <span data-ttu-id="43872-114">Перечисляет имена входных данных веб-метода.</span><span class="sxs-lookup"><span data-stu-id="43872-114">Lists the names of the inputs to the Web method.</span></span>  
  
 <span data-ttu-id="43872-115">**Тип**</span><span class="sxs-lookup"><span data-stu-id="43872-115">**Type**</span></span>  
 <span data-ttu-id="43872-116">Перечисляет тип входных данных.</span><span class="sxs-lookup"><span data-stu-id="43872-116">Lists the data type of the inputs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43872-117">Задача «Веб-служба» поддерживает только параметры следующих типов данных: типы-примитивы, такие как integer и string, массивы и последовательности типов-примитивов, а также перечисления.</span><span class="sxs-lookup"><span data-stu-id="43872-117">The Web Service task supports parameters of the following data types only: primitive types such as integers and strings; arrays and sequences of primitive types; and enumerations.</span></span>  
  
 <span data-ttu-id="43872-118">**Переменная**</span><span class="sxs-lookup"><span data-stu-id="43872-118">**Variable**</span></span>  
 <span data-ttu-id="43872-119">Установите флажки, чтобы использовать переменные для входных данных.</span><span class="sxs-lookup"><span data-stu-id="43872-119">Select the check boxes to use variables to provide inputs.</span></span>  
  
 <span data-ttu-id="43872-120">**Значение**</span><span class="sxs-lookup"><span data-stu-id="43872-120">**Value**</span></span>  
 <span data-ttu-id="43872-121">Если установлены флажки «Переменная», выберите переменные из списка для входных данных; в противном случае введите значения входных данных вручную.</span><span class="sxs-lookup"><span data-stu-id="43872-121">If the Variable check-boxes are selected, select the variables in the list to provide the inputs; otherwise, type the values to use in the inputs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43872-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="43872-122">See Also</span></span>  
 <span data-ttu-id="43872-123">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="43872-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="43872-124">[Редактор задачи "веб-служба" &#40;страница "Общие"&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="43872-124">[Web Service Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="43872-125">[Редактор задачи "веб-служба" &#40;страница "выходные данные"&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="43872-125">[Web Service Task Editor &#40;Output Page&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span></span>  
 [<span data-ttu-id="43872-126">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="43872-126">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
