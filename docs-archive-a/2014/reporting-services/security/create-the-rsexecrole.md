---
title: Создание роли RSExecRole | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RSExecRole
ms.assetid: 7ac17341-df7e-4401-870e-652caa2859c0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0037ef0c4d7a949b5a30bb45356613f6114db130
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731401"
---
# <a name="create-the-rsexecrole"></a><span data-ttu-id="9575e-102">Создание роли RSExecRole</span><span class="sxs-lookup"><span data-stu-id="9575e-102">Create the RSExecRole</span></span>
  <span data-ttu-id="9575e-103">Службы [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] используют стандартную роль базы данных с именем `RSExecRole`, чтобы предоставить серверу отчетов разрешения в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9575e-103">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] uses a predefined database role called `RSExecRole` to grant report server permissions to the report server database.</span></span> <span data-ttu-id="9575e-104">Роль `RSExecRole` создается автоматически с базой данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9575e-104">The `RSExecRole` role is created automatically with the report server database.</span></span> <span data-ttu-id="9575e-105">Как правило, никогда не следует изменять ее или назначать другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="9575e-105">As a rule, you should never modify it or assign other users to the role.</span></span> <span data-ttu-id="9575e-106">Однако при перемещении базы данных сервера отчетов в новое или другое значение [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../../includes/ssde-md.md)] необходимо повторно создать роль в системных базах данных master и msdb.</span><span class="sxs-lookup"><span data-stu-id="9575e-106">However, when you move a report server database to a new or different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../../includes/ssde-md.md)], must re-create the role in the Master and MSDB system databases.</span></span>

 <span data-ttu-id="9575e-107">С помощью следующих инструкций выполняются следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="9575e-107">Using the following instructions, you will perform the following steps:</span></span>

-   <span data-ttu-id="9575e-108">Создание и предоставление роли `RSExecRole` в системной базе данных master.</span><span class="sxs-lookup"><span data-stu-id="9575e-108">Create and provision the `RSExecRole` in the Master system database.</span></span>

-   <span data-ttu-id="9575e-109">Создание и предоставление роли `RSExecRole` в системной базе данных msdb.</span><span class="sxs-lookup"><span data-stu-id="9575e-109">Create and provision the `RSExecRole` in the MSDB system database.</span></span>

> [!NOTE]
>  <span data-ttu-id="9575e-110">Инструкции в этом разделе предназначены для пользователей, которые не хотят запускать скрипт или писать код инструментария WMI для предоставления базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9575e-110">The instructions in this topic are intended for users who do not want to run a script or write WMI code to provision the report server database.</span></span> <span data-ttu-id="9575e-111">Если предстоит управлять большим развертыванием и регулярно перемещать базы данных, необходимо подготовить скрипт для автоматизации этих шагов.</span><span class="sxs-lookup"><span data-stu-id="9575e-111">If you manage a large deployment and will be moving databases routinely, you should write a script to automate these steps.</span></span> <span data-ttu-id="9575e-112">Дополнительные сведения см. в разделе [Доступ к поставщику WMI для служб Reporting Services](../tools/access-the-reporting-services-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="9575e-112">For more information, see [Access the Reporting Services WMI Provider](../tools/access-the-reporting-services-wmi-provider.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="9575e-113">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="9575e-113">Before you start</span></span>

-   <span data-ttu-id="9575e-114">Создайте резервную копию ключей шифрования, чтобы их можно было восстановить после перемещения базы данных.</span><span class="sxs-lookup"><span data-stu-id="9575e-114">Back up the encryption keys so that you can restore them after the database is moved.</span></span> <span data-ttu-id="9575e-115">Этот шаг не влияет напрямую на возможность создавать и предоставлять роль `RSExecRole`, но резервная копия ключей необходима, чтобы проверить работу.</span><span class="sxs-lookup"><span data-stu-id="9575e-115">This is step does not directly affect your ability to create and provision the `RSExecRole`, but you must have a backup of the keys in order to verify your work.</span></span> <span data-ttu-id="9575e-116">Дополнительные сведения см. в разделе [Резервное копирование и восстановление ключей шифрования служб Reporting Services](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md).</span><span class="sxs-lookup"><span data-stu-id="9575e-116">For more information, see [Back Up and Restore Reporting Services Encryption Keys](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md).</span></span>

