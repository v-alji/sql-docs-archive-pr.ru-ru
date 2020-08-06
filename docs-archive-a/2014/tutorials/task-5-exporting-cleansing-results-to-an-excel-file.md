---
title: Задача 5. Экспорт результатов очистки в файл Excel | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: eaeafd65-d0d4-4a7d-a3ad-110ef644e90b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0dbdc1bef348e03e211e4933132985ea2c089b97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666914"
---
# <a name="task-5-exporting-cleansing-results-to-an-excel-file"></a><span data-ttu-id="bd44f-102">Задача 5. Экспорт результатов очистки в файл Excel</span><span class="sxs-lookup"><span data-stu-id="bd44f-102">Task 5: Exporting Cleansing Results to an Excel File</span></span>
  <span data-ttu-id="bd44f-103">В этой задаче вы экспортируете результаты операции очистки в файл Excel.</span><span class="sxs-lookup"><span data-stu-id="bd44f-103">In this task, you export results from the cleansing activity to an Excel file.</span></span> <span data-ttu-id="bd44f-104">Дополнительные сведения см. в разделе [этап экспорта](https://msdn.microsoft.com/library/hh213061.aspx#Export) .</span><span class="sxs-lookup"><span data-stu-id="bd44f-104">See [Export Stage](https://msdn.microsoft.com/library/hh213061.aspx#Export) topic for more details.</span></span>  
  
1.  <span data-ttu-id="bd44f-105">В области справа выберите **Excel** для **типа назначения**.</span><span class="sxs-lookup"><span data-stu-id="bd44f-105">In the right pane, select **Excel** for the **Destination Type**.</span></span>  
  
2.  <span data-ttu-id="bd44f-106">Нажмите кнопку **Обзор**, укажите имя выходного файла в виде \*\*очищенного List.xlsпоставщика \*\*, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="bd44f-106">Click **Browse**, specify the output file name as **Cleansed Supplier List.xls**, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="bd44f-107">Выберите **данные только** для формата **выходных** данных, чтобы экспортировать только очищенные данные.</span><span class="sxs-lookup"><span data-stu-id="bd44f-107">Select **Data Only** for the **Output** format to export just the cleansed data.</span></span> <span data-ttu-id="bd44f-108">Второй вариант, **данные и сведения о очистке**позволяют экспортировать сведения о действии очистки вместе с очищенными данными.</span><span class="sxs-lookup"><span data-stu-id="bd44f-108">The second option, **Data and Cleansing Info**, lets you export cleansing activity details along with the cleansed data.</span></span> <span data-ttu-id="bd44f-109">Параметр **Стандартиз Format** позволяет применять любые форматы вывода, определенные в домене, к значениям этого домена.</span><span class="sxs-lookup"><span data-stu-id="bd44f-109">The **Standardize Format** option lets you apply any output formats you define on a domain to the values of that domain.</span></span> <span data-ttu-id="bd44f-110">В этом учебнике формат вывода не был задан ни для одного домена.</span><span class="sxs-lookup"><span data-stu-id="bd44f-110">You have not defined an output format on any domain in the tutorial.</span></span>  
  
     <span data-ttu-id="bd44f-111">![Страница «Экспорт результатов очистки»](../../2014/tutorials/media/et-exportingcleansingresultstoanexcelfile.jpg "Страница «Экспорт результатов очистки»")</span><span class="sxs-lookup"><span data-stu-id="bd44f-111">![Export Cleansing Results Page](../../2014/tutorials/media/et-exportingcleansingresultstoanexcelfile.jpg "Export Cleansing Results Page")</span></span>  
  
4.  <span data-ttu-id="bd44f-112">Нажмите кнопку **Экспорт** , чтобы экспортировать данные.</span><span class="sxs-lookup"><span data-stu-id="bd44f-112">Click **Export** to export the data.</span></span> <span data-ttu-id="bd44f-113">Пока не нажимайте кнопку **Готово** .</span><span class="sxs-lookup"><span data-stu-id="bd44f-113">Do not click **Finish** yet.</span></span>  
  
5.  <span data-ttu-id="bd44f-114">Нажмите кнопку **Закрыть** в диалоговом окне **Экспорт** .</span><span class="sxs-lookup"><span data-stu-id="bd44f-114">Click **Close** on the **Exporting** dialog box.</span></span>  
  
6.  <span data-ttu-id="bd44f-115">Нажмите кнопку **Готово** , чтобы завершить работу.</span><span class="sxs-lookup"><span data-stu-id="bd44f-115">Click **Finish** to finish the activity.</span></span> <span data-ttu-id="bd44f-116">Если вы забыли экспортировать результаты перед нажатием кнопки **"Готово"**, нажмите кнопку " **Открыть проект** **служб DQS**" на главной странице клиента, выберите в списке проектов пункт **очистить список поставщиков** и нажмите кнопку **Далее** в нижней части экрана, чтобы снова перейти к этапу **экспорта** процесса очистки.</span><span class="sxs-lookup"><span data-stu-id="bd44f-116">If you forgot to export results before clicking **Finish**, click **Open Data Quality Project** in the main page of **DQS Client**, select **Cleanse Supplier List** from the list of projects, and click **Next** at the bottom of the screen to get to the **Export** stage of cleansing process again.</span></span> <span data-ttu-id="bd44f-117">Можно также переключиться на вкладку **Управление и просмотр результатов** , нажав кнопку **назад** .</span><span class="sxs-lookup"><span data-stu-id="bd44f-117">You can also switch to **Manage and View Results** tab by clicking **Back** button.</span></span>  
  
7.  <span data-ttu-id="bd44f-118">Откройте **очищенный поставщик List.xls** и выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bd44f-118">Open the **Cleansed Supplier List.xls** and do the following:</span></span>  
  
    1.  <span data-ttu-id="bd44f-119">Убедитесь в отсутствии адресов электронной почты, которые заканчиваются на adventure-work.com (без символа "), выполнив поиск adventure-work.com на листе.</span><span class="sxs-lookup"><span data-stu-id="bd44f-119">Ensure that there are no email addresses that end with adventure-work.com (without character 's') by searching for adventure-work.com in the worksheet.</span></span>  
  
    2.  <span data-ttu-id="bd44f-120">Видите, что в столбце **Country** нет значения **USA** .</span><span class="sxs-lookup"><span data-stu-id="bd44f-120">See that there is no **USA** value in the **Country** column.</span></span>  
  
    3.  <span data-ttu-id="bd44f-121">Найдите **Лос-Анджелес** и посмотрите, что для **состояния** задано значение **CA**.</span><span class="sxs-lookup"><span data-stu-id="bd44f-121">Search for **Los Angeles** and see that the **State** is set to **CA**.</span></span>  
  
    4.  <span data-ttu-id="bd44f-122">Убедитесь, что отсутствуют условия **Co.**, **Corp.** и **Inc.**</span><span class="sxs-lookup"><span data-stu-id="bd44f-122">Confirm that there are no terms **Co.**, **Corp.**, and **Inc.**.</span></span>  
  
    5.  <span data-ttu-id="bd44f-123">Удалите столбец **проверки адреса** из электронной таблицы и сохраните файл Excel.</span><span class="sxs-lookup"><span data-stu-id="bd44f-123">Delete the **Address Validation** column from the spreadsheet and save the excel file.</span></span> <span data-ttu-id="bd44f-124">Этот дополнительный столбец соответствует составному домену проверки адреса.</span><span class="sxs-lookup"><span data-stu-id="bd44f-124">This additional column corresponds to the Address Validation composite domain.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="bd44f-125">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="bd44f-125">Next Step</span></span>  
 [<span data-ttu-id="bd44f-126">Задача 6. Импорт значений из проекта очистки списка поставщиков</span><span class="sxs-lookup"><span data-stu-id="bd44f-126">Task 6: Importing Values from the Cleanse Supplier List Project</span></span>](../../2014/tutorials/task-6-importing-values-from-the-cleanse-supplier-list-project.md)  
  
  
