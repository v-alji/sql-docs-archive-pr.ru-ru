---
title: Диалоговое окно "Версии проекта" | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isprojectprop.versions.f1
ms.assetid: a48a387c-2e70-45bc-be2e-26e57a9bb2c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 998dd194c2a056121fd6f7a404e75c7080b85aa1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736680"
---
# <a name="project-versions-dialog-box"></a><span data-ttu-id="fcf06-102">Диалоговое окно «Версии проекта»</span><span class="sxs-lookup"><span data-stu-id="fcf06-102">Project Versions Dialog Box</span></span>
  <span data-ttu-id="fcf06-103">Диалоговое окно **Версии проекта** используется для просмотра версий проекта и восстановления предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="fcf06-103">Use the **Project Versions** dialog box to view versions of a project and to restore a previous version.</span></span>  
  
 <span data-ttu-id="fcf06-104">Можно также просмотреть предыдущие версии в представлении [catalog.object_versions (база данных SSISDB)](/sql/integration-services/system-views/catalog-object-versions-ssisdb-database) и использовать хранимую процедуру [catalog.restore_project (база данных SSISDB)](/sql/integration-services/system-stored-procedures/catalog-restore-project-ssisdb-database) для восстановления предыдущих версий.</span><span class="sxs-lookup"><span data-stu-id="fcf06-104">You can also view previous versions in the [catalog.object_versions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-object-versions-ssisdb-database) view, and use the [catalog.restore_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-restore-project-ssisdb-database) stored procedure to restore previous versions.</span></span>  
  
 <span data-ttu-id="fcf06-105">**Выбор действия**</span><span class="sxs-lookup"><span data-stu-id="fcf06-105">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="fcf06-106">Открытие диалогового окна «Версии проекта»</span><span class="sxs-lookup"><span data-stu-id="fcf06-106">Open the Project Versions dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="fcf06-107">Восстановление версии проекта</span><span class="sxs-lookup"><span data-stu-id="fcf06-107">Restore a Project Version</span></span>](#restore)  
  
##  <a name="open-the-project-versions-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="fcf06-108">Открытие диалогового окна «Версии проекта»</span><span class="sxs-lookup"><span data-stu-id="fcf06-108">Open the Project Versions dialog box</span></span>  
  
1.  <span data-ttu-id="fcf06-109">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]установите соединение с сервером служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fcf06-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="fcf06-110">Другими словами, подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , размещающего базу данных служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fcf06-110">That is, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="fcf06-111">В обозревателе объектов разверните дерево для отображения узла **Каталоги служб Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="fcf06-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="fcf06-112">Для отображения узла **SSISDB** разверните узел **Каталоги служб Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="fcf06-112">Expand the **Integration Services Catalogs** node to display the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="fcf06-113">Узел **SSISDB** содержит одну или несколько папок, в каждой из которых содержится один или несколько проектов.</span><span class="sxs-lookup"><span data-stu-id="fcf06-113">The **SSISDB** node contains one or more folders that each contain one or more projects.</span></span> <span data-ttu-id="fcf06-114">Разверните папку, содержащую интересующий вас проект.</span><span class="sxs-lookup"><span data-stu-id="fcf06-114">Expand the folder that contains the project you are interested in.</span></span>  
  
5.  <span data-ttu-id="fcf06-115">Щелкните правой кнопкой мыши проект и выберите пункт **Версии**.</span><span class="sxs-lookup"><span data-stu-id="fcf06-115">Right-click the project, and then click **Versions**.</span></span>  
  
 <span data-ttu-id="fcf06-116">В диалоговом окне **Версии проекта** в таблице **Версии** отображается список версий проектов, которые развернуты на сервере, с указанием даты и времени развертывания версии и ее восстановления (если таковое имело место), описания версии и ее идентификатора.</span><span class="sxs-lookup"><span data-stu-id="fcf06-116">In the **Project Versions** dialog box, the **Versions** table displays the list of versions of the project that have been deployed on the server, with the date and time the version was deployed, the date and time the version was restored (if it was restored), the version description, and a version identifier.</span></span> <span data-ttu-id="fcf06-117">Активная в настоящее время версия отмечена галочкой в столбце **Текущая** таблицы.</span><span class="sxs-lookup"><span data-stu-id="fcf06-117">The currently active version is indicated with a check mark in the **Current** column of the table.</span></span>  
  
##  <a name="restore-a-project-version"></a><a name="restore"></a> <span data-ttu-id="fcf06-118">Восстановление версии проекта</span><span class="sxs-lookup"><span data-stu-id="fcf06-118">Restore a Project Version</span></span>  
 <span data-ttu-id="fcf06-119">Для восстановления предыдущей версии проекта выберите версию в таблице **Версии** и щелкните **Восстановление до выбранной версии**.</span><span class="sxs-lookup"><span data-stu-id="fcf06-119">To restore a previous version of a project, select the version in the **Versions** table, and then click **Restore to Selected Version**.</span></span> <span data-ttu-id="fcf06-120">Проект восстанавливается до выбранной версии, которая отмечена флажком в столбце **Текущая** таблицы **Версии** .</span><span class="sxs-lookup"><span data-stu-id="fcf06-120">The project is restored to the selected version and that version is indicated with a check mark in the **Current** column of the **Versions** table.</span></span>  
  
  