-   <span data-ttu-id="9575e-117">Проверьте, что выполнен вход в систему под учетной записью пользователя, у которой есть разрешения `sysadmin` на экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9575e-117">Verify you are logged on as a user account that has `sysadmin` permissions on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span>

-   <span data-ttu-id="9575e-118">Проверьте, что служба агента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] установлена и работает на экземпляре компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)] , который планируется использовать.</span><span class="sxs-lookup"><span data-stu-id="9575e-118">Verify [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service is installed and running on the instance of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] instance that you plan to use.</span></span>

-   <span data-ttu-id="9575e-119">Присоедините базы данных reportservertempdb и reportserver.</span><span class="sxs-lookup"><span data-stu-id="9575e-119">Attach the reportservertempdb and reportserver databases.</span></span> <span data-ttu-id="9575e-120">Не требуется присоединять базы данных, чтобы создать собственно роль, но они должны быть присоединены, прежде чем удастся проверить работу.</span><span class="sxs-lookup"><span data-stu-id="9575e-120">You are not required to attach the databases to create the actual role, but they must be attached before you can test your work.</span></span>

 <span data-ttu-id="9575e-121">Инструкции для создания роли `RSExecRole` вручную предназначены для использования в контексте миграции установки сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9575e-121">The instructions for manually creating the `RSExecRole` are intended to be used within the context of migrating a report server installation.</span></span> <span data-ttu-id="9575e-122">Важные задачи, такие как резервное копирование и перемещение базы данных сервера отчетов, не рассматриваются в данном разделе, но описаны в документации по компоненту Database Engine.</span><span class="sxs-lookup"><span data-stu-id="9575e-122">Important tasks such as backing up and moving the report server database are not addressed in this topic, but are documented in the Database Engine documentation.</span></span>

## <a name="create-rsexecrole-in-master"></a><span data-ttu-id="9575e-123">Создание роли RSExecRole в базе данных master</span><span class="sxs-lookup"><span data-stu-id="9575e-123">Create RSExecRole in Master</span></span>
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="9575e-124">используют расширенные хранимые процедуры для службы агента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9575e-124">uses extended stored procedures for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service to support scheduled operations.</span></span> <span data-ttu-id="9575e-125">Следующие шаги поясняют, как предоставить разрешения EXECUTE для процедур роли `RSExecRole`.</span><span class="sxs-lookup"><span data-stu-id="9575e-125">The following steps explain how to grant Execute permissions for the procedures to the `RSExecRole` role.</span></span>

#### <a name="to-create-rsexecrole-in-the-master-system-database-using-management-studio"></a><span data-ttu-id="9575e-126">Создание роли RSExecRole в системной базе данных master с помощью среды Management Studio</span><span class="sxs-lookup"><span data-stu-id="9575e-126">To create RSExecRole in the Master system database using Management Studio</span></span>

1.  <span data-ttu-id="9575e-127">Запустите среду [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] и подключитесь к экземпляру [!INCLUDE[ssDE](../../../includes/ssde-md.md)], на котором размещается база данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9575e-127">Start [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] instance that hosts the report server database.</span></span>

2.  <span data-ttu-id="9575e-128">Откройте узел **Базы данных**.</span><span class="sxs-lookup"><span data-stu-id="9575e-128">Open **Databases**.</span></span>

3.  <span data-ttu-id="9575e-129">Откройте узел **Системные базы данных**.</span><span class="sxs-lookup"><span data-stu-id="9575e-129">Open **System Databases**.</span></span>

4.  <span data-ttu-id="9575e-130">Откройте `Master`.</span><span class="sxs-lookup"><span data-stu-id="9575e-130">Open `Master`.</span></span>

5.  <span data-ttu-id="9575e-131">Откройте **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="9575e-131">Open **Security**.</span></span>

6.  <span data-ttu-id="9575e-132">Откройте **Роли**.</span><span class="sxs-lookup"><span data-stu-id="9575e-132">Open **Roles**.</span></span>

7.  <span data-ttu-id="9575e-133">Щелкните правой кнопкой мыши **Роли базы данных**и выберите пункт **Создать роль базы данных**.</span><span class="sxs-lookup"><span data-stu-id="9575e-133">Right-click **Database Roles**, and select **New Database Role**.</span></span> <span data-ttu-id="9575e-134">Отображается страница «Общие».</span><span class="sxs-lookup"><span data-stu-id="9575e-134">The General page appears.</span></span>

