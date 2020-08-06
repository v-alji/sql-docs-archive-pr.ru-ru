---
title: 'Задача 1 (Предварительная проверка): удаление данных поставщика в MDS | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6f0a4287-7fd4-4f18-b7e4-a5191a9d4a3c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e78dc5ff04f95d42cf440e3f80b1b349e0315a69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666917"
---
# <a name="task-1-prerequisite-removing-supplier-data-in-mds"></a><span data-ttu-id="46e41-102">Задача 1 (предварительное требование). Удаление данных о поставщиках в MDS</span><span class="sxs-lookup"><span data-stu-id="46e41-102">Task 1 (Prerequisite): Removing Supplier Data in MDS</span></span>
  <span data-ttu-id="46e41-103">В этой задаче будут удалены данные о поставщиках, хранящихся в MDS.</span><span class="sxs-lookup"><span data-stu-id="46e41-103">In this task, you remove the supplier data stored in MDS.</span></span> <span data-ttu-id="46e41-104">Вы перегрузили данные вручную с помощью **надстройки MDS для Excel** на предыдущем занятии.</span><span class="sxs-lookup"><span data-stu-id="46e41-104">You uploaded the data manually using **MDS Excel Add-in** in the previous lesson.</span></span> <span data-ttu-id="46e41-105">Пакет служб SSIS, который будет создан на этом занятии, будет автоматически загружать данные в MDS.</span><span class="sxs-lookup"><span data-stu-id="46e41-105">The SSIS package you create in this lesson will automatically upload the data to MDS for you.</span></span> <span data-ttu-id="46e41-106">Поэтому перед тестированием пакета служб SSIS необходимо удалить данные поставщиков из MDS, удалить производную иерархию, удалить сущности поставщиков и состояний, а также создать сущность поставщика без данных.</span><span class="sxs-lookup"><span data-stu-id="46e41-106">Therefore, before testing the SSIS package, you need to remove the supplier data from MDS, remove the derived hierarchy, remove supplier and state entities, and create the supplier entity with no data.</span></span>  
  
1.  <span data-ttu-id="46e41-107">Запустите **Диспетчер основных данных** , перейдя к `http://localhost/MDS` веб-сайту и приложению, которое вы указали при настройке MDS.</span><span class="sxs-lookup"><span data-stu-id="46e41-107">Launch **Master Data Manager** by navigating to `http://localhost/MDS` or the website and application you specified when configuring MDS.</span></span> <span data-ttu-id="46e41-108">Если вы сохранили **Диспетчер основных данных** открыть, щелкните **SQL Server 2012 Master Data Services** в верхней части, чтобы перейти на **домашнюю страницу**.</span><span class="sxs-lookup"><span data-stu-id="46e41-108">If you kept the **Master Data Manager** open, click **SQL Server 2012 Master Data Services** at the top to switch to the **home page**.</span></span>  
  
2.  <span data-ttu-id="46e41-109">В разделе **задачи администрирования** щелкните **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="46e41-109">Click **System Administration** in the **Administrative Tasks** section.</span></span>  
  
3.  <span data-ttu-id="46e41-110">Наведите указатель мыши на **Управление** в меню и выберите пункт **производные иерархии**.</span><span class="sxs-lookup"><span data-stu-id="46e41-110">Hover the mouse over **Manage** on the menu and click **Derived Hierarchies**.</span></span> <span data-ttu-id="46e41-111">Необходимо удалить производную иерархию **SuppliersInState** перед удалением сущностей в модели **поставщиков** .</span><span class="sxs-lookup"><span data-stu-id="46e41-111">You need to delete the derived hierarchy **SuppliersInState** before deleting the entities in the **Suppliers** model.</span></span>  
  
4.  <span data-ttu-id="46e41-112">Выберите **SuppliersInState** из списка **производная иерархия** и нажмите кнопку **X (удалить)** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="46e41-112">Select **SuppliersInState** from the **Derived Hierarchy** list and click **X (Delete)** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="46e41-113">Нажмите кнопку **ОК** , чтобы подтвердить удаление.</span><span class="sxs-lookup"><span data-stu-id="46e41-113">Click **OK** to confirm deletion.</span></span>  
  
6.  <span data-ttu-id="46e41-114">Наведите указатель мыши на **Управление** в меню и щелкните **сущности**.</span><span class="sxs-lookup"><span data-stu-id="46e41-114">Hover the mouse over **Manage** on the menu and click **Entities**.</span></span>  
  
