---
title: Сохранение скриптов в виде проектов или решений | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 72dfd37f-dbe7-4d1d-bda6-7eb54c7922d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9fade3900c8859f211bb0c66820dc97792262481
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733397"
---
# <a name="save-scripts-as-projects-or-solutions"></a><span data-ttu-id="8af19-102">Сохранение скриптов в виде проектов или решений</span><span class="sxs-lookup"><span data-stu-id="8af19-102">Save Scripts as Projects or Solutions</span></span>
  <span data-ttu-id="8af19-103">Разработчики, знакомые со средой [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio, найдут удобным обозреватель решений в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8af19-103">Developers familiar with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio will welcome Solution Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="8af19-104">Скрипты, которые поддерживают бизнес, могут быть сгруппированы в проекты скриптов, а проектами скриптов можно одновременно управлять как решением.</span><span class="sxs-lookup"><span data-stu-id="8af19-104">The scripts that support your business can be grouped into script projects, and the script projects can be managed together as a solution.</span></span> <span data-ttu-id="8af19-105">Когда скрипты помещены в проекты скриптов и решения, они могут быть открыты вместе как группа или сохранены вместе в системе управления версиями, например Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="8af19-105">When scripts are placed in script projects and solutions they can be opened together as a group, or saved together to a source control product such as Visual SourceSafe.</span></span> <span data-ttu-id="8af19-106">Проекты скриптов включают данные о соединениях, необходимые для правильного выполнения скриптов, а также могут содержать файлы других типов, такие как вспомогательные текстовые файлы.</span><span class="sxs-lookup"><span data-stu-id="8af19-106">Script projects include the connection information for the scripts to execute properly, and can include non-script files such as a supporting text file.</span></span>  
  
 <span data-ttu-id="8af19-107">В следующем практическом задании предстоит создать короткий скрипт, выполняющий запрос к базе данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , включенной в проект скрипта и решение.</span><span class="sxs-lookup"><span data-stu-id="8af19-107">The following practice creates a short script that queries the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, placed in a script project and solution.</span></span>  
  
## <a name="using-script-projects-and-solutions"></a><span data-ttu-id="8af19-108">Использование проектов скриптов и решений</span><span class="sxs-lookup"><span data-stu-id="8af19-108">Using Script Projects and Solutions</span></span>  
  
#### <a name="to-create-a-script-project-and-solution"></a><span data-ttu-id="8af19-109">Создание проекта скрипта и решения</span><span class="sxs-lookup"><span data-stu-id="8af19-109">To create a script project and solution</span></span>  
  
1.  <span data-ttu-id="8af19-110">Откройте среду [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]и подключитесь к серверу в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="8af19-110">Open [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and connect to a server with Object Explorer.</span></span>  
  
2.  <span data-ttu-id="8af19-111">В меню **Файл** выберите пункт **Создать**, а затем команду **Проект**.</span><span class="sxs-lookup"><span data-stu-id="8af19-111">On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="8af19-112">Откроется диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="8af19-112">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="8af19-113">В текстовом поле **Имя** введите **StatusCheck**, выберите в списке **Шаблоны** шаблон **Скрипты SQL Server**и нажмите кнопку **ОК** , чтобы открыть новое решение и проект скрипта.</span><span class="sxs-lookup"><span data-stu-id="8af19-113">In the **Name** text box, type **StatusCheck**, click **SQL Server Scripts** in **Templates**, and then click **OK** to open a new solution and script project.</span></span>  
  
4.  <span data-ttu-id="8af19-114">В обозревателе решений щелкните правой кнопкой мыши элемент **Соединения**и выберите команду **Создать соединение**.</span><span class="sxs-lookup"><span data-stu-id="8af19-114">In Solution Explorer, right-click **Connections**, and then click **New Connection**.</span></span> <span data-ttu-id="8af19-115">Будет открыто диалоговое окно **Соединение с сервером** .</span><span class="sxs-lookup"><span data-stu-id="8af19-115">The **Connect to Server** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="8af19-116">В списке **Имя сервера** введите имя сервера.</span><span class="sxs-lookup"><span data-stu-id="8af19-116">In the **Server name** list box, type the name of your server.</span></span>  
  
6.  <span data-ttu-id="8af19-117">Щелкните элемент **Параметры**и перейдите на вкладку **Свойства соединения** .</span><span class="sxs-lookup"><span data-stu-id="8af19-117">Click **Options**, and then click the **Connection Properties** tab.</span></span>  
  
7.  <span data-ttu-id="8af19-118">В поле **Соединение с базой данных** найдите нужный сервер, выберите базу данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] и нажмите кнопку **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="8af19-118">In the **Connect to database** box, browse the server, select the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, and then click **Connect**.</span></span> <span data-ttu-id="8af19-119">Сведения о соединении, включая базу данных, добавляются к проекту.</span><span class="sxs-lookup"><span data-stu-id="8af19-119">The connection information including the database is added to the project.</span></span>  
  
8.  <span data-ttu-id="8af19-120">Если окно свойств не отображено, выберите новое соединение в обозревателе решений и нажмите клавишу F4.</span><span class="sxs-lookup"><span data-stu-id="8af19-120">If the Properties window is not displayed, click the new connection in Solution Explorer, and then press F4.</span></span> <span data-ttu-id="8af19-121">Откроется окно свойств соединения, в котором приводятся сведения о соединении, причем параметр **Исходная база данных** будет иметь значение [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8af19-121">The properties for the connection appear, and show information about the connection including the **Initial Database** as [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
9. <span data-ttu-id="8af19-122">В обозревателе решений щелкните соединение правой кнопкой мыши и выберите команду **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="8af19-122">In Solution Explorer, right-click the connection, and then click **New Query**.</span></span> <span data-ttu-id="8af19-123">Будет создан новый запрос с именем **SQLQuery1.sql** , который будет подключен к базе данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] и добавлен в проект скрипта.</span><span class="sxs-lookup"><span data-stu-id="8af19-123">A new query called **SQLQuery1.sql** is created, connected to the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database on your server, and added to your script project.</span></span>  
  
10. <span data-ttu-id="8af19-124">В редакторе запросов введите следующий запрос, чтобы узнать, в скольких заказах на производство дата выполнения предшествует дате начала работы по этим заказам.</span><span class="sxs-lookup"><span data-stu-id="8af19-124">In Query Editor, type the following query to determine how many work orders have due dates, before the work order starting dates.</span></span> <span data-ttu-id="8af19-125">Код сценария можно скопировать из учебника.</span><span class="sxs-lookup"><span data-stu-id="8af19-125">(You can copy and paste the code from the Tutorial window.)</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT COUNT(WorkOrderID)  
    FROM Production.WorkOrder  
    WHERE DueDate < StartDate;  
  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="8af19-126">Если требуется больше места для ввода запроса, нажмите клавиши SHIFT + ALT + ВВОД, чтобы переключиться в полноэкранный режим.</span><span class="sxs-lookup"><span data-stu-id="8af19-126">If you need more room to type your query, press SHIFT+ALT+ENTER, to switch to full-screen mode.</span></span>  
  
11. <span data-ttu-id="8af19-127">В обозревателе решений щелкните правой кнопкой мыши элемент **SQLQuery1**и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="8af19-127">In Solution Explorer, right-click **SQLQuery1**, and then click **Rename**.</span></span> <span data-ttu-id="8af19-128">Введите **Check заказы. SQL** в качестве нового имени запроса и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="8af19-128">Type **Check Workorders.sql** as the new name for the query and press ENTER.</span></span>  
  
12. <span data-ttu-id="8af19-129">Чтобы сохранить проект скрипта и решение, в меню **Файл** выберите команду **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="8af19-129">To save your solution and script project, on the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="8af19-130">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="8af19-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="8af19-131">Сводка. Решения и проекты скриптов</span><span class="sxs-lookup"><span data-stu-id="8af19-131">Summary: Solutions and Script Projects</span></span>](lesson-3-4-summary-solutions-and-script-projects.md)  
  
  
