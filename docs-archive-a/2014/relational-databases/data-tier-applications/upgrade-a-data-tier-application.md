---
title: Обновление приложения уровня данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.upgradedacwizard.reviewpolicy.f1
- sql12.swb.upgradedacwizard.selectoptions.f1
- sql12.swb.upgradedacwizard.selectpackage.f1
- sql12.swb.upgradedacwizard.reviewplan.f1
- sql12.swb.upgradedacwizard.checkdrift.f1
- sql12.swb.upgradedacwizard.summary.f1
- sql12.swb.upgradedacwizard.upgradedac.f1
- sql12.swb.upgradedacwizard.introduction.f1
helpviewer_keywords:
- upgrade DAC
- data-tier application [SQL Server], upgrade
- wizard [DAC], upgrade
- How to [DAC], upgrade
ms.assetid: c117df94-f02b-403f-9383-ec5b3ac3763c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0e597d02af28a16539b50ff76503059278ef7a03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668385"
---
# <a name="upgrade-a-data-tier-application"></a><span data-ttu-id="e3b68-102">Обновление приложения уровня данных</span><span class="sxs-lookup"><span data-stu-id="e3b68-102">Upgrade a Data-tier Application</span></span>
  <span data-ttu-id="e3b68-103">Используйте мастер обновления приложений уровня данных или скрипт Windows PowerShell, чтобы изменить схему и свойства приложения уровня данных (DAC), развернутого на данный момент, для соответствия схеме и свойствам, заданным в новой версии приложений уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-103">Use either the Upgrade Data-tier Application Wizard or a Windows PowerShell script to change the schema and properties of a currently deployed data-tier application (DAC) to match the schema and properties defined in a new version of the DAC.</span></span>  
  
