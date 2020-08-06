---
title: Работа с профилями агента репликации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], agents and profiles
- replication agent profiles [SQL Server]
- agents [SQL Server replication], profiles
- profiles [SQL Server], replication agents
ms.assetid: 9c290a88-4e9f-4a7e-aab5-4442137a9918
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fc20451edfb1096fca7e468effb14df78b51f758
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655657"
---
# <a name="work-with-replication-agent-profiles"></a><span data-ttu-id="1a424-102">Работа с профилями агента репликации</span><span class="sxs-lookup"><span data-stu-id="1a424-102">Work with Replication Agent Profiles</span></span>
  <span data-ttu-id="1a424-103">В данном разделе описывается работа с профилями агента репликации в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]или объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="1a424-103">This topic describes how to work with Replication Agent Profiles in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span> <span data-ttu-id="1a424-104">Поведение каждого агента репликации контролируется набором параметров, который может устанавливаться через профили агента.</span><span class="sxs-lookup"><span data-stu-id="1a424-104">The behavior of each replication agent is controlled by a set of parameters that can be set through agent profiles.</span></span> <span data-ttu-id="1a424-105">У каждого агента имеются профили по умолчанию, а некоторые агенты имеют дополнительные предопределенные профили. В каждый момент времени активен только один профиль.</span><span class="sxs-lookup"><span data-stu-id="1a424-105">Each agent has a default profile, and some have additional predefined profiles; at a given time, only one profile is active for an agent.</span></span>  
  
 <span data-ttu-id="1a424-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="1a424-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1a424-107">**Для работы с профилями агента репликации используется:**</span><span class="sxs-lookup"><span data-stu-id="1a424-107">**To work with Replication Agent Profiles, using:**</span></span>  
  
     [<span data-ttu-id="1a424-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1a424-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
    -   <span data-ttu-id="1a424-109">Доступ к диалоговому окну «Профили агентов»</span><span class="sxs-lookup"><span data-stu-id="1a424-109">Access the Agent Profiles dialog box</span></span>  
  
    -   <span data-ttu-id="1a424-110">Указание профиля для агента</span><span class="sxs-lookup"><span data-stu-id="1a424-110">Specify a profile for an agent</span></span>  
  
    -   <span data-ttu-id="1a424-111">Создание профиля</span><span class="sxs-lookup"><span data-stu-id="1a424-111">Create a profile</span></span>  
  
    -   <span data-ttu-id="1a424-112">Изменение профиля</span><span class="sxs-lookup"><span data-stu-id="1a424-112">Modify a profile</span></span>  
  
    -   <span data-ttu-id="1a424-113">Удаление профиля</span><span class="sxs-lookup"><span data-stu-id="1a424-113">Delete a profile</span></span>  
  
     [<span data-ttu-id="1a424-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1a424-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
    -   <span data-ttu-id="1a424-115">Создание профиля</span><span class="sxs-lookup"><span data-stu-id="1a424-115">Create a profile</span></span>  
  
    -   <span data-ttu-id="1a424-116">Изменение профиля</span><span class="sxs-lookup"><span data-stu-id="1a424-116">Modify a profile</span></span>  
  
    -   <span data-ttu-id="1a424-117">Удаление профиля</span><span class="sxs-lookup"><span data-stu-id="1a424-117">Delete a profile</span></span>  
  
    -   <span data-ttu-id="1a424-118">Использование профилей агента при синхронизации</span><span class="sxs-lookup"><span data-stu-id="1a424-118">Use agent profiles during synchronization</span></span>  
  
    -   <span data-ttu-id="1a424-119">Пример (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1a424-119">Transact-SQL example</span></span>  
  
     [<span data-ttu-id="1a424-120">Объекты RMO</span><span class="sxs-lookup"><span data-stu-id="1a424-120">Replication Management Objects</span></span>](#RMOProcedure)  
  
    -   <span data-ttu-id="1a424-121">Создание профиля</span><span class="sxs-lookup"><span data-stu-id="1a424-121">Create a profile</span></span>  
  
    -   <span data-ttu-id="1a424-122">Изменение профиля</span><span class="sxs-lookup"><span data-stu-id="1a424-122">Modify a profile</span></span>  
  
    -   <span data-ttu-id="1a424-123">Удаление профиля</span><span class="sxs-lookup"><span data-stu-id="1a424-123">Delete a profile</span></span>  
  
-   <span data-ttu-id="1a424-124">**Дальнейшие действия.**  [После изменения параметров агента](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="1a424-124">**Follow Up:**  [After Changing Agent Parameters](#FollowUp)</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1a424-125">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1a424-125">Using SQL Server Management Studio</span></span>  
  
###  <a name="to-access-the-agent-profiles-dialog-box-from-sql-server-management-studio"></a><a name="Access_SSMS"></a> <span data-ttu-id="1a424-126">Доступ к диалоговому окну «Профили агентов» из среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1a424-126">To access the Agent Profiles dialog box from SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="1a424-127">На странице **Общие** диалогового окна **Свойства распространителя — \<Distributor>** щелкните элемент **Параметры профиля по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="1a424-127">On the **General** page of the **Distributor Properties - \<Distributor>** dialog box, click **Profile Defaults**.</span></span>  
  
#### <a name="to-access-the-agent-profiles-dialog-box-from-replication-monitor"></a><span data-ttu-id="1a424-128">Доступ к диалоговому окну «Профили агентов» из монитора репликации</span><span class="sxs-lookup"><span data-stu-id="1a424-128">To access the Agent Profiles dialog box from Replication Monitor</span></span>  
  
-   <span data-ttu-id="1a424-129">Чтобы открыть диалоговое окно для всех агентов, щелкните издатель правой кнопкой мыши, затем щелкните **Профили агентов**.</span><span class="sxs-lookup"><span data-stu-id="1a424-129">To open the dialog box for all agents, right-click a Publisher, and then click **Agent Profiles**.</span></span>  
  
-   <span data-ttu-id="1a424-130">Чтобы открыть диалоговое окно для одного агента:</span><span class="sxs-lookup"><span data-stu-id="1a424-130">To open the dialog box for a single agent:</span></span>  
  
    1.  <span data-ttu-id="1a424-131">На левой панели монитора репликации раскройте группу издателей, раскройте нужный издатель, а затем выберите публикацию.</span><span class="sxs-lookup"><span data-stu-id="1a424-131">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
    2.  <span data-ttu-id="1a424-132">Для доступа к профилям агента распространителя и агента слияния щелкните правой кнопкой мыши подписку на вкладке **Все подписки** , затем щелкните **Профиль агента**.</span><span class="sxs-lookup"><span data-stu-id="1a424-132">For Distribution Agent and Merge Agent profiles, right-click a subscription on the **All Subscriptions** tab, and then click **Agent Profile**.</span></span> <span data-ttu-id="1a424-133">Для других агентов щелкните правой кнопкой мыши агент на вкладке **Агенты** и выберите **Профиль агента**.</span><span class="sxs-lookup"><span data-stu-id="1a424-133">For other agents, right-click the agent on the **Agents** tab, and then click **Agent Profile**.</span></span>  
  
###  <a name="to-specify-a-profile-for-an-agent"></a><a name="Specify_SSMS"></a> <span data-ttu-id="1a424-134">Указание профиля для агента</span><span class="sxs-lookup"><span data-stu-id="1a424-134">To specify a profile for an agent</span></span>  
  
1.  <span data-ttu-id="1a424-135">Если в окне **Профили агентов** отображаются профили нескольких агентов, следует выбрать агент.</span><span class="sxs-lookup"><span data-stu-id="1a424-135">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="1a424-136">Выберите профиль в столбце **По умолчанию для новых** сетки **Профили агентов** .</span><span class="sxs-lookup"><span data-stu-id="1a424-136">Select a profile in the **Default for new** column of the **Agent profiles** grid.</span></span> <span data-ttu-id="1a424-137">По умолчанию профиль применяется к агентам только для новых публикаций и подписок.</span><span class="sxs-lookup"><span data-stu-id="1a424-137">By default, the profile is only applied to agents for new publications and subscriptions.</span></span>  
  
3.  <span data-ttu-id="1a424-138">Чтобы указать, что всем агентам выбранного типа следует использовать для существующих публикаций или подписок данный профиль, щелкните **Изменить существующие агенты**.</span><span class="sxs-lookup"><span data-stu-id="1a424-138">To specify that all agents of the selected type for existing publications or subscriptions should use this profile, click **Change existing agents**.</span></span>  
  
###  <a name="to-view-and-edit-the-parameters-associated-with-a-profile"></a><a name="Modify_SSMS"></a> <span data-ttu-id="1a424-139">Просмотр и редактирование параметров, связанных с профилем</span><span class="sxs-lookup"><span data-stu-id="1a424-139">To view and edit the parameters associated with a profile</span></span>  
  
1.  <span data-ttu-id="1a424-140">Если в окне **Профили агентов** отображаются профили нескольких агентов, следует выбрать агент.</span><span class="sxs-lookup"><span data-stu-id="1a424-140">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="1a424-141">Нажмите кнопку свойств ( **…** ), следующую за профилем.</span><span class="sxs-lookup"><span data-stu-id="1a424-141">Click the properties button (**...**) next to a profile.</span></span>  
  
3.  <span data-ttu-id="1a424-142">Просмотрите параметры и значения в диалоговом окне **Свойства профиля \<ProfileName>** .</span><span class="sxs-lookup"><span data-stu-id="1a424-142">View the parameters and values in the **\<ProfileName> Profile Properties** dialog box.</span></span>  
  
    -   <span data-ttu-id="1a424-143">Параметры в пользовательских профилях могут редактироваться, параметры же в предопределенных системных профилях недоступны для изменения.</span><span class="sxs-lookup"><span data-stu-id="1a424-143">Parameters in user-defined profiles can be edited; parameters in predefined system profiles cannot.</span></span>  
  
    -   <span data-ttu-id="1a424-144">Для просмотра всех параметров агента снимите флажок **Показывать только параметры, используемые в этом профиле** .</span><span class="sxs-lookup"><span data-stu-id="1a424-144">To view all parameters for an agent, clear the **Show only parameters used in this profile** check box.</span></span> <span data-ttu-id="1a424-145">К дополнительным сведениям о параметрах агента можно перейти по ссылкам в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="1a424-145">For information about agent parameters, see the links at the end of this topic.</span></span>  
  
4.  <span data-ttu-id="1a424-146">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1a424-146">Click **Close**.</span></span>  
  
###  <a name="to-create-a-user-defined-profile"></a><a name="Create_SSMS"></a> <span data-ttu-id="1a424-147">Создание пользовательского профиля</span><span class="sxs-lookup"><span data-stu-id="1a424-147">To create a user-defined profile</span></span>  
  
1.  <span data-ttu-id="1a424-148">Если в окне **Профили агентов** отображаются профили нескольких агентов, следует выбрать агент.</span><span class="sxs-lookup"><span data-stu-id="1a424-148">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="1a424-149">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="1a424-149">Click **New**.</span></span>  
  
3.  <span data-ttu-id="1a424-150">В диалоговом окне инициализации **Создать профиль агента** выберите существующий профиль, который будет служить основой нового профиля.</span><span class="sxs-lookup"><span data-stu-id="1a424-150">In the **New Agent Profile** initialization dialog box, select an existing profile on which to base the new profile.</span></span>  
  
4.  <span data-ttu-id="1a424-151">В диалоговом окне **Создать профиль агента** введите значения в текстовые поля **Имя** и **Описание** .</span><span class="sxs-lookup"><span data-stu-id="1a424-151">In the **New Agent Profile** dialog box, enter values in the **Name** and **Description** text boxes.</span></span>  
  
5.  <span data-ttu-id="1a424-152">Чтобы настроить профиль, измените параметры.</span><span class="sxs-lookup"><span data-stu-id="1a424-152">Modify parameters to tailor the profile.</span></span> <span data-ttu-id="1a424-153">Для просмотра всех параметров агента снимите флажок **Показывать только параметры, используемые в этом профиле** .</span><span class="sxs-lookup"><span data-stu-id="1a424-153">To view all parameters for an agent, clear the **Show only parameters used in this profile** check box.</span></span> <span data-ttu-id="1a424-154">К дополнительным сведениям о параметрах агента можно перейти по ссылкам в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="1a424-154">For information about agent parameters, see the links at the end of this topic.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
###  <a name="to-delete-a-user-defined-profile"></a><a name="Delete_SSMS"></a> <span data-ttu-id="1a424-155">Удаление пользовательского профиля</span><span class="sxs-lookup"><span data-stu-id="1a424-155">To delete a user-defined profile</span></span>  
  
1.  <span data-ttu-id="1a424-156">Если в окне **Профили агентов** отображаются профили нескольких агентов, следует выбрать агент.</span><span class="sxs-lookup"><span data-stu-id="1a424-156">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="1a424-157">Если профиль связан с одним или более агентом, измените профиль для этих агентов:</span><span class="sxs-lookup"><span data-stu-id="1a424-157">If a profile is associated with one or more agents, change the profile for those agents:</span></span>  
  
    1.  <span data-ttu-id="1a424-158">Выберите другой профиль в сетке **Профили агентов** .</span><span class="sxs-lookup"><span data-stu-id="1a424-158">Select a different profile in the **Agent profiles** grid.</span></span>  
  
    2.  <span data-ttu-id="1a424-159">Щелкните **Изменить существующие агенты**.</span><span class="sxs-lookup"><span data-stu-id="1a424-159">Click **Change existing agents**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="1a424-160">В результате изменится профиль всех агентов выбранного типа для существующих публикаций или подписок, а не только тех из них, которые вы намереваетесь удалить.</span><span class="sxs-lookup"><span data-stu-id="1a424-160">This will change the profile for all agents of the selected type for existing publications or subscriptions, not only the ones using the profile you want to delete.</span></span>  
  
3.  <span data-ttu-id="1a424-161">Выберите профиль, подлежащий удалению, затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="1a424-161">Select the profile you want to delete, and then click **Delete**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1a424-162">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1a424-162">Using Transact-SQL</span></span>  
  
###  <a name="to-create-a-new-agent-profile"></a><a name="Create_tsql"></a> <span data-ttu-id="1a424-163">Создание нового профиля агента</span><span class="sxs-lookup"><span data-stu-id="1a424-163">To create a new agent profile</span></span>  
  
1.  <span data-ttu-id="1a424-164">На распространителе выполните хранимую процедуру [sp_add_agent_profile (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-add-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1a424-164">At the Distributor, execute [sp_add_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-profile-transact-sql).</span></span> <span data-ttu-id="1a424-165">Укажите **@name** значение, равное **1** **@profile_type** , и одно из следующих значений **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="1a424-165">Specify **@name**, a value of **1** for **@profile_type**, and one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="1a424-166">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-166">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="1a424-167">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-167">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="1a424-168">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-168">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="1a424-169">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-169">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="1a424-170">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-170">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="1a424-171">Если этот профиль станет профилем по умолчанию для агента репликации данного типа, укажите значение **1** для **@default**.</span><span class="sxs-lookup"><span data-stu-id="1a424-171">If this profile will become the new default profile for its type of replication agent, specify a value of **1** for **@default**.</span></span> <span data-ttu-id="1a424-172">Идентификатор нового профиля возвращается с помощью **@profile_id** выходного параметра.</span><span class="sxs-lookup"><span data-stu-id="1a424-172">The identifier for the new profile is returned using the **@profile_id** output parameter.</span></span> <span data-ttu-id="1a424-173">Таким образом создается новый профиль с набором параметров профиля на основе профиля по умолчанию для данного типа агента.</span><span class="sxs-lookup"><span data-stu-id="1a424-173">This creates a new profile with a set of profile parameters based on the default profile for the given agent type.</span></span>  
  
2.  <span data-ttu-id="1a424-174">Когда новый профиль создан, для его настройки можно добавить, удалить или изменить параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1a424-174">After the new profile has been created, add, remove, or modify the default parameters to customize the profile.</span></span>  
  
###  <a name="to-modify-an-existing-agent-profile"></a><a name="Modify_tsql"></a> <span data-ttu-id="1a424-175">Изменение существующего профиля агента</span><span class="sxs-lookup"><span data-stu-id="1a424-175">To modify an existing agent profile</span></span>  
  
1.  <span data-ttu-id="1a424-176">На распространителе выполните хранимую процедуру [sp_help_agent_profile (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1a424-176">At the Distributor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span></span> <span data-ttu-id="1a424-177">Укажите одно из следующих значений для **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="1a424-177">Specify one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="1a424-178">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-178">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="1a424-179">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-179">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="1a424-180">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-180">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="1a424-181">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-181">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="1a424-182">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-182">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="1a424-183">Будут получены все профили для указанного типа агента.</span><span class="sxs-lookup"><span data-stu-id="1a424-183">This returns all profiles for the specified type of agent.</span></span> <span data-ttu-id="1a424-184">Запомните значение **profile_id** в результирующем наборе для профиля, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="1a424-184">Note the value of **profile_id** in the result set for the profile to change.</span></span>  
  
2.  <span data-ttu-id="1a424-185">На распространителе выполните хранимую процедуру [sp_help_agent_parameter (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-help-agent-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1a424-185">At the Distributor, execute [sp_help_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-parameter-transact-sql).</span></span> <span data-ttu-id="1a424-186">Укажите идентификатор профиля из шага 1 в параметре **@profile_id** .</span><span class="sxs-lookup"><span data-stu-id="1a424-186">Specify the profile identifier from step 1 for **@profile_id**.</span></span> <span data-ttu-id="1a424-187">В результате будут возвращены все параметры для профиля.</span><span class="sxs-lookup"><span data-stu-id="1a424-187">This returns all parameters for the profile.</span></span> <span data-ttu-id="1a424-188">Запомните имена параметров профиля, которые требуется изменить или удалить.</span><span class="sxs-lookup"><span data-stu-id="1a424-188">Note the name of any parameters to modify or remove from the profile.</span></span>  
  
3.  <span data-ttu-id="1a424-189">Чтобы изменить значение параметра в профиле, выполните хранимую процедуру [sp_change_agent_profile (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-change-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1a424-189">To change the value of a parameter in a profile, execute [sp_change_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-agent-profile-transact-sql).</span></span> <span data-ttu-id="1a424-190">Укажите идентификатор профиля из шага 1 в **@profile_id** параметре, имя параметра для изменения **@property** и новое значение параметра для **@value** .</span><span class="sxs-lookup"><span data-stu-id="1a424-190">Specify the profile identifier from step 1 for **@profile_id**, the name of the parameter to change for **@property**, and a new value for the parameter for **@value**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1a424-191">Существующий профиль агента невозможно сделать профилем по умолчанию для агента.</span><span class="sxs-lookup"><span data-stu-id="1a424-191">You cannot change an existing agent profile to become the default profile for an agent.</span></span> <span data-ttu-id="1a424-192">Профиль по умолчанию должен быть создан заново, как показано в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="1a424-192">You must instead create a new profile as the default profile, as shown in the previous procedure.</span></span>  
  
4.  <span data-ttu-id="1a424-193">Чтобы удалить параметр из профиля, выполните хранимую процедуру [sp_drop_agent_parameter (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-drop-agent-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1a424-193">To remove a parameter from a profile, execute [sp_drop_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-parameter-transact-sql).</span></span> <span data-ttu-id="1a424-194">Укажите идентификатор профиля из шага 1 в **@profile_id** параметре и имя параметра, для которого необходимо удалить **@parameter_name** .</span><span class="sxs-lookup"><span data-stu-id="1a424-194">Specify the profile identifier from step 1 for **@profile_id** and the name of the parameter to remove for **@parameter_name**.</span></span>  
  
5.  <span data-ttu-id="1a424-195">Чтобы добавить новый параметр в профиль, сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="1a424-195">To add a new parameter to a profile, you must do the following:</span></span>  
  
    -   <span data-ttu-id="1a424-196">Запросите таблицу [MSagentparameterlist (Transact-SQL)](/sql/relational-databases/system-tables/msagentparameterlist-transact-sql) на распространителе, чтобы определить, какие параметры профиля можно задать для каждого типа агента.</span><span class="sxs-lookup"><span data-stu-id="1a424-196">Query the [MSagentparameterlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/msagentparameterlist-transact-sql) table at the Distributor to determine which profile parameters can be set for each agent type.</span></span>  
  
    -   <span data-ttu-id="1a424-197">На распространителе выполните хранимую процедуру [sp_add_agent_parameter (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-add-agent-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1a424-197">At the Distributor, execute [sp_add_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-parameter-transact-sql).</span></span> <span data-ttu-id="1a424-198">Укажите идентификатор профиля из шага 1 в **@profile_id** параметре, имя допустимого параметра для добавления **@parameter_name** и значение параметра для **@parameter_value** .</span><span class="sxs-lookup"><span data-stu-id="1a424-198">Specify the profile identifier from step 1 for **@profile_id**, the name of a valid parameter to add for **@parameter_name**, and the value of the parameter for **@parameter_value**.</span></span>  
  
###  <a name="to-delete-an-agent-profile"></a><a name="Delete_tsql"></a> <span data-ttu-id="1a424-199">Удаление профиля агента</span><span class="sxs-lookup"><span data-stu-id="1a424-199">To delete an agent profile</span></span>  
  
1.  <span data-ttu-id="1a424-200">На распространителе выполните хранимую процедуру [sp_help_agent_profile (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1a424-200">At the Distributor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span></span> <span data-ttu-id="1a424-201">Укажите одно из следующих значений для **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="1a424-201">Specify one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="1a424-202">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-202">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="1a424-203">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-203">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="1a424-204">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-204">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="1a424-205">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-205">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="1a424-206">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-206">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="1a424-207">Будут получены все профили для указанного типа агента.</span><span class="sxs-lookup"><span data-stu-id="1a424-207">This returns all profiles for the specified type of agent.</span></span> <span data-ttu-id="1a424-208">Запомните **profile_id** в результирующем наборе для удаляемого профиля.</span><span class="sxs-lookup"><span data-stu-id="1a424-208">Note the value of **profile_id** in the result set for the profile to remove.</span></span>  
  
2.  <span data-ttu-id="1a424-209">На распространителе выполните хранимую процедуру [sp_drop_agent_profile (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-drop-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1a424-209">At the Distributor, execute [sp_drop_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-profile-transact-sql).</span></span> <span data-ttu-id="1a424-210">Укажите идентификатор профиля из шага 1 в параметре **@profile_id** .</span><span class="sxs-lookup"><span data-stu-id="1a424-210">Specify the profile identifier from step 1 for **@profile_id**.</span></span>  
  
###  <a name="to-use-agent-profiles-during-synchronization"></a><a name="Synch_tsql"></a> <span data-ttu-id="1a424-211">Использование профилей агента при синхронизации</span><span class="sxs-lookup"><span data-stu-id="1a424-211">To use agent profiles during synchronization</span></span>  
  
1.  <span data-ttu-id="1a424-212">На распространителе выполните хранимую процедуру [sp_help_agent_profile (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1a424-212">At the Distributor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span></span> <span data-ttu-id="1a424-213">Укажите одно из следующих значений для **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="1a424-213">Specify one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="1a424-214">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-214">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="1a424-215">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-215">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="1a424-216">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-216">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="1a424-217">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-217">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="1a424-218">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="1a424-218">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="1a424-219">Будут получены все профили для указанного типа агента.</span><span class="sxs-lookup"><span data-stu-id="1a424-219">This returns all profiles for the specified type of agent.</span></span> <span data-ttu-id="1a424-220">Запишите значение `profile_name` в результирующем наборе для используемого профиля.</span><span class="sxs-lookup"><span data-stu-id="1a424-220">Note the value of `profile_name` in the result set for the profile to use.</span></span>  
  
2.  <span data-ttu-id="1a424-221">Если агент запускается из задания агента, измените шаг задания, запускающий агент, чтобы указать значение, `profile_name` полученное на шаге 1 после параметра командной строки **-имя_профиля** .</span><span class="sxs-lookup"><span data-stu-id="1a424-221">If the agent is started from an agent job, edit the job step that starts the agent to specify the value of `profile_name` obtained in step 1 after the **-ProfileName** command-line parameter.</span></span> <span data-ttu-id="1a424-222">Дополнительные сведения см. в статье [View and Modify Replication Agent Command Prompt Parameters](view-and-modify-replication-agent-command-prompt-parameters.md) (Просмотр и изменение параметров командной строки агента репликации).</span><span class="sxs-lookup"><span data-stu-id="1a424-222">For more information, see [View and Modify Replication Agent Command Prompt Parameters &#40;SQL Server Management Studio&#41;](view-and-modify-replication-agent-command-prompt-parameters.md).</span></span>  
  
3.  <span data-ttu-id="1a424-223">При запуске агента из командной строки укажите значение, `profile_name` полученное на шаге 1 после параметра **-имя_профиля** в командной строке.</span><span class="sxs-lookup"><span data-stu-id="1a424-223">When starting the agent from the command prompt, specify the value of `profile_name` obtained in step 1 after the **-ProfileName** command-line parameter.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="1a424-224">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1a424-224">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="1a424-225">В этом примере создается пользовательский профиль для агента слияния с именем **custom_merge**, меняется значение параметра **-UploadReadChangesPerBatch** , добавляется новый параметр **-ExchangeType** и выводятся сведения о созданном профиле.</span><span class="sxs-lookup"><span data-stu-id="1a424-225">This example creates a custom profile for the Merge Agent named **custom_merge**, changes the value of the **-UploadReadChangesPerBatch** parameter, adds a new **-ExchangeType** parameter, and returns information on the profile that is created.</span></span>  
  
 [!code-sql[HowTo#sp_addagentprofileparam](../../../snippets/tsql/SQL15/replication/howto/tsql/createperfparammerge.sql#sp_addagentprofileparam)]  
  
##  <a name="using-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="1a424-226">При помощи объектов RMO</span><span class="sxs-lookup"><span data-stu-id="1a424-226">Using RMO</span></span>  
  
###  <a name="to-create-a-new-agent-profile"></a><a name="Create_RMO"></a> <span data-ttu-id="1a424-227">Создание нового профиля агента</span><span class="sxs-lookup"><span data-stu-id="1a424-227">To create a new agent profile</span></span>  
  
1.  <span data-ttu-id="1a424-228">Создайте соединение с распространителем с помощью экземпляра класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="1a424-228">Create a connection to the Distributor by using an instance of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="1a424-229">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.AgentProfile>.</span><span class="sxs-lookup"><span data-stu-id="1a424-229">Create an instance of the <xref:Microsoft.SqlServer.Replication.AgentProfile> class.</span></span>  
  
3.  <span data-ttu-id="1a424-230">Установите следующие свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="1a424-230">Set the following properties on the object:</span></span>  
  
    -   <span data-ttu-id="1a424-231"><xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> — имя профиля.</span><span class="sxs-lookup"><span data-stu-id="1a424-231"><xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> - the name for the profile.</span></span>  
  
    -   <span data-ttu-id="1a424-232"><xref:Microsoft.SqlServer.Replication.AgentProfile.AgentType%2A> – значение <xref:Microsoft.SqlServer.Replication.AgentType> , указывающее на тип агента репликации, для которого создается профиль.</span><span class="sxs-lookup"><span data-stu-id="1a424-232"><xref:Microsoft.SqlServer.Replication.AgentProfile.AgentType%2A> - an <xref:Microsoft.SqlServer.Replication.AgentType> value that specifies the type of replication agent for which the profile is being created.</span></span>  
  
    -   <span data-ttu-id="1a424-233"><xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> – значение <xref:Microsoft.SqlServer.Management.Common.ServerConnection> , созданного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="1a424-233"><xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> - the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> created in step 1.</span></span>  
  
    -   <span data-ttu-id="1a424-234"><xref:Microsoft.SqlServer.Replication.AgentProfile.Description%2A> – описание профиля (необязательно).</span><span class="sxs-lookup"><span data-stu-id="1a424-234">(Optional) <xref:Microsoft.SqlServer.Replication.AgentProfile.Description%2A> - a description of the profile.</span></span>  
  
    -   <span data-ttu-id="1a424-235"><xref:Microsoft.SqlServer.Replication.AgentProfile.Default%2A>  – установите в значение `true`, если во всех заданиях агентов для данного <xref:Microsoft.SqlServer.Replication.AgentType> этот профиль будет использоваться по умолчанию (необязательно).</span><span class="sxs-lookup"><span data-stu-id="1a424-235">(Optional) <xref:Microsoft.SqlServer.Replication.AgentProfile.Default%2A> - set this property to `true` if all new agent jobs for this <xref:Microsoft.SqlServer.Replication.AgentType> will use this profile by default.</span></span>  
  
4.  <span data-ttu-id="1a424-236">Вызовите метод <xref:Microsoft.SqlServer.Replication.AgentProfile.Create%2A> для создания профиля на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="1a424-236">Call the <xref:Microsoft.SqlServer.Replication.AgentProfile.Create%2A> method to create the profile on the server.</span></span>  
  
5.  <span data-ttu-id="1a424-237">После создания профиля на сервере можно производить его настройку, добавляя, удаляя или изменяя значения параметров агента репликации.</span><span class="sxs-lookup"><span data-stu-id="1a424-237">Once the profile exists on the server, you can customize it by adding, removing, or changing the values of replication agent parameters.</span></span>  
  
6.  <span data-ttu-id="1a424-238">Назначение профиля для существующего задания агента репликации производится методом <xref:Microsoft.SqlServer.Replication.AgentProfile.AssignToAgent%2A> .</span><span class="sxs-lookup"><span data-stu-id="1a424-238">To assign the profile to an existing replication agent job, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.AssignToAgent%2A> method.</span></span> <span data-ttu-id="1a424-239">В качестве параметра *distributionDBName* передайте имя базы данных распространителя, а в параметре *agentID*— идентификатор задания.</span><span class="sxs-lookup"><span data-stu-id="1a424-239">Pass the name of the distribution database for *distributionDBName* and the ID of the job for *agentID*.</span></span>  
  
###  <a name="to-modify-an-existing-agent-profile"></a><a name="Modify_RMO"></a> <span data-ttu-id="1a424-240">Изменение существующего профиля агента</span><span class="sxs-lookup"><span data-stu-id="1a424-240">To modify an existing agent profile</span></span>  
  
1.  <span data-ttu-id="1a424-241">Создайте соединение с распространителем с помощью экземпляра класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="1a424-241">Create a connection to the Distributor by using an instance of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="1a424-242">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="1a424-242">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span> <span data-ttu-id="1a424-243">Передайте объект <xref:Microsoft.SqlServer.Management.Common.ServerConnection> , созданный на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="1a424-243">Pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object created in step 1.</span></span>  
  
3.  <span data-ttu-id="1a424-244">Вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="1a424-244">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="1a424-245">Если этот метод возвратил значение `false`, проверьте, существует ли распространитель.</span><span class="sxs-lookup"><span data-stu-id="1a424-245">If this method returns `false`, verify that the Distributor exists.</span></span>  
  
4.  <span data-ttu-id="1a424-246">Вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationServer.EnumAgentProfiles%2A> .</span><span class="sxs-lookup"><span data-stu-id="1a424-246">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.EnumAgentProfiles%2A> method.</span></span> <span data-ttu-id="1a424-247">Передайте значение <xref:Microsoft.SqlServer.Replication.AgentType> , чтобы возвращались только те профили, которые предназначены для конкретного типа агента репликации.</span><span class="sxs-lookup"><span data-stu-id="1a424-247">Pass an <xref:Microsoft.SqlServer.Replication.AgentType> value to narrow down the returned profiles to a specific type of replication agent.</span></span>  
  
5.  <span data-ttu-id="1a424-248">Извлеките объект <xref:Microsoft.SqlServer.Replication.AgentProfile> из возвращенного списка <xref:System.Collections.ArrayList>, где свойство <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> объекта соответствует имени профиля.</span><span class="sxs-lookup"><span data-stu-id="1a424-248">Get the desired <xref:Microsoft.SqlServer.Replication.AgentProfile> object from the returned <xref:System.Collections.ArrayList>, where the <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> property of the object matches the profile name.</span></span>  
  
6.  <span data-ttu-id="1a424-249">Чтобы изменить профиль, вызовите один из следующих методов объекта <xref:Microsoft.SqlServer.Replication.AgentProfile> .</span><span class="sxs-lookup"><span data-stu-id="1a424-249">Call one of the following methods of <xref:Microsoft.SqlServer.Replication.AgentProfile> to change the profile:</span></span>  
  
    -   <span data-ttu-id="1a424-250"><xref:Microsoft.SqlServer.Replication.AgentProfile.AddParameter%2A> – добавляет к профилю поддерживаемый параметр, где *name* – имя параметра агента репликации, а *value* – заданное значение.</span><span class="sxs-lookup"><span data-stu-id="1a424-250"><xref:Microsoft.SqlServer.Replication.AgentProfile.AddParameter%2A> - adds a supported parameter to the profile, where *name* is the name of the replication agent parameter and *value* is the specified value.</span></span> <span data-ttu-id="1a424-251">Перебор всех поддерживаемых параметров агента для данного типа агента производится методом <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> .</span><span class="sxs-lookup"><span data-stu-id="1a424-251">To enumerate all supported agent parameters for a given agent type, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> method.</span></span> <span data-ttu-id="1a424-252">Этот метод возвращает список <xref:System.Collections.ArrayList> , содержащий объекты <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> , которые представляют все поддерживаемые параметры.</span><span class="sxs-lookup"><span data-stu-id="1a424-252">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> objects that represent all supported parameters.</span></span>  
  
    -   <span data-ttu-id="1a424-253"><xref:Microsoft.SqlServer.Replication.AgentProfile.RemoveParameter%2A> – удаляет один из существующих параметров из профиля, где *name* – имя параметра агента репликации.</span><span class="sxs-lookup"><span data-stu-id="1a424-253"><xref:Microsoft.SqlServer.Replication.AgentProfile.RemoveParameter%2A> - removes an existing parameter from the profile, where *name* is the name of the replication agent parameter.</span></span> <span data-ttu-id="1a424-254">Чтобы перечислить все определенные для профиля параметры текущего агента, вызовите метод <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> .</span><span class="sxs-lookup"><span data-stu-id="1a424-254">To enumerate all current agent parameters defined for the profile, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> method.</span></span> <span data-ttu-id="1a424-255">Этот метод возвращает список <xref:System.Collections.ArrayList> объектов <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> , которые представляют существующие параметры для данного профиля.</span><span class="sxs-lookup"><span data-stu-id="1a424-255">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> objects that represent the existing parameter for this profile.</span></span>  
  
    -   <span data-ttu-id="1a424-256"><xref:Microsoft.SqlServer.Replication.AgentProfile.ChangeParameter%2A> – изменяет значение существующего параметра профиля, где *name* – имя параметра агента, а *newValue* – значение, которое параметр получает после изменения.</span><span class="sxs-lookup"><span data-stu-id="1a424-256"><xref:Microsoft.SqlServer.Replication.AgentProfile.ChangeParameter%2A> - changes the setting of an existing parameter in the profile, where *name* is the name of the agent parameter and *newValue* is the value to which the parameter is being changed.</span></span> <span data-ttu-id="1a424-257">Чтобы перечислить все определенные для профиля параметры текущего агента, вызовите метод <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> .</span><span class="sxs-lookup"><span data-stu-id="1a424-257">To enumerate all current agent parameters defined for the profile, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> method.</span></span> <span data-ttu-id="1a424-258">Этот метод возвращает список <xref:System.Collections.ArrayList> объектов <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> , которые представляют существующие параметры для данного профиля.</span><span class="sxs-lookup"><span data-stu-id="1a424-258">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> objects that represent the existing parameter for this profile.</span></span> <span data-ttu-id="1a424-259">Перебор всех поддерживаемых параметров агента производится методом <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> .</span><span class="sxs-lookup"><span data-stu-id="1a424-259">To enumerate all supported agent parameter settings, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> method.</span></span> <span data-ttu-id="1a424-260">Этот метод возвращает список <xref:System.Collections.ArrayList> , содержащий объекты <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> , которые представляют поддерживаемые значения для всех параметров.</span><span class="sxs-lookup"><span data-stu-id="1a424-260">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> objects that represent the supported values for all parameters.</span></span>  
  
###  <a name="to-delete-an-agent-profile"></a><a name="Delete_RMO"></a> <span data-ttu-id="1a424-261">Удаление профиля агента</span><span class="sxs-lookup"><span data-stu-id="1a424-261">To delete an agent profile</span></span>  
  
1.  <span data-ttu-id="1a424-262">Создайте соединение с распространителем с помощью экземпляра класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="1a424-262">Create a connection to the Distributor by using an instance of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="1a424-263">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.AgentProfile>.</span><span class="sxs-lookup"><span data-stu-id="1a424-263">Create an instance of the <xref:Microsoft.SqlServer.Replication.AgentProfile> class.</span></span> <span data-ttu-id="1a424-264">Присвойте имя профиля свойству <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> и значение <xref:Microsoft.SqlServer.Management.Common.ServerConnection> , полученное на шаге 1, свойству <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="1a424-264">Set the name of the profile for <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> and the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="1a424-265">Вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="1a424-265">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="1a424-266">Если метод вернул значение `false`, то имя указано неверно или профиль не существует на сервере.</span><span class="sxs-lookup"><span data-stu-id="1a424-266">If this method returns `false`, either the specified name was incorrect or the profile does not exist on the server.</span></span>  
  
4.  <span data-ttu-id="1a424-267">Удостоверьтесь в том, что свойству <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A> присвоено значение <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.User>, указывающее на клиентский профиль.</span><span class="sxs-lookup"><span data-stu-id="1a424-267">Verify that the <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A> property is set to <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.User>, which indicates a customer profile.</span></span> <span data-ttu-id="1a424-268">Не следует удалять профиль, имеющий значение <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.System> в свойстве <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A>.</span><span class="sxs-lookup"><span data-stu-id="1a424-268">You should not remove a profile that has a value of <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.System> for <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A>.</span></span>  
  
5.  <span data-ttu-id="1a424-269">Вызовите метод <xref:Microsoft.SqlServer.Replication.AgentProfile.Remove%2A> для удаления с сервера пользовательского профиля, представляемого этим объектом.</span><span class="sxs-lookup"><span data-stu-id="1a424-269">Call the <xref:Microsoft.SqlServer.Replication.AgentProfile.Remove%2A> method to remove the user-defined profile represented by this object from the server.</span></span>  
  
##  <a name="follow-up-after-changing-agent-parameters"></a><a name="FollowUp"></a> <span data-ttu-id="1a424-270">Дальнейшие действия. После изменения параметров агента</span><span class="sxs-lookup"><span data-stu-id="1a424-270">Follow Up: After Changing Agent Parameters</span></span>  
 <span data-ttu-id="1a424-271">Изменения параметров агента вступают в действие при следующем запуске агента.</span><span class="sxs-lookup"><span data-stu-id="1a424-271">Agent parameter changes take effect the next time the agent is started.</span></span> <span data-ttu-id="1a424-272">Если агент выполняется в непрерывном режиме, следует остановить и перезапустить агент.</span><span class="sxs-lookup"><span data-stu-id="1a424-272">If the agent runs continuously, you must stop and restart the agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a424-273">См. также:</span><span class="sxs-lookup"><span data-stu-id="1a424-273">See Also</span></span>  
 <span data-ttu-id="1a424-274">[Профили агента репликации](replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="1a424-274">[Replication Agent Profiles](replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="1a424-275">[Replication Snapshot Agent](replication-snapshot-agent.md) </span><span class="sxs-lookup"><span data-stu-id="1a424-275">[Replication Snapshot Agent](replication-snapshot-agent.md) </span></span>  
 <span data-ttu-id="1a424-276">[Replication Log Reader Agent](replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="1a424-276">[Replication Log Reader Agent](replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="1a424-277">[Replication Distribution Agent](replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="1a424-277">[Replication Distribution Agent](replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="1a424-278">[Replication Merge Agent](replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="1a424-278">[Replication Merge Agent](replication-merge-agent.md) </span></span>  
 [<span data-ttu-id="1a424-279">Replication Queue Reader Agent</span><span class="sxs-lookup"><span data-stu-id="1a424-279">Replication Queue Reader Agent</span></span>](replication-queue-reader-agent.md)  
  
  
