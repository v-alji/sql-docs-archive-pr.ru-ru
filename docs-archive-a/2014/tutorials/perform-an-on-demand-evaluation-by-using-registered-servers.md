---
title: Выполнение оценки по запросу с помощью компонента "зарегистрированные серверы" | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: c14034ef-6e0b-4df5-8072-bfb8d90b3172
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: a3a06efaabff7e94e5b560744f0e1c739831042a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654672"
---
# <a name="perform-an-on-demand-evaluation-by-using-registered-servers"></a><span data-ttu-id="9c349-102">выполнить политику по запросу с помощью зарегистрированных серверов</span><span class="sxs-lookup"><span data-stu-id="9c349-102">Perform an On-Demand Evaluation by Using Registered Servers</span></span>

  <span data-ttu-id="9c349-103">Можно выполнить оценку по требованию рекомендуемых политик по отношению к одному или нескольким экземплярам [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] через окно «Зарегистрированные серверы».</span><span class="sxs-lookup"><span data-stu-id="9c349-103">You can perform an on-demand evaluation of best practices policies against one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by using Registered Servers.</span></span> <span data-ttu-id="9c349-104">Можно использовать локальную группу серверов или центральный сервер управления.</span><span class="sxs-lookup"><span data-stu-id="9c349-104">You can use either local server groups or a central management server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9c349-105">Выполнение рекомендуемых политик по запросу может быть выполнено по отношению к членам группы серверов, на которых запущен [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] или более поздняя версия [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c349-105">You can perform an on-demand evaluation of best practices policies against server group members that are running [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] or a later version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9c349-106">Однако, если в политике имеется ссылка на некоторые свойства, неподдерживаемые в [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] или [!INCLUDE[ssVersion2000](../includes/ssversion2000-md.md)], может возникнуть исключение.</span><span class="sxs-lookup"><span data-stu-id="9c349-106">However, you may receive an exception error if there are some properties that are referred to by a policy that are not supported in [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] or [!INCLUDE[ssVersion2000](../includes/ssversion2000-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9c349-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9c349-107">Prerequisites</span></span>  
 <span data-ttu-id="9c349-108">Для выполнения этой задачи необходимо иметь в настроенном виде один или несколько серверов в окне «Зарегистрированные серверы».</span><span class="sxs-lookup"><span data-stu-id="9c349-108">To perform this task, you must have configured one or more server registrations in Registered Servers.</span></span> <span data-ttu-id="9c349-109">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9c349-109">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="9c349-110">Создание или изменение группы серверов (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="9c349-110">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-or-edit-a-server-group-sql-server-management-studio.md)  
  
