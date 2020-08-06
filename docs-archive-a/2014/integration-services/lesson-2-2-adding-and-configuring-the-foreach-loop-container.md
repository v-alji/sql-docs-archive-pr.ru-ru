---
title: Шаг 2. Добавление и настройка контейнера "цикл по каждому элементу" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 88a973cc-0f23-4ecf-adb6-5b06279c2df6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: de5e8875c43edda618ccef4839c88c3b84a003cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655831"
---
# <a name="step-2-adding-and-configuring-the-foreach-loop-container"></a><span data-ttu-id="3b9cb-102">Шаг 2. Добавление и настройка контейнера "цикл по каждому элементу"</span><span class="sxs-lookup"><span data-stu-id="3b9cb-102">Step 2: Adding and Configuring the Foreach Loop Container</span></span>
  <span data-ttu-id="3b9cb-103">В этой задаче будет добавлена возможность выполнить циклическую обработку папки неструктурированных файлов и применить для каждого из этих неструктурированных файлов одинаковое преобразование потока данных, использованное на занятии 1.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-103">In this task, you will add the ability to loop through a folder of flat files and apply the same data flow transformation used in Lesson 1 to each of those flat files.</span></span> <span data-ttu-id="3b9cb-104">Это будет выполнено путем добавления в поток управления и настройки контейнера «цикл по каждому элементу».</span><span class="sxs-lookup"><span data-stu-id="3b9cb-104">You do this by adding and configuring a Foreach Loop container to the control flow.</span></span>  
  
 <span data-ttu-id="3b9cb-105">Добавленный контейнер «цикл по каждому элементу» должен иметь возможность соединения с каждым неструктурированным файлом в данной папке.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-105">The Foreach Loop container that you add must be able to connect to each flat file in the folder.</span></span> <span data-ttu-id="3b9cb-106">Так как все файлы в папке имеют одинаковый формат, контейнер «цикл по каждому элементу» может использовать один и тот же диспетчер соединений с неструктурированными файлами для соединения с каждым из файлов.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-106">Because all the files in the folder have the same format, the Foreach Loop container can use the same Flat File connection manager to connect to each of these files.</span></span> <span data-ttu-id="3b9cb-107">Контейнер будет использовать диспетчер соединений с неструктурированными файлами, созданный на занятии 1.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-107">The Flat File connection manager that the container will use is the same Flat File connection manager that you created in Lesson 1.</span></span>  
  
 <span data-ttu-id="3b9cb-108">В настоящее время диспетчер соединений с неструктурированными файлами занятия 1 соединен только с одним неструктурированным файлом.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-108">Currently, the Flat File connection manager from Lesson 1 connects to only one, specific flat file.</span></span> <span data-ttu-id="3b9cb-109">Чтобы последовательно соединиться с каждым неструктурированным файлом в папке, необходимо настроить контейнер «цикл по каждому элементу» и диспетчер соединений с неструктурированными файлами, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-109">To iteratively connect to each flat file in the folder, you will have to configure both the Foreach Loop container and the Flat File connection manager as follows:</span></span>  
  
-   <span data-ttu-id="3b9cb-110">**Контейнер "цикл по каждому элементу".** Необходимо сопоставить перечисляемое значение контейнера с пользовательской переменной пакета.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-110">**Foreach Loop container:** You will map the enumerated value of the container to a user-defined package variable.</span></span> <span data-ttu-id="3b9cb-111">Контейнер будет использовать определенные пользователем переменные, чтобы динамически изменять свойства `ConnectionString` диспетчера соединений с неструктурированными файлами и последовательно соединяться с каждым файлом в папке.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-111">The container will then use this user-defined variable to dynamically modify the `ConnectionString` property of the Flat File connection manager and iteratively connect to each flat file in the folder.</span></span>  
  
