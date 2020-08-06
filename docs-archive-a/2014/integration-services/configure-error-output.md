---
title: Настройка вывода ошибок | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.configureerroroutput.f1
ms.assetid: 5f8da390-fab5-44f8-b268-d8fa313ce4b9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: de1a5908c6075438599f4108e9780f5591b042c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665496"
---
# <a name="configure-error-output"></a><span data-ttu-id="7b291-102">Настройка вывода ошибок</span><span class="sxs-lookup"><span data-stu-id="7b291-102">Configure Error Output</span></span>
  <span data-ttu-id="7b291-103">Используйте диалоговое окно **Настройка вывода ошибок** , чтобы настроить параметры обработки ошибок для преобразований потока данных, поддерживающих вывод ошибок.</span><span class="sxs-lookup"><span data-stu-id="7b291-103">Use the **Configure Error Output** dialog box to configure error handling options for data flow transformations that support an error output.</span></span>  
  
 <span data-ttu-id="7b291-104">Дополнительные сведения о работе с выводом ошибок на выходе см. в разделе [Обработка ошибок в данных](data-flow/error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="7b291-104">To learn more about working with error outputs, see [Error Handling in Data](data-flow/error-handling-in-data.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7b291-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7b291-105">Options</span></span>  
 <span data-ttu-id="7b291-106">**Вход или выход**</span><span class="sxs-lookup"><span data-stu-id="7b291-106">**Input or Output**</span></span>  
 <span data-ttu-id="7b291-107">Просмотр имени вывода.</span><span class="sxs-lookup"><span data-stu-id="7b291-107">View the name of the output.</span></span>  
  
 <span data-ttu-id="7b291-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7b291-108">**Column**</span></span>  
 <span data-ttu-id="7b291-109">Просмотр выходных столбцов, выбранных в диалоговом окне редактора преобразования.</span><span class="sxs-lookup"><span data-stu-id="7b291-109">View the output columns that you selected in the transformation editor dialog box.</span></span>  
  
 <span data-ttu-id="7b291-110">**Error**</span><span class="sxs-lookup"><span data-stu-id="7b291-110">**Error**</span></span>  
 <span data-ttu-id="7b291-111">Если это применимо, при возникновении ошибки задайте событие: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="7b291-111">If applicable, specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="7b291-112">**См. также:** [Обработка ошибок в данных](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="7b291-112">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="7b291-113">**Усечение**</span><span class="sxs-lookup"><span data-stu-id="7b291-113">**Truncation**</span></span>  
 <span data-ttu-id="7b291-114">Если это применимо, при возникновении усечения задайте событие: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="7b291-114">If applicable, specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="7b291-115">**См. также:** [Обработка ошибок в данных](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="7b291-115">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="7b291-116">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7b291-116">**Description**</span></span>  
 <span data-ttu-id="7b291-117">Просмотрите описание операции.</span><span class="sxs-lookup"><span data-stu-id="7b291-117">View the description of the operation.</span></span>  
  
 <span data-ttu-id="7b291-118">**Присвоить указанное значение выбранным ячейкам**</span><span class="sxs-lookup"><span data-stu-id="7b291-118">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="7b291-119">Укажите действие, которое необходимо применить ко всем выбранным ячейкам при возникновении ошибки или усечения: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="7b291-119">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="7b291-120">**Применить**</span><span class="sxs-lookup"><span data-stu-id="7b291-120">**Apply**</span></span>  
 <span data-ttu-id="7b291-121">Применить параметр обработки ошибок к выбранным ячейкам.</span><span class="sxs-lookup"><span data-stu-id="7b291-121">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b291-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="7b291-122">See Also</span></span>  
 [<span data-ttu-id="7b291-123">Справочник по сообщениям об ошибках служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="7b291-123">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
