---
title: Задача 14. Добавление задачи «Выполнение SQL» в поток управления для запуска хранимой процедуры MDS | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 9a5d1b52-d505-4e6f-8a89-569329c094e2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: da8e80b25706c40e749fc364baeb578681e76b42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731161"
---
# <a name="task-14-adding-execute-sql-task-to-control-flow-to-run-the-stored-procedure-for-mds"></a><span data-ttu-id="fe2ca-102">Задача 14. Добавление в поток управления задачи "Выполнение SQL" для запуска хранимой процедуры для MDS</span><span class="sxs-lookup"><span data-stu-id="fe2ca-102">Task 14: Adding Execute SQL Task to Control Flow to Run the Stored Procedure for MDS</span></span>
  <span data-ttu-id="fe2ca-103">После загрузки данных в промежуточные таблицы служб MDS вы выполняете хранимую процедуру, связанную с этой таблицей, для загрузки данных из промежуточных таблиц в соответствующие таблицы в базе данных MDS.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-103">After loading data into the staging tables of MDS, you run a stored procedure associated with that table to load the data from staging into the appropriate tables in the MDS database.</span></span> <span data-ttu-id="fe2ca-104">У этой хранимой процедуры два обязательных параметра, которые нужно передать: LogFlag и VersionName.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-104">This stored procedure has two required parameters that you need to pass: LogFlag and VersionName.</span></span> <span data-ttu-id="fe2ca-105">Параметр LogFlag определяет, записываются ли транзакции в журнал в ходе промежуточного процесса, а параметр VersionName представляет версию модели.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-105">LogFlag specifies whether transactions are logged during the staging process and VersionName represents the version of the model.</span></span> <span data-ttu-id="fe2ca-106">Дополнительные сведения см. в разделе [Промежуточная хранимая процедура](https://msdn.microsoft.com/library/hh231028.aspx) .</span><span class="sxs-lookup"><span data-stu-id="fe2ca-106">See [Staged Stored Procedure](https://msdn.microsoft.com/library/hh231028.aspx) topic for more details.</span></span>

 <span data-ttu-id="fe2ca-107">В этой задаче вы добавляете задачу «Выполнение SQL» в поток управления для вызова хранимой процедуры и загрузки промежуточных данных в соответствующие таблицы базы данных MDS.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-107">In this task, you add the Execute SQL Task to the control flow to invoke the stored procedure to load the staged data into appropriate MDS tables.</span></span>

1.  <span data-ttu-id="fe2ca-108">Теперь перейдите на вкладку **поток управления** .</span><span class="sxs-lookup"><span data-stu-id="fe2ca-108">Now, switch to the **Control Flow** tab.</span></span>

2.  <span data-ttu-id="fe2ca-109">Перетащите задачу « **Выполнение SQL** » с **панели элементов служб SSIS** на вкладку **поток управления** .</span><span class="sxs-lookup"><span data-stu-id="fe2ca-109">Drag-drop **Execute SQL Task** from the **SSIS Toolbox** to the **Control Flow** tab.</span></span>

3.  <span data-ttu-id="fe2ca-110">Щелкните правой кнопкой мыши **задача "Выполнение SQL** " на вкладке " **поток управления** " и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-110">Right-click **Execute SQL Task** in the **Control Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="fe2ca-111">Введите **триггер хранимой процедуры для загрузки данных в MDS** и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-111">Type **Trigger Stored Procedure to Load Data into MDS** and press **ENTER**.</span></span>

4.  <span data-ttu-id="fe2ca-112">Соедините **данные о получении, очистке, совпадении и проверенных данных поставщика,** чтобы **активировать хранимую процедуру для загрузки данных** с помощью зеленого соединителя.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-112">Connect **Receive, Cleanse, Match, and Curate Supplier Data** to **Trigger Stored Procedure to Load Data** using the green connector.</span></span>

     <span data-ttu-id="fe2ca-113">![Соединение с задачей «Выполнение SQL»](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-01.jpg "Соединение с задачей «Выполнение SQL»")</span><span class="sxs-lookup"><span data-stu-id="fe2ca-113">![Connect to Execute SQL Task](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-01.jpg "Connect to Execute SQL Task")</span></span>

