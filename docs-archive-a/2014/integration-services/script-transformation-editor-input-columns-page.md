---
title: Редактор преобразования "Скрипт" (страница "входные столбцы") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.scriptcomponent.inputcolumn.f1
helpviewer_keywords:
- Script Transformation Editor
ms.assetid: d6e4ce84-3335-48e6-82d3-1c359ed87f63
author: chugugrace
ms.author: chugu
ms.openlocfilehash: daffb52b62ad59ae4fe574d7fa27d4820b9cb5a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728465"
---
# <a name="script-transformation-editor-input-columns-page"></a><span data-ttu-id="fd66a-102">Редактор преобразования «Скрипт» (страница «Входные столбцы»)</span><span class="sxs-lookup"><span data-stu-id="fd66a-102">Script Transformation Editor (Input Columns Page)</span></span>
  <span data-ttu-id="fd66a-103">Страница **Входные столбцы** диалогового окна **Редактор преобразования «Скрипт»** используется для установки свойств входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="fd66a-103">Use the **Input Columns** page of the **Script Transformation Editor** dialog box to set properties on input columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fd66a-104">Страница **Входные столбцы** не отображается для компонентов источника, которые имеют выводы, но не имеют входов.</span><span class="sxs-lookup"><span data-stu-id="fd66a-104">The **Input Columns** page is not displayed for Source components, which have outputs but no inputs.</span></span>  
  
 <span data-ttu-id="fd66a-105">Дополнительные сведения о компоненте скрипта см. в разделах [Script Component](data-flow/transformations/script-component.md) и [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="fd66a-105">To learn more about the Script component, see [Script Component](data-flow/transformations/script-component.md) and [Configuring the Script Component in the Script Component Editor](extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span> <span data-ttu-id="fd66a-106">Дополнительные сведения о программировании компонента скрипта см. в разделе [Расширение потока данных с помощью компонента скрипта](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="fd66a-106">To learn about programming the Script component, see [Extending the Data Flow with the Script Component](extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="fd66a-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="fd66a-107">Options</span></span>  
 <span data-ttu-id="fd66a-108">**Имя входа**</span><span class="sxs-lookup"><span data-stu-id="fd66a-108">**Input name**</span></span>  
 <span data-ttu-id="fd66a-109">Выберите из списка доступных входов.</span><span class="sxs-lookup"><span data-stu-id="fd66a-109">Select from the list of available inputs.</span></span>  
  
 <span data-ttu-id="fd66a-110">**Доступные входные столбцы**</span><span class="sxs-lookup"><span data-stu-id="fd66a-110">**Available Input Columns**</span></span>  
 <span data-ttu-id="fd66a-111">С помощью флажков укажите столбцы, которые будут использоваться в преобразовании «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="fd66a-111">Using the check boxes, specify the columns that the script transformation will use.</span></span>  
  
 <span data-ttu-id="fd66a-112">**Входной столбец**</span><span class="sxs-lookup"><span data-stu-id="fd66a-112">**Input Column**</span></span>  
 <span data-ttu-id="fd66a-113">Выберите для каждой строки столбец из списка доступных входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="fd66a-113">Select from the list of available input columns for each row.</span></span> <span data-ttu-id="fd66a-114">Выбранные столбцы обозначаются флажками в таблице **Доступные входные столбцы**.</span><span class="sxs-lookup"><span data-stu-id="fd66a-114">Your selections are reflected in the check box selections in the **Available Input Columns**table.</span></span>  
  
 <span data-ttu-id="fd66a-115">**Псевдоним вывода**</span><span class="sxs-lookup"><span data-stu-id="fd66a-115">**Output Alias**</span></span>  
 <span data-ttu-id="fd66a-116">Введите псевдоним для каждого выходного столбца.</span><span class="sxs-lookup"><span data-stu-id="fd66a-116">Type an alias for each output column.</span></span> <span data-ttu-id="fd66a-117">По умолчанию, используется имя входного столбца, однако можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="fd66a-117">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="fd66a-118">**Тип применения**</span><span class="sxs-lookup"><span data-stu-id="fd66a-118">**Usage Type**</span></span>  
 <span data-ttu-id="fd66a-119">Указывает, будет ли преобразование «Скрипт» рассматривать каждый столбец как `ReadOnly` или `ReadWrite`.</span><span class="sxs-lookup"><span data-stu-id="fd66a-119">Specify whether the Script Transformation will treat each column as `ReadOnly` or `ReadWrite`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd66a-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="fd66a-120">See Also</span></span>  
 <span data-ttu-id="fd66a-121">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="fd66a-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="fd66a-122">[Выбор типа компонента скрипта](../../2014/integration-services/select-script-component-type.md) </span><span class="sxs-lookup"><span data-stu-id="fd66a-122">[Select Script Component Type](../../2014/integration-services/select-script-component-type.md) </span></span>  
 <span data-ttu-id="fd66a-123">[Редактор преобразования "Скрипт" &#40;страница "входы и выходы"&#41;](../../2014/integration-services/script-transformation-editor-inputs-and-outputs-page.md) </span><span class="sxs-lookup"><span data-stu-id="fd66a-123">[Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../../2014/integration-services/script-transformation-editor-inputs-and-outputs-page.md) </span></span>  
 <span data-ttu-id="fd66a-124">[Редактор преобразования "Скрипт" &#40;страница "Скрипт"&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span><span class="sxs-lookup"><span data-stu-id="fd66a-124">[Script Transformation Editor &#40;Script Page&#41;](../../2014/integration-services/script-transformation-editor-script-page.md) </span></span>  
 <span data-ttu-id="fd66a-125">[Редактор преобразования "Скрипт" &#40;страница "диспетчеры соединений"&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span><span class="sxs-lookup"><span data-stu-id="fd66a-125">[Script Transformation Editor &#40;Connection Managers Page&#41;](../../2014/integration-services/script-transformation-editor-connection-managers-page.md) </span></span>  
 [<span data-ttu-id="fd66a-126">Дополнительные примеры компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="fd66a-126">Additional Script Component Examples</span></span>](extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md)  
  
  
