---
title: Задача 2. Передача данных поставщика в MDS с помощью надстройка MDS для Excel | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 598deb57-e0cc-4e0a-aeb1-94432c094c67
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 16c5fa9db81649b30c12fae4d2e57afa8bf094e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654664"
---
# <a name="task-2-uploading-supplier-data-to-mds-using-mds-add-in-for-excel"></a><span data-ttu-id="855d6-102">Задача 2. Отправка данных поставщика в MDS с помощью надстройки MDS для Excel</span><span class="sxs-lookup"><span data-stu-id="855d6-102">Task 2: Uploading Supplier Data to MDS using MDS Add-in for Excel</span></span>
  <span data-ttu-id="855d6-103">В этой задаче данные о очищенных данных и поставщиках публикуются в службах **MDS** с помощью **надстройка MDS для Excel**.</span><span class="sxs-lookup"><span data-stu-id="855d6-103">In this task, you publish the cleansed and supplier data to **MDS** using the **MDS Add-in for Excel**.</span></span> <span data-ttu-id="855d6-104">Вы создаете сущность с именем « **поставщик** » в модели « **поставщики** », созданной на предыдущем занятии.</span><span class="sxs-lookup"><span data-stu-id="855d6-104">You create an entity named **Supplier** in the **Suppliers** model you created in the previous lesson.</span></span> <span data-ttu-id="855d6-105">Сущность будет иметь атрибуты для каждого столбца в файле Excel.</span><span class="sxs-lookup"><span data-stu-id="855d6-105">The entity will have an attribute for each column in the Excel file.</span></span> <span data-ttu-id="855d6-106">Атрибуты кода и имени сущности «поставщик» соответствуют столбцам « **КодПоставщика** » и « **название поставщика** » в Excel.</span><span class="sxs-lookup"><span data-stu-id="855d6-106">The Code and Name attributes of the Supplier entity correspond to the **SupplierID** and **Supplier Name** columns in Excel.</span></span>  
  
1.  <span data-ttu-id="855d6-107">Откройте **очищенные и соответствующие Suppliers.xls** в **Excel**.</span><span class="sxs-lookup"><span data-stu-id="855d6-107">Open **Cleansed and Matched Suppliers.xls** in **Excel**.</span></span>  
  
2.  <span data-ttu-id="855d6-108">Нажмите клавиши **CTRL + A** , чтобы выбрать все данные.</span><span class="sxs-lookup"><span data-stu-id="855d6-108">Press **CTRL+A** to select entire data.</span></span> <span data-ttu-id="855d6-109">**Важно** выбрать все данные в электронной таблице.</span><span class="sxs-lookup"><span data-stu-id="855d6-109">It is **important** that you select the entire data in the spreadsheet.</span></span>  
  
3.  <span data-ttu-id="855d6-110">В строке меню щелкните **основные данные** .</span><span class="sxs-lookup"><span data-stu-id="855d6-110">Click **Master Data** on the menu bar.</span></span>  
  
4.  <span data-ttu-id="855d6-111">На ленте нажмите кнопку **создать сущность** .</span><span class="sxs-lookup"><span data-stu-id="855d6-111">Click **Create Entity** button on the ribbon.</span></span>  
  
     <span data-ttu-id="855d6-112">![Excel — вкладка основных данных — кнопка «Создать сущность»](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-01.jpg "Excel — вкладка основных данных — кнопка «Создать сущность»")</span><span class="sxs-lookup"><span data-stu-id="855d6-112">![Excel - Master Data Tab - Create Entity Button](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-01.jpg "Excel - Master Data Tab - Create Entity Button")</span></span>  
  
5.  <span data-ttu-id="855d6-113">Если в диалоговом окне **Управление соединениями** не отображается подключение к **локальному серверу MDS** в разделе **существующие подключения**, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="855d6-113">In **Manage Connections** dialog box, if you do not see the connection to **local MDS server** under **Existing connections**, do the following:</span></span>  
  
    1.  <span data-ttu-id="855d6-114">Выберите **создать новое соединение**и нажмите кнопку **создать** .</span><span class="sxs-lookup"><span data-stu-id="855d6-114">Select **Create a new connection**, and click **New** button.</span></span>  
  
    2.  <span data-ttu-id="855d6-115">В диалоговом окне **Добавление нового соединения** введите **локальный сервер MDS** в поле **Описание** и адрес **http: \/ /ЛОКАЛХОСТ/МДС** для **сервера MDS**, а затем нажмите кнопку **ОК** , чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="855d6-115">In the **Add New Connection** dialog box, type **Local MDS Server** for **Description** and **http:\//localhost/MDS** for **MDS server address**, and click **OK** to close the dialog box.</span></span>  
  
6.  <span data-ttu-id="855d6-116">В диалоговом окне **Управление соединениями** выберите **локальный сервер MDS** ( `http://localhost/MDS` ), нажмите кнопку **проверить** , чтобы проверить подключение.</span><span class="sxs-lookup"><span data-stu-id="855d6-116">In **Manage Connections** dialog box, select **Local MDS Server** (`http://localhost/MDS`), click **Test** to test the connection.</span></span> <span data-ttu-id="855d6-117">Нажмите кнопку **ОК** в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="855d6-117">Click **OK** on the message box.</span></span>  
  
7.  <span data-ttu-id="855d6-118">Нажмите кнопку **Подключиться** , чтобы подключиться к серверу MDS.</span><span class="sxs-lookup"><span data-stu-id="855d6-118">Click **Connect** to connect to the MDS server.</span></span>  
  
