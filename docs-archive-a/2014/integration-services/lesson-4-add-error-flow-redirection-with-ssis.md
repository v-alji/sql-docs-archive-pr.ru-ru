---
title: Занятие 4. Добавление перенаправления потока ошибок | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0c8dbda2-75e3-4278-9b4e-dcd220c92522
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5b1d1ff9abf59a6288d1b693fce5a6fb707a129b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750020"
---
# <a name="lesson-4-adding-error-flow-redirection"></a><span data-ttu-id="7a360-102">Урок 4. Добавление перенаправления потока ошибок</span><span class="sxs-lookup"><span data-stu-id="7a360-102">Lesson 4: Adding Error Flow Redirection</span></span>
  <span data-ttu-id="7a360-103">Для обработки ошибок, которые могут возникнуть в процессе преобразования, [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] дает возможность выбрать для каждого компонента и каждого столбца, как обрабатывать данные, которые не могут быть преобразованы.</span><span class="sxs-lookup"><span data-stu-id="7a360-103">To handle errors that may occur in the transformation process, [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] gives you the ability to decide on a per component and per column basis how to handle data that cannot be transformed.</span></span> <span data-ttu-id="7a360-104">Можно проигнорировать ошибки в определенных столбцах, перенаправить всю строку с ошибкой или просто завершить работу компонента с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="7a360-104">You can choose to ignore a failure in certain columns, redirect the entire failed row, or just fail the component.</span></span> <span data-ttu-id="7a360-105">По умолчанию для всех компонентов в службах [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] указано завершение работы при возникновении ошибки.</span><span class="sxs-lookup"><span data-stu-id="7a360-105">By default, all components in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] are configured to fail when errors occur.</span></span> <span data-ttu-id="7a360-106">Завершение работы компонента с ошибкой, в свою очередь, приводит к сбою в работе пакета и остановке дальнейшей обработки.</span><span class="sxs-lookup"><span data-stu-id="7a360-106">Failing a component, in turn, causes the package to fail and all subsequent processing to stop.</span></span>  
  
 <span data-ttu-id="7a360-107">Рекомендуется вместо прекращения выполнения пакетов при возникновении ошибок обрабатывать потенциальные ошибки обработки при их возникновении в ходе преобразования.</span><span class="sxs-lookup"><span data-stu-id="7a360-107">Instead of letting failures stop package execution, it is good practice to configure and handle potential processing errors as they occur within the transformation.</span></span> <span data-ttu-id="7a360-108">Хотя ошибки можно игнорировать, чтобы не прекращать выполнение пакета, зачастую лучше перенаправить строку с ошибкой по другому пути обработки, где данные вместе с ошибкой могут быть сохранены, а впоследствии проверены и повторно обработаны.</span><span class="sxs-lookup"><span data-stu-id="7a360-108">While you might choose to ignore failures to ensure your package runs successfully, it is often better to redirect the failed row to another processing path where the data and the error can be persisted, examined and reprocessed at a later time.</span></span>  
  
 <span data-ttu-id="7a360-109">На этом занятии предстоит создать копию пакета, разработанного на [Lesson 3: Adding Logging](lesson-3-add-logging-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="7a360-109">In this lesson, you will create a copy of the package that you developed in [Lesson 3: Adding Logging](lesson-3-add-logging-with-ssis.md).</span></span> <span data-ttu-id="7a360-110">При работе с этим новым пакетом будет создана поврежденная версия одного из файлов образцов данных.</span><span class="sxs-lookup"><span data-stu-id="7a360-110">Working with this new package, you will create a corrupted version of one of the sample data files.</span></span> <span data-ttu-id="7a360-111">Повреждение файла приведет к возникновению ошибки обработки при выполнении пакета.</span><span class="sxs-lookup"><span data-stu-id="7a360-111">The corrupted file will force a processing error to occur when you run the package.</span></span>  
  
 <span data-ttu-id="7a360-112">Чтобы обработать данные об ошибке, будет добавлено и настроено назначение «Неструктурированный файл», которое будет записывать все строки, которым не удалось расположить в файле искомое значение преобразование «Уточняющий запрос ключа валюты».</span><span class="sxs-lookup"><span data-stu-id="7a360-112">To handle the error data, you will add and configure a Flat File destination that will write any rows that fail to locate a lookup value in the Lookup Currency Key transformation to a file.</span></span>  
  
 <span data-ttu-id="7a360-113">Прежде чем данные об ошибке будут записаны в файл, следует включить компонент скрипта, который использует скрипт для получения описания ошибки.</span><span class="sxs-lookup"><span data-stu-id="7a360-113">Before the error data is written to the file, you will include a Script component that uses script to get error descriptions.</span></span> <span data-ttu-id="7a360-114">Затем следует перенастроить преобразование «Уточняющий запрос ключа валюты» таким образом, чтобы перенаправлять все данные, обработка которых невозможна, в преобразование «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="7a360-114">You will then reconfigure the Lookup Currency Key transformation to redirect any data that could not be processed to the Script transformation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7a360-115">Для выполнения упражнений этого учебника потребуется образец базы данных **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="7a360-115">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="7a360-116">Дополнительные сведения об установке и развертывании **AdventureWorksDW2012**см. в разделе [Проект образцов продуктов службы Reporting Services на сайте CodePlex](https://go.microsoft.com/fwlink/p/?LinkId=526910).</span><span class="sxs-lookup"><span data-stu-id="7a360-116">For more information about how to install and deploy **AdventureWorksDW2012**, see [Reporting Services Product Samples Project on CodePlex](https://go.microsoft.com/fwlink/p/?LinkId=526910).</span></span>  
  
## <a name="tasks-in-lesson"></a><span data-ttu-id="7a360-117">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="7a360-117">Tasks in Lesson</span></span>  
 <span data-ttu-id="7a360-118">Это занятие содержит следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="7a360-118">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="7a360-119">Шаг 1. Копирование пакета занятия 3</span><span class="sxs-lookup"><span data-stu-id="7a360-119">Step 1: Copying the Lesson 3 Package</span></span>](lesson-4-1-copying-the-lesson-3-package.md)  
  
