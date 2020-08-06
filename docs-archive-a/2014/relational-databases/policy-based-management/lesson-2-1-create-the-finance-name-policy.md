---
title: Создание политики имен для базы данных Finance | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 56b2c852-fd69-4cd2-9b5d-977467b94fd9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 44ffff45f126d2ad9b73c5b8410b8f89ad2b0604
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655675"
---
# <a name="create-the-finance-name-policy"></a><span data-ttu-id="b3878-102">Создание политики имен финансов</span><span class="sxs-lookup"><span data-stu-id="b3878-102">Create the Finance Name Policy</span></span>
  <span data-ttu-id="b3878-103"> В этой задаче создается база данных с именем Finance, а затем формируется условие, требующее, чтобы все таблицы начинались с букв **fintbl**.</span><span class="sxs-lookup"><span data-stu-id="b3878-103">In this task, you will create a database named Finance, and then create a condition that requires all tables to start with the letters **fintbl**.</span></span> <span data-ttu-id="b3878-104">После этого создается политика и категория политики по обеспечению стандарта именования таблиц в базе данных Finance.</span><span class="sxs-lookup"><span data-stu-id="b3878-104">Then, you will create a policy and policy category to enforce a naming standard for tables in the Finance database.</span></span>  
  
### <a name="to-create-the-finance-database"></a><span data-ttu-id="b3878-105">Создание базы данных Finance</span><span class="sxs-lookup"><span data-stu-id="b3878-105">To create the Finance database</span></span>  
  
1.  <span data-ttu-id="b3878-106">В среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]откройте окно запросов и выполните следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="b3878-106">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], open a query window and execute the following statement:</span></span>  
  
    ```  
    CREATE DATABASE Finance ;  
    GO  
    ```  
  
2.  <span data-ttu-id="b3878-107">В обозревателе объектов щелкните **Базы данных**и нажмите клавишу F5 для обновления списка баз данных.</span><span class="sxs-lookup"><span data-stu-id="b3878-107">In Object Explorer, click **Databases**, and then press F5 to refresh the list of databases.</span></span>  
  
### <a name="to-create-the-finance-tables-condition"></a><span data-ttu-id="b3878-108">Создание условия «Таблицы Finance»</span><span class="sxs-lookup"><span data-stu-id="b3878-108">To create the Finance Tables condition</span></span>  
  
1.  <span data-ttu-id="b3878-109">В обозревателе объектов раскройте узлы **Управление**и **Управление политиками**, щелкните правой кнопкой мыши узел **Условия**и выберите пункт **Создать условие**.</span><span class="sxs-lookup"><span data-stu-id="b3878-109">In Object Explorer, expand **Management**, expand **Policy Management**, right-click **Conditions**, and then click **New Condition**.</span></span>  
  
2.  <span data-ttu-id="b3878-110">В диалоговом окне **Создание нового условия** в поле **Имя** введите **Finance Tables**.</span><span class="sxs-lookup"><span data-stu-id="b3878-110">In the **Create New Condition** dialog box, in the **Name** box, type **Finance Tables**.</span></span>  
  
3.  <span data-ttu-id="b3878-111">В списке **Аспект** выберите **Многокомпонентное имя**.</span><span class="sxs-lookup"><span data-stu-id="b3878-111">In the **Facet** list, select **Multipart Name**.</span></span>  
  
4.  <span data-ttu-id="b3878-112">В области **выражение** в поле **поле** выберите \*\* \@ имя\*\*; в поле **оператор** выберите **Like**, а в поле **значение** введите **' fintbl% '** , чтобы все имена таблиц начинались с букв **fintbl**.</span><span class="sxs-lookup"><span data-stu-id="b3878-112">In the **Expression** area, in the **Field** box, select **\@Name**; in the **Operator** box, select **Like**; and in the **Value** box, type **'fintbl%'** to force all table names to start with the letters **fintbl**.</span></span>  
  
5.  <span data-ttu-id="b3878-113">На странице **Описание** введите **Имена таблиц Finance должны начинаться с букв "fintbl"**, а затем нажмите кнопку **ОК** для создания условия.</span><span class="sxs-lookup"><span data-stu-id="b3878-113">On the **Description** page, type **Finance table names must begin with fintbl**, and then click **OK** to create the condition.</span></span>  
  
### <a name="to-create-the-finance-name-policy"></a><span data-ttu-id="b3878-114">Создание политики имен Finance</span><span class="sxs-lookup"><span data-stu-id="b3878-114">To create the Finance Name policy</span></span>  
  
1.  <span data-ttu-id="b3878-115">В обозревателе объектов щелкните правой кнопкой мыши папку **Политики**и выберите в контекстном меню пункт **Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="b3878-115">In Object Explorer, right-click **Policies**, and then click **New Policy**.</span></span>  
  
2.  <span data-ttu-id="b3878-116">В диалоговом окне **Создание новой политики** в поле **Имя** введите **Finance Name**.</span><span class="sxs-lookup"><span data-stu-id="b3878-116">In the **Create New Policy** dialog box, in the **Name** box, type **Finance Name**.</span></span>  
  
