---
title: Развертывание запланированных политик в нескольких экземплярах | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: f551b8e8-3668-4ed4-852f-bae826254f4f
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 30faf94c2033be43ac035517e58d5a18c0c68ab8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728985"
---
# <a name="deploy-scheduled-policies-to-multiple-instances"></a><span data-ttu-id="3be22-102">Развертывание запланированных политик на нескольких экзмплярах</span><span class="sxs-lookup"><span data-stu-id="3be22-102">Deploy Scheduled Policies to Multiple Instances</span></span>
  <span data-ttu-id="3be22-103">В окне «Зарегистрированные серверы» можно выполнить развертывание политик на управляемых серверах из центрального узла.</span><span class="sxs-lookup"><span data-stu-id="3be22-103">By using Registered Servers, you can deploy scheduled policies to managed servers from a central location.</span></span> <span data-ttu-id="3be22-104">Можно выполнить развертывание политик либо с группы локальных серверов, либо с сервера централизованного управления.</span><span class="sxs-lookup"><span data-stu-id="3be22-104">You can deploy scheduled policies from either a local server group, or from a Central Management Server.</span></span>  
  
 <span data-ttu-id="3be22-105">В этой задаче будут выполнены следующие действия.</span><span class="sxs-lookup"><span data-stu-id="3be22-105">In this task, you will do the following:</span></span>  
  
1.  <span data-ttu-id="3be22-106">Экспорт политик, запланированный в предыдущей задаче, в папку на диске.</span><span class="sxs-lookup"><span data-stu-id="3be22-106">Export the policies that you scheduled in the previous task to a folder.</span></span>  
  
2.  <span data-ttu-id="3be22-107">Развертывание запланированных политик на целевых экземплярах, управляемых через окно «Зарегистрированные серверы».</span><span class="sxs-lookup"><span data-stu-id="3be22-107">Deploy the scheduled policies to target instances that are managed through Registered Servers.</span></span>  
  
 <span data-ttu-id="3be22-108">Выполнение этих задач будет производиться на компьютере, где производилось выполнение предыдущих задач этого занятия.</span><span class="sxs-lookup"><span data-stu-id="3be22-108">You will perform these tasks on the computer where you completed the previous tasks in this lesson.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3be22-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="3be22-109">Prerequisites</span></span>  
 <span data-ttu-id="3be22-110">Эта задача предусматривает следующие предварительные условия.</span><span class="sxs-lookup"><span data-stu-id="3be22-110">This task has the following prerequisites:</span></span>  
  
-   <span data-ttu-id="3be22-111">Должено быть завершено выполнение предыдущих задач этого занятия.</span><span class="sxs-lookup"><span data-stu-id="3be22-111">You must have completed the previous tasks in this lesson.</span></span>  
  
