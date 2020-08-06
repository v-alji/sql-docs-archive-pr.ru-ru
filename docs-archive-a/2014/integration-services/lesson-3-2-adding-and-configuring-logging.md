---
title: Шаг 2. Добавление и настройка ведения журнала | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 56105f3f-e500-4669-8c8e-acf434527727
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0f2cdce6f34a19e22830d357d20f5d99cff8c14f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731882"
---
# <a name="step-2-adding-and-configuring-logging"></a><span data-ttu-id="26c5e-102">Шаг 2. Добавление и настройка ведения журнала</span><span class="sxs-lookup"><span data-stu-id="26c5e-102">Step 2: Adding and Configuring Logging</span></span>
  <span data-ttu-id="26c5e-103">В этой задаче будет включена запись в журнал потоков данных для пакета «Урок 3.dtsx».</span><span class="sxs-lookup"><span data-stu-id="26c5e-103">In this task, you will enable logging for the data flow in the Lesson 3.dtsx package.</span></span> <span data-ttu-id="26c5e-104">Затем предстоит настроить регистратор для текстовых файлов, чтобы записать в журнал события PipelineExecutionPlan и PipelineExecuteTrees.</span><span class="sxs-lookup"><span data-stu-id="26c5e-104">Then, you will configure a Text File log provider to log the PipelineExecutionPlan and PipelineExecuteTrees events.</span></span> <span data-ttu-id="26c5e-105">Регистратор текстовых файлов создает журналы, которые легко просматривать и пересылать.</span><span class="sxs-lookup"><span data-stu-id="26c5e-105">The Text Files log provider creates logs that are easy to view and easily transportable.</span></span> <span data-ttu-id="26c5e-106">Простота этих файлов журнала делает их особенно полезными во время базового тестирования пакета.</span><span class="sxs-lookup"><span data-stu-id="26c5e-106">The simplicity of these log files makes these files especially useful during the basic testing phase of a package.</span></span> <span data-ttu-id="26c5e-107">Для просмотра журнала приложений можно использовать окно «Регистрация событий» конструктора служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="26c5e-107">You can also view the log entries in the Log Events window of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
### <a name="to-add-logging-to-the-package"></a><span data-ttu-id="26c5e-108">Добавление ведения журнала в пакет</span><span class="sxs-lookup"><span data-stu-id="26c5e-108">To add logging to the package</span></span>  
  
1.  <span data-ttu-id="26c5e-109">В меню **Службы SSIS** нажмите **Ведение журнала**.</span><span class="sxs-lookup"><span data-stu-id="26c5e-109">On the **SSIS** menu, click **Logging**.</span></span>  
  
2.  <span data-ttu-id="26c5e-110">В диалоговом окне **Настройка журналов служб SSIS** на панели **Контейнеры** убедитесь, что выбран самый верхний объект, представляющий пакет занятия 3.</span><span class="sxs-lookup"><span data-stu-id="26c5e-110">In the **Configure SSIS Logs** dialog box, in the **Containers** pane, make sure that the topmost object, which represents the Lesson 3 package, is selected.</span></span>  
  
3.  <span data-ttu-id="26c5e-111">На вкладке **Поставщики и журналы** в окне **Типы поставщика** выберите **Регистратор служб SSIS для текстовых файлов**и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="26c5e-111">On the **Providers and Logs** tab, in the **Provider type** box, select **SSIS log provider for Text files**, and then click **Add**.</span></span>  
  
     <span data-ttu-id="26c5e-112">Integration Services добавляет новый поставщик журнала текстовых файлов в пакет с именем по умолчанию **регистратор служб SSIS для текстовых файлов**.</span><span class="sxs-lookup"><span data-stu-id="26c5e-112">Integration Services adds a new Text File log provider to the package with the default name **SSIS log provider for text files**.</span></span> <span data-ttu-id="26c5e-113">Теперь можно настроить новый регистратор.</span><span class="sxs-lookup"><span data-stu-id="26c5e-113">You can now configure the new log provider.</span></span>  
  
4.  <span data-ttu-id="26c5e-114">В столбце **имя** введите `Lesson 3 Log File` .</span><span class="sxs-lookup"><span data-stu-id="26c5e-114">In the **Name** column, type `Lesson 3 Log File`.</span></span>  
  
5.  <span data-ttu-id="26c5e-115">При желании измените столбец **Описание**.</span><span class="sxs-lookup"><span data-stu-id="26c5e-115">Optionally, modify the **Description**.</span></span>  
  
