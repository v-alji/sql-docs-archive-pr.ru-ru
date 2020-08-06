---
title: Добавление пользовательского отчета в среду Management Studio | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], custom reports
ms.assetid: 3cf8d726-0a90-4f80-98d0-352a2a59be0f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 07263edfb9b255257e0c79733c2c34b279b61cd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654031"
---
# <a name="add-a-custom-report-to-management-studio"></a><span data-ttu-id="87a90-102">Добавление пользовательского отчета в среду Management Studio</span><span class="sxs-lookup"><span data-stu-id="87a90-102">Add a Custom Report to Management Studio</span></span>
  <span data-ttu-id="87a90-103">В данном разделе описывается процесс создания простого отчета служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , который сохраняется как файл в формате RDL, а затем добавляется в среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] в качестве пользовательского отчета.</span><span class="sxs-lookup"><span data-stu-id="87a90-103">This topic describes how to create a simple [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report that is saved as an .rdl file, and then add that rdl file to [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] as a custom report.</span></span> [!INCLUDE[ssRS](../../includes/ssrs.md)] <span data-ttu-id="87a90-104">могут создавать разнообразные сложные отчеты.</span><span class="sxs-lookup"><span data-stu-id="87a90-104">can create a wide variety of sophisticated reports.</span></span> <span data-ttu-id="87a90-105">Чтобы создать отчет по материалам этого раздела, на компьютере необходимо установить среду [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="87a90-105">To create a report by using this topic, you must have [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] installed on the computer.</span></span> <span data-ttu-id="87a90-106">Для запуска пользовательского отчета с помощью среды [!INCLUDE[ssRS](../../includes/ssrs.md)] устанавливать на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] службы [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]не обязательно.</span><span class="sxs-lookup"><span data-stu-id="87a90-106">You do not have to install [!INCLUDE[ssRS](../../includes/ssrs.md)] on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to run a custom report using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
  
### <a name="to-create-a-simple-report-saved-as-an-rdl-file"></a><span data-ttu-id="87a90-107">Создание простого отчета, сохраняемого в файле в формате RDL</span><span class="sxs-lookup"><span data-stu-id="87a90-107">To create a simple report saved as an .rdl file</span></span>  
  
1.  <span data-ttu-id="87a90-108">В меню **Пуск**наведите указатель на **Программы**, **Microsoft SQL Server**и щелкните **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="87a90-108">Click **Start**, point to **Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="87a90-109">В меню **Файл** укажите **Создать**, затем нажмите **Проект**.</span><span class="sxs-lookup"><span data-stu-id="87a90-109">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="87a90-110">В списке **Типы проектов** выберите значение **Проекты бизнес-аналитики**.</span><span class="sxs-lookup"><span data-stu-id="87a90-110">In the **Project Types** list, click **Business Intelligence Projects**.</span></span>  
  
4.  <span data-ttu-id="87a90-111">В списке **Шаблоны** щелкните **Мастер проекта сервера отчетов**.</span><span class="sxs-lookup"><span data-stu-id="87a90-111">In the **Templates** list, click **Report Server Project Wizard**.</span></span>  
  
5.  <span data-ttu-id="87a90-112">В поле **Имя**введите **ConnectionsReport**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="87a90-112">In **Name**, type **ConnectionsReport**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="87a90-113">На вводной странице **Мастер отчетов** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="87a90-113">On the **Report Wizard** introduction page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="87a90-114">На странице **Выбор источника данных** введите в поле "Имя" имя для этого соединения с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)], а затем щелкните **Правка**.</span><span class="sxs-lookup"><span data-stu-id="87a90-114">On the **Select the Data Source** page, in the Name box type a name for this connection to your [!INCLUDE[ssDE](../../includes/ssde-md.md)], and then click **Edit**.</span></span>  
  
8.  <span data-ttu-id="87a90-115">В диалоговом окне **Свойства соединения** в поле **Имя сервера** введите имя экземпляра компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87a90-115">In the **Connection Properties** dialog box, in the **Server name** box, type the name of your instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
9. <span data-ttu-id="87a90-116">В поле **Выберите или введите имя базы данных** введите имя любой базы данных на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], например [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="87a90-116">In the **Select or enter a database name** box, type the name of any database on your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **OK**.</span></span>  
  
10. <span data-ttu-id="87a90-117">На странице **Выбор источника данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="87a90-117">On the **Select the Data Source** page, click **Next**.</span></span>  
  
11. <span data-ttu-id="87a90-118">На странице **Создание запроса** в поле **Строка запроса** введите следующую инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] , указывающую текущие соединения с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)], а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="87a90-118">On the **Design the Query** page, in the **Query string** box, type the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that lists the current connections to your [!INCLUDE[ssDE](../../includes/ssde-md.md)], and then click **Next**.</span></span> <span data-ttu-id="87a90-119">В поле запроса мастера отчетов нельзя вводить параметры отчета.</span><span class="sxs-lookup"><span data-stu-id="87a90-119">The Report Wizard Query string box will not accept report parameters.</span></span> <span data-ttu-id="87a90-120">Более сложные отчеты необходимо создавать вручную.</span><span class="sxs-lookup"><span data-stu-id="87a90-120">More complex custom reports must be created manually.</span></span>  
  
     `SELECT session_id, net_transport FROM sys.dm_exec_connections;`  
  
