---
title: Шаг 4. Развертывание пакета, созданного на занятии 6 | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b613cef7-7993-4d89-a429-a8251d74d435
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8c5109dc96af138bbd0c8c0087e8b73cf3bac435
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669003"
---
# <a name="step-4-deploying-the-lesson-6-package"></a><span data-ttu-id="8bbdc-102">Шаг 4. Развертывание пакета, созданного на занятии 6</span><span class="sxs-lookup"><span data-stu-id="8bbdc-102">Step 4: Deploying the Lesson 6 Package</span></span>
  <span data-ttu-id="8bbdc-103">Развертывание пакета предполагает добавление пакета в каталоге SSISDB в службах Integration Services на экземпляре SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-103">Deploying the package involves adding the package to the SSISDB catalog in Integration Services on an instance of SQL Server.</span></span> <span data-ttu-id="8bbdc-104">На этом занятии вы добавите пакет Lesson 6 в каталог SSISDB, зададите параметр и выполните пакет.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-104">In this lesson you will add the Lesson 6 package to the SSISDB catalog, set the parameter, and execute the package.</span></span> <span data-ttu-id="8bbdc-105">На этом занятии будет использоваться SQL Server Management Studio для добавления пакета Lesson 6 в каталог SSISDB и развертывания пакета.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-105">For this lesson you will use SQL Server Management Studio to add the Lesson 6 package to the SSISDB catalog, and deploy the package.</span></span> <span data-ttu-id="8bbdc-106">После развертывания пакета будет изменен параметр для указания нового расположения, а затем выполнен пакет.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-106">After deploying the package you will modify the parameter to point to a new location then execute the package.</span></span>  
  
 <span data-ttu-id="8bbdc-107">На этом занятии вы научитесь:</span><span class="sxs-lookup"><span data-stu-id="8bbdc-107">In this lesson you will:</span></span>  
  
-   <span data-ttu-id="8bbdc-108">Добавлять пакет в каталог SSISDB в узле служб SSIS в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-108">Add the package to the SSISDB catalog in the SSIS node in SQL Server.</span></span>  
  
-   <span data-ttu-id="8bbdc-109">Развертывать пакет.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-109">Deploy the package.</span></span>  
  
-   <span data-ttu-id="8bbdc-110">Задавать значение параметра пакета.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-110">Set the package parameter value.</span></span>  
  
-   <span data-ttu-id="8bbdc-111">Выполнять пакет в среде SSMS.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-111">Execute the package in SSMS.</span></span>  
  
### <a name="to-locate-or-add-the-ssisdb-catalog"></a><span data-ttu-id="8bbdc-112">Поиск или добавление каталога SSISDB</span><span class="sxs-lookup"><span data-stu-id="8bbdc-112">To Locate or add the SSISDB catalog</span></span>  
  
1.  <span data-ttu-id="8bbdc-113">Нажмите кнопку Пуск, выберите Все программы, выберите Microsoft SQL Server 2012 и затем щелкните SQL Management Studio.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-113">Click Start, point to All Programs, point to Microsoft SQL Server 2012, and then click SQL Management Studio.</span></span>  
  
2.  <span data-ttu-id="8bbdc-114">В диалоговом окне "Подключение к серверу" проверьте заданные по умолчанию параметры, а затем нажмите кнопку "Подключить".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-114">On the Connect to Server dialog box, verify the default settings, and then click Connect.</span></span> <span data-ttu-id="8bbdc-115">Для подключения необходимо, чтобы поле Имя сервера содержало имя компьютера, на котором установлен SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-115">To connect, the Server name box must contain the name of the computer where SQL Server is installed.</span></span> <span data-ttu-id="8bbdc-116">Если компонент базы данных является именованным экземпляром, то поле "Имя сервера" должно также содержать имя экземпляра в формате <имя_компьютера>\\<имя_экземпляра>.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-116">If the Database Engine is a named instance, the Server name box should also contain the instance name in the format <computer_name>\\<instance_name>.</span></span>  
  
3.  <span data-ttu-id="8bbdc-117">В обозревателе объектов разверните каталоги служб Integration Services.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-117">In Object Explorer expand Integration Services Catalogs.</span></span>  
  
