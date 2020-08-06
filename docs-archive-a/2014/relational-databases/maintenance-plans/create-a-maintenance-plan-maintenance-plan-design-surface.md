---
title: Создание плана обслуживания (область конструктора планов обслуживания) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Maintenance Plan Design Surface
ms.assetid: 2ef803ee-a9f8-454a-ad63-fedcbe6838d1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 77e347720824198ba7d6abaddedd7a581ace98a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666578"
---
# <a name="create-a-maintenance-plan-maintenance-plan-design-surface"></a><span data-ttu-id="c7d22-102">Создание планов обслуживания (область конструктора планов обслуживания)</span><span class="sxs-lookup"><span data-stu-id="c7d22-102">Create a Maintenance Plan (Maintenance Plan Design Surface)</span></span>
  <span data-ttu-id="c7d22-103">В этом разделе описывается создание плана обслуживания одного или нескольких серверов с помощью области конструктора для плана обслуживания в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7d22-103">This topic describes how to create a single server or multiserver maintenance plan using the Maintenance Plan Design Surface in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="c7d22-104">**Мастер планов обслуживания** лучше подходит для создания простых планов обслуживания, а область конструктора позволяет использовать расширенные рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="c7d22-104">While the **Maintenance Plan Wizard** is best for creating basic maintenance plans, creating a plan using the design surface allows you to utilize enhanced workflow.</span></span>  
  
 <span data-ttu-id="c7d22-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="c7d22-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c7d22-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="c7d22-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c7d22-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c7d22-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c7d22-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="c7d22-108">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="c7d22-109">Создание плана обслуживания с помощью области конструктора планов обслуживания</span><span class="sxs-lookup"><span data-stu-id="c7d22-109">Creating a maintenance plan using the Maintenance Plan Design Surface</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c7d22-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="c7d22-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c7d22-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c7d22-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c7d22-112">Для создания многосерверного плана обслуживания необходимо настроить многосерверную среду, содержащую один главный сервер и один или несколько целевых серверов.</span><span class="sxs-lookup"><span data-stu-id="c7d22-112">To create a multiserver maintenance plan, a multiserver environment containing one master server and one or more target servers must be configured.</span></span> <span data-ttu-id="c7d22-113">План многосерверного обслуживания необходимо создать и хранить на главном сервере.</span><span class="sxs-lookup"><span data-stu-id="c7d22-113">Multiserver maintenance plans must be created and maintained on the master server.</span></span> <span data-ttu-id="c7d22-114">На целевых серверах эти планы можно просматривать, но нельзя хранить.</span><span class="sxs-lookup"><span data-stu-id="c7d22-114">These plans can be viewed, but not maintained, on target servers.</span></span>  
  
