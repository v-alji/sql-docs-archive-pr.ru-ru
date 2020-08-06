---
title: Просмотр файлов журнала в режиме "вне сети" | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Log File Viewer, viewing offline logs
- offline log files
ms.assetid: 9223e474-f224-4907-a4f2-081e11db58f5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2afc1992b54c78f69bfae1fc152b41c20bcd4ea1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666585"
---
# <a name="view-offline-log-files"></a><span data-ttu-id="bb69f-102">просматривать файлы журнала в режиме «вне сети»</span><span class="sxs-lookup"><span data-stu-id="bb69f-102">View Offline Log Files</span></span>
  <span data-ttu-id="bb69f-103">Начиная с версии [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], появилась возможность просматривать файлы журнала [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на локальных и удаленных экземплярах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которые находятся вне сети или не могут запуститься.</span><span class="sxs-lookup"><span data-stu-id="bb69f-103">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], you can view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files from a local or remote instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] when the target instance is offline or cannot start.</span></span>  
  
 <span data-ttu-id="bb69f-104">Получить доступ к файлам журналов вне сети можно в списке «Зарегистрированные серверы» или программным способом с помощью запросов WMI и WQL.</span><span class="sxs-lookup"><span data-stu-id="bb69f-104">You can access the offline log files from Registered Servers, or programmatically through WMI and WQL (WMI Query Language) queries.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb69f-105">Эти методы подходят для подключения к экземпляру в сети, к которому по ряду причин нельзя подключиться с помощью соединения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb69f-105">You can also use these methods to connect to an instance that is online, but for some reason, you cannot connect through a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="bb69f-106">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="bb69f-106">Before you Begin</span></span>  
 <span data-ttu-id="bb69f-107">Чтобы подключиться к файлам журналов вне сети, на компьютере, который используется для просмотра автономных файлов журнала, и на компьютере, на котором расположены файлы журналов для просмотра, должен быть установлен экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb69f-107">To connect to offline log files, an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be installed on the computer that you are using to view the offline log files, and on the computer where the log files that you want to view are located.</span></span> <span data-ttu-id="bb69f-108">Если на обоих компьютерах установлен экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , то на каждом из них можно просматривать «вне сети» файлы журналов для экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]и экземпляров, на которых выполняется [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="bb69f-108">If an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on both computers, you can view offline files for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and for instances that are running earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on either computer.</span></span>  
  
 <span data-ttu-id="bb69f-109">При использовании списка "Зарегистрированные серверы" экземпляр, к которому нужно подключиться, должен быть зарегистрирован в **Группы локальных серверов** или **Центральные серверы управления**.</span><span class="sxs-lookup"><span data-stu-id="bb69f-109">If you are using Registered Servers, the instance that you want to connect to must be registered under **Local Server Groups** or under **Central Management Servers**.</span></span> <span data-ttu-id="bb69f-110">(Экземпляр может быть зарегистрирован сам по себе или в качестве члена группы серверов.) Дополнительные сведения о добавлении экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в список «Зарегистрированные серверы» см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="bb69f-110">(The instance can be registered on its own or be a member of a server group.) For more information about how to add an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to Registered Servers, see the following topics:</span></span>  
  