4.  <span data-ttu-id="8bbdc-118">Если нет каталогов, перечисленных в разделе каталоги служб Integration Services, добавьте каталог SSISDB.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-118">If there are no catalogs listed under Integration Services Catalogs then add the SSISDB catalog.</span></span>  
  
5.  <span data-ttu-id="8bbdc-119">Чтобы добавить каталог SSISDB, щелкните правой кнопкой мыши каталоги служб Integration Services и затем щелкните "Создать каталог".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-119">To Add the SSISDB catalog, right-click Integration Services Catalogs and click Create Catalog.</span></span>  
  
6.  <span data-ttu-id="8bbdc-120">В диалоговом окне "Создание каталога" выберите "Включить интеграцию со средой CLR".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-120">On the Create Catalog dialog box select Enable CLR Integration.</span></span>  
  
7.  <span data-ttu-id="8bbdc-121">В поле "Пароль" введите новый пароль, затем введите его еще раз в поле "Повторный ввод пароля".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-121">In the Password box, type a new password then type it again in the Retype Password box.</span></span> <span data-ttu-id="8bbdc-122">Обязательно запомните введенный пароль.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-122">Be sure to remember the password you type.</span></span>  
  
8.  <span data-ttu-id="8bbdc-123">Нажмите кнопку ОК, чтобы добавить каталог SSISDB.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-123">Click OK to add the SSISDB catalog.</span></span>  
  
### <a name="to-add-the-package-to-the-ssisdb-catalog"></a><span data-ttu-id="8bbdc-124">Добавление пакета в каталог SSISDB</span><span class="sxs-lookup"><span data-stu-id="8bbdc-124">To add the package to the SSISDB catalog</span></span>  
  
1.  <span data-ttu-id="8bbdc-125">В обозревателе объектов щелкните правой кнопкой мыши SSISDB и нажмите кнопку "Создать папку".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-125">In Object Explorer, right-click SSISDB and click Create Folder.</span></span>  
  
2.  <span data-ttu-id="8bbdc-126">В диалоговом окне "Создание папки" введите учебник по службам SSIS в поле имени папки и нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-126">In the Create Folder dialog box type SSIS Tutorial in the Folder name box and click OK.</span></span>  
  
3.  <span data-ttu-id="8bbdc-127">Разверните папку "Учебник по службам SSIS", щелкните правой кнопкой мыши Проекты и нажмите кнопку "Импорт пакетов".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-127">Expand the SSIS Tutorial folder, right-click Projects, and click Import Packages.</span></span>  
  
4.  <span data-ttu-id="8bbdc-128">На странице "Общие сведения мастера преобразования проекта служб Integration Services" нажмите кнопку "Далее".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-128">On the Integration Services Project Conversion Wizard Introduction page click Next.</span></span>  
  
5.  <span data-ttu-id="8bbdc-129">На странице "Поиск пакетов"» убедитесь, что файловая система выбрана в списке источников, а затем нажмите кнопку обзора.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-129">On the Locate Packages page, ensure that File system is selected in the Source list, then click Browse.</span></span>  
  
6.  <span data-ttu-id="8bbdc-130">В диалоговом окне "Обзор папок" перейдите в папку, содержащую проект учебника по службам SSIS, а затем нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-130">On the Browse For Folder dialog box, browse to the folder containing the SSIS Tutorial project, then click OK.</span></span>  
  
7.  <span data-ttu-id="8bbdc-131">Нажмите кнопку "Далее".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-131">Click Next.</span></span>  
  
8.  <span data-ttu-id="8bbdc-132">На странице "Выбор пакетов" вы должны увидите все шесть пакетов из учебника по службам SSIS.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-132">On the Select Packages page you should see all six packages from the SSIS Tutorial.</span></span> <span data-ttu-id="8bbdc-133">В списке пакетов выберите Lesson 6.dtsx, а затем нажмите кнопку "Далее".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-133">In the Packages list, select Lesson 6.dtsx, then click Next.</span></span>  
  
9. <span data-ttu-id="8bbdc-134">На странице "Выбор назначения" введите учебник по развертыванию служб SSIS в поле имя проекта, затем нажмите кнопку "Далее".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-134">On the Select Destination page, type SSIS Tutorial Deployment in the Project Name box then click Next.</span></span>  
  