-   <span data-ttu-id="c7d22-115">Члены ролей **db_ssisadmin** и **dc_admin** могут повышать свои права доступа до **sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-115">Members of the **db_ssisadmin** and **dc_admin** roles may be able to elevate their privileges to **sysadmin**.</span></span> <span data-ttu-id="c7d22-116">Такое повышение прав доступа может происходить, поскольку эти роли могут изменять пакеты служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , а эти пакеты могут выполняться [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при помощи контекста безопасности **sysadmin** агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c7d22-116">This elevation of privilege can occur because these roles can modify [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages; these packages can be executed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the **sysadmin** security context of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="c7d22-117">Чтобы предотвратить такое повышение прав доступа при выполнении планов обслуживания, наборов элементов сбора данных и других пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , настройте задания агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , запускающие пакеты, на использование учетной записи-посредника с ограниченными правами доступа или добавьте в роли **db_ssisadmin** и **dc_admin** только членов роли **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="c7d22-117">To guard against this elevation of privilege when running maintenance plans, data collection sets, and other [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs that run packages to use a proxy account with limited privileges or only add **sysadmin** members to the **db_ssisadmin** and **dc_admin** roles.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c7d22-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="c7d22-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c7d22-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="c7d22-119">Permissions</span></span>  
 <span data-ttu-id="c7d22-120">Для создания планов обслуживания и работы с ними пользователь должен быть членом предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="c7d22-120">To create or manage maintenance plans, you must be a member of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="c7d22-121">В обозревателе объектов узел **Планы обслуживания** отображается только для пользователей, являющихся членами предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="c7d22-121">Object Explorer only displays the **Maintenance Plans** node for users who are members of the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-maintenance-plan-design-surface"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c7d22-122">Использование области конструктора планов обслуживания</span><span class="sxs-lookup"><span data-stu-id="c7d22-122">Using Maintenance Plan Design Surface</span></span>  
  
#### <a name="to-create-a-maintenance-plan"></a><span data-ttu-id="c7d22-123">Создание плана обслуживания</span><span class="sxs-lookup"><span data-stu-id="c7d22-123">To create a maintenance plan</span></span>  
  
1.  <span data-ttu-id="c7d22-124">В обозревателе объектов щелкните знак «плюс», чтобы развернуть сервер, где нужно создать план обслуживания.</span><span class="sxs-lookup"><span data-stu-id="c7d22-124">In Object Explorer, click the plus sign to expand the server where you want to create a maintenance plan.</span></span>  
  
2.  <span data-ttu-id="c7d22-125">Щелкните знак «плюс», чтобы развернуть папку **Управление** .</span><span class="sxs-lookup"><span data-stu-id="c7d22-125">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="c7d22-126">Щелкните правой кнопкой мыши папку **Планы обслуживания** и выберите команду **Создать план обслуживания**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-126">Right-click the **Maintenance Plans** folder and select **New Maintenance Plan**.</span></span>  
  
4.  <span data-ttu-id="c7d22-127">В диалоговом окне **Создание плана обслуживания** в поле **Имя** введите имя плана и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-127">In the **New Maintenance Plan** dialog box, in the **Name** box, type a name for the plan and click **OK**.</span></span> <span data-ttu-id="c7d22-128">Откроется панель элементов и область _maintenance_plan_name_ **[Конструктор]** с вложенным планом **Subplan_1** в основной сетке.</span><span class="sxs-lookup"><span data-stu-id="c7d22-128">This opens the  Toolbox and the _maintenance_plan_name_ **[Design]** surface with the **Subplan_1** subplan created in the main grid.</span></span>  
  
     <span data-ttu-id="c7d22-129">В заголовке области конструктора доступны следующие команды.</span><span class="sxs-lookup"><span data-stu-id="c7d22-129">The following options are available in the design space's header.</span></span>  
  
     <span data-ttu-id="c7d22-130">**Добавление вложенного плана**</span><span class="sxs-lookup"><span data-stu-id="c7d22-130">**Add Subplan**</span></span>  
     <span data-ttu-id="c7d22-131">Добавляет настраиваемый вложенный план.</span><span class="sxs-lookup"><span data-stu-id="c7d22-131">Adds a subplan that you can configure.</span></span>  
  
     <span data-ttu-id="c7d22-132">**Свойства вложенного плана**</span><span class="sxs-lookup"><span data-stu-id="c7d22-132">**Subplan Properties**</span></span>  
     <span data-ttu-id="c7d22-133">Открывает диалоговое окно **Свойства вложенного плана** для выбранного вложенного плана в основной сетке.</span><span class="sxs-lookup"><span data-stu-id="c7d22-133">Displays the **Subplan Properties** dialog box for the selected subplan in the main grid.</span></span> <span data-ttu-id="c7d22-134">Чтобы открыть диалоговое окно **Свойства вложенного плана** , также можно дважды щелкнуть вложенный план в сетке.</span><span class="sxs-lookup"><span data-stu-id="c7d22-134">Alternately, double-click a subplan in the grid to display the **Subplan Properties** dialog box.</span></span> <span data-ttu-id="c7d22-135">Дополнительные сведения об этом диалоговом окне см. ниже.</span><span class="sxs-lookup"><span data-stu-id="c7d22-135">See below for more information on this dialog box.</span></span>  
  
     <span data-ttu-id="c7d22-136">**Удаление выбранного вложенного плана**</span><span class="sxs-lookup"><span data-stu-id="c7d22-136">**Delete Selected Subplan**</span></span>  
     <span data-ttu-id="c7d22-137">Удаляет выбранный вложенный план.</span><span class="sxs-lookup"><span data-stu-id="c7d22-137">Deletes the selected subplan.</span></span>  
  
     <span data-ttu-id="c7d22-138">**Расписание вложенного плана**</span><span class="sxs-lookup"><span data-stu-id="c7d22-138">**Subplan Schedule**</span></span>  
     <span data-ttu-id="c7d22-139">Открывает диалоговое окно **Создание расписания задания** для выбранного вложенного плана.</span><span class="sxs-lookup"><span data-stu-id="c7d22-139">Displays the **New Job Schedule** dialog box for the selected subplan.</span></span>  
  
     <span data-ttu-id="c7d22-140">**Удаление расписания**</span><span class="sxs-lookup"><span data-stu-id="c7d22-140">**Remove Schedule**</span></span>  
     <span data-ttu-id="c7d22-141">Удаляет расписание из выбранного вложенного плана.</span><span class="sxs-lookup"><span data-stu-id="c7d22-141">Removes a schedule from the selected subplan.</span></span>  
  
     <span data-ttu-id="c7d22-142">**Управление подключениями**</span><span class="sxs-lookup"><span data-stu-id="c7d22-142">**Manage Connections**</span></span>  
     <span data-ttu-id="c7d22-143">Открывает диалоговое окно **Управление соединениями** .</span><span class="sxs-lookup"><span data-stu-id="c7d22-143">Displays the **Manage Connections** dialog box.</span></span> <span data-ttu-id="c7d22-144">Используется для добавления дополнительных соединений экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] к плану обслуживания.</span><span class="sxs-lookup"><span data-stu-id="c7d22-144">Used to add additional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance connections to the maintenance plan.</span></span> <span data-ttu-id="c7d22-145">Дополнительные сведения об этом диалоговом окне см. ниже.</span><span class="sxs-lookup"><span data-stu-id="c7d22-145">See below for more information on this dialog box.</span></span>  
  
     <span data-ttu-id="c7d22-146">**Отчеты и ведение журнала**</span><span class="sxs-lookup"><span data-stu-id="c7d22-146">**Reporting and Logging**</span></span>  
     <span data-ttu-id="c7d22-147">Открывает диалоговое окно **Отчеты и ведение журнала** .</span><span class="sxs-lookup"><span data-stu-id="c7d22-147">Displays the **Reporting and Logging** dialog box.</span></span> <span data-ttu-id="c7d22-148">Дополнительные сведения об этом диалоговом окне см. ниже.</span><span class="sxs-lookup"><span data-stu-id="c7d22-148">See below for more information on this dialog box.</span></span>  
  
     <span data-ttu-id="c7d22-149">**Серверы**</span><span class="sxs-lookup"><span data-stu-id="c7d22-149">**Servers**</span></span>  
     <span data-ttu-id="c7d22-150">Отображает диалоговое окно **Серверы** , которое используется для выбора серверов, на которых будут выполняться задачи вложенного плана.</span><span class="sxs-lookup"><span data-stu-id="c7d22-150">Display the **Servers** dialog box, which is used to select the servers where the subplan tasks will be run.</span></span> <span data-ttu-id="c7d22-151">Этот параметр доступен только на главных серверах в многосерверном окружении.</span><span class="sxs-lookup"><span data-stu-id="c7d22-151">This option is enabled only on master servers in multiserver environments.</span></span> <span data-ttu-id="c7d22-152">Дополнительные сведения см. в статье [Создание многосерверной среды](../../ssms/agent/create-a-multiserver-environment.md) и [План обслуживания (серверы)](maintenance-plan-servers.md).</span><span class="sxs-lookup"><span data-stu-id="c7d22-152">For more information, see [Create a Multiserver Environment](../../ssms/agent/create-a-multiserver-environment.md) and [Maintenance Plan &#40;Servers&#41;](maintenance-plan-servers.md).</span></span>  
  
     <span data-ttu-id="c7d22-153">**имя**;</span><span class="sxs-lookup"><span data-stu-id="c7d22-153">**Name**</span></span>  
     <span data-ttu-id="c7d22-154">Отображает имя плана обслуживания.</span><span class="sxs-lookup"><span data-stu-id="c7d22-154">Display the maintenance plan name.</span></span> <span data-ttu-id="c7d22-155">Имя нового плана обслуживания необходимо указать в диалоговом окне до открытия конструктора планов обслуживания.</span><span class="sxs-lookup"><span data-stu-id="c7d22-155">For new maintenance plans, the name is specified in a dialog box before the maintenance plan designer opens.</span></span> <span data-ttu-id="c7d22-156">Чтобы переименовать план обслуживания, щелкните правой кнопкой мыши план в обозревателе объектов и выберите **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-156">To rename a maintenance plan, right-click the plan in Object Explorer, and then click **Rename**.</span></span>  
  
     <span data-ttu-id="c7d22-157">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c7d22-157">**Description**</span></span>  
     <span data-ttu-id="c7d22-158">Просмотрите или укажите описание для плана обслуживания.</span><span class="sxs-lookup"><span data-stu-id="c7d22-158">View or specify a description for the maintenance plan.</span></span> <span data-ttu-id="c7d22-159">Максимальная длина описания составляет 512 знаков.</span><span class="sxs-lookup"><span data-stu-id="c7d22-159">The maximum length for a description is 512 characters.</span></span>  
  
     <span data-ttu-id="c7d22-160">**Область конструктора**</span><span class="sxs-lookup"><span data-stu-id="c7d22-160">**Designer Surface**</span></span>  
     <span data-ttu-id="c7d22-161">Создание и обслуживание планов обслуживания.</span><span class="sxs-lookup"><span data-stu-id="c7d22-161">Design and maintain maintenance plans.</span></span> <span data-ttu-id="c7d22-162">Используйте область конструктора, чтобы добавлять задачи обслуживания к плану, удалять задачи из плана, указывать ссылки очередности между задачами, а также для указания ветвления задач и параллелизма.</span><span class="sxs-lookup"><span data-stu-id="c7d22-162">Use the designer surface to add maintenance tasks to a plan, remove tasks from a plan, specify precedence links between the tasks, and indicate task branching and parallelism.</span></span>  
  
     <span data-ttu-id="c7d22-163">Ссылка очередности между двумя задачами устанавливает связь между ними.</span><span class="sxs-lookup"><span data-stu-id="c7d22-163">A precedence link between two tasks establishes a relationship between the tasks.</span></span> <span data-ttu-id="c7d22-164">Вторая задача ( *зависимая*) выполняется только в том случае, если результат выполнения первой задачи ( *приоритетной*) удовлетворяет указанным критериям.</span><span class="sxs-lookup"><span data-stu-id="c7d22-164">The second task (the *dependent task*) executes only if the execution result of the first task (the *precedent task*) matches specified criteria.</span></span> <span data-ttu-id="c7d22-165">Обычно оценка результата выполнения задается как **Успешно**, **Ошибка**или **Завершение**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-165">Typically the execution result specified is **Success**, **Failure**, or **Completion**.</span></span> <span data-ttu-id="c7d22-166">Дополнительные сведения см. в шаге **8** ниже.</span><span class="sxs-lookup"><span data-stu-id="c7d22-166">For more information, see step **8** below.</span></span>  
  
5.  <span data-ttu-id="c7d22-167">В заголовке области конструктора дважды щелкните **Subplan_1** и введите имя и описание для вложенного плана в диалоговом окне **Свойства вложенного плана** .</span><span class="sxs-lookup"><span data-stu-id="c7d22-167">In the design space's header, double-click **Subplan_1** and enter a name and description for the subplan in the **Subplan Properties** dialog box.</span></span>  
  
     <span data-ttu-id="c7d22-168">В диалоговом окне **Свойства вложенного плана** доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="c7d22-168">The following options are available in the **Subplan Properties** dialog box.</span></span>  
  
     <span data-ttu-id="c7d22-169">**имя**;</span><span class="sxs-lookup"><span data-stu-id="c7d22-169">**Name**</span></span>  
     <span data-ttu-id="c7d22-170">Имя вложенного плана.</span><span class="sxs-lookup"><span data-stu-id="c7d22-170">The name of the subplan.</span></span>  
  
     <span data-ttu-id="c7d22-171">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c7d22-171">**Description**</span></span>  
     <span data-ttu-id="c7d22-172">Краткое описание вложенного плана.</span><span class="sxs-lookup"><span data-stu-id="c7d22-172">A brief description of the subplan.</span></span>  
  
     <span data-ttu-id="c7d22-173">**Расписание**</span><span class="sxs-lookup"><span data-stu-id="c7d22-173">**Schedule**</span></span>  
     <span data-ttu-id="c7d22-174">Расписание, по которому будет выполняться вложенный план.</span><span class="sxs-lookup"><span data-stu-id="c7d22-174">Indicates on what schedule the subplan will be run.</span></span> <span data-ttu-id="c7d22-175">Щелкните значок **Расписание вложенного плана** , чтобы открыть диалоговое окно **Создание расписания заданий** .</span><span class="sxs-lookup"><span data-stu-id="c7d22-175">Click **Subplan Schedule** to open the **New Job Schedule** dialog box.</span></span> <span data-ttu-id="c7d22-176">Нажмите кнопку **Удалить расписание** , чтобы удалить расписание из вложенного плана.</span><span class="sxs-lookup"><span data-stu-id="c7d22-176">Click **Remove Schedule** to delete the schedule from the subplan.</span></span>  
  
     <span data-ttu-id="c7d22-177">Список**Запуск от имени**</span><span class="sxs-lookup"><span data-stu-id="c7d22-177">**Run as** list</span></span>  
     <span data-ttu-id="c7d22-178">Выберите учетную запись, используемую для запуска этой вложенной задачи.</span><span class="sxs-lookup"><span data-stu-id="c7d22-178">Select the account to use to run this subtask.</span></span>  
  
6.  <span data-ttu-id="c7d22-179">Нажмите кнопку **Расписание вложенного плана** , чтобы ввести данные расписания в диалоговом окне **Создание расписания заданий** .</span><span class="sxs-lookup"><span data-stu-id="c7d22-179">Click **Subplan Schedule** to enter schedule details in the **New Job Schedule** dialog box.</span></span>  
  
7.  <span data-ttu-id="c7d22-180">Для создания вложенного плана перетащите элементы потока задач с **панели элементов** в область конструктора планов.</span><span class="sxs-lookup"><span data-stu-id="c7d22-180">To build the subplan, drag and drop task flow elements from the **Toolbox** to the plan design surface.</span></span> <span data-ttu-id="c7d22-181">Двойной щелчок задачи открывает диалоговое окно, где можно настроить параметры задачи.</span><span class="sxs-lookup"><span data-stu-id="c7d22-181">Double-click tasks to open dialog boxes to configure the task options.</span></span>  
  
     <span data-ttu-id="c7d22-182">На **панели элементов**доступны следующие задачи плана обслуживания:</span><span class="sxs-lookup"><span data-stu-id="c7d22-182">The following maintenance plan tasks are available in the **Toolbox**:</span></span>  
  
    -   <span data-ttu-id="c7d22-183">**Задача «Создание резервной копии базы данных»**</span><span class="sxs-lookup"><span data-stu-id="c7d22-183">**Back up Database Task**</span></span>  
  
    -   <span data-ttu-id="c7d22-184">**Задача «Проверка целостности базы данных»**</span><span class="sxs-lookup"><span data-stu-id="c7d22-184">**Check Database Integrity Task**</span></span>  
  
    -   <span data-ttu-id="c7d22-185">**Задача «Выполнение задания агента SQL Server»**</span><span class="sxs-lookup"><span data-stu-id="c7d22-185">**Execute SQL Server Agent Job Task**</span></span>  
  
    -   <span data-ttu-id="c7d22-186">**Задача «Выполнение инструкции T-SQL»**</span><span class="sxs-lookup"><span data-stu-id="c7d22-186">**Execute T-SQL Statement Task**</span></span>  
  
    -   <span data-ttu-id="c7d22-187">**Задача «Очистка журнала»**</span><span class="sxs-lookup"><span data-stu-id="c7d22-187">**History Cleanup Task**</span></span>  
  
    -   <span data-ttu-id="c7d22-188">**Задача «Очистка после обслуживания»**</span><span class="sxs-lookup"><span data-stu-id="c7d22-188">**Maintenance Cleanup Task**</span></span>  
  
    -   <span data-ttu-id="c7d22-189">**Задача «Уведомление оператора»**</span><span class="sxs-lookup"><span data-stu-id="c7d22-189">**Notify Operator Task**</span></span>  
  
    -   <span data-ttu-id="c7d22-190">**Задача «Перестроение индекса»**</span><span class="sxs-lookup"><span data-stu-id="c7d22-190">**Rebuild Index Task**</span></span>  
  
    -   <span data-ttu-id="c7d22-191">**Задача «Реорганизация индекса»**</span><span class="sxs-lookup"><span data-stu-id="c7d22-191">**Reorganize Index Task**</span></span>  
  
    -   <span data-ttu-id="c7d22-192">**Задача «Сжатие базы данных»**</span><span class="sxs-lookup"><span data-stu-id="c7d22-192">**Shrink Database Task**</span></span>  
  
    -   <span data-ttu-id="c7d22-193">**Задача «Обновление статистики»**</span><span class="sxs-lookup"><span data-stu-id="c7d22-193">**Update Statistics Task**</span></span>  
  
     <span data-ttu-id="c7d22-194">Добавление задач на **панель элементов**</span><span class="sxs-lookup"><span data-stu-id="c7d22-194">To add tasks to the **Toolbox**:</span></span>  
  
    1.  <span data-ttu-id="c7d22-195">В меню **Сервис** выберите пункт **Выбрать элементы панели элементов**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-195">On the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
    2.  <span data-ttu-id="c7d22-196">Выберите инструменты, которые должны появиться на **панели элементов**, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-196">Select the tools you want to appear in the **Toolbox**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c7d22-197">При добавлении задач плана обслуживания на **панель элементов** они становятся доступными в **мастере планов обслуживания**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-197">Adding maintenance plan tasks to the **Toolbox** also makes them available in the **Maintenance Plan Wizard**.</span></span> <span data-ttu-id="c7d22-198">Дополнительные сведения по отдельным задачам, перечисленным выше, см. в разделе [Использование мастера планов обслуживания](use-the-maintenance-plan-wizard.md#SSMSProcedure) статьи **Запуск мастера планов обслуживания**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-198">For more information on the individual tasks above, see [Using Maintenance Plan Wizard](use-the-maintenance-plan-wizard.md#SSMSProcedure) under **Start the Maintenance Plan Wizard**.</span></span>  
  
8.  <span data-ttu-id="c7d22-199">Определение рабочего процесса между задачами</span><span class="sxs-lookup"><span data-stu-id="c7d22-199">To define a workflow between tasks:</span></span>  
  
    1.  <span data-ttu-id="c7d22-200">Щелкните правой кнопкой мыши приоритетную задачу и выберите команду **Добавить элементы управления очередностью**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-200">Right-click the precedent task and select **Add Precedence Constraint**.</span></span>  
  
    2.  <span data-ttu-id="c7d22-201">В диалоговом окне **Поток управления** в списке **Для** выберите зависимую задачу и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-201">In the **Control Flow** dialog box, in the **To** list, select the dependent task and click **OK**.</span></span>  
  
    3.  <span data-ttu-id="c7d22-202">Дважды щелкните соединитель между двумя задачами, чтобы открыть диалоговое окно **Редактор элементов управления очередностью** .</span><span class="sxs-lookup"><span data-stu-id="c7d22-202">Double click the connector between the two tasks to open the **Precedence Constraint Editor** dialog box.</span></span>  
  
         <span data-ttu-id="c7d22-203">В диалоговом окне **Редактор элементов управления очередностью** доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="c7d22-203">The following options are available in the **Precedence Constraint Editor** dialog box.</span></span>  
  
         <span data-ttu-id="c7d22-204">**Ограничение**</span><span class="sxs-lookup"><span data-stu-id="c7d22-204">**Constraint option**</span></span>  
         <span data-ttu-id="c7d22-205">Определяет механизм работы ограничения между двумя задачами.</span><span class="sxs-lookup"><span data-stu-id="c7d22-205">Defines how a constraint works between two tasks.</span></span>  
  
         <span data-ttu-id="c7d22-206">Список**Вычислительная операция**</span><span class="sxs-lookup"><span data-stu-id="c7d22-206">**Evaluation operation**  list</span></span>  
         <span data-ttu-id="c7d22-207">Определяет вычислительную операцию, которую использует ограничение очередностью.</span><span class="sxs-lookup"><span data-stu-id="c7d22-207">Specify the evaluation operation that the precedence constraint uses.</span></span> <span data-ttu-id="c7d22-208">Операциями могут быть: **Ограничение**, **Выражение**, **Выражение и ограничение** и **Выражение или ограничение**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-208">The operations are: **Constraint**, **Expression**, **Expression and Constraint**, and **Expression or Constraint**.</span></span>  
  
         <span data-ttu-id="c7d22-209">Список**Значение**</span><span class="sxs-lookup"><span data-stu-id="c7d22-209">**Value** list</span></span>  
         <span data-ttu-id="c7d22-210">Укажите ограничение по значению: **Успешно**, **Сбой** или **Завершение**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-210">Specify the constraint value: **Success**, **Failure**, or **Completion**.</span></span> <span data-ttu-id="c7d22-211">**Успех** является значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c7d22-211">**Success** is the default.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="c7d22-212">Строка элементов управления очередностью имеет зеленый цвет для значения **Успех**, красный для значения **Неудача**и синий для значения **Завершение**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-212">The precedence constraint line is green for **Success**, red for **Failure**, and blue for **Completion**.</span></span>  
  
         <span data-ttu-id="c7d22-213">**Выражение**</span><span class="sxs-lookup"><span data-stu-id="c7d22-213">**Expression**</span></span>  
         <span data-ttu-id="c7d22-214">При использовании операций **Выражение**, **Выражение и ограничение**или **Выражение или ограничение**введите выражение.</span><span class="sxs-lookup"><span data-stu-id="c7d22-214">If using the operations **Expression**, **Expression and Constraint**, or **Expression or Constraint**, type an expression.</span></span> <span data-ttu-id="c7d22-215">Выражение должно иметь логическое значение.</span><span class="sxs-lookup"><span data-stu-id="c7d22-215">The expression must evaluate to a Boolean.</span></span>  
  
         <span data-ttu-id="c7d22-216">**Тест**</span><span class="sxs-lookup"><span data-stu-id="c7d22-216">**Test**</span></span>  
         <span data-ttu-id="c7d22-217">Проверка выражения.</span><span class="sxs-lookup"><span data-stu-id="c7d22-217">Validate the expression.</span></span>  
  
         <span data-ttu-id="c7d22-218">**Несколько ограничений**</span><span class="sxs-lookup"><span data-stu-id="c7d22-218">**Multiple constraints**</span></span>  
         <span data-ttu-id="c7d22-219">Определяет механизм взаимодействия нескольких ограничений друг с другом при управлении выполнением задачи с ограничением.</span><span class="sxs-lookup"><span data-stu-id="c7d22-219">Define how multiple constraints interoperate to control the execution of the constrained task.</span></span>  
  
         <span data-ttu-id="c7d22-220">**Логическое И**</span><span class="sxs-lookup"><span data-stu-id="c7d22-220">**Logical AND**</span></span>  
         <span data-ttu-id="c7d22-221">Выберите, чтобы указать, что несколько ограничений очередности в одном исполняемом объекте должны учитываться вместе.</span><span class="sxs-lookup"><span data-stu-id="c7d22-221">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="c7d22-222">Все ограничения должны иметь значение True.</span><span class="sxs-lookup"><span data-stu-id="c7d22-222">All constraints must evaluate to True.</span></span> <span data-ttu-id="c7d22-223">Этот параметр выбирается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c7d22-223">This option is the default.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="c7d22-224">Этот тип ограничения очередностью имеет вид сплошной зеленой, красной или синей линии.</span><span class="sxs-lookup"><span data-stu-id="c7d22-224">This type of precedence constraint appears as a solid green, red, or blue line.</span></span>  
  
         <span data-ttu-id="c7d22-225">**Логическое ИЛИ**</span><span class="sxs-lookup"><span data-stu-id="c7d22-225">**Logical OR**</span></span>  
         <span data-ttu-id="c7d22-226">Выберите, чтобы указать, что несколько ограничений очередности в одном исполняемом объекте должны учитываться вместе.</span><span class="sxs-lookup"><span data-stu-id="c7d22-226">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="c7d22-227">По крайней мере одно ограничение должно иметь значение True.</span><span class="sxs-lookup"><span data-stu-id="c7d22-227">At least one constraint must evaluate to True.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="c7d22-228">Этот тип ограничения очередностью имеет вид пунктирной зеленой, красной или синей линии.</span><span class="sxs-lookup"><span data-stu-id="c7d22-228">This type of precedence constraint appears as a dotted green, red, or blue line.</span></span>  
  
9. <span data-ttu-id="c7d22-229">Чтобы добавить другой вложенный план, содержащий задачи, выполняемые по другому расписанию, на панели инструментов нажмите кнопку **Добавить вложенный план** , чтобы открыть диалоговое окно **Свойства вложенного плана** .</span><span class="sxs-lookup"><span data-stu-id="c7d22-229">To add another subplan that contains tasks run on a different schedule, click **Add Subplan** on the toolbar to open the **Subplan Properties** dialog box.</span></span>  
  
10. <span data-ttu-id="c7d22-230">Добавление соединений с разными серверами</span><span class="sxs-lookup"><span data-stu-id="c7d22-230">To add connections to different servers:</span></span>  
  
    1.  <span data-ttu-id="c7d22-231">На панели инструментов области конструктора нажмите кнопку **Управление соединениями**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-231">In the design space's toolbar, click **Manage Connections**.</span></span>  
  
    2.  <span data-ttu-id="c7d22-232">В диалоговом окне **Управление соединениями** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-232">In the **Manage Connections** dialog box, click **Add**.</span></span>  
  
    3.  <span data-ttu-id="c7d22-233">В диалоговом окне **Свойства соединениями** в поле **Имя соединения** введите имя создаваемого подключения.</span><span class="sxs-lookup"><span data-stu-id="c7d22-233">In the **Connection Properties** dialog box, in the **Connection name** box, enter the name of the connection you are creating.</span></span>  
  
    4.  <span data-ttu-id="c7d22-234">В области **Укажите следующие параметры для подключения к данным SQL Server** в поле **Выберите или введите имя сервера** введите имя сервера SQL Server, который нужно использовать, или нажмите кнопку с многоточием **(…)** и выберите сервер в диалоговом окне **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-234">Under **Specify the following to connect to SQL Server data**, in the **Select or enter a server name** box, either enter the name of the SQL server you want to use or click the ellipsis **(...)** and select a server in the **SQL Server** dialog box.</span></span> <span data-ttu-id="c7d22-235">После выбора сервера в диалоговом окне **SQL Server** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-235">If you select a server from the **SQL Server** dialog box, click **OK**.</span></span>  
  
    5.  <span data-ttu-id="c7d22-236">В области **Введите данные для входа на сервер**выберите **Использовать встроенную систему безопасности Windows NT** или **Использовать указанные имя пользователя и пароль**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-236">Under **Enter information to log on to the server**, select either **Use Windows NT Integrated security** or **Use a specific user name and password**.</span></span> <span data-ttu-id="c7d22-237">Если выбрано использование указанных имени пользователя и пароля, введите данные в полях **Имя пользователя** и **Пароль** соответственно.</span><span class="sxs-lookup"><span data-stu-id="c7d22-237">If you elect to use a specific user name and password, enter that information in the **User name** and **Password** boxes, respectively.</span></span>  
  
    6.  <span data-ttu-id="c7d22-238">В диалоговом окне **Свойства соединения** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-238">In the **Connection Properties** dialog box, click **OK**.</span></span>  
  
    7.  <span data-ttu-id="c7d22-239">В диалоговом окне **Управление соединениями** нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-239">In the **Manage Connections** dialog box, click **Close**.</span></span>  
  
11. <span data-ttu-id="c7d22-240">Задание параметров отчета</span><span class="sxs-lookup"><span data-stu-id="c7d22-240">To specify reporting options:</span></span>  
  
    1.  <span data-ttu-id="c7d22-241">На панели инструментов области конструктора щелкните значок **Отчеты и ведение журнала**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-241">In the design space's toolbar, click **Reporting and Logging**.</span></span>  
  
    2.  <span data-ttu-id="c7d22-242">В диалоговом окне **Отчеты и ведение журнала** в области **Отчеты**выберите **Сформировать текстовый файл отчета** , **Отправить отчет адресату по электронной почте** или оба варианта.</span><span class="sxs-lookup"><span data-stu-id="c7d22-242">In the **Reporting and Logging** dialog box, under **Reporting**, select **Generate a text file report** or **Send report to an email recipient** or both.</span></span>  
  
        1.  <span data-ttu-id="c7d22-243">Если выбран параметр **Сформировать текстовый файл отчета**, выберите **Создать новый файл** или **Добавить в файл**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-243">If you select **Generate a text file report**, select either **Create a new file** or **Append to file**.</span></span>  
  
        2.  <span data-ttu-id="c7d22-244">В зависимости от выбора выше введите имя и полный путь к новому файлу или файлу, который будет дополняться, указав данные в полях **Папка** или **Имя файла** .</span><span class="sxs-lookup"><span data-stu-id="c7d22-244">Depending on the selection above, enter the name and full path of the new file or file to be appended by entering the information in the **Folder** or **File name** boxes.</span></span> <span data-ttu-id="c7d22-245">Можно также нажать кнопку с многоточием **(...)** и выбрать путь к папке или имени файла из диалоговых окон **расположение папки —**_server_name_ или **Расположение файлов базы данных —**_server_name_ .</span><span class="sxs-lookup"><span data-stu-id="c7d22-245">Alternately, click on the ellipsis **(...)** and select the path to the folder or file name from the **Locate Folder -**_server_name_ or **Locate Database Files -**_server_name_ dialog boxes.</span></span>  
  
        3.  <span data-ttu-id="c7d22-246">Если выбран параметр **Отправить отчет адресату по электронной почте**, то в списке **Оператор агента** нужно выбрать получателя отчета.</span><span class="sxs-lookup"><span data-stu-id="c7d22-246">If you select **Send report to an email recipient**, on the **Agent operator** list, select the recipient of the emailed report.</span></span>  
  
            > [!NOTE]  
            >  <span data-ttu-id="c7d22-247">В агенте SQL Server должно быть настроено использование компонента Database Mail для отправки почты.</span><span class="sxs-lookup"><span data-stu-id="c7d22-247">SQL Server Agent must be configured to use Database Mail in order to send mail.</span></span> <span data-ttu-id="c7d22-248">Дополнительные сведения см. в разделе [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="c7d22-248">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md)</span></span>  
  
    3.  <span data-ttu-id="c7d22-249">Чтобы сохранить более подробные сведения, в области **Ведение журнала**выберите **Записывать подробные данные в журнал**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-249">To save more detailed information, under **Logging**, select **Log extended information**.</span></span>  
  
    4.  <span data-ttu-id="c7d22-250">Чтобы записать результаты выполнения плана обслуживания на другой сервер, выберите **Войти на удаленный сервер** и выберите соединение с сервером в списке **Соединение** или нажмите кнопку **Создать** и введите данные соединения в диалоговом окне **Свойства подключения** .</span><span class="sxs-lookup"><span data-stu-id="c7d22-250">To write maintenance plan results information to another server, select **Log to remote server** and either select a server connection from the **Connection** list or click **New** and enter the connection information in the **Connection Properties** dialog box.</span></span>  
  
    5.  <span data-ttu-id="c7d22-251">В диалоговом окне **Отчеты и ведение журнала** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-251">In the **Reporting and Logging** dialog box, click **OK**.</span></span>  
  
12. <span data-ttu-id="c7d22-252">Для просмотра результатов в средстве просмотра журнала в **Обозревателе объектов**щелкните правой кнопкой мыши папку **Планы обслуживания** или конкретный план обслуживания и выберите команду **Просмотр журнала**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-252">To view the results in the log file viewer, in **Object Explorer**, right-click either the **Maintenance Plans** folder or the specific maintenance plan and select **View History**.</span></span>  
  
     <span data-ttu-id="c7d22-253">В диалоговом окне **Просмотр файла журнала —**_server_name_ доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="c7d22-253">The following options are available on the **Log File Viewer -**_server_name_ dialog box.</span></span>  
  
     <span data-ttu-id="c7d22-254">**Загрузить журнал**</span><span class="sxs-lookup"><span data-stu-id="c7d22-254">**Load Log**</span></span>  
     <span data-ttu-id="c7d22-255">Открывает диалоговое окно, в котором можно указать загружаемый файл журнала.</span><span class="sxs-lookup"><span data-stu-id="c7d22-255">Open a dialog box where you can specify a log file to load.</span></span>  
  
     <span data-ttu-id="c7d22-256">**Экспорт**</span><span class="sxs-lookup"><span data-stu-id="c7d22-256">**Export**</span></span>  
     <span data-ttu-id="c7d22-257">Открывает диалоговое окно, позволяющее экспортировать данные из сетки **Сведения о файле журнала** в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="c7d22-257">Open a dialog box that lets you export the information that is shown in the **Log file summary** grid to a text file.</span></span>  
  
     <span data-ttu-id="c7d22-258">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="c7d22-258">**Refresh**</span></span>  
     <span data-ttu-id="c7d22-259">Позволяет обновить представление выбранных журналов.</span><span class="sxs-lookup"><span data-stu-id="c7d22-259">Refresh the view of the selected logs.</span></span> <span data-ttu-id="c7d22-260">При нажатии кнопки **Обновить** выбранные журналы заново считываются с целевого сервера с применением параметров фильтра.</span><span class="sxs-lookup"><span data-stu-id="c7d22-260">The **Refresh** button rereads the selected logs from the target server while applying any filter settings.</span></span>  
  
     <span data-ttu-id="c7d22-261">**Filter**</span><span class="sxs-lookup"><span data-stu-id="c7d22-261">**Filter**</span></span>  
     <span data-ttu-id="c7d22-262">Открывает диалоговое окно, позволяющее указывать параметры фильтрации файла журнала, например **Соединение**и **Дата**или другие **Общие** условия фильтра.</span><span class="sxs-lookup"><span data-stu-id="c7d22-262">Open a dialog box that lets you specify settings that are used to filter the log file, such as **Connection**, **Date**, or other **General** filter criteria.</span></span>  
  
     <span data-ttu-id="c7d22-263">**Поиск**</span><span class="sxs-lookup"><span data-stu-id="c7d22-263">**Search**</span></span>  
     <span data-ttu-id="c7d22-264">Позволяет найти определенный текст в файле журнала.</span><span class="sxs-lookup"><span data-stu-id="c7d22-264">Search the log file for specific text.</span></span> <span data-ttu-id="c7d22-265">Поиск с символами-шаблонами не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="c7d22-265">Searching with wildcard characters is not supported.</span></span>  
  
     <span data-ttu-id="c7d22-266">**Остановить**</span><span class="sxs-lookup"><span data-stu-id="c7d22-266">**Stop**</span></span>  
     <span data-ttu-id="c7d22-267">Прекращает загрузку записей файла журнала.</span><span class="sxs-lookup"><span data-stu-id="c7d22-267">Stops loading the log file entries.</span></span> <span data-ttu-id="c7d22-268">Например, можно использовать этот параметр, если загрузка удаленного файла или файла журнала вне сети занимает длительное время, а нужно просмотреть лишь наиболее свежие записи.</span><span class="sxs-lookup"><span data-stu-id="c7d22-268">For example, you can use this option if a remote or offline log file takes a long time to load, and you only want to view the most recent entries.</span></span>  
  
     <span data-ttu-id="c7d22-269">**Сведения о файле журнала**</span><span class="sxs-lookup"><span data-stu-id="c7d22-269">**Log file summary**</span></span>  
     <span data-ttu-id="c7d22-270">Эта информационная панель содержит сводку данных по фильтрации файла журнала.</span><span class="sxs-lookup"><span data-stu-id="c7d22-270">This information panel displays a summary of the log file filtering.</span></span> <span data-ttu-id="c7d22-271">Если файл не фильтруется, на панели отображается текст **без фильтров**.</span><span class="sxs-lookup"><span data-stu-id="c7d22-271">If the file is not filtered, you will see the following text, **No filter applied**.</span></span> <span data-ttu-id="c7d22-272">Если фильтр применяется к журналу, отображается следующий текст: **Критерий отбора:** \<filter criteria>.</span><span class="sxs-lookup"><span data-stu-id="c7d22-272">If a filter is applied to the log, you will see the following text, **Filter log entries where:** \<filter criteria>.</span></span>  
  
     <span data-ttu-id="c7d22-273">**Дата**</span><span class="sxs-lookup"><span data-stu-id="c7d22-273">**Date**</span></span>  
     <span data-ttu-id="c7d22-274">Дата события.</span><span class="sxs-lookup"><span data-stu-id="c7d22-274">Displays the date of the event.</span></span>  
  
     <span data-ttu-id="c7d22-275">**Source**</span><span class="sxs-lookup"><span data-stu-id="c7d22-275">**Source**</span></span>  
     <span data-ttu-id="c7d22-276">Исходная функция, создавшая событие, например имя службы (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="c7d22-276">Displays the source feature from which the event is created, such as the name of the service (MSSQLSERVER, for example).</span></span> <span data-ttu-id="c7d22-277">Отображается не для всех типов журнала.</span><span class="sxs-lookup"><span data-stu-id="c7d22-277">This does not appear for all log types.</span></span>  
  
     <span data-ttu-id="c7d22-278">**Сообщение**</span><span class="sxs-lookup"><span data-stu-id="c7d22-278">**Message**</span></span>  
     <span data-ttu-id="c7d22-279">Сообщение, связанное с событием.</span><span class="sxs-lookup"><span data-stu-id="c7d22-279">Displays any messages associated with the event.</span></span>  
  
     <span data-ttu-id="c7d22-280">**Log Type**</span><span class="sxs-lookup"><span data-stu-id="c7d22-280">**Log Type**</span></span>  
     <span data-ttu-id="c7d22-281">Отображает тип журнала, которому принадлежит событие.</span><span class="sxs-lookup"><span data-stu-id="c7d22-281">Displays the type of log to which the event belongs.</span></span> <span data-ttu-id="c7d22-282">Все выбранные журналы отображаются в окне сводки файла журнала.</span><span class="sxs-lookup"><span data-stu-id="c7d22-282">All selected logs appear in the log file summary window.</span></span>  
  
     <span data-ttu-id="c7d22-283">**Log Source**</span><span class="sxs-lookup"><span data-stu-id="c7d22-283">**Log Source**</span></span>  
     <span data-ttu-id="c7d22-284">Отображает описание исходного журнала, в котором зарегистрировано событие.</span><span class="sxs-lookup"><span data-stu-id="c7d22-284">Displays a description of the source log in which the event is captured.</span></span>  
  
     <span data-ttu-id="c7d22-285">**Сведения о выбранной строке**</span><span class="sxs-lookup"><span data-stu-id="c7d22-285">**Selected row details**</span></span>  
     <span data-ttu-id="c7d22-286">Выберите строку для отображения дополнительных сведений о выбранной строке события внизу страницы.</span><span class="sxs-lookup"><span data-stu-id="c7d22-286">Select a row to display additional details about the selected event row at the bottom of the page.</span></span> <span data-ttu-id="c7d22-287">Порядок столбцов можно менять, перетаскивая их в нужное место сетки.</span><span class="sxs-lookup"><span data-stu-id="c7d22-287">The columns can be reordered by dragging them to new locations in the grid.</span></span> <span data-ttu-id="c7d22-288">Размер столбцов можно менять, перетаскивая разделители столбцов в заголовке сетки вправо или влево.</span><span class="sxs-lookup"><span data-stu-id="c7d22-288">The columns can be resized by dragging the column separator bars in the grid header to the left or right.</span></span> <span data-ttu-id="c7d22-289">Если дважды щелкнуть разделитель столбцов в заголовке сетки, ширина столбца будет автоматически подогнана под его содержимое.</span><span class="sxs-lookup"><span data-stu-id="c7d22-289">Double-click the column separator bars in the grid header to automatically size the column to the content width.</span></span>  
  
     <span data-ttu-id="c7d22-290">**Экземпляр**</span><span class="sxs-lookup"><span data-stu-id="c7d22-290">**Instance**</span></span>  
     <span data-ttu-id="c7d22-291">Имя экземпляра, к которому относится происшедшее событие.</span><span class="sxs-lookup"><span data-stu-id="c7d22-291">The name of the instance on which the event occurred.</span></span> <span data-ttu-id="c7d22-292">Отображается как *имя_компьютера*\\*имя_экземпляра*.</span><span class="sxs-lookup"><span data-stu-id="c7d22-292">This is displayed as *computer name*\\*instance name*.</span></span>  
  
  
