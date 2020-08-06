---
title: Задача 4. Экспорт результатов из действия сопоставления в файл Excel | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 644454c4-3c5a-469a-90ec-e51dc7fb99fc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b583e44f887fc0595fb904ec977f1de28c2fecd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735586"
---
# <a name="task-4-exporting-the-results-from-matching-activity-to-an-excel-file"></a><span data-ttu-id="09139-102">Задача 4. Экспорт результатов сопоставления в файл Excel</span><span class="sxs-lookup"><span data-stu-id="09139-102">Task 4: Exporting the Results from Matching Activity to an Excel File</span></span>
  <span data-ttu-id="09139-103">В этой задаче вы экспортируете результаты операции сопоставления в файл Excel.</span><span class="sxs-lookup"><span data-stu-id="09139-103">In this task, you export the results from the matching activity to an Excel file.</span></span>

1.  <span data-ttu-id="09139-104">На странице **Экспорт** выберите **файл Excel** для **целевого типа**.</span><span class="sxs-lookup"><span data-stu-id="09139-104">In the **Export** page, select **Excel File** for the **Destination Type**.</span></span>

2.  <span data-ttu-id="09139-105">Выберите параметр **выживания Results (результаты** ).</span><span class="sxs-lookup"><span data-stu-id="09139-105">Select **Survivorship Results** option.</span></span> <span data-ttu-id="09139-106">В процессе выживания DQS определяет запись выжившую» для каждого кластера на основе выбранного **правила выживания** .</span><span class="sxs-lookup"><span data-stu-id="09139-106">In the survivorship process, DQS determines a survivor record for each cluster based on the **Survivorship Rule** you selected.</span></span>

3.  <span data-ttu-id="09139-107">Нажмите кнопку **Обзор** и перейдите к папке, в которой необходимо сохранить выходной файл.</span><span class="sxs-lookup"><span data-stu-id="09139-107">Click **Browse** and navigate to the folder where you want to store the output file.</span></span>

4.  <span data-ttu-id="09139-108">Введите **очистку и совпадение Suppliers.xls** для имени и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="09139-108">Type **Cleansed and Matched Suppliers.xls** for the name and click **Open**.</span></span>

5.  <span data-ttu-id="09139-109">Убедитесь, что для **правила выживания**выбрана **сводная запись** .</span><span class="sxs-lookup"><span data-stu-id="09139-109">Confirm that **Pivot Record** is selected for the **Survivorship Rule**.</span></span> <span data-ttu-id="09139-110">Если вы выбрали этот параметр, сводная запись для каждого кластера используется для вывода из кластера.</span><span class="sxs-lookup"><span data-stu-id="09139-110">When you select this option, the pivot record for each cluster is picked for the output from a cluster.</span></span> <span data-ttu-id="09139-111">Другие параметры для правила сохранения перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="09139-111">The other options for the Survivorship Rule are:</span></span>

    1.  <span data-ttu-id="09139-112">**Наиболее полная запись:** Запись выжившую» с максимальным числом заполненных полей.</span><span class="sxs-lookup"><span data-stu-id="09139-112">**Most complete record:** Survivor record is the one with the largest number of populated fields.</span></span>

    2.  <span data-ttu-id="09139-113">Самая **длинная запись:** Запись выжившую» с максимальным числом терминов в исходных полях.</span><span class="sxs-lookup"><span data-stu-id="09139-113">**Longest record:** Survivor record is the one with the largest number of terms in source fields.</span></span>

    3.  <span data-ttu-id="09139-114">**Наиболее полная и длинная запись:** Запись выжившую» с максимальным числом заполненных полей и имеет максимальное количество терминов в каждом поле.</span><span class="sxs-lookup"><span data-stu-id="09139-114">**Most complete and longest record:** Survivor record is the one with the largest number of populated fields, and has the largest number of terms in each field.</span></span>

     <span data-ttu-id="09139-115">![Экспорт результатов со страницы совпадения](../../2014/tutorials/media/et-exportingtheresultsfrommatoanexcelfile.jpg "Экспорт результатов со страницы совпадения")</span><span class="sxs-lookup"><span data-stu-id="09139-115">![Export Results from Matching Page](../../2014/tutorials/media/et-exportingtheresultsfrommatoanexcelfile.jpg "Export Results from Matching Page")</span></span>

6.  <span data-ttu-id="09139-116">Нажмите кнопку **Экспорт** , чтобы экспортировать результаты в файл Excel.</span><span class="sxs-lookup"><span data-stu-id="09139-116">Click **Export** to export the results to an Excel file.</span></span>

7.  <span data-ttu-id="09139-117">Нажмите кнопку **Закрыть** , чтобы закрыть диалоговое окно « **экспорт сопоставления** ».</span><span class="sxs-lookup"><span data-stu-id="09139-117">Click **Close** to close the **Matching Export** dialog box.</span></span>

8.  <span data-ttu-id="09139-118">Нажмите кнопку **Готово** , чтобы завершить действие сопоставления.</span><span class="sxs-lookup"><span data-stu-id="09139-118">Click **Finish** to finish the matching activity.</span></span>

9. <span data-ttu-id="09139-119">Откройте **очищенный и сопоставленный файл Suppliers.xlsx** и убедитесь, что не отображаются дубликаты (КодПоставщика).</span><span class="sxs-lookup"><span data-stu-id="09139-119">Open the **Cleansed and Matched Suppliers.xlsx** file and confirm that you do not see any duplicates (SupplierID).</span></span>

 <span data-ttu-id="09139-120">Вы получили данные поставщика, которые были очищены и сопоставлены для удаления повторяющихся значений.</span><span class="sxs-lookup"><span data-stu-id="09139-120">Now, you have supplier data that has been cleansed and matched to remove duplicates.</span></span>

## <a name="next-step"></a><span data-ttu-id="09139-121">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="09139-121">Next Step</span></span>
 [<span data-ttu-id="09139-122">Занятие 4: Хранение данных поставщика в MDS</span><span class="sxs-lookup"><span data-stu-id="09139-122">Lesson 4: Storing Supplier Data in MDS</span></span>](../../2014/tutorials/lesson-4-storing-supplier-data-in-mds.md)