8.  <span data-ttu-id="9575e-135">В окне **имя роли**введите `RSExecRole` .</span><span class="sxs-lookup"><span data-stu-id="9575e-135">In **Role name**, type `RSExecRole`.</span></span>

9. <span data-ttu-id="9575e-136">В поле **Владелец**введите **DBO**.</span><span class="sxs-lookup"><span data-stu-id="9575e-136">In **Owner**, type **DBO**.</span></span>

10. <span data-ttu-id="9575e-137">Щелкните **Защищаемые объекты**.</span><span class="sxs-lookup"><span data-stu-id="9575e-137">Click **Securables**.</span></span>

11. <span data-ttu-id="9575e-138">Нажмите кнопку **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="9575e-138">Click **Search**.</span></span> <span data-ttu-id="9575e-139">Отображается диалоговое окно **Добавление объектов** .</span><span class="sxs-lookup"><span data-stu-id="9575e-139">The **Add Objects** dialog box appears.</span></span> <span data-ttu-id="9575e-140">Параметр **Определенные объекты** выбран по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9575e-140">The **Specific Objects** option is selected by default.</span></span>

12. <span data-ttu-id="9575e-141">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9575e-141">Click **OK**.</span></span> <span data-ttu-id="9575e-142">Появится диалоговое окно **Выбор объектов** .</span><span class="sxs-lookup"><span data-stu-id="9575e-142">The **Select Objects** dialog box appears.</span></span>

13. <span data-ttu-id="9575e-143">Щелкните **Типы объектов**.</span><span class="sxs-lookup"><span data-stu-id="9575e-143">Click **Object Types**.</span></span>

14. <span data-ttu-id="9575e-144">Щелкните **Расширенные хранимые процедуры**.</span><span class="sxs-lookup"><span data-stu-id="9575e-144">Click **Extended Stored Procedures**.</span></span>

15. <span data-ttu-id="9575e-145">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9575e-145">Click **OK**.</span></span>

16. <span data-ttu-id="9575e-146">Нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="9575e-146">Click **Browse**.</span></span>

17. <span data-ttu-id="9575e-147">Прокрутите список расширенных хранимых процедур и выберите следующие:</span><span class="sxs-lookup"><span data-stu-id="9575e-147">Scroll down the list of extended stored procedures and select the following:</span></span>

    1.  <span data-ttu-id="9575e-148">xp_sqlagent_enum_jobs</span><span class="sxs-lookup"><span data-stu-id="9575e-148">xp_sqlagent_enum_jobs</span></span>

    2.  <span data-ttu-id="9575e-149">xp_sqlagent_is_starting</span><span class="sxs-lookup"><span data-stu-id="9575e-149">xp_sqlagent_is_starting</span></span>

    3.  <span data-ttu-id="9575e-150">xp_sqlagent_notify</span><span class="sxs-lookup"><span data-stu-id="9575e-150">xp_sqlagent_notify</span></span>

18. <span data-ttu-id="9575e-151">Нажмите кнопку **ОК**, а затем еще раз кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="9575e-151">Click **OK**, and the click **OK** again.</span></span>

19. <span data-ttu-id="9575e-152">В строке **Выполнить** в столбце **Предоставить** установите флажок и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9575e-152">In the **Execute** row, in the **Grant** column, click the check box, and then click **OK**.</span></span>

20. <span data-ttu-id="9575e-153">Повторите действия для каждой оставшейся хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="9575e-153">Repeat for each of the remaining stored procedures.</span></span> <span data-ttu-id="9575e-154">Роль `RSExecRole` должна иметь разрешения EXECUTE для всех трех хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="9575e-154">`RSExecRole` must be granted Execute permissions for all three stored procedures.</span></span>

 <span data-ttu-id="9575e-155">![Страница свойств ролей базы данных](../media/rsexecroledbproperties.gif "Страница свойств ролей базы данных")</span><span class="sxs-lookup"><span data-stu-id="9575e-155">![Database Role Properties page](../media/rsexecroledbproperties.gif "Database Role Properties page")</span></span>

