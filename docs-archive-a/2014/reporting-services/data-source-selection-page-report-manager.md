---
title: Страница «Выбор источника данных» (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7f7e8b19-0c0b-4b1f-9cc1-057099aa07eb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 03c5558397786b02b764b78d47584d9b190290cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665854"
---
# <a name="data-source-selection-page-report-manager"></a><span data-ttu-id="12db8-102">Страница «Выбор источника данных» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="12db8-102">Data Source Selection Page (Report Manager)</span></span>
  <span data-ttu-id="12db8-103">Страница «Выбор источника данных» позволяет выбрать существующий совместно используемый элемент источника данных для использования в отчете или модели отчета.</span><span class="sxs-lookup"><span data-stu-id="12db8-103">Use the Data Source Selection page to select an existing shared data source item to use with a report or a report model.</span></span> <span data-ttu-id="12db8-104">Эту страницу можно также использовать для выбора другого источника данных.</span><span class="sxs-lookup"><span data-stu-id="12db8-104">You can also use this page to select a different data source.</span></span> <span data-ttu-id="12db8-105">Чтобы просмотреть тип источника данных или строку соединения, необходимо переместиться к общему источнику данных и открыть страницы «Свойства».</span><span class="sxs-lookup"><span data-stu-id="12db8-105">To view the data source type or connection string, you must navigate to the shared data source and open the property pages.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="12db8-106">Навигация</span><span class="sxs-lookup"><span data-stu-id="12db8-106">Navigation</span></span>  
 <span data-ttu-id="12db8-107">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="12db8-107">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-data-source-selection-page"></a><span data-ttu-id="12db8-108">Открытие страницы «Выбор источника данных»</span><span class="sxs-lookup"><span data-stu-id="12db8-108">To open the Data Source Selection page</span></span>  
  
1.  <span data-ttu-id="12db8-109">Откройте диспетчер отчетов и найдите отчет или модель, для которой необходимо выбрать источник данных.</span><span class="sxs-lookup"><span data-stu-id="12db8-109">Open Report Manager, and locate the report or model for which you want to select a data source.</span></span>  
  
2.  <span data-ttu-id="12db8-110">Подведите курсор к отчету и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="12db8-110">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="12db8-111">В раскрывающемся меню выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="12db8-111">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="12db8-112">Откроется страница свойств отчета или модели «Общие».</span><span class="sxs-lookup"><span data-stu-id="12db8-112">This opens the General properties page for the report or model.</span></span>  
  
4.  <span data-ttu-id="12db8-113">Перейдите на вкладку **Источники данных** .</span><span class="sxs-lookup"><span data-stu-id="12db8-113">Select the **Data Sources** tab.</span></span>  
  
5.  <span data-ttu-id="12db8-114">На панели свойств выберите **Общий источник данных** , а затем щелкните **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="12db8-114">In the properties pane, select **A shared data source** and then click **Browse**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="12db8-115">Варианты</span><span class="sxs-lookup"><span data-stu-id="12db8-115">Options</span></span>  
 <span data-ttu-id="12db8-116">**Расположение**</span><span class="sxs-lookup"><span data-stu-id="12db8-116">**Location**</span></span>  
 <span data-ttu-id="12db8-117">Позволяет задать полный путь к общему элементу источника данных, начинающийся с имени корневой папки.</span><span class="sxs-lookup"><span data-stu-id="12db8-117">Specify the full path to the shared data source item, beginning with the root folder name.</span></span> <span data-ttu-id="12db8-118">Этот путь можно ввести вручную или перейти к нужному общему источнику данных в древовидном представлении.</span><span class="sxs-lookup"><span data-stu-id="12db8-118">You can type the path name or use the tree view to navigate to the shared data source you want.</span></span>  
  
 <span data-ttu-id="12db8-119">**Представление в виде дерева**</span><span class="sxs-lookup"><span data-stu-id="12db8-119">**Tree view**</span></span>  
 <span data-ttu-id="12db8-120">Показывает структуру папок пространства имен для сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="12db8-120">Shows the folder structure of the report server namespace.</span></span> <span data-ttu-id="12db8-121">Щелкните общий элемент, источника данных, чтобы добавить полный путь к нему в поле **Размещение** .</span><span class="sxs-lookup"><span data-stu-id="12db8-121">Click a shared data source item to add the full path to the **Location** field.</span></span>  
  
 <span data-ttu-id="12db8-122">**OK**</span><span class="sxs-lookup"><span data-stu-id="12db8-122">**OK**</span></span>  
 <span data-ttu-id="12db8-123">Нажмите, чтобы скопировать выбор источника данных на страницу свойств источников данных.</span><span class="sxs-lookup"><span data-stu-id="12db8-123">Click to copy the data source selection to the Data Sources properties page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12db8-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="12db8-124">See Also</span></span>  
 <span data-ttu-id="12db8-125">[Управление источниками данных отчета](report-data/manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="12db8-125">[Manage Report Data Sources](report-data/manage-report-data-sources.md) </span></span>  
 <span data-ttu-id="12db8-126">[Задание учетных данных и сведениях о соединении для источников данных отчета](report-data/specify-credential-and-connection-information-for-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="12db8-126">[Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md) </span></span>  
 <span data-ttu-id="12db8-127">[Страница свойств «Источники данных» &#40;диспетчер отчетов&#41;](../../2014/reporting-services/data-sources-properties-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="12db8-127">[Data Sources Properties Page &#40;Report Manager&#41;](../../2014/reporting-services/data-sources-properties-page-report-manager.md) </span></span>  
 <span data-ttu-id="12db8-128">[Страница "Создание источника данных" &#40;диспетчер отчетов&#41;](../../2014/reporting-services/new-data-source-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="12db8-128">[New Data Source Page &#40;Report Manager&#41;](../../2014/reporting-services/new-data-source-page-report-manager.md) </span></span>  
 [<span data-ttu-id="12db8-129">Справка F1 диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="12db8-129">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