-   <span data-ttu-id="9c349-111">[Зарегистрируйте подключенный сервер &#40;SQL Server Management Studio&#41;](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="9c349-111">[Register a Connected Server &#40;SQL Server Management Studio&#41;](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span></span>  
  
-   [<span data-ttu-id="9c349-112">Создание центрального сервера управления и группы сервера (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="9c349-112">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-a-central-management-server-and-server-group.md)  
  
### <a name="to-evaluate-best-practices-policies-against-a-server-group"></a><span data-ttu-id="9c349-113">Оценка рекомендованных политик по отношению к группе серверов</span><span class="sxs-lookup"><span data-stu-id="9c349-113">To evaluate best practices policies against a server group</span></span>  
  
1.  <span data-ttu-id="9c349-114">В среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]в меню **Вид** выберите пункт **Зарегистрированные серверы**.</span><span class="sxs-lookup"><span data-stu-id="9c349-114">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="9c349-115">Разверните **ядро СУБД**, а затем в зависимости от конфигурации разверните узел **локальные группы серверов**или **Серверы централизованного управления**.</span><span class="sxs-lookup"><span data-stu-id="9c349-115">Expand **Database Engine**, and then expand either **Local Server Groups**, or **Central Management Servers**, depending on your configuration.</span></span>  
  
3.  <span data-ttu-id="9c349-116">Выполните одно из приведенных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="9c349-116">Do either of the following:</span></span>  
  
    -   <span data-ttu-id="9c349-117">Чтобы оценить политики для всех серверов, управляемых локальной группой серверов или центральным сервером управления, щелкните правой кнопкой мыши имя группы локальных серверов или имя сервера централизованного управления, а затем выберите пункт **вычислить политики**.</span><span class="sxs-lookup"><span data-stu-id="9c349-117">To evaluate the policies against all servers that are managed by the local server group or the central management server, right-click the local server group name or the central management server name, and then click **Evaluate Policies**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="9c349-118">При выполнении политик по центральному серверу управления эти политики не вычисляются по центральному серверу управления.</span><span class="sxs-lookup"><span data-stu-id="9c349-118">When you evaluate policies through a central management server, the policies are not evaluated against the central management server itself.</span></span>  
  
    -   <span data-ttu-id="9c349-119">Чтобы оценить политики на определенном сервере или группе серверов, разверните узел **локальные группы серверов** или имя сервера управления, щелкните правой кнопкой мыши сервер или группу серверов, для которых нужно оценить политики, а затем выберите команду **вычислить политики**.</span><span class="sxs-lookup"><span data-stu-id="9c349-119">To evaluate the policies against a specific server or server group, expand **Local Server Groups** or the central management server name, right-click the server or server group that you want to evaluate policies against, and then click **Evaluate Policies**.</span></span>  
  
4.  <span data-ttu-id="9c349-120">В диалоговом окне **Вычисление политик** рядом с полем **источник** нажмите кнопку с многоточием (**...**).</span><span class="sxs-lookup"><span data-stu-id="9c349-120">In the **Evaluate Policies** dialog box, next to the **Source** box, click the ellipsis (**...**) button.</span></span>  
  
5.  <span data-ttu-id="9c349-121">В диалоговом окне **Выбор источника** можно выбрать **файлы** или **сервер** в качестве источника файлов политики для вычисления.</span><span class="sxs-lookup"><span data-stu-id="9c349-121">In the **Select Source** dialog box, you can select either **Files** or **Server** as the source of the policy files to evaluate.</span></span> <span data-ttu-id="9c349-122">Если щелкнуть **сервер**, можно выполнить оценку всех рекомендаций по запросу, которые ранее были импортированы в управление на основе политик на локальном или удаленном сервере.</span><span class="sxs-lookup"><span data-stu-id="9c349-122">If you click **Server**, you can perform an on-demand evaluation of any best practices policies that were previously imported into Policy-Based Management on a local or remote server.</span></span> <span data-ttu-id="9c349-123">В этом учебнике вы щелкните **файлы**, а затем выберите отдельные файлы политики, которые нужно оценить.</span><span class="sxs-lookup"><span data-stu-id="9c349-123">In this tutorial, you will click **Files**, and then select the individual policy files that you want to evaluate.</span></span> <span data-ttu-id="9c349-124">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9c349-124">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="9c349-125">Щелкните **файлы**.</span><span class="sxs-lookup"><span data-stu-id="9c349-125">Click **Files**.</span></span>  
  
    2.  <span data-ttu-id="9c349-126">Рядом с пунктом **файлы**нажмите кнопку с многоточием (**...**).</span><span class="sxs-lookup"><span data-stu-id="9c349-126">Next to **Files**, click the ellipsis (**...**) button.</span></span>  
  
    3.  <span data-ttu-id="9c349-127">Выберите один или несколько файлов политики XML для вычисления, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="9c349-127">Select one or more .xml policy files to evaluate, and then click **Open**.</span></span>  
  
         <span data-ttu-id="9c349-128">Список выбранных файлов появится в поле **файлы** .</span><span class="sxs-lookup"><span data-stu-id="9c349-128">The list of selected files appears in the **Files** box.</span></span>  
  
    4.  <span data-ttu-id="9c349-129">В диалоговом окне **Выбор источника** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9c349-129">In the **Select Source** dialog box, click **OK**.</span></span>  
  
    5.  <span data-ttu-id="9c349-130">Если откроется диалоговое окно " **Загрузка политик** ", нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="9c349-130">If the **Loading Policies** dialog box appears, click **Close**.</span></span>  
  
     <span data-ttu-id="9c349-131">Выбранные политики будут перечислены на странице **Выбор политики** .</span><span class="sxs-lookup"><span data-stu-id="9c349-131">The policies that you selected are listed on the **Policy Selection** page.</span></span> <span data-ttu-id="9c349-132">Учтите, что предупреждающий значок рядом с политикой показывает, что она содержит скрипты.</span><span class="sxs-lookup"><span data-stu-id="9c349-132">Be aware that a warning icon next to a policy indicates that the policy contains scripts.</span></span>  
  
6.  <span data-ttu-id="9c349-133">Нажмите кнопку **вычислить** , чтобы оценить политики.</span><span class="sxs-lookup"><span data-stu-id="9c349-133">Click **Evaluate** to evaluate the policies.</span></span>  
  
7.  <span data-ttu-id="9c349-134">В некоторых случаях ошибок политик система управления на основе политик позволяет немедленно принудительно применить политику к цели.</span><span class="sxs-lookup"><span data-stu-id="9c349-134">For some policy failures, Policy-Based Management enables you to immediately enforce policy compliance on the target.</span></span> <span data-ttu-id="9c349-135">В таких случаях рядом с политикой, вызвавшей ошибку, появится флажок.</span><span class="sxs-lookup"><span data-stu-id="9c349-135">For such failures, a check box will appear next to the failed policy.</span></span> <span data-ttu-id="9c349-136">Если установлен флажок или выбрана строка с политикой "сбой", то рядом с целевыми экземплярами, для которых произошел сбой оценки, отобразятся флажки в области **Подробности целевого объекта** .</span><span class="sxs-lookup"><span data-stu-id="9c349-136">If you select the check box, or click the row with the failed policy, check boxes appear in the **Target details** pane next to the target instances that failed the evaluation.</span></span> <span data-ttu-id="9c349-137">Если один из флажков установлен, кнопка **Применить** станет доступной.</span><span class="sxs-lookup"><span data-stu-id="9c349-137">If any of the check boxes are selected, the **Apply** button becomes available.</span></span> <span data-ttu-id="9c349-138">При нажатии кнопки " **Применить**" параметр "не соответствует политике" будет автоматически обновлен на выбранных целевых экземплярах.</span><span class="sxs-lookup"><span data-stu-id="9c349-138">When you click **Apply**, the noncompliant setting will be automatically updated on the target instances that you selected.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="9c349-139">Перед автоматическим обновлением целевого экземпляра убедитесь, что точно известны последствия применения политики.</span><span class="sxs-lookup"><span data-stu-id="9c349-139">Make sure that you fully understand the policy setting before automatically updating a target instance.</span></span> <span data-ttu-id="9c349-140">Рекомендуется после выбора одного или нескольких флажков нажать кнопку **Скрипт**и выбрать расположение выходных данных, чтобы можно было просмотреть базовый [!INCLUDE[tsql](../includes/tsql-md.md)] код перед применением изменений.</span><span class="sxs-lookup"><span data-stu-id="9c349-140">We recommend that after you select one or more check boxes, you click **Script**, and choose an output location so that you can review the underlying [!INCLUDE[tsql](../includes/tsql-md.md)] code before you apply the changes.</span></span>  
  
8.  <span data-ttu-id="9c349-141">Чтобы просмотреть подробные результаты для политики, щелкните политику в таблице **результатов** .</span><span class="sxs-lookup"><span data-stu-id="9c349-141">To view detailed results for a policy, click the policy in the **Results** table.</span></span> <span data-ttu-id="9c349-142">В таблице **целевые сведения** отображаются сведения для каждого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9c349-142">The **Target details** table shows the details for each instance.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="9c349-143">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="9c349-143">Next Lesson</span></span>  
 [<span data-ttu-id="9c349-144">Урок 2. Выполнение политик рекомендаций по расписанию</span><span class="sxs-lookup"><span data-stu-id="9c349-144">Lesson 2: Evaluate Best Practices Policies on a Scheduled Basis</span></span>](../../2014/tutorials/lesson-2-evaluate-best-practices-policies-on-a-scheduled-basis.md)  
  
## <a name="see-also"></a><span data-ttu-id="9c349-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="9c349-145">See Also</span></span>  
 <span data-ttu-id="9c349-146">[Мониторинг и применение рекомендаций с помощью управления на основе политик](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md) </span><span class="sxs-lookup"><span data-stu-id="9c349-146">[Monitor and Enforce Best Practices by Using Policy-Based Management](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md) </span></span>  
 [<span data-ttu-id="9c349-147">Администрирование нескольких серверов с помощью центральных серверов управления</span><span class="sxs-lookup"><span data-stu-id="9c349-147">Administer Multiple Servers Using Central Management Servers</span></span>](../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
