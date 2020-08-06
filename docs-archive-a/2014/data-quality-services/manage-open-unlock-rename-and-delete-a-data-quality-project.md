---
title: Управление (открытие, разблокировка, переименование и удаление) проекта качества данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dqproject.opendqproject.f1
helpviewer_keywords:
- data quality project,delete
- data quality project,rename
- data quality project,unlock
- data quality project,open
ms.assetid: de8a2b04-4673-4beb-b4cf-96a28cdf3a93
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 216c95937676954c509890b879abdee8f55b778c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667892"
---
# <a name="manage-open-unlock-rename-and-delete-a-data-quality-project"></a><span data-ttu-id="9b9aa-102">Управление проектом служб DQS (открытие, разблокировка, переименование и удаление)</span><span class="sxs-lookup"><span data-stu-id="9b9aa-102">Manage (Open, Unlock, Rename, and Delete) a Data Quality Project</span></span>
  <span data-ttu-id="9b9aa-103">В этом разделе описывается управление проектом служб DQS с помощью [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] : такие действия, как открытие, разблокирование, переименование и удаление проекта.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-103">This topic describes how to manage a data quality project by using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] such as open, unlock, rename, and delete a data quality project.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9b9aa-104">Перед началом</span><span class="sxs-lookup"><span data-stu-id="9b9aa-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="9b9aa-105">Ограничения</span><span class="sxs-lookup"><span data-stu-id="9b9aa-105">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9b9aa-106">Нельзя открыть заблокированный проект, созданный другим пользователем.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-106">You cannot open a locked project that is created by another user.</span></span>  
  
-   <span data-ttu-id="9b9aa-107">Невозможно разблокировать, переименовать или удалить проект служб DQS, созданный другим пользователем.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-107">You cannot unlock, rename, or delete a data quality project that is created by another user.</span></span>  
  
-   <span data-ttu-id="9b9aa-108">Нельзя удалить заблокированный проект служб DQS.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-108">You cannot delete a locked data quality project.</span></span> <span data-ttu-id="9b9aa-109">Чтобы проект можно было удалить, его необходимо сначала разблокировать.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-109">You must first unlock it to delete.</span></span>  
  
-   <span data-ttu-id="9b9aa-110">Вы можете разблокировать только тот проект служб DQS, который сами создали.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-110">You can only unlock a data quality project that is created by you.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="9b9aa-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9b9aa-111">Prerequisites</span></span>  
 <span data-ttu-id="9b9aa-112">Для управления должен быть в наличии хотя бы один проект служб DQS.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-112">You must have at least one data quality project to manage.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9b9aa-113">безопасность</span><span class="sxs-lookup"><span data-stu-id="9b9aa-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9b9aa-114">Permissions</span><span class="sxs-lookup"><span data-stu-id="9b9aa-114">Permissions</span></span>  
 <span data-ttu-id="9b9aa-115">Для управления проектом служб DQS необходимо иметь роль dqs_kb_editor или dqs_kb_operator в базе данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-115">You must have the dqs_kb_editor or dqs_kb_operator role on the DQS_MAIN database to manage a data quality project.</span></span>  
  
##  <a name="open-a-data-quality-project"></a><a name="Open"></a> <span data-ttu-id="9b9aa-116">Открытие проекта служб DQS</span><span class="sxs-lookup"><span data-stu-id="9b9aa-116">Open a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="9b9aa-117">[Запустите приложение Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="9b9aa-117">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="9b9aa-118">На [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] главном экране щелкните **Open Data Quality Project (открыть проект**служб DQS).</span><span class="sxs-lookup"><span data-stu-id="9b9aa-118">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="9b9aa-119">Появится экран **Открытие проекта** .</span><span class="sxs-lookup"><span data-stu-id="9b9aa-119">The **Open project** screen appears.</span></span>  
  
     <span data-ttu-id="9b9aa-120">Также вы можете напрямую открыть проект служб DQS, щелкнув его в области **Последние проекты служб DQS** .</span><span class="sxs-lookup"><span data-stu-id="9b9aa-120">Alternately, you can directly open a data quality project listed under **Recent data quality project** area by clicking it.</span></span>  
  
3.  <span data-ttu-id="9b9aa-121">На экране **Открытие проекта** щелчком выберите нужный проект служб DQS и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-121">In the **Open project** screen, click to select the data quality project that you want to open, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="9b9aa-122">Проект служб DQS откроется в том же состоянии, в каком он был закрыт в последний раз.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-122">The data quality project opens at the same state of the activity where it was last closed.</span></span> <span data-ttu-id="9b9aa-123">Проект служб DQS имеет следующие состояния:</span><span class="sxs-lookup"><span data-stu-id="9b9aa-123">A data quality project has the following states:</span></span>  
  
    -   <span data-ttu-id="9b9aa-124">Для действия **Очистка** проект качества данных может иметь следующие состояния: **Очистка-Map**, **Очистка — Очистка**, **Очистка — управление и просмотр результатов**, а также **Очистка и экспорт**.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-124">For the **Cleansing** activity, a data quality project can have the following states: **Cleansing - Map**, **Cleansing - Cleanse**, **Cleansing - Manage and View Results**, and **Cleansing - Export**.</span></span>  
  
    -   <span data-ttu-id="9b9aa-125">Для действия **сопоставления** проект качества данных может иметь следующие состояния: **Match-Map**, **Match-Match**, **Match-выживания**и **Match-Export**.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-125">For the **Matching** activity, a data quality project can have the following states: **Matching - Map**, **Matching - Matching**, **Matching - Survivorship**, and **Matching - Export**.</span></span>  
  
