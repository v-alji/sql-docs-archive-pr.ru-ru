---
title: Настройка служб IIS 7 для веб-синхронизации | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- IIS 7 server configuration [SQL Server replication]
- Web synchronization, IIS 7 servers
ms.assetid: c201fe2c-0a76-44e5-a233-05e14cd224a6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 65b5aa1ea0d314a9675b1c1b90b688d2990e6d24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669393"
---
# <a name="configure-iis-7-for-web-synchronization"></a><span data-ttu-id="5fbc9-102">Настройка сервера IIS 7 для веб-синхронизации</span><span class="sxs-lookup"><span data-stu-id="5fbc9-102">Configure IIS 7 for Web Synchronization</span></span>
  <span data-ttu-id="5fbc9-103">В этой статье описывается процесс настройки вручную служб [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) версии 7 и более поздней, которые будут использоваться при веб-синхронизации для репликации слиянием.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-103">The procedures in this topic will guide you through the process of manually configuring [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) version 7 and higher for use with Web synchronization for merge replication.</span></span> 
  
 <span data-ttu-id="5fbc9-104">Настройка служб IIS 7 является первым из трех шагов, которые необходимо выполнить для включения веб-синхронизации.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-104">Configuring IIS 7 is the first of three steps needed to enable Web synchronization.</span></span>  
  
 <span data-ttu-id="5fbc9-105">Обзор процесса настройки см. в статье [Настройка веб-синхронизации](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="5fbc9-105">For an overview of the entire configuration process, see [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5fbc9-106">Убедитесь в том, что приложение использует только [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] или более позднюю версию, а более ранние версии [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] на IIS-сервере не установлены.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-106">Make sure that your application uses only [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] or later versions, and that earlier versions of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] are not installed on the IIS server.</span></span> <span data-ttu-id="5fbc9-107">Более ранние версии платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] могут вызывать ошибки, например: "Недопустимый формат сообщения во время веб-синхронизации.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-107">Earlier versions of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] can cause errors, such as: "The format of a message during Web synchronization was invalid.</span></span> <span data-ttu-id="5fbc9-108">Убедитесь в том, что компоненты репликации на веб-сервере настроены правильно».</span><span class="sxs-lookup"><span data-stu-id="5fbc9-108">Ensure that replication components are properly configured at the Web server."</span></span>  
  
 <span data-ttu-id="5fbc9-109">Чтобы использовать веб-синхронизацию, необходимо настроить службы IIS 7, выполнив следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-109">To use Web synchronization, you must configure IIS 7 by completing the following steps.</span></span> <span data-ttu-id="5fbc9-110">Каждый шаг подробно описан в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-110">Each step is described in detail in this topic.</span></span>  
  
