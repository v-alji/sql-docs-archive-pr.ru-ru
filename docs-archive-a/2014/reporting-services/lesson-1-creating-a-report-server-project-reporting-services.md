---
title: Занятие 1. Создание проекта сервера отчетов (службы Reporting Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 675671ca-e6c9-48a2-82e9-386778f3a49f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a708e5114344e87edd620ef58bc50594a9b9ef8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751812"
---
# <a name="lesson-1-creating-a-report-server-project-reporting-services"></a><span data-ttu-id="8a0fb-102">Занятие 1. Создание проекта сервера отчетов (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="8a0fb-102">Lesson 1: Creating a Report Server Project (Reporting Services)</span></span>
  <span data-ttu-id="8a0fb-103">Чтобы создать отчет в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], необходимо сначала создать проект сервера отчетов, в котором будет сохранен файл определения отчета (с расширением RDL) и другие файлы ресурсов, необходимые для отчета.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-103">To create a report in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you must first create a report server project where you will save your report definition (.rdl) file and any other resource files that you need for your report.</span></span> <span data-ttu-id="8a0fb-104">Затем будет создан действительный файл определения отчета, определен источник данных для этого отчета, набор данных и макет отчета.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-104">Then you will create the actual report definition file, define a data source for your report, define a dataset, and define the report layout.</span></span> <span data-ttu-id="8a0fb-105">При выполнении отчета происходит получение и объединение фактических данных с макетом, затем осуществляется его подготовка к просмотру на экране, после чего может быть выполнен их импорт, печать или сохранение.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-105">When you run the report, the actual data is retrieved and combined with the layout, and then rendered on your screen, from where you can export it, print it, or save it.</span></span>  
  
 <span data-ttu-id="8a0fb-106">На этом занятии описано, как создать проект сервера отчетов в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a0fb-106">In this lesson, you will learn how to create a report server project in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="8a0fb-107">Проект сервера отчетов используется для создания отчетов, которые выполняются на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-107">A report server project is used to create reports that run on a report server.</span></span>  
  
### <a name="to-create-a-report-server-project"></a><span data-ttu-id="8a0fb-108">Создание проекта сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="8a0fb-108">To create a report server project</span></span>  
  
1.  <span data-ttu-id="8a0fb-109">Нажмите кнопку **Пуск**, укажите пункт **все программы**, [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] а затем выберите пункт **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-109">Click **Start**, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)], and then click **SQL Server Data Tools**.</span></span> <span data-ttu-id="8a0fb-110">Если вы открыли его впервые [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] , щелкните **Параметры бизнес-аналитики** для параметров среды по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-110">If this is the first time you have opened [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Business Intelligence Settings** for the default environment settings.</span></span>  
  
2.  <span data-ttu-id="8a0fb-111">В меню **Файл** выберите пункт **Создать**, а затем команду **Проект**.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-111">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="8a0fb-112">В списке **Установленные шаблоны** щелкните **Бизнес-аналитика**.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-112">In the **Installed Templates** list, click **Business Intelligence**.</span></span>  
  
4.  <span data-ttu-id="8a0fb-113">Щелкните **проект сервера отчетов**.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-113">Click **Report Server Project**.</span></span>  
  
5.  <span data-ttu-id="8a0fb-114">В поле **Имя**введите **Руководство**.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-114">In **Name**, type **Tutorial**.</span></span>  
  
6.  <span data-ttu-id="8a0fb-115">Чтобы создать проект, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="8a0fb-115">Click **OK** to create the project.</span></span>  
  
     <span data-ttu-id="8a0fb-116">Проект «Учебник» будет отображен в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-116">The Tutorial project is displayed in Solution Explorer.</span></span>  
  
### <a name="to-create-a-new-report-definition-file"></a><span data-ttu-id="8a0fb-117">Создание файла определения отчета</span><span class="sxs-lookup"><span data-stu-id="8a0fb-117">To create a new report definition file</span></span>  
  
1.  <span data-ttu-id="8a0fb-118">В обозреватель решений щелкните правой кнопкой мыши элемент **отчеты**, наведите указатель на пункт **Добавить**и выберите пункт **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-118">In Solution Explorer, right-click **Reports**, point to **Add**, and click **New Item**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8a0fb-119">Если окно **Обозреватель решений** не отображается, в меню **Вид** выберите пункт **Обозреватель решений**.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-119">If the **Solution Explorer** window is not visible, from the **View** menu, click **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="8a0fb-120">В диалоговом окне **Добавление нового элемента** в разделе **шаблоны**щелкните **отчет**.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-120">In the **Add New Item** dialog box, under **Templates**, click **Report**.</span></span>  
  
3.  <span data-ttu-id="8a0fb-121">В поле **Имя**введите **Sales Orders.rdl** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-121">In **Name**, type **Sales Orders.rdl** and then click **Add**.</span></span>  
  
     <span data-ttu-id="8a0fb-122">Конструктор отчетов откроет и отобразит новый RDL-файл в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-122">Report Designer opens and displays the new .rdl file in Design view.</span></span>  
  
 <span data-ttu-id="8a0fb-123">Конструктор отчетов является компонентом служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , запускаемым в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a0fb-123">Report Designer is a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] component that runs in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="8a0fb-124">Он имеет два представления: **Конструктор** и **Предварительный просмотр**.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-124">It has two views: **Design** and **Preview**.</span></span> <span data-ttu-id="8a0fb-125">Смена представлений осуществляется посредством выбора вкладок.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-125">Click each tab to change views.</span></span>  
  
 <span data-ttu-id="8a0fb-126">Данные определяются в области **Данные отчета** .</span><span class="sxs-lookup"><span data-stu-id="8a0fb-126">You define your data in the **Report Data** pane.</span></span> <span data-ttu-id="8a0fb-127">Макет отчета определяется в представлении **Конструктор** .</span><span class="sxs-lookup"><span data-stu-id="8a0fb-127">You define your report layout in **Design** view.</span></span> <span data-ttu-id="8a0fb-128">Отчет можно выполнить и посмотреть, как он выглядит, в представлении **Предварительный просмотр** .</span><span class="sxs-lookup"><span data-stu-id="8a0fb-128">You can run the report and see what it looks like in **Preview** view.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="8a0fb-129">Следующая задача</span><span class="sxs-lookup"><span data-stu-id="8a0fb-129">Next Task</span></span>  
 <span data-ttu-id="8a0fb-130">Создание проекта отчета с именем «Учебник» и добавление в него файла определения отчета (с расширением RDL) успешно завершено.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-130">You have successfully created a report project called "Tutorial" and added a report definition (.rdl) file to the report project.</span></span> <span data-ttu-id="8a0fb-131">Далее требуется определить источник данных, который будет использован в отчете.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-131">Next, you will specify a data source to use for the report.</span></span> <span data-ttu-id="8a0fb-132">См. раздел [Занятие 2. Задание информации о соединении (службы Reporting Services)](lesson-2-specifying-connection-information-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="8a0fb-132">See [Lesson 2: Specifying Connection Information &#40;Reporting Services&#41;](lesson-2-specifying-connection-information-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a0fb-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="8a0fb-133">See Also</span></span>  
 [<span data-ttu-id="8a0fb-134">Создание простого табличного отчета (учебник по службам SSRS)</span><span class="sxs-lookup"><span data-stu-id="8a0fb-134">Create a Basic Table Report &#40;SSRS Tutorial&#41;</span></span>](create-a-basic-table-report-ssrs-tutorial.md)  
  
  