##  <a name="unlock-a-data-quality-project"></a><a name="Unlock"></a> <span data-ttu-id="9b9aa-126">Разблокирование проекта служб DQS</span><span class="sxs-lookup"><span data-stu-id="9b9aa-126">Unlock a Data Quality Project</span></span>  
 <span data-ttu-id="9b9aa-127">При создании проекта служб DQS он находится в заблокированном состоянии для предотвращения использования или изменения другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-127">When you create a data quality project, it is in a locked state to prevent usage or modification by other users.</span></span> <span data-ttu-id="9b9aa-128">Необходимо разблокировать проект служб DQS после завершения работы, если требуется, чтобы с этим проектом могли работать другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-128">You must unlock the data quality project after you have completed your work if you want other users to work on your data quality project.</span></span> <span data-ttu-id="9b9aa-129">Для заблокированных проектов отображается символ блокировки.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-129">A lock symbol is displayed for projects that are locked.</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="9b9aa-130">[Запустите приложение Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="9b9aa-130">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="9b9aa-131">На [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] главном экране щелкните **Open Data Quality Project (открыть проект**служб DQS).</span><span class="sxs-lookup"><span data-stu-id="9b9aa-131">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="9b9aa-132">Появится экран **Открытие проекта** .</span><span class="sxs-lookup"><span data-stu-id="9b9aa-132">The **Open project** screen appears.</span></span>  
  
3.  <span data-ttu-id="9b9aa-133">На экране **Открытие проекта** щелкните правой кнопкой мыши созданный вами заблокированный проект служб DQS, затем выберите **Разблокировать** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-133">In the **Open project** screen, right-click a locked data quality project that is created by you, and then click **Unlock** in the shortcut menu.</span></span> <span data-ttu-id="9b9aa-134">Рядом с именем проекта отобразится зеленый флажок, означающий, что проект разблокирован.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-134">A green check mark is displayed for the project indicating that it is unlocked.</span></span>  
  
##  <a name="rename-a-data-quality-project"></a><a name="Rename"></a> <span data-ttu-id="9b9aa-135">Переименование проекта служб DQS</span><span class="sxs-lookup"><span data-stu-id="9b9aa-135">Rename a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="9b9aa-136">[Запустите приложение Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="9b9aa-136">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="9b9aa-137">На [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] главном экране щелкните **Open Data Quality Project (открыть проект**служб DQS).</span><span class="sxs-lookup"><span data-stu-id="9b9aa-137">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="9b9aa-138">Появится экран **Открытие проекта** .</span><span class="sxs-lookup"><span data-stu-id="9b9aa-138">The **Open project** screen appears.</span></span>  
  
3.  <span data-ttu-id="9b9aa-139">На экране **Открытие проекта** щелкните правой кнопкой мыши созданный вами проект служб DQS, затем выберите **Переименовать** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-139">In the **Open project** screen, right-click a data quality project that is created by you, and then click **Rename** in the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="9b9aa-140">Имя проекта служб DQS станет доступным для редактирования в столбце **Имя** .</span><span class="sxs-lookup"><span data-stu-id="9b9aa-140">The data quality project name becomes editable in the **Name** column.</span></span> <span data-ttu-id="9b9aa-141">Введите новое имя и нажмите клавишу «Ввод».</span><span class="sxs-lookup"><span data-stu-id="9b9aa-141">Type a new name, and then press Enter.</span></span>  
  
##  <a name="delete-a-data-quality-project"></a><a name="Delete"></a> <span data-ttu-id="9b9aa-142">Удаление проекта служб DQS</span><span class="sxs-lookup"><span data-stu-id="9b9aa-142">Delete a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="9b9aa-143">[Запустите приложение Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="9b9aa-143">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="9b9aa-144">На [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] главном экране щелкните **Open Data Quality Project (открыть проект**служб DQS).</span><span class="sxs-lookup"><span data-stu-id="9b9aa-144">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open data quality project**.</span></span> <span data-ttu-id="9b9aa-145">Появится экран **Открытие проекта** .</span><span class="sxs-lookup"><span data-stu-id="9b9aa-145">The **Open project** screen appears.</span></span>  
  
3.  <span data-ttu-id="9b9aa-146">На экране **Открытие проекта** щелкните правой кнопкой мыши созданный вами разблокированный проект служб DQS, затем выберите **Удалить** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-146">In the **Open project** screen, right-click an unlocked data quality project that is created by you, and then click **Delete** in the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="9b9aa-147">Появится окно подтверждения.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-147">A confirmation message appears.</span></span> <span data-ttu-id="9b9aa-148">Нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="9b9aa-148">Click **Yes**.</span></span>  
  
  
