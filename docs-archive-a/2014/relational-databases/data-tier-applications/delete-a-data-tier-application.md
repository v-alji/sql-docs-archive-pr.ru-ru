---
title: Удаление приложения уровня данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.deletedacwizard.introduction.f1
- sql12.swb.deletedacwizard.deletedac.f1
- sql12.swb.deletedacwizard.summary.f1
- sql12.swb.deletedacwizard.choosemethod.f1
helpviewer_keywords:
- How to [DAC], delete
- data-tier application [SQL Server], delete
- wizard [DAC], delete
- delete DAC
ms.assetid: 16fe1c18-4486-424d-81d6-d276ed97482f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 602256c287a8c7bcf9d3fa5597b2fec2085c626c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736389"
---
# <a name="delete-a-data-tier-application"></a><span data-ttu-id="c540a-102">Удаление приложения уровня данных</span><span class="sxs-lookup"><span data-stu-id="c540a-102">Delete a Data-tier Application</span></span>
  <span data-ttu-id="c540a-103">Для удаления приложения уровня данных (DAC) используйте мастер удаления приложения уровня данных или скрипт Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c540a-103">You can delete a data-tier application by using either the Delete Data-tier Application wizard or a Windows PowerShell script.</span></span> <span data-ttu-id="c540a-104">Можно указать, будет ли связанная база данных сохранена, отсоединена или уничтожена.</span><span class="sxs-lookup"><span data-stu-id="c540a-104">You can specify whether the associated database is retained, detached, or dropped.</span></span>  
  