## <a name="create-rsexecrole-in-msdb"></a><span data-ttu-id="9575e-156">Создание роли RSExecRole в базе данных msdb</span><span class="sxs-lookup"><span data-stu-id="9575e-156">Create RSExecRole in MSDB</span></span>
 <span data-ttu-id="9575e-157">Службы Reporting Services используют хранимые процедуры для службы агента SQL Server и получают сведения о заданиях из системных таблиц для поддержки запланированных действий.</span><span class="sxs-lookup"><span data-stu-id="9575e-157">Reporting Services uses stored procedures for SQL Server Agent service and retrieves job information from system tables to support scheduled operations.</span></span> <span data-ttu-id="9575e-158">Следующие шаги поясняют, как предоставить роли RSExecRole разрешения EXECUTE для процедур и разрешений SELECT в таблицах.</span><span class="sxs-lookup"><span data-stu-id="9575e-158">The following steps explain how to grant Execute permissions for the procedures and Select permissions on the tables to the RSExecRole.</span></span>

#### <a name="to-create-rsexecrole-in-the-msdb-system-database"></a><span data-ttu-id="9575e-159">Создание роли RSExecRole в системной базе данных msdb</span><span class="sxs-lookup"><span data-stu-id="9575e-159">To create RSExecRole in the MSDB system database</span></span>

1.  <span data-ttu-id="9575e-160">Повторите аналогичные шаги, чтобы предоставить разрешения хранимым процедурам и таблицам в базе данных msdb.</span><span class="sxs-lookup"><span data-stu-id="9575e-160">Repeat similar steps for granting permissions to stored procedures and tables in MSDB.</span></span> <span data-ttu-id="9575e-161">Чтобы упростить шаги, обрабатывайте хранимые процедуры и таблицы отдельно.</span><span class="sxs-lookup"><span data-stu-id="9575e-161">To simplify the steps, you will provision the stored procedures and tables separately.</span></span>

2.  <span data-ttu-id="9575e-162">Откройте `MSDB`.</span><span class="sxs-lookup"><span data-stu-id="9575e-162">Open `MSDB`.</span></span>

3.  <span data-ttu-id="9575e-163">Откройте **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="9575e-163">Open **Security**.</span></span>

4.  <span data-ttu-id="9575e-164">Откройте **Роли**.</span><span class="sxs-lookup"><span data-stu-id="9575e-164">Open **Roles**.</span></span>

5.  <span data-ttu-id="9575e-165">Щелкните правой кнопкой мыши **Роли базы данных**и выберите пункт **Создать роль базы данных**.</span><span class="sxs-lookup"><span data-stu-id="9575e-165">Right-click **Database Roles**, and select **New Database Role**.</span></span> <span data-ttu-id="9575e-166">Отображается страница «Общие».</span><span class="sxs-lookup"><span data-stu-id="9575e-166">The General page appears.</span></span>

6.  <span data-ttu-id="9575e-167">В окне имя роли введите `RSExecRole` .</span><span class="sxs-lookup"><span data-stu-id="9575e-167">In Role name, type `RSExecRole`.</span></span>

7.  <span data-ttu-id="9575e-168">В окне Владелец введите **dbo**.</span><span class="sxs-lookup"><span data-stu-id="9575e-168">In Owner, type **DBO**.</span></span>

8.  <span data-ttu-id="9575e-169">Щелкните **Защищаемые объекты**.</span><span class="sxs-lookup"><span data-stu-id="9575e-169">Click **Securables**.</span></span>

9. <span data-ttu-id="9575e-170">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9575e-170">Click **Add**.</span></span> <span data-ttu-id="9575e-171">Отображается диалоговое окно **Добавление объектов** .</span><span class="sxs-lookup"><span data-stu-id="9575e-171">The **Add Objects** dialog box appears.</span></span> <span data-ttu-id="9575e-172">Параметр **Выбрать объекты** выбран по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9575e-172">The **Specify Objects** option is selected by default.</span></span>

10. <span data-ttu-id="9575e-173">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9575e-173">Click **OK**.</span></span>

11. <span data-ttu-id="9575e-174">Щелкните **Типы объектов**.</span><span class="sxs-lookup"><span data-stu-id="9575e-174">Click **Object Types**.</span></span>

12. <span data-ttu-id="9575e-175">Щелкните **Хранимые процедуры**.</span><span class="sxs-lookup"><span data-stu-id="9575e-175">Click **Stored Procedures.**</span></span>

