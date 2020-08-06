---
title: Шаг 9. Проверка учебного пакета, созданного на занятии 1 | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9aee7acf-797b-46f2-830d-80ab64a9f0b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dff1132489c1683430b1003e88f5037664b11983
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664338"
---
# <a name="step-9-testing-the-lesson-1-tutorial-package"></a><span data-ttu-id="5f1b3-102">Шаг 9. Проверка учебного пакета, созданного на занятии 1</span><span class="sxs-lookup"><span data-stu-id="5f1b3-102">Step 9: Testing the Lesson 1 Tutorial Package</span></span>
  <span data-ttu-id="5f1b3-103">На этом занятии были выполнены представленные ниже задачи.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-103">In this lesson, you have done the following tasks:</span></span>  
  
-   <span data-ttu-id="5f1b3-104">Был создан проект служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5f1b3-104">Created a new [!INCLUDE[ssIS](../includes/ssis-md.md)] project.</span></span>  
  
-   <span data-ttu-id="5f1b3-105">Была выполнена настройка диспетчеров соединений, используемых пакетом для подключения к исходным и целевым данным.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-105">Configured the connection managers that the package needs to connect to the source and destination data.</span></span>  
  
-   <span data-ttu-id="5f1b3-106">Был добавлен поток данных, который получает данные от источника «неструктурированный файл», производит необходимые преобразования «Уточняющий запрос» и настраивает данные для назначения.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-106">Added a data flow that takes the data from a flat file source, performs the necessary Lookup transformations on the data, and configures the data for the destination.</span></span>  
  
 <span data-ttu-id="5f1b3-107">Создание пакета завершено.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-107">Your package is now complete!</span></span> <span data-ttu-id="5f1b3-108">Теперь необходимо проверить пакет.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-108">It is time to test your package.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="5f1b3-109">Проверка макета пакета</span><span class="sxs-lookup"><span data-stu-id="5f1b3-109">Checking the Package Layout</span></span>  
 <span data-ttu-id="5f1b3-110">Прежде чем проверить пакет, нужно убедиться в том, что потоки данных и управления в пакете занятия 1 содержат объекты, показанные на следующих диаграммах.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-110">Before you test the package you should verify that the control and data flows in the Lesson 1 package contain the objects shown in the following diagrams.</span></span>  
  
 <span data-ttu-id="5f1b3-111">**Поток управления**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-111">**Control Flow**</span></span>  
  
 <span data-ttu-id="5f1b3-112">![Поток управления в пакете](../../2014/tutorials/media/task9lesson1control.gif "Поток управления в пакете")</span><span class="sxs-lookup"><span data-stu-id="5f1b3-112">![Control flow in package](../../2014/tutorials/media/task9lesson1control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="5f1b3-113">**Поток данных**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-113">**Data Flow**</span></span>  
  
 <span data-ttu-id="5f1b3-114">![Поток данных в пакете](../../2014/tutorials/media/task9lesson1data.gif "Поток данных в пакете")</span><span class="sxs-lookup"><span data-stu-id="5f1b3-114">![Data flow in package](../../2014/tutorials/media/task9lesson1data.gif "Data flow in package")</span></span>  
  
### <a name="to-run-the-lesson-1-tutorial-package"></a><span data-ttu-id="5f1b3-115">Выполнение учебного пакета занятия 1</span><span class="sxs-lookup"><span data-stu-id="5f1b3-115">To run the Lesson 1 tutorial package</span></span>  
  
1.  <span data-ttu-id="5f1b3-116">В меню **Отладка** выберите пункт **Начать отладку**.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-116">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="5f1b3-117">В результате запуска пакета к таблице фактов **FactCurrency** в базе данных **AdventureWorksDW2012**будет добавлено 1097 строк.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-117">The package will run, resulting in 1097 rows successfully added into the **FactCurrency** fact table in **AdventureWorksDW2012**.</span></span>  
  
2.  <span data-ttu-id="5f1b3-118">После окончания работы пакета выберите в меню **Отладка** пункт **Остановить отладку**.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-118">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="5f1b3-119">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="5f1b3-119">Next Lesson</span></span>  
 [<span data-ttu-id="5f1b3-120">Занятие 2. Добавление циклов</span><span class="sxs-lookup"><span data-stu-id="5f1b3-120">Lesson 2: Adding Looping</span></span>](../integration-services/lesson-2-adding-looping-with-ssis.md)  
  
## <a name="see-also"></a><span data-ttu-id="5f1b3-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="5f1b3-121">See Also</span></span>  
 [<span data-ttu-id="5f1b3-122">Запуск проектов и пакетов</span><span class="sxs-lookup"><span data-stu-id="5f1b3-122">Execution of Projects and Packages</span></span>](packages/run-integration-services-ssis-packages.md)  
  
  