-   <span data-ttu-id="c540a-105">**Перед началом работы**  [ограничения](#LimitationsRestrictions), [разрешения](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="c540a-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="c540a-106">**Обновление приложения уровня данных с использованием:**  [Мастер регистрации приложения уровня данных](#UsingDeleteDACWizard), [PowerShell](#DeleteDACPowerShell)</span><span class="sxs-lookup"><span data-stu-id="c540a-106">**To upgrade a DAC, using:**  [The Register Data-tier Application Wizard](#UsingDeleteDACWizard), [PowerShell](#DeleteDACPowerShell)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="c540a-107">Перед началом</span><span class="sxs-lookup"><span data-stu-id="c540a-107">Before You Begin</span></span>  
 <span data-ttu-id="c540a-108">При удалении экземпляра приложения уровня данных (DAC) можно выбрать один из трех параметров, которые определяют действие над базой данных, связанной с этим приложением уровня данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-108">When you delete a data-tier application (DAC) instance, you choose one of three options specifying what is to be done with the database associated with the data-tier application.</span></span> <span data-ttu-id="c540a-109">При использовании любого из трех параметров удаляются метаданные определения DAC.</span><span class="sxs-lookup"><span data-stu-id="c540a-109">All three options delete the DAC definition metadata.</span></span> <span data-ttu-id="c540a-110">Различие между ними состоит в действиях, которые они выполняют с базой данных, связанной с приложением уровня данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-110">The options differ in what they do with the database associated with the data-tier application.</span></span> <span data-ttu-id="c540a-111">Мастер не удаляет ни один из объектов уровня экземпляра, связанных с DAC или базой данных, таких как имена входа.</span><span class="sxs-lookup"><span data-stu-id="c540a-111">The wizard does not delete any of the instance-level objects associated with the DAC or database, such as logins.</span></span>  
  
|<span data-ttu-id="c540a-112">Параметр</span><span class="sxs-lookup"><span data-stu-id="c540a-112">Option</span></span>|<span data-ttu-id="c540a-113">Операции базы данных</span><span class="sxs-lookup"><span data-stu-id="c540a-113">Database actions</span></span>|  
|------------|----------------------|  
|<span data-ttu-id="c540a-114">Регистрация удаления</span><span class="sxs-lookup"><span data-stu-id="c540a-114">Delete registration</span></span>|<span data-ttu-id="c540a-115">Связанная база данных остается неизменной.</span><span class="sxs-lookup"><span data-stu-id="c540a-115">The associated database remains intact.</span></span>|  
|<span data-ttu-id="c540a-116">Отсоединение базы данных</span><span class="sxs-lookup"><span data-stu-id="c540a-116">Detach database</span></span>|<span data-ttu-id="c540a-117">Выполняется отсоединение связанной базы данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-117">The associated database is detached.</span></span> <span data-ttu-id="c540a-118">Экземпляр компонента Database Engine не может ссылаться на эту базу данных, но данные и файлы журналов сохраняются целыми.</span><span class="sxs-lookup"><span data-stu-id="c540a-118">The instance of the Database Engine cannot reference the database, but the data and log files are intact.</span></span>|  
|<span data-ttu-id="c540a-119">Удаление базы данных</span><span class="sxs-lookup"><span data-stu-id="c540a-119">Delete database</span></span>|<span data-ttu-id="c540a-120">Связанная база данных уничтожается.</span><span class="sxs-lookup"><span data-stu-id="c540a-120">The associated database is dropped.</span></span> <span data-ttu-id="c540a-121">Происходит удаление данных и файлов журналов.</span><span class="sxs-lookup"><span data-stu-id="c540a-121">The data and log files are deleted.</span></span>|  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="c540a-122">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c540a-122">Limitations and Restrictions</span></span>  
 <span data-ttu-id="c540a-123">Автоматический механизм восстановления метаданных определения приложения уровня данных или базы данных после удаления приложения уровня данных отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c540a-123">There is no automatic mechanism to restore the DAC definition metadata or the database after you delete a DAC.</span></span> <span data-ttu-id="c540a-124">Способ, как можно будет вручную перестроить экземпляр приложения уровня данных, зависит от параметра удаления.</span><span class="sxs-lookup"><span data-stu-id="c540a-124">How you can manually rebuild the DAC instance depends on the delete option.</span></span>  
  
|<span data-ttu-id="c540a-125">Параметр</span><span class="sxs-lookup"><span data-stu-id="c540a-125">Option</span></span>|<span data-ttu-id="c540a-126">Повторное создание экземпляра приложения уровня данных</span><span class="sxs-lookup"><span data-stu-id="c540a-126">How to Rebuild the DAC Instance</span></span>|  
|------------|-------------------------------------|  
|<span data-ttu-id="c540a-127">Регистрация удаления</span><span class="sxs-lookup"><span data-stu-id="c540a-127">Delete registration</span></span>|<span data-ttu-id="c540a-128">Зарегистрируйте приложение уровня данных из оставшейся базы данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-128">Register a DAC from the database left in place.</span></span>|  
|<span data-ttu-id="c540a-129">Отсоединение базы данных</span><span class="sxs-lookup"><span data-stu-id="c540a-129">Detach database</span></span>|<span data-ttu-id="c540a-130">Повторно присоедините базу данных с помощью команды **sp_attachdb** или среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], а затем зарегистрируйте новый экземпляр приложения уровня данных из базы данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-130">Re-attach the database by using **sp_attachdb** or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then register a new DAC instance from the database.</span></span>|  
|<span data-ttu-id="c540a-131">Удаление базы данных</span><span class="sxs-lookup"><span data-stu-id="c540a-131">Delete database</span></span>|<span data-ttu-id="c540a-132">Восстановите базу данных из полной резервной копии, созданной до удаления приложения уровня данных, а затем зарегистрируйте новый экземпляр приложения уровня данных из базы данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-132">Restore the database from a full backup made before the DAC was deleted, and then register a new DAC instance from the database.</span></span>|  
  
> [!WARNING]  
>  <span data-ttu-id="c540a-133">При повторном создании экземпляра приложения уровня данных путем его регистрации из восстановленной или повторно присоединенной базы данных некоторые части исходного приложения уровня данных, например политика выбора сервера, не создаются повторно.</span><span class="sxs-lookup"><span data-stu-id="c540a-133">Rebuilding a DAC instance by registering a DAC from a restored or re-attached database will not recreate some parts of the original DAC, such as the server selection policy.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c540a-134">Permissions</span><span class="sxs-lookup"><span data-stu-id="c540a-134">Permissions</span></span>  
 <span data-ttu-id="c540a-135">Приложение уровня данных (DAC) может быть удалено только членами предопределенных ролей сервера **sysadmin** и **serveradmin** или владельцем базы данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-135">A DAC can only be deleted by members of the **sysadmin** or **serveradmin** fixed server roles, or by the database owner.</span></span> <span data-ttu-id="c540a-136">Этот мастер также может быть запущен от имени учетной записи системного администратора [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с именем **sa** .</span><span class="sxs-lookup"><span data-stu-id="c540a-136">The built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator account named **sa** can also launch the wizard.</span></span>  
  
