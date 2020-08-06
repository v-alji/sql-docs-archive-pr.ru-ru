---
title: Выполнение оценки по запросу с помощью обозревателя объектов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: ee6d3b79-18bc-49d3-8a1d-0c0905b990f0
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: e32876978ac462af361986d84e11ef3dc0f278e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654671"
---
# <a name="perform-an-on-demand-evaluation-by-using-object-explorer"></a><span data-ttu-id="1d626-102">Perform an On-Demand Evaluation by Using Object Explorer</span><span class="sxs-lookup"><span data-stu-id="1d626-102">Perform an On-Demand Evaluation by Using Object Explorer</span></span>
  <span data-ttu-id="1d626-103">В этой задаче для выполнения по запросу рекомендуемых политик для компонента [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] на единственном экземпляре [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] используется обозреватель объектов.</span><span class="sxs-lookup"><span data-stu-id="1d626-103">In this task, you will use Object Explorer to perform an on-demand evaluation of best practices policies for the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] on a single instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1d626-104">Выполнение политик может также производиться на единственном экземпляре через окно «Зарегистрированные серверы».</span><span class="sxs-lookup"><span data-stu-id="1d626-104">You can also evaluate policies on a single instance through Registered Servers.</span></span> <span data-ttu-id="1d626-105">Дополнительные сведения см. [в разделе Выполнение оценки по запросу с помощью компонента зарегистрированные серверы](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span><span class="sxs-lookup"><span data-stu-id="1d626-105">For more information, see [Perform an On-Demand Evaluation by Using Registered Servers](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1d626-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="1d626-106">Prerequisites</span></span>  
 <span data-ttu-id="1d626-107">На этом занятие используется версия [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] из [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d626-107">This lesson is based on the version of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1d626-108">Чтобы выполнить оценку рекомендаций по запросу для выполняемых экземпляров [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] , необходимо использовать процедуру, описанную в разделе [выполнение оценки по запросу с помощью компонента зарегистрированные серверы](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span><span class="sxs-lookup"><span data-stu-id="1d626-108">To perform an on-demand evaluation of best practices policies against instances that are running [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], you must use the procedure in the topic [Perform an On-Demand Evaluation by Using Registered Servers](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span></span>  
  
### <a name="to-perform-an-on-demand-evaluation-by-using-object-explorer"></a><span data-ttu-id="1d626-109">Выполнение политики по запросу с помощью обозревателя объектов</span><span class="sxs-lookup"><span data-stu-id="1d626-109">To perform an on-demand evaluation by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="1d626-110">Запустите среду [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]и подключитесь к компоненту [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d626-110">Start [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], and then connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1d626-111">В обозревателе объектов раскройте узлы **Управление**, **Управление политиками**, щелкните правой кнопкой мыши **политики**и выберите команду **вычислить**.</span><span class="sxs-lookup"><span data-stu-id="1d626-111">In Object Explorer, expand **Management**, expand **Policy Management**, right-click **Policies**, and then click **Evaluate**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1d626-112">По умолчанию в качестве источника политик используется локальный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="1d626-112">By default, the local instance is used as the source of the policies.</span></span> <span data-ttu-id="1d626-113">Если ранее были импортированы рекомендованные политики, то они будут перечислены наряду со всеми другими политиками, созданными пользователем.</span><span class="sxs-lookup"><span data-stu-id="1d626-113">If you have previously imported best practices policies, they will be listed, together with any other policies that you have created.</span></span> <span data-ttu-id="1d626-114">Можно выбрать любую из импортированных политик рекомендаций, а затем нажать кнопку **вычислить**.</span><span class="sxs-lookup"><span data-stu-id="1d626-114">You can select any of the imported best practices policies, and then click **Evaluate**.</span></span> <span data-ttu-id="1d626-115">Если рекомендованные политики не были импортированы, то продолжите выполнение этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="1d626-115">If you have not imported the best practices policies, continue with this procedure.</span></span>  
  
3.  <span data-ttu-id="1d626-116">В диалоговом окне **Вычисление политик** рядом с полем **источник** нажмите кнопку с многоточием (**...**).</span><span class="sxs-lookup"><span data-stu-id="1d626-116">In the **Evaluate Policies** dialog box, next to the **Source** box, click the ellipsis (**...**) button.</span></span>  
  
4.  <span data-ttu-id="1d626-117">В диалоговом окне **Выбор источника** можно выбрать **файлы** или **сервер** в качестве источника файлов политики для вычисления.</span><span class="sxs-lookup"><span data-stu-id="1d626-117">In the **Select Source** dialog box, you can select either **Files** or **Server** as the source of the policy files to evaluate.</span></span> <span data-ttu-id="1d626-118">Если щелкнуть **сервер**, можно выполнить оценку всех рекомендаций по запросу, которые ранее были импортированы в управление на основе политик на локальном или удаленном сервере.</span><span class="sxs-lookup"><span data-stu-id="1d626-118">If you click **Server**, you can perform an on-demand evaluation of any best practices policies that were previously imported into Policy-Based Management on a local or remote server.</span></span> <span data-ttu-id="1d626-119">В этом учебнике вы щелкните **файлы**, а затем выберите отдельные файлы политики, которые нужно оценить.</span><span class="sxs-lookup"><span data-stu-id="1d626-119">In this tutorial, you will click **Files**, and then select the individual policy files that you want to evaluate.</span></span> <span data-ttu-id="1d626-120">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1d626-120">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="1d626-121">Щелкните **файлы**.</span><span class="sxs-lookup"><span data-stu-id="1d626-121">Click **Files**.</span></span>  
  
    2.  <span data-ttu-id="1d626-122">Рядом с пунктом **файлы**нажмите кнопку с многоточием (**...**).</span><span class="sxs-lookup"><span data-stu-id="1d626-122">Next to **Files**, click the ellipsis (**...**) button.</span></span>  
  
    3.  <span data-ttu-id="1d626-123">В диалоговом окне **Выбор политики** перейдите к следующей папке, которая содержит политики Best Practices:</span><span class="sxs-lookup"><span data-stu-id="1d626-123">In the **Select Policy** dialog box, browse to the following folder, which contains the best practices policies:</span></span>  
  
         <span data-ttu-id="1d626-124">**C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span><span class="sxs-lookup"><span data-stu-id="1d626-124">**C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="1d626-125">Путь к файлу может меняться в зависимости от места установки файлов [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , используемой версии (32-разрядной или 64-разрядной) операционной системы и идентификатора языка.</span><span class="sxs-lookup"><span data-stu-id="1d626-125">The file path may vary, depending on where you installed the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] program files, whether you are running a 32-bit or 64-bit operating system, and the language identifier.</span></span>  
  
    4.  <span data-ttu-id="1d626-126">Выберите один или несколько файлов политики XML для вычисления, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="1d626-126">Select one or more .xml policy files to evaluate, and then click **Open**.</span></span>  
  
         <span data-ttu-id="1d626-127">Список выбранных файлов появится в поле **файлы** .</span><span class="sxs-lookup"><span data-stu-id="1d626-127">The list of selected files appears in the **Files** box.</span></span>  
  
    5.  <span data-ttu-id="1d626-128">В диалоговом окне **Выбор источника** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1d626-128">In the **Select Source** dialog box, click **OK**.</span></span>  
  
    6.  <span data-ttu-id="1d626-129">Если откроется диалоговое окно " **Загрузка политик** ", нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1d626-129">If the **Loading Policies** dialog box appears, click **Close**.</span></span>  
  
     <span data-ttu-id="1d626-130">Выбранные политики будут перечислены на странице **Выбор политики** .</span><span class="sxs-lookup"><span data-stu-id="1d626-130">The policies that you selected are listed on the **Policy Selection** page.</span></span> <span data-ttu-id="1d626-131">Учтите, что предупреждающий значок рядом с политикой показывает, что она содержит скрипты.</span><span class="sxs-lookup"><span data-stu-id="1d626-131">Be aware that a warning icon next to a policy indicates that the policy contains scripts.</span></span>  
  
5.  <span data-ttu-id="1d626-132">Нажмите кнопку **вычислить** , чтобы оценить политики.</span><span class="sxs-lookup"><span data-stu-id="1d626-132">Click **Evaluate** to evaluate the policies.</span></span>  
  
     <span data-ttu-id="1d626-133">В таблице **результатов** перечислены результаты для каждой политики.</span><span class="sxs-lookup"><span data-stu-id="1d626-133">In the **Results** table, the results for each policy are listed.</span></span> <span data-ttu-id="1d626-134">Красный значок «x» указывает, что проверка соответствия политике окончилась неуспешно.</span><span class="sxs-lookup"><span data-stu-id="1d626-134">A red "x" icon indicates that policy compliance failed.</span></span>  
  
6.  <span data-ttu-id="1d626-135">В некоторых случаях ошибок политик система управления на основе политик позволяет немедленно принудительно применить политику к цели.</span><span class="sxs-lookup"><span data-stu-id="1d626-135">For some policy failures, Policy-Based Management enables you to immediately enforce policy compliance on the target.</span></span> <span data-ttu-id="1d626-136">В таких случаях рядом с политикой, вызвавшей ошибку, появится флажок.</span><span class="sxs-lookup"><span data-stu-id="1d626-136">For such failures, a check box will appear next to the failed policy.</span></span> <span data-ttu-id="1d626-137">Если установить этот флажок, кнопка **Применить** станет доступной.</span><span class="sxs-lookup"><span data-stu-id="1d626-137">If you select the check box, the **Apply** button becomes available.</span></span> <span data-ttu-id="1d626-138">При нажатии кнопки " **Применить**" параметр "не соответствует политике" будет автоматически обновлен на целевом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="1d626-138">When you click **Apply**, the noncompliant setting will be automatically updated on the target instance.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="1d626-139">Перед автоматическим обновлением целевого экземпляра убедитесь, что точно известны последствия применения политики.</span><span class="sxs-lookup"><span data-stu-id="1d626-139">Make sure that you fully understand the policy setting before automatically updating a target instance.</span></span> <span data-ttu-id="1d626-140">Рекомендуется после выбора одного или нескольких флажков нажать кнопку **Скрипт**и выбрать расположение выходных данных, чтобы можно было просмотреть базовый [!INCLUDE[tsql](../includes/tsql-md.md)] код перед применением изменений.</span><span class="sxs-lookup"><span data-stu-id="1d626-140">We recommend that after you select one or more check boxes, you click **Script**, and choose an output location so that you can review the underlying [!INCLUDE[tsql](../includes/tsql-md.md)] code before you apply the changes.</span></span>  
  
7.  <span data-ttu-id="1d626-141">Чтобы просмотреть подробные результаты для политики, щелкните политику в таблице **результатов** .</span><span class="sxs-lookup"><span data-stu-id="1d626-141">To view detailed results for a policy, click the policy in the **Results** table.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="1d626-142">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="1d626-142">Next Task in Lesson</span></span>  
 [<span data-ttu-id="1d626-143">выполнить политику по запросу с помощью зарегистрированных серверов</span><span class="sxs-lookup"><span data-stu-id="1d626-143">Perform an On-Demand Evaluation by Using Registered Servers</span></span>](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md)  
  
  
