---
title: Задача 17. Просмотр проекта очистки DQS, созданного с помощью пакета служб SSIS | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: fc6cc258-72f5-4593-8edb-9f5bc66de9db
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0876a0b727e810f8834fcf5445958bf9884a87f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727489"
---
# <a name="task-17-reviewing-dqs-cleansing-project-created-by-the-ssis-package"></a><span data-ttu-id="1f8ea-102">Задача 17. Проверка проекта очистки DQS, созданного пакетом SSIS</span><span class="sxs-lookup"><span data-stu-id="1f8ea-102">Task 17: Reviewing DQS Cleansing Project Created by the SSIS package</span></span>
  <span data-ttu-id="1f8ea-103">В этой задаче вы откроете проект служб DQS, созданный пакетом служб SSIS в клиенте DQS, просмотрите результаты очистки и при желании выполните интерактивную очистку и экспортируете результаты.</span><span class="sxs-lookup"><span data-stu-id="1f8ea-103">In this task, you open the DQS project created by the SSIS package in DQS Client, review the results from the cleansing process, and optionally perform interactive cleansing and export the results.</span></span>  
  
1.  <span data-ttu-id="1f8ea-104">Запустите **Data Quality Client**.</span><span class="sxs-lookup"><span data-stu-id="1f8ea-104">Launch **Data Quality Client**.</span></span>  
  
2.  <span data-ttu-id="1f8ea-105">Щелкните **мониторинг активности** в области **Администрирование** .</span><span class="sxs-lookup"><span data-stu-id="1f8ea-105">Click **Activity Monitoring** in the **Administration** pane.</span></span>  
  
3.  <span data-ttu-id="1f8ea-106">Отсортируйте список на основе **времени начала действия** , чтобы просмотреть последнюю запись.</span><span class="sxs-lookup"><span data-stu-id="1f8ea-106">Sort the list based on **Activity Start Time** to see the latest record.</span></span>  
  
4.  <span data-ttu-id="1f8ea-107">Обратите внимание, что имя проекта отображается в следующем формате: **CleanseAndCurate. Очистка данных поставщика. GUID**.</span><span class="sxs-lookup"><span data-stu-id="1f8ea-107">Notice that you see a name of the project in the following format: **CleanseAndCurate.Cleanse Supplier Data.GUID**.</span></span>  
  
     <span data-ttu-id="1f8ea-108">![Проект очистки DQS, созданный пакетом SSIS](../../2014/tutorials/media/et-reviewingdqscpcreatedbythessispackage.jpg "Проект очистки DQS, созданный пакетом SSIS")</span><span class="sxs-lookup"><span data-stu-id="1f8ea-108">![DQS Cleansing Project Created by SSIS Package](../../2014/tutorials/media/et-reviewingdqscpcreatedbythessispackage.jpg "DQS Cleansing Project Created by SSIS Package")</span></span>  
  
5.  <span data-ttu-id="1f8ea-109">Обратите внимание, что значение **в поле активно** . **Active**</span><span class="sxs-lookup"><span data-stu-id="1f8ea-109">Notice that the value in the **Is Active** field is **Active**.</span></span>  
  
6.  <span data-ttu-id="1f8ea-110">Щелкните вкладку **профилировщик** в нижней области, чтобы просмотреть статистику профилировщика для действия Очистка, выполненного пакетом служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="1f8ea-110">Click **Profiler** tab in the bottom pane to see profiler statistics for the Cleansing activity that the SSIS package performed.</span></span>  
  
7.  <span data-ttu-id="1f8ea-111">Нажмите кнопку **Закрыть** , чтобы закрыть экран **Администрирование** .</span><span class="sxs-lookup"><span data-stu-id="1f8ea-111">Click **Close** to close the **Administration** screen.</span></span>  
  
8.  <span data-ttu-id="1f8ea-112">На главной странице **клиента DQS**щелкните **Открыть проект качества данных** в области **проекты качества данных** .</span><span class="sxs-lookup"><span data-stu-id="1f8ea-112">In the main page of **DQS Client**, click **Open Data Quality Project** in the **Data Quality Projects** pane.</span></span>  
  
9. <span data-ttu-id="1f8ea-113">В списке проектов выберите проект, созданный компонентом «Очистка данных DQS» пакета служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="1f8ea-113">In the list of projects, select the project created by SSIS DQS Cleansing component.</span></span> <span data-ttu-id="1f8ea-114">Имя проекта должно быть в формате: **CleanseAndCurate. Очистка данных поставщика. GUID (красный цвет)**.</span><span class="sxs-lookup"><span data-stu-id="1f8ea-114">The name of the project should be in format:  **CleanseAndCurate.Cleanse Supplier Data.GUID (in red color)**.</span></span> <span data-ttu-id="1f8ea-115">Возможно, потребуется отсортировать список на основе столбца **Date Created** и найти последнюю запись.</span><span class="sxs-lookup"><span data-stu-id="1f8ea-115">You may need to sort the list based on **Date Created** column and look for the latest record.</span></span>  
  
10. <span data-ttu-id="1f8ea-116">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1f8ea-116">Click **Next**.</span></span>  
  
11. <span data-ttu-id="1f8ea-117">Страница " **Управление результатами" и "Просмотр результатов** " должна быть знакома с интерактивной очистки, которая выполнялась ранее в этом учебнике.</span><span class="sxs-lookup"><span data-stu-id="1f8ea-117">The **Manage and View Results** page should be familiar to you from the interactive cleansing you did earlier in this tutorial.</span></span>  
  
12. <span data-ttu-id="1f8ea-118">Просмотрите результаты очистки.</span><span class="sxs-lookup"><span data-stu-id="1f8ea-118">Review the cleansing results.</span></span> <span data-ttu-id="1f8ea-119">Вы также можете провести интерактивную очистку и экспортировать результаты в файл Excel или в базу данных на следующей странице.</span><span class="sxs-lookup"><span data-stu-id="1f8ea-119">You can also perform interactive cleansing and export results to an Excel file or to a database in the next page.</span></span>  
  
13. <span data-ttu-id="1f8ea-120">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1f8ea-120">Click **Next**.</span></span> <span data-ttu-id="1f8ea-121">На этой странице **экспорта** можно экспортировать результаты в файл Excel, в CSV-файл или в базу данных SQL.</span><span class="sxs-lookup"><span data-stu-id="1f8ea-121">In this **Export** page, you can export results to an excel file, CSV file, or to a SQL database.</span></span>  
  
14. <span data-ttu-id="1f8ea-122">Нажмите кнопку **Готово** , чтобы завершить работу.</span><span class="sxs-lookup"><span data-stu-id="1f8ea-122">Click **Finish** to finish the activity.</span></span>  
  
15. <span data-ttu-id="1f8ea-123">На главной странице **клиента DQS**щелкните **мониторинг активности** в области **Администрирование** .</span><span class="sxs-lookup"><span data-stu-id="1f8ea-123">In the main page of **DQS Client**, click **Activity Monitoring** in the **Administration** pane.</span></span>  
  
16. <span data-ttu-id="1f8ea-124">Обратите внимание, что **значение поля "** штат \" для проекта **завершено** .</span><span class="sxs-lookup"><span data-stu-id="1f8ea-124">Notice that the value of **IsActive** field for the project is **Ended** now.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="1f8ea-125">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="1f8ea-125">Next Step</span></span>  
 [<span data-ttu-id="1f8ea-126">Заключение</span><span class="sxs-lookup"><span data-stu-id="1f8ea-126">Conclusion</span></span>](../../2014/tutorials/conclusion.md)  
  
  