##  <a name="using-the-delete-data-tier-application-wizard"></a><a name="UsingDeleteDACWizard"></a> <span data-ttu-id="c540a-137">Использование мастера удаления приложения уровня данных</span><span class="sxs-lookup"><span data-stu-id="c540a-137">Using the Delete Data-tier Application Wizard</span></span>  
 <span data-ttu-id="c540a-138">**Удаление приложения уровня данных с помощью мастера**</span><span class="sxs-lookup"><span data-stu-id="c540a-138">**To Delete a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="c540a-139">В **Обозревателе объектов**разверните узел экземпляра, содержащего приложение уровня данных, которое требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="c540a-139">In **Object Explorer**, expand the node for the instance containing the DAC to be deleted.</span></span>  
  
2.  <span data-ttu-id="c540a-140">Разверните узел **Управление** .</span><span class="sxs-lookup"><span data-stu-id="c540a-140">Expand the **Management** node.</span></span>  
  
3.  <span data-ttu-id="c540a-141">Разверните узел **Приложения уровня данных** .</span><span class="sxs-lookup"><span data-stu-id="c540a-141">Expand the **Data-tier Applications** node.</span></span>  
  
4.  <span data-ttu-id="c540a-142">Щелкните правой кнопкой мыши приложение уровня данных, которое требуется удалить, и выберите пункт **Удалить приложение уровня данных...** .</span><span class="sxs-lookup"><span data-stu-id="c540a-142">Right-click the DAC to be deleted, and then select **Delete Data-tier Application...**</span></span>  
  
