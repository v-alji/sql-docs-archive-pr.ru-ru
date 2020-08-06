---
title: Редактор источника «CDC» (страница «вывод ошибок») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.errorhandling.f1
ms.assetid: 8a4c2cb8-fd2f-4c45-824f-b93473a8981e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b39532304fddfa90fabe8cafe2a6caf5b1fb5c8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667846"
---
# <a name="cdc-source-editor-error-output-page"></a><span data-ttu-id="863aa-102">Редактор источника «CDC» (страница «Вывод ошибок»)</span><span class="sxs-lookup"><span data-stu-id="863aa-102">CDC Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="863aa-103">Страница **Вывод ошибок** диалогового окна **Редактор источника CDC** используется для выбора параметров обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="863aa-103">Use the **Error Output** page of the **CDC Source Editor** dialog box to select error handling options.</span></span>  
  
 <span data-ttu-id="863aa-104">Дополнительные сведения об источнике CDC см. в разделе [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="863aa-104">To learn more about the CDC source, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="863aa-105">Список задач</span><span class="sxs-lookup"><span data-stu-id="863aa-105">Task List</span></span>  
 <span data-ttu-id="863aa-106">**Открытие страницы «Вывод ошибок» редактора источника CDC**</span><span class="sxs-lookup"><span data-stu-id="863aa-106">**To open the CDC Source Editor Error Output Page**</span></span>  
  
1.  <span data-ttu-id="863aa-107">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]откройте пакет служб [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] , содержащий источник CDC.</span><span class="sxs-lookup"><span data-stu-id="863aa-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the CDC source.</span></span>  
  
2.  <span data-ttu-id="863aa-108">На вкладке **Поток данных** дважды щелкните источник CDC.</span><span class="sxs-lookup"><span data-stu-id="863aa-108">On the **Data Flow** tab, double-click the CDC source.</span></span>  
  
3.  <span data-ttu-id="863aa-109">В окне **Редактор источника CDC**нажмите кнопку **Вывод ошибок**.</span><span class="sxs-lookup"><span data-stu-id="863aa-109">In the **CDC Source Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="863aa-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="863aa-110">Options</span></span>  
 <span data-ttu-id="863aa-111">**Ввод-вывод**</span><span class="sxs-lookup"><span data-stu-id="863aa-111">**Input/Output**</span></span>  
 <span data-ttu-id="863aa-112">Просмотр имени источника данных.</span><span class="sxs-lookup"><span data-stu-id="863aa-112">View the name of the data source.</span></span>  
  
 <span data-ttu-id="863aa-113">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="863aa-113">**Column**</span></span>  
 <span data-ttu-id="863aa-114">Просмотрите внешние (исходные) столбцы, выбранные на странице **Диспетчер соединений** диалогового окна **Редактор источника CDC** .</span><span class="sxs-lookup"><span data-stu-id="863aa-114">View the external (source) columns that you selected on the **Connection Manager** page of the **CDC Source Editor** dialog box.</span></span>  
  
 <span data-ttu-id="863aa-115">**Ошибка**</span><span class="sxs-lookup"><span data-stu-id="863aa-115">**Error**</span></span>  
 <span data-ttu-id="863aa-116">Выберите порядок обработки ошибок в потоке источником CDC: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="863aa-116">Select how the CDC source should handle errors in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="863aa-117">**Усечение**</span><span class="sxs-lookup"><span data-stu-id="863aa-117">**Truncation**</span></span>  
 <span data-ttu-id="863aa-118">Выберите порядок обработки усечений в потоке источником CDC: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="863aa-118">Select how the CDC source should handle truncation in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="863aa-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="863aa-119">**Description**</span></span>  
 <span data-ttu-id="863aa-120">Не используется.</span><span class="sxs-lookup"><span data-stu-id="863aa-120">Not used.</span></span>  
  
 <span data-ttu-id="863aa-121">**Присвоить указанное значение выбранным ячейкам**</span><span class="sxs-lookup"><span data-stu-id="863aa-121">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="863aa-122">Выберите, как источник CDC обрабатывает все выбранные ячейки при возникновении ошибки или усечения: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="863aa-122">Select how the CDC source handles all selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="863aa-123">**Применить**</span><span class="sxs-lookup"><span data-stu-id="863aa-123">**Apply**</span></span>  
 <span data-ttu-id="863aa-124">Примените параметры обработки ошибок к выбранным ячейкам.</span><span class="sxs-lookup"><span data-stu-id="863aa-124">Apply the error handling options to the selected cells.</span></span>  
  
## <a name="error-handling-options"></a><span data-ttu-id="863aa-125">Параметры обработки ошибок</span><span class="sxs-lookup"><span data-stu-id="863aa-125">Error Handling Options</span></span>  
 <span data-ttu-id="863aa-126">Следующие параметры позволяют настроить обработку ошибок и усечений источником CDC.</span><span class="sxs-lookup"><span data-stu-id="863aa-126">You use the following options to configure how the CDC source handles errors and truncations.</span></span>  
  
 <span data-ttu-id="863aa-127">**Компонент, завершившийся сбоем**</span><span class="sxs-lookup"><span data-stu-id="863aa-127">**Fail Component**</span></span>  
 <span data-ttu-id="863aa-128">Задача потока данных заканчивается сбоем, если возникли ошибка или усечение.</span><span class="sxs-lookup"><span data-stu-id="863aa-128">The Data Flow task fails when an error or a truncation occurs.</span></span> <span data-ttu-id="863aa-129">Это поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="863aa-129">This is the default behavior.</span></span>  
  
 <span data-ttu-id="863aa-130">**Пропуск неудачи**</span><span class="sxs-lookup"><span data-stu-id="863aa-130">**Ignore Failure**</span></span>  
 <span data-ttu-id="863aa-131">Ошибка или усечение пропускается, и строка данных направляется на выход источника CDC.</span><span class="sxs-lookup"><span data-stu-id="863aa-131">The error or the truncation is ignored and the data row is directed to the CDC source output.</span></span>  
  
 <span data-ttu-id="863aa-132">**Перенаправление потока**</span><span class="sxs-lookup"><span data-stu-id="863aa-132">**Redirect Flow**</span></span>  
 <span data-ttu-id="863aa-133">Ошибка или строка данных усечения направляется на выход ошибок источника CDC.</span><span class="sxs-lookup"><span data-stu-id="863aa-133">The error or the truncation data row is directed to the error output of the CDC source.</span></span> <span data-ttu-id="863aa-134">В этом случае используется обработка ошибок источника CDC.</span><span class="sxs-lookup"><span data-stu-id="863aa-134">In this case the CDC source error handling is used.</span></span> <span data-ttu-id="863aa-135">Дополнительные сведения см. в статье [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="863aa-135">For more information, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="863aa-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="863aa-136">See Also</span></span>  
 <span data-ttu-id="863aa-137">[Редактор источника "CDC" (страница "Диспетчер соединений")](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="863aa-137">[CDC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="863aa-138">Редактор источника "CDC" (страница "Столбцы")</span><span class="sxs-lookup"><span data-stu-id="863aa-138">CDC Source Editor &#40;Columns Page&#41;</span></span>](../../2014/integration-services/cdc-source-editor-columns-page.md)  
  
  
