---
title: Задание свойств службы Integration Services | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services service, configuring
- Integration Services service, properties
ms.assetid: 3a8ad546-0f58-4b31-ab56-58d6313b1098
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 055eadd9a1d59c59dd40675b142eae480763f6f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751263"
---
# <a name="set-the-properties-of-the-integration-services-service"></a><span data-ttu-id="0c968-102">задать свойства службы Integration Services</span><span class="sxs-lookup"><span data-stu-id="0c968-102">Set the Properties of the Integration Services Service</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="0c968-103">В данном разделе описывается компонент [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] — служба Windows для управления пакетами служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0c968-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="0c968-104">поддерживает эту службу для обеспечения обратной совместимости с более ранними версиями служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c968-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="0c968-105">Начиная с [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], на сервере служб Integration Services можно управлять пакетами.</span><span class="sxs-lookup"><span data-stu-id="0c968-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="0c968-106">Служба [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] управляет и отслеживает пакеты в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c968-106">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages and monitors packages in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="0c968-107">При первой установке [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Служба запускается, а в качестве типа запуска службы устанавливается значение автоматически.</span><span class="sxs-lookup"><span data-stu-id="0c968-107">When you first install [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is started and the startup type of the service is set to automatic.</span></span>  
  
 <span data-ttu-id="0c968-108">После установки службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] можно задавать свойства службы, используя диспетчер конфигурации SQL Server или оснастку Services консоли MMC.</span><span class="sxs-lookup"><span data-stu-id="0c968-108">After the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service has been installed, you can set the properties of the service by using either SQL Server Configuration Manager or the Services MMC snap-in.</span></span>  
  
 <span data-ttu-id="0c968-109">Чтобы настроить другие важные функции службы, включая местоположения, в которых осуществляется хранение и управление пакетами, необходимо внести изменения в файл конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="0c968-109">To configure other important features of the service, including the locations where it stores and manages packages, you must modify the configuration file of the service.</span></span> <span data-ttu-id="0c968-110">Дополнительные сведения см. в разделе [Настройка служб Integration Services (службы SSIS)](service/integration-services-service-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="0c968-110">For more information, see [Configuring the Integration Services Service &#40;SSIS Service&#41;](service/integration-services-service-ssis-service.md).</span></span>  
  
### <a name="to-set-properties-of-the-integration-services-service-by-using-sql-server-configuration-manager"></a><span data-ttu-id="0c968-111">Определение свойств службы Integration Services с использованием диспетчера конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="0c968-111">To set properties of the Integration Services service by using SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="0c968-112">В меню **Пуск** укажите **Все программы**, **Microsoft SQL Server**, **Средства настройки**и выберите пункт **Диспетчер конфигурации SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0c968-112">On the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="0c968-113">В оснастке **Диспетчер конфигурации SQL Server** в списке служб найдите **Службы SQL Server Integration Services** , щелкните правой кнопкой мыши **Службы SQL Server Integration Services**и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="0c968-113">In the **SQL Server Configuration Manager** snap-in, locate **SQL Server Integration Services** in the list of services, right-click **SQL Server Integration Services**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="0c968-114">В диалоговом окне " **свойства SQL Server Integration Services** " можно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0c968-114">In the **SQL Server Integration Services Properties** dialog box you can do the following:</span></span>  
  
    -   <span data-ttu-id="0c968-115">Перейдите на вкладку **Вход** , чтобы просмотреть учетные данные, такие как имя учетной записи.</span><span class="sxs-lookup"><span data-stu-id="0c968-115">Click the **Log On** tab to view the logon information such as the account name.</span></span>  
  
    -   <span data-ttu-id="0c968-116">Перейдите на вкладку **Служба** , чтобы просмотреть сведения о службе, такие как имя главного компьютера, и указать режим запуска службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0c968-116">Click the **Service** tab to view information about the service such as the name of the host computer and to specify the start mode of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="0c968-117">На вкладке **Дополнительно** сведений о службе [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] не содержится.</span><span class="sxs-lookup"><span data-stu-id="0c968-117">The **Advanced** tab contains no information for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span>  
  
4.  <span data-ttu-id="0c968-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0c968-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="0c968-119">Чтобы закрыть оснастку **Диспетчер конфигурации SQL Server** , в меню **Файл** выберите пункт **Выход** .</span><span class="sxs-lookup"><span data-stu-id="0c968-119">On the **File** menu, click **Exit** to close the **SQL Server Configuration Manager** snap-in.</span></span>  
  
### <a name="to-set-properties-of-the-integration-services-service-by-using-services"></a><span data-ttu-id="0c968-120">Определение свойств службы Integration Services с использованием оснастки Services</span><span class="sxs-lookup"><span data-stu-id="0c968-120">To set properties of the Integration Services service by using Services</span></span>  
  
1.  <span data-ttu-id="0c968-121">При использовании классического вида **панели управления**щелкните **Администрирование**; если используется вид по категориям, щелкните **Производительность и обслуживание** , а затем **Администрирование**.</span><span class="sxs-lookup"><span data-stu-id="0c968-121">In **Control Panel**, if you are using Classic View, click **Administrative Tools**, or, if you are using Category View, click **Performance and Maintenance** and then click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="0c968-122">Щелкните **Службы**.</span><span class="sxs-lookup"><span data-stu-id="0c968-122">Click **Services**.</span></span>  
  
3.  <span data-ttu-id="0c968-123">В оснастке **Службы** в списке служб найдите **SQL Server Integration Services** , щелкните правой кнопкой мыши **SQL Server Integration Services**и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="0c968-123">In the **Services** snap-in, locate **SQL Server Integration Services** in the list of services, right-click **SQL Server Integration Services**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="0c968-124">В диалоговом окне **Свойства служб SQL Server Integration Services** можно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0c968-124">In the **SQL Server Integration Services Properties** dialog box, you can do the following:</span></span>  
  
    -   <span data-ttu-id="0c968-125">Перейдите на вкладку **Общие** . Чтобы включить службу, выберите ручной или автоматический тип запуска.</span><span class="sxs-lookup"><span data-stu-id="0c968-125">Click the **General** tab. To enable the service, select either the manual or automatic startup type.</span></span> <span data-ttu-id="0c968-126">Чтобы выключить службу, выберите «Отключено» в поле **Тип запуска** .</span><span class="sxs-lookup"><span data-stu-id="0c968-126">To disable the service, select Disable in the **Startup type** box.</span></span> <span data-ttu-id="0c968-127">Выбор варианта «Отключено» не останавливает службу, если она работает в данный момент.</span><span class="sxs-lookup"><span data-stu-id="0c968-127">Selecting Disable does not stop the service if it is currently running.</span></span>  
  
         <span data-ttu-id="0c968-128">Если служба уже включена, можно нажать кнопку **Стоп** для остановки службы или **Пуск** для запуска службы.</span><span class="sxs-lookup"><span data-stu-id="0c968-128">If the service is already enabled, you can click **Stop** to stop the service, or click **Start** to start the service.</span></span>  
  
    -   <span data-ttu-id="0c968-129">Перейдите на вкладку **Вход** , чтобы просмотреть или изменить учетные данные.</span><span class="sxs-lookup"><span data-stu-id="0c968-129">Click the **Log On** tab to view or edit the logon information.</span></span>  
  
    -   <span data-ttu-id="0c968-130">Перейдите на вкладку **Восстановление** для просмотра реакции компьютера по умолчанию на ошибку в работе службы.</span><span class="sxs-lookup"><span data-stu-id="0c968-130">Click the **Recovery** tab to view the default computer responses to service failure.</span></span> <span data-ttu-id="0c968-131">Эти параметры можно изменять в соответствии с требованиями среды.</span><span class="sxs-lookup"><span data-stu-id="0c968-131">You can modify these options to suit your environment.</span></span>  
  
    -   <span data-ttu-id="0c968-132">Перейдите на вкладку **Зависимости** для просмотра перечня зависимых служб.</span><span class="sxs-lookup"><span data-stu-id="0c968-132">Click the **Dependencies** tab to view a list of dependent services.</span></span> <span data-ttu-id="0c968-133">У служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] нет зависимостей.</span><span class="sxs-lookup"><span data-stu-id="0c968-133">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service has no dependencies.</span></span>  
  
5.  <span data-ttu-id="0c968-134">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0c968-134">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="0c968-135">При необходимости, если тип запуска ручной или автоматический, можно щелкнуть правой кнопкой мыши службы **SQL Server Integration Services** и выбрать пункт **Пуск, Стоп или Перезапустить**.</span><span class="sxs-lookup"><span data-stu-id="0c968-135">Optionally, if the startup type is Manual or Automatic, you can right-click **SQL Server Integration Services** and click **Start, Stop, or Restart**.</span></span>  
  
7.  <span data-ttu-id="0c968-136">Чтобы закрыть оснастку **Службы** , в меню **Файл** выберите пункт **Выход** .</span><span class="sxs-lookup"><span data-stu-id="0c968-136">On the **File** menu, click **Exit** to close the **Services** snap-in.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c968-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="0c968-137">See Also</span></span>  
 [<span data-ttu-id="0c968-138">Управление службой Integration Services</span><span class="sxs-lookup"><span data-stu-id="0c968-138">Manage the Integration Services Service</span></span>](../../2014/integration-services/manage-the-integration-services-service.md)  
  
  
