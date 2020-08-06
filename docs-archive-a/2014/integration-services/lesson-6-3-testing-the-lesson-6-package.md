---
title: Шаг 3. Проверка пакета, созданного на занятии 6 | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c184c92d-948f-4037-a502-5fabd909c84c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3c7ab82e9b04fe0752252102374f745e311d830d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736560"
---
# <a name="step-3-testing-the-lesson-6-package"></a><span data-ttu-id="5f0cc-102">Шаг 3. Проверка пакета, созданного на занятии 6</span><span class="sxs-lookup"><span data-stu-id="5f0cc-102">Step 3: Testing the Lesson 6 Package</span></span>
  <span data-ttu-id="5f0cc-103">Во время выполнения пакет получит значение для свойства Directory из параметра VarFolderName.</span><span class="sxs-lookup"><span data-stu-id="5f0cc-103">At run time, your package will obtain the value for the Directory property from the VarFolderName parameter.</span></span>  
  
 <span data-ttu-id="5f0cc-104">Чтобы убедиться, что пакет обновляет свойство Directory новым значением во время выполнения, выполните пакет.</span><span class="sxs-lookup"><span data-stu-id="5f0cc-104">To verify that the package updates the Directory property with the new value during run time, simply execute the package.</span></span> <span data-ttu-id="5f0cc-105">Поскольку в новый каталог были скопированы только три файла образцов данных, поток данных будет запущен только три раза, а не 14 раз в соответствии с количеством файлов в исходном каталоге.</span><span class="sxs-lookup"><span data-stu-id="5f0cc-105">Because only three sample data files were copied to the new directory, the data flow will run only three times, rather than iterate through the 14 files in the original folder.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="5f0cc-106">Проверка макета пакета</span><span class="sxs-lookup"><span data-stu-id="5f0cc-106">Checking the Package Layout</span></span>  
 <span data-ttu-id="5f0cc-107">Прежде чем тестировать пакет, следует убедиться, что поток управления и поток данных пакета, созданного на занятии 6, содержит объекты, показанные на следующих диаграммах.</span><span class="sxs-lookup"><span data-stu-id="5f0cc-107">Before you test the package you should verify that the control and data flows in the Lesson 6 package contains the objects shown in the following diagrams.</span></span> <span data-ttu-id="5f0cc-108">Поток управления должен быть таким же, как и поток управления в занятии 5.</span><span class="sxs-lookup"><span data-stu-id="5f0cc-108">The control flow should be identical to the control flow in lesson 5.</span></span> <span data-ttu-id="5f0cc-109">Поток данных должен быть идентичен потоку данных в занятии 5.</span><span class="sxs-lookup"><span data-stu-id="5f0cc-109">The data flow should be identical to the data flow in lesson 5.</span></span>  
  
 <span data-ttu-id="5f0cc-110">**Поток управления**</span><span class="sxs-lookup"><span data-stu-id="5f0cc-110">**Control Flow**</span></span>  
  
 <span data-ttu-id="5f0cc-111">![Поток управления](../../2014/tutorials/media/task3lesson6control.jpg "Поток управления")</span><span class="sxs-lookup"><span data-stu-id="5f0cc-111">![Control Flow](../../2014/tutorials/media/task3lesson6control.jpg "Control Flow")</span></span>  
  
 <span data-ttu-id="5f0cc-112">**Поток данных**</span><span class="sxs-lookup"><span data-stu-id="5f0cc-112">**Data Flow**</span></span>  
  
 <span data-ttu-id="5f0cc-113">![Поток данных](../../2014/tutorials/media/task3lesson6data.jpg "Поток данных")</span><span class="sxs-lookup"><span data-stu-id="5f0cc-113">![Data Flow](../../2014/tutorials/media/task3lesson6data.jpg "Data Flow")</span></span>  
  
### <a name="to-test-the-lesson-6-tutorial-package"></a><span data-ttu-id="5f0cc-114">Тестирование пакета учебника Lesson 6</span><span class="sxs-lookup"><span data-stu-id="5f0cc-114">TO test the Lesson 6 tutorial package</span></span>  
  
1.  <span data-ttu-id="5f0cc-115">В меню Отладка выберите команду Начать отладку.</span><span class="sxs-lookup"><span data-stu-id="5f0cc-115">On the Debug menu, click Start Debugging.</span></span>  
  
2.  <span data-ttu-id="5f0cc-116">После окончания работы пакета выберите в меню Отладка пункт Остановить отладку.</span><span class="sxs-lookup"><span data-stu-id="5f0cc-116">After the package has completed running, on the Debug menu, and then click Stop Debugging.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="5f0cc-117">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="5f0cc-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="5f0cc-118">Шаг 4. Развертывание пакета, созданного на занятии 6</span><span class="sxs-lookup"><span data-stu-id="5f0cc-118">Step 4: Deploying the Lesson 6 Package</span></span>](../integration-services/lesson-6-4-deploying-the-lesson-6-package.md)  
  
  