6.  <span data-ttu-id="26c5e-116">В столбце **Конфигурация** щелкните **\<New Connection>** , чтобы указать путь назначения, куда будут записываться сведения журнала.</span><span class="sxs-lookup"><span data-stu-id="26c5e-116">In the **Configuration** column, click **\<New Connection>** to specify the destination to which the log information is written.</span></span>  
  
     <span data-ttu-id="26c5e-117">В диалоговом окне **Редактор диспетчера подключения файлов** в поле **Тип применения**выберите **Создать файл**, после чего нажмите кнопку **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="26c5e-117">In the **File Connection Manager Editor** dialog box, for **Usage type**, select **Create file**, and then click **Browse**.</span></span> <span data-ttu-id="26c5e-118">По умолчанию в диалоговом окне **Выбрать файл** откроется папка проекта, но можно сохранить сведения журнала в любом расположении.</span><span class="sxs-lookup"><span data-stu-id="26c5e-118">By default, the **Select File** dialog box opens the project folder, but you can save log information to any location.</span></span>  
  
7.  <span data-ttu-id="26c5e-119">В диалоговом окне **Выбор файла** в поле **имя файла** введите `TutorialLog.log` и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="26c5e-119">In the **Select File** dialog box, in the **File name** box type `TutorialLog.log`, and click **Open**.</span></span>  
  
8.  <span data-ttu-id="26c5e-120">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Редактор диспетчера подключения файлов** .</span><span class="sxs-lookup"><span data-stu-id="26c5e-120">Click **OK** to close the **File Connection Manager Editor** dialog box.</span></span>  
  
9. <span data-ttu-id="26c5e-121">На панели **Контейнеры** раскройте все узлы иерархии контейнера пакета и снимите все флажки, включая **Извлечь данные валют образца** .</span><span class="sxs-lookup"><span data-stu-id="26c5e-121">In the **Containers** pane, expand all nodes of the package container hierarchy, and then clear all check boxes, including the **Extract Sample Currency Data** check box.</span></span> <span data-ttu-id="26c5e-122">Теперь установите флажок **Извлечь данные валют образца** , чтобы получить события только для данного узла.</span><span class="sxs-lookup"><span data-stu-id="26c5e-122">Now select the check box for **Extract Sample Currency Data** to get only the events for this node.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="26c5e-123"> Если флажок **Извлечь данные валют образца** не установлен и недоступен для выбора, то задача использует установки журнала родительского контейнера и невозможно включить события журнала, которые являются специфичными для данной задачи.</span><span class="sxs-lookup"><span data-stu-id="26c5e-123">If the state of the **Extract Sample Currency Data** check box is dimmed instead of selected, the task uses the log settings of the parent container and you cannot enable the log events that are specific to the task.</span></span>  
  
10. <span data-ttu-id="26c5e-124">На вкладке **Подробности** в столбце **События** выберите события **PipelineExecutionPlan** и **PipelineExecutionTrees** .</span><span class="sxs-lookup"><span data-stu-id="26c5e-124">On the **Details** tab, in the **Events** column, select the **PipelineExecutionPlan** and **PipelineExecutionTrees** events.</span></span>  
  
11. <span data-ttu-id="26c5e-125">Нажмите кнопку **Дополнительно** , чтобы просмотреть подробности, которые регистратор запишет в журнал для каждого события.</span><span class="sxs-lookup"><span data-stu-id="26c5e-125">Click **Advanced** to review the details that the log provider will write to the log for each event.</span></span> <span data-ttu-id="26c5e-126">По умолчанию для выбранных событий автоматически выбираются все категории сведений.</span><span class="sxs-lookup"><span data-stu-id="26c5e-126">By default, all information categories are automatically selected for the events you specify.</span></span>  
  
12. <span data-ttu-id="26c5e-127">Нажмите **Основной** , чтобы скрыть категории сведений.</span><span class="sxs-lookup"><span data-stu-id="26c5e-127">Click **Basic** to hide the information categories.</span></span>  
  
13. <span data-ttu-id="26c5e-128">На вкладке **поставщики и журналы** в столбце **имя** выберите `Lesson 3 Log File` .</span><span class="sxs-lookup"><span data-stu-id="26c5e-128">On the **Provider and Logs** tab, in the **Name** column, select `Lesson 3 Log File`.</span></span> <span data-ttu-id="26c5e-129">Как только будет создан регистратор для пакета, при желании можно отменить его выбор, чтобы временно прекратить регистрацию. При этом регистратор не надо удалять и создавать заново.</span><span class="sxs-lookup"><span data-stu-id="26c5e-129">Once you have created a log provider for your package, you can optionally deselect it to temporarily turn off logging, without having to delete and re-create a log provider.</span></span>  
  
14. <span data-ttu-id="26c5e-130">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="26c5e-130">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="26c5e-131">Next Steps</span><span class="sxs-lookup"><span data-stu-id="26c5e-131">Next Steps</span></span>  
 [<span data-ttu-id="26c5e-132">Шаг 3. Проверка учебного пакета, созданного на занятии 3</span><span class="sxs-lookup"><span data-stu-id="26c5e-132">Step 3: Testing the Lesson 3 Tutorial Package</span></span>](../integration-services/lesson-3-3-testing-the-lesson-3-tutorial-package.md)  
  
  
