---
title: Занятие 12. Создание ролей | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 984face4-00fc-46d3-8ae1-9755bf737bdf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 962cd19726a5404de81e20a2209b25b9cc277e21
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654551"
---
# <a name="lesson-12-create-roles"></a><span data-ttu-id="bc1ee-102">Урок 12. Создание ролей</span><span class="sxs-lookup"><span data-stu-id="bc1ee-102">Lesson 12: Create Roles</span></span>
  <span data-ttu-id="bc1ee-103">На этом занятии мы создадим роли.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-103">In this lesson, you will create roles.</span></span> <span data-ttu-id="bc1ee-104">Роли обеспечивают безопасность данных и объектов базы данных модели, разрешая доступ только тем пользователям Windows, которые являются членами роли.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-104">Roles provide model database object and data security by limiting access to only those Windows users which are role members.</span></span> <span data-ttu-id="bc1ee-105">Каждая роль определяется с помощью одного разрешения: "Нет", "Чтение", "Чтение и обработка", "Обработка" или "Администратор".</span><span class="sxs-lookup"><span data-stu-id="bc1ee-105">Each role is defined with a single permission: None, Read, Read and Process, Process, or Administrator.</span></span> <span data-ttu-id="bc1ee-106">Роли могут определяться во время разработки моделей с помощью диалогового окна «Диспетчер ролей» в среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc1ee-106">Roles can be defined during model authoring by using the Role Manager dialog box in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="bc1ee-107">После развертывания модели ролями можно управлять с помощью среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc1ee-107">After a model has been deployed, you can manage roles by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="bc1ee-108">Дополнительные сведения см. в разделе [Роли (табличные службы SSAS)](tabular-models/roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="bc1ee-108">To learn more, see [Roles &#40;SSAS Tabular&#41;](tabular-models/roles-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc1ee-109">Для выполнения этого учебника создавать роли не обязательно.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-109">Creating roles is not necessary to complete this tutorial.</span></span> <span data-ttu-id="bc1ee-110">По умолчанию учетная запись, с которой вы выполнили вход, будет иметь права администратора для модели.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-110">By default, the account you are currently logged in with will have Administrator privileges on the model.</span></span> <span data-ttu-id="bc1ee-111">Однако, чтобы разрешить другим пользователям в организации просматривать модель с помощью клиентского приложения для создания отчетов, необходимо создать по крайней мере одну роль с разрешением «Чтение» и добавить этих пользователей в качестве ее членов.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-111">However, to allow other users in your organization to browse the model by using a reporting client application, you must create at least one role with Read permissions and add those users as members.</span></span>  
  
 <span data-ttu-id="bc1ee-112">Мы создадим три роли.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-112">You will create three roles:</span></span>  
  
-   <span data-ttu-id="bc1ee-113">Менеджер по продажам — эта роль может включать пользователей в Организации, для которых требуется разрешение на чтение всех объектов и данных модели.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-113">Sales Manager - This role can include users in your organization for which you want to have Read permission to all model objects and data.</span></span>  
  
-   <span data-ttu-id="bc1ee-114">Аналитик продаж — эта роль может включать пользователей в Организации, для которых требуется только просматривать данные, связанные с продажами в США (США).</span><span class="sxs-lookup"><span data-stu-id="bc1ee-114">Sales Analyst US - This role can include users in your organization for which you want only to be able to browse data related to sales in the US (United States).</span></span> <span data-ttu-id="bc1ee-115">Для этой роли вы определите с помощью формулы DAX *фильтр строк*, который ограничит для членов роли доступ к данным только информацией по США.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-115">For this role, you will use a DAX formula to define a *Row Filter*, which restricts members to browse data only for the United States.</span></span>  
  
-   <span data-ttu-id="bc1ee-116">Администратор. Эта роль может включать пользователей, для которых требуется разрешение администратора, которое обеспечивает неограниченный доступ и разрешения на выполнение административных задач в базе данных model.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-116">Administrator - This role can include users for which you want to have Administrator permission, which allows unlimited access and permissions to perform administrative tasks on the model database.</span></span>  
  
 <span data-ttu-id="bc1ee-117">Поскольку учетные записи пользователей и групп Windows в вашей организации являются уникальными, вы можете добавлять учетные записи членов вашей организации в качестве членов ролей.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-117">Because Windows user and group accounts in your organization are unique, you can add accounts from your particular organization to members.</span></span> <span data-ttu-id="bc1ee-118">Однако в этом учебнике список членов ролей можно также оставить пустым.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-118">However, for this tutorial, you can also leave the members blank.</span></span> <span data-ttu-id="bc1ee-119">Вы все же сможете проверить действие каждой из ролей позже, в занятии 12 "Анализ в Excel".</span><span class="sxs-lookup"><span data-stu-id="bc1ee-119">You will still be able to test the effect of each role later in Lesson 12: Analyze in Excel.</span></span>  
  
 <span data-ttu-id="bc1ee-120">Предполагаемое время выполнения этого занятия: **15 минут**</span><span class="sxs-lookup"><span data-stu-id="bc1ee-120">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bc1ee-121">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="bc1ee-121">Prerequisites</span></span>  
 <span data-ttu-id="bc1ee-122">Этот раздел входит в учебник по табличному моделированию, который следует изучать в предложенном порядке.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-122">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="bc1ee-123">Прежде чем выполнять задания в этом занятии, необходимо завершить предыдущее [Занятие 11. Создание секций](lesson-10-create-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="bc1ee-123">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 11: Create Partitions](lesson-10-create-partitions.md).</span></span>  
  
## <a name="create-roles"></a><span data-ttu-id="bc1ee-124">Создание ролей</span><span class="sxs-lookup"><span data-stu-id="bc1ee-124">Create Roles</span></span>  
  
#### <a name="to-create-a-sales-manager-user-role"></a><span data-ttu-id="bc1ee-125">Создание роли пользователя "Менеджер по продажам"</span><span class="sxs-lookup"><span data-stu-id="bc1ee-125">To create a Sales Manager user role</span></span>  
  
1.  <span data-ttu-id="bc1ee-126">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]в меню **Модель** выберите пункт **Роли**.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-126">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Roles**.</span></span>  
  
2.  <span data-ttu-id="bc1ee-127">В диалоговом окне **Диспетчер ролей** выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-127">In the **Role Manager** dialog box, click **New**.</span></span>  
  
     <span data-ttu-id="bc1ee-128">В список добавляется новая роль с разрешением "Нет".</span><span class="sxs-lookup"><span data-stu-id="bc1ee-128">A new role with the None permission is added to the list.</span></span>  
  
3.  <span data-ttu-id="bc1ee-129">Щелкните новую роль, а затем в столбце **имя** переименуйте роль в `Internet Sales Manager` .</span><span class="sxs-lookup"><span data-stu-id="bc1ee-129">Click on the new role, and then in the **Name** column, rename the role to `Internet Sales Manager`.</span></span>  
  
4.  <span data-ttu-id="bc1ee-130">В столбце **Разрешения** щелкните раскрывающийся список и выберите разрешение **Чтение**.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-130">In the **Permissions** column, click the dropdown list, and then select the **Read** permission.</span></span>  
  
5.  <span data-ttu-id="bc1ee-131">Дополнительно: откройте вкладку **Члены**, а затем щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-131">Optional: Click on the **Members** tab, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="bc1ee-132">В диалоговом окне **Выбор пользователей или групп** укажите пользователей или группы Windows из вашей организации, которым вы хотите назначить эту роль.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-132">In the **Select Users or Groups** dialog box, enter the Windows users or groups from your organization you want to include in the role.</span></span>  
  
7.  <span data-ttu-id="bc1ee-133">Проверьте параметры и нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="bc1ee-133">Verify your selections, and then click **OK**</span></span>  
  
#### <a name="to-create-a-sales-analyst-us-user-role"></a><span data-ttu-id="bc1ee-134">Создание роли пользователя аналитика продаж в США</span><span class="sxs-lookup"><span data-stu-id="bc1ee-134">To create a Sales Analyst US user role</span></span>  
  
1.  <span data-ttu-id="bc1ee-135">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]в меню **Модель** выберите пункт **Роли**.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-135">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Roles**.</span></span>  
  