-   <span data-ttu-id="3b9cb-112">**Диспетчер соединений с неструктурированными файлами:** Диспетчер соединений, созданный на занятии 1, будет изменен с помощью пользовательской переменной для заполнения свойства диспетчера соединений `ConnectionString` .</span><span class="sxs-lookup"><span data-stu-id="3b9cb-112">**Flat File connection manager:** You will modify the connection manager that was created in Lesson 1 by using a user-defined variable to populate the connection manager's `ConnectionString` property.</span></span>  
  
 <span data-ttu-id="3b9cb-113">Процедуры в этом задании показывают, как создавать и изменять контейнер «цикл по каждому элементу» для использования пользовательских переменных пакетов и как добавлять в цикл задачи потока данных.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-113">The procedures in this task show you how to create and modify the Foreach Loop container to use a user-defined package variable and to add the data flow task to the loop.</span></span> <span data-ttu-id="3b9cb-114">В следующей задаче будет рассмотрено, как изменить настройки диспетчера соединений с неструктурированными файлами таким образом, чтобы использовать в нем пользовательскую переменную.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-114">You will learn how to modify the Flat File connection manager to use a user-defined variable in the next task.</span></span>  
  
 <span data-ttu-id="3b9cb-115">После внесения этих изменений в пакет при его выполнении контейнер «цикл по каждому элементу» будет применен к коллекции файлов из папки образцов данных.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-115">After you have made these modifications to the package, when the package is run, the Foreach Loop Container will iterate through the collection of files in the Sample Data folder.</span></span> <span data-ttu-id="3b9cb-116">Каждый раз при нахождении отвечающего критериям поиска файла контейнер «цикл по каждому элементу» будет подставлять в пользовательскую переменную имя этого файла, сопоставлять эту переменную со свойством `ConnectionString` диспетчера соединений с неструктурированными файлами SampleCurrencyData, а затем выполнять поток данных по этому файлу.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-116">Each time a file is found that matches the criteria, the Foreach Loop Container will populate the user-defined variable with the file name, map the user-defined variable to the `ConnectionString` property of the Sample Currency Data Flat File connection manager, and then run the data flow against that file.</span></span> <span data-ttu-id="3b9cb-117">Таким образом, при каждом проходе цикла Foreach для выполнения задачи потока данных будет подставляться другой неструктурированный файл.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-117">Therefore, in each iteration of the Foreach Loop the Data Flow task will consume a different flat file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b9cb-118">Так как в службах [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] поток управления и поток данных разделены, любые циклы, добавленные в поток управления, не требуют изменения потока данных.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-118">Because [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] separates control flow from data flow, any looping that you add to the control flow will not require modification to the data flow.</span></span> <span data-ttu-id="3b9cb-119">Поэтому поток данных, созданный на занятии 1, не требуется изменять.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-119">Therefore, the data flow that you created in Lesson 1 does not have to be changed.</span></span>  
  
### <a name="to-add-a-foreach-loop-container"></a><span data-ttu-id="3b9cb-120">Добавление контейнера «цикл по каждому элементу»</span><span class="sxs-lookup"><span data-stu-id="3b9cb-120">To add a Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="3b9cb-121">В **SQL Server Data Tools**перейдите на вкладку **Поток управления** .</span><span class="sxs-lookup"><span data-stu-id="3b9cb-121">In **SQL Server Data Tools**, click the **Control Flow** tab.</span></span>  
  
2.  <span data-ttu-id="3b9cb-122">На **панели элементов служб SSIS**разверните элемент **Контейнеры**и перетащите **Контейнер "цикл по каждому элементу"** в рабочую область конструктора вкладки **Поток управления** .</span><span class="sxs-lookup"><span data-stu-id="3b9cb-122">In the **SSIS Toolbox**, expand **Containers**, and then drag a **Foreach Loop Container** onto the design surface of the **Control Flow** tab.</span></span>  
  
3.  <span data-ttu-id="3b9cb-123">Щелкните правой кнопкой мыши добавленный **Контейнер "цикл по каждому элементу"** и выберите команду **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-123">Right-click the newly added **Foreach Loop Container** and select **Edit**.</span></span>  
  
4.  <span data-ttu-id="3b9cb-124">В диалоговом окне **Редактор циклов по каждому** элементу на странице **Общие** в поле **имя**введите `Foreach File in Folder` .</span><span class="sxs-lookup"><span data-stu-id="3b9cb-124">In the **Foreach Loop Editor** dialog box, on the **General** page, for **Name**, enter `Foreach File in Folder`.</span></span> <span data-ttu-id="3b9cb-125">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-125">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="3b9cb-126">Щелкните правой кнопкой мыши контейнер «цикл по каждому элементу», выберите пункт **Свойства**, а затем в окно свойств убедитесь, что `LocaleID` для свойства задано значение **Английский (США)**.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-126">Right-click the Foreach Loop container, click **Properties**, and in the Properties window, verify that the `LocaleID` property is set to **English (United States)**.</span></span>  
  
### <a name="to-configure-the-enumerator-for-the-foreach-loop-container"></a><span data-ttu-id="3b9cb-127">Настройка перечислителя контейнера «цикл по каждому элементу»</span><span class="sxs-lookup"><span data-stu-id="3b9cb-127">To configure the enumerator for the Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="3b9cb-128">Дважды щелкните Цикл по каждому файлу в папке, чтобы снова открыть **Редактор циклов по каждому элементу**.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-128">Double-click Foreach File in Folder to reopen the **Foreach Loop Editor**.</span></span>  
  
2.  <span data-ttu-id="3b9cb-129">Щелкните **Коллекция**.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-129">Click **Collection**.</span></span>  
  
3.  <span data-ttu-id="3b9cb-130">На странице **Коллекция** выберите **Перечислитель с циклом по каждому файлу**.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-130">On the **Collection** page, select **Foreach File Enumerator**.</span></span>  
  
4.  <span data-ttu-id="3b9cb-131">В группе **Конфигурация перечислителя** нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-131">In the **Enumerator configuration** group, click **Browse**.</span></span>  
  
