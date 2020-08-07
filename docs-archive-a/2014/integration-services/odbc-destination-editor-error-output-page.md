---
title: Редактор назначения «ODBC» (страница «вывод ошибок») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcdest.errorhandling.f1
ms.assetid: 0a743f8d-2a51-4296-9976-8104f5ca22d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 475a2e00d67b221ddf05fdd273317fbab5248cd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734362"
---
# <a name="odbc-destination-editor-error-output-page"></a><span data-ttu-id="a4a6c-102">Редактор назначения «ODBC» (страница «Вывод ошибок»)</span><span class="sxs-lookup"><span data-stu-id="a4a6c-102">ODBC Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="a4a6c-103">Страница **Вывод ошибок** диалогового окна **Редактор назначения ODBC** используется для выбора параметров обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="a4a6c-103">Use the **Error Output** page of the **ODBC Destination Editor** dialog box to select error handling options.</span></span>  
  
 <span data-ttu-id="a4a6c-104">Дополнительные сведения о назначении ODBC см. в разделе [ODBC Destination](data-flow/odbc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="a4a6c-104">To learn more about the ODBC destination, see [ODBC Destination](data-flow/odbc-destination.md).</span></span>  
  
 <span data-ttu-id="a4a6c-105">**Открытие страницы «Вывод ошибок» редактора назначения ODBC**</span><span class="sxs-lookup"><span data-stu-id="a4a6c-105">**To open the ODBC Destination Editor Error Output Page**</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="a4a6c-106">Список задач</span><span class="sxs-lookup"><span data-stu-id="a4a6c-106">Task List</span></span>  
  
-   <span data-ttu-id="a4a6c-107">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]откройте пакет служб [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] , содержащий назначение ODBC.</span><span class="sxs-lookup"><span data-stu-id="a4a6c-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC destination.</span></span>  
  
-   <span data-ttu-id="a4a6c-108">На вкладке **Поток данных** дважды щелкните назначение ODBC.</span><span class="sxs-lookup"><span data-stu-id="a4a6c-108">On the **Data Flow** tab, double-click the ODBC destination.</span></span>  
  
-   <span data-ttu-id="a4a6c-109">В окне **Редактор назначения ODBC**нажмите кнопку **Вывод ошибок**.</span><span class="sxs-lookup"><span data-stu-id="a4a6c-109">In the **ODBC Destination Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a4a6c-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="a4a6c-110">Options</span></span>  
  
### <a name="inputoutput"></a><span data-ttu-id="a4a6c-111">Ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="a4a6c-111">Input/Output</span></span>  
 <span data-ttu-id="a4a6c-112">Просмотр имени источника данных.</span><span class="sxs-lookup"><span data-stu-id="a4a6c-112">View the name of the data source.</span></span>  
  
### <a name="column"></a><span data-ttu-id="a4a6c-113">Столбец</span><span class="sxs-lookup"><span data-stu-id="a4a6c-113">Column</span></span>  
 <span data-ttu-id="a4a6c-114">Не используется.</span><span class="sxs-lookup"><span data-stu-id="a4a6c-114">Not used.</span></span>  
  
### <a name="error"></a><span data-ttu-id="a4a6c-115">Ошибка</span><span class="sxs-lookup"><span data-stu-id="a4a6c-115">Error</span></span>  
 <span data-ttu-id="a4a6c-116">Выберите порядок обработки ошибок в потоке назначением ODBC: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="a4a6c-116">Select how the ODBC destination should handle errors in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="truncation"></a><span data-ttu-id="a4a6c-117">Усечение</span><span class="sxs-lookup"><span data-stu-id="a4a6c-117">Truncation</span></span>  
 <span data-ttu-id="a4a6c-118">Выберите порядок обработки усечений в потоке назначением ODBC: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="a4a6c-118">Select how the ODBC destination should handle truncation in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="description"></a><span data-ttu-id="a4a6c-119">Description</span><span class="sxs-lookup"><span data-stu-id="a4a6c-119">Description</span></span>  
 <span data-ttu-id="a4a6c-120">Просмотрите описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="a4a6c-120">View a description of the error.</span></span>  
  