10. <span data-ttu-id="8bbdc-135">Нажмите кнопки "Далее" на каждой из оставшихся страниц мастера, пока не откроется страница "Просмотр".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-135">Click Next on each of the remaining wizard pages until you get to the Review page.</span></span>  
  
11. <span data-ttu-id="8bbdc-136">На странице "Просмотр"» нажмите кнопку "Преобразовать".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-136">On the Review page, click Convert.</span></span>  
  
12. <span data-ttu-id="8bbdc-137">После завершения преобразования нажмите кнопку "Закрыть".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-137">When the conversion completes, click Close.</span></span>  
  
 <span data-ttu-id="8bbdc-138">После закрытия мастера преобразования проекта служб Integration Services служба SSIS отображает мастер развертывания служб Integration Services.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-138">When you close the Integration Services Project Conversion Wizard, SSIS displays the Integration Services Deployment Wizard.</span></span> <span data-ttu-id="8bbdc-139">Этот мастер используется для развертывания пакета Lesson 6.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-139">You will use this wizard now to deploy the Lesson 6 package.</span></span>  
  
1.  <span data-ttu-id="8bbdc-140">На странице "Общие сведения мастера развертывания служб Integration Services" просмотрите действия для развертывания проекта, а затем нажмите кнопку "Далее".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-140">On the Integration Services Deployment Wizard Introduction page, review the steps for deploying the project, then click Next.</span></span>  
  
2.  <span data-ttu-id="8bbdc-141">На странице "Выбор назначения"» убедитесь, что сервер имеет имя экземпляра SQL Server, содержащего каталог SSISDB, и, что путь показывает развертывание учебника служб SSIS, а затем нажмите кнопку "Далее".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-141">On the Select Destination page verify that the server name is the instance of SQL Server containing the SSISDB catalog and that the path shows SSIS Tutorial Deployment, then click Next.</span></span>  
  
3.  <span data-ttu-id="8bbdc-142">На странице "Просмотр" просмотрите сводку, а затем нажмите кнопку "Развернуть".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-142">On the Review page, review the Summary then click Deploy.</span></span>  
  
4.  <span data-ttu-id="8bbdc-143">После завершения развертывания нажмите кнопку "Закрыть".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-143">When the deployment completes, click Close.</span></span>  
  
5.  <span data-ttu-id="8bbdc-144">В обозревателе объектов щелкните правой кнопкой мыши каталоги служб Integration Services и щелкните "Обновить".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-144">In Object Explorer, right-click Integration Services Catalogs and click Refresh.</span></span>  
  
6.  <span data-ttu-id="8bbdc-145">Разверните каталоги служб Integration Services, а затем разверните SSISDB.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-145">Expand Integration Services Catalogs then expand SSISDB.</span></span> <span data-ttu-id="8bbdc-146">Продолжите разворачивать дерево под учебником по службам SSIS до тех пор, пока проект не будет развернут полностью.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-146">Continue to Expand the tree under SSIS Tutorial until you have completely expanded the project.</span></span> <span data-ttu-id="8bbdc-147">Вы должны увидеть файл Lesson 6.dtsx в узле Packages узла развертывания учебника по службам SSIS.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-147">You should see Lesson 6.dtsx under the Packages node of the SSIS Tutorial Deployment node.</span></span>  
  
 <span data-ttu-id="8bbdc-148">Чтобы убедиться в полноте пакета, щелкните правой кнопкой мыши файл Lesson 6.dtsx, а затем щелкните "Настройка".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-148">To verify that the package is complete, right-click Lesson 6.dtsx and click Configure.</span></span> <span data-ttu-id="8bbdc-149">В диалоговом окне "Настройка" выберите "Параметры" и убедитесь, что имеется запись с файлом Lesson 6.dtsx в качестве контейнера, VarFolderName в качестве имени и пути к данным нового образца как значения, а затем нажмите кнопку "Закрыть".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-149">On the Configure dialog box, select Parameters and verify that there is an entry with Lesson 6.dtsx as the Container, VarFolderName as the Name and the path to New Sample Data as the value, then click Close.</span></span>  
  
 <span data-ttu-id="8bbdc-150">Перед продолжением создайте папку данных нового образца, присвойте ей имя Sample Data Two и скопируйте в нее любые три образца исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-150">Before continuing create a new sample data folder, name it Sample Data Two, and copy any three of the original sample files into it.</span></span>  
  