13. <span data-ttu-id="9575e-176">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9575e-176">Click **OK**.</span></span>

14. <span data-ttu-id="9575e-177">Нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="9575e-177">Click **Browse**.</span></span>

15. <span data-ttu-id="9575e-178">Прокрутите список объектов и выберите следующие:</span><span class="sxs-lookup"><span data-stu-id="9575e-178">Scroll down the list of items and select the following:</span></span>

    1.  <span data-ttu-id="9575e-179">sp_add_category</span><span class="sxs-lookup"><span data-stu-id="9575e-179">sp_add_category</span></span>

    2.  <span data-ttu-id="9575e-180">sp_add_job</span><span class="sxs-lookup"><span data-stu-id="9575e-180">sp_add_job</span></span>

    3.  <span data-ttu-id="9575e-181">sp_add_jobschedule</span><span class="sxs-lookup"><span data-stu-id="9575e-181">sp_add_jobschedule</span></span>

    4.  <span data-ttu-id="9575e-182">sp_add_jobserver</span><span class="sxs-lookup"><span data-stu-id="9575e-182">sp_add_jobserver</span></span>

    5.  <span data-ttu-id="9575e-183">sp_add_jobstep</span><span class="sxs-lookup"><span data-stu-id="9575e-183">sp_add_jobstep</span></span>

    6.  <span data-ttu-id="9575e-184">sp_delete_job</span><span class="sxs-lookup"><span data-stu-id="9575e-184">sp_delete_job</span></span>

    7.  <span data-ttu-id="9575e-185">sp_help_category</span><span class="sxs-lookup"><span data-stu-id="9575e-185">sp_help_category</span></span>

    8.  <span data-ttu-id="9575e-186">sp_help_job</span><span class="sxs-lookup"><span data-stu-id="9575e-186">sp_help_job</span></span>

    9. <span data-ttu-id="9575e-187">sp_help_jobschedule</span><span class="sxs-lookup"><span data-stu-id="9575e-187">sp_help_jobschedule</span></span>

    10. <span data-ttu-id="9575e-188">sp_verify_job_identifiers</span><span class="sxs-lookup"><span data-stu-id="9575e-188">sp_verify_job_identifiers</span></span>

16. <span data-ttu-id="9575e-189">Нажмите кнопку **ОК**, а затем еще раз кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="9575e-189">Click **OK**, and the click **OK** again.</span></span>

17. <span data-ttu-id="9575e-190">Выберите первую хранимую процедуру sp_add_category.</span><span class="sxs-lookup"><span data-stu-id="9575e-190">Select the first stored procedure: sp_add_category.</span></span>

18. <span data-ttu-id="9575e-191">В строке **Выполнить** в столбце **Предоставить** установите флажок и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9575e-191">In the **Execute** row, in the **Grant** column, click the checkbox, and then click **OK**.</span></span>

19. <span data-ttu-id="9575e-192">Повторите действия для каждой оставшейся хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="9575e-192">Repeat for each of the remaining stored procedures.</span></span> <span data-ttu-id="9575e-193">Роли RSExecRole должны быть предоставлены разрешения EXECUTE для всех десяти хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="9575e-193">RSExecRole must be granted Execute permissions for all ten stored procedures.</span></span>

20. <span data-ttu-id="9575e-194">На вкладке «Защищаемые объекты» повторно нажмите кнопку **Добавить** .</span><span class="sxs-lookup"><span data-stu-id="9575e-194">On the Securables tab, and click **Add** again.</span></span> <span data-ttu-id="9575e-195">Отображается диалоговое окно **Добавление объектов** .</span><span class="sxs-lookup"><span data-stu-id="9575e-195">The **Add Objects** dialog box appears.</span></span> <span data-ttu-id="9575e-196">Параметр **Выбрать объекты** выбран по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9575e-196">The **Specify Objects** option is selected by default.</span></span>

21. <span data-ttu-id="9575e-197">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9575e-197">Click **OK**.</span></span>

22. <span data-ttu-id="9575e-198">Щелкните **Типы объектов**.</span><span class="sxs-lookup"><span data-stu-id="9575e-198">Click **Object Types**.</span></span>

23. <span data-ttu-id="9575e-199">Щелкните **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="9575e-199">Click **Tables.**</span></span>

24. <span data-ttu-id="9575e-200">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9575e-200">Click **OK**.</span></span>

