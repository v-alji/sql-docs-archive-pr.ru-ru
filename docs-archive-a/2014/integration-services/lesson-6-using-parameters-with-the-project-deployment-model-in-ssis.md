---
title: Занятие 6. Использование параметров в модели развертывания проекта | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9216f18c-1762-4f2d-8c22-bd0ab7107555
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4bdc6b9dfc019822d6cf1bd9ec7d89ffcc5ea5e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657146"
---
# <a name="lesson-6-using-parameters-with-the-project-deployment-model"></a><span data-ttu-id="a5ab5-102">Занятие 6: Использование параметров в модели развертывания проекта</span><span class="sxs-lookup"><span data-stu-id="a5ab5-102">Lesson 6: Using Parameters with the Project Deployment Model</span></span>
  <span data-ttu-id="a5ab5-103">В SQL Server 2012 была добавлена новая модель развертывания, позволяющая развертывать проекты на сервере служб Integration Services.</span><span class="sxs-lookup"><span data-stu-id="a5ab5-103">SQL Server 2012 introduces a new deployment model where you can deploy your projects to the Integration Services server.</span></span> <span data-ttu-id="a5ab5-104">Сервер служб Integration Services позволяет управлять пакетами, запускать пакеты, а также настраивать значения времени выполнения для пакетов.</span><span class="sxs-lookup"><span data-stu-id="a5ab5-104">The Integration Services server enables you to manage and run packages, and to configure runtime values for packages.</span></span>  
  
 <span data-ttu-id="a5ab5-105">На этом занятии будет изменен пакет, созданный на [занятии 5. Добавление конфигураций пакетов для модели развертывания пакетов](lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md) для использования модели развертывания проекта.</span><span class="sxs-lookup"><span data-stu-id="a5ab5-105">In this lesson, you will modify the package that you created in [Lesson 5: Adding Package Configurations for the Package Deployment Model](lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md) to use the Project Deployment Model.</span></span> <span data-ttu-id="a5ab5-106">Значение конфигурации будет заменено на параметр, чтобы указать местоположение образцов данных.</span><span class="sxs-lookup"><span data-stu-id="a5ab5-106">You replace the configuration value with a parameter to specify the sample data location.</span></span> <span data-ttu-id="a5ab5-107">Также можно скопировать пакет завершенного урока 5, который включен в учебник.</span><span class="sxs-lookup"><span data-stu-id="a5ab5-107">You can also copy the completed Lesson 5 package that is included with the tutorial.</span></span>  
  
 <span data-ttu-id="a5ab5-108">С использованием мастера настройки проекта служб Integration Services будет выполнено преобразование проекта для использования модели развертывания проектов, а также использования параметра, а не значения конфигурации для задания свойства каталога.</span><span class="sxs-lookup"><span data-stu-id="a5ab5-108">Using the Integration Services Project Configuration Wizard, you will convert the project to the Project Deployment Model and use a Parameter rather than a configuration value to set the Directory property.</span></span> <span data-ttu-id="a5ab5-109">На этом занятии частично рассматриваются шаги, необходимые для преобразования существующих пакетов служб SSIS в новую модель развертывания проекта.</span><span class="sxs-lookup"><span data-stu-id="a5ab5-109">This lesson partially covers the steps you would follow to convert existing SSIS packages to the new Project Deployment Model.</span></span>  
  
 <span data-ttu-id="a5ab5-110">При повторном выполнении пакета служба Integration Services использует параметр для заполнения значения переменной, а переменная в свою очередь обновит свойство "Каталог".</span><span class="sxs-lookup"><span data-stu-id="a5ab5-110">When you run the package again, the Integration Services service uses the parameter to populate the value of the variable, and the variable in turn updates the Directory property.</span></span> <span data-ttu-id="a5ab5-111">В итоге пакет последовательно проходит все файлы в новой папке данных, определенной значением параметра, а не в папке, заданной в файле конфигурации пакета.</span><span class="sxs-lookup"><span data-stu-id="a5ab5-111">As a result, the package iterates through the files in the new data folder specified by the parameter value rather than the folder that was set in the package configuration file.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a5ab5-112">Для выполнения упражнений этого учебника потребуется образец базы данных **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="a5ab5-112">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="a5ab5-113">Дополнительные сведения об установке и развертывании образца базы данных **AdventureWorksDW2012**см. в разделе [Вопросы установки образцов кода и образцов баз данных SQL Server](https://technet.microsoft.com/library/ms161556%28v=sql.105%29).</span><span class="sxs-lookup"><span data-stu-id="a5ab5-113">For more information about how to install and deploy **AdventureWorksDW2012**, see [Considerations for Installing SQL Server Samples and Sample Databases](https://technet.microsoft.com/library/ms161556%28v=sql.105%29).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="a5ab5-114">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="a5ab5-114">Lesson Tasks</span></span>  
 <span data-ttu-id="a5ab5-115">Это занятие содержит следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="a5ab5-115">This lesson contains the following tasks:</span></span>  
  
1.  [<span data-ttu-id="a5ab5-116">Шаг 1. Копирование пакета занятия 5</span><span class="sxs-lookup"><span data-stu-id="a5ab5-116">Step 1: Copying the Lesson 5 Package</span></span>](lesson-6-1-copying-the-lesson-5-package.md)  
  
2.  [<span data-ttu-id="a5ab5-117">Этап 2. Преобразование проекта в модель развертывания проекта</span><span class="sxs-lookup"><span data-stu-id="a5ab5-117">Step 2: Converting the Project to the Project Deployment Model</span></span>](lesson-6-2-converting-the-project-to-the-project-deployment-model.md)  
  
3.  [<span data-ttu-id="a5ab5-118">Шаг 3. Проверка пакета, созданного на занятии 6</span><span class="sxs-lookup"><span data-stu-id="a5ab5-118">Step 3: Testing the Lesson 6 Package</span></span>](lesson-6-3-testing-the-lesson-6-package.md)  
  
4.  [<span data-ttu-id="a5ab5-119">Шаг 4. Развертывание пакета, созданного на занятии 6</span><span class="sxs-lookup"><span data-stu-id="a5ab5-119">Step 4: Deploying the Lesson 6 Package</span></span>](lesson-6-4-deploying-the-lesson-6-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="a5ab5-120">Начало занятия</span><span class="sxs-lookup"><span data-stu-id="a5ab5-120">Start the Lesson</span></span>  
 [<span data-ttu-id="a5ab5-121">Шаг 1. Копирование пакета занятия 5</span><span class="sxs-lookup"><span data-stu-id="a5ab5-121">Step 1: Copying the Lesson 5 Package</span></span>](lesson-6-1-copying-the-lesson-5-package.md)  
  
  