7.  <span data-ttu-id="46e41-115">Щелкните **поставщик** и нажмите кнопку **Удалить (X)** на панели инструментов, чтобы удалить сущность.</span><span class="sxs-lookup"><span data-stu-id="46e41-115">Click **Supplier** and click **Delete (X)** button on toolbar to delete the entity.</span></span> <span data-ttu-id="46e41-116">Нажмите кнопку **ОК** в окне сообщений.</span><span class="sxs-lookup"><span data-stu-id="46e41-116">Click **OK** on message boxes.</span></span>  
  
8.  <span data-ttu-id="46e41-117">Повторите предыдущий шаг, чтобы удалить сущность **State** .</span><span class="sxs-lookup"><span data-stu-id="46e41-117">Repeat the previous step to delete **State** entity.</span></span>  
  
9. <span data-ttu-id="46e41-118">Не закрывайте **Диспетчер основных данных**.</span><span class="sxs-lookup"><span data-stu-id="46e41-118">Don't close **Master Data Manager**.</span></span>  
  
10. <span data-ttu-id="46e41-119">Перейдите в окно Excel, которое было **очищено и Сопоставлено Suppliers.xls** открытии файла.</span><span class="sxs-lookup"><span data-stu-id="46e41-119">Switch to the Excel window that has **Cleansed and Matched Suppliers.xls** file open.</span></span> <span data-ttu-id="46e41-120">Перейдите на вкладку **Sheet1** внизу.</span><span class="sxs-lookup"><span data-stu-id="46e41-120">Switch to the **Sheet1** tab at the bottom.</span></span>  
  
11. <span data-ttu-id="46e41-121">Выберите только **первую строку с заголовками**.</span><span class="sxs-lookup"><span data-stu-id="46e41-121">Select only the **first row with headers**.</span></span> <span data-ttu-id="46e41-122">Не выбирайте другие строки.</span><span class="sxs-lookup"><span data-stu-id="46e41-122">Don't select any other row.</span></span> <span data-ttu-id="46e41-123">Вы хотите создать сущности на основе столбцов Excel, но не хотите отправлять какие бы то ни было данные.</span><span class="sxs-lookup"><span data-stu-id="46e41-123">You want to create the entities based on the Excel columns but don't want to upload any data.</span></span> <span data-ttu-id="46e41-124">Именно поэтому следует выбрать только первую строку с заголовками.</span><span class="sxs-lookup"><span data-stu-id="46e41-124">Therefore you select only the first row with the headers.</span></span>  
  
12. <span data-ttu-id="46e41-125">В строке меню щелкните **основные данные** .</span><span class="sxs-lookup"><span data-stu-id="46e41-125">Click **Master Data** on the menu bar.</span></span>  
  
13. <span data-ttu-id="46e41-126">Щелкните **создать сущность** на ленте.</span><span class="sxs-lookup"><span data-stu-id="46e41-126">Click **Create Entity** from the ribbon.</span></span>  
  
14. <span data-ttu-id="46e41-127">Если в диалоговом окне **Управление соединениями** не отображается подключение к **локальному серверу MDS** в разделе **существующие подключения**, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="46e41-127">In **Manage Connections** dialog box, if you do not see the connection to **local MDS server** under **Existing connections**, do the following:</span></span>  
  
    1.  <span data-ttu-id="46e41-128">Выберите **создать новое соединение**и нажмите кнопку **создать** .</span><span class="sxs-lookup"><span data-stu-id="46e41-128">Select **Create a new connection**, and click **New** button.</span></span>  
  
    2.  <span data-ttu-id="46e41-129">В диалоговом окне Добавление нового соединения введите **локальный сервер MDS** в поле **Описание** и **адрес http: \/ /ЛОКАЛХОСТ/МДС** для **сервера MDS**, а затем нажмите кнопку **ОК** , чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="46e41-129">In the Add New Connection dialog box, type **Local MDS Server** for **Description** and **http:\//localhost/MDS** for **MDS server address**, and click **OK** to close the dialog box.</span></span>  
  
15. <span data-ttu-id="46e41-130">В диалоговом окне **Управление соединениями** выберите **локальный сервер MDS** ( `http://localhost/MDS` ), нажмите кнопку **проверить** , чтобы проверить подключение.</span><span class="sxs-lookup"><span data-stu-id="46e41-130">In **Manage Connections** dialog box, select **Local MDS Server** (`http://localhost/MDS`), click **Test** to test the connection.</span></span> <span data-ttu-id="46e41-131">Нажмите кнопку **ОК** в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="46e41-131">Click **OK** on the message box.</span></span>  
  
