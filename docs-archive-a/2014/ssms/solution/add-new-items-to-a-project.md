---
title: Добавление новых элементов в проект | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], item additions
- adding project items
ms.assetid: 76af8692-324f-4f5e-b1a0-d72ca8a107e3
author: stevestein
ms.author: sstein
ms.openlocfilehash: c73c58952c7801b3a0e2c86652feb461292cf37c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668547"
---
# <a name="add-new-items-to-a-project"></a><span data-ttu-id="33b62-102">Добавление в проект новые элементы</span><span class="sxs-lookup"><span data-stu-id="33b62-102">Add New Items to a Project</span></span>
  <span data-ttu-id="33b62-103">Для расширения возможностей приложения в проект можно добавлять новые элементы.</span><span class="sxs-lookup"><span data-stu-id="33b62-103">Add new items to a project to extend application functionality.</span></span> <span data-ttu-id="33b62-104">В качестве нового элемента может быть выбран запрос или соединение.</span><span class="sxs-lookup"><span data-stu-id="33b62-104">A new item can be a query or a connection.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="33b62-105">имеет два типа проектов: проект скрипта [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и проект скрипта служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="33b62-105">has two project types: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script Project, and Analysis Services Script Project.</span></span> <span data-ttu-id="33b62-106">Тип проекта определяет элементы, которые можно добавлять в проект.</span><span class="sxs-lookup"><span data-stu-id="33b62-106">The project type determines the items that you can add to the project.</span></span> <span data-ttu-id="33b62-107">Например, запрос [!INCLUDE[tsql](../../includes/tsql-md.md)] (SQL-файл) можно добавить в проект скрипта [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , но нельзя добавить в проект скрипта служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="33b62-107">For example, you can add a [!INCLUDE[tsql](../../includes/tsql-md.md)] query (a file with a .sql extension) to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script project, but you cannot add it to an Analysis Services Script Project.</span></span>  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="33b62-108">не разрешает добавлять папки внутри проекта.</span><span class="sxs-lookup"><span data-stu-id="33b62-108">does not allow you to create folders within projects.</span></span> <span data-ttu-id="33b62-109">Для организации работы следует создавать несколько проектов внутри решения.</span><span class="sxs-lookup"><span data-stu-id="33b62-109">To organize your work, create multiple projects within the solution.</span></span>  
  
### <a name="to-add-a-new-query-to-an-existing-project"></a><span data-ttu-id="33b62-110">Добавление нового запроса в существующий проект</span><span class="sxs-lookup"><span data-stu-id="33b62-110">To add a new query to an existing project</span></span>  
  
1.  <span data-ttu-id="33b62-111">Выберите целевой проект в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="33b62-111">In Solution Explorer, select a target project.</span></span>  
  
2.  <span data-ttu-id="33b62-112">В меню **Проект** выберите **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="33b62-112">On the **Project** menu, click **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="33b62-113">Выберите категорию в левой панели диалогового окна **Добавление нового элемента** .</span><span class="sxs-lookup"><span data-stu-id="33b62-113">In the **Add New Item** dialog box, select a category in the left pane.</span></span>  
  
4.  <span data-ttu-id="33b62-114">В правой панели выберите шаблон запроса, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="33b62-114">Select a query template in the right pane, and then click **Add**.</span></span> <span data-ttu-id="33b62-115">Новый запрос будет добавлен в папку **Запросы** проекта.</span><span class="sxs-lookup"><span data-stu-id="33b62-115">The new query is added in the **Queries** folder of the project.</span></span>  
  
5.  <span data-ttu-id="33b62-116">В диалоговом окне **Подключиться к ядру СУБД** задайте соединение для нового запроса, затем нажмите **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="33b62-116">In the **Connect to Database Engine** dialog box, specify a connection for the new query, and then click **Connect**.</span></span> <span data-ttu-id="33b62-117">Если нет необходимости связывать подключение с новым запросом, в диалоговом окне соединения можно нажать кнопку **Отмена** .</span><span class="sxs-lookup"><span data-stu-id="33b62-117">You can click **Cancel** on the connection dialog if you do not want to associate a connection to the new query.</span></span>  
  
6.  <span data-ttu-id="33b62-118">При необходимости переименуйте запрос в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="33b62-118">Rename the query in Solution Explorer if you wish.</span></span>  
  
### <a name="to-add-a-new-connection-to-an-existing-project"></a><span data-ttu-id="33b62-119">Добавление нового соединения в существующий проект</span><span class="sxs-lookup"><span data-stu-id="33b62-119">To add a new connection to an existing project</span></span>  
  
1.  <span data-ttu-id="33b62-120">Выберите целевой проект в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="33b62-120">In Solution Explorer, select a target project.</span></span>  
  
2.  <span data-ttu-id="33b62-121">В меню **Проект** выберите **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="33b62-121">On the **Project** menu, click **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="33b62-122">В левой панели выберите пункт **Соединение** .</span><span class="sxs-lookup"><span data-stu-id="33b62-122">Select **Connection** in the left pane.</span></span>  
  
4.  <span data-ttu-id="33b62-123">В правой панели выберите пункт **Новое соединение** , а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="33b62-123">Select **New Connection** in the right pane, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="33b62-124">В диалоговом окне **Подключиться к ядру СУБД** задайте соединение для нового запроса, затем нажмите **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="33b62-124">In the **Connect to Database Engine** dialog box, specify a connection for the new query, and then click **Connect**.</span></span> <span data-ttu-id="33b62-125">Новое соединение будет добавлено в папку **Соединение** проекта.</span><span class="sxs-lookup"><span data-stu-id="33b62-125">The new connection gets added in the **Connections** folder of the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b62-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="33b62-126">See Also</span></span>  
 <span data-ttu-id="33b62-127">[обозреватель решений](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="33b62-127">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="33b62-128">[Связывание расширений файлов с редактором кода](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md) </span><span class="sxs-lookup"><span data-stu-id="33b62-128">[Associate File Extensions to a Code Editor](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md) </span></span>  
 <span data-ttu-id="33b62-129">[Добавление существующих элементов в проект](add-existing-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="33b62-129">[Add Existing Items to a Project](add-existing-items-to-a-project.md) </span></span>  
 [<span data-ttu-id="33b62-130">Перемещение или удаление элемента или проекта</span><span class="sxs-lookup"><span data-stu-id="33b62-130">Remove or Delete an Item or Project</span></span>](remove-or-delete-an-item-or-project.md)  
  
  