2.  <span data-ttu-id="bc1ee-136">В диалоговом окне **Диспетчер ролей** выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-136">In the **Role Manager** dialog box, click **New**.</span></span>  
  
     <span data-ttu-id="bc1ee-137">В список добавляется новая роль с разрешением "Нет".</span><span class="sxs-lookup"><span data-stu-id="bc1ee-137">A new role with the None permission is added to the list.</span></span>  
  
3.  <span data-ttu-id="bc1ee-138">Щелкните новую роль, а затем в столбце **имя** переименуйте роль в `Internet Sales US` .</span><span class="sxs-lookup"><span data-stu-id="bc1ee-138">Click on the new role, and then in the **Name** column, rename the role to `Internet Sales US`.</span></span>  
  
4.  <span data-ttu-id="bc1ee-139">В столбце **Разрешения** щелкните раскрывающийся список и выберите разрешение **Чтение**.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-139">In the **Permissions** column, click the dropdown list, and then select the **Read** permission.</span></span>  
  
5.  <span data-ttu-id="bc1ee-140">Перейдите на вкладку "Фильтры строк" и, выбрав только таблицу **Geography** , в столбце "Фильтр DAX" введите следующую формулу:</span><span class="sxs-lookup"><span data-stu-id="bc1ee-140">Click on the Row Filters tab, and then for the **Geography** table only, in the DAX Filter column, type the following formula:</span></span>  
  
     `=Geography[Country Region Code] = "US"`  
  
     <span data-ttu-id="bc1ee-141">Формула фильтра строк должна разрешаться в логическое значение (TRUE/FALSE).</span><span class="sxs-lookup"><span data-stu-id="bc1ee-141">A Row Filter formula must resolve to a Boolean (TRUE/FALSE) value.</span></span> <span data-ttu-id="bc1ee-142">С помощью этой формулы вы указываете, что пользователю будут видны только строки со значением кода региона страны "US".</span><span class="sxs-lookup"><span data-stu-id="bc1ee-142">With this formula, you are specifying that only rows with the Country Region Code value of "US" be visible to the user.</span></span>  
  
     <span data-ttu-id="bc1ee-143">Завершив построение формулы, нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-143">When you have finished building the formula, press ENTER.</span></span>  
  