### <a name="to-create-and-populate-a-new-sample-data-folder"></a><span data-ttu-id="8bbdc-151">Создание и заполнение новой папки с образцами данных</span><span class="sxs-lookup"><span data-stu-id="8bbdc-151">To create and populate a new sample data folder</span></span>  
  
1.  <span data-ttu-id="8bbdc-152">В проводнике в корневом каталоге диска (например, C:\\) создайте папку с именем Sample Data Two.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-152">In Windows Explorer, at the root level of your drive (for example, C:\\), create a new folder named Sample Data Two.</span></span>  
  
2.  <span data-ttu-id="8bbdc-153">Откройте папку c:\Program Files\Microsoft SQL Server\110\Samples\Integration Services\Tutorial\Creating a Simple ETL Package\Sample Data и скопируйте любые три образца файлов из папки.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-153">Open the c:\Program Files\Microsoft SQL Server\110\Samples\Integration Services\Tutorial\Creating a Simple ETL Package\Sample Data folder and then copy any three of the sample files from the folder.</span></span>  
  
3.  <span data-ttu-id="8bbdc-154">Вставьте скопированные файлы в папку New Sample Data.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-154">In the New Sample Data folder, paste the copied files.</span></span>  
  
### <a name="to-change-the-package-parameter-to-point-to-the-new-sample-data"></a><span data-ttu-id="8bbdc-155">Изменение параметра пакета для указания на данные нового образца</span><span class="sxs-lookup"><span data-stu-id="8bbdc-155">To change the package parameter to point to the new sample data</span></span>  
  
1.  <span data-ttu-id="8bbdc-156">В обозревателе объектов щелкните правой кнопкой мыши файл Lesson 6.dtsx и нажмите кнопку "Настроить".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-156">In Object Explorer, right click Lesson 6.dtsx and click Configure.</span></span>  
  
2.  <span data-ttu-id="8bbdc-157">В диалоговом окне "Настройка"» измените значение параметра на путь к паке Sample Data Two.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-157">On the Configure dialog box, change the parameter value to the path to Sample Data Two.</span></span> <span data-ttu-id="8bbdc-158">Например, C:\Sample Data Two, если новая папка размещена в корневой папке на диске C.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-158">For example C:\Sample Data Two if you placed the new folder in the root folder on the C drive.</span></span>  
  
3.  <span data-ttu-id="8bbdc-159">Нажмите кнопку "OК", чтобы закрыть диалоговое окно "Настройка".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-159">Click OK to close the Configure dialog box.</span></span>  
  
### <a name="to-test-the-lesson-6-package-deployment"></a><span data-ttu-id="8bbdc-160">Тестирование развертывания пакета Lesson 6</span><span class="sxs-lookup"><span data-stu-id="8bbdc-160">To test the Lesson 6 package deployment</span></span>  
  
1.  <span data-ttu-id="8bbdc-161">В обозревателе объектов щелкните правой кнопкой мыши файл Lesson 6.dtsx и нажмите кнопку "Выполнить".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-161">In Object Explorer, right click Lesson 6.dtsx and click Execute.</span></span>  
  
2.  <span data-ttu-id="8bbdc-162">В диалоговом окне "Выполнение пакета" нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="8bbdc-162">On the Execute Package dialog box, click OK.</span></span>  
  
3.  <span data-ttu-id="8bbdc-163">В диалоговом окне сообщения нажмите кнопку "Да", чтобы открыть отчет Обзор.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-163">On the message dialog box click Yes to open Overview Report.</span></span>  
  
 <span data-ttu-id="8bbdc-164">Обзорный отчет для пакета отображается с указанием имени пакета и сводки состояния.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-164">The Overview report for the package is displayed showing the name of the package and a status summary.</span></span> <span data-ttu-id="8bbdc-165">В разделе "Обзор выполнения" показан результат каждой задачи в пакете, а в разделе "Использованные параметры" показаны имена и значения всех параметров, использованных в выполнении пакета, в том числе VarFolderName.</span><span class="sxs-lookup"><span data-stu-id="8bbdc-165">The Execution Overview section shows the result from each task in the package and the Parameters Used section shows the names and values of all parameters used in the package execution, including VarFolderName.</span></span>  
  
  