5.  <span data-ttu-id="c540a-143">Выполните шаги в диалоговых окнах мастера.</span><span class="sxs-lookup"><span data-stu-id="c540a-143">Complete the wizard dialogs:</span></span>  
  
    1.  [<span data-ttu-id="c540a-144">Введение</span><span class="sxs-lookup"><span data-stu-id="c540a-144">Introduction</span></span>](#Introduction)  
  
    2.  [<span data-ttu-id="c540a-145">Выбор метода</span><span class="sxs-lookup"><span data-stu-id="c540a-145">Choose Method</span></span>](#Choose_method)  
  
    3.  [<span data-ttu-id="c540a-146">Сводка</span><span class="sxs-lookup"><span data-stu-id="c540a-146">Summary</span></span>](#Summary)  
  
    4.  [<span data-ttu-id="c540a-147">Удалить приложение уровня данных</span><span class="sxs-lookup"><span data-stu-id="c540a-147">Delete Data-tier Application</span></span>](#Delete_datatier_application)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="c540a-148">Вводная страница</span><span class="sxs-lookup"><span data-stu-id="c540a-148">Introduction Page</span></span>  
 <span data-ttu-id="c540a-149">На этой странице описаны шаги удаления приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-149">This page describes the steps for deleting a data-tier application.</span></span>  
  
 <span data-ttu-id="c540a-150">**Больше не показывать эту страницу.**</span><span class="sxs-lookup"><span data-stu-id="c540a-150">**Do not show this page again.**</span></span> <span data-ttu-id="c540a-151">— щелкните этот флажок, чтобы предотвратить отображение этой страницы в будущем.</span><span class="sxs-lookup"><span data-stu-id="c540a-151">- Click the check box to stop the page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="c540a-152">**Далее >** — переход к странице **Выбор метода**.</span><span class="sxs-lookup"><span data-stu-id="c540a-152">**Next >** - Proceeds to the **Choose Method** page.</span></span>  
  
 <span data-ttu-id="c540a-153">**Отмена** — отмена действий мастера без удаления приложения уровня данных или базы данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-153">**Cancel** - Ends the wizard without deleting a data-tier application or database.</span></span>  
  
##  <a name="choose-method-page"></a><a name="Choose_method"></a> <span data-ttu-id="c540a-154">Страница «Выбор метода»</span><span class="sxs-lookup"><span data-stu-id="c540a-154">Choose Method Page</span></span>  
 <span data-ttu-id="c540a-155">Используйте данную страницу, чтобы указать параметр для обработки связанной с удаляемым приложением уровня данных базы данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-155">Use this page to specify the option for handling the database associated with the DAC to be deleted.</span></span>  
  
 <span data-ttu-id="c540a-156">**Регистрация удаления** удаляет метаданные, определяющие приложение уровня данных, но оставляет неизменной связанную базу данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-156">**Delete registration** - Removes the metadata defining the data-tier application, but leaves the associated database intact.</span></span>  
  
 <span data-ttu-id="c540a-157">**Отсоединение базы данных** — удаляет метаданные, определяющие приложение уровня данных, и отсоединяет связанную базу данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-157">**Detach database** - Removes the metadata defining the data-tier application and detaches the associated database.</span></span>  
  
 <span data-ttu-id="c540a-158">На эту базу данных больше нельзя будет ссылаться из экземпляра компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)], но данные и файлы журнала останутся неизменными.</span><span class="sxs-lookup"><span data-stu-id="c540a-158">The database can no longer be referenced by that instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], but the data and log files remain intact.</span></span>  
  
 <span data-ttu-id="c540a-159">**Удаление базы данных** — производится удаление метаданных, определяющих DAC, и уничтожение связанной базы данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-159">**Delete database** - Removes the metadata defining the DAC and drops the associated database.</span></span>  
  
 <span data-ttu-id="c540a-160">Удаление данных и файлов журналов, относящихся к базе данных, осуществляется на постоянной основе.</span><span class="sxs-lookup"><span data-stu-id="c540a-160">The data and log files for the database are permanently deleted.</span></span>  
  
 <span data-ttu-id="c540a-161">\*\* \< Назад\*\* — возврат на страницу **Введение** .</span><span class="sxs-lookup"><span data-stu-id="c540a-161">**\< Previous** - Returns to the **Introduction** page.</span></span>  
  
 <span data-ttu-id="c540a-162">**Далее >** — переход к странице **Сводка**.</span><span class="sxs-lookup"><span data-stu-id="c540a-162">**Next >** - Proceeds to the **Summary** page.</span></span>  
  
 <span data-ttu-id="c540a-163">**Отмена** — завершение работы мастера без удаления DAC или базы данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-163">**Cancel** - Ends the wizard without deleting the DAC or database.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="c540a-164">Страница «Сводка»</span><span class="sxs-lookup"><span data-stu-id="c540a-164">Summary Page</span></span>  
 <span data-ttu-id="c540a-165">На этой странице можно просмотреть действия, которые будут выполнены мастером при удалении экземпляра приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-165">Use this page to review the actions the wizard will take when deleting the DAC instance.</span></span>  
  
 <span data-ttu-id="c540a-166">**Просмотр сводки по своему выбору** — предоставляет возможность ознакомиться со сведениями о DAC, базе данных и методе удаления, отображенными в этом окне.</span><span class="sxs-lookup"><span data-stu-id="c540a-166">**Review your selection summary** - Review the DAC, database, and deletion method displayed in the box.</span></span> <span data-ttu-id="c540a-167">Если эти сведения правильны, выберите **Далее** или **Готово** , чтобы удалить DAC.</span><span class="sxs-lookup"><span data-stu-id="c540a-167">If the information is correct, select either **Next** or **Finish** to delete the DAC.</span></span> <span data-ttu-id="c540a-168">Если сведения о DAC и базе данных неверны, выберите **Отмена** и правильно укажите DAC.</span><span class="sxs-lookup"><span data-stu-id="c540a-168">If the DAC and database information is not correct, select **Cancel** and select the correct DAC.</span></span> <span data-ttu-id="c540a-169">Если неверным является метод удаления, нажмите кнопку **Назад** , чтобы вернуться к странице **Выбор метода** , и укажите другой метод.</span><span class="sxs-lookup"><span data-stu-id="c540a-169">If the deletion method is not correct, select **Previous** to return to the **Choose Method** page and select a different method.</span></span>  
  
 <span data-ttu-id="c540a-170">\*\* \< Назад\*\* — возврат на страницу **Выбор метода** для выбора другого метода удаления.</span><span class="sxs-lookup"><span data-stu-id="c540a-170">**\< Previous** - Returns to the **Choose Method** page to choose a different delete method.</span></span>  
  
 <span data-ttu-id="c540a-171">**Далее >** — удаление экземпляра приложения уровня данных методом, выбранным на предыдущей странице, и переход к странице **Удаление приложения уровня данных**.</span><span class="sxs-lookup"><span data-stu-id="c540a-171">**Next >** - Deletes the DAC instance using the method you chose on the previous page, and proceeds to the **Delete Data-tier Application** page.</span></span>  
  
 <span data-ttu-id="c540a-172">**Отмена** — завершение работы мастера без удаления экземпляра приложения уровня данных или базы данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-172">**Cancel** - Ends the wizard without deleting the DAC instance.</span></span>  
  
##  <a name="delete-data-tier-application-page"></a><a name="Delete_datatier_application"></a><span data-ttu-id="c540a-173">Страница "Удаление приложения уровня данных"</span><span class="sxs-lookup"><span data-stu-id="c540a-173">Delete Data-tier Application Page</span></span>  
 <span data-ttu-id="c540a-174">Эта страница сообщает об успешном или неуспешном завершении операции удаления.</span><span class="sxs-lookup"><span data-stu-id="c540a-174">This page reports the success or failure of the delete operation.</span></span>  
  
 <span data-ttu-id="c540a-175">**Удаление приложения уровня данных** — сообщает об успехе или неуспехе каждого действия, предпринятого для удаления экземпляра приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-175">**Deleting the DAC** - Reports the success or failure of each action taken to delete the DAC instance.</span></span> <span data-ttu-id="c540a-176">Просмотрите эти сведения, чтобы выяснить результаты каждого действия.</span><span class="sxs-lookup"><span data-stu-id="c540a-176">Review the information to determine the success or failure of each action.</span></span> <span data-ttu-id="c540a-177">Для каждого действия, в котором обнаружена ошибка, предусмотрена ссылка в столбце **Результат** .</span><span class="sxs-lookup"><span data-stu-id="c540a-177">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="c540a-178">Выберите эту ссылку, чтобы просмотреть отчет об ошибках, относящихся данному действию.</span><span class="sxs-lookup"><span data-stu-id="c540a-178">Select the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="c540a-179">**Сохранить отчет** — сохранить отчет об удалении в HTML-файле.</span><span class="sxs-lookup"><span data-stu-id="c540a-179">**Save Report** - Select this button to save the deletion report to an HTML file.</span></span> <span data-ttu-id="c540a-180">В этом файле содержится отчет о состоянии каждого из действий, в том числе все выданные сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="c540a-180">The file reports the status of each action, including all errors generated by any of the actions.</span></span> <span data-ttu-id="c540a-181">По умолчанию используется папка «SQL Server Management Studio\DAC Packages», вложенная в папку Documents рабочего каталога учетной записи пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="c540a-181">The default folder is a SQL Server Management Studio\DAC Packages folder in the Documents folder of your Windows account..</span></span>  
  
 <span data-ttu-id="c540a-182">**Готово** — завершение работы мастера.</span><span class="sxs-lookup"><span data-stu-id="c540a-182">**Finish** - Ends the wizard.</span></span>  
  
##  <a name="delete-a-dac-using-powershell"></a><a name="DeleteDACPowerShell"></a><span data-ttu-id="c540a-183">Удаление приложения уровня данных с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c540a-183">Delete a DAC Using PowerShell</span></span>  
 <span data-ttu-id="c540a-184">**Удаление приложения уровня данных с помощью скрипта PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c540a-184">**To delete a DAC using a PowerShell script**</span></span>  
  
1.  <span data-ttu-id="c540a-185">Создайте объект SMO Server и задайте его экземпляру, содержащему приложение уровня данных, которое требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="c540a-185">Create a SMO Server object and set it to the instance that contains the DAC to be deleted.</span></span>  
  
2.  <span data-ttu-id="c540a-186">Откройте объект `ServerConnection` и подключитесь к тому же экземпляру.</span><span class="sxs-lookup"><span data-stu-id="c540a-186">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="c540a-187">Используйте `add_DacActionStarted` и `add_DacActionFinished` для подписки на обновление событий приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-187">Use `add_DacActionStarted` and `add_DacActionFinished` to subscribe to the DAC upgrade events.</span></span>  
  
4.  <span data-ttu-id="c540a-188">Укажите приложение уровня данных, которое требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="c540a-188">Specify the DAC to delete.</span></span>  
  
5.  <span data-ttu-id="c540a-189">Используйте один из этих трех наборов кода в зависимости от того, какой из вариантов удаления является подходящим:</span><span class="sxs-lookup"><span data-stu-id="c540a-189">Use one of these three sets of code, depending on which delete option is appropriate:</span></span>  
  
    -   <span data-ttu-id="c540a-190">Для удаления регистрации приложения уровня данных без изменения базы данных используйте метод `Unmanage()`.</span><span class="sxs-lookup"><span data-stu-id="c540a-190">To delete the DAC registration but leave the database intact, use the `Unmanage()` method.</span></span>  
  
    -   <span data-ttu-id="c540a-191">Для удаления регистрации приложения уровня данных и отсоединения базы данных используйте метод `Uninstall()` и укажите `DetachDatabase`.</span><span class="sxs-lookup"><span data-stu-id="c540a-191">To delete the DAC registration and detach the database, use the `Uninstall()` method and specify `DetachDatabase`.</span></span>  
  
    -   <span data-ttu-id="c540a-192">Для удаления регистрации приложения уровня данных и сброса базы данных используйте метод `Uninstall()` и укажите `DropDatabase`.</span><span class="sxs-lookup"><span data-stu-id="c540a-192">To delete the DAC registration and drop the database, use the `Uninstall()` method and specify `DropDatabase`.</span></span>  
  
### <a name="example-deleting-the-dac-but-leaving-the-database-powershell"></a><span data-ttu-id="c540a-193">Пример удаления приложения уровня данных без изменения базы данных (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="c540a-193">Example Deleting the DAC but Leaving the Database (PowerShell)</span></span>  
 <span data-ttu-id="c540a-194">В следующем примере рассматривается удаление приложения уровня данных с названием MyApplication при помощи метода `Unmanage()`, который позволяет удалить приложение уровня данных без изменения базы данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-194">The following example deletes a DAC named MyApplication using the `Unmanage()` method to delete the DAC but leave the database intact.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Subscribe to the DAC delete events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Specify the DAC to delete.  
$dacName  = "MyApplication"  
  
## Only delete the DAC definition from msdb, the associated database remains active.  
$dacstore.Unmanage($dacName)  
```  
  
### <a name="example-deleting-the-dac-and-detaching-the-database-powershell"></a><span data-ttu-id="c540a-195">Пример удаления приложения уровня данных с отсоединением базы данных (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="c540a-195">Example Deleting the DAC and Detaching the Database (PowerShell)</span></span>  
 <span data-ttu-id="c540a-196">В следующем примере рассматривается удаление приложения уровня данных с названием MyApplication при помощи метода `Uninstall()`, который позволяет удалить приложение уровня данных с отсоединением базы данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-196">The following example deletes a DAC named MyApplication using the `Uninstall()` method to delete the DAC and detach the database.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = get-item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Subscribe to the DAC delete events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Specify the DAC to delete.  
$dacName  = "MyApplication"  
  
## Delete the DAC definition from msdb and detach the associated database.  
$dacstore.Uninstall($dacName, [Microsoft.SqlServer.Management.Dac.DacUninstallMode]::DetachDatabase)  
```  
  
### <a name="example-deleting-the-dac-and-dropping-the-database-powershell"></a><span data-ttu-id="c540a-197">Пример удаления приложения уровня данных и базы данных (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="c540a-197">Example Deleting the DAC and Dropping the Database (PowerShell)</span></span>  
 <span data-ttu-id="c540a-198">В следующем примере рассматривается удаление приложения уровня данных с названием MyApplication при помощи метода `Uninstall()`, который позволяет удалить приложение уровня данных и базу данных.</span><span class="sxs-lookup"><span data-stu-id="c540a-198">The following example deletes a DAC named MyApplication using the `Uninstall()` method to delete the DAC and drop the database.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Subscribe to the DAC delete events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Specify the DAC to delete.  
$dacName  = "MyApplication"  
  
## Delete the DAC definition from msdb and drop the associated database.  
## $dacstore.Uninstall($dacName, [Microsoft.SqlServer.Management.Dac.DacUninstallMode]::DropDatabase)  
```  
  
## <a name="see-also"></a><span data-ttu-id="c540a-199">См. также:</span><span class="sxs-lookup"><span data-stu-id="c540a-199">See Also</span></span>  
 <span data-ttu-id="c540a-200">[Приложения уровня данных](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="c540a-200">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="c540a-201">[Приложения уровня данных](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="c540a-201">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="c540a-202">[Развертывание приложения уровня данных](deploy-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="c540a-202">[Deploy a Data-tier Application](deploy-a-data-tier-application.md) </span></span>  
 <span data-ttu-id="c540a-203">[Регистрация базы данных в качестве DAC](register-a-database-as-a-dac.md) </span><span class="sxs-lookup"><span data-stu-id="c540a-203">[Register a Database As a DAC](register-a-database-as-a-dac.md) </span></span>  
 <span data-ttu-id="c540a-204">[Резервное копирование и восстановление баз данных SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="c540a-204">[Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="c540a-205">Присоединение и отсоединение базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c540a-205">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../databases/database-detach-and-attach-sql-server.md)  
