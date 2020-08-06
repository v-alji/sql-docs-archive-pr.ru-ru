---
title: Шаг 4. Проверка учебного пакета, созданного на занятии 5 | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5215b77d-c2ec-4b25-a3de-ca49ea197d74
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 76e4692de4daa9ddd6ed0e418bed5cda74ec7650
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657148"
---
# <a name="step-4-testing-the-lesson-5-tutorial-package"></a><span data-ttu-id="f5ba8-102">Шаг 4. Проверка учебного пакета, созданного на занятии 5</span><span class="sxs-lookup"><span data-stu-id="f5ba8-102">Step 4: Testing the Lesson 5 Tutorial Package</span></span>
  <span data-ttu-id="f5ba8-103">В ходе выполнения пакету будет присвоено значение свойства `Directory` из переменной, обновленной во время выполнения, а не имя исходного каталога, которое было указано при создании пакета.</span><span class="sxs-lookup"><span data-stu-id="f5ba8-103">At run time, your package will obtain the value for the `Directory` property from a variable updated at run time, rather than using the original directory name that you specified when you created the package.</span></span> <span data-ttu-id="f5ba8-104">Значение этой переменной заполняется из файла SSISTutorial.dtsConfig.</span><span class="sxs-lookup"><span data-stu-id="f5ba8-104">The value of the variable is populated by the SSISTutorial.dtsConfig file.</span></span>  
  
 <span data-ttu-id="f5ba8-105">Чтобы убедиться, что пакет обновляет свойство Directory новым значением во время выполнения, выполните пакет.</span><span class="sxs-lookup"><span data-stu-id="f5ba8-105">To verify that the package updates the Directory property with the new value during run time, simply execute the package.</span></span> <span data-ttu-id="f5ba8-106">Поскольку в новый каталог были скопированы только три файла образцов данных, поток данных будет запущен только три раза, а не 14 раз в соответствии с количеством файлов в исходном каталоге.</span><span class="sxs-lookup"><span data-stu-id="f5ba8-106">Because only three sample data files were copied to the new directory, the data flow will run only three times, rather than iterate through the 14 files in the original folder.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="f5ba8-107">Проверка макета пакета</span><span class="sxs-lookup"><span data-stu-id="f5ba8-107">Checking the Package Layout</span></span>  
 <span data-ttu-id="f5ba8-108">Прежде чем тестировать пакет, следует убедиться, что поток управления и поток данных пакета, созданного на занятии 5, содержит объекты, показанные на следующих диаграммах.</span><span class="sxs-lookup"><span data-stu-id="f5ba8-108">Before you test the package you should verify that the control and data flows in the Lesson 5 package contains the objects shown in the following diagrams.</span></span> <span data-ttu-id="f5ba8-109">Поток управления должен быть таким же, как и поток управления в занятии 4.</span><span class="sxs-lookup"><span data-stu-id="f5ba8-109">The control flow should be identical to the control flow in lesson 4.</span></span> <span data-ttu-id="f5ba8-110">Поток данных должен быть идентичен потоку данных в занятии 4.</span><span class="sxs-lookup"><span data-stu-id="f5ba8-110">The data flow should be identical to the data flow in lessons 4.</span></span>  
  
 <span data-ttu-id="f5ba8-111">**Поток управления**</span><span class="sxs-lookup"><span data-stu-id="f5ba8-111">**Control Flow**</span></span>  
  
 <span data-ttu-id="f5ba8-112">![Поток управления в пакете](../../2014/tutorials/media/task4lesson2control.gif "Поток управления в пакете")</span><span class="sxs-lookup"><span data-stu-id="f5ba8-112">![Control flow in package](../../2014/tutorials/media/task4lesson2control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="f5ba8-113">**Поток данных**</span><span class="sxs-lookup"><span data-stu-id="f5ba8-113">**Data Flow**</span></span>  
  
 <span data-ttu-id="f5ba8-114">![Поток данных в пакете](../../2014/tutorials/media/task9lesson1data.gif "Поток данных в пакете")</span><span class="sxs-lookup"><span data-stu-id="f5ba8-114">![Data flow in package](../../2014/tutorials/media/task9lesson1data.gif "Data flow in package")</span></span>  
  
### <a name="to-test-the-lesson-5-tutorial-package"></a><span data-ttu-id="f5ba8-115">Проверка пакета занятия 5 учебника</span><span class="sxs-lookup"><span data-stu-id="f5ba8-115">To test the Lesson 5 tutorial package</span></span>  
  
1.  <span data-ttu-id="f5ba8-116">В меню **Отладка** выберите пункт **Начать отладку**.</span><span class="sxs-lookup"><span data-stu-id="f5ba8-116">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
2.  <span data-ttu-id="f5ba8-117">После завершения выполнения пакета в меню **Отладка** выберите команду **завершить отладку**.</span><span class="sxs-lookup"><span data-stu-id="f5ba8-117">After the package has completed running, on the **Debug** menu, and then click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="f5ba8-118">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="f5ba8-118">Next Lesson</span></span>  
 [<span data-ttu-id="f5ba8-119">Занятие 6: Использование параметров в модели развертывания проекта</span><span class="sxs-lookup"><span data-stu-id="f5ba8-119">Lesson 6: Using Parameters with the Project Deployment Model</span></span>](../integration-services/lesson-6-using-parameters-with-the-project-deployment-model-in-ssis.md)  
  
  
