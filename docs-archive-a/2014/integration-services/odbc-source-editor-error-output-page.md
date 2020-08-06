---
title: Редактор источника «ODBC» (страница «вывод ошибок») | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.errorhandling.f1
ms.assetid: b2f6866c-db07-4cb3-9f38-889f8d2b03e6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a8e169875a26efbe0a7f1ac3d06856b393266eb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734350"
---
# <a name="odbc-source-editor-error-output-page"></a><span data-ttu-id="92d94-102">Редактор источника «ODBC» (страница «Вывод ошибок»)</span><span class="sxs-lookup"><span data-stu-id="92d94-102">ODBC Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="92d94-103">Страница **Вывод ошибок** диалогового окна **Редактор источника ODBC** используется для выбора параметров обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="92d94-103">Use the **Error Output** page of the **ODBC Source Editor** dialog box to select error handling options.</span></span>  
  
 <span data-ttu-id="92d94-104">Дополнительные сведения об источнике ODBC см. в разделе [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="92d94-104">To learn more about the ODBC source, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="92d94-105">Список задач</span><span class="sxs-lookup"><span data-stu-id="92d94-105">Task List</span></span>  
 <span data-ttu-id="92d94-106">**Открытие страницы «Вывод ошибок» редактора источника ODBC**</span><span class="sxs-lookup"><span data-stu-id="92d94-106">**To open the ODBC Source Editor Error Output Page**</span></span>  
  
-   <span data-ttu-id="92d94-107">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]откройте пакет служб [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] , содержащий источник ODBC.</span><span class="sxs-lookup"><span data-stu-id="92d94-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC source.</span></span>  
  
-   <span data-ttu-id="92d94-108">На вкладке **Поток данных** дважды щелкните источник ODBC.</span><span class="sxs-lookup"><span data-stu-id="92d94-108">On the **Data Flow** tab, double-click the ODBC source.</span></span>  
  
-   <span data-ttu-id="92d94-109">В окне **Редактор источника ODBC**нажмите кнопку **Вывод ошибок**.</span><span class="sxs-lookup"><span data-stu-id="92d94-109">In the **ODBC Source Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="92d94-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="92d94-110">Options</span></span>  
  
### <a name="inputoutput"></a><span data-ttu-id="92d94-111">Ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="92d94-111">Input/Output</span></span>  
 <span data-ttu-id="92d94-112">Просмотр имени источника данных.</span><span class="sxs-lookup"><span data-stu-id="92d94-112">View the name of the data source.</span></span>  
  
### <a name="column"></a><span data-ttu-id="92d94-113">Столбец</span><span class="sxs-lookup"><span data-stu-id="92d94-113">Column</span></span>  
 <span data-ttu-id="92d94-114">Не используется.</span><span class="sxs-lookup"><span data-stu-id="92d94-114">Not used.</span></span>  
  
### <a name="error"></a><span data-ttu-id="92d94-115">Ошибка</span><span class="sxs-lookup"><span data-stu-id="92d94-115">Error</span></span>  
 <span data-ttu-id="92d94-116">Выберите порядок обработки ошибок в потоке источником ODBC: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="92d94-116">Select how the ODBC source should handle errors in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="truncation"></a><span data-ttu-id="92d94-117">Усечение</span><span class="sxs-lookup"><span data-stu-id="92d94-117">Truncation</span></span>  
 <span data-ttu-id="92d94-118">Выберите порядок обработки усечений в потоке источником ODBC: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="92d94-118">Select how the ODBC source should handle truncation in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="description"></a><span data-ttu-id="92d94-119">Описание</span><span class="sxs-lookup"><span data-stu-id="92d94-119">Description</span></span>  
 <span data-ttu-id="92d94-120">Не используется.</span><span class="sxs-lookup"><span data-stu-id="92d94-120">Not used.</span></span>  
  
### <a name="set-this-value-to-selected-cells"></a><span data-ttu-id="92d94-121">Присвоить указанное значение выбранным ячейкам</span><span class="sxs-lookup"><span data-stu-id="92d94-121">Set this value to selected cells</span></span>  
 <span data-ttu-id="92d94-122">Выберите, как источник ODBC обрабатывает все выбранные ячейки при возникновении ошибки или усечения: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="92d94-122">Select how the ODBC source handles all selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="apply"></a><span data-ttu-id="92d94-123">Применить</span><span class="sxs-lookup"><span data-stu-id="92d94-123">Apply</span></span>  
 <span data-ttu-id="92d94-124">Примените параметры обработки ошибок к выбранным ячейкам.</span><span class="sxs-lookup"><span data-stu-id="92d94-124">Apply the error handling options to the selected cells.</span></span>  
  
## <a name="error-handling-options"></a><span data-ttu-id="92d94-125">Параметры обработки ошибок</span><span class="sxs-lookup"><span data-stu-id="92d94-125">Error Handling Options</span></span>  
 <span data-ttu-id="92d94-126">Следующие параметры позволяют настроить обработку ошибок и усечений источником ODBC.</span><span class="sxs-lookup"><span data-stu-id="92d94-126">You use the following options to configure how the ODBC source handles errors and truncations.</span></span>  
  
### <a name="fail-component"></a><span data-ttu-id="92d94-127">Компонент, завершившийся сбоем</span><span class="sxs-lookup"><span data-stu-id="92d94-127">Fail Component</span></span>  
 <span data-ttu-id="92d94-128">Задача потока данных заканчивается сбоем, если возникли ошибка или усечение.</span><span class="sxs-lookup"><span data-stu-id="92d94-128">The Data Flow task fails when an error or a truncation occurs.</span></span> <span data-ttu-id="92d94-129">Это поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="92d94-129">This is the default behavior.</span></span>  
  
### <a name="ignore-failure"></a><span data-ttu-id="92d94-130">Пропуск неудачи</span><span class="sxs-lookup"><span data-stu-id="92d94-130">Ignore Failure</span></span>  
 <span data-ttu-id="92d94-131">Ошибка или усечение пропускается.</span><span class="sxs-lookup"><span data-stu-id="92d94-131">The error or the truncation is ignored.</span></span>  
  
### <a name="redirect-flow"></a><span data-ttu-id="92d94-132">Перенаправление потока</span><span class="sxs-lookup"><span data-stu-id="92d94-132">Redirect Flow</span></span>  
 <span data-ttu-id="92d94-133">Строка, вызывающая ошибку или усечение, направляется на вывод ошибок источника ODBC.</span><span class="sxs-lookup"><span data-stu-id="92d94-133">The row that is causing the error or the truncation is directed to the error output of the ODBC source.</span></span> <span data-ttu-id="92d94-134">Дополнительные сведения см. в статье [ODBC Source](data-flow/odbc-source.md).</span><span class="sxs-lookup"><span data-stu-id="92d94-134">For more information, see [ODBC Source](data-flow/odbc-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92d94-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="92d94-135">See Also</span></span>  
 <span data-ttu-id="92d94-136">[Редактор источника ODBC &#40;страница "Диспетчер соединений"&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="92d94-136">[ODBC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="92d94-137">Редактор источника ODBC (страница "Столбцы")</span><span class="sxs-lookup"><span data-stu-id="92d94-137">ODBC Source Editor &#40;Columns Page&#41;</span></span>](../../2014/integration-services/odbc-source-editor-columns-page.md)  
  
  
