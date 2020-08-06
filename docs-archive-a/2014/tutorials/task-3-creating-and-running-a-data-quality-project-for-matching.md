---
title: Задача 3. Создание и запуск проекта качества данных для сопоставления | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6260e911-ea8b-4c69-a39d-d1bccd565a32
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 221d6d583c61ee035c20fcb63f0ed5278f2b8678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656106"
---
# <a name="task-3-creating-and-running-a-data-quality-project-for-matching"></a><span data-ttu-id="34412-102">Задача 3. Создание и запуск проекта качества данных для сопоставления</span><span class="sxs-lookup"><span data-stu-id="34412-102">Task 3: Creating and Running a Data Quality Project for Matching</span></span>
  <span data-ttu-id="34412-103">В этой задаче вы создадите проект служб DQS для операции сопоставления и выполните сопоставление очищенных данных поставщика, чтобы удалить все повторяющиеся значения.</span><span class="sxs-lookup"><span data-stu-id="34412-103">In this task, you create a Data Quality Project for the matching activity and run the matching process on cleansed supplier data to remove any duplicates in the data.</span></span>

1.  <span data-ttu-id="34412-104">На главной странице **клиента DQS**нажмите кнопку **Создать проект качества данных**.</span><span class="sxs-lookup"><span data-stu-id="34412-104">On the main page of **DQS Client**, click **New Data Quality Project**.</span></span>

2.  <span data-ttu-id="34412-105">Введите **Удаление повторений поставщика** в поле **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="34412-105">Type **Remove Supplier Duplicates** from the **Name of the project**.</span></span>

3.  <span data-ttu-id="34412-106">Выберите **Поставщики** в списке баз знаний для поля **Использовать базу знаний** .</span><span class="sxs-lookup"><span data-stu-id="34412-106">Select **Suppliers** from the list of KBs for the **Use Knowledge Base** field.</span></span> <span data-ttu-id="34412-107">Вы создали политику проверки соответствия в этой базе знаний на предыдущем занятии.</span><span class="sxs-lookup"><span data-stu-id="34412-107">You have created a matching policy in this knowledge base in the previous lesson.</span></span>

4.  <span data-ttu-id="34412-108">Выберите **Сопоставление** в **списке действий** в нижней правой области.</span><span class="sxs-lookup"><span data-stu-id="34412-108">Select **Matching** from the **list of activities** from the bottom-right pane.</span></span>

     <span data-ttu-id="34412-109">![Новый проект служб DQS — выбрано сопоставление](../../2014/tutorials/media/et-creatingandrunningadqpformatching.jpg "Новый проект служб DQS — выбрано сопоставление")</span><span class="sxs-lookup"><span data-stu-id="34412-109">![New Data Quality Project - Matching Selected](../../2014/tutorials/media/et-creatingandrunningadqpformatching.jpg "New Data Quality Project - Matching Selected")</span></span>

5.  <span data-ttu-id="34412-110">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="34412-110">Click **Next**.</span></span>

6.  <span data-ttu-id="34412-111">На странице **Сопоставление** выберите **Файл Excel** как **Источник данных**.</span><span class="sxs-lookup"><span data-stu-id="34412-111">In the **Map** page, select **Excel File** for **Data Source**.</span></span>

7.  <span data-ttu-id="34412-112">Нажмите кнопку **Обзор** и выберите выходной файл процедуры очистки **Cleansed Supplier List.xls**.</span><span class="sxs-lookup"><span data-stu-id="34412-112">Click **Browse** and select **Cleansed Supplier List.xls**, which is the output file from the cleansing activity.</span></span>

8.  <span data-ttu-id="34412-113">Сопоставьте исходный столбец **SupplierID** с доменом **Идентификатор поставщика** , столбец **Имя поставщика** с доменом **Имя поставщика** , столбец **ContactEmailAddress** с доменом **Адрес электронной почты** .</span><span class="sxs-lookup"><span data-stu-id="34412-113">Map **SupplierID** source column to the **Supplier ID** domain, **Supplier Name** column to **Supplier Name** domain, and **ContactEmailAddress** column to **Contact Email** domain.</span></span>

9. <span data-ttu-id="34412-114">Нажмите кнопку **Далее** , чтобы перейти к странице **Сопоставление** .</span><span class="sxs-lookup"><span data-stu-id="34412-114">Click **Next** to switch to the **Matching** page.</span></span>

10. <span data-ttu-id="34412-115">Нажмите кнопку **Запустить** , чтобы начать процесс сопоставления.</span><span class="sxs-lookup"><span data-stu-id="34412-115">Click **Start** to start the matching process.</span></span> <span data-ttu-id="34412-116">Должны быть получены результаты, аналогичные результатам предыдущей задачи, поскольку для определения политики проверки соответствия использовался тот же входной файл.</span><span class="sxs-lookup"><span data-stu-id="34412-116">You should see results similar to those from the previous task because you used the same input file for defining the matching policy.</span></span>

11. <span data-ttu-id="34412-117">Просмотрите все сопоставленные записи и соответствующие оценки в списке.</span><span class="sxs-lookup"><span data-stu-id="34412-117">Review all the matched records and their matching score in the list box.</span></span> <span data-ttu-id="34412-118">Результаты должны быть такими же, как и в предыдущей задаче.</span><span class="sxs-lookup"><span data-stu-id="34412-118">The results should be same as the ones you saw in the previous task.</span></span> <span data-ttu-id="34412-119">Сведения об анализе результатов сопоставления см. в предыдущей задаче.</span><span class="sxs-lookup"><span data-stu-id="34412-119">See the steps in the previous task to analyze the results from this matching activity.</span></span>

12. <span data-ttu-id="34412-120">Нажмите кнопку **Далее** , чтобы перейти к странице **Экспорт** .</span><span class="sxs-lookup"><span data-stu-id="34412-120">Click **Next** to switch to the **Export** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="34412-121">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="34412-121">Next Step</span></span>
 [<span data-ttu-id="34412-122">Задача 4. Экспорт результатов сопоставления в файл Excel</span><span class="sxs-lookup"><span data-stu-id="34412-122">Task 4: Exporting the Results from Matching Activity to an Excel File</span></span>](../../2014/tutorials/task-4-exporting-the-results-from-matching-activity-to-an-excel-file.md)