25. <span data-ttu-id="9575e-201">Нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="9575e-201">Click **Browse**.</span></span>

26. <span data-ttu-id="9575e-202">Прокрутите список объектов и выберите следующие:</span><span class="sxs-lookup"><span data-stu-id="9575e-202">Scroll down the list of items and select the following:</span></span>

    1.  <span data-ttu-id="9575e-203">syscategories</span><span class="sxs-lookup"><span data-stu-id="9575e-203">syscategories</span></span>

    2.  <span data-ttu-id="9575e-204">sysjobs</span><span class="sxs-lookup"><span data-stu-id="9575e-204">sysjobs</span></span>

27. <span data-ttu-id="9575e-205">Нажмите кнопку **ОК**, а затем еще раз кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="9575e-205">Click **OK**, and the click **OK** again.</span></span>

28. <span data-ttu-id="9575e-206">Выберите первую таблицу — syscategories.</span><span class="sxs-lookup"><span data-stu-id="9575e-206">Select the first table: syscategories.</span></span>

29. <span data-ttu-id="9575e-207">В строке **Выбрать** в столбце **Предоставить** установите флажок и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9575e-207">In the **Select** row, in the **Grant** column, click the checkbox, and then click **OK**.</span></span>

30. <span data-ttu-id="9575e-208">Повторите для таблицы sysjobs.</span><span class="sxs-lookup"><span data-stu-id="9575e-208">Repeat for the sysjobs table.</span></span> <span data-ttu-id="9575e-209">Роли RSExecRole должны быть предоставлены разрешения SELECT для обеих таблиц.</span><span class="sxs-lookup"><span data-stu-id="9575e-209">RSExecRole must be granted Select permissions for both tables.</span></span>

## <a name="move-the-report-server-database"></a><span data-ttu-id="9575e-210">Перемещение базы данных сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="9575e-210">Move the Report Server Database</span></span>
 <span data-ttu-id="9575e-211">После создания ролей можно переместить базу данных сервера отчетов на новый экземпляр SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9575e-211">After you create the roles, you can move the report server database to new SQL Server instance.</span></span> <span data-ttu-id="9575e-212">Дополнительные сведения см. в разделе [Перемещение баз данных сервера отчетов на другой компьютер (собственный режим служб SSRS)](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="9575e-212">For more information, see [Moving the Report Server Databases to Another Computer &#40;SSRS Native Mode&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md).</span></span>

 <span data-ttu-id="9575e-213">Если компонент [!INCLUDE[ssDE](../../../includes/ssde-md.md)] обновляется до [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], можно обновить его до или после перемещения базы данных.</span><span class="sxs-lookup"><span data-stu-id="9575e-213">If you are upgrading the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], you can upgrade it before or after moving the database.</span></span>

 <span data-ttu-id="9575e-214">База данных сервера отчетов обновляется автоматически до уровня [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] при подключении к ней сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9575e-214">The report server database will be upgraded to the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] automatically when the report server connects to it.</span></span> <span data-ttu-id="9575e-215">Для обновления этой базы данных не требуется никаких конкретных шагов.</span><span class="sxs-lookup"><span data-stu-id="9575e-215">There are no specific steps required for upgrading the database.</span></span>

## <a name="restore-encryption-keys-and-verify-your-work"></a><span data-ttu-id="9575e-216">Восстановление ключей шифрования и проверка проделанной работы</span><span class="sxs-lookup"><span data-stu-id="9575e-216">Restore Encryption Keys and Verify Your Work</span></span>
 <span data-ttu-id="9575e-217">Если имеются присоединенные базы данных сервера отчетов, можно выполнить следующие шаги для проверки работы.</span><span class="sxs-lookup"><span data-stu-id="9575e-217">If you have attached the report server databases, you should now be able to complete the following steps to verify your work.</span></span>

#### <a name="to-verify-report-server-operability-after-a-database-move"></a><span data-ttu-id="9575e-218">Проверка работоспособности сервера отчетов после перемещения базы данных</span><span class="sxs-lookup"><span data-stu-id="9575e-218">To verify report server operability after a database move</span></span>

1.  <span data-ttu-id="9575e-219">Запустите программу настройки служб Reporting Services и подключитесь к серверу отчетов.</span><span class="sxs-lookup"><span data-stu-id="9575e-219">Start the Reporting Services Configuration tool and connect to the report server.</span></span>