5.  <span data-ttu-id="fe2ca-114">С помощью окна **переменные** добавьте две новые переменные со следующими параметрами.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-114">Using the **Variables** window, add two new variables with the following settings.</span></span> <span data-ttu-id="fe2ca-115">Если окно **переменные** не отображается, щелкните **SSIS** в строке меню и выберите **переменные**.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-115">If you do not see the **Variables** window, click **SSIS** on the menu bar and click **Variables**.</span></span>

    |<span data-ttu-id="fe2ca-116">Имя</span><span class="sxs-lookup"><span data-stu-id="fe2ca-116">Name</span></span>|<span data-ttu-id="fe2ca-117">Тип данных</span><span class="sxs-lookup"><span data-stu-id="fe2ca-117">Data Type</span></span>|<span data-ttu-id="fe2ca-118">Значение</span><span class="sxs-lookup"><span data-stu-id="fe2ca-118">Value</span></span>|
    |----------|---------------|-----------|
    |<span data-ttu-id="fe2ca-119">LogFlag</span><span class="sxs-lookup"><span data-stu-id="fe2ca-119">LogFlag</span></span>|<span data-ttu-id="fe2ca-120">Int32</span><span class="sxs-lookup"><span data-stu-id="fe2ca-120">Int32</span></span>|<span data-ttu-id="fe2ca-121">1</span><span class="sxs-lookup"><span data-stu-id="fe2ca-121">1</span></span>|
    |<span data-ttu-id="fe2ca-122">VersionName</span><span class="sxs-lookup"><span data-stu-id="fe2ca-122">VersionName</span></span>|<span data-ttu-id="fe2ca-123">Строка</span><span class="sxs-lookup"><span data-stu-id="fe2ca-123">String</span></span>|<span data-ttu-id="fe2ca-124">VERSION_1</span><span class="sxs-lookup"><span data-stu-id="fe2ca-124">VERSION_1</span></span>|

     <span data-ttu-id="fe2ca-125">![Окно переменных служб SSIS](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-02.jpg "Окно переменных служб SSIS")</span><span class="sxs-lookup"><span data-stu-id="fe2ca-125">![SSIS Variables Window](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-02.jpg "SSIS Variables Window")</span></span>

6.  <span data-ttu-id="fe2ca-126">Дважды щелкните **триггер хранимая процедура, чтобы загрузить данные в MDS**.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-126">Double-click **Trigger Stored Procedure to Load Data into MDS**.</span></span>

7.  <span data-ttu-id="fe2ca-127">В диалоговом окне **Редактор задачи «Выполнение SQL** » выберите **(local). MDS** (или **localhost). MDS**) для **подключения**.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-127">In the **Execute SQL Task Editor** dialog box, select **(local).MDS** (or **localhost.MDS**) for **Connection**.</span></span>

8.  <span data-ttu-id="fe2ca-128">Введите **exec [STG]. [ udp_Supplier_Leaf]?,?,?**</span><span class="sxs-lookup"><span data-stu-id="fe2ca-128">Type **EXEC [stg].[udp_Supplier_Leaf] ?, ?, ?**</span></span> <span data-ttu-id="fe2ca-129">для **инструкции SQL**.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-129">for **SQL Statement**.</span></span> <span data-ttu-id="fe2ca-130">Имя можно проверить с помощью среды SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-130">You can verify the name by using SQL Server Management Studio.</span></span>

     <span data-ttu-id="fe2ca-131">![Диалоговое окно редактора «Выполнение SQL» — общие параметры](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-03.jpg "Диалоговое окно редактора «Выполнение SQL» — общие параметры")</span><span class="sxs-lookup"><span data-stu-id="fe2ca-131">![Execute SQL Editor Dialog Box - General Settings](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-03.jpg "Execute SQL Editor Dialog Box - General Settings")</span></span>