-   [<span data-ttu-id="bb69f-111">Создание или изменение группы серверов (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="bb69f-111">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/register-servers/create-or-edit-a-server-group-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="bb69f-112">Регистрация подключенного сервера (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="bb69f-112">Register a Connected Server &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="bb69f-113">Создание центрального сервера управления и группы сервера (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="bb69f-113">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/register-servers/create-a-central-management-server-and-server-group.md)  
  
 <span data-ttu-id="bb69f-114">Дополнительные сведения о просмотре файлов журналов вне сети программным способом с помощью запросов WMI и WQL см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="bb69f-114">For more information about how to view offline log files programmatically through WMI and WQL queries, see the following topics:</span></span>  
  
-   <span data-ttu-id="bb69f-115">[SqlErrorLogEvent, класс](../wmi-provider-configuration-classes/sqlerrorlogevent-class.md) (В этом разделе рассматривается извлечение значений событий, зарегистрированных в указанном файле журнала.)</span><span class="sxs-lookup"><span data-stu-id="bb69f-115">[SqlErrorLogEvent Class](../wmi-provider-configuration-classes/sqlerrorlogevent-class.md) (This topic shows how to retrieve values for logged events in a specified log file.)</span></span>  
  
-   <span data-ttu-id="bb69f-116">[SqlErrorLogFile, класс](../wmi-provider-configuration-classes/sqlerrorlogfile-class.md) (В этом разделе рассматривается извлечение данных из всех файлов журнала [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в указанном экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="bb69f-116">[SqlErrorLogFile Class](../wmi-provider-configuration-classes/sqlerrorlogfile-class.md) (This topic shows how to retrieve information about all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files on a specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bb69f-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="bb69f-117">Permissions</span></span>  
 <span data-ttu-id="bb69f-118">Для подключения к файлу журнала вне сети необходимы следующие разрешения на локальном и на удаленном компьютерах.</span><span class="sxs-lookup"><span data-stu-id="bb69f-118">To connect to an offline log file, you must have the following permissions on both the local and remote computers:</span></span>  
  
-   <span data-ttu-id="bb69f-119">Доступ для чтения к пространству имен WMI **Root\Microsoft\SqlServer\ComputerManagement12** .</span><span class="sxs-lookup"><span data-stu-id="bb69f-119">Read access to the **Root\Microsoft\SqlServer\ComputerManagement12** WMI namespace.</span></span> <span data-ttu-id="bb69f-120">По умолчанию доступ для чтения задается для всех с помощью разрешения «Включить учетную запись».</span><span class="sxs-lookup"><span data-stu-id="bb69f-120">By default, everyone has read access through the Enable Account permission.</span></span> <span data-ttu-id="bb69f-121">Дополнительные сведения см. в описании процедуры «Проверка разрешений WMI» этого раздела.</span><span class="sxs-lookup"><span data-stu-id="bb69f-121">For more information, see the "To verify WMI permissions" procedure later in this section.</span></span>  
  
-   <span data-ttu-id="bb69f-122">Разрешение на чтение для папки, содержащей файлы журналов ошибок.</span><span class="sxs-lookup"><span data-stu-id="bb69f-122">Read permission to the folder that contains the error log files.</span></span> <span data-ttu-id="bb69f-123">По умолчанию файлы журналов ошибок находятся по следующему пути (где \<*Drive>\* представляет диск, на котором установлен [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], а \<*InstanceName*> является именем экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span><span class="sxs-lookup"><span data-stu-id="bb69f-123">By default the error log files are located in the following path (where \<*Drive>\* represents the drive where you installed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and \<*InstanceName*> is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span></span>  
  
     <span data-ttu-id="bb69f-124">**\<Drive>: \Program Files\Microsoft SQL Server\MSSQL12. \<InstanceName> \MSSQL\Log**</span><span class="sxs-lookup"><span data-stu-id="bb69f-124">**\<Drive>:\Program Files\Microsoft SQL Server\MSSQL12.\<InstanceName>\MSSQL\Log**</span></span>  
  
 <span data-ttu-id="bb69f-125">Для проверки параметров безопасности пространства имен WMI можно использовать оснастку «Элемент управления WMI».</span><span class="sxs-lookup"><span data-stu-id="bb69f-125">To verify WMI namespace security settings, you can use the WMI Control snap-in.</span></span>  
  
#### <a name="to-verify-wmi-permissions"></a><span data-ttu-id="bb69f-126">Проверка разрешений WMI</span><span class="sxs-lookup"><span data-stu-id="bb69f-126">To verify WMI permissions</span></span>  
  
1.  <span data-ttu-id="bb69f-127">Откройте оснастку «Элемент управления WMI».</span><span class="sxs-lookup"><span data-stu-id="bb69f-127">Open the WMI Control snap-in.</span></span> <span data-ttu-id="bb69f-128">Для этого выполните одно из следующих действий в зависимости от операционной системы.</span><span class="sxs-lookup"><span data-stu-id="bb69f-128">To do this, do either of the following, depending on the operating system:</span></span>  
  
    -   <span data-ttu-id="bb69f-129">Нажмите кнопку **Пуск**, введите `wmimgmt.msc` в поле **начать поиск** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="bb69f-129">Click **Start**, type `wmimgmt.msc` in the **Start Search** box, and then press ENTER.</span></span>  
  
    -   <span data-ttu-id="bb69f-130">Нажмите кнопку **Пуск**, выберите команду **выполнить**, введите `wmimgmt.msc` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="bb69f-130">Click **Start**, click **Run**, type `wmimgmt.msc`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="bb69f-131">По умолчанию оснастка «Элемент управления WMI» управляет локальным компьютером.</span><span class="sxs-lookup"><span data-stu-id="bb69f-131">By default, the WMI Control snap-in manages the local computer.</span></span>  
  
     <span data-ttu-id="bb69f-132">Чтобы подключиться к удаленному компьютеру, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bb69f-132">If you want to connect to a remote computer, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="bb69f-133">Щелкните правой кнопкой мыши **Элемент управления WMI (локальный)** и выберите пункт **Подключение к другому компьютеру**.</span><span class="sxs-lookup"><span data-stu-id="bb69f-133">Right-click **WMI Control (Local)**, and then click **Connect to another computer**.</span></span>  
  
    2.  <span data-ttu-id="bb69f-134">В диалоговом окне **Выбор управляемого компьютера** выберите **Другой компьютер**.</span><span class="sxs-lookup"><span data-stu-id="bb69f-134">In the **Change managed computer** dialog box, click **Another computer**.</span></span>  
  
    3.  <span data-ttu-id="bb69f-135">Введите имя удаленного компьютера и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bb69f-135">Enter the remote computer name, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="bb69f-136">Щелкните правой кнопкой мыши **элемент управления WMI (локальный)** или **элемент управления WMI (***имя_удаленного_компьютера***)** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="bb69f-136">Right-click **WMI Control (Local)** or **WMI Control (***RemoteComputerName***)**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="bb69f-137">В диалоговом окне **Свойства: элемент управления WMI** перейдите на вкладку **Безопасность** .</span><span class="sxs-lookup"><span data-stu-id="bb69f-137">In the **WMI Control Properties** dialog box, click the **Security** tab.</span></span>  
  
5.  <span data-ttu-id="bb69f-138">В дереве пространства имен найдите и выберите следующее пространство имен:</span><span class="sxs-lookup"><span data-stu-id="bb69f-138">In the namespace tree, locate and then click the following namespace:</span></span>  
  
     <span data-ttu-id="bb69f-139">**Root\Microsoft\SqlServer\ComputerManagement10**</span><span class="sxs-lookup"><span data-stu-id="bb69f-139">**Root\Microsoft\SqlServer\ComputerManagement10**</span></span>  
  
6.  <span data-ttu-id="bb69f-140">Перейдите на вкладку **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="bb69f-140">Click **Security**.</span></span>  
  
7.  <span data-ttu-id="bb69f-141">Убедитесь в том, что у учетной записи, которая будет использоваться, имеется разрешение **Включить учетную запись** .</span><span class="sxs-lookup"><span data-stu-id="bb69f-141">Make sure that the account that will be used has the **Enable Account** permission.</span></span> <span data-ttu-id="bb69f-142">Это разрешение предоставляет доступ на чтение к объектам WMI.</span><span class="sxs-lookup"><span data-stu-id="bb69f-142">This permission allows Read access to WMI objects.</span></span>  
  
### <a name="view-log-files"></a><span data-ttu-id="bb69f-143">Просмотр файлов журнала</span><span class="sxs-lookup"><span data-stu-id="bb69f-143">View Log Files</span></span>  
 <span data-ttu-id="bb69f-144">В следующей процедуре демонстрируется просмотр файлов журнала вне сети с помощью списка «Зарегистрированные серверы».</span><span class="sxs-lookup"><span data-stu-id="bb69f-144">The following procedure shows how to view offline log files through Registered Servers.</span></span> <span data-ttu-id="bb69f-145">Для этой процедуры предполагается следующее.</span><span class="sxs-lookup"><span data-stu-id="bb69f-145">The procedure assumes the following:</span></span>  
  
 <span data-ttu-id="bb69f-146">Экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , к которому нужно подключиться, уже зарегистрирован в списке «Зарегистрированные серверы».</span><span class="sxs-lookup"><span data-stu-id="bb69f-146">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to connect to is already registered in Registered Servers.</span></span>  
  
##### <a name="to-view-log-files-for-instances-that-are-offline"></a><span data-ttu-id="bb69f-147">Просмотр файлов журнала для экземпляров вне сети</span><span class="sxs-lookup"><span data-stu-id="bb69f-147">To view log files for instances that are offline</span></span>  
  
1.  <span data-ttu-id="bb69f-148">Если необходимо просмотреть файлы журнала вне сети на локальном экземпляре, среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] необходимо запустить с повышенными разрешениями.</span><span class="sxs-lookup"><span data-stu-id="bb69f-148">If you want to view offline log files on a local instance, make sure that you start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] with elevated permissions.</span></span> <span data-ttu-id="bb69f-149">Для этого при запуске среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]щелкните правой кнопкой мыши **SQL Server Management Studio**и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="bb69f-149">To do this, when you start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click **SQL Server Management Studio**, and then click **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="bb69f-150">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]в меню **Вид** выберите пункт **Зарегистрированные серверы**.</span><span class="sxs-lookup"><span data-stu-id="bb69f-150">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
3.  <span data-ttu-id="bb69f-151">В дереве консоли найдите экземпляр, на котором нужно просмотреть файлы вне сети.</span><span class="sxs-lookup"><span data-stu-id="bb69f-151">In the console tree, locate the instance on which you want to view the offline files.</span></span>  
  
4.  <span data-ttu-id="bb69f-152">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="bb69f-152">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="bb69f-153">Если экземпляр вложен в **Группы локальных серверов**, разверните **Группы локальных серверов**, затем группу серверов (если экземпляр является членом группы), щелкните экземпляр правой кнопкой мыши и выберите пункт **Просмотр журнала SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bb69f-153">If the instance is under **Local Server Groups**, expand **Local Server Groups**, expand the server group (if the instance is a member of a group), right-click the instance, and then click **View SQL Server Log**.</span></span>  
  
    -   <span data-ttu-id="bb69f-154">Если экземпляр сам является центральным сервером управления, разверните **Центральные серверы управления**, щелкните правой кнопкой мыши экземпляр, наведите указатель на пункт **Действия центрального сервера управления**и выберите пункт **Просмотр журнала SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bb69f-154">If the instance is the Central Management Server itself, expand **Central Management Servers**, right-click the instance, point to **Central Management Server Actions**, and then click **View SQL Server Log**.</span></span>  
  
    -   <span data-ttu-id="bb69f-155">Если экземпляр вложен в **Центральные серверы управления**, разверните **Центральные серверы управления**, затем разверните центральный сервер управления, щелкните экземпляр правой кнопкой мыши (или разверните группу серверов и щелкните экземпляр правой кнопкой мыши), а затем выберите пункт **Просмотр журнала SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bb69f-155">If the instance is under **Central Management Servers**, expand **Central Management Servers**, expand the Central Management Server, right-click the instance (or expand a server group and right-click the instance), and then click **View SQL Server Log**.</span></span>  
  
5.  <span data-ttu-id="bb69f-156">При подключении к локальному экземпляру соединение устанавливается с использованием учетных данных текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="bb69f-156">If you are connecting to a local instance, the connection is made using the current user credentials.</span></span>  
  
     <span data-ttu-id="bb69f-157">При соединении с удаленным экземпляром в диалоговом окне **Средство просмотра журнала — подключиться как** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="bb69f-157">If you are connecting to a remote instance, in the **Log File Viewer - Connect As** dialog box, do either of the following:</span></span>  
  
    -   <span data-ttu-id="bb69f-158">Чтобы подключиться от имени текущего пользователя, снимите флажок **Подключиться от имени другого пользователя** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bb69f-158">To connect as the current user, make sure that the **Connect as another user** check box is cleared, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="bb69f-159">Чтобы подключиться от имени другого пользователя, установите флажок **Подключиться от имени другого пользователя** и нажмите кнопку **Задать пользователя**.</span><span class="sxs-lookup"><span data-stu-id="bb69f-159">To connect as another user, select the **Connect as another user** check box, and then click **Set User**.</span></span> <span data-ttu-id="bb69f-160">При появлении запроса введите учетные данные пользователя (указав имя пользователя в формате *имя_домена*\\*имя_пользователя*) и дважды нажмите кнопку **ОК**, чтобы подключиться.</span><span class="sxs-lookup"><span data-stu-id="bb69f-160">When you are prompted, enter the user credentials (with the user name in the format *domain_name*\\*user_name*), click **OK**, and then click **OK** again to connect.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bb69f-161">Если файлы журналов загружаются слишком долго, можно нажать кнопку **Стоп** на панели инструментов средства просмотра файлов журналов.</span><span class="sxs-lookup"><span data-stu-id="bb69f-161">If the log files take too long to load, you can click **Stop** on the Log File Viewer toolbar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb69f-162">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb69f-162">See Also</span></span>  
 [<span data-ttu-id="bb69f-163">Средство просмотра файлов журнала</span><span class="sxs-lookup"><span data-stu-id="bb69f-163">Log File Viewer</span></span>](log-file-viewer.md)  
  
  