8.  <span data-ttu-id="855d6-119">В диалоговом окне **Создание сущности** выберите **поставщики** для **модели**.</span><span class="sxs-lookup"><span data-stu-id="855d6-119">In the **Create Entity** dialog box, select **Suppliers** for the **Model**.</span></span>  
  
9. <span data-ttu-id="855d6-120">Убедитесь, что для **версии**выбрано **VERSION_1** .</span><span class="sxs-lookup"><span data-stu-id="855d6-120">Ensure that **VERSION_1** is selected for **Version**.</span></span>  
  
10. <span data-ttu-id="855d6-121">Введите имя **поставщика** для **нового имени сущности**.</span><span class="sxs-lookup"><span data-stu-id="855d6-121">Enter **Supplier** for **New entity name**.</span></span>  
  
11. <span data-ttu-id="855d6-122">Выберите **КодПоставщика** для **столбца, содержащего поле уникального идентификатора** (также можно создать код автоматически).</span><span class="sxs-lookup"><span data-stu-id="855d6-122">Select **SupplierID** for **the column that contains a unique identifier** field (you can also generate a code automatically).</span></span> <span data-ttu-id="855d6-123">По сути, столбец « **КодПоставщика** » в **Excel** сопоставляется с атрибутом **Code** сущности « **поставщик** ».</span><span class="sxs-lookup"><span data-stu-id="855d6-123">You are essentially mapping the **SupplierID** column in **Excel** to the **Code** attribute of **Supplier** entity.</span></span>  
  
12. <span data-ttu-id="855d6-124">Выберите **имя поставщика** для **столбца, содержащего поле Names (имена** ).</span><span class="sxs-lookup"><span data-stu-id="855d6-124">Select **Supplier Name** for **the column that contains names** field.</span></span> <span data-ttu-id="855d6-125">По сути, столбец « **имя поставщика** » в **Excel** сопоставляется с атрибутом **Name** сущности « **поставщик** ».</span><span class="sxs-lookup"><span data-stu-id="855d6-125">You are essentially mapping the **Supplier Name** column in **Excel** to the **Name** attribute of the **Supplier** entity.</span></span> <span data-ttu-id="855d6-126">Атрибуты **Code** и **Name** являются обязательными атрибутами сущности в MDS.</span><span class="sxs-lookup"><span data-stu-id="855d6-126">The **Code** and **Name** attributes are mandatory attributes for an entity in MDS.</span></span>  
  
     <span data-ttu-id="855d6-127">![Диалоговое окно «Создать сущность»](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-02.jpg "Диалоговое окно «Создать сущность»")</span><span class="sxs-lookup"><span data-stu-id="855d6-127">![Create Entity Dialog Box](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-02.jpg "Create Entity Dialog Box")</span></span>  
  
13. <span data-ttu-id="855d6-128">Нажмите кнопку **ОК** , чтобы создать сущность в MDS, опубликовать основные данные в сущности, а затем закрыть диалоговое окно **Создание сущности** .</span><span class="sxs-lookup"><span data-stu-id="855d6-128">Click **OK** to create the entity on MDS, publish the master data to the entity, and close **Create Entity** dialog box.</span></span>  
  
14. <span data-ttu-id="855d6-129">Теперь вы увидите новый лист под названием « **поставщик**», который является именем сущности, добавленным в электронную таблицу Excel и в верхней части листа вы увидите, что лист подключен к серверу MDS.</span><span class="sxs-lookup"><span data-stu-id="855d6-129">Now, you should see a new sheet titled **Supplier**, which is the name of the entity, added to your Excel spreadsheet and at the top of the worksheet you should see that the worksheet is connected to the MDS server.</span></span> <span data-ttu-id="855d6-130">Обратите внимание, что исходный лист (с именем **Sheet1**) по-прежнему существует.</span><span class="sxs-lookup"><span data-stu-id="855d6-130">Notice that the original worksheet (titled **Sheet1**) still exists.</span></span>  
  
     <span data-ttu-id="855d6-131">![Excel — вкладки Supplier и Sheet1](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-03.jpg "Excel — вкладки Supplier и Sheet1")</span><span class="sxs-lookup"><span data-stu-id="855d6-131">![Excel - Supplier and Sheet1 Tabs](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-03.jpg "Excel - Supplier and Sheet1 Tabs")</span></span>  
  
     <span data-ttu-id="855d6-132">![Excel — показ подробных сведений о соединении с MDS](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-04.jpg "Excel — показ подробных сведений о соединении с MDS")</span><span class="sxs-lookup"><span data-stu-id="855d6-132">![Excel - Showing MDS Connection Details](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-04.jpg "Excel - Showing MDS Connection Details")</span></span>  
  
15. <span data-ttu-id="855d6-133">Не закрывайте **Excel** .</span><span class="sxs-lookup"><span data-stu-id="855d6-133">Keep **Excel** open.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="855d6-134">Следующая задача</span><span class="sxs-lookup"><span data-stu-id="855d6-134">Next Task</span></span>  
 [<span data-ttu-id="855d6-135">Задача 3. Проверка данных в диспетчере основных данных</span><span class="sxs-lookup"><span data-stu-id="855d6-135">Task 3: Verifying the Data in Master Data Manager</span></span>](../../2014/tutorials/task-3-verifying-the-data-in-master-data-manager.md)  
  
  
