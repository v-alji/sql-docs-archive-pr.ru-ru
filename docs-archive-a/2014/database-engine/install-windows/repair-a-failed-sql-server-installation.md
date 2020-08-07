---
title: Восстановление установки SQL Server 2014 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 90c11b28-892b-44d6-978e-0eee48c75b7d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f3e382137a971b3f8b23cf1d814bff9908f04150
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732902"
---
# <a name="drop-a-sql-server-2014-installation"></a><span data-ttu-id="71fee-102">Удаление установки SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="71fee-102">Drop a SQL Server 2014 Installation</span></span>
  <span data-ttu-id="71fee-103">Операцию исправления можно применять в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="71fee-103">Repair operation can be used in the following scenarios:</span></span>  
  
-   <span data-ttu-id="71fee-104">Для исправления экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который оказался поврежденным после успешной установки.</span><span class="sxs-lookup"><span data-stu-id="71fee-104">Repair an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is corrupted after it was successfully installed.</span></span>  
  
-   <span data-ttu-id="71fee-105">Для исправления экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , если операция обновления была отменена или завершилась ошибкой после сопоставления имени экземпляра с экземпляром после обновления.</span><span class="sxs-lookup"><span data-stu-id="71fee-105">Repair an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if the upgrade operation is cancelled or fails after the instance name is mapped to the newly-upgraded instance.</span></span>  
  
    -   <span data-ttu-id="71fee-106">Если в сводном журнале присутствует следующее сообщение, экземпляр можно исправить после ошибки обновления:</span><span class="sxs-lookup"><span data-stu-id="71fee-106">If you see the following message in the summary log, you can repair the failed upgrade instance:</span></span>  
  
         <span data-ttu-id="71fee-107">«Не удалось обновить[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71fee-107">"[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] upgrade failed.</span></span> <span data-ttu-id="71fee-108">Чтобы продолжить, определите причину сбоя, устраните проблему, а затем запустите исправление установки».</span><span class="sxs-lookup"><span data-stu-id="71fee-108">To continue, investigate the reason for the failure, correct the problem, and then repair your installation."</span></span>  
  
    -   <span data-ttu-id="71fee-109">Если в сводном журнале присутствует следующее сообщение, необходимо удалить и повторно установить [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71fee-109">If you see the following message in the summary log, you need to uninstall and reinstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="71fee-110">Исправить экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] невозможно.</span><span class="sxs-lookup"><span data-stu-id="71fee-110">You cannot repair the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
         <span data-ttu-id="71fee-111">«Не удалось обновить[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71fee-111">"[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] upgrade failed.</span></span> <span data-ttu-id="71fee-112">Чтобы продолжить, определите причину сбоя и устраните проблему».</span><span class="sxs-lookup"><span data-stu-id="71fee-112">To continue, investigate the reason for the failure, correct the problem."</span></span>  
  
 <span data-ttu-id="71fee-113">В ходе восстановления экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]выполняются следующие действия.</span><span class="sxs-lookup"><span data-stu-id="71fee-113">When you repair an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="71fee-114">Заменяются все отсутствующие или поврежденные файлы.</span><span class="sxs-lookup"><span data-stu-id="71fee-114">All missing or corrupt files are replaced.</span></span>  
  
-   <span data-ttu-id="71fee-115">Заменяются все отсутствующие или поврежденные разделы реестра.</span><span class="sxs-lookup"><span data-stu-id="71fee-115">All missing or corrupt registry keys are replaced.</span></span>  
  
-   <span data-ttu-id="71fee-116">Для всех отсутствующих или недопустимых параметров конфигурации устанавливаются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71fee-116">All missing or invalid configuration values are set to default values.</span></span>  
  
 <span data-ttu-id="71fee-117">Перед тем как продолжить, при использовании отказоустойчивых кластеров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ознакомьтесь со следующими важными сведениями.</span><span class="sxs-lookup"><span data-stu-id="71fee-117">Before you continue, for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover clusters, review the following important information:</span></span>  
  
-   <span data-ttu-id="71fee-118">Исправление должно быть запущено на отдельных узлах кластера.</span><span class="sxs-lookup"><span data-stu-id="71fee-118">Repair must be run on individual cluster nodes.</span></span>  
  
-   <span data-ttu-id="71fee-119">Для исправления узла отказоустойчивого кластера после неудачной операции «Подготовка» используйте кнопку **Удалить узел** , а затем еще раз осуществите шаг «Подготовка».</span><span class="sxs-lookup"><span data-stu-id="71fee-119">To repair a failover cluster node after a failed Prepare operation, use **Remove node** and then perform the Prepare step again.</span></span> <span data-ttu-id="71fee-120">Дополнительные сведения см. на странице [Добавление и удаление узлов в отказоустойчивом кластере SQL Server (настройка)](../../sql-server/failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span><span class="sxs-lookup"><span data-stu-id="71fee-120">For more information, see [Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;](../../sql-server/failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span></span>  
  
### <a name="to-repair-a-failed-installation-of-ssnoversion-from-the-installation-center"></a><span data-ttu-id="71fee-121">Исправление ошибочной установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из центра установки</span><span class="sxs-lookup"><span data-stu-id="71fee-121">To repair a failed installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the Installation Center</span></span>  
  
1.  <span data-ttu-id="71fee-122">Запустите программу установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (setup.exe), расположенную на установочном носителе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71fee-122">Launch the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup program (setup.exe) from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation media.</span></span>  
  
2.  <span data-ttu-id="71fee-123">После выполнения необходимых условий и проверки системы программа установки выводит страницу центра установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71fee-123">After prerequisites and system verification, the Setup program will display the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Center page.</span></span>  
  
3.  <span data-ttu-id="71fee-124">Для начала операции исправления нажмите кнопку **Обслуживание** в левой части области навигации, а затем кнопку **Исправление** .</span><span class="sxs-lookup"><span data-stu-id="71fee-124">Click **Maintenance** in the left-hand navigation area, and then click **Repair** to start the repair operation.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="71fee-125">Если центр установки был запущен из меню «Пуск», то в этот раз потребуется указать расположение установочного носителя.</span><span class="sxs-lookup"><span data-stu-id="71fee-125">If the Installation Center was launched using the start menu, you will need to provide the location of the installation media at this time.</span></span>  
  
4.  <span data-ttu-id="71fee-126">Будут запущены правило поддержки установки и файлы подпрограмм, чтобы удостовериться, что в системе установлены необходимые компоненты и что компьютер отвечает правилам проверки.</span><span class="sxs-lookup"><span data-stu-id="71fee-126">Setup support rule and file routines will run to ensure that your system has prerequisites installed and that the computer passes Setup validation rules.</span></span> <span data-ttu-id="71fee-127">Для продолжения нажмите кнопку **ОК** или **Установить** .</span><span class="sxs-lookup"><span data-stu-id="71fee-127">Click **OK** or **Install** to continue.</span></span>  
  
5.  <span data-ttu-id="71fee-128">На странице «Выбор экземпляра» выберите экземпляр для исправления и нажмите кнопку **Далее** для продолжения.</span><span class="sxs-lookup"><span data-stu-id="71fee-128">On the Select Instance page, select the instance to repair, and then click **Next** to continue.</span></span>  
  
6.  <span data-ttu-id="71fee-129">Будут запущены правила исправления для проверки операции.</span><span class="sxs-lookup"><span data-stu-id="71fee-129">The repair rules will run to validate the operation.</span></span> <span data-ttu-id="71fee-130">Чтобы продолжить, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="71fee-130">To continue, click **Next**.</span></span>  
  
7.  <span data-ttu-id="71fee-131">Страница «Готовность к исправлению» показывает, что операция готова к продолжению.</span><span class="sxs-lookup"><span data-stu-id="71fee-131">The Ready to Repair page indicates that the operation is ready to proceed.</span></span> <span data-ttu-id="71fee-132">Чтобы продолжить, нажмите кнопку **Исправить**.</span><span class="sxs-lookup"><span data-stu-id="71fee-132">To continue, click **Repair**.</span></span>  
  
8.  <span data-ttu-id="71fee-133">Страница «Состояние исправления» показывает состояние операции исправления.</span><span class="sxs-lookup"><span data-stu-id="71fee-133">The Repair Progress page shows the status of the repair operation.</span></span> <span data-ttu-id="71fee-134">Страница «Готово» показывает, что операция завершена.</span><span class="sxs-lookup"><span data-stu-id="71fee-134">The Complete page indicates that the operation is finished.</span></span>  
  
### <a name="to-repair-a-failed-installation-of-ssnoversion-using-command-prompt"></a><span data-ttu-id="71fee-135">Исправление ошибочной установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из командной строки</span><span class="sxs-lookup"><span data-stu-id="71fee-135">To repair a failed installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Command Prompt</span></span>  
  
1.  <span data-ttu-id="71fee-136">Выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="71fee-136">Run the following command at a command prompt:</span></span>  
  
    ```  
    Setup.exe /q /ACTION=Repair /INSTANCENAME=instancename  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="71fee-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="71fee-137">See Also</span></span>  
 <span data-ttu-id="71fee-138">[Просмотр и чтение файлов журналов программы установки SQL Server](view-and-read-sql-server-setup-log-files.md) </span><span class="sxs-lookup"><span data-stu-id="71fee-138">[View and Read SQL Server Setup Log Files](view-and-read-sql-server-setup-log-files.md) </span></span>  
 [<span data-ttu-id="71fee-139">Инструкции по установке</span><span class="sxs-lookup"><span data-stu-id="71fee-139">Installation How-to Topics</span></span>](../../sql-server/install/installation-how-to-topics.md)  
  
  
