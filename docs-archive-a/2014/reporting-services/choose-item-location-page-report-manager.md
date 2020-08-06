---
title: Страница «Выбор расположения элементов» (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4a53a1a8-d1e1-47ef-b1fc-63352ece7d3c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 82c044731552033ddd7fc0d8150cf83f300c7d9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729145"
---
# <a name="choose-item-location-page-report-manager"></a><span data-ttu-id="c8bc2-102">Страница «Выбор расположения элементов» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="c8bc2-102">Choose Item Location Page (Report Manager)</span></span>
  <span data-ttu-id="c8bc2-103">Страница «Выбор расположения элемента» позволяет выбрать папку для нового связанного отчета или новой модели.</span><span class="sxs-lookup"><span data-stu-id="c8bc2-103">Use the Choose Item Location page to select a folder for a new linked report or a new model.</span></span> <span data-ttu-id="c8bc2-104">При создании связанного отчета или модели для определенной группы пользователей может потребоваться переместить элемент в папку с другими отчетами и моделями этой группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="c8bc2-104">If you are creating a linked report or a model for a specific group of users, you may want to place the item in a folder that contains other reports and models they use.</span></span> <span data-ttu-id="c8bc2-105">Необходимо выбрать существующую папку, для которой имеется разрешение на добавление данных.</span><span class="sxs-lookup"><span data-stu-id="c8bc2-105">You must choose a folder that already exists and for which you have permission to add contents.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="c8bc2-106">Навигация</span><span class="sxs-lookup"><span data-stu-id="c8bc2-106">Navigation</span></span>  
 <span data-ttu-id="c8bc2-107">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующие процедуры.</span><span class="sxs-lookup"><span data-stu-id="c8bc2-107">Use the following procedures to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-choose-item-location-page-for-a-report"></a><span data-ttu-id="c8bc2-108">Открытие страницы «Выбор расположения элементов» отчета</span><span class="sxs-lookup"><span data-stu-id="c8bc2-108">To open the Choose Item Location page for a report</span></span>  
  
1.  <span data-ttu-id="c8bc2-109">Откройте диспетчер отчетов и найдите отчет, для которого необходимо добавить связанный отчет.</span><span class="sxs-lookup"><span data-stu-id="c8bc2-109">Open Report Manager, and locate the report for which you want to add a linked report.</span></span>  
  
2.  <span data-ttu-id="c8bc2-110">Подведите курсор к отчету и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="c8bc2-110">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="c8bc2-111">В раскрывающемся меню выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="c8bc2-111">In the drop-down menu, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="c8bc2-112">Нажмите кнопку **Создать связанный отчет** , чтобы открыть страницу «Создание связанного отчета».</span><span class="sxs-lookup"><span data-stu-id="c8bc2-112">Click **Create Linked Report** to open the New Linked Report page.</span></span>  
  
    -   <span data-ttu-id="c8bc2-113">Выберите **Управление** , чтобы открыть страницу свойств отчета «Общие».</span><span class="sxs-lookup"><span data-stu-id="c8bc2-113">Click **Manage** to open the General properties page for the report.</span></span> <span data-ttu-id="c8bc2-114">Затем нажмите кнопку **Создать связанный отчет** , чтобы открыть страницу «Создание связанного отчета».</span><span class="sxs-lookup"><span data-stu-id="c8bc2-114">Then click **Create Linked Report** to open the New Linked Report page.</span></span>  
  
4.  <span data-ttu-id="c8bc2-115">На вкладке страницы свойств **Общие** нажмите кнопку **Изменить местоположение** , чтобы открыть страницу «Выбор расположения элементов».</span><span class="sxs-lookup"><span data-stu-id="c8bc2-115">On the **General** tab, on the properties page, click **Change Location** to open the Choose Item Location page.</span></span>  
  
###### <a name="to-open-the-choose-item-location-page-for-a-model"></a><span data-ttu-id="c8bc2-116">Открытие страницы «Выбор расположения элементов» модели</span><span class="sxs-lookup"><span data-stu-id="c8bc2-116">To open the Choose Item Location page for a model</span></span>  
  
1.  <span data-ttu-id="c8bc2-117">Откройте диспетчер отчетов и найдите источник данных, к которому необходимо добавить модель.</span><span class="sxs-lookup"><span data-stu-id="c8bc2-117">Open Report Manager, and locate the data source for which you want to add a model.</span></span>  
  
2.  <span data-ttu-id="c8bc2-118">Подведите курсор к источнику данных и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="c8bc2-118">Hover over the data source, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="c8bc2-119">В раскрывающемся меню выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="c8bc2-119">In the drop-down menu, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="c8bc2-120">Нажмите кнопку **Создать модель отчета** , чтобы открыть страницу «Создать модель».</span><span class="sxs-lookup"><span data-stu-id="c8bc2-120">Click **Generate Report Model** to open the New Model page.</span></span>  
  
    -   <span data-ttu-id="c8bc2-121">Выберите **Управление** , чтобы открыть страницу свойств источника данных «Общие».</span><span class="sxs-lookup"><span data-stu-id="c8bc2-121">Click **Manage** to open the General properties page for the data source.</span></span> <span data-ttu-id="c8bc2-122">Затем нажмите кнопку **Создать модель отчета** , чтобы открыть страницу «Создать модель».</span><span class="sxs-lookup"><span data-stu-id="c8bc2-122">Then click **Generate Model** to open the New Model page.</span></span>  
  
4.  <span data-ttu-id="c8bc2-123">На вкладке страницы свойств **Общие** нажмите кнопку **Изменить местоположение** , чтобы открыть страницу «Выбор расположения элементов».</span><span class="sxs-lookup"><span data-stu-id="c8bc2-123">On the **General** tab, on the properties page, click **Change Location** to open the Choose Item Location page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c8bc2-124">Варианты</span><span class="sxs-lookup"><span data-stu-id="c8bc2-124">Options</span></span>  
 <span data-ttu-id="c8bc2-125">**Расположение**</span><span class="sxs-lookup"><span data-stu-id="c8bc2-125">**Location**</span></span>  
 <span data-ttu-id="c8bc2-126">Укажите имя папки, в которую будет помещен создаваемый элемент.</span><span class="sxs-lookup"><span data-stu-id="c8bc2-126">Specify the name of the folder to contain the item you are creating.</span></span> <span data-ttu-id="c8bc2-127">Можно ввести полное имя или выбрать нужную папку в древовидном представлении.</span><span class="sxs-lookup"><span data-stu-id="c8bc2-127">You can type the full name or use the tree view to navigate to the folder you want to use.</span></span>  
  
 <span data-ttu-id="c8bc2-128">**Представление в виде дерева**</span><span class="sxs-lookup"><span data-stu-id="c8bc2-128">**Tree view**</span></span>  
 <span data-ttu-id="c8bc2-129">Позволяет показать структуру папок пространства имен сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="c8bc2-129">Shows the folder structure of report server namespace.</span></span> <span data-ttu-id="c8bc2-130">Чтобы добавить в поле **Расположение** полный путь к папке, щелкните имя папки.</span><span class="sxs-lookup"><span data-stu-id="c8bc2-130">Click a folder name to add the full path to the **Location** field.</span></span>  
  
 <span data-ttu-id="c8bc2-131">Щелкните значок (+) или (-), чтобы открыть или закрыть папку без добавления ее имени в поле **Расположение** .</span><span class="sxs-lookup"><span data-stu-id="c8bc2-131">Click the expand (+) and collapse (-) icons in the tree view to open and close folders without adding the folder names to the **Location** field.</span></span> <span data-ttu-id="c8bc2-132">Чтобы добавить имя папки в поле **Расположение** , щелкните имя папки.</span><span class="sxs-lookup"><span data-stu-id="c8bc2-132">To add a folder name to the **Location** field, click the name of the folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8bc2-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="c8bc2-133">See Also</span></span>  
 <span data-ttu-id="c8bc2-134">[Страница создания связанного отчета &#40;диспетчер отчетов&#41;](../../2014/reporting-services/new-linked-report-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="c8bc2-134">[New Linked Report Page &#40;Report Manager&#41;](../../2014/reporting-services/new-linked-report-page-report-manager.md) </span></span>  
 <span data-ttu-id="c8bc2-135">[Диспетчер отчетов &#40;новой страницы модели&#41;](../../2014/reporting-services/new-model-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="c8bc2-135">[New Model Page &#40;Report Manager&#41;](../../2014/reporting-services/new-model-page-report-manager.md) </span></span>  
 [<span data-ttu-id="c8bc2-136">Справка F1 диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="c8bc2-136">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