-   [<span data-ttu-id="7a360-120">Этап 2. Создание поврежденного файла</span><span class="sxs-lookup"><span data-stu-id="7a360-120">Step 2: Creating a Corrupted File</span></span>](lesson-4-2-creating-a-corrupted-file.md)  
  
-   [<span data-ttu-id="7a360-121">Шаг 3. Добавление перенаправления потока ошибок</span><span class="sxs-lookup"><span data-stu-id="7a360-121">Step 3: Adding Error Flow Redirection</span></span>](lesson-4-3-adding-error-flow-redirection.md)  
  
-   [<span data-ttu-id="7a360-122">Шаг 4. Добавление назначения «Неструктурированный файл»</span><span class="sxs-lookup"><span data-stu-id="7a360-122">Step 4: Adding a Flat File Destination</span></span>](lesson-4-4-adding-a-flat-file-destination.md)  
  
-   [<span data-ttu-id="7a360-123">Шаг 5. Проверка учебного пакета, созданного на занятии 4</span><span class="sxs-lookup"><span data-stu-id="7a360-123">Step 5: Testing the Lesson 4 Tutorial Package</span></span>](lesson-4-5-testing-the-lesson-4-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="7a360-124">Начало занятия</span><span class="sxs-lookup"><span data-stu-id="7a360-124">Start the Lesson</span></span>  
 [<span data-ttu-id="7a360-125">Шаг 1. Копирование пакета занятия 3</span><span class="sxs-lookup"><span data-stu-id="7a360-125">Step 1: Copying the Lesson 3 Package</span></span>](lesson-4-1-copying-the-lesson-3-package.md)  
  
  