### <a name="set-this-value-to-selected-cells"></a><span data-ttu-id="a4a6c-121">Присвоить указанное значение выбранным ячейкам</span><span class="sxs-lookup"><span data-stu-id="a4a6c-121">Set this value to selected cells</span></span>  
 <span data-ttu-id="a4a6c-122">Выберите, как назначение ODBC обрабатывает все выбранные ячейки при возникновении ошибки или усечения: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="a4a6c-122">Select how the ODBC destination handles all selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="apply"></a><span data-ttu-id="a4a6c-123">Применить</span><span class="sxs-lookup"><span data-stu-id="a4a6c-123">Apply</span></span>  
 <span data-ttu-id="a4a6c-124">Примените параметры обработки ошибок к выбранным ячейкам.</span><span class="sxs-lookup"><span data-stu-id="a4a6c-124">Apply the error handling options to the selected cells.</span></span>  
  
## <a name="error-handling-options"></a><span data-ttu-id="a4a6c-125">Параметры обработки ошибок</span><span class="sxs-lookup"><span data-stu-id="a4a6c-125">Error Handling Options</span></span>  
 <span data-ttu-id="a4a6c-126">Следующие параметры позволяют настроить обработку ошибок и усечений назначением ODBC.</span><span class="sxs-lookup"><span data-stu-id="a4a6c-126">You use the following options to configure how the ODBC destination handles errors and truncations.</span></span>  
  
### <a name="fail-component"></a><span data-ttu-id="a4a6c-127">Компонент, завершившийся сбоем</span><span class="sxs-lookup"><span data-stu-id="a4a6c-127">Fail Component</span></span>  
 <span data-ttu-id="a4a6c-128">Задача потока данных заканчивается сбоем, если возникли ошибка или усечение.</span><span class="sxs-lookup"><span data-stu-id="a4a6c-128">The Data Flow task fails when an error or a truncation occurs.</span></span> <span data-ttu-id="a4a6c-129">Это поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a4a6c-129">This is the default behavior.</span></span>  
  
### <a name="ignore-failure"></a><span data-ttu-id="a4a6c-130">Пропуск неудачи</span><span class="sxs-lookup"><span data-stu-id="a4a6c-130">Ignore Failure</span></span>  
 <span data-ttu-id="a4a6c-131">Ошибка или усечение пропускается.</span><span class="sxs-lookup"><span data-stu-id="a4a6c-131">The error or the truncation is ignored.</span></span>  
  
### <a name="redirect-flow"></a><span data-ttu-id="a4a6c-132">Перенаправление потока</span><span class="sxs-lookup"><span data-stu-id="a4a6c-132">Redirect Flow</span></span>  
 <span data-ttu-id="a4a6c-133">Строка, вызывающая ошибку или усечение, направляется на вывод ошибок назначения ODBC.</span><span class="sxs-lookup"><span data-stu-id="a4a6c-133">The row that is causing the error or the truncation is directed to the error output of the ODBC destination.</span></span> <span data-ttu-id="a4a6c-134">Дополнительные сведения см. в разделе, посвященном назначению ODBC.</span><span class="sxs-lookup"><span data-stu-id="a4a6c-134">For more information, see ODBC Destination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4a6c-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="a4a6c-135">See Also</span></span>  
 <span data-ttu-id="a4a6c-136">[Редактор назначения ODBC &#40;страница "Диспетчер соединений"&#41;](../../2014/integration-services/odbc-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="a4a6c-136">[ODBC Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/odbc-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="a4a6c-137">Редактор назначения ODBC (страница "Сопоставления")</span><span class="sxs-lookup"><span data-stu-id="a4a6c-137">ODBC Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/odbc-destination-editor-mappings-page.md)  
  
  
