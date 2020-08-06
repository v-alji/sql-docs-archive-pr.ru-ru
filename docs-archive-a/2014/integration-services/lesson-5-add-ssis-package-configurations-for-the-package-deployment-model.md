---
title: Занятие 5. Добавление конфигураций пакетов для модели развертывания пакетов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1c10dd54-67cb-4b63-9e4d-aa6ff0452ecb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ee03d624ac7144cf6aef0829bcb7835fe5af9c53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729625"
---
# <a name="lesson-5-adding-package-configurations-for-the-package-deployment-model"></a><span data-ttu-id="a9648-102">Урок 5. Добавление конфигураций пакетов в модель развертывания пакета</span><span class="sxs-lookup"><span data-stu-id="a9648-102">Lesson 5: Adding Package Configurations for the Package Deployment Model</span></span>
  <span data-ttu-id="a9648-103">С помощью конфигураций пакета можно задавать исполняемые свойства и переменные вне среды разработки.</span><span class="sxs-lookup"><span data-stu-id="a9648-103">Package configurations let you set run-time properties and variables from outside of the development environment.</span></span> <span data-ttu-id="a9648-104">Конфигурации дают возможность разрабатывать пакеты, обладающие гибкостью и простотой распространения и развертывания.</span><span class="sxs-lookup"><span data-stu-id="a9648-104">Configurations allow you to develop packages that are flexible and easy to both deploy and distribute.</span></span> <span data-ttu-id="a9648-105">В [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] предусмотрены следующие типы конфигурации:</span><span class="sxs-lookup"><span data-stu-id="a9648-105">[!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] offers the following configuration types:</span></span>  
  
-   <span data-ttu-id="a9648-106">XML-файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="a9648-106">XML configuration file</span></span>  
  
-   <span data-ttu-id="a9648-107">Переменная среды</span><span class="sxs-lookup"><span data-stu-id="a9648-107">Environment variable</span></span>  
  
-   <span data-ttu-id="a9648-108">Параметр реестра</span><span class="sxs-lookup"><span data-stu-id="a9648-108">Registry entry</span></span>  
  
-   <span data-ttu-id="a9648-109">Переменная родительского пакета</span><span class="sxs-lookup"><span data-stu-id="a9648-109">Parent package variable</span></span>  
  
-   <span data-ttu-id="a9648-110">Таблица [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9648-110">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table</span></span>  
  
 <span data-ttu-id="a9648-111">На этом занятии требуется изменить простой пакет [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], созданный на [Уроке 4. Добавление перенаправления потока ошибок](lesson-4-add-error-flow-redirection-with-ssis.md), чтобы использовать модель развертывания пакетов и воспользоваться преимуществами конфигураций пакетов.</span><span class="sxs-lookup"><span data-stu-id="a9648-111">In this lesson, you will modify the simple [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that you created in [Lesson 4: Adding Error Flow Redirection](lesson-4-add-error-flow-redirection-with-ssis.md) to use the Package Deployment Model and take advantage of package configurations.</span></span> <span data-ttu-id="a9648-112">Также можно скопировать пакет из завершенного урока 4, который включен в учебник.</span><span class="sxs-lookup"><span data-stu-id="a9648-112">You can also copy the completed Lesson 4 package that is included with the tutorial.</span></span> <span data-ttu-id="a9648-113">В мастере настройки пакета предстоит создать XML-конфигурацию, которая обновляет свойство `Directory` контейнера «цикл по каждому элементу» с помощью переменной уровня пакета, сопоставленной свойству «Каталог».</span><span class="sxs-lookup"><span data-stu-id="a9648-113">Using the Package Configuration Wizard, you will create an XML configuration that updates the `Directory` property of the Foreach Loop container by using a package-level variable mapped to the Directory property.</span></span> <span data-ttu-id="a9648-114">После создания файла конфигурации следует изменить значение переменной вне среды разработки и создать в измененном свойстве ссылку на новую папку с образцами данных.</span><span class="sxs-lookup"><span data-stu-id="a9648-114">Once you have created the configuration file, you will modify the value of the variable from outside of the development environment and point the modified property to a new sample data folder.</span></span> <span data-ttu-id="a9648-115">При повторном запуске пакета файл конфигурации заполняет значение переменной, а переменная в свою очередь обновляет `Directory` свойство.</span><span class="sxs-lookup"><span data-stu-id="a9648-115">When you run the package again, the configuration file populates the value of the variable, and the variable in turn updates the `Directory` property.</span></span> <span data-ttu-id="a9648-116">В итоге пакет последовательно проходит все файлы в новой, а не исходной папке данных, жестко закодированной в пакете.</span><span class="sxs-lookup"><span data-stu-id="a9648-116">As a result, the package iterates through the files in the new data folder, rather than iterating through the files in the original folder that was hard-coded in the package.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a9648-117">Для выполнения упражнений этого учебника потребуется образец базы данных **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="a9648-117">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="a9648-118">Дополнительные сведения об установке и развертывании **AdventureWorksDW2012**см. в разделе [Проект образцов продуктов службы Reporting Services на сайте CodePlex](https://go.microsoft.com/fwlink/?LinkID=526910).</span><span class="sxs-lookup"><span data-stu-id="a9648-118">For more information about how to install and deploy **AdventureWorksDW2012**, see [Reporting Services Product Samples on CodePlex](https://go.microsoft.com/fwlink/?LinkID=526910).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="a9648-119">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="a9648-119">Lesson Tasks</span></span>  
 <span data-ttu-id="a9648-120">Это занятие содержит следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="a9648-120">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="a9648-121">Шаг 1. Копирование пакета занятия 4</span><span class="sxs-lookup"><span data-stu-id="a9648-121">Step 1: Copying the Lesson 4 Package</span></span>](lesson-5-1-copying-the-lesson-4-package.md)  
  
-   [<span data-ttu-id="a9648-122">Шаг 2. Активация и настройка конфигурации пакетов</span><span class="sxs-lookup"><span data-stu-id="a9648-122">Step 2: Enabling and Configuring Package Configurations</span></span>](lesson-5-2-enabling-and-configuring-package-configurations.md)  
  
-   [<span data-ttu-id="a9648-123">Шаг 3. Изменение значения конфигурации свойства Directory</span><span class="sxs-lookup"><span data-stu-id="a9648-123">Step 3: Modifying the Directory Property Configuration Value</span></span>](lesson-5-3-modifying-the-directory-property-configuration-value.md)  
  
-   [<span data-ttu-id="a9648-124">Шаг 4. Проверка учебного пакета, созданного на занятии 5</span><span class="sxs-lookup"><span data-stu-id="a9648-124">Step 4: Testing the Lesson 5 Tutorial Package</span></span>](lesson-5-4-testing-the-lesson-5-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="a9648-125">Начало занятия</span><span class="sxs-lookup"><span data-stu-id="a9648-125">Start the Lesson</span></span>  
  
-   [<span data-ttu-id="a9648-126">Шаг 1. Копирование пакета занятия 4</span><span class="sxs-lookup"><span data-stu-id="a9648-126">Step 1: Copying the Lesson 4 Package</span></span>](lesson-5-1-copying-the-lesson-4-package.md)  
  
  