9. <span data-ttu-id="fe2ca-132">Щелкните **Сопоставление параметров** в меню слева.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-132">Click **Parameter Mapping** from the menu on left.</span></span>

10. <span data-ttu-id="fe2ca-133">На странице **Сопоставление параметров** нажмите кнопку **Добавить** , чтобы добавить сопоставление.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-133">In the **Parameter Mapping** page, click **Add** to add a mapping.</span></span> <span data-ttu-id="fe2ca-134">Разверните окно и измените размер столбцов, чтобы можно было видеть значения в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-134">Maximize the window and resize columns so that you can see values in drop-down lists properly.</span></span>

11. <span data-ttu-id="fe2ca-135">Выберите **User:: VersionName** из раскрывающегося списка для **имени переменной**.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-135">Select **User::VersionName** from the drop-down list for the **Variable Name**.</span></span>

12. <span data-ttu-id="fe2ca-136">Выберите **nvarchar** для **типа данных**.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-136">Select **NVARCHAR** for **Data Type**.</span></span>

13. <span data-ttu-id="fe2ca-137">Введите **0** (нуль) в качестве **имени параметра**.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-137">Type **0** (zero) for **Parameter Name**.</span></span>

14. <span data-ttu-id="fe2ca-138">Повторите предыдущие четыре шага, чтобы добавить другие переменные.</span><span class="sxs-lookup"><span data-stu-id="fe2ca-138">Repeat the previous four steps to add two more variables.</span></span>

    |<span data-ttu-id="fe2ca-139">Имя переменной</span><span class="sxs-lookup"><span data-stu-id="fe2ca-139">Variable Name</span></span>|<span data-ttu-id="fe2ca-140">Тип данных (важно)</span><span class="sxs-lookup"><span data-stu-id="fe2ca-140">Data Type (important)</span></span>|<span data-ttu-id="fe2ca-141">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="fe2ca-141">Parameter Name</span></span>|
    |-------------------|-----------------------------|--------------------|
    |<span data-ttu-id="fe2ca-142">User::LogFlag</span><span class="sxs-lookup"><span data-stu-id="fe2ca-142">User::LogFlag</span></span>|<span data-ttu-id="fe2ca-143">LONG</span><span class="sxs-lookup"><span data-stu-id="fe2ca-143">LONG</span></span>|<span data-ttu-id="fe2ca-144">1</span><span class="sxs-lookup"><span data-stu-id="fe2ca-144">1</span></span>|
    |<span data-ttu-id="fe2ca-145">User::BatchTag</span><span class="sxs-lookup"><span data-stu-id="fe2ca-145">User::BatchTag</span></span>|<span data-ttu-id="fe2ca-146">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="fe2ca-146">NVARCHAR</span></span>|<span data-ttu-id="fe2ca-147">2</span><span class="sxs-lookup"><span data-stu-id="fe2ca-147">2</span></span>|

     <span data-ttu-id="fe2ca-148">![Редактор задачи «Выполнение SQL» — сопоставление параметров](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-04.jpg "Редактор задачи «Выполнение SQL» — сопоставление параметров")</span><span class="sxs-lookup"><span data-stu-id="fe2ca-148">![Execute SQL Task Editor - Parameter Mapping](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-04.jpg "Execute SQL Task Editor - Parameter Mapping")</span></span>

15. <span data-ttu-id="fe2ca-149">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно « **выполнение редактора SQL** ».</span><span class="sxs-lookup"><span data-stu-id="fe2ca-149">Click **OK** to close the **Execute SQL Editor** dialog box.</span></span>

## <a name="next-step"></a><span data-ttu-id="fe2ca-150">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="fe2ca-150">Next Step</span></span>
 [<span data-ttu-id="fe2ca-151">Задача 15. Сборка и запуск проекта SSIS</span><span class="sxs-lookup"><span data-stu-id="fe2ca-151">Task 15: Building and Running the SSIS Project</span></span>](../../2014/tutorials/task-15-building-and-running-the-ssis-project.md)


