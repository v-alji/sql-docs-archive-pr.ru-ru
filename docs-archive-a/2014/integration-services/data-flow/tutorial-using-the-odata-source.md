---
title: Учебник. Использование источника OData [SSIS] | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 2c64cf8b-5edb-48df-8ffe-697096258f71
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a13b04494ed00251774b490b1cc929769a869acb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667295"
---
# <a name="tutorial-using-the-odata-source-ssis"></a><span data-ttu-id="ae4eb-102">Учебник. Использование источника OData [SSIS]</span><span class="sxs-lookup"><span data-stu-id="ae4eb-102">Tutorial: Using the OData Source [SSIS]</span></span>
  <span data-ttu-id="ae4eb-103">Этот учебник содержит процедуру извлечения коллекции **Employees** из образца **Northwind** службы OData (http://services.odata.org/V3/Northwind/Northwind.svc/) ) и последующей ее загрузки в неструктурированный файл.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-103">This tutorial walks you through the process to extract the **Employees** collection from the sample **Northwind** OData service (http://services.odata.org/V3/Northwind/Northwind.svc/), and then load it into a flat file.</span></span>  
  
## <a name="1-create-an-integration-services-project"></a><span data-ttu-id="ae4eb-104">1. Создание проекта служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="ae4eb-104">1. Create an Integration Services Project</span></span>  
  
1.  <span data-ttu-id="ae4eb-105">Запустите **SQL Server Data Tools** или [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae4eb-105">Launch **SQL Server Data Tools** or [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
2.  <span data-ttu-id="ae4eb-106">В меню **Файл**выберите **Создать**, а затем **Проект**.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-106">Click **File**, point to **New**, and click **Project**.</span></span>  
  
3.  <span data-ttu-id="ae4eb-107">В диалоговом окне **Создание проекта** разверните пункты **Установлено**, **Шаблоны**, **Бизнес-аналитика**и выберите **Службы Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-107">In the **New Project** dialog box, expand **Installed**, expand **Templates**, expand **Business Intelligence**, and click **Integration Services**.</span></span>  
  
4.  <span data-ttu-id="ae4eb-108">Выберите **Проект служб Integration Services** в качестве типа проекта.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-108">Select **Integration Services Project** for the type of project.</span></span>  
  
5.  <span data-ttu-id="ae4eb-109">Введите **имя** и выберите **расположение** для проекта и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-109">Enter a **name** and select a **location** for the project, and click **OK**.</span></span>  
  
## <a name="2-add-and-configure-odata-source-to-the-ssis-package"></a><span data-ttu-id="ae4eb-110">2. Добавление и настройка источника OData для пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="ae4eb-110">2. Add and Configure OData Source to the SSIS Package</span></span>  
  
1.  <span data-ttu-id="ae4eb-111">Перетащите **задачу потока данных** из **панели элементов служб SSIS** в область конструктора потока управления для пакетов служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-111">Drag-drop a **Data Flow Task** from the **SSIS Toolbox** on to the control flow design surface of your SSIS package.</span></span>  
  
2.  <span data-ttu-id="ae4eb-112">Перейдите на вкладку **Поток данных** и дважды щелкните добавленный элемент **Задача потока данных** , чтобы запустить **Область конструктора потока данных**.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-112">Click the **Data Flow** tab, or double click on the newly added **Data Flow Task** to launch the **Data Flow design surface**.</span></span>  
  
3.  <span data-ttu-id="ae4eb-113">Перетащите **Источник OData** из группы **Общие** на **панель элементов служб SSIS**.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-113">Drag-drop **OData Source** from the **Common** group in the **SSIS Toolbox**.</span></span> <span data-ttu-id="ae4eb-114">Если **Источник OData** устанавливается в первый раз, то он отобразится в группе **Общие** на **панели элементов служб SSIS**.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-114">When the **OData Source** is first installed, it will appear under the **Common** group in the **SSIS Toolbox**.</span></span>  
  
4.  <span data-ttu-id="ae4eb-115">Дважды щелкните компонент **Источник OData** , чтобы открыть диалоговое окно **Редактор источника OData** .</span><span class="sxs-lookup"><span data-stu-id="ae4eb-115">Double click the **OData Source** component to launch the **OData Source Editor** dialog box.</span></span>  
  
5.  <span data-ttu-id="ae4eb-116">Щелкните **Создать…**, чтобы добавить новый диспетчера соединений OData.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-116">Click **New...** to add a new OData Connection Manager.</span></span>  
  
6.  <span data-ttu-id="ae4eb-117">Введите URL-адрес службы OData в поле **Расположение сервисного документа**.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-117">Enter the OData service URL for **Service document location**.</span></span> <span data-ttu-id="ae4eb-118">Это может быть URL-адрес сервисного документа либо определенный канал или сущность.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-118">This can be the URL to the service document, or to a specific feed or entity.</span></span> <span data-ttu-id="ae4eb-119">Для целей данного учебника введите [http://services.odata.org/V3/Northwind/Northwind.svc/](http://services.odata.org/V3/Northwind/Northwind.svc/) .</span><span class="sxs-lookup"><span data-stu-id="ae4eb-119">For the purpose of this tutorial, type [http://services.odata.org/V3/Northwind/Northwind.svc/](http://services.odata.org/V3/Northwind/Northwind.svc/).</span></span>  
  
7.  <span data-ttu-id="ae4eb-120">Убедитесь, что выбрано **Проверка подлинности Windows** для **проверки подлинности** для использования для доступа к службе OData.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-120">Confirm that **Windows Authentication** is selected for the **authentication** to use to access the OData Service.</span></span> <span data-ttu-id="ae4eb-121">**Проверка подлинности Windows** выбрана по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-121">**Windows Authentication** is selected by default.</span></span> <span data-ttu-id="ae4eb-122">Чтобы использовалась обычная проверка подлинности, выберите **Использовать указанные имя пользователя и пароль**.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-122">To use basic authentication, select **Use this user name and password**.</span></span>  
  
8.  <span data-ttu-id="ae4eb-123">Щелкните **Проверка соединения** и нажмите кнопку **ОК** , чтобы создать экземпляр диспетчера соединений с OData.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-123">Click **Test Connection** to the connection, and click **OK** to create an instance of OData Connection Manager.</span></span>  
  
9. <span data-ttu-id="ae4eb-124">В диалоговом окне **Редактор источника OData** убедитесь, что выбрано значение **Коллекция** для параметра **Использовать коллекцию на пути ресурса** .</span><span class="sxs-lookup"><span data-stu-id="ae4eb-124">In the **OData Source Editor** Dialog Box, confirm that **Collection** is selected for **Use collection on resource path** option.</span></span>  
  
10. <span data-ttu-id="ae4eb-125">В раскрывающемся списке **Коллекция** выберите **Employees**.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-125">From the **Collection** drop down list, select **Employees**.</span></span>  
  
11. <span data-ttu-id="ae4eb-126">Введите любые дополнительные параметры запроса OData или фильтры для **Параметры запроса**.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-126">Enter any additional OData query options or filters for **Query Options**.</span></span> <span data-ttu-id="ae4eb-127">Например:</span><span class="sxs-lookup"><span data-stu-id="ae4eb-127">Ex.</span></span> <span data-ttu-id="ae4eb-128">$orderby=CompanyName&$top=100.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-128">$orderby=CompanyName&$top=100.</span></span> <span data-ttu-id="ae4eb-129">Для целей данного учебного примера введите **$top=5**.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-129">For the purpose of this tutorial, enter **$top=5**.</span></span>  
  
12. <span data-ttu-id="ae4eb-130">Щелкните **Предварительный просмотр** , чтобы просмотреть данные.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-130">Click **Preview** to preview the data.</span></span>  
  
13. <span data-ttu-id="ae4eb-131">Щелкните **Столбцы** на левой панели навигации, чтобы перейти на страницу **Столбцы** .</span><span class="sxs-lookup"><span data-stu-id="ae4eb-131">Click **Columns** in the left navigation pane to switch to the **Columns** page.</span></span>  
  
14. <span data-ttu-id="ae4eb-132">Выберите **EmployeeID**, **FirstName**и **LastName** в **Доступные внешние столбцы** , установив соответствующие флажки.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-132">Select **EmployeeID**, **FirstName**, and **LastName** from **Available External Columns** by checking the check boxes.</span></span>  
  
15. <span data-ttu-id="ae4eb-133">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Редактор источника OData** .</span><span class="sxs-lookup"><span data-stu-id="ae4eb-133">Click **OK** to close the **OData Source Editor** dialog box.</span></span>  
  
## <a name="3-add-flat-file-destination-and-test-the-solution"></a><span data-ttu-id="ae4eb-134">3. Добавление назначения неструктурированных файлов и тестирование решения</span><span class="sxs-lookup"><span data-stu-id="ae4eb-134">3. Add Flat File Destination and Test the Solution</span></span>  
  
1.  <span data-ttu-id="ae4eb-135">Теперь перетащите **Назначение "Неструктурированный файл"** из **панели элементов служб SSIS** в область конструктора потока данных, расположенную ниже компонента **Источник OData** .</span><span class="sxs-lookup"><span data-stu-id="ae4eb-135">Now, drag-drop a **Flat File Destination** from **SSIS Toolbox** to the Data Flow design surface below the **OData Source** component.</span></span>  
  
2.  <span data-ttu-id="ae4eb-136">Подключите компонент **Источник OData** к компоненту **Назначение «Неструктурированный файл»** с помощью синей стрелки.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-136">Connect **OData Source** component with the **Flat File Destination** component using blue arrow.</span></span>  
  
3.  <span data-ttu-id="ae4eb-137">Дважды щелкните **Назначение "Неструктурированный файл"**.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-137">Double-click on **Flat File Destination**.</span></span> <span data-ttu-id="ae4eb-138">Отобразится диалоговое окно **Редактор назначения «Неструктурированный файл»** .</span><span class="sxs-lookup"><span data-stu-id="ae4eb-138">You should see the **Flat File Destination Editor** dialog box.</span></span>  
  
4.  <span data-ttu-id="ae4eb-139">В диалоговом окне **Редактор назначения «Неструктурированный файл»** щелкните **Создать** , чтобы создать новый диспетчер соединений с неструктурированными файлами.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-139">In the **Flat File Destination Editor** dialog box, click **New** to create a new flat file connection manager.</span></span>  
  
5.  <span data-ttu-id="ae4eb-140">В диалоговом окне **Формат неструктурированного файла** выберите **С разделителями**.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-140">In the **Flat File Format** dialog box, select **Delimited**.</span></span> <span data-ttu-id="ae4eb-141">Отобразится диалоговое окно **Редактор диспетчера соединений с неструктурированными файлами** .</span><span class="sxs-lookup"><span data-stu-id="ae4eb-141">You should see the **Flat File Connection Manager Editor** dialog box.</span></span>  
  
6.  <span data-ttu-id="ae4eb-142">В диалоговом окне **Редактор диспетчера соединений с неструктурированными файлами** в поле **Имя файла**введите путь **c:\Employees.txt**.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-142">In the **Flat File Connection Manager Editor** dialog box, for the **File name**, enter **c:\Employees.txt**.</span></span>  
  
7.  <span data-ttu-id="ae4eb-143">В левой области панели навигации щелкните **Столбцы**.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-143">In the left navigation pane, click **Columns**.</span></span> <span data-ttu-id="ae4eb-144">На этой странице для просмотра данных можно воспользоваться функцией предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-144">You can preview the data on this page.</span></span>  
  
8.  <span data-ttu-id="ae4eb-145">Нажмите кнопку «ОК», чтобы закрыть диалоговое окно редактора **Диспетчер соединений с неструктурированными файлами** .</span><span class="sxs-lookup"><span data-stu-id="ae4eb-145">Click OK to close the **Flat File Connection Manager** Editor dialog box.</span></span>  
  
9. <span data-ttu-id="ae4eb-146">В диалоговом окне **Редактор назначения «Неструктурированный файл»** щелкните **Сопоставления** на панели навигации слева.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-146">In the **Flat File Destination Editor** dialog box, click **Mappings** in the left navigation pane.</span></span> <span data-ttu-id="ae4eb-147">Просмотрите сопоставления.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-147">Review the mappings.</span></span>  
  
10. <span data-ttu-id="ae4eb-148">Нажмите кнопку «ОК», чтобы закрыть диалоговое окно **Редактор назначения «Неструктурированный файл»** .</span><span class="sxs-lookup"><span data-stu-id="ae4eb-148">Click OK to close the **Flat File Destination Editor** dialog box.</span></span>  
  
11. <span data-ttu-id="ae4eb-149">Скомпилируйте и выполните пакет служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-149">Compile and execute the SSIS package.</span></span> <span data-ttu-id="ae4eb-150">Убедитесь, что выходной файл создается с параметрами «Идентификатор», «Имя» и «Фамилия» для 5 сотрудников из канала OData.</span><span class="sxs-lookup"><span data-stu-id="ae4eb-150">Verify that the output file is created with ID, First Name, and Last Name for 5 employees from the OData feed.</span></span>  
  
  
