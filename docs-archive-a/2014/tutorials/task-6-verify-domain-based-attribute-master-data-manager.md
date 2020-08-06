---
title: Задача 6. Проверка создания атрибута на основе домена с помощью диспетчер основных данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6e90517a-910c-4c33-8f11-92ac3cff4fdc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ea26202ca9e607058b1e385957be3ea3d04038b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654647"
---
# <a name="task-6-verify-that-the-domain-based-attribute-is-created-using-master-data-manager"></a><span data-ttu-id="71a1e-102">Задача 6. Проверка создания атрибута на основе домена в диспетчере основных данных</span><span class="sxs-lookup"><span data-stu-id="71a1e-102">Task 6: Verify that the Domain-Based Attribute is Created using Master Data Manager</span></span>
  <span data-ttu-id="71a1e-103">В этой задаче вы проверите, создана ли сущность **Штат** в службах **MDS** и является ли атрибут **Штат** сущности **Поставщик** атрибутом на основе домена, который зависит от сущности **Штат**, с помощью **диспетчера основных данных**.</span><span class="sxs-lookup"><span data-stu-id="71a1e-103">In this task, you verify that the **State** entity is created in **MDS** and the **State** attribute of the **Supplier** entity is a domain-based attribute that depends on the **State** entity by using **Master Data Manager**.</span></span>

1.  <span data-ttu-id="71a1e-104">Перейдите в веб-приложение **диспетчера основных данных**.</span><span class="sxs-lookup"><span data-stu-id="71a1e-104">Switch to the **Master Data Manger** web application.</span></span>

2.  <span data-ttu-id="71a1e-105">Щелкните **Службы SQL Server 2012 Master Data Services** в верхней части экрана для перехода на домашнюю страницу.</span><span class="sxs-lookup"><span data-stu-id="71a1e-105">Click **SQL Server 2012 Master Data Services** at the top to get to the home page.</span></span>

3.  <span data-ttu-id="71a1e-106">Убедитесь, что выбрана модель **Поставщики**, и нажмите кнопку **Обозреватель**.</span><span class="sxs-lookup"><span data-stu-id="71a1e-106">Ensure that **Suppliers** model is selected and click **Explorer**.</span></span> <span data-ttu-id="71a1e-107">Вы можете перезагрузить страницу, если **Обозреватель** уже открыт.</span><span class="sxs-lookup"><span data-stu-id="71a1e-107">You could refresh the page if you already had **Explorer** open.</span></span>

4.  <span data-ttu-id="71a1e-108">Наведите указатель мыши на элемент **Сущности** в строке меню и обратите внимание, что теперь там две сущности: **Поставщик** и **Штат**.</span><span class="sxs-lookup"><span data-stu-id="71a1e-108">Hover your mouse over **Entities** on the menu bar and notice that now there are two entities: **Supplier** and **State**.</span></span>

     <span data-ttu-id="71a1e-109">![Меню сущностей с штатом и поставщиком](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-01.jpg "Меню сущностей с штатом и поставщиком")</span><span class="sxs-lookup"><span data-stu-id="71a1e-109">![Entities Menu with State and Supplier](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-01.jpg "Entities Menu with State and Supplier")</span></span>

5.  <span data-ttu-id="71a1e-110">Щелкните **Штат**, если сущность еще не открыта.</span><span class="sxs-lookup"><span data-stu-id="71a1e-110">Click **State** if the entity is not open already.</span></span>

6.  <span data-ttu-id="71a1e-111">Выберите **GA** из списка.</span><span class="sxs-lookup"><span data-stu-id="71a1e-111">Select **GA** from the list.</span></span>

7.  <span data-ttu-id="71a1e-112">На панели **Подробности** справа измените значение параметра **Имя** на **Джорджия** в **правой области** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="71a1e-112">In the **Details** pane to the right, change the **Name** to **Georgia** in the **right pane**, and click **OK**.</span></span>

