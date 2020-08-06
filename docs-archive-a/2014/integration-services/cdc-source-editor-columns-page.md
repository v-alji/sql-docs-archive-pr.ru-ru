---
title: Редактор источника «CDC» (страница «Столбцы») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.columns.f1
ms.assetid: bcf3030e-98d8-4445-967c-33c3f8ecb4fc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa30defb5e6873ea05e8e41c733477cf50d0dc4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667847"
---
# <a name="cdc-source-editor-columns-page"></a><span data-ttu-id="a70be-102">Редактор источника «CDC» (страница «Столбцы»)</span><span class="sxs-lookup"><span data-stu-id="a70be-102">CDC Source Editor (Columns Page)</span></span>
  <span data-ttu-id="a70be-103">Страница **Столбцы** диалогового окна **Редактор источника CDC** используется для сопоставления выходного столбца с каждым внешним (исходным) столбцом.</span><span class="sxs-lookup"><span data-stu-id="a70be-103">Use the **Columns** page of the **CDC Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="a70be-104">Дополнительные сведения об источнике CDC см. в разделе [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="a70be-104">To learn more about the CDC source, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="a70be-105">Список задач</span><span class="sxs-lookup"><span data-stu-id="a70be-105">Task List</span></span>  
 <span data-ttu-id="a70be-106">**Открытие страницы «Столбцы» редактора источника CDC**</span><span class="sxs-lookup"><span data-stu-id="a70be-106">**To open the CDC Source Editor Columns Page**</span></span>  
  
1.  <span data-ttu-id="a70be-107">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]откройте пакет служб [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] , содержащий источник CDC.</span><span class="sxs-lookup"><span data-stu-id="a70be-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the CDC source.</span></span>  
  
2.  <span data-ttu-id="a70be-108">На вкладке **Поток данных** дважды щелкните источник CDC.</span><span class="sxs-lookup"><span data-stu-id="a70be-108">On the **Data Flow** tab, double-click the CDC source.</span></span>  
  
3.  <span data-ttu-id="a70be-109">В окне **Редактор источника CDC**нажмите кнопку **Столбцы**.</span><span class="sxs-lookup"><span data-stu-id="a70be-109">In the **CDC Source Editor**, click **Columns**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a70be-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="a70be-110">Options</span></span>  
 <span data-ttu-id="a70be-111">**Доступные внешние столбцы**</span><span class="sxs-lookup"><span data-stu-id="a70be-111">**Available External Columns**</span></span>  
 <span data-ttu-id="a70be-112">Список доступных внешних столбцов источника данных.</span><span class="sxs-lookup"><span data-stu-id="a70be-112">A list of available external columns in the data source.</span></span> <span data-ttu-id="a70be-113">В этой таблице нельзя добавлять или удалять столбцы.</span><span class="sxs-lookup"><span data-stu-id="a70be-113">You cannot use this table to add or delete columns.</span></span> <span data-ttu-id="a70be-114">Выберите используемые столбцы источника.</span><span class="sxs-lookup"><span data-stu-id="a70be-114">Select the columns to use in the source.</span></span> <span data-ttu-id="a70be-115">Выбранные столбцы добавляются в список **Внешний столбец** в порядке выбора.</span><span class="sxs-lookup"><span data-stu-id="a70be-115">The selected columns are added to the **External Column** list in the order they are selected.</span></span>  
  
 <span data-ttu-id="a70be-116">**Внешний столбец**</span><span class="sxs-lookup"><span data-stu-id="a70be-116">**External Column**</span></span>  
 <span data-ttu-id="a70be-117">Представление внешних (исходных) столбцов в порядке, заданном при настройке компонентов, которые обрабатывают данные из источника CDC.</span><span class="sxs-lookup"><span data-stu-id="a70be-117">A view of the external (source) columns in the order that you see them when configuring components that consume data from the CDC source.</span></span> <span data-ttu-id="a70be-118">Чтобы изменить этот порядок, снимите флажки для выбранных столбцов в списке **Доступные внешние столбцы** , а затем выберите внешние столбцы в другом порядке.</span><span class="sxs-lookup"><span data-stu-id="a70be-118">To change this order, first clear the selected columns in the **Available External Columns** list, and then select external columns from the list in a different order.</span></span> <span data-ttu-id="a70be-119">Выбранные столбцы добавляются в список **Внешний столбец** в порядке выбора.</span><span class="sxs-lookup"><span data-stu-id="a70be-119">The selected columns are added to the **External Column** list in the order you select them.</span></span>  
  
 <span data-ttu-id="a70be-120">**Выходной столбец**</span><span class="sxs-lookup"><span data-stu-id="a70be-120">**Output Column**</span></span>  
 <span data-ttu-id="a70be-121">Введите уникальное имя для каждого выходного столбца.</span><span class="sxs-lookup"><span data-stu-id="a70be-121">Enter a unique name for each output column.</span></span> <span data-ttu-id="a70be-122">По умолчанию используется имя выбранного внешнего (исходного) столбца, но можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="a70be-122">The default is the name of the selected external (source) column, however you can choose any unique, descriptive name.</span></span> <span data-ttu-id="a70be-123">Введенное имя отображается в конструкторе служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="a70be-123">The name entered is displayed in the SSIS Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a70be-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="a70be-124">See Also</span></span>  
 <span data-ttu-id="a70be-125">[Редактор источника "CDC" (страница "Диспетчер соединений")](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="a70be-125">[CDC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="a70be-126">Редактор источника "CDC" (страница "Вывод ошибок")</span><span class="sxs-lookup"><span data-stu-id="a70be-126">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/cdc-source-editor-error-output-page.md)  
  
  