3.  <span data-ttu-id="b3878-117">В списке **Проверить условия** выберите пункт **Таблицы Finance**.</span><span class="sxs-lookup"><span data-stu-id="b3878-117">In the **Check condition** list, select **Finance Tables**.</span></span> <span data-ttu-id="b3878-118">Он находится в области **Многокомпонентное имя** .</span><span class="sxs-lookup"><span data-stu-id="b3878-118">This is in the **Multipart Name** area.</span></span>  
  
4.  <span data-ttu-id="b3878-119">В области **Применить к** отображается список объектов баз данных, к которым можно применить эту политику.</span><span class="sxs-lookup"><span data-stu-id="b3878-119">In the **Against** area you will see a list of the database objects that could apply this policy.</span></span> <span data-ttu-id="b3878-120">Установите флажок **Каждая таблица**.</span><span class="sxs-lookup"><span data-stu-id="b3878-120">Select the check box for **Every Table**.</span></span>  
  
5.  <span data-ttu-id="b3878-121">В области **Каждая база данных** разверните раздел **Каждый**и нажмите **Создать условие**.</span><span class="sxs-lookup"><span data-stu-id="b3878-121">In the **Every Database** area, expand **Every**, and then click **New condition**.</span></span>  
  
6.  <span data-ttu-id="b3878-122">В диалоговом окне **Создание нового условия** в поле **Имя** введите **База данных Finance**.</span><span class="sxs-lookup"><span data-stu-id="b3878-122">In the **Create New Condition** dialog box, in the **Name** box, type **Finance Database**.</span></span>  
  
7.  <span data-ttu-id="b3878-123">В поле **выражение** введите выражение, чтобы включить \*\* \@ имя = "Finance"\*\*, а затем нажмите кнопку **ОК** , чтобы закрыть страницу условия.</span><span class="sxs-lookup"><span data-stu-id="b3878-123">In the **Expression** box, complete the expression to include **\@Name = 'Finance'**, and then click **OK** to close the condition page.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b3878-124">Возможно, потребуется выйти из поля **Значение** для включения кнопки **ОК** .</span><span class="sxs-lookup"><span data-stu-id="b3878-124">You might have to tab out of the **Value** box to enable the **OK** button.</span></span>  
  
8.  <span data-ttu-id="b3878-125">В списке **Режим оценки** выберите **При изменении: запретить**.</span><span class="sxs-lookup"><span data-stu-id="b3878-125">In the **Evaluation Mode** list, select **On change: prevent**.</span></span> <span data-ttu-id="b3878-126">Это обеспечит создание политикой триггера базы данных в базе данных Finance.</span><span class="sxs-lookup"><span data-stu-id="b3878-126">This will enforce the policy by creating a database trigger on the Finance database.</span></span>  
  
9. <span data-ttu-id="b3878-127">Установите флажок **Включено** .</span><span class="sxs-lookup"><span data-stu-id="b3878-127">Select the **Enabled** list.</span></span> <span data-ttu-id="b3878-128">(Флажок **Включено** не применяется к политикам **По запросу** .)</span><span class="sxs-lookup"><span data-stu-id="b3878-128">(The **Enabled** box does not apply to **On demand** policies.)</span></span>  
  
10. <span data-ttu-id="b3878-129">В списке **Ограничение сервера** выберите пункт **Нет**.</span><span class="sxs-lookup"><span data-stu-id="b3878-129">In the **Server restriction** list, select **None**.</span></span>  
  
11. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-create-the-finance-policy-category"></a><span data-ttu-id="b3878-130">Создание категории политики Finance</span><span class="sxs-lookup"><span data-stu-id="b3878-130">To create the Finance policy category</span></span>  
  
1.  <span data-ttu-id="b3878-131">В обозревателе объектов разверните узел **Управление**, щелкните правой кнопкой мыши узел **Управление политиками**и выберите пункт **Управление категориями**.</span><span class="sxs-lookup"><span data-stu-id="b3878-131">In Object Explorer, expand **Management**, right-click **Policy Management**, and then click **Manage Categories**.</span></span>  
  
2.  <span data-ttu-id="b3878-132">В диалоговом окне **Управление категориями политики** в поле **имя**введите `Finance` пустое поле и снимите флажок затребовать **подписки базы данных**.</span><span class="sxs-lookup"><span data-stu-id="b3878-132">In the **Manage Policy Categories** dialog box, under **Name**, type `Finance` in the blank box, and then clear **Mandate Database Subscriptions**.</span></span> <span data-ttu-id="b3878-133">Параметр**Сделать подписки базы данных обязательными** принудительно подписывает каждую базу данных в экземпляре на политики, которые относятся к данной категории политик.</span><span class="sxs-lookup"><span data-stu-id="b3878-133">**Mandate Database Subscriptions** will force every database in the instance to subscribe to the policies that belong to this policy category.</span></span> <span data-ttu-id="b3878-134">В рамках этого занятия только база данных Finance должна быть подписана на политику "Finance Name".</span><span class="sxs-lookup"><span data-stu-id="b3878-134">For this lesson, only the Finance database should subscribe to the Finance Name policy.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b3878-135">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="b3878-135">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b3878-136">Подписка на политику имен финансов и ее проверка</span><span class="sxs-lookup"><span data-stu-id="b3878-136">Subscribe to and Check the Finance Name Policy</span></span>](lesson-2-2-subscribe-to-and-check-the-finance-name-policy.md)  
  
  