8.  <span data-ttu-id="71a1e-113">Повторите предыдущие шаги для других штатов.</span><span class="sxs-lookup"><span data-stu-id="71a1e-113">Repeat the previous steps for other states.</span></span>

    |<span data-ttu-id="71a1e-114">Код</span><span class="sxs-lookup"><span data-stu-id="71a1e-114">Code</span></span>|<span data-ttu-id="71a1e-115">Имя</span><span class="sxs-lookup"><span data-stu-id="71a1e-115">Name</span></span>|
    |----------|----------|
    |<span data-ttu-id="71a1e-116">Целостности и доступности</span><span class="sxs-lookup"><span data-stu-id="71a1e-116">CA</span></span>|<span data-ttu-id="71a1e-117">Калифорния</span><span class="sxs-lookup"><span data-stu-id="71a1e-117">California</span></span>|
    |<span data-ttu-id="71a1e-118">CO</span><span class="sxs-lookup"><span data-stu-id="71a1e-118">CO</span></span>|<span data-ttu-id="71a1e-119">Колорадо</span><span class="sxs-lookup"><span data-stu-id="71a1e-119">Colorado</span></span>|
    |<span data-ttu-id="71a1e-120">IL</span><span class="sxs-lookup"><span data-stu-id="71a1e-120">IL</span></span>|<span data-ttu-id="71a1e-121">Иллинойс</span><span class="sxs-lookup"><span data-stu-id="71a1e-121">Illinois</span></span>|
    |<span data-ttu-id="71a1e-122">DC</span><span class="sxs-lookup"><span data-stu-id="71a1e-122">DC</span></span>|<span data-ttu-id="71a1e-123">Округ Колумбия</span><span class="sxs-lookup"><span data-stu-id="71a1e-123">District of Columbia</span></span>|
    |<span data-ttu-id="71a1e-124">FL</span><span class="sxs-lookup"><span data-stu-id="71a1e-124">FL</span></span>|<span data-ttu-id="71a1e-125">Флорида</span><span class="sxs-lookup"><span data-stu-id="71a1e-125">Florida</span></span>|
    |<span data-ttu-id="71a1e-126">AL</span><span class="sxs-lookup"><span data-stu-id="71a1e-126">AL</span></span>|<span data-ttu-id="71a1e-127">Алабама</span><span class="sxs-lookup"><span data-stu-id="71a1e-127">Alabama</span></span>|
    |<span data-ttu-id="71a1e-128">KY</span><span class="sxs-lookup"><span data-stu-id="71a1e-128">KY</span></span>|<span data-ttu-id="71a1e-129">Кентукки</span><span class="sxs-lookup"><span data-stu-id="71a1e-129">Kentucky</span></span>|
    |<span data-ttu-id="71a1e-130">MA</span><span class="sxs-lookup"><span data-stu-id="71a1e-130">MA</span></span>|<span data-ttu-id="71a1e-131">Массачусетс</span><span class="sxs-lookup"><span data-stu-id="71a1e-131">Massachusetts</span></span>|
    |<span data-ttu-id="71a1e-132">AZ</span><span class="sxs-lookup"><span data-stu-id="71a1e-132">AZ</span></span>|<span data-ttu-id="71a1e-133">Аризона</span><span class="sxs-lookup"><span data-stu-id="71a1e-133">Arizona</span></span>|
    |<span data-ttu-id="71a1e-134">MI</span><span class="sxs-lookup"><span data-stu-id="71a1e-134">MI</span></span>|<span data-ttu-id="71a1e-135">Мичиган</span><span class="sxs-lookup"><span data-stu-id="71a1e-135">Michigan</span></span>|
    |<span data-ttu-id="71a1e-136">MN</span><span class="sxs-lookup"><span data-stu-id="71a1e-136">MN</span></span>|<span data-ttu-id="71a1e-137">Миннесота</span><span class="sxs-lookup"><span data-stu-id="71a1e-137">Minnesota</span></span>|
    |<span data-ttu-id="71a1e-138">Нью-Джерси</span><span class="sxs-lookup"><span data-stu-id="71a1e-138">NJ</span></span>|<span data-ttu-id="71a1e-139">Нью-Джерси</span><span class="sxs-lookup"><span data-stu-id="71a1e-139">New Jersey</span></span>|
    |<span data-ttu-id="71a1e-140">NV</span><span class="sxs-lookup"><span data-stu-id="71a1e-140">NV</span></span>|<span data-ttu-id="71a1e-141">Невада</span><span class="sxs-lookup"><span data-stu-id="71a1e-141">Nevada</span></span>|
    |<span data-ttu-id="71a1e-142">Нью-Йорк</span><span class="sxs-lookup"><span data-stu-id="71a1e-142">NY</span></span>|<span data-ttu-id="71a1e-143">Нью-Йорк</span><span class="sxs-lookup"><span data-stu-id="71a1e-143">New York</span></span>|
    |<span data-ttu-id="71a1e-144">OH</span><span class="sxs-lookup"><span data-stu-id="71a1e-144">OH</span></span>|<span data-ttu-id="71a1e-145">Огайо</span><span class="sxs-lookup"><span data-stu-id="71a1e-145">Ohio</span></span>|
    |<span data-ttu-id="71a1e-146">ОК</span><span class="sxs-lookup"><span data-stu-id="71a1e-146">OK</span></span>|<span data-ttu-id="71a1e-147">Оклахома</span><span class="sxs-lookup"><span data-stu-id="71a1e-147">Oklahoma</span></span>|
    |<span data-ttu-id="71a1e-148">ИЛИ</span><span class="sxs-lookup"><span data-stu-id="71a1e-148">OR</span></span>|<span data-ttu-id="71a1e-149">Орегон</span><span class="sxs-lookup"><span data-stu-id="71a1e-149">Oregon</span></span>|
    |<span data-ttu-id="71a1e-150">PA</span><span class="sxs-lookup"><span data-stu-id="71a1e-150">PA</span></span>|<span data-ttu-id="71a1e-151">Пенсильвания</span><span class="sxs-lookup"><span data-stu-id="71a1e-151">Pennsylvania</span></span>|
    |<span data-ttu-id="71a1e-152">SC</span><span class="sxs-lookup"><span data-stu-id="71a1e-152">SC</span></span>|<span data-ttu-id="71a1e-153">Южная Каролина</span><span class="sxs-lookup"><span data-stu-id="71a1e-153">South Carolina</span></span>|
    |<span data-ttu-id="71a1e-154">KS</span><span class="sxs-lookup"><span data-stu-id="71a1e-154">KS</span></span>|<span data-ttu-id="71a1e-155">Канзас</span><span class="sxs-lookup"><span data-stu-id="71a1e-155">Kansas</span></span>|
    |<span data-ttu-id="71a1e-156">TN</span><span class="sxs-lookup"><span data-stu-id="71a1e-156">TN</span></span>|<span data-ttu-id="71a1e-157">Теннесси</span><span class="sxs-lookup"><span data-stu-id="71a1e-157">Tennessee</span></span>|
    |<span data-ttu-id="71a1e-158">TX</span><span class="sxs-lookup"><span data-stu-id="71a1e-158">TX</span></span>|<span data-ttu-id="71a1e-159">Техас</span><span class="sxs-lookup"><span data-stu-id="71a1e-159">Texas</span></span>|
    |<span data-ttu-id="71a1e-160">UT</span><span class="sxs-lookup"><span data-stu-id="71a1e-160">UT</span></span>|<span data-ttu-id="71a1e-161">Юта</span><span class="sxs-lookup"><span data-stu-id="71a1e-161">Utah</span></span>|
    |<span data-ttu-id="71a1e-162">VA</span><span class="sxs-lookup"><span data-stu-id="71a1e-162">VA</span></span>|<span data-ttu-id="71a1e-163">Виргиния</span><span class="sxs-lookup"><span data-stu-id="71a1e-163">Virginia</span></span>|
    |<span data-ttu-id="71a1e-164">WA</span><span class="sxs-lookup"><span data-stu-id="71a1e-164">WA</span></span>|<span data-ttu-id="71a1e-165">Вашингтон</span><span class="sxs-lookup"><span data-stu-id="71a1e-165">Washington</span></span>|
    |<span data-ttu-id="71a1e-166">WI</span><span class="sxs-lookup"><span data-stu-id="71a1e-166">WI</span></span>|<span data-ttu-id="71a1e-167">Висконсин</span><span class="sxs-lookup"><span data-stu-id="71a1e-167">Wisconsin</span></span>|
    |<span data-ttu-id="71a1e-168">HI</span><span class="sxs-lookup"><span data-stu-id="71a1e-168">HI</span></span>|<span data-ttu-id="71a1e-169">Гавайи</span><span class="sxs-lookup"><span data-stu-id="71a1e-169">Hawaii</span></span>|
    |<span data-ttu-id="71a1e-170">MD</span><span class="sxs-lookup"><span data-stu-id="71a1e-170">MD</span></span>|<span data-ttu-id="71a1e-171">Мэриленд</span><span class="sxs-lookup"><span data-stu-id="71a1e-171">Maryland</span></span>|
    |<span data-ttu-id="71a1e-172">CT</span><span class="sxs-lookup"><span data-stu-id="71a1e-172">CT</span></span>|<span data-ttu-id="71a1e-173">Коннектикут</span><span class="sxs-lookup"><span data-stu-id="71a1e-173">Connecticut</span></span>|