-   <span data-ttu-id="e3b68-104">**Перед началом работы**  [Выбор параметров обновления DAC](#ChoseDACUpgOptions), [Ограничения](#LimitationsRestrictions), [Предварительные требования](#Prerequisites), [Безопасность](#Security), [Разрешения](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="e3b68-104">**Before you begin:**  [Choosing DAC Upgrade Options](#ChoseDACUpgOptions), [Limitations and Restrictions](#LimitationsRestrictions), [Prerequisites](#Prerequisites), [Security](#Security), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="e3b68-105">**Обновление приложения уровня данных с использованием:**  [мастера обновления приложения уровня данных](#UsingDACUpgradeWizard), [PowerShell](#UpgradeDACPowerShell)</span><span class="sxs-lookup"><span data-stu-id="e3b68-105">**To upgrade a DAC, using:**  [The Upgrade Data-tier Application Wizard](#UsingDACUpgradeWizard), [PowerShell](#UpgradeDACPowerShell)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e3b68-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="e3b68-106">Before You Begin</span></span>  
 <span data-ttu-id="e3b68-107">Обновление приложения уровня данных — это процесс, который выполняется на месте и изменяет схему существующей базы для соответствия схеме, заданной в новой версии приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-107">A DAC upgrade is an in-place process that alters the schema of the existing database to match the schema defined in a new version of the DAC.</span></span> <span data-ttu-id="e3b68-108">Новая версия приложения уровня данных содержится в файле пакета приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-108">The new version of the DAC is supplied in a DAC package file.</span></span> <span data-ttu-id="e3b68-109">Дополнительные сведения о создании пакета DAC см. в разделе [Приложения уровня данных](data-tier-applications.md).</span><span class="sxs-lookup"><span data-stu-id="e3b68-109">For more information about creating a DAC package, see [Data-tier Applications](data-tier-applications.md).</span></span>  
  
###  <a name="choosing-dac-upgrade-options"></a><a name="ChoseDACUpgOptions"></a> <span data-ttu-id="e3b68-110">выбор параметров обновления DAC</span><span class="sxs-lookup"><span data-stu-id="e3b68-110">Choosing DAC Upgrade Options</span></span>  
 <span data-ttu-id="e3b68-111">Для обновления на месте существует четыре варианта:</span><span class="sxs-lookup"><span data-stu-id="e3b68-111">There are four upgrade options for an in-place upgrade:</span></span>  
  
-   <span data-ttu-id="e3b68-112">**Игнорировать потери данных** . Если `True` обновление будет продолжено, даже если некоторые операции приведут к утрате данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-112">**Ignore Data Loss** - If `True`, the upgrade will proceed even if some of the operations result in the loss of data.</span></span> <span data-ttu-id="e3b68-113">если этот параметр равен `False`, обновление прекращается при обнаружении таких операций.</span><span class="sxs-lookup"><span data-stu-id="e3b68-113">If `False`, these operations will terminate the upgrade.</span></span> <span data-ttu-id="e3b68-114">Например, если какая-то таблица текущей базы данных отсутствует в схеме нового приложения уровня данных и этот параметр равен `True`, такая таблица будет удалена.</span><span class="sxs-lookup"><span data-stu-id="e3b68-114">For example, if a table in the current database is not present in the schema of the new DAC, the table will be dropped if `True` is specified.</span></span> <span data-ttu-id="e3b68-115">Значение по умолчанию — `True`.</span><span class="sxs-lookup"><span data-stu-id="e3b68-115">The default setting is `True`.</span></span>  
  
-   <span data-ttu-id="e3b68-116">**Блокировать при изменении** . Если `True` значение равно, то обновление будет завершено, если схема базы данных отличается от схемы, определенной в предыдущем приложении DAC.</span><span class="sxs-lookup"><span data-stu-id="e3b68-116">**Block on Changes** - If `True`, the upgrade is terminated if the database schema is different than that defined in the previous DAC.</span></span> <span data-ttu-id="e3b68-117">Если этот параметр равен `False`, обновление продолжится даже в случае обнаружения изменений.</span><span class="sxs-lookup"><span data-stu-id="e3b68-117">If `False`, the upgrade continues even if changes are detected.</span></span> <span data-ttu-id="e3b68-118">Значение по умолчанию — `False`.</span><span class="sxs-lookup"><span data-stu-id="e3b68-118">The default setting is `False`.</span></span>  
  
-   <span data-ttu-id="e3b68-119">**Откат в случае сбоя** — если `True` Обновление заключается в транзакцию, а при возникновении ошибок будет предпринята попытка отката.</span><span class="sxs-lookup"><span data-stu-id="e3b68-119">**Rollback on Failure** - If `True`, the upgrade is enclosed in a transaction, and if errors are encountered a rollback will be attempted.</span></span> <span data-ttu-id="e3b68-120">Если этот параметр равен `False`, все изменения фиксируются по мере внесения, а в случае сбоя придется восстанавливать предыдущую версию базы данных с резервной копии.</span><span class="sxs-lookup"><span data-stu-id="e3b68-120">If `False`, all changes are committed as they are made and if errors occur you may have to restore a previous backup of the database.</span></span> <span data-ttu-id="e3b68-121">Значение по умолчанию — `False`.</span><span class="sxs-lookup"><span data-stu-id="e3b68-121">The default setting is `False`.</span></span>  
  
-   <span data-ttu-id="e3b68-122">**Пропустить проверку политики** — `True` значение, если политика выбора сервера DAC не оценивается.</span><span class="sxs-lookup"><span data-stu-id="e3b68-122">**Skip Policy Validation** - If `True`, the DAC server selection policy is not evaluated.</span></span> <span data-ttu-id="e3b68-123">Если этот параметр равен `False`, проверка политики производится, а в случае обнаружения несоответствия обновление прекращается.</span><span class="sxs-lookup"><span data-stu-id="e3b68-123">If `False`, the policy is evaluated and the upgrade terminates if there is a validation error.</span></span> <span data-ttu-id="e3b68-124">Значение по умолчанию — `False`.</span><span class="sxs-lookup"><span data-stu-id="e3b68-124">The default setting is `False`.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="e3b68-125">Ограничения</span><span class="sxs-lookup"><span data-stu-id="e3b68-125">Limitations and Restrictions</span></span>  
 <span data-ttu-id="e3b68-126">Обновление приложений уровня данных возможно только в [!INCLUDE[ssSDS](../../includes/sssds-md.md)]или [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] с пакетом управления 4 (SP4) или более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="e3b68-126">DAC uprades can only be performed in [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="e3b68-127">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="e3b68-127">Prerequisites</span></span>  
 <span data-ttu-id="e3b68-128">Перед началом обновления рекомендуется сделать полную резервную копию базы данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-128">It is prudent to take a full database backup before starting the upgrade.</span></span> <span data-ttu-id="e3b68-129">Если при обновлении возникнет ошибка и откатить все изменения не удастся, может потребоваться восстановление с резервной копии.</span><span class="sxs-lookup"><span data-stu-id="e3b68-129">If an upgrade encounters an error and cannot roll back all of its changes, you may need to restore the backup.</span></span>  
  
 <span data-ttu-id="e3b68-130">Прежде чем начинать обновление, необходимо выполнить некоторые шаги для проверки пакета DAC и действий обновления.</span><span class="sxs-lookup"><span data-stu-id="e3b68-130">Before starting the upgrade, there are several actions that you should take to validate the DAC package and the upgrade actions.</span></span> <span data-ttu-id="e3b68-131">Дополнительные сведения о том, как выполнить эти проверки, см. в разделе [Validate a DAC Package](validate-a-dac-package.md).</span><span class="sxs-lookup"><span data-stu-id="e3b68-131">For more information about how to perform these checks, see [Validate a DAC Package](validate-a-dac-package.md).</span></span>  
  
-   <span data-ttu-id="e3b68-132">Рекомендуется не выполнять обновление с помощью пакета приложения уровня данных, полученного из неизвестных или ненадежных источников.</span><span class="sxs-lookup"><span data-stu-id="e3b68-132">We recommend that you do not upgrade by using a DAC package from unknown or untrusted sources.</span></span> <span data-ttu-id="e3b68-133">Эти пакеты могут содержать вредоносный код, который может выполнить непредусмотренный код Transact-SQL или вызвать ошибки, изменив схему.</span><span class="sxs-lookup"><span data-stu-id="e3b68-133">Such packages could contain malicious code that might execute unintended Transact-SQL code or cause errors by modifying the schema.</span></span> <span data-ttu-id="e3b68-134">Прежде чем использовать пакет из неизвестного или ненадежного источника, распакуйте приложение уровня данных и проверьте такой код, как хранимые процедуры или другой пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="e3b68-134">Before you use a package from an unknown or untrusted source, unpack the DAC and examine the code, such as stored procedures or other user-defined code.</span></span>  
  
-   <span data-ttu-id="e3b68-135">Если в действующую базу данных вносились изменения после развертывания последней версии приложения уровня данных, некоторые такие изменения могут помешать успешному обновлению или будут удалены при обновлении.</span><span class="sxs-lookup"><span data-stu-id="e3b68-135">If changes have been made to the current database after the last version of the DAC was deployed, some of the changes may prevent the successful completion of the upgrade, or be removed by the upgrade.</span></span> <span data-ttu-id="e3b68-136">Сначала следует создать и проанализировать отчет обо всех изменениях, внесенных в базу данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-136">You should first generate and review a report of any such changes made in the database.</span></span>  
  
-   <span data-ttu-id="e3b68-137">Рекомендуется создать список изменений схемы, которые будут внесены при обновлении, и проанализировать его на предмет возможных проблем.</span><span class="sxs-lookup"><span data-stu-id="e3b68-137">It is prudent to generate a list of the schema changes the upgrade will perform, and review the list for any problems.</span></span>  
  
 <span data-ttu-id="e3b68-138">Имя приложения в пакете приложения уровня данных должно быть таким же, как и имя приложения развернутого приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-138">The application name in the DAC package must match the application name of the currently deployed DAC.</span></span> <span data-ttu-id="e3b68-139">Например, если имя текущего приложения уровня данных — **GeneralLedger**, то обновить его можно только с помощью пакета приложения уровня данных с именем приложения **GeneralLedger**.</span><span class="sxs-lookup"><span data-stu-id="e3b68-139">For example, if the current DAC has an application name of **GeneralLedger**, you can only upgrade by using a DAC package that also has an application name of **GeneralLedger**.</span></span>  
  
 <span data-ttu-id="e3b68-140">Проверить, что в журнале транзакций достаточно места для регистрации всех изменений.</span><span class="sxs-lookup"><span data-stu-id="e3b68-140">Ensure there is enough transaction log space available to log all of the modifications.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e3b68-141">безопасность</span><span class="sxs-lookup"><span data-stu-id="e3b68-141">Security</span></span>  
 <span data-ttu-id="e3b68-142">Для повышения безопасности имена входа, использующие проверку подлинности SQL Server, хранятся в пакете DAC без пароля.</span><span class="sxs-lookup"><span data-stu-id="e3b68-142">To improve security, SQL Server Authentication logins are stored in a DAC package without a password.</span></span> <span data-ttu-id="e3b68-143">При развертывании или обновлении пакета имя входа создается как отключенное имя входа с созданным паролем.</span><span class="sxs-lookup"><span data-stu-id="e3b68-143">When the package is deployed or upgraded, the login is created as a disabled login with a generated password.</span></span> <span data-ttu-id="e3b68-144">Чтобы включить имена входа, войдите в систему под учетной записью, имеющей разрешение ALTER ANY LOGIN и с помощью команды ALTER LOGIN включите имя входа и присвойте ему новый пароль, который можно передать пользователю.</span><span class="sxs-lookup"><span data-stu-id="e3b68-144">To enable the logins, log in using a login that has ALTER ANY LOGIN permission and use ALTER LOGIN to enable the login and assign a new password that can be communicated to the user.</span></span> <span data-ttu-id="e3b68-145">Это не требуется для имен входа, использующих проверку подлинности Windows, поскольку SQL Server не управляет их паролями.</span><span class="sxs-lookup"><span data-stu-id="e3b68-145">This is not needed for Windows Authentication logins because their passwords are not managed by SQL Server.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e3b68-146">Permissions</span><span class="sxs-lookup"><span data-stu-id="e3b68-146">Permissions</span></span>  
 <span data-ttu-id="e3b68-147">Обновление DAC может проводиться только членами стандартных ролей сервера **sysadmin** или **serveradmin** , либо членами стандартной роли сервера **dbcreator** с правами доступа ALTER ANY LOGIN.</span><span class="sxs-lookup"><span data-stu-id="e3b68-147">A DAC can only be upgraded by members of the **sysadmin** or **serveradmin** fixed server roles, or by logins that are in the **dbcreator** fixed server role and have ALTER ANY LOGIN permissions.</span></span> <span data-ttu-id="e3b68-148">Имя входа должно быть владельцем существующей базы данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-148">The login must be the owner of the existing database.</span></span> <span data-ttu-id="e3b68-149">Встроенная учетная запись администратора системы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с именем **sa** также может обновлять приложение уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-149">The built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator account named **sa** can also upgrade a DAC.</span></span>  
  
##  <a name="using-the-upgrade-data-tier-application-wizard"></a><a name="UsingDACUpgradeWizard"></a> <span data-ttu-id="e3b68-150">Использование мастера обновления приложения уровня данных</span><span class="sxs-lookup"><span data-stu-id="e3b68-150">Using the Upgrade Data-tier Application Wizard</span></span>  
 <span data-ttu-id="e3b68-151">**Обновление приложения уровня данных с помощью мастера**</span><span class="sxs-lookup"><span data-stu-id="e3b68-151">**To Upgrade a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="e3b68-152">В **Обозревателе объектов**разверните узел экземпляра с приложением уровня данных, которое требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="e3b68-152">In **Object Explorer**, expand the node for the instance containing the DAC to be upgraded.</span></span>  
  
2.  <span data-ttu-id="e3b68-153">Разверните узел **Управление** , а затем узел **Приложения уровня данных** .</span><span class="sxs-lookup"><span data-stu-id="e3b68-153">Expand the **Management** node, and then expand the **Data-tier Applications** node.</span></span>  
  
3.  <span data-ttu-id="e3b68-154">Щелкните правой кнопкой мыши узел с обновляемым приложением уровня данных и выберите пункт **Обновить приложение уровня данных…** .</span><span class="sxs-lookup"><span data-stu-id="e3b68-154">Right-click the node for the DAC to be upgraded, and then select **Upgrade Data-tier Application...**</span></span>  
  
4.  <span data-ttu-id="e3b68-155">Выполните шаги в диалоговых окнах мастера.</span><span class="sxs-lookup"><span data-stu-id="e3b68-155">Complete the wizard dialogs:</span></span>  
  
    1.  [<span data-ttu-id="e3b68-156">Вводная страница</span><span class="sxs-lookup"><span data-stu-id="e3b68-156">Introduction Page</span></span>](#Introduction)  
  
    2.  [<span data-ttu-id="e3b68-157">Страница «Выбор пакета»</span><span class="sxs-lookup"><span data-stu-id="e3b68-157">Select Package Page</span></span>](#Select_dac_package)  
  
    3.  [<span data-ttu-id="e3b68-158">Страница «Просмотр политики»</span><span class="sxs-lookup"><span data-stu-id="e3b68-158">Review Policy Page</span></span>](#Review_policy)  
  
    4.  [<span data-ttu-id="e3b68-159">Страница «Обнаружение изменений»</span><span class="sxs-lookup"><span data-stu-id="e3b68-159">Detect Change Page</span></span>](#Detect_change)  
  
    5.  [<span data-ttu-id="e3b68-160">Анализ плана обновления</span><span class="sxs-lookup"><span data-stu-id="e3b68-160">Review the Upgrade Plan</span></span>](#ReviewUpgPlan)  
  
    6.  [<span data-ttu-id="e3b68-161">Страница «Сводка»</span><span class="sxs-lookup"><span data-stu-id="e3b68-161">Summary Page</span></span>](#Summary)  
  
    7.  [<span data-ttu-id="e3b68-162">Страница «Обновление DAC»</span><span class="sxs-lookup"><span data-stu-id="e3b68-162">Upgrade DAC Page</span></span>](#Upgrade)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="e3b68-163">Вводная страница</span><span class="sxs-lookup"><span data-stu-id="e3b68-163">Introduction Page</span></span>  
 <span data-ttu-id="e3b68-164">На этой странице описаны шаги обновления приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-164">This page describes the steps for upgrading a data-tier application.</span></span>  
  
 <span data-ttu-id="e3b68-165">**Больше не показывать эту страницу.**</span><span class="sxs-lookup"><span data-stu-id="e3b68-165">**Do not show this page again.**</span></span> <span data-ttu-id="e3b68-166">— щелкните этот флажок, чтобы предотвратить отображение этой страницы в будущем.</span><span class="sxs-lookup"><span data-stu-id="e3b68-166">- Click the check box to stop the page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="e3b68-167">**Далее >**  — переход на страницу **Выбор пакета**.</span><span class="sxs-lookup"><span data-stu-id="e3b68-167">**Next >** - Proceeds to the **Select Package** page.</span></span>  
  
 <span data-ttu-id="e3b68-168">**Отмена** — работа мастера завершается без обновления DAC.</span><span class="sxs-lookup"><span data-stu-id="e3b68-168">**Cancel** - Terminates the wizard without upgrading the DAC.</span></span>  
  
##  <a name="select-package-page"></a><a name="Select_dac_package"></a> <span data-ttu-id="e3b68-169">Страница «Выбор пакета»</span><span class="sxs-lookup"><span data-stu-id="e3b68-169">Select Package Page</span></span>  
 <span data-ttu-id="e3b68-170">На этой странице указывается пакет приложения уровня данных, содержащий новую версию приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-170">Use this page to specify the DAC package that contains the new version of the data-tier application.</span></span> <span data-ttu-id="e3b68-171">Страница проходит через два состояния.</span><span class="sxs-lookup"><span data-stu-id="e3b68-171">The page transitions through two states.</span></span>  
  
### <a name="select-the-dac-package"></a><span data-ttu-id="e3b68-172">Выбор пакета DAC</span><span class="sxs-lookup"><span data-stu-id="e3b68-172">Select the DAC Package</span></span>  
 <span data-ttu-id="e3b68-173">Чтобы выбрать пакет DAC для развертывания, воспользуйтесь первоначальным состоянием страницы.</span><span class="sxs-lookup"><span data-stu-id="e3b68-173">Use the initial state of the page to choose the DAC package to deploy.</span></span> <span data-ttu-id="e3b68-174">Пакет DAC должен представлять собой работоспособный файл пакета DAC с расширением DACPAC.</span><span class="sxs-lookup"><span data-stu-id="e3b68-174">The DAC package must be a valid DAC package file and must have a .dacpac extension.</span></span> <span data-ttu-id="e3b68-175">Имя приложения уровня данных в пакете приложения уровня данных должно быть таким же, как и имя текущего приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-175">The DAC application name in the DAC package must be the same as the application name of the current DAC.</span></span>  
  
 <span data-ttu-id="e3b68-176">**Пакет приложения уровня данных** — укажите путь и имя файла пакета приложения уровня данных, содержащего новую версию приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-176">**DAC Package** - Specify the path and file name of the DAC package that contains the new version of the data-tier application.</span></span> <span data-ttu-id="e3b68-177">Чтобы указать расположение пакета DAC, можно нажать кнопку **Обзор** в правой части окна.</span><span class="sxs-lookup"><span data-stu-id="e3b68-177">You can select the **Browse** button at the right of the box to browse to the location of the DAC package.</span></span>  
  
 <span data-ttu-id="e3b68-178">**Имя приложения** — доступное только для чтения текстовое поле, в котором отображается имя приложения уровня данных, присвоенное при создании приложения уровня данных или извлечении из базы данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-178">**Application Name** - A read-only box that displays the DAC application name assigned when the DAC was authored or extracted from a database.</span></span>  
  
 <span data-ttu-id="e3b68-179">**Версия** — доступное только для чтения поле, в котором отображается версия, присвоенная пакету DAC при создании или извлечении из базы данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-179">**Version** - A read-only box that displays the version assigned when the DAC was authored or extracted from a database.</span></span>  
  
 <span data-ttu-id="e3b68-180">**Описание** — доступное только для чтения поле, в котором отображается описание, сделанное при создании или извлечении пакета DAC из базы данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-180">**Description** - A read-only box that displays the description written when the DAC was authored or extracted from a database.</span></span>  
  
 <span data-ttu-id="e3b68-181">\*\* \< Назад\*\* — возврат на страницу **Введение** .</span><span class="sxs-lookup"><span data-stu-id="e3b68-181">**\< Previous** - Returns to the **Introduction** page.</span></span>  
  
 <span data-ttu-id="e3b68-182">**Далее >**  — отображается индикатор выполнения, когда мастер подтверждает, что выбранный файл является исправным пакетом приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-182">**Next >** - Displays a progress bar as the wizard confirms that the selected file is a valid DAC package.</span></span>  
  
 <span data-ttu-id="e3b68-183">**Отмена** — работа мастера завершается без обновления DAC.</span><span class="sxs-lookup"><span data-stu-id="e3b68-183">**Cancel** - Terminates the wizard without upgrading the DAC.</span></span>  
  
### <a name="validating-the-dac-package"></a><span data-ttu-id="e3b68-184">Проверка пакета DAC</span><span class="sxs-lookup"><span data-stu-id="e3b68-184">Validating the DAC Package</span></span>  
 <span data-ttu-id="e3b68-185">Отображается индикатор выполнения, когда мастер подтверждает, что выбранный файл является исправным пакетом DAC.</span><span class="sxs-lookup"><span data-stu-id="e3b68-185">Displays a progress bar as the wizard confirms that the selected file is a valid DAC package.</span></span> <span data-ttu-id="e3b68-186">Если выполняется проверка пакета приложения уровня данных, то мастер перейдет на страницу **Просмотр политики** .</span><span class="sxs-lookup"><span data-stu-id="e3b68-186">If the DAC package is validated, the wizard proceeds to the **Review Policy** page.</span></span> <span data-ttu-id="e3b68-187">Если файл не является допустимым пакетом DAC, мастер остается на странице **Выбор пакета DAC** .</span><span class="sxs-lookup"><span data-stu-id="e3b68-187">If the file is not a valid DAC package, the wizard remains on the **Select DAC Package** page.</span></span> <span data-ttu-id="e3b68-188">Выберите другой исправный пакет DAC, либо выйдите из мастера и создайте новый пакет DAC.</span><span class="sxs-lookup"><span data-stu-id="e3b68-188">Either select another valid DAC package or cancel the wizard and generate a new DAC package.</span></span>  
  
 <span data-ttu-id="e3b68-189">**Проверка содержимого DAC** — индикатор выполнения, отражающий текущее состояние процесса выполнения.</span><span class="sxs-lookup"><span data-stu-id="e3b68-189">**Validating the contents of the DAC** - The progress bar that reports the current status of the validation process.</span></span>  
  
 <span data-ttu-id="e3b68-190">\*\* \< Назад\*\* — возврат к начальному состоянию страницы **Выбор пакета** .</span><span class="sxs-lookup"><span data-stu-id="e3b68-190">**\< Previous** - Returns to the initial state of the **Select Package** page.</span></span>  
  
 <span data-ttu-id="e3b68-191">**Далее >**  — переход к окончательной версии страницы **Выбор пакета**.</span><span class="sxs-lookup"><span data-stu-id="e3b68-191">**Next >** - Proceeds to the final version of the **Select Package** page.</span></span>  
  
 <span data-ttu-id="e3b68-192">**Отмена** — мастер прекращает работу без развертывания DAC.</span><span class="sxs-lookup"><span data-stu-id="e3b68-192">**Cancel** - Terminates the wizard without deploying the DAC.</span></span>  
  
##  <a name="review-policy-page"></a><a name="Review_policy"></a> <span data-ttu-id="e3b68-193">Страница «Просмотр политики»</span><span class="sxs-lookup"><span data-stu-id="e3b68-193">Review Policy Page</span></span>  
 <span data-ttu-id="e3b68-194">На этой странице можно просмотреть результаты проверки политики выбора на сервере DAC, если у DAC есть политика.</span><span class="sxs-lookup"><span data-stu-id="e3b68-194">Use this page to review the results of evaluating the DAC server selection policy, if the DAC has a policy.</span></span> <span data-ttu-id="e3b68-195">Политика выбора сервера приложения уровня данных не является обязательной, она назначается приложению уровня данных, созданному в среде Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e3b68-195">The DAC server selection policy is optional, and is assigned to a DAC authored in Microsoft Visual Studio.</span></span> <span data-ttu-id="e3b68-196">Политика с помощью аспектов политики выбора серверов задает условия, которым экземпляр компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] должен соответствовать, чтобы на нем можно было размещать DAC.</span><span class="sxs-lookup"><span data-stu-id="e3b68-196">The policy uses the server selection policy facets to specify conditions an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] should meet to host the DAC.</span></span>  
  
 <span data-ttu-id="e3b68-197">**Результаты проверки условий политики** — доступный только для чтения отчет, показывающий, успешно ли прошла оценка условий в политике выбора сервера приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-197">**Evaluation results of policy conditions** - A read-only report showing whether the evaluations of the conditions in the DAC server selection policy succeeded.</span></span> <span data-ttu-id="e3b68-198">Результаты проверки каждого из условий выводятся отдельной строкой.</span><span class="sxs-lookup"><span data-stu-id="e3b68-198">The results of evaluating each condition are reported on a separate line.</span></span>  
  
 <span data-ttu-id="e3b68-199">**Пропускать нарушения политик** — установите этот флажок, чтобы приступить к обновлению, если не удалось соблюсти одно или несколько условий политики.</span><span class="sxs-lookup"><span data-stu-id="e3b68-199">**Ignore policy violations** - Use this check box to proceed with the upgrade if one or more of the policy conditions failed.</span></span> <span data-ttu-id="e3b68-200">Этот параметр следует выбирать только при уверенности, что ни одно из невыполненных условий не будет препятствовать успешной работе DAC.</span><span class="sxs-lookup"><span data-stu-id="e3b68-200">Only select this option if you are sure that all of the conditions which failed will not prevent the successful operation of the DAC.</span></span>  
  
 <span data-ttu-id="e3b68-201">\*\* \< Назад\*\* — возврат на страницу **Выбор пакета** .</span><span class="sxs-lookup"><span data-stu-id="e3b68-201">**\< Previous** - Returns to the **Select Package** page.</span></span>  
  
 <span data-ttu-id="e3b68-202">**Далее >**  — переход на страницу **Обнаружение изменений**.</span><span class="sxs-lookup"><span data-stu-id="e3b68-202">**Next >** - Proceeds to the **Detect Change** page.</span></span>  
  
 <span data-ttu-id="e3b68-203">**Отмена** — работа мастера завершается без обновления DAC.</span><span class="sxs-lookup"><span data-stu-id="e3b68-203">**Cancel** - Terminates the wizard without upgrading the DAC.</span></span>  
  
##  <a name="detect-change-page"></a><a name="Detect_change"></a> <span data-ttu-id="e3b68-204">Страница «Обнаружение изменений»</span><span class="sxs-lookup"><span data-stu-id="e3b68-204">Detect Change Page</span></span>  
 <span data-ttu-id="e3b68-205">На этой странице отображаются результаты проверки изменений в базе данных, выполненной мастером. Это изменения, из-за которых схема базы данных отличается от определения схемы, которое хранится в метаданных приложения уровня данных в базе данных **msdb**.</span><span class="sxs-lookup"><span data-stu-id="e3b68-205">Use this page reports the results of the wizards check for changes made to the database that make it's schema different than the schema definition stored in the DAC metadata in **msdb**.</span></span> <span data-ttu-id="e3b68-206">Например, если после развертывания исходного приложения уровня данных с помощью инструкций CREATE, ALTER или DROP выполнялось добавление, изменение или удаление объектов из базы данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-206">For example, if CREATE, ALTER, or DROP statements have been used to add, change, or remove objects from the database after the DAC was originally deployed.</span></span> <span data-ttu-id="e3b68-207">Сначала на этой странице отображается индикатор выполнения, а затем результаты анализа.</span><span class="sxs-lookup"><span data-stu-id="e3b68-207">The page first displays a progress bar, and then reports the results of the analysis.</span></span>  
  
 <span data-ttu-id="e3b68-208">**Выполняется обнаружение изменений, это может занять несколько минут** — отображает индикатор выполнения во время проверки мастером различий между текущей схемой базы данных и объектами из определения приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-208">**Detecting change, this may take a few minutes** - Displays a progress bar as the wizard checks for differences between the current schema of the database and the objects in the DAC definition.</span></span>  
  
 <span data-ttu-id="e3b68-209">**Результаты обнаружения изменений:** — указывается, что анализ завершен, а его результаты приводятся ниже.</span><span class="sxs-lookup"><span data-stu-id="e3b68-209">**Change detection results:** - Indicates that the analysis has completed and the results are reported below.</span></span>  
  
 <span data-ttu-id="e3b68-210">**База данных "ИмяБазыДанных" не изменилась** — мастер не обнаружил отличий объектов, определенных в базе данных, и их копий из определения приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-210">**The database DatabaseName has not changed** - The wizard detected no differences in the objects defined in the database and their counterparts in the DAC definition.</span></span>  
  
 <span data-ttu-id="e3b68-211">**База данных "ИмяБазыДанных" изменилась** — мастер обнаружил отличия между объектами из базы данных и их копиями из определения приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-211">**The database DatabaseName has changed** - The wizard detected changes between the objects in the database and their counterparts in the DAC definition.</span></span>  
  
 <span data-ttu-id="e3b68-212">**Продолжить, несмотря на возможную потерю изменений** — указывает, что пользователь понимает, что некоторые объекты или данные из текущей базы данных не будут перенесены в новую базу данных, но все равно хочет продолжить обновление.</span><span class="sxs-lookup"><span data-stu-id="e3b68-212">**Proceed despite possible loss of changes** - Specifies that you understand some of the objects or data in the current database will not be present in the new database, and that you are willing to proceed with the upgrade.</span></span> <span data-ttu-id="e3b68-213">Эту кнопку следует нажимать только после анализа отчета об изменениях, понимая, какие действия необходимо выполнить, чтобы вручную передать объекты или данные, которые потребуются в новой базе данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-213">You should select this button only if you have analyzed the change report and understand the steps you must perform to manually transfer any objects or data required in the new database.</span></span> <span data-ttu-id="e3b68-214">Если такой уверенности нет, нажмите кнопку **Сохранить отчет** , чтобы сохранить отчет об изменениях, а затем нажмите кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="e3b68-214">If you are not sure, click the **Save Report** button to save the change report, then click **Cancel**.</span></span> <span data-ttu-id="e3b68-215">Проанализируйте отчет, запланируйте перенос необходимых объектов и данных после завершения обновления, а затем повторно запустите мастер.</span><span class="sxs-lookup"><span data-stu-id="e3b68-215">Analyze the report, plan how to transfer any required objects and data after the upgrade completes, then restart the wizard.</span></span>  
  
 <span data-ttu-id="e3b68-216">**Сохранить отчет** — нажмите эту кнопку, чтобы сохранить отчет об изменениях, обнаруженных мастером, между объектами из базы данных и их копиями из определения приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-216">**Save Report** - Click the button to save a report of the changes the wizard detected between the objects in the database and their counterparts in the DAC definition.</span></span> <span data-ttu-id="e3b68-217">Отчет можно будет проанализировать, чтобы определить, потребуются ли дополнительные действия после завершения обновления для внесения некоторых или всех объектов, приведенных в отчете, в новую базу данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-217">You can then review the report to determine if you need to take actions after the upgrade completes to incorporate some or all of the objects listed in the report into the new database.</span></span>  
  
 <span data-ttu-id="e3b68-218">\*\* \< Назад\*\* — возврат на страницу **Выбор пакета DAC** .</span><span class="sxs-lookup"><span data-stu-id="e3b68-218">**\< Previous** - Returns to the **Select DAC Package** page.</span></span>  
  
 <span data-ttu-id="e3b68-219">**Далее >**  — переход на страницу **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="e3b68-219">**Next >** - Proceeds to the **Options** page.</span></span>  
  
 <span data-ttu-id="e3b68-220">**Отмена** — мастер прекращает работу без развертывания DAC.</span><span class="sxs-lookup"><span data-stu-id="e3b68-220">**Cancel** - Terminates the wizard without deploying the DAC.</span></span>  
  
## <a name="options-page"></a><span data-ttu-id="e3b68-221">Страницы параметров</span><span class="sxs-lookup"><span data-stu-id="e3b68-221">Options Page</span></span>  
 <span data-ttu-id="e3b68-222">Используйте эту страницу, чтобы выбрать для обновления параметр отката при сбое.</span><span class="sxs-lookup"><span data-stu-id="e3b68-222">Use this page to select the rollback on failure option for the upgrade.</span></span>  
  
 <span data-ttu-id="e3b68-223">**Откатить при сбое** — выберите этот параметр, чтобы заключить обновление в транзакцию, которую в случае сбоя мастер может попытаться откатить.</span><span class="sxs-lookup"><span data-stu-id="e3b68-223">**Rollback on failure** - Select this option to enclose the upgrade in a transaction which the wizard can attempt to roll back if errors occur.</span></span> <span data-ttu-id="e3b68-224">Дополнительные сведения об этом параметре см. в разделе [Выбор параметров обновления DAC](#ChoseDACUpgOptions).</span><span class="sxs-lookup"><span data-stu-id="e3b68-224">For more information about the option, see [Choosing DAC Upgrade Options](#ChoseDACUpgOptions).</span></span>  
  
 <span data-ttu-id="e3b68-225">**Восстановить значения по умолчанию** — параметр возвращается к значению по умолчанию (false).</span><span class="sxs-lookup"><span data-stu-id="e3b68-225">**Restore Defaults** - Returns the option to its default setting of false.</span></span>  
  
 <span data-ttu-id="e3b68-226">\*\* \< Назад\*\* — возврат на страницу **Обнаружение изменений** .</span><span class="sxs-lookup"><span data-stu-id="e3b68-226">**\< Previous** - Returns to the **Detect Change** page.</span></span>  
  
 <span data-ttu-id="e3b68-227">**Далее >**  — переход на страницу **Проверить план обновления**.</span><span class="sxs-lookup"><span data-stu-id="e3b68-227">**Next >** - Proceeds to the **Review the Upgrade Plan** page.</span></span>  
  
 <span data-ttu-id="e3b68-228">**Отмена** — мастер прекращает работу без развертывания DAC.</span><span class="sxs-lookup"><span data-stu-id="e3b68-228">**Cancel** - Terminates the wizard without deploying the DAC.</span></span>  
  
##  <a name="review-the-upgrade-plan-page"></a><a name="ReviewUpgPlan"></a> <span data-ttu-id="e3b68-229">Просмотр страницы «План обновления»</span><span class="sxs-lookup"><span data-stu-id="e3b68-229">Review the Upgrade Plan Page</span></span>  
 <span data-ttu-id="e3b68-230">На этой странице можно увидеть, какие действия будут выполнены в процессе обновления.</span><span class="sxs-lookup"><span data-stu-id="e3b68-230">Use this page to do review the actions that will be taken by the upgrade process.</span></span> <span data-ttu-id="e3b68-231">Продолжайте только в случае, если уверены, что обновление не вызовет проблем.</span><span class="sxs-lookup"><span data-stu-id="e3b68-231">Only proceed when you are confident the upgrade will not create problems.</span></span>  
  
 <span data-ttu-id="e3b68-232">**Следующие действия будут использоваться для обновления приложения уровня данных.**</span><span class="sxs-lookup"><span data-stu-id="e3b68-232">**The following actions will be used to upgrade the DAC.**</span></span> <span data-ttu-id="e3b68-233">Просмотрите отображенные сведения для проверки правильности произведенных действий.</span><span class="sxs-lookup"><span data-stu-id="e3b68-233">- Review the information displayed to ensure the actions taken will be correct.</span></span> <span data-ttu-id="e3b68-234">В столбце **Действие** показаны все действия, которые будут выполняться для обновления (например, инструкции Transact-SQL).</span><span class="sxs-lookup"><span data-stu-id="e3b68-234">The **Action** column displays the actions, such as Transact-SQL statements, that will be run to perform the upgrade.</span></span> <span data-ttu-id="e3b68-235">Столбец **Потеря данных** будет содержать предупреждение, если соответствующее действие может вызвать удаление данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-235">The **Data Loss** column will contain a warning if the associated action could delete data.</span></span>  
  
 <span data-ttu-id="e3b68-236">**Обновить** — обновляет список действий.</span><span class="sxs-lookup"><span data-stu-id="e3b68-236">**Refresh** - refreshes the action list.</span></span>  
  
 <span data-ttu-id="e3b68-237">**Сохранить отчет действия** — сохраняет содержимое окна действия в виде HTML-файла.</span><span class="sxs-lookup"><span data-stu-id="e3b68-237">**Save Action Report** - saves the contents of the action window to an HTML file.</span></span>  
  
 <span data-ttu-id="e3b68-238">**Продолжить, несмотря на возможную потерю изменений** — указывает, что пользователь понимает, что некоторые объекты или данные из текущей базы данных не будут перенесены в новую базу данных, но все равно хочет продолжить обновление.</span><span class="sxs-lookup"><span data-stu-id="e3b68-238">**Proceed despite possible loss of changes** - Specifies that you understand some of the objects or data in the current database will not be present in the new database, and that you are willing to proceed with the upgrade.</span></span> <span data-ttu-id="e3b68-239">Эту кнопку следует нажимать только после анализа отчета об изменениях, понимая, какие действия необходимо выполнить, чтобы вручную передать объекты или данные, которые потребуются в новой базе данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-239">You should select this button only if you have analyzed the change report and understand the steps you must perform to manually transfer any objects or data required in the new database.</span></span> <span data-ttu-id="e3b68-240">Если вы не уверены, нажмите кнопку **Сохранить отчет о действии** , чтобы сохранить отчет о выполнении, а затем кнопку **Сохранить скрипты** , чтобы сохранить скрипт Transact-SQL. После этого нажмите кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="e3b68-240">If you are not sure, click the **Save Action Report** button to save the change report and the **Save Scripts** button to save the Transact-SQL script, then click **Cancel**.</span></span> <span data-ttu-id="e3b68-241">Проанализируйте отчет и скрипт, запланируйте перенос необходимых объектов и данных после завершения обновления, а затем повторно запустите мастер.</span><span class="sxs-lookup"><span data-stu-id="e3b68-241">Analyze the report and script, and then plan how to transfer any required objects and data after the upgrade completes, then restart the wizard.</span></span>  
  
 <span data-ttu-id="e3b68-242">**Сохранить скрипты** — сохраняет инструкции Transact-SQL, которые будут выполнены для обновления, в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="e3b68-242">**Save Scripts** - saves the Transact-SQL statements that will be used to perform the upgrade to a text file.</span></span>  
  
 <span data-ttu-id="e3b68-243">**Восстановить значения по умолчанию** — параметр возвращается к значению по умолчанию (false).</span><span class="sxs-lookup"><span data-stu-id="e3b68-243">**Restore Defaults** - Returns the option to its default setting of false.</span></span>  
  
 <span data-ttu-id="e3b68-244">\*\* \< Назад\*\* — возврат на страницу **Обнаружение изменений** .</span><span class="sxs-lookup"><span data-stu-id="e3b68-244">**\< Previous** - Returns to the **Detect Change** page.</span></span>  
  
 <span data-ttu-id="e3b68-245">**Далее >** — переход к странице **Сводка**.</span><span class="sxs-lookup"><span data-stu-id="e3b68-245">**Next >** - Proceeds to the **Summary** page.</span></span>  
  
 <span data-ttu-id="e3b68-246">**Отмена** — мастер прекращает работу без развертывания DAC.</span><span class="sxs-lookup"><span data-stu-id="e3b68-246">**Cancel** - Terminates the wizard without deploying the DAC.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="e3b68-247">Страница «Сводка»</span><span class="sxs-lookup"><span data-stu-id="e3b68-247">Summary Page</span></span>  
 <span data-ttu-id="e3b68-248">Используйте эту страницу для окончательного анализа действий, которые мастер выполнит для обновления приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-248">Use this page to do a final review of the actions the wizard will take when upgrading the DAC.</span></span>  
  
 <span data-ttu-id="e3b68-249">**Следующие параметры будут использоваться для обновления приложения уровня данных.**</span><span class="sxs-lookup"><span data-stu-id="e3b68-249">**The following settings will be used to upgrade your DAC.**</span></span> <span data-ttu-id="e3b68-250">Просмотрите отображенные сведения для проверки правильности произведенных действий.</span><span class="sxs-lookup"><span data-stu-id="e3b68-250">- Review the information displayed to ensure the actions taken will be correct.</span></span> <span data-ttu-id="e3b68-251">В этом окне отображается выбранное для обновления приложение уровня данных и пакет приложения уровня данных, содержащий новую версию приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-251">The window displays the DAC you selected to be upgraded, and the DAC package containing the new version of the DAC.</span></span> <span data-ttu-id="e3b68-252">В нем также отображается, совпадает ли текущая версия базы данных с текущим определением приложения уровня данных или она изменилась.</span><span class="sxs-lookup"><span data-stu-id="e3b68-252">The window also displays whether the current version of the database is the same as the current DAC definition, or if the database has changed.</span></span>  
  
 <span data-ttu-id="e3b68-253">\*\* \< Назад\*\* — возврат на страницу **Проверка плана обновления** .</span><span class="sxs-lookup"><span data-stu-id="e3b68-253">**\< Previous** - Returns you to the **Review the Upgrade Plan** page.</span></span>  
  
 <span data-ttu-id="e3b68-254">**Далее >**  — развертывание приложения уровня данных и отображение результатов на странице **Обновить приложение уровня данных**.</span><span class="sxs-lookup"><span data-stu-id="e3b68-254">**Next >** - Deploys the DAC and displays the results in the **Upgrade DAC** page.</span></span>  
  
 <span data-ttu-id="e3b68-255">**Отмена** — мастер прекращает работу без развертывания DAC.</span><span class="sxs-lookup"><span data-stu-id="e3b68-255">**Cancel** - Terminates the wizard without deploying the DAC.</span></span>  
  
##  <a name="upgrade-dac-page"></a><a name="Upgrade"></a> <span data-ttu-id="e3b68-256">Страница «Обновление DAC»</span><span class="sxs-lookup"><span data-stu-id="e3b68-256">Upgrade DAC Page</span></span>  
 <span data-ttu-id="e3b68-257">Эта страница сообщает об успешном или неуспешном завершении операции обновления.</span><span class="sxs-lookup"><span data-stu-id="e3b68-257">This page reports the success or failure of the upgrade operation.</span></span>  
  
 <span data-ttu-id="e3b68-258">**Обновление приложения уровня данных** — сообщает об успехе или неуспехе каждого действия, предпринятого для обновления приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-258">**Upgrading the DAC** - Reports the success or failure of each action taken to upgrade the DAC.</span></span> <span data-ttu-id="e3b68-259">Просмотрите эти сведения, чтобы выяснить результаты каждого действия.</span><span class="sxs-lookup"><span data-stu-id="e3b68-259">Review the information to determine the success or failure of each action.</span></span> <span data-ttu-id="e3b68-260">Для каждого действия, в котором обнаружена ошибка, предусмотрена ссылка в столбце **Результат** .</span><span class="sxs-lookup"><span data-stu-id="e3b68-260">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="e3b68-261">Выберите эту ссылку, чтобы просмотреть отчет об ошибках, относящихся данному действию.</span><span class="sxs-lookup"><span data-stu-id="e3b68-261">Select the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="e3b68-262">**Сохранить отчет** — сохранение отчета об обновлении в HTML-файле.</span><span class="sxs-lookup"><span data-stu-id="e3b68-262">**Save Report** - Select this button to save the upgrade report to an HTML file.</span></span> <span data-ttu-id="e3b68-263">В этом файле содержится отчет о состоянии каждого из действий, в том числе все выданные сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="e3b68-263">The file reports the status of each action, including all errors generated by any of the actions.</span></span> <span data-ttu-id="e3b68-264">Папка по умолчанию используется SQL Server Management Studio\DAC Packages, вложенная в папки Documents рабочего каталога учетной записи пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="e3b68-264">The default folder is a SQL Server Management Studio\DAC Packages folder in the Documents folder of your Windows account.</span></span>  
  
 <span data-ttu-id="e3b68-265">**Готово** — завершает работу мастера.</span><span class="sxs-lookup"><span data-stu-id="e3b68-265">**Finish** - Terminates the wizard.</span></span>  
  
##  <a name="using-powershell"></a><a name="UpgradeDACPowerShell"></a> <span data-ttu-id="e3b68-266">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3b68-266">Using PowerShell</span></span>  
 <span data-ttu-id="e3b68-267">**Обновление приложения уровня данных с помощью метода IncrementalUpgrade() в скрипте PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e3b68-267">**To upgrade a DAC using the IncrementalUpgrade() method in a PowerShell script**</span></span>  
  
1.  <span data-ttu-id="e3b68-268">Создайте объект SMO Server и задайте его экземпляру с приложением уровня данных, которое должно быть обновлено.</span><span class="sxs-lookup"><span data-stu-id="e3b68-268">Create a SMO Server object and set it to the instance that contains the DAC to be upgraded.</span></span>  
  
2.  <span data-ttu-id="e3b68-269">Откройте объект `ServerConnection` и подключитесь к тому же экземпляру.</span><span class="sxs-lookup"><span data-stu-id="e3b68-269">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="e3b68-270">Используйте `System.IO.File` для загрузки файла пакета приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-270">Use `System.IO.File` to load the DAC package file.</span></span>  
  
4.  <span data-ttu-id="e3b68-271">Используйте `add_DacActionStarted` и `add_DacActionFinished` для подписки на обновление событий приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-271">Use `add_DacActionStarted` and `add_DacActionFinished` to subscribe to the DAC upgrade events.</span></span>  
  
5.  <span data-ttu-id="e3b68-272">Задайте `DacUpgradeOptions`.</span><span class="sxs-lookup"><span data-stu-id="e3b68-272">Set the `DacUpgradeOptions`.</span></span>  
  
6.  <span data-ttu-id="e3b68-273">Для обновления приложения уровня данных используйте метод `IncrementalUpgrade`.</span><span class="sxs-lookup"><span data-stu-id="e3b68-273">Use the `IncrementalUpgrade` method to upgrade the DAC.</span></span>  
  
7.  <span data-ttu-id="e3b68-274">Закройте файловый поток, используемый для чтения файла пакета приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="e3b68-274">Close the file stream used to read the DAC package file.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="e3b68-275">Пример (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="e3b68-275">Example (PowerShell)</span></span>  
 <span data-ttu-id="e3b68-276">В следующем примере приложение уровня данных MyApplication обновляется на экземпляре [!INCLUDE[ssDE](../../includes/ssde-md.md)]по умолчанию с использованием новой версии в пакете MyApplication.dacpac.</span><span class="sxs-lookup"><span data-stu-id="e3b68-276">The following example upgrades a DAC named MyApplication on a default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], using a new DAC version in a MyApplicationVNext.dacpac package.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Load the DAC package file.  
$dacpacPath = "C:\MyDACs\MyApplicationVNext.dacpac"  
$fileStream = [System.IO.File]::Open($dacpacPath,[System.IO.FileMode]::OpenOrCreate)  
$dacType = [Microsoft.SqlServer.Management.Dac.DacType]::Load($fileStream)  
  
## Subscribe to the DAC upgrade events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Upgrade the DAC and close the package.  
$dacName  = "MyApplication"  
  
## Set the upgrade options.  
$upgradeProperties = New-Object Microsoft.SqlServer.Management.Dac.DacUpgradeOptions  
$upgradeProperties.blockonchanges = $true  
$upgradeProperties.ignoredataloss = $false  
$upgradeProperties.rollbackonfailure = $true  
$ upgradeProperties.skippolicyvalidation = $false  
  
## Upgrade the DAC  
$dacstore.IncrementalUpgrade($dacName, $dacType, $upgradeProperties)  
## Close the package file.  
$fileStream.Close()  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3b68-277">См. также:</span><span class="sxs-lookup"><span data-stu-id="e3b68-277">See Also</span></span>  
 <span data-ttu-id="e3b68-278">[Приложения уровня данных](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="e3b68-278">[Data-tier Applications](data-tier-applications.md) </span></span>  
 [<span data-ttu-id="e3b68-279">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3b68-279">SQL Server PowerShell</span></span>](../../powershell/sql-server-powershell.md)  
