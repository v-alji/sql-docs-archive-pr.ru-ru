---
title: Редактор преобразования "Скрипт" (страница "входные и выходные данные") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.scriptcomponent.columnproperties.f1
helpviewer_keywords:
- Script Transformation Editor
ms.assetid: 9659d2d2-5d73-4470-9768-e07b77142fc9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16adf74a1cd8f0c778bc18eaff84437b8fc13603
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728461"
---
# <a name="script-transformation-editor-inputs-and-outputs-page"></a><span data-ttu-id="069d9-102">Редактор преобразования «Скрипт» (страница «Входы и выходы»)</span><span class="sxs-lookup"><span data-stu-id="069d9-102">Script Transformation Editor (Inputs and Outputs Page)</span></span>
  <span data-ttu-id="069d9-103">Используйте страницу **Входы и выходы** в диалоговом окне **Редактор преобразования «Скрипт»** , чтобы добавить, удалить или настроить входы и выходы преобразования «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="069d9-103">Use the **Inputs and Outputs** page of the **Script Transformation Editor** dialog box to add, remove, and configure inputs and outputs for the Script Transformation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="069d9-104">У исходных компонентов есть выводы, но нет входов, тогда как у компонентов назначения есть входы, но нет выводов.</span><span class="sxs-lookup"><span data-stu-id="069d9-104">Source components have outputs and no inputs, while destination components have inputs but no outputs.</span></span> <span data-ttu-id="069d9-105">У преобразований есть как входы, так и выводы.</span><span class="sxs-lookup"><span data-stu-id="069d9-105">Transformations have both inputs and outputs.</span></span>  
  
 <span data-ttu-id="069d9-106">Дополнительные сведения о компоненте скрипта см. в разделах [Script Component](data-flow/transformations/script-component.md) и [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="069d9-106">To learn more about the Script component, see [Script Component](data-flow/transformations/script-component.md) and [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span> <span data-ttu-id="069d9-107">Дополнительные сведения о программировании компонента скрипта см. в разделе [Расширение потока данных с помощью компонента скрипта](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="069d9-107">To learn about programming the Script component, see [Extending the Data Flow with the Script Component](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="069d9-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="069d9-108">Options</span></span>  
 <span data-ttu-id="069d9-109">**Inputs and outputs**</span><span class="sxs-lookup"><span data-stu-id="069d9-109">**Inputs and outputs**</span></span>  
 <span data-ttu-id="069d9-110">Выберите вход или вывод слева, чтобы посмотреть его свойства в таблице справа.</span><span class="sxs-lookup"><span data-stu-id="069d9-110">Select an input or output on the left to view its properties in the table on the right.</span></span> <span data-ttu-id="069d9-111">Свойства, доступные для редактирования, варьируются в зависимости от выбора.</span><span class="sxs-lookup"><span data-stu-id="069d9-111">Properties available for editing vary according to the selection.</span></span> <span data-ttu-id="069d9-112">Многие отображаемые параметры доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="069d9-112">Many of the properties displayed are read-only.</span></span> <span data-ttu-id="069d9-113">Дополнительные сведения об индивидуальных свойствах см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="069d9-113">For more information on the individual properties, see the following topics.</span></span>  
  
 [<span data-ttu-id="069d9-114">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="069d9-114">Common Properties</span></span>](../../2014/integration-services/common-properties.md)  
  
 [<span data-ttu-id="069d9-115">Пользовательские свойства преобразований</span><span class="sxs-lookup"><span data-stu-id="069d9-115">Transformation Custom Properties</span></span>](data-flow/transformations/transformation-custom-properties.md)  
  
 <span data-ttu-id="069d9-116">**Добавление выходных данных**</span><span class="sxs-lookup"><span data-stu-id="069d9-116">**Add Output**</span></span>  
 <span data-ttu-id="069d9-117">Добавить в список дополнительный выход.</span><span class="sxs-lookup"><span data-stu-id="069d9-117">Add an additional output to the list.</span></span>  
  
 <span data-ttu-id="069d9-118">**Добавить столбец**</span><span class="sxs-lookup"><span data-stu-id="069d9-118">**Add Column**</span></span>  
 <span data-ttu-id="069d9-119">Выберите папку, в которую необходимо поместить новый выходной столбец, и добавьте его, нажав кнопку **Добавить столбец**.</span><span class="sxs-lookup"><span data-stu-id="069d9-119">Select a folder in which to place the new output column, and then add the column by clicking **Add Column**.</span></span>  
  
 <span data-ttu-id="069d9-120">**Удалить выход**</span><span class="sxs-lookup"><span data-stu-id="069d9-120">**Remove Output**</span></span>  
 <span data-ttu-id="069d9-121">Выберите выход и удалите его, нажав кнопку **Удалить выход**.</span><span class="sxs-lookup"><span data-stu-id="069d9-121">Select an output, and then remove it by clicking **Remove Output**.</span></span>  
  
 <span data-ttu-id="069d9-122">**Удалить столбец**</span><span class="sxs-lookup"><span data-stu-id="069d9-122">**Remove Column**</span></span>  
 <span data-ttu-id="069d9-123">Выберите столбец и удалите его, нажав кнопку **Удалить столбец**.</span><span class="sxs-lookup"><span data-stu-id="069d9-123">Select a column, and then remove it by clicking **Remove Column**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="069d9-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="069d9-124">See Also</span></span>  
 <span data-ttu-id="069d9-125">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="069d9-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="069d9-126">[Выбор типа компонента скрипта](../../2014/integration-services/select-script-component-type.md) </span><span class="sxs-lookup"><span data-stu-id="069d9-126">[Select Script Component Type](../../2014/integration-services/select-script-component-type.md) </span></span>  
 <span data-ttu-id="069d9-127">[Редактор преобразования "Скрипт" &#40;страница "входные столбцы"&#41;](../../2014/integration-services/script-transformation-editor-input-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="069d9-127">[Script Transformation Editor &#40;Input Columns Page&#41;](../../2014/integration-services/script-transformation-editor-input-columns-page.md) </span></span>  
 <span data-ttu-id="069d9-128">[Редактор преобразования "Скрипт" &#40;страница "Скрипт"&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span><span class="sxs-lookup"><span data-stu-id="069d9-128">[Script Transformation Editor &#40;Script Page&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span></span>  
 <span data-ttu-id="069d9-129">[Редактор преобразования "Скрипт" &#40;страница "диспетчеры соединений"&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span><span class="sxs-lookup"><span data-stu-id="069d9-129">[Script Transformation Editor &#40;Connection Managers Page&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span></span>  
 [<span data-ttu-id="069d9-130">Дополнительные примеры компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="069d9-130">Additional Script Component Examples</span></span>](extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md)  
  
  