16. <span data-ttu-id="46e41-132">Нажмите кнопку **подключить** , чтобы установить соединение с сервером MDS.</span><span class="sxs-lookup"><span data-stu-id="46e41-132">Click **Connect** to make a connection to the MDS server.</span></span>  
  
17. <span data-ttu-id="46e41-133">В диалоговом окне **Создание сущности** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="46e41-133">In the **Create Entity** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="46e41-134">Убедитесь, что для параметра **диапазон** задано значение **$1: $1**.</span><span class="sxs-lookup"><span data-stu-id="46e41-134">Confirm that **Range** is set to **$1:$1**.</span></span>  
  
    2.  <span data-ttu-id="46e41-135">Выберите **поставщики** для **модели**.</span><span class="sxs-lookup"><span data-stu-id="46e41-135">Select **Suppliers** for **Model**.</span></span>  
  
    3.  <span data-ttu-id="46e41-136">Выберите **VERSION_1** для **версии**.</span><span class="sxs-lookup"><span data-stu-id="46e41-136">Select **VERSION_1** for **Version**.</span></span>  
  
    4.  <span data-ttu-id="46e41-137">Введите имя **поставщика** для **нового имени сущности**.</span><span class="sxs-lookup"><span data-stu-id="46e41-137">Type **Supplier** for **New entity name**.</span></span>  
  
    5.  <span data-ttu-id="46e41-138">Выберите **КодПоставщика** для **кода**.</span><span class="sxs-lookup"><span data-stu-id="46e41-138">Select **SupplierID** for **Code**.</span></span>  
  
    6.  <span data-ttu-id="46e41-139">Выберите **имя поставщика** в качестве **имени**.</span><span class="sxs-lookup"><span data-stu-id="46e41-139">Select **Supplier Name** for **Name**.</span></span>  
  
    7.  <span data-ttu-id="46e41-140">Нажмите кнопку **ОК** , чтобы создать сущность и закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="46e41-140">Click **OK** to create the entity and close the dialog box.</span></span>  
  
18. <span data-ttu-id="46e41-141">Закройте **Excel** и **не сохраняйте** файл.</span><span class="sxs-lookup"><span data-stu-id="46e41-141">Close **Excel** and **do not save** the file.</span></span>  
  
19. <span data-ttu-id="46e41-142">В **Диспетчер основных данных**обновите Интернет-браузер и убедитесь, что в списке отображается сущность **поставщика** .</span><span class="sxs-lookup"><span data-stu-id="46e41-142">In **Master Data Manager**, refresh the internet browser and confirm that **Supplier** entity is displayed in the list.</span></span>  
  
20. <span data-ttu-id="46e41-143">Перейдите на **домашнюю страницу** , щелкнув **SQL Server 2012 Master Data Services** в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="46e41-143">Switch to the **home page** by clicking **SQL Server 2012 Master Data Services** at the top.</span></span>  
  
21. <span data-ttu-id="46e41-144">Убедитесь, что для **model** выбрана модель **поставщики** , а для **версии**выбрано **VERSION_1** .</span><span class="sxs-lookup"><span data-stu-id="46e41-144">Confirm that **Suppliers** model is selected for **Model** and **VERSION_1** is selected for **Version**.</span></span>  
  
22. <span data-ttu-id="46e41-145">Нажмите кнопку **Браузер**.</span><span class="sxs-lookup"><span data-stu-id="46e41-145">Click **Explorer**.</span></span> <span data-ttu-id="46e41-146">Обратите внимание, что сущность **поставщика** со всеми атрибутами создается без **значений**.</span><span class="sxs-lookup"><span data-stu-id="46e41-146">Notice that the **Supplier** entity with all the attributes is created with **no values**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="46e41-147">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="46e41-147">Next Step</span></span>  
 [<span data-ttu-id="46e41-148">Задача 2 &#40;необязательно&#41;: создание представления подписки MDS с помощью диспетчер основных данных</span><span class="sxs-lookup"><span data-stu-id="46e41-148">Task 2 &#40;Optional&#41;: Creating a MDS Subscription View using Master Data Manager</span></span>](../../2014/tutorials/task-2-optional-creating-a-mds-subscription-view-using-master-data-manager.md)  
  
  
