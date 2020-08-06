---
title: Редактор преобразования "Уточняющий запрос" (страница "вывод ошибок") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.erroroutput.f1
ms.assetid: 15d53bb0-8be1-46fb-b459-04a397e75fac
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9cd78f40a0072f7f0c5c923cdd51431873402f3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664319"
---
# <a name="lookup-transformation-editor-error-output-page"></a><span data-ttu-id="b08cc-102">Редактор преобразования «Уточняющий запрос» (страница «Вывод ошибок»)</span><span class="sxs-lookup"><span data-stu-id="b08cc-102">Lookup Transformation Editor (Error Output Page)</span></span>
  <span data-ttu-id="b08cc-103">Страница **Вывод ошибок** диалогового окна **Редактор преобразования «Уточняющий запрос»** используется для задания параметров обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="b08cc-103">Use the **Error Output** page of the **Lookup Transformation Editor** dialog box to specify error handling options.</span></span>  
  
 <span data-ttu-id="b08cc-104">Дополнительные сведения о преобразовании «Уточняющий запрос» см. в разделе [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="b08cc-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b08cc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b08cc-105">Options</span></span>  
 <span data-ttu-id="b08cc-106">**Ввод-вывод**</span><span class="sxs-lookup"><span data-stu-id="b08cc-106">**Input/Output**</span></span>  
 <span data-ttu-id="b08cc-107">Просмотрите имя входных данных.</span><span class="sxs-lookup"><span data-stu-id="b08cc-107">View the name of the input.</span></span>  
  
 <span data-ttu-id="b08cc-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="b08cc-108">**Column**</span></span>  
 <span data-ttu-id="b08cc-109">Не используется.</span><span class="sxs-lookup"><span data-stu-id="b08cc-109">Not used.</span></span>  
  
 <span data-ttu-id="b08cc-110">**Error**</span><span class="sxs-lookup"><span data-stu-id="b08cc-110">**Error**</span></span>  
 <span data-ttu-id="b08cc-111">Укажите, какой тип ошибки должен появляться при обработке строк, не имеющих совпадающих записей в эталонном наборе данных:</span><span class="sxs-lookup"><span data-stu-id="b08cc-111">Specify what type of error should occur when handling rows without matching entries in the reference dataset:</span></span>  
  
-   <span data-ttu-id="b08cc-112">не учитывать сбой и направить строки на выход;</span><span class="sxs-lookup"><span data-stu-id="b08cc-112">Ignore the failure and direct the rows to an output.</span></span>  
  
-   <span data-ttu-id="b08cc-113">перенаправлять строки в вывод ошибок;</span><span class="sxs-lookup"><span data-stu-id="b08cc-113">Redirect the rows to an error output.</span></span>  
  
-   <span data-ttu-id="b08cc-114">завершить работу компонента с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b08cc-114">Fail the component.</span></span>  
  
 <span data-ttu-id="b08cc-115">Этот параметр недоступен при выборе параметра **Перенаправлять строки в выход несовпадающих строк** в списке **Укажите метод обработки строк без совпадающих элементов** .</span><span class="sxs-lookup"><span data-stu-id="b08cc-115">This option is not available when you select **Redirect rows to no match output** in the **Specify how to handle rows with no matching entries** list.</span></span> <span data-ttu-id="b08cc-116">Этот список находится на странице **Общие** диалогового окна **Редактор преобразования «Уточняющий запрос»** .</span><span class="sxs-lookup"><span data-stu-id="b08cc-116">This list is on the **General** page of the **Lookup Transformation Editor** dialog box.</span></span>  
  
 <span data-ttu-id="b08cc-117">**См. также:** [Обработка ошибок в данных](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="b08cc-117">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="b08cc-118">**Усечение**</span><span class="sxs-lookup"><span data-stu-id="b08cc-118">**Truncation**</span></span>  
 <span data-ttu-id="b08cc-119">Задайте действие при усечении данных:</span><span class="sxs-lookup"><span data-stu-id="b08cc-119">Specify what should happen when data truncation occurs:</span></span>  
  
-   <span data-ttu-id="b08cc-120">пропустить ошибку;</span><span class="sxs-lookup"><span data-stu-id="b08cc-120">Ignore the failure.</span></span>  
  
-   <span data-ttu-id="b08cc-121">перенаправить строку;</span><span class="sxs-lookup"><span data-stu-id="b08cc-121">Redirect the row.</span></span>  
  
-   <span data-ttu-id="b08cc-122">завершить работу компонента с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b08cc-122">Fail the component.</span></span>  
  
 <span data-ttu-id="b08cc-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b08cc-123">**Description**</span></span>  
 <span data-ttu-id="b08cc-124">Просмотрите описание операции.</span><span class="sxs-lookup"><span data-stu-id="b08cc-124">View the description of the operation.</span></span>  
  
 <span data-ttu-id="b08cc-125">**Присвоить указанное значение выбранным ячейкам**</span><span class="sxs-lookup"><span data-stu-id="b08cc-125">**Set selected cells to this value**</span></span>  
 <span data-ttu-id="b08cc-126">Укажите действие, которое необходимо применить ко всем выбранным ячейкам при возникновении ошибки или усечения:</span><span class="sxs-lookup"><span data-stu-id="b08cc-126">Specify what should happen to all the selected cells when an error or truncation occurs:</span></span>  
  
-   <span data-ttu-id="b08cc-127">пропустить ошибку;</span><span class="sxs-lookup"><span data-stu-id="b08cc-127">Ignore the failure.</span></span>  
  
-   <span data-ttu-id="b08cc-128">перенаправить строку;</span><span class="sxs-lookup"><span data-stu-id="b08cc-128">Redirect the row.</span></span>  
  
-   <span data-ttu-id="b08cc-129">завершить работу компонента с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b08cc-129">Fail the component.</span></span>  
  
 <span data-ttu-id="b08cc-130">**Применить**</span><span class="sxs-lookup"><span data-stu-id="b08cc-130">**Apply**</span></span>  
 <span data-ttu-id="b08cc-131">Применить параметр обработки ошибок к выбранным ячейкам.</span><span class="sxs-lookup"><span data-stu-id="b08cc-131">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b08cc-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="b08cc-132">See Also</span></span>  
 [<span data-ttu-id="b08cc-133">Справочник по сообщениям об ошибках служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="b08cc-133">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