12. <span data-ttu-id="87a90-121">На странице **Выбор типа отчета** выберите параметр **Табличный**и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="87a90-121">On the **Select the Report Type** page, select **Tabular**, and then click **Finish**.</span></span>  
  
13. <span data-ttu-id="87a90-122">На странице **Завершение работы мастера** в поле **Имя отчета** введите **ConnectionsReport**, затем нажмите кнопку **Готово** , чтобы создать и сохранить отчет.</span><span class="sxs-lookup"><span data-stu-id="87a90-122">On the **Completing the Wizard** page, in the **Report name** box, type **ConnectionsReport**, and then click **Finish** to create and save the report.</span></span>  
  
14. <span data-ttu-id="87a90-123">Закройте среду [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87a90-123">Close [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
15. <span data-ttu-id="87a90-124">Скопируйте файл **ConnectionsReport.rdl** в папку, созданную на сервере баз данных для пользовательских отчетов.</span><span class="sxs-lookup"><span data-stu-id="87a90-124">Copy **ConnectionsReport.rdl** to a folder that you created on the database server for custom reports.</span></span>  
  
### <a name="to-add-a-report-to-management-studio"></a><span data-ttu-id="87a90-125">Добавление отчета в среду Management Studio</span><span class="sxs-lookup"><span data-stu-id="87a90-125">To add a report to Management Studio</span></span>  
  
-   <span data-ttu-id="87a90-126">В среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]щелкните узел в обозревателе объектов, укажите **Отчеты**и выберите **Пользовательские отчеты**.</span><span class="sxs-lookup"><span data-stu-id="87a90-126">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click a node in Object Explorer, point to **Reports**, click **Custom Reports**.</span></span> <span data-ttu-id="87a90-127">В диалоговом окне **Открытие файла** выберите папку пользовательских отчетов, укажите файл **ConnectionsReport.rdl** и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="87a90-127">In the **Open File** dialog box, locate the custom reports folder and select the **ConnectionsReport.rdl** file, and then click **Open**.</span></span>  
  
     <span data-ttu-id="87a90-128">При первом открытии пользовательского отчета из узла в обозревателе этот отчет добавляется к списку недавно использовавшихся **пользовательских отчетов** в контекстном меню этого узла.</span><span class="sxs-lookup"><span data-stu-id="87a90-128">When a new custom report is first opened from an Object Explorer node, the custom report is added to the most recently used list under **Custom Reports** on the shortcut menu of that node.</span></span> <span data-ttu-id="87a90-129">При первом открытии стандартного отчета он также отобразится в списке недавно использовавшихся **пользовательских отчетов**.</span><span class="sxs-lookup"><span data-stu-id="87a90-129">When a standard report is opened for the first time, it will also appear on the most recently used list under **Custom Reports**.</span></span> <span data-ttu-id="87a90-130">Если удалить пользовательский отчет, при следующем выборе этого элемента появится запрос на удаление его из списка недавно использовавшихся отчетов.</span><span class="sxs-lookup"><span data-stu-id="87a90-130">If a custom report file is deleted, the next time that the item is selected, a prompt will appear to delete the item from the most recently used list.</span></span>  
  
    1.  <span data-ttu-id="87a90-131">Чтобы изменить количество файлов, отображаемых в списке недавно использовавшихся, выберите в меню **Сервис** пункт **Параметры** , раскройте папку **Среда** и выберите **Общие**.</span><span class="sxs-lookup"><span data-stu-id="87a90-131">To change the number of files that are displayed on the recently used list, on the **Tools** menu, click **Options,** expand the **Environment** folder, and then click **General**.</span></span>  
  
    2.  <span data-ttu-id="87a90-132">Измените число в поле **Показать n файлов в списке недавно использованных**.</span><span class="sxs-lookup"><span data-stu-id="87a90-132">Adjust the number for **Display files in recently used list**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87a90-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="87a90-133">See Also</span></span>  
 <span data-ttu-id="87a90-134">[Пользовательские отчеты в Management Studio](custom-reports-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="87a90-134">[Custom Reports in Management Studio](custom-reports-in-management-studio.md) </span></span>  
 <span data-ttu-id="87a90-135">[Использование пользовательских отчетов в свойствах узла обозревателя объектов](use-custom-reports-with-object-explorer-node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="87a90-135">[Use Custom Reports with Object Explorer Node Properties](use-custom-reports-with-object-explorer-node-properties.md) </span></span>  
 <span data-ttu-id="87a90-136">[Отменить подавление предупреждений о выполнении пользовательских отчетов](unsuppress-run-custom-report-warnings.md) </span><span class="sxs-lookup"><span data-stu-id="87a90-136">[Unsuppress Run Custom Report Warnings](unsuppress-run-custom-report-warnings.md) </span></span>  
 [<span data-ttu-id="87a90-137">Службы Reporting Services (SSRS)</span><span class="sxs-lookup"><span data-stu-id="87a90-137">Reporting Services &#40;SSRS&#41;</span></span>](../../reporting-services/create-deploy-and-manage-mobile-and-paginated-reports.md)  
  
  