1.  <span data-ttu-id="5fbc9-111">Установите и настройте средство прослушивания репликации [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на компьютере, на котором запущены службы IIS.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-111">Install and configure the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener on the computer that is running IIS.</span></span>  
  
2.  <span data-ttu-id="5fbc9-112">Настройте протокол SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="5fbc9-112">Configure Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="5fbc9-113">Протокол SSL необходим для взаимодействия сервера IIS и всех подписчиков.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-113">SSL is required for communication between IIS and all subscribers.</span></span>  
  
3.  <span data-ttu-id="5fbc9-114">Настройка проверки подлинности служб IIS</span><span class="sxs-lookup"><span data-stu-id="5fbc9-114">Configure IIS authentication.</span></span>  
  
4.  <span data-ttu-id="5fbc9-115">Настройте учетную запись и задайте разрешения для средства прослушивания репликации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-115">Configure an account and set permissions for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener.</span></span>  
  
## <a name="installing-the-sql-server-replication-listener"></a><span data-ttu-id="5fbc9-116">Установка средства прослушивания репликации SQL Server</span><span class="sxs-lookup"><span data-stu-id="5fbc9-116">Installing the SQL Server Replication Listener</span></span>  

<span data-ttu-id="5fbc9-117">Веб-синхронизация поддерживается в IIS, начиная с версии 5.0.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-117">Web synchronization is supported on IIS, beginning with version 5.0.</span></span> <span data-ttu-id="5fbc9-118">Мастер настройки веб-синхронизации служб IIS версии 5 и 6 не поддерживается в версии служб IIS 7.0 и более поздних.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-118">The Configure Web Synchronization Wizard of IIS version 5 and 6, is not available with IIS version 7.0 and higher.</span></span> <span data-ttu-id="5fbc9-119">**Начиная с SQL Server 2012, чтобы использовать компонент веб-синхронизации на сервере IIS, необходимо установить SQL Server с поддержкой репликации. Это может быть бесплатный выпуск SQL Server Express.**</span><span class="sxs-lookup"><span data-stu-id="5fbc9-119">**Beginning with SQL Server 2012, to use the web sync component on IIS server, you should install SQL Server with replication. This can be the free SQL Server Express edition.**</span></span>
  
#### <a name="to-install-and-configure-the-sql-server-replication-listener"></a><span data-ttu-id="5fbc9-120">Установка и настройка средства прослушивания репликации SQL Server</span><span class="sxs-lookup"><span data-stu-id="5fbc9-120">To install and configure the SQL Server Replication Listener</span></span>  
  
1. <span data-ttu-id="5fbc9-121">Установите репликацию SQL Server на компьютере IIS.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-121">Install SQL Server replication on the IIS computer.</span></span>

2.  <span data-ttu-id="5fbc9-122">Создайте на компьютере, где запущены службы IIS, новый каталог для файла replisapi.dll.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-122">Create a new file directory for replisapi.dll on the computer that is running IIS.</span></span> <span data-ttu-id="5fbc9-123">Этот каталог можно создать в любом месте, но рекомендуется разместить его в каталоге \<*drive*>:\Inetpub.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-123">You can create the directory wherever you want, but we recommend that you create the directory under the \<*drive*>:\Inetpub directory.</span></span> <span data-ttu-id="5fbc9-124">Например, создайте каталог \<*drive*>:\Inetpub\SQLReplication\\.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-124">For example, create the directory \<*drive*>:\Inetpub\SQLReplication\\.</span></span>  
  
3.  <span data-ttu-id="5fbc9-125">Скопируйте файл replisapi.dll из каталога [!INCLUDE[ssInstallPathVar](../../includes/ssinstallpathvar-md.md)]com\ в каталог с файлами, созданный на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-125">Copy replisapi.dll from the directory [!INCLUDE[ssInstallPathVar](../../includes/ssinstallpathvar-md.md)]com\ to the file directory that you created in step 1.</span></span>  
  
4.  <span data-ttu-id="5fbc9-126">Зарегистрируйте файл replisapi.dll:</span><span class="sxs-lookup"><span data-stu-id="5fbc9-126">Register replisapi.dll:</span></span>  
  
    1.  <span data-ttu-id="5fbc9-127">Нажмите кнопку **Пуск**, затем щелкните **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-127">Click **Start**, and then click **Run**.</span></span> <span data-ttu-id="5fbc9-128">В поле **Открыть** введите `cmd` , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-128">In the **Open** box, enter `cmd`, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="5fbc9-129">В каталоге, созданном в шаге 1, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5fbc9-129">In the directory created in step 1, execute the following command:</span></span>  
  
         `regsvr32 replisapi.dll`  
  
5.  <span data-ttu-id="5fbc9-130">Создайте новый веб-сайт для репликации или воспользуйтесь уже существующим.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-130">Create a new Web site for replication or use an existing site.</span></span> <span data-ttu-id="5fbc9-131">Во время синхронизации компоненты репликации будут обращаться к этому веб-сайту.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-131">This Web site will be accessed by replication components during synchronization.</span></span> <span data-ttu-id="5fbc9-132">В процедурах, описываемых в этом разделе, будет использоваться веб-сайт по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-132">Procedures in this topic will assume the Default Web Site.</span></span> <span data-ttu-id="5fbc9-133">Дополнительные сведения о том, как создать веб-сайт, содержатся в документации по службам IIS.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-133">For more information about how to create Web sites, see the IIS documentation</span></span>  
  
6.  <span data-ttu-id="5fbc9-134">Создайте виртуальный каталог в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-134">Create a virtual directory in IIS.</span></span> <span data-ttu-id="5fbc9-135">Виртуальный каталог должен быть создан на сайте, созданном в шаге 4, и сопоставлен с каталогом, созданным в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-135">The virtual directory should be created under the Web site that you created in step 4 and map it to the directory created in step 1.</span></span> <span data-ttu-id="5fbc9-136">Разрешения для этого каталога должны быть максимально ограничены.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-136">Be as restrictive as possible when you assign permissions to this directory.</span></span> <span data-ttu-id="5fbc9-137">Необходимо выбрать как минимум разрешения **Чтение** и **Выполнение** .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-137">You must select at least **Read** and **Execute** permissions.</span></span>  
  
    1.  <span data-ttu-id="5fbc9-138">В **диспетчере служб IIS**на панели **Соединения** щелкните правой кнопкой мыши **Веб-сайт по умолчанию**и выберите **Добавить виртуальный каталог**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-138">In **Internet Information Services (IIS) Manager**, in the **Connections** pane, right-click **Default Web Site**, and then select **Add Virtual Directory**.</span></span>  
  
    2.  <span data-ttu-id="5fbc9-139">В качестве **псевдонима**введите `SQLReplication` .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-139">For **Alias**, enter `SQLReplication`.</span></span>  
  
    3.  <span data-ttu-id="5fbc9-140">В поле **Физический путь** введите **\<drive>:\Inetpub\SQLReplication\\** , а затем нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-140">For **Physical Path**, enter **\<drive>:\Inetpub\SQLReplication\\**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="5fbc9-141">Установите в настройках служб IIS разрешение выполнять файл replisapi.dll.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-141">Configure IIS to enable replisapi.dll to execute.</span></span>  
  
    1.  <span data-ttu-id="5fbc9-142">В **диспетчере служб IIS**щелкните **Веб-сайт по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-142">In **Internet Information Services (IIS) Manager**, click **Default Web Site**.</span></span>  
  
    2.  <span data-ttu-id="5fbc9-143">На центральной панели выберите **Сопоставления обработчика**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-143">In the center pane, click **Handler Mappings**.</span></span>  
  
    3.  <span data-ttu-id="5fbc9-144">На панели **Действия** выберите **Добавить сопоставление модуля**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-144">In the **Actions** pane, click **Add Module Mapping**.</span></span>  
  
    4.  <span data-ttu-id="5fbc9-145">В качестве пути **запроса** введите `replisapi.dll` .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-145">For **Request** Path, enter `replisapi.dll`.</span></span>  
  
    5.  <span data-ttu-id="5fbc9-146">В раскрывающемся списке **Модуль** выберите **IsapiModule**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-146">From the **Module** drop-down list, select **IsapiModule**.</span></span>  
  
    6.  <span data-ttu-id="5fbc9-147">В поле **Исполняемый файл** введите **\<drive>:\Inetpub\SQLReplication\replisapi.dll**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-147">For **Executable**, enter **\<drive>:\Inetpub\SQLReplication\replisapi.dll**.</span></span>  
  
    7.  <span data-ttu-id="5fbc9-148">Для параметра **Имя** введите `Replisapi`.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-148">For **Name**, enter `Replisapi`.</span></span>  
  
    8.  <span data-ttu-id="5fbc9-149">Нажмите кнопку **Ограничения запроса** , перейдите на вкладку **Доступ** и щелкните **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-149">Click the **Request Restrictions** button, click the **Access** tab, and then click **Execute**.</span></span>  
  
    9. <span data-ttu-id="5fbc9-150">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Ограничения запроса** , а затем повторно нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Добавить сопоставление модуля** .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-150">Click **OK** to close the **Request Restrictions** dialog box, and then click **OK** again to close the **Add Module Mapping** dialog box.</span></span> <span data-ttu-id="5fbc9-151">При запросе на разрешение расширений ISAPI нажмите **Да** , чтобы добавить расширение.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-151">When you are prompted to allow the ISAPI extension, click **Yes** to add the extension.</span></span>  
  
    10. <span data-ttu-id="5fbc9-152">Убедитесь, что файл Replisapi.dll включен в список **Включены** сопоставлений обработчика.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-152">Verify that Replisapi.dll is listed under the **Enabled** handler mappings.</span></span> <span data-ttu-id="5fbc9-153">Если он находится в списке **Выключены** , щелкните правой кнопкой мыши Replisapi и выберите **Изменить разрешения функции**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-153">If it is in the **Disabled** list, right-click the Replisapi entry and then click **Edit Feature Permissions**.</span></span> <span data-ttu-id="5fbc9-154">Установите флажок **Выполнить** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-154">Check the **Execute** box, and then click **OK**.</span></span>  
  
## <a name="configuring-iis-authentication"></a><span data-ttu-id="5fbc9-155">Настройка проверки подлинности служб IIS</span><span class="sxs-lookup"><span data-stu-id="5fbc9-155">Configuring IIS Authentication</span></span>  
 <span data-ttu-id="5fbc9-156">При подключении компьютеров подписчиков к серверу IIS службы IIS должны проверить подлинность подключаемых подписчиков перед предоставлением им доступа к ресурсам и процессам.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-156">When subscriber computers connect to IIS, IIS must authenticate the subscribers before they can access resources and processes.</span></span> <span data-ttu-id="5fbc9-157">Проверка подлинности может выполняться для всего веб-сайта или для созданного виртуального каталога.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-157">Authentication can be applied to the whole Web site or to the virtual directory that you created.</span></span>  
  
 <span data-ttu-id="5fbc9-158">Рекомендуется использовать процедуру обычной проверки подлинности в сочетании с протоколом SSL.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-158">We recommend that you use Basic Authentication with SSL.</span></span> <span data-ttu-id="5fbc9-159">Протокол SSL должен использоваться вне независимости от типа применяемой проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-159">SSL is required, regardless of the type of authentication that is used.</span></span>  
  
 <span data-ttu-id="5fbc9-160">Рекомендуется использовать процедуру обычной проверки подлинности в сочетании с протоколом SSL.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-160">We recommend that you use Basic Authentication with SSL.</span></span> <span data-ttu-id="5fbc9-161">Протокол SSL должен использоваться вне независимости от типа применяемой проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-161">SSL is required, regardless of the type of authentication that is used.</span></span>  
  
#### <a name="to-configure-iis-authentication"></a><span data-ttu-id="5fbc9-162">Настройка проверки подлинности служб IIS</span><span class="sxs-lookup"><span data-stu-id="5fbc9-162">To Configure IIS Authentication</span></span>  
  
1.  <span data-ttu-id="5fbc9-163">В **диспетчере служб IIS**щелкните **Веб-сайт по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-163">In **Internet Information Services (IIS) Manager**, click **Default Web Site**.</span></span>  
  
2.  <span data-ttu-id="5fbc9-164">На средней панели дважды щелкните **Проверка подлинности**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-164">In the middle pane, double-click **Authentication**.</span></span>  
  
3.  <span data-ttu-id="5fbc9-165">Щелкните правой кнопкой мыши «Анонимная проверка подлинности» и выберите «Выключить».</span><span class="sxs-lookup"><span data-stu-id="5fbc9-165">Right-click Anonymous Authentication, and then choose Disable.</span></span>  
  
4.  <span data-ttu-id="5fbc9-166">Щелкните правой кнопкой мыши «Обычная проверка подлинности» и выберите «Включить».</span><span class="sxs-lookup"><span data-stu-id="5fbc9-166">Right-click Basic Authentication, and then choose Enable.</span></span>  
  
## <a name="configuring-secure-sockets-layer"></a><span data-ttu-id="5fbc9-167">Настройка протокола SSL</span><span class="sxs-lookup"><span data-stu-id="5fbc9-167">Configuring Secure Sockets Layer</span></span>  
 <span data-ttu-id="5fbc9-168">Чтобы настроить протокол SSL, укажите сертификат, который будет использоваться компьютером, на котором запущены службы IIS.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-168">To configure SSL, specify a certificate to be used by the computer running IIS.</span></span> <span data-ttu-id="5fbc9-169">Веб-синхронизация для репликации слиянием поддерживает использование сертификатов сервера, но не клиентских.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-169">Web synchronization for merge replication supports using server certificates, but not client certificates.</span></span> <span data-ttu-id="5fbc9-170">Чтобы настроить службы IIS для развертывания, необходимо вначале получить сертификат из центра сертификации (certification authority, CA).</span><span class="sxs-lookup"><span data-stu-id="5fbc9-170">To configure IIS for deployment, you must first obtain a certificate from a certification authority (CA).</span></span> <span data-ttu-id="5fbc9-171">Дополнительные сведения о сертификатах см. в документации по службам IIS.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-171">For more information about certificates, see the IIS documentation.</span></span>  
  
 <span data-ttu-id="5fbc9-172">После установки сертификата необходимо связать сертификат с веб-сайтом, который используется веб-синхронизацией.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-172">After you install the certificate, you must associate the certificate with the Web site that is used by Web synchronization.</span></span> <span data-ttu-id="5fbc9-173">При отладке можно указать самозаверяющий сертификат.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-173">For development and testing, you can specify a self-signed certificate.</span></span> <span data-ttu-id="5fbc9-174">С помощью служб IIS 7 можно создать сертификат и зарегистрировать его на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-174">IIS 7 can create a certificate for you and register it on your computer.</span></span>  
  
 <span data-ttu-id="5fbc9-175">Различие развертывания в рабочей среде и процедуры, описанной здесь, заключается в том, что при проверке в рабочей среде необходимо использовать сертификат, выданный центром сертификации, а не самозаверяющий сертификат.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-175">The difference between deploying for production and the procedures given here is that in production and pre-production testing, you would use a certificate issued by a CA instead of a self-signed certificate.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5fbc9-176">В рабочей среде использовать самозаверяющие сертификаты не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-176">A self-signed certificate is not recommended for a production installation.</span></span> <span data-ttu-id="5fbc9-177">Самозаверяющие сертификаты не безопасны.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-177">Self-signed certificates are not secure.</span></span> <span data-ttu-id="5fbc9-178">Самозаверяющие сертификаты следует использовать только при разработке и отладке.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-178">Use self-signed certificates for development and testing only.</span></span>  
  
 <span data-ttu-id="5fbc9-179">Для настройки протокола SSL следует выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-179">To configure SSL, you will perform the following steps:</span></span>  
  
1.  <span data-ttu-id="5fbc9-180">Настроить веб-сайт для принятия только SSL и игнорирование сертификатов клиента.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-180">Configure the Web site to require SSL and ignore client certificates.</span></span>  
  
2.  <span data-ttu-id="5fbc9-181">Получить сертификат в центре сертификации или создать самозаверяющий сертификат.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-181">Obtain a certificate from a CA or create a self-signed certificate.</span></span>  
  
3.  <span data-ttu-id="5fbc9-182">Выполнить привязку сертификата к веб-сайту репликации.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-182">Bind the certificate to the replication Web site.</span></span>  
  
#### <a name="to-require-ssl-security-for-a-web-site"></a><span data-ttu-id="5fbc9-183">Настройка проверки безопасности с помощью SSL для веб-сайта</span><span class="sxs-lookup"><span data-stu-id="5fbc9-183">To require SSL security for a Web site</span></span>  
  
1.  <span data-ttu-id="5fbc9-184">В **диспетчере служб IIS**разверните узел локального сервера и выберите **Веб-сайт по умолчанию** (или используемый веб-сайт синхронизации, если это не веб-сайт по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="5fbc9-184">In **Internet Information Services (IIS) Manager**, expand the local server node, and then click the **Default Web Site** (or your Web synchronization site if it is different from the default Web site).</span></span>  
  
2.  <span data-ttu-id="5fbc9-185">На центральной панели дважды щелкните **Параметры SSL**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-185">In the middle pane, double-click **SSL Settings**.</span></span>  
  
3.  <span data-ttu-id="5fbc9-186">Выберите параметр **Требовать SSL** .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-186">Check the **Require SSL** option.</span></span> <span data-ttu-id="5fbc9-187">Убедитесь, что в области **Клиентские сертификаты**выбран параметр **Игнорировать** .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-187">Under **Client certificates**, verify that the **Ignore** button is selected.</span></span>  
  
#### <a name="to-create-a-self-signed-certificate-for-testing"></a><span data-ttu-id="5fbc9-188">Создание самозаверяющего сертификата для тестирования</span><span class="sxs-lookup"><span data-stu-id="5fbc9-188">To create a self-signed certificate for testing</span></span>  
  
1.  <span data-ttu-id="5fbc9-189">В **диспетчере служб IIS**разверните узел локального сервера, затем на центральной панели дважды щелкните **Сертификаты сервера**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-189">In **Internet Information Services (IIS) Manager**, click the local server node, and then in the center pane, double-click on **Server Certificates**.</span></span>  
  
2.  <span data-ttu-id="5fbc9-190">На панели **Действия** выберите **Создать самозаверяющий сертификат**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-190">In the **Actions** pane, click **Create Self-Signed Certificate**.</span></span>  
  
3.  <span data-ttu-id="5fbc9-191">В диалоговом окне **Создать самозаверяющий сертификат** введите имя сертификата и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-191">In the **Create Self-Signed Certificate** dialog box, enter a name for the certificate, and then click **OK**.</span></span>  
  
###### <a name="to-bind-a-certificate-to-a-web-site"></a><span data-ttu-id="5fbc9-192">Привязка сертификата к веб-сайту</span><span class="sxs-lookup"><span data-stu-id="5fbc9-192">To bind a certificate to a Web site</span></span>  
  
1.  <span data-ttu-id="5fbc9-193">На панели **Соединения** выберите **Веб-сайт по умолчанию** (или используемый веб-сайт синхронизации, если это не веб-сайт по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="5fbc9-193">In the **Connections** pane, click the **Default Web Site** (or your Web synchronization site, if it is different from the default Web site).</span></span>  
  
2.  <span data-ttu-id="5fbc9-194">На панели **Действия** выберите **Привязки**и щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-194">In the **Actions** pane, click **Bindings**, and then click **Add**.</span></span> <span data-ttu-id="5fbc9-195">Откроется диалоговое окно **Добавить привязку сайта** .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-195">The **Add Site Binding** dialog box will appear.</span></span>  
  
3.  <span data-ttu-id="5fbc9-196">В раскрывающемся списке **Тип** выберите **HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-196">From the **Type** drop-down list, select **https**.</span></span> <span data-ttu-id="5fbc9-197">Оставьте без изменений настройки для полей **IP-адрес** и **Порт**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-197">Leave the default settings for **IP address** and **Port**.</span></span>  
  
4.  <span data-ttu-id="5fbc9-198">В раскрывающемся списке **SSL-сертификат** выберите сертификат, созданный в разделе «Создание самозаверяющего сертификата для тестирования», нажмите кнопку **ОК**, затем кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-198">From the **SSL certificate** drop-down list, select the certificate created in "To create a self-signed certificate for testing," click **OK**, and then click **Close**.</span></span>  
  
###### <a name="to-test-the-certificate"></a><span data-ttu-id="5fbc9-199">Тестирование сертификата</span><span class="sxs-lookup"><span data-stu-id="5fbc9-199">To test the certificate</span></span>  
  
1.  <span data-ttu-id="5fbc9-200">В **Вternet Вformation Services (IIS) Manager**щелкните **Веб-сайт по умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="5fbc9-200">In **Internet Information Services (IIS) Manager**, click **Default Web Site.**</span></span>  
  
2.  <span data-ttu-id="5fbc9-201">На панели **Действия** выберите **Перейти \*:443(https)** .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-201">From the **Actions** pane, click **Browse \*:443(https)**.</span></span>  
  
3.  <span data-ttu-id="5fbc9-202">В Internet Explorer появится сообщение «Ошибка проверки сертификата безопасности веб-сайта».</span><span class="sxs-lookup"><span data-stu-id="5fbc9-202">Internet Explorer will open and display a message that "There is a problem with this website's security certificate."</span></span> <span data-ttu-id="5fbc9-203">Это предупреждение указывает на то, что сертификат, связанный с этим веб-сайтом, не был выдан официальным центром сертификации и может не являться надежным.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-203">This warning tells you that the associated certificate was not issued by a recognized CA and might not be trustworthy.</span></span> <span data-ttu-id="5fbc9-204">Это предупреждение должно было появиться, поэтому нажмите **Перейти на веб-сайт (не рекомендуется)** .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-204">This is an expected warning, so click **Continue to this website (not recommended)**.</span></span>  
  
4.  <span data-ttu-id="5fbc9-205">При запросе **Подключиться к локальному компьютеру**введите имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-205">If you are prompted to **Connect to localhost**, enter a user name and password to proceed.</span></span> <span data-ttu-id="5fbc9-206">Должна отобразиться домашняя страница веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-206">You should see the default page for the Web site.</span></span>  
  
## <a name="setting-permissions-for-the-sql-server-replication-listener"></a><span data-ttu-id="5fbc9-207">Установка разрешений для средства прослушивания репликации SQL Server</span><span class="sxs-lookup"><span data-stu-id="5fbc9-207">Setting Permissions for the SQL Server Replication Listener</span></span>  
 <span data-ttu-id="5fbc9-208">При подключении компьютера подписчика к компьютеру, на котором запущены службы IIS, проверка подлинности подписчика производится с помощью типа проверки подлинности, заданного при настройке служб IIS.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-208">When a subscriber computer connects to the computer running IIS, the subscriber is authenticated by using the type of authentication specified when you configured IIS.</span></span> <span data-ttu-id="5fbc9-209">После проверки подлинности подписчика службы IIS проверяют, обладает ли подписчик правами для использования репликации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-209">After IIS authenticates the subscriber, IIS checks whether the subscriber is authorized to invoke [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication.</span></span> <span data-ttu-id="5fbc9-210">Задание разрешений на файл replisapi.dll позволяет определить пользователей, которые получают возможность запускать репликацию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-210">You control the users that can invoke [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication by setting permissions for replisapi.dll.</span></span> <span data-ttu-id="5fbc9-211">Правильная настройка разрешений необходима для предотвращения несанкционированного доступа к репликации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-211">Properly configuring permissions is necessary to prevent unauthorized access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication.</span></span>  
  
 <span data-ttu-id="5fbc9-212">Чтобы установить минимальные разрешения для учетной записи, под которой может запускаться средство прослушивания репликации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , выполните следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-212">To configure the minimum permissions for the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener runs, complete the following procedure.</span></span> <span data-ttu-id="5fbc9-213">Шаги, описанные в следующей процедуре, применимы к [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Server 2008, на котором запущены службы IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-213">The steps in the following procedure apply to [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Server 2008 running IIS 7.0.</span></span>  
  
 <span data-ttu-id="5fbc9-214">Помимо выполнения следующих шагов, убедитесь в том, что все необходимые имена входа содержатся в списке доступа к публикации (PAL).</span><span class="sxs-lookup"><span data-stu-id="5fbc9-214">In addition to performing the following steps, make sure that the required logins are in the publication access list (PAL).</span></span> <span data-ttu-id="5fbc9-215">Дополнительные сведения о списке доступа к публикации см. в статье [Организация безопасности издателя](security/secure-the-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="5fbc9-215">For more information about the PAL, see [Secure the Publisher](security/secure-the-publisher.md).</span></span>  
  
 <span data-ttu-id="5fbc9-216">**Внимание!** Учетная запись, созданная в этом разделе, будет использоваться для соединения с издателем и распространителем во время синхронизации.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-216">**Important** The account created in this section is the account that will connect to the Publisher and Distributor during synchronization.</span></span> <span data-ttu-id="5fbc9-217">Эта учетная запись должна быть добавлена как учетная запись входа SQL на сервере издателя и распространителя.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-217">This account must be added as a SQL Login account on the distribution and publication server.</span></span>  
  
 <span data-ttu-id="5fbc9-218">Для учетной записи, используемой для средства прослушивания репликации SQL Server, необходимы разрешения, описанные в разделе «Соединение с издателем и распространителем».</span><span class="sxs-lookup"><span data-stu-id="5fbc9-218">The account used for the SQL Server Replication Listener must have permissions as described in the Merge Agent Security topic, in the "Connect to the Publisher or Distributor" section.</span></span>  
  
 <span data-ttu-id="5fbc9-219">В нескольких словах, учетная запись должна отвечать следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-219">In summary, the account must:</span></span>  
  
-   <span data-ttu-id="5fbc9-220">Она должна входить в список доступа к публикации (PAL).</span><span class="sxs-lookup"><span data-stu-id="5fbc9-220">Be a member of the Publication Access List (PAL).</span></span>  
  
-   <span data-ttu-id="5fbc9-221">Она должна быть сопоставлена с именем входа, связанным с пользователем в базе данных публикации.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-221">Be mapped to a login associated with a user in the publication database.</span></span>  
  
-   <span data-ttu-id="5fbc9-222">Она должна быть сопоставлена с именем входа, связанным с пользователем в базе данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-222">Be mapped to a login associated with a user in the distribution database.</span></span>  
  
-   <span data-ttu-id="5fbc9-223">Она должна иметь разрешение на чтение в хранилище моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-223">Have Read permissions on the snapshot share.</span></span>  
  
#### <a name="to-configure-the-account-and-permissions"></a><span data-ttu-id="5fbc9-224">Настройка учетной записи и разрешений</span><span class="sxs-lookup"><span data-stu-id="5fbc9-224">To configure the account and permissions</span></span>  
  
1.  <span data-ttu-id="5fbc9-225">На компьютере, на котором запущены службы IIS, создайте локальную учетную запись:</span><span class="sxs-lookup"><span data-stu-id="5fbc9-225">Create a local account on the computer running IIS:</span></span>  
  
    1.  <span data-ttu-id="5fbc9-226">Откройте **Диспетчер сервера**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-226">Open **Server Manager**.</span></span> <span data-ttu-id="5fbc9-227">В меню «Пуск» щелкните правой кнопкой мыши **Компьютер**и выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-227">From the Start menu, right-click **Computer**, and then click **Manage**.</span></span>  
  
    2.  <span data-ttu-id="5fbc9-228">В **Диспетчер сервера**разверните узел **Настройка**, затем узел **Локальные пользователи и группы**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-228">In **Server Manager**, expand **Configuration**, and then expand **Local Users and Groups**.</span></span>  
  
    3.  <span data-ttu-id="5fbc9-229">Щелкните правой кнопкой мыши значок **Пользователи**, а затем выберите **Новый пользователь…** .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-229">Right-click **Users**, and then click **New User**.</span></span>  
  
    4.  <span data-ttu-id="5fbc9-230">Введите имя пользователя и надежный пароль.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-230">Enter a user name and a strong password.</span></span> <span data-ttu-id="5fbc9-231">Снимите флажок **Потребовать смену пароля при следующем входе в систему**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-231">Clear **User must change password at next logon**.</span></span>  
  
    5.  <span data-ttu-id="5fbc9-232">Нажмите кнопку **Создать**, а затем кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-232">Click **Create**, and then click **Close**.</span></span>  
  
2.  <span data-ttu-id="5fbc9-233">Добавьте учетную запись в группу IIS_IUSRS:</span><span class="sxs-lookup"><span data-stu-id="5fbc9-233">Add the account to the IIS_IUSRS group:</span></span>  
  
    1.  <span data-ttu-id="5fbc9-234">В **диспетчере сервера**разверните узел **Настройка**, затем узел **Локальные пользователи и группы**, выберите элемент **Группы**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-234">In **Server Manager**, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>  
  
    2.  <span data-ttu-id="5fbc9-235">Щелкните правой кнопкой мыши группу **IIS_IUSRS**и выберите **Добавить в группу**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-235">Right-click **IIS_IUSRS**, and then click **Add to Group**.</span></span>  
  
    3.  <span data-ttu-id="5fbc9-236">В диалоговом окне **Свойства: IIS_IUSRS** щелкните **Добавить...** .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-236">In the **IIS_IUSRS Properties** dialog box, click **Add**.</span></span>  
  
    4.  <span data-ttu-id="5fbc9-237">В диалоговом окне **Выбор: Пользователи, Компьютеры или Группы** добавьте учетную запись, созданную на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-237">In the **Select Users, Computers, or Groups** dialog box, add the account created in step 1.</span></span>  
  
    5.  <span data-ttu-id="5fbc9-238">Убедитесь, что в поле **В следующем месте:** указано имя локального компьютера, а не домена.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-238">Verify that **From this location** displays the name of the local computer (not a domain).</span></span> <span data-ttu-id="5fbc9-239">Если в этом поле не отображается имя локального компьютера, нажмите кнопку **Расположение...** .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-239">If this field does not display the local computer name, click **Locations**.</span></span> <span data-ttu-id="5fbc9-240">В диалоговом окне **Расположение...** выберите локальный компьютер, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-240">In the **Locations** dialog box, select the local computer, and then click **OK**.</span></span>  
  
    6.  <span data-ttu-id="5fbc9-241">В диалоговых окнах **Выбор пользователей** и **Свойства: IIS_IUSRS** нажмите кнопку**ОК**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-241">In the **Select Users** dialog box and the **IIS_IUSRS Properties** dialog box, click**OK**.</span></span>  
  
3.  <span data-ttu-id="5fbc9-242">Предоставьте учетной записи минимальные разрешения для доступа к папке, содержащей библиотеку replisapi.dll:</span><span class="sxs-lookup"><span data-stu-id="5fbc9-242">Grant minimum account permissions on the folder that contains replisapi.dll:</span></span>  
  
    1.  <span data-ttu-id="5fbc9-243">В обозревателе Windows щелкните правой кнопкой мыши папку, созданную для файла replisapi.dll, и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-243">In Windows Explorer, right-click the folder that you created for replisapi.dll, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="5fbc9-244">На вкладке **Безопасность** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-244">On the **Security** tab, click **Edit**.</span></span>  
  
    3.  <span data-ttu-id="5fbc9-245">В диалоговом окне **Разрешения для \<foldername>** нажмите **Добавить**, чтобы добавить учетную запись, созданную в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-245">In the **Permissions for \<foldername>** dialog box, click **Add** to add the account that you created in step 1.</span></span>  
  
    4.  <span data-ttu-id="5fbc9-246">Убедитесь, что в поле **В следующем месте:** указано имя локального компьютера, а не домена.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-246">Verify that **From this location** displays the name of the local computer (not a domain).</span></span> <span data-ttu-id="5fbc9-247">Если в этом поле не отображается имя локального компьютера, нажмите кнопку **Расположение...** .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-247">If this field does not display the local computer name, click **Locations**.</span></span> <span data-ttu-id="5fbc9-248">В диалоговом окне **Расположение...** выберите локальный компьютер, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-248">In the **Locations** dialog box, select the local computer, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="5fbc9-249">Убедитесь, что учетной записи предоставлены только разрешения **Чтение**, **Чтение и выполнение** и **List Folder Contents** (Перечисление содержимого папки).</span><span class="sxs-lookup"><span data-stu-id="5fbc9-249">Verify that the account is granted only **Read**, **Read & Execute**, and **List Folder Contents** permissions.</span></span>  
  
    6.  <span data-ttu-id="5fbc9-250">Выберите пользователей и группы, которым не требуется доступ к этому каталогу, и нажмите **Удалить**, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-250">Select any users or groups that do not require access to the directory, click **Remove**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="5fbc9-251">Создайте пул приложений в **диспетчере служб IIS**:</span><span class="sxs-lookup"><span data-stu-id="5fbc9-251">Create an application pool in **Internet Information Services (IIS) Manager**:</span></span>  
  
    1.  <span data-ttu-id="5fbc9-252">В **диспетчере служб IIS**на панели **Соединения** разверните узел локального сервера.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-252">In **Internet Information Services (IIS) Manager**, in the **Connections** pane, expand the local server node.</span></span>  
  
    2.  <span data-ttu-id="5fbc9-253">Щелкните правой кнопкой **Пулы приложений**и выберите **Добавить пул приложений**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-253">Right-click **Application Pools**, and then click **Add Application Pool**.</span></span>  
  
    3.  <span data-ttu-id="5fbc9-254">Введите имя пула приложений, оставьте без изменений значения по умолчанию в остальных полях и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-254">Enter a name for the application pool, leave the default values for the remaining fields, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5fbc9-255">Если предполагается использовать более двух параллельных клиентов синхронизации, рекомендуется создать веб-сад.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-255">If you anticipate having more than two concurrent synchronization clients, you might want to create a web garden.</span></span> <span data-ttu-id="5fbc9-256">Дополнительные сведения см. в разделе "Создание веб-сада" статьи [Настройка веб-синхронизации](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="5fbc9-256">For more information, see "Creating a Web Garden" in [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
5.  <span data-ttu-id="5fbc9-257">Свяжите учетную запись с этим пулом приложений:</span><span class="sxs-lookup"><span data-stu-id="5fbc9-257">Associate the account with the application pool:</span></span>  
  
    1.  <span data-ttu-id="5fbc9-258">В **диспетчере служб IIS**раскройте узел локального сервера и выберите **Пулы приложений**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-258">In **Internet Information Services (IIS) Manager**, expand the local server node, and then click on **Application Pools**.</span></span>  
  
    2.  <span data-ttu-id="5fbc9-259">Щелкните правой кнопкой мыши созданный пул приложений, а затем выберите **Настройки по умолчанию пула приложений**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-259">Right-click the application pool that you created, and then click **Set Application Pool Defaults**.</span></span>  
  
    3.  <span data-ttu-id="5fbc9-260">В диалоговом окне **Настройки по умолчанию пула приложений** с помощью прокрутки перейдите к разделу **Модель процесса** , а затем выберите поле **Удостоверение** .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-260">In the **Application Pool Defaults** dialog box, scroll down to the **Process Model** section, and then click the **Identity** field.</span></span>  
  
    4.  <span data-ttu-id="5fbc9-261">Нажмите овальную кнопку справа от строки **Удостоверение** .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-261">Click the ellipsis button on the right side of the **Identity** row.</span></span>  
  
    5.  <span data-ttu-id="5fbc9-262">Щелкните переключатель **Настраиваемая учетная запись** и выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-262">Click the **Custom Account** radio button, and then click **Set**.</span></span>  
  
    6.  <span data-ttu-id="5fbc9-263">В полях **Имя пользователя** и **Пароль** введите имя пользователя и пароль для учетной записи, созданной на шаге 1, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-263">In the **User name** and **Password** fields, enter the account and password that were created in step 1, and then click **OK**.</span></span>  
  
    7.  <span data-ttu-id="5fbc9-264">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Удостоверение пула приложений** , затем повторно нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Значения по умолчанию для пула приложений**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-264">Click **OK** to close the **Application Pool Identity** dialog box, and then click **OK** again to close the **Application Pool Defaults**dialog box.</span></span>  
  
6.  <span data-ttu-id="5fbc9-265">Свяжите пул приложений с веб-сайтом репликации:</span><span class="sxs-lookup"><span data-stu-id="5fbc9-265">Associate the application pool with the replication Web site:</span></span>  
  
    1.  <span data-ttu-id="5fbc9-266">В **диспетчере служб IIS**разверните узел локального сервера и выберите **Веб-сайт по умолчанию** (или используемый веб-сайт синхронизации, если это не веб-сайт по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="5fbc9-266">In **Internet Information Services (IIS) Manager**, expand the local server node, and then click on the **Default Web Site** (or your Web synchronization site if it is different from the default Web site).</span></span>  
  
    2.  <span data-ttu-id="5fbc9-267">На панели **Действия** под **Управление веб-сайтом**выберите **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-267">In the **Actions** pane, under **Manage Web Site**, click **Advanced Settings**.</span></span>  
  
    3.  <span data-ttu-id="5fbc9-268">В диалоговом окне **Дополнительные параметры** нажмите кнопку с многоточием справа от **Пула приложений**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-268">In the **Advanced Settings** dialog box, click on the ellipsis button to the right of **Application Pool**.</span></span>  
  
    4.  <span data-ttu-id="5fbc9-269">В раскрывающемся списке **Пул приложений** выберите пул приложений, созданный в шаге 4, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-269">From the **Application pool** drop-down list, select the application pool you created in step 4, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="5fbc9-270">Повторно нажмите кнопку **ОК** , чтобы закрыть диалоговое окно «Дополнительные параметры».</span><span class="sxs-lookup"><span data-stu-id="5fbc9-270">Click **OK** again to close Advanced Settings.</span></span>  
  
## <a name="testing-the-connection-to-replisapidll"></a><span data-ttu-id="5fbc9-271">Проверка подключения к replisapi.dll</span><span class="sxs-lookup"><span data-stu-id="5fbc9-271">Testing the Connection to replisapi.dll</span></span>  
 <span data-ttu-id="5fbc9-272">Запустите веб-синхронизацию в диагностическом режиме, чтобы проверить соединение с сервером IIS и удостовериться, что SSL-сертификаты установлены правильно.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-272">Run Web synchronization in diagnostic mode to test the connection to the computer running IIS and to make sure that the Secure Sockets Layer (SSL) certificate is properly installed.</span></span> <span data-ttu-id="5fbc9-273">Чтобы запустить веб-синхронизацию в режиме диагностики, необходимо быть администратором сервера IIS.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-273">To run Web synchronization in diagnostic mode, you must be an administrator on the computer running IIS.</span></span>  
  
#### <a name="to-test-the-connection-to-replisapidll"></a><span data-ttu-id="5fbc9-274">Проверка подключения к replisapi.dll</span><span class="sxs-lookup"><span data-stu-id="5fbc9-274">To test the connection to replisapi.dll</span></span>  
  
1.  <span data-ttu-id="5fbc9-275">Убедитесь, что параметры локальной сети на подписчике установлены правильно:</span><span class="sxs-lookup"><span data-stu-id="5fbc9-275">Make sure that local area network (LAN) settings at the Subscriber are correct:</span></span>  
  
    1.  <span data-ttu-id="5fbc9-276">В [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer в меню **Сервис** щелкните **Свойства обозревателя**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-276">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer, on the **Tools** menu, click **Internet Options**.</span></span>  
  
    2.  <span data-ttu-id="5fbc9-277">На вкладке **Подключения** щелкните **Настройки локальной сети**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-277">On the **Connections** tab, click **LAN Settings**.</span></span>  
  
    3.  <span data-ttu-id="5fbc9-278">Если в локальной сети не используется прокси-сервер, снимите флажки **Автоматическое определение параметров** и **Использовать прокси-сервер для подключений LAN**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-278">If a proxy server is not used on the LAN, clear **Automatically Detect Settings** and **Use a proxy server for your LAN**.</span></span>  
  
    4.  <span data-ttu-id="5fbc9-279">Если прокси-сервер используется, выберите **Использовать прокси-сервер для подключений локальной сети** и **Не использовать прокси-сервер для локальных адресов**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-279">If a proxy server is used, click **Use a proxy server for your LAN** and **Bypass proxy server for local addresses**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="5fbc9-280">В обозревателе Internet Explorer на подписчике подключитесь к серверу в диагностическом режиме, добавив параметр `?diag` к адресу replisapi.dll.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-280">At the Subscriber, in Internet Explorer, connect to the server in diagnostic mode by appending `?diag` to the address for the replisapi.dll.</span></span> <span data-ttu-id="5fbc9-281">Например: `https://server.domain.com/directory/replisapi.dll?diag`.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-281">For example: `https://server.domain.com/directory/replisapi.dll?diag`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5fbc9-282">В примере выше **server.domain.com** необходимо заменить точным именем **Кому выдан** , указанным в разделе **Сертификаты сервера** в диспетчере служб IIS.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-282">In the example above, **server.domain.com** should be replaced with the exact **Issued To** name listed under the **Server Certificates** section in IIS Manager.</span></span>  
  
3.  <span data-ttu-id="5fbc9-283">Если сертификат, заданный для сервера IIS, не распознается операционной системой  Windows, то выводится диалоговое окно **Предупреждение безопасности** .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-283">If the certificate that you specified for IIS is not recognized by the Windows operating system, the **Security Alert** dialog box appears.</span></span> <span data-ttu-id="5fbc9-284">Это предупреждение может возникать из-за того, что это проверочный сертификат или сертификат, выданный центром сертификации, который не распознается Windows.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-284">This alert might occur because the certificate is a test certificate or the certificate was issued by a certification authority (CA) that Windows does not recognize.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5fbc9-285">Если это диалоговое окно не выводится, обязательно добавьте этот сертификат для сервера, с которым устанавливается соединение, в качестве доверенного в хранилище сертификатов на подписчике.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-285">If this dialog box does not appear, make sure that the certificate for the server that you are accessing has been added to the certificate store at the Subscriber as a trusted certificate.</span></span> <span data-ttu-id="5fbc9-286">Дополнительные сведения об экспорте сертификатов см. в документации по службам IIS.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-286">For more information about exporting certificates, see the IIS documentation.</span></span>  
  
    1.  <span data-ttu-id="5fbc9-287">В диалоговом окне **Предупреждение системы безопасности** щелкните **Просмотреть сертификат**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-287">In the **Security Alert** dialog box, click **View Certificate**.</span></span>  
  
    2.  <span data-ttu-id="5fbc9-288">В диалоговом окне **Сертификат** на вкладке **Общие** щелкните **Установить сертификат**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-288">In the **Certificate** dialog box, on the **General** tab, click **Install Certificate**.</span></span>  
  
    3.  <span data-ttu-id="5fbc9-289">Выполните указания мастера импорта сертификатов, приняв значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-289">Complete the Certificate Import Wizard, accepting the defaults.</span></span>  
  
    4.  <span data-ttu-id="5fbc9-290">В диалоговом окне **Предупреждение безопасности** нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-290">In the **Security Warning** dialog box, click **Yes**.</span></span>  
  
    5.  <span data-ttu-id="5fbc9-291">В окне подтверждения мастера импорта сертификатов нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-291">In the Certificate Import Wizard confirmation dialog box, click **OK**.</span></span>  
  
    6.  <span data-ttu-id="5fbc9-292">Закройте диалоговое окно **Сертификат** .</span><span class="sxs-lookup"><span data-stu-id="5fbc9-292">Close the **Certificate** dialog box.</span></span>  
  
    7.  <span data-ttu-id="5fbc9-293">В диалоговом окне **Предупреждение безопасности** нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-293">In the **Security Alert** dialog box, click **Yes**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5fbc9-294">Сертификаты установлены.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-294">Certificates are installed for users.</span></span> <span data-ttu-id="5fbc9-295">Эту операцию необходимо выполнить для каждого пользователя, который будет выполнять синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-295">This process must be performed for each user that will synchronize with IIS.</span></span>  
  
4.  <span data-ttu-id="5fbc9-296">В диалоговом окне **Соединение с \<ServerName>** укажите имя входа и пароль, которые агент слияния будет использовать для подключения к серверу IIS.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-296">In the **Connect to \<ServerName>** dialog box, specify the login and password that the Merge Agent will use to connect to IIS.</span></span> <span data-ttu-id="5fbc9-297">Эти учетные данные указываются также в мастере создания подписки.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-297">These credentials will also be specified in the New Subscription Wizard.</span></span>  
  
5.  <span data-ttu-id="5fbc9-298">В окне обозревателя Internet Explorer **Диагностические сведения SQL Websync**проверьте, чтобы значение в каждом столбце **Состояние** на этой странице было равно **SUCCESS**.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-298">In the Internet Explorer window called **SQL Websync diagnostic information**, verify that the value in each **Status** column on the page is **SUCCESS**.</span></span>  
  
6.  <span data-ttu-id="5fbc9-299">Убедитесь в том, что сертификат правильно установлен на подписчике:</span><span class="sxs-lookup"><span data-stu-id="5fbc9-299">Make sure that the certificate is installed correctly on the Subscriber:</span></span>  
  
    1.  <span data-ttu-id="5fbc9-300">Закройте, а затем повторно откройте окно Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-300">Close and then reopen Internet Explorer.</span></span>  
  
    2.  <span data-ttu-id="5fbc9-301">Подключитесь к серверу в диагностическом режиме.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-301">Connect to the server in diagnostic mode.</span></span> <span data-ttu-id="5fbc9-302">Если сертификат установлен правильно, диалоговое окно **Предупреждение безопасности** не появится.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-302">If the certificate is installed properly, the **Security Alert** dialog box will not appear.</span></span> <span data-ttu-id="5fbc9-303">Если это окно появилось, то агент слияния не сможет подключиться к серверу IIS.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-303">If the dialog box appears, the Merge Agent will fail when it tries to connect to the computer that is running IIS.</span></span> <span data-ttu-id="5fbc9-304">Необходимо убедиться, что этот сертификат добавлен в качестве доверенного в хранилище сертификатов у подписчика.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-304">You must make sure that the certificate for the server that you are accessing has been added to the certificate store at the Subscriber as a trusted certificate.</span></span> <span data-ttu-id="5fbc9-305">Дополнительные сведения об экспорте сертификатов см. в документации по службам IIS.</span><span class="sxs-lookup"><span data-stu-id="5fbc9-305">For more information about exporting certificates, see the IIS documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fbc9-306">См. также:</span><span class="sxs-lookup"><span data-stu-id="5fbc9-306">See Also</span></span>  
 <span data-ttu-id="5fbc9-307">[Веб-синхронизация для репликации слиянием](web-synchronization-for-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="5fbc9-307">[Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md) </span></span>  
 [<span data-ttu-id="5fbc9-308">Настройка веб-синхронизации</span><span class="sxs-lookup"><span data-stu-id="5fbc9-308">Configure Web Synchronization</span></span>](configure-web-synchronization.md)  
  
  