-   <span data-ttu-id="3be22-112">На экземплярах, где будут развертываться запланированные политики, должен быть запущен [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="3be22-112">The instances where you want to deploy the scheduled policies must be running [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] or a later version.</span></span> <span data-ttu-id="3be22-113">Автоматизация требует локального сохранения политик, которое не поддерживается на версиях [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ранее [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3be22-113">Automation requires the policies to be stored locally, which is not supported on versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] earlier than [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
-   <span data-ttu-id="3be22-114">Серверы, на которых требуется развернуть запланированные политики, должны быть зарегистрированы в списке «Зарегистрированные серверы» либо в узле « **локальные** серверы», либо на **центральном сервере управления** .</span><span class="sxs-lookup"><span data-stu-id="3be22-114">The servers where you want to deploy the scheduled policies must be registered in Registered Servers in either the **Local Server Groups** or the **Central Management Servers** node.</span></span> <span data-ttu-id="3be22-115">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="3be22-115">For more information, see the following topics:</span></span>  
  
    -   [<span data-ttu-id="3be22-116">Создание или изменение группы серверов (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="3be22-116">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-or-edit-a-server-group-sql-server-management-studio.md)  
  
    -   <span data-ttu-id="3be22-117">[Зарегистрируйте подключенный сервер &#40;SQL Server Management Studio&#41;](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="3be22-117">[Register a Connected Server &#40;SQL Server Management Studio&#41;](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span></span>  
  
    -   [<span data-ttu-id="3be22-118">Создание центрального сервера управления и группы сервера (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="3be22-118">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-a-central-management-server-and-server-group.md)  
  
### <a name="to-export-the-scheduled-policies-as-xml-files"></a><span data-ttu-id="3be22-119">Экспорт запланированных политик в XML-файлы</span><span class="sxs-lookup"><span data-stu-id="3be22-119">To export the scheduled policies as .xml files</span></span>  
  
1.  <span data-ttu-id="3be22-120">На сервере, где настроены политики планирования в предыдущей задаче, разверните узел **Управление**, разверните **Управление политиками**, а затем щелкните **политики**.</span><span class="sxs-lookup"><span data-stu-id="3be22-120">On the server where you configured scheduled policies in the previous task, expand **Management**, expand **Policy Management**, and then click **Policies**.</span></span>  
  
2.  <span data-ttu-id="3be22-121">В меню **Вид** выберите **Сведения об обозревателе объектов**.</span><span class="sxs-lookup"><span data-stu-id="3be22-121">On the **View** menu, click **Object Explorer Details**.</span></span>  
  
3.  <span data-ttu-id="3be22-122">В области **Подробности обозревателя объектов** выберите все запланированные политики рекомендаций, которые требуется развернуть на других серверах с помощью зарегистрированных серверов.</span><span class="sxs-lookup"><span data-stu-id="3be22-122">In the **Object Explorer Details** pane, select all the scheduled best practices policies that you want to deploy to other servers through Registered Servers.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3be22-123">Можно щелкнуть заголовок **категории** , чтобы отсортировать политики по категориям.</span><span class="sxs-lookup"><span data-stu-id="3be22-123">You can click the **Category** heading to sort the policies by category.</span></span>  
  
4.  <span data-ttu-id="3be22-124">Щелкните выделенный фрагмент правой кнопкой мыши и выберите пункт **Экспорт политики**.</span><span class="sxs-lookup"><span data-stu-id="3be22-124">Right-click the selection, and then click **Export Policy**.</span></span>  
  
5.  <span data-ttu-id="3be22-125">Если вы выбрали несколько политик для экспорта, в диалоговом окне **Выбор папки** выберите папку назначения или создайте новую папку.</span><span class="sxs-lookup"><span data-stu-id="3be22-125">If you selected multiple policies to export, in the **Browse For Folder** dialog box, select a destination folder, or create a new folder.</span></span> <span data-ttu-id="3be22-126">Для этого занятия создайте новую папку с параметром path **c:\ Scheduled_BP_Policies**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3be22-126">For this lesson, create a new folder with the path **C:\Scheduled_BP_Policies**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="3be22-127">Если для экспорта выбрана только одна политика, в диалоговом окне **Экспорт политики** создайте новую папку с путем **c:\ Scheduled_BP_Policies**, нажмите кнопку **Открыть**, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3be22-127">If you only selected one policy to export, in the **Export Policy** dialog box, create a new folder with the path **C:\Scheduled_BP_Policies**, click **Open**, and then click **Save**.</span></span>  
  
     <span data-ttu-id="3be22-128">XML-файлы политики создаются в указанной папке.</span><span class="sxs-lookup"><span data-stu-id="3be22-128">The .xml policy files are created in the folder location.</span></span>  
  
### <a name="to-deploy-the-scheduled-policies-to-servers-that-are-managed-through-registered-servers"></a><span data-ttu-id="3be22-129">Развертывание политики на серверах, управляемых через окно «Зарегистрированные серверы»</span><span class="sxs-lookup"><span data-stu-id="3be22-129">To deploy the scheduled policies to servers that are managed through Registered Servers</span></span>  
  
1.  <span data-ttu-id="3be22-130">В меню **Вид** выберите пункт **Зарегистрированные серверы**.</span><span class="sxs-lookup"><span data-stu-id="3be22-130">On the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="3be22-131">Разверните **ядро СУБД**, разверните узел **локальные группы серверов** или **Серверы централизованного управления**, щелкните правой кнопкой мыши узел, к которому требуется развернуть политики, и выберите команду **Импорт политик**.</span><span class="sxs-lookup"><span data-stu-id="3be22-131">Expand **Database Engine**, expand either **Local Server Groups** or **Central Management Servers**, right-click the node that you want to deploy the policies to, and then click **Import Policies**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3be22-132">Если щелкнуть правой кнопкой мыши узел **локальные группы серверов** или сам сервер централизованного управления, политики будут развернуты на всех управляемых серверах.</span><span class="sxs-lookup"><span data-stu-id="3be22-132">If you right-click **Local Server Groups** or the Central Management Server itself, the policies will be deployed to all managed servers.</span></span> <span data-ttu-id="3be22-133">Если щелкнуть правой кнопкой мыши конкретную группу серверов, то политики будут развернуты только на серверах, входящих в эту группу.</span><span class="sxs-lookup"><span data-stu-id="3be22-133">If you right-click a specific server group, the policies will only be deployed to servers in that group.</span></span> <span data-ttu-id="3be22-134">Если щелкнуть правой кнопкой мыши конкретный зарегистрированный сервер, то политики будут развернуты только на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="3be22-134">If you right-click a specific registered server, the policies will only be deployed to that server.</span></span>  
  
3.  <span data-ttu-id="3be22-135">Нажмите кнопку с многоточием (**...**) рядом с **файлами для импорта**.</span><span class="sxs-lookup"><span data-stu-id="3be22-135">Next to **Files to import**, click the ellipsis button (**...**).</span></span>  
  
4.  <span data-ttu-id="3be22-136">В диалоговом окне **Выбор политики** перейдите к расположению папки, в которой были сохранены запланированные политики.</span><span class="sxs-lookup"><span data-stu-id="3be22-136">In the **Select Policy** dialog box, browse to the folder location where you saved the scheduled policies.</span></span> <span data-ttu-id="3be22-137">В этом примере перейдите к расположению **c:\ Scheduled_BP_Policies**.</span><span class="sxs-lookup"><span data-stu-id="3be22-137">For this example, browse to the location **C:\Scheduled_BP_Policies**.</span></span>  
  
5.  <span data-ttu-id="3be22-138">Выберите политики, которые необходимо импортировать в целевые экземпляры, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="3be22-138">Select the policies that you want to import to the target instances, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="3be22-139">В диалоговом окне **Импорт** в списке **состояние политики** выберите нужное состояние политики.</span><span class="sxs-lookup"><span data-stu-id="3be22-139">In the **Import** dialog box, in the **Policy state** list, select the desired policy state.</span></span> <span data-ttu-id="3be22-140">Можно выбрать то состояние политики, которое будет применяться при импорте — включать политики или отключать.</span><span class="sxs-lookup"><span data-stu-id="3be22-140">You can choose to preserve the policy state, enable, or disable the policies on import.</span></span> <span data-ttu-id="3be22-141">Имейте в виду, что для политик должен быть разрешен запуск по расписанию.</span><span class="sxs-lookup"><span data-stu-id="3be22-141">Be aware that the policies must be enabled to run on a schedule.</span></span>  
  
7.  <span data-ttu-id="3be22-142">Нажмите кнопку **ОК** , чтобы импортировать политики во все целевые экземпляры.</span><span class="sxs-lookup"><span data-stu-id="3be22-142">Click **OK** to import the policies to all the target instances.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3be22-143">При возникновении ошибок диалоговое окно **Импорт** не исчезает.</span><span class="sxs-lookup"><span data-stu-id="3be22-143">If there are any errors, the **Import** dialog box does not disappear.</span></span> <span data-ttu-id="3be22-144">Щелкните страницу **журнала** , чтобы проверить сообщения.</span><span class="sxs-lookup"><span data-stu-id="3be22-144">Click the **Log** page to review the messages.</span></span> <span data-ttu-id="3be22-145">Нажмите кнопку **Отмена**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="3be22-145">Click **Cancel** to close the dialog box.</span></span>  
  
8.  <span data-ttu-id="3be22-146">Чтобы просмотреть политики из целевого экземпляра, подключитесь к экземпляру, откройте обозреватель объектов, разверните узел **Управление**, а затем узел **политики**.</span><span class="sxs-lookup"><span data-stu-id="3be22-146">To view the policies from a target instance, connect to the instance, open Object Explorer, expand **Management**, and then expand **Policies**.</span></span> <span data-ttu-id="3be22-147">Импортированные политики должны отобразиться в узле **политики** .</span><span class="sxs-lookup"><span data-stu-id="3be22-147">You should see the imported policies in the **Policies** node.</span></span> <span data-ttu-id="3be22-148">Если дважды щелкнуть каждую политику, можно просмотреть расписание или изменить настройки.</span><span class="sxs-lookup"><span data-stu-id="3be22-148">If you double-click each policy, you can view the schedule, or change the settings.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3be22-149">Чтобы просмотреть результаты вычисления после запуска запланированной политики, откройте журнал политик на целевом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="3be22-149">To view the evaluation results after a scheduled policy runs, open the Policy History log on the target instance.</span></span> <span data-ttu-id="3be22-150">Чтобы открыть журнал, щелкните правой кнопкой мыши элемент **Управление политиками**и выберите пункт **Просмотр журнала**.</span><span class="sxs-lookup"><span data-stu-id="3be22-150">To open the log, right-click **Policy Management**, and then click **View History**.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="3be22-151">Итоги</span><span class="sxs-lookup"><span data-stu-id="3be22-151">Summary</span></span>  
 <span data-ttu-id="3be22-152">В этом учебнике было показано, как по требованию и по расписанию производить оценки политик рекомендаций для одного или более экземпляров [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3be22-152">This tutorial has shown you how to perform both on-demand and scheduled evaluations of the best practices policies against one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="next"></a><span data-ttu-id="3be22-153">Следующая</span><span class="sxs-lookup"><span data-stu-id="3be22-153">Next</span></span>  
 <span data-ttu-id="3be22-154">Данный учебник завершен.</span><span class="sxs-lookup"><span data-stu-id="3be22-154">This tutorial is finished.</span></span> <span data-ttu-id="3be22-155">Чтобы вернуться к началу работы, см. раздел [учебник. Оценка рекомендаций с помощью управления на основе политик](../../2014/tutorials/tutorial-evaluating-best-practices-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="3be22-155">To return to the start, see [Tutorial: Evaluating Best Practices by Using Policy-Based Management](../../2014/tutorials/tutorial-evaluating-best-practices-by-using-policy-based-management.md).</span></span>  
  
 <span data-ttu-id="3be22-156">Чтобы просмотреть список [!INCLUDE[ssDE](../includes/ssde-md.md)] учебников, щелкните [ядро СУБД учебники](../relational-databases/database-engine-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="3be22-156">To see a list of [!INCLUDE[ssDE](../includes/ssde-md.md)] tutorials, click [Database Engine Tutorials](../relational-databases/database-engine-tutorials.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be22-157">См. также:</span><span class="sxs-lookup"><span data-stu-id="3be22-157">See Also</span></span>  
 [<span data-ttu-id="3be22-158">Администрирование серверов с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="3be22-158">Administer Servers by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
