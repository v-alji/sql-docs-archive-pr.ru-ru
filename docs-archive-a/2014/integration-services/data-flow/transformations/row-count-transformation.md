---
title: Преобразование "Подсчет строк" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rowcounttrans.f1
helpviewer_keywords:
- updating variables
- Row Count transformation
- number of rows
- variables [Integration Services], updating
- counting rows
ms.assetid: b68293b9-a68c-40be-9d81-77342da1be29
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b0940d608aeaa96b7ec43fa4486944ce0f887e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752311"
---
# <a name="row-count-transformation"></a><span data-ttu-id="94e01-102">преобразование «Подсчет строк»</span><span class="sxs-lookup"><span data-stu-id="94e01-102">Row Count Transformation</span></span>
  <span data-ttu-id="94e01-103">Преобразование «Подсчет строк» подсчитывает строки по мере прохождения их в потоке данных и сохраняет конечный результат в переменной.</span><span class="sxs-lookup"><span data-stu-id="94e01-103">The Row Count transformation counts rows as they pass through a data flow and stores the final count in a variable.</span></span>  
  
 <span data-ttu-id="94e01-104">Пакет [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] может обновлять значения переменных, используемых в скриптах, выражениях и выражениях свойств.</span><span class="sxs-lookup"><span data-stu-id="94e01-104">A [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] package can use row counts to update the variables used in scripts, expressions, and property expressions.</span></span> <span data-ttu-id="94e01-105">(Например, переменная, используемая для подсчета строк, может обновить текстовое сообщение электронной почты, добавив количество строк.) Переменная, используемая преобразованием «Подсчет строк», должна существовать и находиться в области задачи потока данных, к которой относится поток данных с преобразованием «Подсчет строк».</span><span class="sxs-lookup"><span data-stu-id="94e01-105">(For example, the variable that stores the row count can update the message text in an e-mail message to include the number of rows.) The variable that the Row Count transformation uses must already exist, and it must be in the scope of the Data Flow task to which the data flow with the Row Count transformation belongs.</span></span>  
  
 <span data-ttu-id="94e01-106">Преобразование сохраняет значение подсчета строк таблицы в переменной только после прохождения последней строки через преобразование.</span><span class="sxs-lookup"><span data-stu-id="94e01-106">The transformation stores the row count value in the variable only after the last row has passed through the transformation.</span></span> <span data-ttu-id="94e01-107">Поэтому значение переменной не обновляется сразу, чтобы использовать обновленное значение в потоке данных, содержащем преобразование «Подсчет строк».</span><span class="sxs-lookup"><span data-stu-id="94e01-107">Therefore, the value of the variable is not updated in time to use the updated value in the data flow that contains the Row Count transformation.</span></span> <span data-ttu-id="94e01-108">Можно использовать обновленную переменную в отдельном потоке данных.</span><span class="sxs-lookup"><span data-stu-id="94e01-108">You can use the updated variable in a separate data flow.</span></span>  
  
 <span data-ttu-id="94e01-109">Это преобразование имеет один вход и один выход.</span><span class="sxs-lookup"><span data-stu-id="94e01-109">This transformation has one input and one output.</span></span> <span data-ttu-id="94e01-110">Вывод ошибок не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="94e01-110">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-row-count-transformation"></a><span data-ttu-id="94e01-111">Настройка преобразования «Подсчет строк»</span><span class="sxs-lookup"><span data-stu-id="94e01-111">Configuration of the Row Count Transformation</span></span>  
 <span data-ttu-id="94e01-112">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="94e01-112">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="94e01-113">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="94e01-113">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="94e01-114">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="94e01-114">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="94e01-115">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="94e01-115">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="94e01-116">Пользовательские свойства преобразований</span><span class="sxs-lookup"><span data-stu-id="94e01-116">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="94e01-117">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="94e01-117">Related Tasks</span></span>  
 <span data-ttu-id="94e01-118">Дополнительные сведения о настройке свойств компонента см. в разделе [Установление свойств компонента потока данных](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="94e01-118">For information about how to set the properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94e01-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="94e01-119">See Also</span></span>  
 <span data-ttu-id="94e01-120">[Переменные в службах Integration Services (SSIS)](../../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="94e01-120">[Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="94e01-121">[Поток данных](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="94e01-121">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="94e01-122">Преобразования служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="94e01-122">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