6.  <span data-ttu-id="bc1ee-144">Дополнительно: откройте вкладку **Члены**, а затем щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-144">Optional: Click on the **Members** tab, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="bc1ee-145">В диалоговом окне **Выбор пользователей или групп** укажите пользователей или группы Windows из вашей организации, которым вы хотите назначить эту роль.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-145">In the **Select Users or Groups** dialog box, enter the Windows users or groups from your organization you want to include in the role.</span></span>  
  
8.  <span data-ttu-id="bc1ee-146">Проверьте параметры и нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="bc1ee-146">Verify your selections, and then click **OK**</span></span>  
  
#### <a name="to-create-an-administrator-role"></a><span data-ttu-id="bc1ee-147">Создание роли администратора</span><span class="sxs-lookup"><span data-stu-id="bc1ee-147">To create an Administrator role</span></span>  
  
1.  <span data-ttu-id="bc1ee-148">В диалоговом окне **Диспетчер ролей** выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-148">In the **Role Manager** dialog box, click **New**.</span></span>  
  
2.  <span data-ttu-id="bc1ee-149">Щелкните новую роль, а затем в столбце **имя** переименуйте роль в `Internet Sales Administrator` .</span><span class="sxs-lookup"><span data-stu-id="bc1ee-149">Click on the new role, and then in the **Name** column, rename the role to `Internet Sales Administrator`.</span></span>  
  
3.  <span data-ttu-id="bc1ee-150">В столбце **Разрешения** щелкните раскрывающийся список и выберите разрешение **Администратор** .</span><span class="sxs-lookup"><span data-stu-id="bc1ee-150">In the **Permissions** column, click the dropdown list, and then select the **Administrator** permission.</span></span>  
  
4.  <span data-ttu-id="bc1ee-151">Перейдите на вкладку **Члены** и выберите команду **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="bc1ee-151">Click on the **Members** tab, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="bc1ee-152">В диалоговом окне **Выбор пользователей или групп** введите пользователей или группы Windows из вашей организации, которые нужно включить в роль (необязательно).</span><span class="sxs-lookup"><span data-stu-id="bc1ee-152">Optional: In the **Select Users or Groups** dialog box, enter the Windows users or groups from your organization you want to include in the role.</span></span>  
  
6.  <span data-ttu-id="bc1ee-153">Проверьте параметры и нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="bc1ee-153">Verify your selections, and then click **OK**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bc1ee-154">Next Steps</span><span class="sxs-lookup"><span data-stu-id="bc1ee-154">Next Steps</span></span>  
 <span data-ttu-id="bc1ee-155">Чтобы продолжить изучение этого учебника, перейдите к следующему занятию: [Занятие 13. Анализ в Excel](lesson-12-analyze-in-excel.md).</span><span class="sxs-lookup"><span data-stu-id="bc1ee-155">To continue this tutorial, go to the next lesson: Lesson: [Lesson 13: Analyze in Excel](lesson-12-analyze-in-excel.md).</span></span>  
  
  
