---
title: Редактор источника «ODBC» (страница «Столбцы») | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.columns.f1
ms.assetid: 565984eb-8318-4be7-bebc-262209cf5065
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7a11ab6a86978366d07fbe63362f1702310b5d89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734358"
---
# <a name="odbc-source-editor-columns-page"></a><span data-ttu-id="1a76b-102">Редактор источника «ODBC» (страница «Столбцы»)</span><span class="sxs-lookup"><span data-stu-id="1a76b-102">ODBC Source Editor (Columns Page)</span></span>
  <span data-ttu-id="1a76b-103">Страница **Столбцы** диалогового окна **Редактор источника ODBC** используется для сопоставления выходного столбца с каждым внешним (исходным) столбцом.</span><span class="sxs-lookup"><span data-stu-id="1a76b-103">Use the **Columns** page of the **ODBC Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="1a76b-104">Дополнительные сведения об источнике ODBC см. в разделе [ODBC Source](data-flow/odbc-source.md).</span><span class="sxs-lookup"><span data-stu-id="1a76b-104">To learn more about the ODBC source, see [ODBC Source](data-flow/odbc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="1a76b-105">Список задач</span><span class="sxs-lookup"><span data-stu-id="1a76b-105">Task List</span></span>  
 <span data-ttu-id="1a76b-106">**Открытие страницы «Столбцы» редактора источника ODBC**</span><span class="sxs-lookup"><span data-stu-id="1a76b-106">**To open the ODBC Source Editor Columns Page**</span></span>  
  
1.  <span data-ttu-id="1a76b-107">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]откройте пакет служб [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] , содержащий источник ODBC.</span><span class="sxs-lookup"><span data-stu-id="1a76b-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC source.</span></span>  
  
2.  <span data-ttu-id="1a76b-108">На вкладке **Поток данных** дважды щелкните источник ODBC.</span><span class="sxs-lookup"><span data-stu-id="1a76b-108">On the **Data Flow** tab, double-click the ODBC source.</span></span>  
  
3.  <span data-ttu-id="1a76b-109">В окне **Редактор источника ODBC**нажмите кнопку **Столбцы**.</span><span class="sxs-lookup"><span data-stu-id="1a76b-109">In the **ODBC Source Editor**, click **Columns**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1a76b-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="1a76b-110">Options</span></span>  
  
### <a name="available-external-columns"></a><span data-ttu-id="1a76b-111">Доступные внешние столбцы</span><span class="sxs-lookup"><span data-stu-id="1a76b-111">Available External Columns</span></span>  
 <span data-ttu-id="1a76b-112">Список доступных внешних столбцов источника данных.</span><span class="sxs-lookup"><span data-stu-id="1a76b-112">A list of available external columns in the data source.</span></span> <span data-ttu-id="1a76b-113">В этой таблице нельзя добавлять или удалять столбцы.</span><span class="sxs-lookup"><span data-stu-id="1a76b-113">You cannot use this table to add or delete columns.</span></span> <span data-ttu-id="1a76b-114">Выберите используемые столбцы источника.</span><span class="sxs-lookup"><span data-stu-id="1a76b-114">Select the columns to use from the source.</span></span> <span data-ttu-id="1a76b-115">Выбранные столбцы добавляются в список **Внешний столбец** в порядке выбора.</span><span class="sxs-lookup"><span data-stu-id="1a76b-115">The selected columns are added to the **External Column** list in the order they are selected.</span></span>  
  
 <span data-ttu-id="1a76b-116">Чтобы выбрать все столбцы, установите флажок **Выделить все** .</span><span class="sxs-lookup"><span data-stu-id="1a76b-116">Select the **Select All** check box to select all of the columns.</span></span>  
  
### <a name="external-column"></a><span data-ttu-id="1a76b-117">Внешний столбец</span><span class="sxs-lookup"><span data-stu-id="1a76b-117">External Column</span></span>  
 <span data-ttu-id="1a76b-118">Представление внешних (исходных) столбцов в порядке, заданном при настройке компонентов, которые обрабатывают данные из источника ODBC.</span><span class="sxs-lookup"><span data-stu-id="1a76b-118">A view of the external (source) columns in the order that you see them when configuring components that consume data from the ODBC source.</span></span>  
  
### <a name="output-column"></a><span data-ttu-id="1a76b-119">Выходной столбец</span><span class="sxs-lookup"><span data-stu-id="1a76b-119">Output Column</span></span>  
 <span data-ttu-id="1a76b-120">Введите уникальное имя для каждого выходного столбца.</span><span class="sxs-lookup"><span data-stu-id="1a76b-120">Enter a unique name for each output column.</span></span> <span data-ttu-id="1a76b-121">По умолчанию используется имя выбранного внешнего (исходного) столбца, однако можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="1a76b-121">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="1a76b-122">Введенное имя отображается в конструкторе служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="1a76b-122">The name entered is displayed in the SSIS Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a76b-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="1a76b-123">See Also</span></span>  
 <span data-ttu-id="1a76b-124">[Редактор источника ODBC &#40;страница "Диспетчер соединений"&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="1a76b-124">[ODBC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="1a76b-125">Редактор источника ODBC (страница "Вывод ошибок")</span><span class="sxs-lookup"><span data-stu-id="1a76b-125">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/odbc-source-editor-error-output-page.md)  
  
  