2.  <span data-ttu-id="9575e-220">Щелкните **База данных**.</span><span class="sxs-lookup"><span data-stu-id="9575e-220">Click **Database**.</span></span>

3.  <span data-ttu-id="9575e-221">Нажмите кнопку **Изменить базу данных**.</span><span class="sxs-lookup"><span data-stu-id="9575e-221">Click **Change Database**.</span></span>

4.  <span data-ttu-id="9575e-222">Щелкните **Выбрать существующую базу данных сервера отчетов**.</span><span class="sxs-lookup"><span data-stu-id="9575e-222">Click **Choose an existing report server database**.</span></span>

5.  <span data-ttu-id="9575e-223">Введите имя экземпляра сервера компонента Database Engine.</span><span class="sxs-lookup"><span data-stu-id="9575e-223">Enter the server name of the Database Engine.</span></span> <span data-ttu-id="9575e-224">Если базы данных сервера отчетов присоединены к именованному экземпляру, необходимо ввести имя экземпляра в следующем формате: \<servername> \\<instanceName \> .</span><span class="sxs-lookup"><span data-stu-id="9575e-224">If you attached the report server databases to a named instance, you must type the instance name in this format: \<servername>\\<instancename\>.</span></span>

6.  <span data-ttu-id="9575e-225">Нажмите кнопку **Проверить соединение**.</span><span class="sxs-lookup"><span data-stu-id="9575e-225">Click **Test Connection**.</span></span>

7.  <span data-ttu-id="9575e-226">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9575e-226">Click **Next**.</span></span>

8.  <span data-ttu-id="9575e-227">На странице «База данных» выберите базу данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9575e-227">On the Database, select the report server database.</span></span>

9. <span data-ttu-id="9575e-228">Нажмите кнопку **Далее** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="9575e-228">Click **Next** and complete the wizard.</span></span>

10. <span data-ttu-id="9575e-229">Щелкните **Ключи шифрования**.</span><span class="sxs-lookup"><span data-stu-id="9575e-229">Click **Encryption Keys**.</span></span>

11. <span data-ttu-id="9575e-230">Нажмите кнопку **восстановить**.</span><span class="sxs-lookup"><span data-stu-id="9575e-230">Click **Restore**.</span></span>

12. <span data-ttu-id="9575e-231">Выберите файл ключа для строгого имени (SNK), который содержит резервную копию симметричного ключа, используемого для расшифровки сохраненных учетных данных и сведений о соединении с базой данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9575e-231">Select the strong file (.snk) that has the backup copy of the symmetric key used to decrypt stored credentials and connection information in the report server database.</span></span>

13. <span data-ttu-id="9575e-232">Введите пароль и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9575e-232">Enter the password and click **OK**.</span></span>

14. <span data-ttu-id="9575e-233">Нажмите кнопку **URL-адрес диспетчера отчетов**.</span><span class="sxs-lookup"><span data-stu-id="9575e-233">Click **Report Manager URL**.</span></span>

15. <span data-ttu-id="9575e-234">Щелкните ссылку, чтобы открыть диспетчер отчетов.</span><span class="sxs-lookup"><span data-stu-id="9575e-234">Click the link to open Report Manager.</span></span> <span data-ttu-id="9575e-235">Будут отображены элементы сервера отчетов из базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="9575e-235">You should see the report server items from the report server database.</span></span>

## <a name="see-also"></a><span data-ttu-id="9575e-236">См. также:</span><span class="sxs-lookup"><span data-stu-id="9575e-236">See Also</span></span>
 <span data-ttu-id="9575e-237">[Перемещение баз данных сервера отчетов на другой компьютер &#40;служб SSRS в собственном режиме&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md) [Диспетчер конфигурации служб Reporting Services &#40;собственном режиме&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) [Создание базы данных сервера отчетов в собственном режиме &#40;службы SSRS Configuration Manager&#41;](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md) [резервное копирование и восстановление Reporting Services ключи шифрования](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)</span><span class="sxs-lookup"><span data-stu-id="9575e-237">[Moving the Report Server Databases to Another Computer &#40;SSRS Native Mode&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md) [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) [Create a Native Mode Report Server Database  &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md) [Back Up and Restore Reporting Services Encryption Keys](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)</span></span>


