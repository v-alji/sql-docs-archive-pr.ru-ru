---
title: Шаг 4. Проверка учебного пакета, созданного на занятии 2 | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0e8c0a25-8f79-41df-8ed2-f82a74b129cd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c055f80cbe9e6748b82569204e3a2d82e2f437e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655823"
---
# <a name="step-4-testing-the-lesson-2-tutorial-package"></a><span data-ttu-id="e06fb-102">Шаг 4. Проверка учебного пакета, созданного на занятии 2</span><span class="sxs-lookup"><span data-stu-id="e06fb-102">Step 4: Testing the Lesson 2 Tutorial Package</span></span>
  <span data-ttu-id="e06fb-103">Используя настроенный контейнер «цикл по каждому элементу» и диспетчер соединений с неструктурированными файлами, можно в пакете, созданном на занятии 2, поочередно обрабатывать коллекцию из 14 неструктурированных файлов в папке образцов данных.</span><span class="sxs-lookup"><span data-stu-id="e06fb-103">With the Foreach Loop container and the Flat File connection manager now configured, the Lesson 2 package can iterate through the collection of 14 flat files in the Sample Data folder.</span></span> <span data-ttu-id="e06fb-104">Каждый раз при обнаружении имени файла, отвечающего указанным критериям имен файлов, в контейнере «цикл по каждому элементу» это имя подставляется в определенную пользователем переменную.</span><span class="sxs-lookup"><span data-stu-id="e06fb-104">Each time a file name is found that matches the specified file name criteria, the Foreach Loop container populates the user-defined variable with the file name.</span></span> <span data-ttu-id="e06fb-105">В переменной, в свою очередь, обновляется свойство ConnectionString диспетчера соединений с неструктурированными файлами, после чего выполняется соединение с новым неструктурированным файлом.</span><span class="sxs-lookup"><span data-stu-id="e06fb-105">This variable, in turn, updates the ConnectionString property of the Flat File connection manager, and a connection to the new flat file is made.</span></span> <span data-ttu-id="e06fb-106">Затем в контейнере «цикл по каждому элементу» выполняется задача неизмененного потока данных по данным нового неструктурированного файла, после чего устанавливается соединение со следующим файлом в папке.</span><span class="sxs-lookup"><span data-stu-id="e06fb-106">The Foreach Loop container then runs the unmodified data flow task against the data in the new flat file before connecting to the next file in the folder.</span></span>  
  
 <span data-ttu-id="e06fb-107">Для проверки новой функциональности циклов, которая была добавлена в пакет, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="e06fb-107">Use the following procedure to test the new looping functionality that you have added to your package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e06fb-108">Если вы запускали пакет из занятия 1, то перед запуском пакета из этого занятия необходимо удалить записи из dbo.FactCurrency в AdventureWorksDW2012. В противном случае запуск пакета завершится ошибкой, указывающей на нарушение ограничения первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="e06fb-108">If you ran the package from Lesson 1, you will need to delete the records from dbo.FactCurrency in AdventureWorksDW2012 before you run the package from this lesson or the package will fail with errors indicating a Violation of Primary Key constraint.</span></span> <span data-ttu-id="e06fb-109">Те же ошибки возникнут в случае, если вы запустите пакет путем выбора из меню пунктов «Отладка или начать отладку» (или нажатия клавиши F5), так как будут запущены и занятие 1, и занятие 2.</span><span class="sxs-lookup"><span data-stu-id="e06fb-109">You will receive the same errors if you run the package by selecting Debug/Start Debugging (or press F5) because both Lesson 1 and Lesson 2 will run.</span></span> <span data-ttu-id="e06fb-110">Инструкция из занятия 2 попытается вставить записи, которые уже были вставлены в занятии 1.</span><span class="sxs-lookup"><span data-stu-id="e06fb-110">Lesson 2 will attempt to insert records already inserted in Lesson 1.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="e06fb-111">Проверка макета пакета</span><span class="sxs-lookup"><span data-stu-id="e06fb-111">Checking the Package Layout</span></span>  
 <span data-ttu-id="e06fb-112">Прежде чем тестировать пакет, следует убедиться, что поток управления и поток данных пакета, созданного на занятии 2, содержит объекты, показанные на следующих диаграммах.</span><span class="sxs-lookup"><span data-stu-id="e06fb-112">Before you test the package you should verify that the control and data flows in the Lesson 2 package contains the objects shown in the following diagrams.</span></span> <span data-ttu-id="e06fb-113">Поток данных должен быть идентичен потоку данных в занятии 1.</span><span class="sxs-lookup"><span data-stu-id="e06fb-113">The data flow should be identical to the data flow in lesson 1.</span></span>  
  
 <span data-ttu-id="e06fb-114">**Поток управления**</span><span class="sxs-lookup"><span data-stu-id="e06fb-114">**Control Flow**</span></span>  
  
 <span data-ttu-id="e06fb-115">![Поток управления в пакете](../../2014/tutorials/media/task4lesson2control.gif "Поток управления в пакете")</span><span class="sxs-lookup"><span data-stu-id="e06fb-115">![Control flow in package](../../2014/tutorials/media/task4lesson2control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="e06fb-116">**Поток данных**</span><span class="sxs-lookup"><span data-stu-id="e06fb-116">**Data Flow**</span></span>  
  
 <span data-ttu-id="e06fb-117">![Поток данных в пакете](../../2014/tutorials/media/task9lesson1data.gif "Поток данных в пакете")</span><span class="sxs-lookup"><span data-stu-id="e06fb-117">![Data flow in package](../../2014/tutorials/media/task9lesson1data.gif "Data flow in package")</span></span>  
  
### <a name="to-test-the-lesson-2-tutorial-package"></a><span data-ttu-id="e06fb-118">Тестирование пакета учебника занятия 2</span><span class="sxs-lookup"><span data-stu-id="e06fb-118">To test the Lesson 2 tutorial package</span></span>  
  
1.  <span data-ttu-id="e06fb-119">В **обозревателе решений**щелкните правой кнопкой мыши элемент **Lesson 2.dtsx** и выберите команду **Выполнить пакет**.</span><span class="sxs-lookup"><span data-stu-id="e06fb-119">In **Solution Explorer**, right-click **Lesson 2.dtsx** and click **Execute Package**.</span></span>  
  
     <span data-ttu-id="e06fb-120">Будет начато выполнение пакета.</span><span class="sxs-lookup"><span data-stu-id="e06fb-120">The package will run.</span></span> <span data-ttu-id="e06fb-121">Можно проверить состояние каждого цикла в окне вывода или щелкнув вкладку **выполнение** . Например, можно увидеть, что в целевую таблицу были добавлены 1097 строк из файла Currency_VEB.txt.</span><span class="sxs-lookup"><span data-stu-id="e06fb-121">You can verify the status of each loop in the Output window, or by clicking on the **Progress** tab. For example, you can see that 1097 lines were added to the destination table from the file Currency_VEB.txt.</span></span>  
  
2.  <span data-ttu-id="e06fb-122">После окончания работы пакета выберите в меню **Отладка** пункт **Остановить отладку**.</span><span class="sxs-lookup"><span data-stu-id="e06fb-122">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="e06fb-123">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="e06fb-123">Next Lesson</span></span>  
 [<span data-ttu-id="e06fb-124">Урок 5. Добавление конфигураций пакетов в модель развертывания пакета</span><span class="sxs-lookup"><span data-stu-id="e06fb-124">Lesson 5: Adding Package Configurations for the Package Deployment Model</span></span>](../integration-services/lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="e06fb-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="e06fb-125">See Also</span></span>  
 [<span data-ttu-id="e06fb-126">Запуск проектов и пакетов</span><span class="sxs-lookup"><span data-stu-id="e06fb-126">Execution of Projects and Packages</span></span>](packages/run-integration-services-ssis-packages.md)  
  
  