9. <span data-ttu-id="71a1e-174">Выберите любые записи штатов и щелкните **Просмотр транзакций** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="71a1e-174">Select any of the state entries and click **View Transactions** from the Toolbar.</span></span> <span data-ttu-id="71a1e-175">Транзакция для выполненного обновления должна появиться в списке транзакций.</span><span class="sxs-lookup"><span data-stu-id="71a1e-175">You should see the transaction for the update you just made is in the list of transactions.</span></span>

10. <span data-ttu-id="71a1e-176">Наведите указатель мыши на меню **Сущности** и выберите пункт **Поставщик**.</span><span class="sxs-lookup"><span data-stu-id="71a1e-176">Hover the mouse over **Entities** menu and click **Supplier**.</span></span>

11. <span data-ttu-id="71a1e-177">Теперь обратите внимание, что значение поля **Штат** можно изменить в области **Подробности** с помощью раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="71a1e-177">Now, notice that a value for the **State** field can be changed in the **Details** pane by using the drop-down list.</span></span> <span data-ttu-id="71a1e-178">Также можно увидеть, что в списке слева и в раскрывающемся списке на панели **Подробности** сначала отображается код, а затем название в фигурных скобках.</span><span class="sxs-lookup"><span data-stu-id="71a1e-178">You can also see that, in the list to the left and in the drop-down list in the **Details** pane, code is displayed first and then the name in curly braces.</span></span> <span data-ttu-id="71a1e-179">На панели **Подробности** можно также изменить любое другое значение.</span><span class="sxs-lookup"><span data-stu-id="71a1e-179">You can also change any other value in the **Details** pane.</span></span>

     <span data-ttu-id="71a1e-180">![Атрибут «Штат» с обновленными кодом и названиями](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-02.jpg "Атрибут «Штат» с обновленными кодом и названиями")</span><span class="sxs-lookup"><span data-stu-id="71a1e-180">![State Attribute with Updated Code and Names](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-02.jpg "State Attribute with Updated Code and Names")</span></span>

## <a name="next-step"></a><span data-ttu-id="71a1e-181">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="71a1e-181">Next Step</span></span>
 [<span data-ttu-id="71a1e-182">Задача 7. Просмотр изменений в диспетчере основных данных из Excel</span><span class="sxs-lookup"><span data-stu-id="71a1e-182">Task 7: Viewing Updates Made using Master Data Manager in Excel</span></span>](../../2014/tutorials/task-7-viewing-updates-made-using-master-data-manager-in-excel.md)


