---
title: Диалоговое окно "Обзор всех участников" | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.browseprincipals.f1
ms.assetid: f11d2c5e-ee05-45f3-8dc2-0feb99b2f76f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c204411a4daace27745e46269cbcfa0ed33f323f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655899"
---
# <a name="browse-all-principals-dialog-box"></a><span data-ttu-id="1c7ec-102">Просмотр всех участников-диалоговое окно</span><span class="sxs-lookup"><span data-stu-id="1c7ec-102">Browse All Principals Dialog Box</span></span>
  <span data-ttu-id="1c7ec-103">Диалоговое окно **Просмотр всех участников** используется для выбора участника базы данных с тем, чтобы изменить его разрешения для выбранного проекта или для всех проектов, содержащихся в выбранной папке.</span><span class="sxs-lookup"><span data-stu-id="1c7ec-103">Use the **Browse All Principals** dialog box to select a database principal to change the principal's permissions on the selected project or on all projects contained in a selected folder.</span></span>  
  
 <span data-ttu-id="1c7ec-104">**Выбор действия**</span><span class="sxs-lookup"><span data-stu-id="1c7ec-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="1c7ec-105">Открытие диалогового окна «Просмотр всех участников»</span><span class="sxs-lookup"><span data-stu-id="1c7ec-105">Open the Browse All Principals dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="1c7ec-106">Настройка параметров</span><span class="sxs-lookup"><span data-stu-id="1c7ec-106">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-browse-all-principals-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="1c7ec-107">Открытие диалогового окна «Просмотр всех участников»</span><span class="sxs-lookup"><span data-stu-id="1c7ec-107">Open the Browse All Principals dialog box</span></span>  
  
1.  <span data-ttu-id="1c7ec-108">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]установите соединение с сервером служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1c7ec-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="1c7ec-109">Вы устанавливаете соединение с экземпляром служб [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], на котором размещен каталог SSISDB.</span><span class="sxs-lookup"><span data-stu-id="1c7ec-109">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB catalog.</span></span>  
  
2.  <span data-ttu-id="1c7ec-110">В обозревателе объектов разверните дерево для отображения узла **Каталоги служб Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="1c7ec-110">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="1c7ec-111">Разверните узел **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="1c7ec-111">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="1c7ec-112">Чтобы изменить разрешения участника для всех проектов, содержащихся в выбранной папке, щелкните правой кнопкой мыши папку и выберите команду **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1c7ec-112">To change the principal's permissions on all projects contained in a selected folder, right-click the folder and then click **Properties**.</span></span>  
  
     <span data-ttu-id="1c7ec-113">Чтобы изменить разрешения участника для выбранного проекта, разверните папку, в которой находится этот проект, щелкните его правой кнопкой мыши и выберите команду **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1c7ec-113">To change the principal's permissions on a selected project, expand the folder that contains the project, right-click the project, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="1c7ec-114">Выберите страницу **Разрешения** и нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="1c7ec-114">Select the **Permissions** page, and then click **Browse**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="1c7ec-115">Настройка параметров</span><span class="sxs-lookup"><span data-stu-id="1c7ec-115">Configure the Options</span></span>  
 <span data-ttu-id="1c7ec-116">На этой странице отображаются участники из представления каталога ys.database_principals базы данных служб SSISDB.</span><span class="sxs-lookup"><span data-stu-id="1c7ec-116">This page displays the principals from the catalog view, sys.database_principals, of the SSISDB database.</span></span>  
  
 <span data-ttu-id="1c7ec-117">Выбранные участники добавляются в список **Имена входа или роли** на странице **Разрешения** родительского диалогового окна при нажатии кнопки **ОК** и закрытии диалогового окна **Просмотр всех участников** .</span><span class="sxs-lookup"><span data-stu-id="1c7ec-117">Selecting principals adds them to the **Logins or roles** list on the **Permissions** page of the parent dialog box when you click **OK** and close the **Browse All Principals** dialog box.</span></span> <span data-ttu-id="1c7ec-118">После добавления участников в список **Имена входа или роли** можно изменить их разрешения для выбранного проекта.</span><span class="sxs-lookup"><span data-stu-id="1c7ec-118">After adding principals to the **Logins or roles** list, you can change their permissions on the selected project.</span></span>  
  
 <span data-ttu-id="1c7ec-119">**Столбец выбора**</span><span class="sxs-lookup"><span data-stu-id="1c7ec-119">**Selection column**</span></span>  
 <span data-ttu-id="1c7ec-120">Выберите его для добавления участника в список **Имена входа или роли** на странице **Разрешения** родительского диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="1c7ec-120">Select to add the principal to the **Logins or roles** list on the **Permissions** page of the parent dialog box.</span></span>  
  
 <span data-ttu-id="1c7ec-121">**Значок столбца**</span><span class="sxs-lookup"><span data-stu-id="1c7ec-121">**Icon column**</span></span>  
 <span data-ttu-id="1c7ec-122">Значок, соответствующий **типу** участника.</span><span class="sxs-lookup"><span data-stu-id="1c7ec-122">An icon that corresponds to the **Type** of the principal.</span></span>  
  
 <span data-ttu-id="1c7ec-123">**Название**</span><span class="sxs-lookup"><span data-stu-id="1c7ec-123">**Name**</span></span>  
 <span data-ttu-id="1c7ec-124">Имя участника.</span><span class="sxs-lookup"><span data-stu-id="1c7ec-124">The name of the principal.</span></span>  
  
 <span data-ttu-id="1c7ec-125">**Тип**</span><span class="sxs-lookup"><span data-stu-id="1c7ec-125">**Type**</span></span>  
 <span data-ttu-id="1c7ec-126">Тип участника.</span><span class="sxs-lookup"><span data-stu-id="1c7ec-126">The type of the principal.</span></span> <span data-ttu-id="1c7ec-127">Ниже приведены некоторые наиболее распространенные типы.</span><span class="sxs-lookup"><span data-stu-id="1c7ec-127">The common types are:</span></span>  
  
-   <span data-ttu-id="1c7ec-128">SQL User</span><span class="sxs-lookup"><span data-stu-id="1c7ec-128">SQL User</span></span>  
  
-   <span data-ttu-id="1c7ec-129">Пользователь Windows</span><span class="sxs-lookup"><span data-stu-id="1c7ec-129">Windows User</span></span>  
  
-   <span data-ttu-id="1c7ec-130">Роль базы данных</span><span class="sxs-lookup"><span data-stu-id="1c7ec-130">Database Role</span></span>  
  
  
