---
title: Страница «Создание связанного отчета» (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fefb46e8-6901-4d50-a3f8-7c49ad72e7b1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 61138e51cfd9bb6e1ee124dd4aa3bc224d8aebcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666457"
---
# <a name="new-linked-report-page-report-manager"></a><span data-ttu-id="2a6cc-102">Страница «Создание связанного отчета» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="2a6cc-102">New Linked Report Page (Report Manager)</span></span>
  <span data-ttu-id="2a6cc-103">Используйте страницу «Создание связанного отчета» для формирования нового связанного отчета.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-103">Use the New Linked Report page to create a linked report.</span></span> <span data-ttu-id="2a6cc-104">Связанный отчет — это отчет с собственными параметрами и свойствами, но ссылающийся на определение другого отчета.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-104">A linked report is a report with settings and properties of its own, but links to the report definition of another report.</span></span> <span data-ttu-id="2a6cc-105">Связанные отчеты полезны, когда имеется базовый отчет, который нужно изменять для конкретных групп пользователей. Например, региональный отчет, который возвращает разные данные в зависимости от регионального кода, заданного в виде параметра.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-105">Linked reports are useful when you have a base report that you want to vary for specific groups or users; for example, a regional report that returns different data based on a regional code that you specify as a parameter.</span></span> <span data-ttu-id="2a6cc-106">Связанный отчет, как правило, создается из параметризованного отчета, когда нужно изменить, а затем сохранить разные значения параметров для каждого экземпляра отчета.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-106">A linked report is typically created from a parameterized report when you want to vary and then save different parameter values with each report instance.</span></span> <span data-ttu-id="2a6cc-107">Но связанный отчет можно создавать на основе любого доступного отчета.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-107">However, you can create a linked report from any report to which you have access.</span></span>  
  
 <span data-ttu-id="2a6cc-108">Связанный отчет может иметь собственное имя, описание, размещение, свойства параметров, свойства выполнения отчетов, свойства журнала отчетов, разрешения и подписки.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-108">A linked report can have its own name, description, location, parameter properties, report execution properties, report history properties, permissions, and subscriptions.</span></span> <span data-ttu-id="2a6cc-109">Однако связанный отчет должен использовать свойства и макет источника данных базового отчета, содержащего определение данного отчета.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-109">However, a linked report must use the data source properties and layout of the base report that provides the report definition.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="2a6cc-110">Навигация</span><span class="sxs-lookup"><span data-stu-id="2a6cc-110">Navigation</span></span>  
 <span data-ttu-id="2a6cc-111">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующие процедуры.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-111">Use the following procedures to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-linked-report-page-from-the-contents-page"></a><span data-ttu-id="2a6cc-112">Открытие страницы «Создание связанного отчета» со страницы «Содержимое»</span><span class="sxs-lookup"><span data-stu-id="2a6cc-112">To open the New Linked Report page from the Contents page</span></span>  
  
1.  <span data-ttu-id="2a6cc-113">Откройте диспетчер отчетов и найдите отчет, для которого необходимо создать связанный отчет.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-113">Open Report Manager, and locate a report for which you want to create a linked report.</span></span>  
  
2.  <span data-ttu-id="2a6cc-114">Подведите курсор к отчету и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-114">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="2a6cc-115">В раскрывающемся меню выберите **Создать связанный отчет**.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-115">In the drop-down menu, click **Create Linked Report**.</span></span>  
  
###### <a name="to-open-the-new-linked-report-page-from-the-general-properties-page-of-a-report"></a><span data-ttu-id="2a6cc-116">Открытие страницы «Создание связанного отчета» со страницы свойств отчета «Общие»</span><span class="sxs-lookup"><span data-stu-id="2a6cc-116">To open the New Linked Report page from the General properties page of a report</span></span>  
  
1.  <span data-ttu-id="2a6cc-117">Откройте диспетчер отчетов и найдите отчет, для которого необходимо создать связанный отчет.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-117">Open Report Manager, and locate a report for which you want to create a linked report.</span></span>  
  
2.  <span data-ttu-id="2a6cc-118">Подведите курсор к отчету и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-118">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="2a6cc-119">В раскрывающемся меню выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-119">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="2a6cc-120">Откроется страница свойств отчета «Общие».</span><span class="sxs-lookup"><span data-stu-id="2a6cc-120">This opens the General properties page for the report.</span></span>  
  
4.  <span data-ttu-id="2a6cc-121">На панели инструментов элемента выберите **Создать связанный отчет**.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-121">In the item toolbar, click **Create Linked Report**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2a6cc-122">Параметры</span><span class="sxs-lookup"><span data-stu-id="2a6cc-122">Options</span></span>  
 <span data-ttu-id="2a6cc-123">**имя**;</span><span class="sxs-lookup"><span data-stu-id="2a6cc-123">**Name**</span></span>  
 <span data-ttu-id="2a6cc-124">Укажите имя связанного отчета.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-124">Specify the name of the linked report.</span></span> <span data-ttu-id="2a6cc-125">Имя должно содержать хотя бы одну букву или цифру.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-125">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="2a6cc-126">Оно также может включать пробелы и специальные знаки.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-126">It can also include spaces and certain symbols.</span></span> <span data-ttu-id="2a6cc-127">Однако нельзя использовать символы ; ?</span><span class="sxs-lookup"><span data-stu-id="2a6cc-127">However, you must not use the characters ; ?</span></span> <span data-ttu-id="2a6cc-128">: \@ & = +, $/\* \< > | "или/при указании имени.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-128">: \@ & = + , $ / \* \< > | " or / when specifying a name.</span></span>  
  
 <span data-ttu-id="2a6cc-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2a6cc-129">**Description**</span></span>  
 <span data-ttu-id="2a6cc-130">Введите описание содержимого отчета.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-130">Type a description of the report contents.</span></span> <span data-ttu-id="2a6cc-131">Описание появится на странице «Содержимое» для тех пользователей, которые имеют разрешения на доступ к отчету.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-131">This description appears in the Contents page to users who have permission to access the report.</span></span>  
  
 <span data-ttu-id="2a6cc-132">**Расположение**</span><span class="sxs-lookup"><span data-stu-id="2a6cc-132">**Location**</span></span>  
 <span data-ttu-id="2a6cc-133">Определите местоположение папки, которая содержит отчет.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-133">Specify the folder path that contains the report.</span></span> <span data-ttu-id="2a6cc-134">По умолчанию связанные отчеты имеют с основным отчетом общего родителя.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-134">By default, linked reports are created as siblings to the base report.</span></span> <span data-ttu-id="2a6cc-135">Нажмите кнопку **Изменение расположения** , чтобы поместить связанный отчет в иную папку.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-135">Click **Change Location** to put the linked report in a different folder.</span></span>  
  
 <span data-ttu-id="2a6cc-136">**OK**</span><span class="sxs-lookup"><span data-stu-id="2a6cc-136">**OK**</span></span>  
 <span data-ttu-id="2a6cc-137">Нажмите кнопку **ОК** , чтобы сохранить изменения и возвратиться к общей странице свойств основного отчета.</span><span class="sxs-lookup"><span data-stu-id="2a6cc-137">Click **OK** to save your changes and return to the General properties page of the base report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a6cc-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="2a6cc-138">See Also</span></span>  
 <span data-ttu-id="2a6cc-139">[Создание связанного отчета](reports/create-a-linked-report.md) </span><span class="sxs-lookup"><span data-stu-id="2a6cc-139">[Create a Linked Report](reports/create-a-linked-report.md) </span></span>  
 <span data-ttu-id="2a6cc-140">[Страница «Общие свойства», отчеты &#40;диспетчер отчетов&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="2a6cc-140">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 [<span data-ttu-id="2a6cc-141">Справка F1 диспетчера отчетов</span><span class="sxs-lookup"><span data-stu-id="2a6cc-141">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
