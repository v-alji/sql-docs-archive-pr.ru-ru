---
title: Шаг 5. Проверка учебного пакета, созданного на занятии 4 | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5f18df92-0248-4858-836b-c8b02f0e0439
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4a897f99bf68805e4e66c3b6bbe818b312077fb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735465"
---
# <a name="step-5-testing-the-lesson-4-tutorial-package"></a><span data-ttu-id="d6ffd-102">Шаг 5. Проверка учебного пакета, созданного на занятии 4</span><span class="sxs-lookup"><span data-stu-id="d6ffd-102">Step 5: Testing the Lesson 4 Tutorial Package</span></span>
  <span data-ttu-id="d6ffd-103">На стадии выполнения произойдет ошибка поиска соответствия при работе преобразования «Уточняющий запрос» для Currency Key в поврежденном файле Currency_BAD.txt.</span><span class="sxs-lookup"><span data-stu-id="d6ffd-103">At run time, the corrupted file, Currency_BAD.txt, will fail to generate a match within the Currency Key Lookup transformation.</span></span> <span data-ttu-id="d6ffd-104">Так как вывод ошибок преобразования «Уточняющий запрос» для Currency Key настроен на перенаправление строк новому адресату «неудачные обращения», операция не завершится ошибкой, и пакет будет успешно выполнен.</span><span class="sxs-lookup"><span data-stu-id="d6ffd-104">Because the error output of Currency Key Lookup has now been configured to redirect failed rows to the new Failed Rows destination, the component does not fail, and the package runs successfully.</span></span> <span data-ttu-id="d6ffd-105">Все ошибочные строки будут записаны в файл ErrorOutput.txt.</span><span class="sxs-lookup"><span data-stu-id="d6ffd-105">All failed error rows are written to ErrorOutput.txt.</span></span>  
  
 <span data-ttu-id="d6ffd-106">В этой задаче требуется проверить измененную конфигурацию вывода ошибок, запустив пакет на выполнение.</span><span class="sxs-lookup"><span data-stu-id="d6ffd-106">In this task, you will test the revised error output configuration by running the package.</span></span> <span data-ttu-id="d6ffd-107">После успешного выполнения пакета проверьте содержимое файла ErrorOutput.txt.</span><span class="sxs-lookup"><span data-stu-id="d6ffd-107">Upon successful package execution, you will then view the contents of the ErrorOutput.txt file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6ffd-108">Если нет необходимости накапливать ошибочные строки в файле ErrorOutput.txt, нужно вручную очистить содержимое файла между выполнениями пакета.</span><span class="sxs-lookup"><span data-stu-id="d6ffd-108">If you do not want to accumulate error rows in the ErrorOutput.txt file, you should manually delete the file content between package runs.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="d6ffd-109">Проверка макета пакета</span><span class="sxs-lookup"><span data-stu-id="d6ffd-109">Checking the Package layout</span></span>  
 <span data-ttu-id="d6ffd-110">Перед проверкой пакета нужно проверить, что поток управления и данных в пакете занятия 4 содержит объекты, показанные на следующих диаграммах.</span><span class="sxs-lookup"><span data-stu-id="d6ffd-110">Before you test the package you should verify that the control flow and the data flow in the Lesson 4 package contain the objects shown in the following diagrams.</span></span> <span data-ttu-id="d6ffd-111">Поток управления должен быть таким же, как и поток управления в занятиях 2 — 4.</span><span class="sxs-lookup"><span data-stu-id="d6ffd-111">The control flow should be identical to the control flow in lessons 2 - 4.</span></span>  
  
 <span data-ttu-id="d6ffd-112">**Поток управления**</span><span class="sxs-lookup"><span data-stu-id="d6ffd-112">**Control Flow**</span></span>  
  
 <span data-ttu-id="d6ffd-113">![Поток управления в пакете](../../2014/tutorials/media/task4lesson2control.gif "Поток управления в пакете")</span><span class="sxs-lookup"><span data-stu-id="d6ffd-113">![Control flow in package](../../2014/tutorials/media/task4lesson2control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="d6ffd-114">**Поток данных**</span><span class="sxs-lookup"><span data-stu-id="d6ffd-114">**Data Flow**</span></span>  
  
 <span data-ttu-id="d6ffd-115">![Поток данных в пакете](../../2014/tutorials/media/task5lesson5data.gif "Поток данных в пакете")</span><span class="sxs-lookup"><span data-stu-id="d6ffd-115">![Data flow in package](../../2014/tutorials/media/task5lesson5data.gif "Data flow in package")</span></span>  
  
### <a name="to-run-the-lesson-4-tutorial-package"></a><span data-ttu-id="d6ffd-116">Выполнение учебного пакета занятия 4</span><span class="sxs-lookup"><span data-stu-id="d6ffd-116">To run the Lesson 4 tutorial package</span></span>  
  
1.  <span data-ttu-id="d6ffd-117">В меню **Отладка** выберите пункт **Начать отладку**.</span><span class="sxs-lookup"><span data-stu-id="d6ffd-117">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
2.  <span data-ttu-id="d6ffd-118">После окончания работы пакета выберите в меню **Отладка** пункт **Остановить отладку**.</span><span class="sxs-lookup"><span data-stu-id="d6ffd-118">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
### <a name="to-verify-the-contents-of-the-erroroutputtxt-file"></a><span data-ttu-id="d6ffd-119">Проверка содержимого файла ErrorOutput.txt</span><span class="sxs-lookup"><span data-stu-id="d6ffd-119">To verify the contents of the ErrorOutput.txt file</span></span>  
  
-   <span data-ttu-id="d6ffd-120">Откройте файл ErrorOutput.txt в приложении «Блокнот» или другом текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="d6ffd-120">In Notepad or any other text editor, open the ErrorOutput.txt file.</span></span> <span data-ttu-id="d6ffd-121">Порядок столбцов по умолчанию: AverageRate, CurrencyID, CurrencyDate, EndOfDateRate, ErrorCode, ErrorColumn, ErrorDescription.</span><span class="sxs-lookup"><span data-stu-id="d6ffd-121">The default column order is: AverageRate, CurrencyID, CurrencyDate, EndOfDateRate, ErrorCode, ErrorColumn, ErrorDescription.</span></span>  
  
     <span data-ttu-id="d6ffd-122">Обратите внимание, что все строки файла содержат несовпадающие значения в столбце CurrencyID, значение столбца ErrorCode равно -1071607778, значение столбца ErrorColumn равно 0 и значение столбца ErrorDescription равно «В результате уточняющего запроса для строки не обнаружено соответствия».</span><span class="sxs-lookup"><span data-stu-id="d6ffd-122">Notice that all the rows in the file contain the unmatched CurrencyID value of BAD, the ErrorCode value of -1071607778, the ErrorColumn value of 0, and the ErrorDescription value "Row yielded no match during lookup".</span></span> <span data-ttu-id="d6ffd-123">Значение столбца ErrorColumn равно 0, поскольку ошибка не является специфической для данного столбца.</span><span class="sxs-lookup"><span data-stu-id="d6ffd-123">The value of the ErrorColumn is set to 0 because the error is not column specific.</span></span> <span data-ttu-id="d6ffd-124">Это неудавшаяся операция уточняющего запроса.</span><span class="sxs-lookup"><span data-stu-id="d6ffd-124">It is the lookup operation that failed.</span></span> <span data-ttu-id="d6ffd-125">.</span><span class="sxs-lookup"><span data-stu-id="d6ffd-125">.</span></span>  
  
  