5.  <span data-ttu-id="3b9cb-132">В диалоговом окне **Выбор папки** выберите папку на компьютере, в которой находятся файлы Currency_\*.txt.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-132">In the **Browse for Folder** dialog box, locate the folder on your machine that contains the Currency_\*.txt files.</span></span>  
  
     <span data-ttu-id="3b9cb-133">Образцы данных включаются в состав пакетов занятий по службам [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3b9cb-133">This sample data is included with the [!INCLUDE[ssIS](../includes/ssis-md.md)] lesson packages.</span></span> <span data-ttu-id="3b9cb-134">Чтобы загрузить образцы данных и пакеты занятий выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-134">To download the sample data and the lesson packages, do the following.</span></span>  
  
    1.  <span data-ttu-id="3b9cb-135">Перейдите к [образцам продуктов служб Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027).</span><span class="sxs-lookup"><span data-stu-id="3b9cb-135">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="3b9cb-136">Перейдите на вкладку **Downloads (загрузки** ).</span><span class="sxs-lookup"><span data-stu-id="3b9cb-136">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="3b9cb-137">Щелкните ГИПЕРССЫЛКу " https://msftisprodsamples.codeplex.com/downloads/get/578097 " SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip файл.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-137">Click the  HYPERLINK "https://msftisprodsamples.codeplex.com/downloads/get/578097" SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
6.  <span data-ttu-id="3b9cb-138">В поле **Файлы** введите **Currency_\*.txt**.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-138">In the **Files** box, type **Currency_\*.txt**.</span></span>  
  
### <a name="to-map-the-enumerator-to-a-user-defined-variable"></a><span data-ttu-id="3b9cb-139">Сопоставление перечислителя с пользовательской переменной</span><span class="sxs-lookup"><span data-stu-id="3b9cb-139">To map the enumerator to a user-defined variable</span></span>  
  
1.  <span data-ttu-id="3b9cb-140">Щелкните **Сопоставления переменной**.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-140">Click **Variable Mappings**.</span></span>  
  
2.  <span data-ttu-id="3b9cb-141">На странице **сопоставления переменных** в столбце **переменная** щелкните пустую ячейку и выберите **\<New Variable...>** .</span><span class="sxs-lookup"><span data-stu-id="3b9cb-141">On the **Variable Mappings** page, in the **Variable** column, click the empty cell and select **\<New Variable...>**.</span></span>  
  
3.  <span data-ttu-id="3b9cb-142">В диалоговом окне **Добавление переменной** в поле **имя**введите `varFileName` .</span><span class="sxs-lookup"><span data-stu-id="3b9cb-142">In the **Add Variable** dialog box, for **Name**, type `varFileName`.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3b9cb-143">В именах переменных учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-143">Variable names are case sensitive.</span></span>  
  
4.  <span data-ttu-id="3b9cb-144">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3b9cb-144">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="3b9cb-145">Еще раз нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Редактор циклов по каждому элементу** .</span><span class="sxs-lookup"><span data-stu-id="3b9cb-145">Click **OK** again to exit the **Foreach Loop Editor** dialog box.</span></span>  
  
### <a name="to-add-the-data-flow-task-to-the-loop"></a><span data-ttu-id="3b9cb-146">Добавление задачи потока данных в цикл</span><span class="sxs-lookup"><span data-stu-id="3b9cb-146">To add the data flow task to the loop</span></span>  
  
-   <span data-ttu-id="3b9cb-147">Перетащите задачу потока данных « **Извлечение образца валюты** » в контейнер «цикл по каждому элементу», а затем переименуйте его `Foreach File in Folder` .</span><span class="sxs-lookup"><span data-stu-id="3b9cb-147">Drag the **Extract Sample Currency Data** data flow task onto the Foreach Loop container now renamed `Foreach File in Folder`.</span></span>  
  
## <a name="next-lesson-task"></a><span data-ttu-id="3b9cb-148">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="3b9cb-148">Next Lesson Task</span></span>  
 [<span data-ttu-id="3b9cb-149">Шаг 3. Изменение диспетчера соединений с неструктурированными файлами</span><span class="sxs-lookup"><span data-stu-id="3b9cb-149">Step 3: Modifying the Flat File Connection Manager</span></span>](lesson-2-3-modifying-the-flat-file-connection-manager.md)  
  
## <a name="see-also"></a><span data-ttu-id="3b9cb-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="3b9cb-150">See Also</span></span>  
 <span data-ttu-id="3b9cb-151">[Настройка контейнера «цикл по каждому элементу»](control-flow/foreach-loop-container.md) </span><span class="sxs-lookup"><span data-stu-id="3b9cb-151">[Configure a Foreach Loop Container](control-flow/foreach-loop-container.md) </span></span>  
 [<span data-ttu-id="3b9cb-152">Использование переменных в пакетах</span><span class="sxs-lookup"><span data-stu-id="3b9cb-152">Use Variables in Packages</span></span>](use-variables-in-packages.md)  
  
