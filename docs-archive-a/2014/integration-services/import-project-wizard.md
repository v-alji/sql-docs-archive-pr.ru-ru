---
title: Мастер импорта проектов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.importprojectwizard.f1
ms.assetid: 9247ad6c-4bd1-43ab-b347-583181cb9917
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 81a990995d7e98c21b61f484372d31c9a1773102
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664412"
---
# <a name="import-project-wizard"></a><span data-ttu-id="6804a-102">Мастер импорта проектов</span><span class="sxs-lookup"><span data-stu-id="6804a-102">Import Project Wizard</span></span>
  <span data-ttu-id="6804a-103">Мастер импорта проектов служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] служит для создания нового проекта служб Integration Services на основе существующего проекта.</span><span class="sxs-lookup"><span data-stu-id="6804a-103">Use the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Import Project Wizard create a new Integration Services project based on an existing one.</span></span> <span data-ttu-id="6804a-104">Можно импортировать проекты, уже развернутые в каталоге служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , или проекты из файла развертывания проекта (расширение ISPAC).</span><span class="sxs-lookup"><span data-stu-id="6804a-104">Import projects that have already been deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog or import projects from a project deployment file (.ispac extension).</span></span>  
  
### <a name="to-create-a-project-based-on-a-project-in-ispac-file-or-in-catalog"></a><span data-ttu-id="6804a-105">Создание проекта на основе проекта в файле ISPAC или в каталоге</span><span class="sxs-lookup"><span data-stu-id="6804a-105">To create a project based on a project in .ispac file or in catalog</span></span>  
  
1.  <span data-ttu-id="6804a-106">В меню **файл**выберите пункт **создать**и щелкните проект.</span><span class="sxs-lookup"><span data-stu-id="6804a-106">Click **File**, point to **New**, and click Project.</span></span>  
  
2.  <span data-ttu-id="6804a-107">Разверните узел **Бизнес-аналитика**и выберите **Службы Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="6804a-107">Expand **Business Intelligence**, and click **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="6804a-108">На средней панели выберите **Мастер импорта служб Integration Services** , введите **имя** для решения, проекта, затем введите **папку** для проекта и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6804a-108">Select **Integration Services Import Wizard** in the middle pane, type a **name** for the solution, project, and specify the **folder** for the project, and then click **OK**.</span></span>  
  
     <span data-ttu-id="6804a-109">Должен открыться **Мастер импорта проекта служб Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="6804a-109">You should see the **Integration Services Import Project Wizard**.</span></span> <span data-ttu-id="6804a-110">Мастер создаст новый проект служб Integration Services на основе существующего проекта.</span><span class="sxs-lookup"><span data-stu-id="6804a-110">This wizard creates a new Integration Services project based on an existing one</span></span>  
  
4.  <span data-ttu-id="6804a-111">Нажмите кнопку **Далее** , на странице **Введение** , чтобы перейти на страницу **Выбор источника данных** .</span><span class="sxs-lookup"><span data-stu-id="6804a-111">Click **Next** on the **Introduction** page to see the **Select Source** page.</span></span>  
  
5.  <span data-ttu-id="6804a-112">Укажите, должен ли проект импортироваться из файла ISPAC или из каталога.</span><span class="sxs-lookup"><span data-stu-id="6804a-112">Specify whether you want to import project from an .ispac file or from a catalog.</span></span>  
  
    -   <span data-ttu-id="6804a-113">Если был выбран режим **Файл развертывания проекта** , то укажите путь к файлу ISPAC.</span><span class="sxs-lookup"><span data-stu-id="6804a-113">If you select **Project deployment file** option, specify the path to the .ispac file.</span></span>  
  
    -   <span data-ttu-id="6804a-114">Если был выбран **Каталог служб Integration Services** , то введите имя экземпляра сервера базы данных, в котором содержится каталог, а также путь к проекту в каталоге.</span><span class="sxs-lookup"><span data-stu-id="6804a-114">If you select **Integration Services Catalog** option, specify the name of database server instance on which the catalog exists, and the path to the project in the catalog.</span></span>  
  
6.  <span data-ttu-id="6804a-115">Нажмите кнопку **Далее** , на странице **Выбор источника** , чтобы перейти на страницу **Просмотр** .</span><span class="sxs-lookup"><span data-stu-id="6804a-115">Click **Next** on the **Select Source** page to see the **Review** page.</span></span> <span data-ttu-id="6804a-116">Проверьте отображаемую на странице информацию об операции импорта, которую выполнит мастер.</span><span class="sxs-lookup"><span data-stu-id="6804a-116">Review the information displayed on the page about the import operation the wizard is going to perform.</span></span>  
  
7.  <span data-ttu-id="6804a-117">Нажмите кнопку **Импорт** , чтобы создать новый проект служб Integration Services на основе существующего выбранного проекта.</span><span class="sxs-lookup"><span data-stu-id="6804a-117">Click **Import** to create a new Integration Services project based on the one you selected.</span></span>  
  
8.  <span data-ttu-id="6804a-118">На странице **Результаты** должны быть отображены результаты выполнения операции импорта, выполненной мастером.</span><span class="sxs-lookup"><span data-stu-id="6804a-118">The **Results** page should display the results from import operation the wizard performed.</span></span> <span data-ttu-id="6804a-119">Нажмите кнопку **Сохранить отчет** , чтобы сохранить отчет в XML-файле.</span><span class="sxs-lookup"><span data-stu-id="6804a-119">Click **Save Report** to save the report to an XML file.</span></span>  
  
9. <span data-ttu-id="6804a-120">Нажмите кнопку **Закрыть**, чтобы завершить работу мастера.</span><span class="sxs-lookup"><span data-stu-id="6804a-120">Click **Close** to close the wizard.</span></span>  
  
  
