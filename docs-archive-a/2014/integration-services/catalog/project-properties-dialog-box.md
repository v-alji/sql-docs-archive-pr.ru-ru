---
title: Диалоговое окно "Свойства проекта" | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isprojectprop.general.f1
- sql12.ssis.ssms.isprojectprop.permissions.f1
ms.assetid: d5cf52f5-1fe2-438a-98a3-fe117360acf8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 259ad48f2b1f33356243635bbaa5426a5199eccf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731969"
---
# <a name="project-properties-dialog-box"></a><span data-ttu-id="ce635-102">Диалоговое окно свойств проекта</span><span class="sxs-lookup"><span data-stu-id="ce635-102">Project Properties Dialog Box</span></span>
  <span data-ttu-id="ce635-103">Проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] представляет собой единицу развертывания.</span><span class="sxs-lookup"><span data-stu-id="ce635-103">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project is a unit of deployment.</span></span> <span data-ttu-id="ce635-104">Каждый проект может содержать пакеты, параметры и ссылки на среду.</span><span class="sxs-lookup"><span data-stu-id="ce635-104">Each project can contain packages, parameters, and environment references.</span></span> <span data-ttu-id="ce635-105">Проект является защищаемым объектом и может определять разрешения для участников базы данных.</span><span class="sxs-lookup"><span data-stu-id="ce635-105">A project is a securable object and can define permissions for database principals.</span></span> <span data-ttu-id="ce635-106">При повторном развертывании проекта предыдущая версия проекта может быть сохранена в каталоге служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce635-106">When a project is re-deployed, the previous version of the project can be stored in the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] catalog.</span></span>  
  
 <span data-ttu-id="ce635-107">Параметры проекта и пакета могут быть использованы для присвоения значений свойствам внутри пакетов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ce635-107">Project parameters and package parameters can be used to assign values to properties within packages at the time of execution.</span></span> <span data-ttu-id="ce635-108">Некоторым параметрам необходимо заранее присвоить значения, чтобы пакет можно было выполнить.</span><span class="sxs-lookup"><span data-stu-id="ce635-108">Some parameters require values before the package can be executed.</span></span> <span data-ttu-id="ce635-109">При использовании ссылок на переменные среды в значениях параметров требуется, чтобы эти ссылки присутствовали в проекте перед выполнением.</span><span class="sxs-lookup"><span data-stu-id="ce635-109">Parameter values that reference environment variables require that the project has the corresponding environment reference prior to execution.</span></span>  
  
 <span data-ttu-id="ce635-110">**Выбор действия**</span><span class="sxs-lookup"><span data-stu-id="ce635-110">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="ce635-111">Открытие диалогового окна «Свойства проекта»</span><span class="sxs-lookup"><span data-stu-id="ce635-111">Open the Project Properties dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="ce635-112">Задание параметров на странице «Общие»</span><span class="sxs-lookup"><span data-stu-id="ce635-112">Set the options on the General page</span></span>](#general)  
  
-   [<span data-ttu-id="ce635-113">Задание параметров на странице «Разрешения»</span><span class="sxs-lookup"><span data-stu-id="ce635-113">Set the options on the Permissions page</span></span>](#permissions)  
  
##  <a name="open-the-project-properties-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="ce635-114">Открытие диалогового окна «Свойства проекта»</span><span class="sxs-lookup"><span data-stu-id="ce635-114">Open the Project Properties dialog box</span></span>  
  
1.  <span data-ttu-id="ce635-115">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]установите соединение с сервером служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce635-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="ce635-116">Устанавливается соединение с экземпляром [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], в котором размещена база данных SSISDB.</span><span class="sxs-lookup"><span data-stu-id="ce635-116">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="ce635-117">В обозревателе объектов разверните дерево для отображения узла **Каталоги служб Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="ce635-117">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="ce635-118">Разверните узел **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="ce635-118">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="ce635-119">Разверните папку, содержащую проект, свойства которого требуется установить.</span><span class="sxs-lookup"><span data-stu-id="ce635-119">Expand the folder that contains the project that you want to set properties for.</span></span>  
  
5.  <span data-ttu-id="ce635-120">Щелкните правой кнопкой мыши проект и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ce635-120">Right-click the project, and then click **Properties**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="ce635-121">Задание параметров на странице «Общие»</span><span class="sxs-lookup"><span data-stu-id="ce635-121">Set the options on the General page</span></span>  
 <span data-ttu-id="ce635-122">Используйте страницу «Общие» для просмотра свойств проекта.</span><span class="sxs-lookup"><span data-stu-id="ce635-122">Use the General page to view project properties.</span></span>  
  
 <span data-ttu-id="ce635-123">**Название**</span><span class="sxs-lookup"><span data-stu-id="ce635-123">**Name**</span></span>  
 <span data-ttu-id="ce635-124">Выводит список имен проекта.</span><span class="sxs-lookup"><span data-stu-id="ce635-124">Lists the project name.</span></span>  
  
 <span data-ttu-id="ce635-125">**Идентификатор**</span><span class="sxs-lookup"><span data-stu-id="ce635-125">**Identifier**</span></span>  
 <span data-ttu-id="ce635-126">Выводит список идентификаторов проекта.</span><span class="sxs-lookup"><span data-stu-id="ce635-126">Lists the project ID.</span></span>  
  
 <span data-ttu-id="ce635-127">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ce635-127">**Description**</span></span>  
 <span data-ttu-id="ce635-128">Показывает необязательное описание проекта.</span><span class="sxs-lookup"><span data-stu-id="ce635-128">Displays the optional description of the project.</span></span>  
  
 <span data-ttu-id="ce635-129">**Версия проекта**</span><span class="sxs-lookup"><span data-stu-id="ce635-129">**Project Version**</span></span>  
 <span data-ttu-id="ce635-130">Выводит список версий проекта.</span><span class="sxs-lookup"><span data-stu-id="ce635-130">Lists the project version.</span></span>  
  
 <span data-ttu-id="ce635-131">**Дата развертывания**</span><span class="sxs-lookup"><span data-stu-id="ce635-131">**Deployment Date**</span></span>  
 <span data-ttu-id="ce635-132">Отображает дату и время развертывания или повторного развертывания проекта.</span><span class="sxs-lookup"><span data-stu-id="ce635-132">Lists the date and time the project was deployed or redeployed.</span></span>  
  
##  <a name="set-the-options-on-the-permissions-page"></a><a name="permissions"></a> <span data-ttu-id="ce635-133">Задание параметров на странице «Разрешения»</span><span class="sxs-lookup"><span data-stu-id="ce635-133">Set the options on the Permissions page</span></span>  
 <span data-ttu-id="ce635-134">Страница **Разрешения** используется для просмотра и установки явных разрешений для проекта.</span><span class="sxs-lookup"><span data-stu-id="ce635-134">Use the **Permissions** page to view and set explicit permissions for the project.</span></span>  
  
 <span data-ttu-id="ce635-135">Обзор</span><span class="sxs-lookup"><span data-stu-id="ce635-135">Browse</span></span>  
 <span data-ttu-id="ce635-136">Нажмите кнопку **Обзор** для выбора пользователей и ролей, которым необходимо установить разрешения с помощью диалогового окна **Просмотр всех участников** .</span><span class="sxs-lookup"><span data-stu-id="ce635-136">Click **Browse** to select users and roles that you want to set permissions for, by using the **Browse All Principals** dialog box.</span></span>  
  
 <span data-ttu-id="ce635-137">**Название**</span><span class="sxs-lookup"><span data-stu-id="ce635-137">**Name**</span></span>  
 <span data-ttu-id="ce635-138">Выводит список имен пользователя или роли.</span><span class="sxs-lookup"><span data-stu-id="ce635-138">Lists the name of the user or role.</span></span>  
  
 <span data-ttu-id="ce635-139">**Тип**</span><span class="sxs-lookup"><span data-stu-id="ce635-139">**Type**</span></span>  
 <span data-ttu-id="ce635-140">Выводит список типов пользователя или роли.</span><span class="sxs-lookup"><span data-stu-id="ce635-140">Lists the type of user or role.</span></span>  
  
 <span data-ttu-id="ce635-141">**Разрешение**</span><span class="sxs-lookup"><span data-stu-id="ce635-141">**Permission**</span></span>  
 <span data-ttu-id="ce635-142">Выводит список разрешений.</span><span class="sxs-lookup"><span data-stu-id="ce635-142">Lists the permissions.</span></span>  
  
 <span data-ttu-id="ce635-143">**Grantor**</span><span class="sxs-lookup"><span data-stu-id="ce635-143">**Grantor**</span></span>  
 <span data-ttu-id="ce635-144">Выводит список пользователей или ролей, которым предоставляют разрешение.</span><span class="sxs-lookup"><span data-stu-id="ce635-144">Lists the user or role that grants the permission.</span></span>  
  
 <span data-ttu-id="ce635-145">**Право предоставил**</span><span class="sxs-lookup"><span data-stu-id="ce635-145">**Grant**</span></span>  
 <span data-ttu-id="ce635-146">Если выбрано поле **Предоставить** , то будет предоставлено разрешение для выбранного пользователя или роли.</span><span class="sxs-lookup"><span data-stu-id="ce635-146">When **Grant** is selected, the permission is granted for the selected user or role.</span></span>  
  
 <span data-ttu-id="ce635-147">**Запретить**</span><span class="sxs-lookup"><span data-stu-id="ce635-147">**Deny**</span></span>  
 <span data-ttu-id="ce635-148">Если выбрано поле **Запретить** , то разрешение будет запрещено для выбранного пользователя или роли.</span><span class="sxs-lookup"><span data-stu-id="ce635-148">When **Deny** is selected, the permission is denied for the selected user or role.</span></span>  
  
  
