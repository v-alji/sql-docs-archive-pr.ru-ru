---
title: Создание скриптов
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 9711c617-3c68-4e5a-aea3-befc64d51524
author: rothja
ms.author: jroth
ms.openlocfilehash: 199d5e0c98d220861ee0dfb48a44a71675d8ba87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668237"
---
# <a name="generate-scripts-sql-server-management-studio"></a><span data-ttu-id="c763c-102">Формирование скриптов (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="c763c-102">Generate Scripts (SQL Server Management Studio)</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="c763c-103">предоставляет два механизма формирования скриптов [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c763c-103">provides two mechanisms for generating [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="c763c-104">Скрипты для нескольких объектов можно создавать с помощью **мастера формирования и публикации скриптов.**</span><span class="sxs-lookup"><span data-stu-id="c763c-104">You can create scripts for multiple objects by using the **Generate and Publish Scripts Wizard.**.</span></span> <span data-ttu-id="c763c-105">Можно также создать скрипты для отдельных или нескольких объектов с помощью меню **Сформировать скрипт как** в **обозревателе объектов**.</span><span class="sxs-lookup"><span data-stu-id="c763c-105">You can also generate a script for individual objects or multiple objects by using the **Script as** menu in **Object Explorer**.</span></span>  
  
1.  <span data-ttu-id="c763c-106">**Выберите метод**  [Мастер формирования и публикации скриптов](#GenPubScriptWiz), [Меню "Сформировать скрипт как" в обозревателе объектов](#OEScriptAsMenu)</span><span class="sxs-lookup"><span data-stu-id="c763c-106">**Choose a method:**  [Generate and Publish Scripts Wizard](#GenPubScriptWiz), [Object Explorer Script As Menu](#OEScriptAsMenu)</span></span>  
  
2.  <span data-ttu-id="c763c-107">**Использование меню "Сформировать скрипт как"**  [Скрипт для одного объекта](#ScriptSingleObject), [Скрипт для двух объектов с помощью обозревателя объектов](#ScriptTwoObjectsOE), [Скрипт для двух объектов с помощью данных обозревателя объектов](#ScriptTwoObjectsOED)</span><span class="sxs-lookup"><span data-stu-id="c763c-107">**To use the Script As menu:**  [Script a Single Object](#ScriptSingleObject), [Script Two Objects Using Object Explorer](#ScriptTwoObjectsOE), [Script Two Objects Using Object Explorer Details](#ScriptTwoObjectsOED)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="c763c-108">Перед началом</span><span class="sxs-lookup"><span data-stu-id="c763c-108">Before You Begin</span></span>  
 <span data-ttu-id="c763c-109">Выберите механизм, который лучше всего соответствует имеющимся требованиям.</span><span class="sxs-lookup"><span data-stu-id="c763c-109">Choose the mechanism that best meets your requirements.</span></span>  
  
###  <a name="generate-and-publish-scripts-wizard"></a><a name="GenPubScriptWiz"></a> <span data-ttu-id="c763c-110">Мастер формирования и публикации скриптов</span><span class="sxs-lookup"><span data-stu-id="c763c-110">Generate and Publish Scripts Wizard</span></span>  
 <span data-ttu-id="c763c-111">С помощью **мастера формирования и публикации скриптов** можно создать скрипт [!INCLUDE[tsql](../../includes/tsql-md.md)] для нескольких объектов.</span><span class="sxs-lookup"><span data-stu-id="c763c-111">Use the **Generate and Publish Scripts Wizard** to create a [!INCLUDE[tsql](../../includes/tsql-md.md)] script for many objects.</span></span> <span data-ttu-id="c763c-112">Этот мастер создает скрипт для всех объектов базы данных или скрипт для подмножества выделенных объектов.</span><span class="sxs-lookup"><span data-stu-id="c763c-112">The wizard generates a script of all the objects in a database, or a subset of the objects that you select.</span></span> <span data-ttu-id="c763c-113">Мастер позволяет настраивать различные параметры скрипта, такие как включение разрешений, параметры сортировки, ограничения и т. д.</span><span class="sxs-lookup"><span data-stu-id="c763c-113">The wizard has many options for your scripts, such as whether to include permissions, collation, constraints, and so on.</span></span> <span data-ttu-id="c763c-114">Инструкции по использованию мастера см. в разделе [Мастер формирования и публикации скриптов](generate-and-publish-scripts-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="c763c-114">For instructions on using the wizard, see [Generate and Publish Scripts Wizard](generate-and-publish-scripts-wizard.md).</span></span>  
  
###  <a name="object-explorer-script-as-menu"></a><a name="OEScriptAsMenu"></a> <span data-ttu-id="c763c-115">Меню "Сформировать скрипт как" в обозревателе объектов</span><span class="sxs-lookup"><span data-stu-id="c763c-115">Object Explorer Script As Menu</span></span>  
 <span data-ttu-id="c763c-116">Меню **Сформировать скрипт как** в обозревателе объектов служит для создания скрипта для одного объекта, нескольких объектов или нескольких инструкций одного объекта.</span><span class="sxs-lookup"><span data-stu-id="c763c-116">You can use the **Object Explorer Script as** menu to script a single object, script multiple objects, or script multible statements for a single objects.</span></span> <span data-ttu-id="c763c-117">Можно выбрать один из нескольких типов скрипта, например для создания, изменения или удаления объекта.</span><span class="sxs-lookup"><span data-stu-id="c763c-117">You can choose one of several types of scripts; for example to create, alter, or drop the object.</span></span> <span data-ttu-id="c763c-118">Сохранить скрипт можно в окне редактора запросов — в файл или в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="c763c-118">You can save the script in a Query Editor window, to a file, or to the Clipboard.</span></span> <span data-ttu-id="c763c-119">Скрипт создается в формате Юникода.</span><span class="sxs-lookup"><span data-stu-id="c763c-119">The script is created in Unicode format.</span></span>  
  
##  <a name="to-generate-a-script-of-a-single-object"></a><a name="ScriptSingleObject"></a> <span data-ttu-id="c763c-120">Создание скрипта для одного объекта</span><span class="sxs-lookup"><span data-stu-id="c763c-120">To generate a script of a single object</span></span>  
 <span data-ttu-id="c763c-121">**Создание скрипта для одного объекта**</span><span class="sxs-lookup"><span data-stu-id="c763c-121">**To script a single object**</span></span>  
  
1.  <span data-ttu-id="c763c-122">В обозревателе объектов подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="c763c-122">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c763c-123">Разверните узел **Базы данных**, а затем разверните базу данных, содержащую объекты, для которых необходимо создать скрипт.</span><span class="sxs-lookup"><span data-stu-id="c763c-123">Expand **Databases**, and then expand the database containing the object to be scripted.</span></span>  
  
3.  <span data-ttu-id="c763c-124">Разверните категорию объекта.</span><span class="sxs-lookup"><span data-stu-id="c763c-124">Expand the category of the object.</span></span> <span data-ttu-id="c763c-125">Например, разверните узел **Таблицы** или узел **Представления** .</span><span class="sxs-lookup"><span data-stu-id="c763c-125">For example, expand the **Tables** or **Views** node.</span></span>  
  
4.  <span data-ttu-id="c763c-126">Щелкните объект правой кнопкой мыши, наведите указатель на пункт **скрипт \<object type> как**, например, на пункт **создать скрипт для таблицы**.</span><span class="sxs-lookup"><span data-stu-id="c763c-126">Right-click the object, point to **Script \<object type> as**, For example, point to **Script Table as**.</span></span>  
  
5.  <span data-ttu-id="c763c-127">Укажите тип скрипта, например **Создать** или **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="c763c-127">Point to the script type, such as **Create to** or **Alter to**.</span></span>  
  
6.  <span data-ttu-id="c763c-128">Выберите расположение для сохранения скрипта, например **Новое окно редактора запросов** или **Буфер обмена**.</span><span class="sxs-lookup"><span data-stu-id="c763c-128">Select the location to save the script, such as **New Query Editor Window** or **Clipboard**.</span></span>  
  
##  <a name="to-generate-a-script-of-two-objects-using-object-explorer"></a><a name="ScriptTwoObjectsOE"></a> <span data-ttu-id="c763c-129">Создание скрипта для двух объектов с помощью обозревателя объектов</span><span class="sxs-lookup"><span data-stu-id="c763c-129">To generate a script of two objects using Object Explorer</span></span>  
 <span data-ttu-id="c763c-130">**Создание скрипта для двух объектов с помощью обозревателя объектов**</span><span class="sxs-lookup"><span data-stu-id="c763c-130">**To script two objects using Object Explorer**</span></span>  
  
 <span data-ttu-id="c763c-131">Иногда возникает необходимость создать скрипт с несколькими действиями, например удаление процедуры с последующим созданием другой процедуры, создание таблицы и ее изменение.</span><span class="sxs-lookup"><span data-stu-id="c763c-131">Sometimes you may want a script with multiple options, such as drop a procedure and then create a procedure, or create a table and then alter a table.</span></span> <span data-ttu-id="c763c-132">Следующие процедуры создания скриптов для нескольких объектов также можно использовать, если необходимо создать скрипт, который ссылается на различные типы объектов, например таблицы, представления или хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="c763c-132">The processes below for generating scripts of multiple objects also work if you need to create a script that references different types of objects, such as tables, views, and stored procedures.</span></span>  
  
1.  <span data-ttu-id="c763c-133">В обозревателе объектов подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="c763c-133">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c763c-134">Разверните узел **Базы данных**, а затем разверните базу данных, содержащую объекты, для которых необходимо создать скрипт.</span><span class="sxs-lookup"><span data-stu-id="c763c-134">Expand **Databases**, and then expand the database containing the objects to be scripted.</span></span>  
  
3.  <span data-ttu-id="c763c-135">Щелкните правой кнопкой мыши первый объект, который необходимо создать в скрипте, наведите указатель на пункт **скрипт \<object type> как**и в области **Сохранить как** выберите **новое окно редактора запросов** в качестве назначения выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c763c-135">Right-click the first object to be scripted, point to **Script \<object type> as**, and in the **Save as** selections chooses **New Query Editor Window** as the output destination.</span></span>  
  
4.  <span data-ttu-id="c763c-136">Перейдите ко второму объекту, который необходимо включить в скрипт.</span><span class="sxs-lookup"><span data-stu-id="c763c-136">Navigate to the second object you want to script.</span></span>  
  
5.  <span data-ttu-id="c763c-137">Щелкните правой кнопкой мыши объект, наведите указатель на пункт **скрипт \<object type> как**и в области **Сохранить как** выберите пункт **буфер обмена** в качестве назначения выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c763c-137">Right-click the object, point to **Script \<object type> as**, and in the **Save as** selections chooses **Clipboard** as the output destination.</span></span>  
  
6.  <span data-ttu-id="c763c-138">В окно редактора запросов, открытое для первого объекта, вставьте из буфера обмена скрипт для второго объекта.</span><span class="sxs-lookup"><span data-stu-id="c763c-138">In the Query Editor window opened for the first object, paste the script for the second object from the clipboard.</span></span>  
  
##  <a name="to-generate-a-script-of-two-objects-using-object-explorer-details"></a><a name="ScriptTwoObjectsOED"></a> <span data-ttu-id="c763c-139">Создание скрипта для двух объектов с помощью данных обозревателя объектов</span><span class="sxs-lookup"><span data-stu-id="c763c-139">To generate a script of two objects using Object Explorer Details</span></span>  
 <span data-ttu-id="c763c-140">**Создание скрипта для двух объектов с помощью данных обозревателя объектов**</span><span class="sxs-lookup"><span data-stu-id="c763c-140">**To script two objects using Object Explorer Details**</span></span>  
  
 <span data-ttu-id="c763c-141">Для создания скрипта для нескольких объектов одной категории можно использовать панель **Подробности обозревателя объектов** .</span><span class="sxs-lookup"><span data-stu-id="c763c-141">You can use the **Object Explorer Details** pane to generate a script for mutliple objects of the same category.</span></span>  
  
1.  <span data-ttu-id="c763c-142">В обозревателе объектов подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="c763c-142">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c763c-143">Разверните узел **Базы данных**, а затем разверните базу данных, содержащую объекты, для которых необходимо создать скрипт.</span><span class="sxs-lookup"><span data-stu-id="c763c-143">Expand **Databases**, and then expand the database containing the objects to be scripted.</span></span>  
  
3.  <span data-ttu-id="c763c-144">Разверните узел категории типов объектов, для которых требуется создать скрипт, например узел **Таблицы** .</span><span class="sxs-lookup"><span data-stu-id="c763c-144">Expand the category node of the types of object you want to script, such as the **Tables** node.</span></span>  
  
4.  <span data-ttu-id="c763c-145">Откройте панель **Подробности обозревателя объектов** . Для этого нажмите клавишу **F7**или откройте меню **Вид** и выберите пункт **Подробности обозревателя объектов**.</span><span class="sxs-lookup"><span data-stu-id="c763c-145">Open the **Object Explorer Details** pane by either selecting **F7**, or opening the **View** menu and selecting **Object Explorer Details**.</span></span>  
  
5.  <span data-ttu-id="c763c-146">Щелкните левой кнопкой один из объектов, который нужно включить в скрипт.</span><span class="sxs-lookup"><span data-stu-id="c763c-146">Left-click one of the objects you want to script.</span></span>  
  
6.  <span data-ttu-id="c763c-147">Удерживая клавишу Crtl, щелкните левой кнопкой второй объект, который необходимо включить в скрипт.</span><span class="sxs-lookup"><span data-stu-id="c763c-147">Crtl + left-click the second object you want to script.</span></span>  
  
7.  <span data-ttu-id="c763c-148">Щелкните правой кнопкой мыши один из выбранных объектов и выберите команду **создать скрипт \<object type> как**.</span><span class="sxs-lookup"><span data-stu-id="c763c-148">Right-click one of the selected objects, and select **Script \<object type> as**.</span></span>  
  
  
