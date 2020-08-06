---
title: Шаг 1. Создание нового проекта служб Integration Services | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f14521b5-941e-443b-8f5e-385f98e37fbf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d6d16d7febcdecb01eb7a93167c2a18d225a9c2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664365"
---
# <a name="step-1-creating-a-new-integration-services-project"></a><span data-ttu-id="e294d-102">Шаг 1. Создание нового проекта служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="e294d-102">Step 1: Creating a New Integration Services Project</span></span>
  <span data-ttu-id="e294d-103">Первым шагом создания пакета в службах [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] будет создание проекта служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e294d-103">The first step in creating a package in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is to create an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="e294d-104">Этот проект содержит шаблоны для объектов (источников данных, представлений источников данных и пакетов), которые используются в решении преобразования данных.</span><span class="sxs-lookup"><span data-stu-id="e294d-104">This project includes the templates for the objects - data sources, data source views, and packages - that you use in a data transformation solution.</span></span>  
  
 <span data-ttu-id="e294d-105">Пакеты, которые будут создаваться в этом учебнике по службам [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , преобразуют значения, зависящие от локаля и региональных стандартов.</span><span class="sxs-lookup"><span data-stu-id="e294d-105">The packages that you will create in this [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] tutorial interpret the values of locale-sensitive data.</span></span> <span data-ttu-id="e294d-106">Если компьютер не настроен на использование регионального параметра «Английский (США)», необходимо установить дополнительные свойства в пакете.</span><span class="sxs-lookup"><span data-stu-id="e294d-106">If your computer is not configured to use the regional option English (United States), you need to set additional properties in the package.</span></span> <span data-ttu-id="e294d-107">Пакеты, использовавшиеся на занятиях 2–5, скопированы из пакета, созданного на занятии 1, поэтому в скопированных пакетах не обязательно обновлять свойства, зависящие от языка и региональных стандартов.</span><span class="sxs-lookup"><span data-stu-id="e294d-107">The packages that you use in lessons 2 through 5 are copied from the package created in lesson 1, and you need not update locale-sensitive properties in the copied packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e294d-108">Для выполнения упражнений этого учебника требуется Microsoft SQL Server Data Tools.</span><span class="sxs-lookup"><span data-stu-id="e294d-108">This tutorial requires Microsoft SQL Server Data Tools.</span></span>  
>   
>  <span data-ttu-id="e294d-109">Дополнительные сведения об установке SQL Server Data Tools см. в разделе [Загрузка SQL Server Data Tools](https://msdn.microsoft.com/data/hh297027).</span><span class="sxs-lookup"><span data-stu-id="e294d-109">For more information on installing the SQL Server Data Tools see [SQL Server Data Tools Download](https://msdn.microsoft.com/data/hh297027).</span></span>  
  
### <a name="to-create-a-new-integration-services-project"></a><span data-ttu-id="e294d-110">Создание нового проекта служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="e294d-110">To create a new Integration Services project</span></span>  
  
1.  <span data-ttu-id="e294d-111">В меню **Пуск** последовательно укажите пункты **Все программы**, **Microsoft SQL Server**и выберите **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="e294d-111">On the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server**, and click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="e294d-112">В меню **Файл** укажите **Создать**и выберите пункт **Проект** , чтобы создать новый проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e294d-112">On the **File** menu, point to **New**, and click **Project** to create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
3.  <span data-ttu-id="e294d-113">В диалоговом окне **Создать проект** разверните узел **Бизнес-аналитика** в категории **Установленные шаблоны**и выберите **Проект служб Integration Services** на панели **Шаблоны** .</span><span class="sxs-lookup"><span data-stu-id="e294d-113">In the **New Project** dialog box, expand the **Business Intelligence** node under **Installed Templates**, and select **Integration Services Project** in the **Templates** pane.</span></span>  
  
4.  <span data-ttu-id="e294d-114">В поле **Имя** измените заданное по умолчанию имя на **Учебник по службам SQL Server Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="e294d-114">In the **Name** box, change the default name to **SSIS Tutorial**.</span></span> <span data-ttu-id="e294d-115">При необходимости снимите флажок **Создать каталог для решения** .</span><span class="sxs-lookup"><span data-stu-id="e294d-115">Optionally, clear the **Create directory for solution** check box.</span></span>  
  
5.  <span data-ttu-id="e294d-116">Согласитесь с местоположением по умолчанию или нажмите кнопку **Обзор** , чтобы найти нужную папку.</span><span class="sxs-lookup"><span data-stu-id="e294d-116">Accept the default location, or click **Browse** to browse to locate the folder you want to use.</span></span> <span data-ttu-id="e294d-117">В диалоговом окне **Расположение проекта** щелкните папку и нажмите кнопку **Выбрать папку**.</span><span class="sxs-lookup"><span data-stu-id="e294d-117">In the **Project Location** dialog box, click the folder and click **Select Folder**.</span></span>  
  
6.  <span data-ttu-id="e294d-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e294d-118">Click **OK**.</span></span>  
  
     <span data-ttu-id="e294d-119">По умолчанию будет создан пустой пакет с именем **Package.dtsx**и добавлен к проекту в узле «Пакеты служб SSIS».</span><span class="sxs-lookup"><span data-stu-id="e294d-119">By default, an empty package, titled **Package.dtsx**, will be created and added to your project under SSIS Packages.</span></span>  
  
7.  <span data-ttu-id="e294d-120">На панели инструментов **обозревателя решений** щелкните правой кнопкой мыши файл **Package.dtsx**, выберите команду **Переименовать**и переименуйте пакет по умолчанию в **Урок 1.dtsx**.</span><span class="sxs-lookup"><span data-stu-id="e294d-120">In **Solution Explorer** toolbar, right-click **Package.dtsx**, click **Rename**, and rename the default package to **Lesson 1.dtsx**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="e294d-121">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="e294d-121">Next Task in Lesson</span></span>  
 [<span data-ttu-id="e294d-122">Шаг 2. Добавление и настройка диспетчера соединений с неструктурированными файлами</span><span class="sxs-lookup"><span data-stu-id="e294d-122">Step 2: Adding and Configuring a Flat File Connection Manager</span></span>](lesson-1-2-adding-and-configuring-a-flat-file-connection-manager.md)  
  
  
