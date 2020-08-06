---
title: Редактор назначения SAP BW (страница "Сопоставления") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: dfa1f1d6-6b64-4331-bdc5-eaa8b7aa41a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7c4c2803be3e2649f7425a2974dae8ac0a80fae7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728541"
---
# <a name="sap-bw-destination-editor-mappings-page"></a><span data-ttu-id="1b5f8-102">Редактор назначений SAP BW (страница «Сопоставления»)</span><span class="sxs-lookup"><span data-stu-id="1b5f8-102">SAP BW Destination Editor (Mappings Page)</span></span>
  <span data-ttu-id="1b5f8-103">Страница **Сопоставления** диалогового окна **Редактор назначений SAP BW** используется для сопоставления входных столбцов с целевыми столбцами.</span><span class="sxs-lookup"><span data-stu-id="1b5f8-103">Use the **Mappings** page of the **SAP BW Destination Editor** to map input columns to destination columns.</span></span>  
  
 <span data-ttu-id="1b5f8-104">Для получения дополнительных сведений о назначении SAP BW для [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW см. раздел [Назначение SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="1b5f8-104">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1b5f8-105">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="1b5f8-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="1b5f8-106">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="1b5f8-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="1b5f8-107">**Открытие страницы «Сопоставления»**</span><span class="sxs-lookup"><span data-stu-id="1b5f8-107">**To open the Mappings page**</span></span>  
  
1.  <span data-ttu-id="1b5f8-108">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="1b5f8-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="1b5f8-109">На вкладке **Поток данных** дважды щелкните назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="1b5f8-109">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="1b5f8-110">В окне **Редактор назначений SAP BW**щелкните **Сопоставления** , чтобы открыть страницу редактора **Сопоставления** .</span><span class="sxs-lookup"><span data-stu-id="1b5f8-110">In the **SAP BW Destination Editor**, click **Mappings** to open the **Mappings** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1b5f8-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="1b5f8-111">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1b5f8-112">Если вы не знаете все значения, необходимые для настройки назначения, может потребоваться связаться с администратором SAP.</span><span class="sxs-lookup"><span data-stu-id="1b5f8-112">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="1b5f8-113">Страница **Сопоставления** **Редактора назначения SAP BW** состоит из двух разделов.</span><span class="sxs-lookup"><span data-stu-id="1b5f8-113">The **Mappings** page of the **SAP BW Destination Editor consists** of two sections:</span></span>  
  
-   <span data-ttu-id="1b5f8-114">Верхняя часть содержит доступные входные столбцы и целевые столбцы и используется для создания сопоставлений между этими двумя типами столбцов.</span><span class="sxs-lookup"><span data-stu-id="1b5f8-114">The upper section shows the available input and destination columns and lets you create mappings between these two types of columns.</span></span>  
  
-   <span data-ttu-id="1b5f8-115">Нижний раздел представляет собой таблицу, в которой указывается, какие входные столбцы были сопоставлены с какими целевыми столбцами.</span><span class="sxs-lookup"><span data-stu-id="1b5f8-115">The lower section is a table that lists which input columns have been mapped to which output columns.</span></span>  
  
### <a name="upper-section-options"></a><span data-ttu-id="1b5f8-116">Параметры в верхней области</span><span class="sxs-lookup"><span data-stu-id="1b5f8-116">Upper Section Options</span></span>  
 <span data-ttu-id="1b5f8-117">Верхняя область содержит следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="1b5f8-117">The upper section has the following options:</span></span>  
  
 <span data-ttu-id="1b5f8-118">**Доступные входные столбцы**</span><span class="sxs-lookup"><span data-stu-id="1b5f8-118">**Available Input Columns**</span></span>  
 <span data-ttu-id="1b5f8-119">Просмотрите список доступных входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="1b5f8-119">View the list of available input columns.</span></span>  
  
 <span data-ttu-id="1b5f8-120">Чтобы сопоставить входной столбец с целевым столбцом, перетащите столбец из списка **Доступные входные столбцы** и поместите этот столбец в столбец в списке **Доступные целевые столбцы** .</span><span class="sxs-lookup"><span data-stu-id="1b5f8-120">To map an input column to a destination column, drag a column from the **Available Input Columns** list and drop that column onto a column in the **Available Destination Columns** list.</span></span>  
  
 <span data-ttu-id="1b5f8-121">**Доступные целевые столбцы**</span><span class="sxs-lookup"><span data-stu-id="1b5f8-121">**Available Destination Columns**</span></span>  
 <span data-ttu-id="1b5f8-122">Просмотрите список доступных целевых столбцов.</span><span class="sxs-lookup"><span data-stu-id="1b5f8-122">View the list of available destination columns.</span></span>  
  
 <span data-ttu-id="1b5f8-123">Чтобы сопоставить входной столбец с целевым столбцом, перетащите столбец из списка **Доступные входные столбцы** и поместите этот столбец в столбец в списке **Доступные целевые столбцы** .</span><span class="sxs-lookup"><span data-stu-id="1b5f8-123">To map an input column to destination column, drag a column from the **Available Input Columns** list and drop that column onto a column in the **Available Destination Columns** list.</span></span>  
  
 <span data-ttu-id="1b5f8-124">Верхний раздел также содержит контекстное меню, которое открывается при щелчке правой кнопкой мыши по фону.</span><span class="sxs-lookup"><span data-stu-id="1b5f8-124">The upper section also has a context menu that you can open by right-clicking on the background.</span></span> <span data-ttu-id="1b5f8-125">Это контекстное меню содержит следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="1b5f8-125">This context menu contains the following options:</span></span>  
  
-   <span data-ttu-id="1b5f8-126">**Выбрать все сопоставления**</span><span class="sxs-lookup"><span data-stu-id="1b5f8-126">**Select All Mappings**</span></span>  
  
-   <span data-ttu-id="1b5f8-127">**Удалить выбранные сопоставления**</span><span class="sxs-lookup"><span data-stu-id="1b5f8-127">**Delete Selected Mappings**</span></span>  
  
-   <span data-ttu-id="1b5f8-128">**Сопоставлять элементы по совпадению имен**</span><span class="sxs-lookup"><span data-stu-id="1b5f8-128">**Map Items by Matching Names**</span></span>  
  
### <a name="lower-section-columns"></a><span data-ttu-id="1b5f8-129">Столбцы в нижнем разделе</span><span class="sxs-lookup"><span data-stu-id="1b5f8-129">Lower Section Columns</span></span>  
 <span data-ttu-id="1b5f8-130">Нижний раздел представляет собой таблицу сопоставлений и содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="1b5f8-130">The lower section is a table of the mappings, and has the following columns:</span></span>  
  
 <span data-ttu-id="1b5f8-131">**Входной столбец**</span><span class="sxs-lookup"><span data-stu-id="1b5f8-131">**Input Column**</span></span>  
 <span data-ttu-id="1b5f8-132">Позволяет просматривать выбранные входные столбцы.</span><span class="sxs-lookup"><span data-stu-id="1b5f8-132">View the input columns that you have selected.</span></span>  
  
 <span data-ttu-id="1b5f8-133">Для сопоставления другого входного столбца с тем же целевым столбцом выберите другой входной столбец в списке.</span><span class="sxs-lookup"><span data-stu-id="1b5f8-133">To map a different input column to the same destination column, select a different input column in the list.</span></span> <span data-ttu-id="1b5f8-134">Для удаления сопоставления выберите команду **\<ignore>** , чтобы исключить входной столбец из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="1b5f8-134">To remove a mapping, select **\<ignore>** to exclude the input column from the output.</span></span>  
  
 <span data-ttu-id="1b5f8-135">**Целевой столбец**</span><span class="sxs-lookup"><span data-stu-id="1b5f8-135">**Destination Column**</span></span>  
 <span data-ttu-id="1b5f8-136">Позволяет просмотреть каждый из доступных целевых столбцов без учета наличия или отсутствия сопоставления.</span><span class="sxs-lookup"><span data-stu-id="1b5f8-136">View each available destination column, regardless of whether that column is mapped or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b5f8-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="1b5f8-137">See Also</span></span>  
 <span data-ttu-id="1b5f8-138">[Редактор назначений SAP BW (страница "Диспетчер подключений")](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="1b5f8-138">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="1b5f8-139">[Редактор назначений SAP BW (страница "Вывод ошибок")](sap-bw-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="1b5f8-139">[SAP BW Destination Editor &#40;Error Output Page&#41;](sap-bw-destination-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="1b5f8-140">[Редактор назначений SAP BW (страница "Дополнительно")](sap-bw-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="1b5f8-140">[SAP BW Destination Editor &#40;Advanced Page&#41;](sap-bw-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="1b5f8-141">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="1b5f8-141">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
