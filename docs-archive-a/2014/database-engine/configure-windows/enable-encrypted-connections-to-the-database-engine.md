---
title: Включить зашифрованные подключения к ядро СУБД (диспетчер конфигурации SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], encrypted
- SSL [SQL Server]
- Secure Sockets Layer (SSL)
- encryption [SQL Server], connections
- cryptography [SQL Server], connections
- certificates [SQL Server], installing
- requesting encrypted connections
- installing certificates
- security [SQL Server], encryption
ms.assetid: e1e55519-97ec-4404-81ef-881da3b42006
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e1653df929e3f8bc67158a0685ce07b8ba65de6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750140"
---
# <a name="enable-encrypted-connections-to-the-database-engine-sql-server-configuration-manager"></a><span data-ttu-id="5d3ed-102">Включение шифрования соединений в ядре СУБД (диспетчер конфигурации SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5d3ed-102">Enable Encrypted Connections to the Database Engine (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="5d3ed-103">В этом разделе описано, как активировать зашифрованные соединения для экземпляра компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , указав сертификат для компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] с помощью диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d3ed-103">This topic describes how to enable encrypted connections for an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] by specifying a certificate for the [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="5d3ed-104">Компьютеру сервера должен быть назначен сертификат, а компьютер клиента должен доверять корневому центру сертификации.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-104">The server computer must have a certificate provisioned, and the client machine must be set up to trust the certificate's root authority.</span></span> <span data-ttu-id="5d3ed-105">Провизионирование — это процесс установки сертификата путем импорта сертификата в систему Windows.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-105">Provisioning is the process of installing a certificate by importing it into Windows.</span></span>  
  
 <span data-ttu-id="5d3ed-106">Сертификат должен быть включен для **проверки подлинности сервера**.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-106">The certificate must be issued for **Server Authentication**.</span></span> <span data-ttu-id="5d3ed-107">Имя сертификата должно быть полным доменным именем (FQDN) компьютера.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-107">The name of the certificate must be the fully qualified domain name (FQDN) of the computer.</span></span>  
  
 <span data-ttu-id="5d3ed-108">Сертификаты хранятся локально на пользовательских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-108">Certificates are stored locally for the users on the computer.</span></span> <span data-ttu-id="5d3ed-109">Чтобы установить сертификат для использования в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], необходимо запустить диспетчер конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] под той же учетной записью пользователя, что и службу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , если только служба не запущена как LocalSystem, NetworkService или LocalService — в этих случаях необходима учетная запись администратора.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-109">To install a certificate for use by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must be running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager under the same user account as the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service unless the service is running as LocalSystem, NetworkService, or LocalService, in which case you may use an administrative account.</span></span>  
  
 <span data-ttu-id="5d3ed-110">Клиент должен уметь проверить принадлежность сертификата, используемого сервером.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-110">The client must be able to verify the ownership of the certificate used by the server.</span></span> <span data-ttu-id="5d3ed-111">Если у клиента есть сертификат открытого ключа центра сертификации, который подписал сертификат сервера, то дальнейшее конфигурирование не требуется.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-111">If the client has the public key certificate of the certification authority that signed the server certificate, no further configuration is necessary.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="5d3ed-112">Windows включает сертификаты открытого ключа нескольких центров сертификации.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-112">Windows includes the public key certificates of many certification authorities.</span></span> <span data-ttu-id="5d3ed-113">Если сертификат сервера был подписан общедоступным или частным центром сертификации, для которого у клиента нет сертификата открытого ключа, необходимо установить сертификат открытого ключа того центра сертификации, который подписал сертификат сервера.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-113">If the server certificate was signed by a public or private certification authority for which the client does not have the public key certificate, you must install the public key certificate of the certification authority that signed the server certificate.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5d3ed-114">Чтобы использовать шифрование в отказоустойчивом кластере, необходимо установить сертификат сервера с полным именем DNS виртуального сервера на все узлы отказоустойчивого кластера.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-114">To use encryption with a failover cluster, you must install the server certificate with the fully qualified DNS name of the virtual server on all nodes in the failover cluster.</span></span> <span data-ttu-id="5d3ed-115">Например, если имеется кластер из двух узлов с узлами с именем Test1. *\<your company>* . com и test2. *\<your company>* . com и у вас есть виртуальный сервер с именем Virtsql, необходимо установить сертификат для *\<your company>* Virtsql. com на обоих узлах.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-115">For example, if you have a two-node cluster, with nodes named test1.*\<your company>*.com and test2.*\<your company>*.com, and you have a virtual server named virtsql, you need to install a certificate for virtsql.*\<your company>*.com on both nodes.</span></span> <span data-ttu-id="5d3ed-116">Параметру **ForceEncryption**можно присвоить значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-116">You can set the value of the **ForceEncryption**option to **Yes**.</span></span>  
  
 <span data-ttu-id="5d3ed-117">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="5d3ed-117">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5d3ed-118">**Включение зашифрованных соединений**</span><span class="sxs-lookup"><span data-stu-id="5d3ed-118">**To enable encrypted connections:**</span></span>  
  
     [<span data-ttu-id="5d3ed-119">Установка сертификата на сервер</span><span class="sxs-lookup"><span data-stu-id="5d3ed-119">Provision (install) a certificate on the server</span></span>](#Provision)  
  
     [<span data-ttu-id="5d3ed-120">Экспорт сертификата сервера</span><span class="sxs-lookup"><span data-stu-id="5d3ed-120">Export the server certificate</span></span>](#Export)  
  
     [<span data-ttu-id="5d3ed-121">Настройка сервера на прием зашифрованных соединений</span><span class="sxs-lookup"><span data-stu-id="5d3ed-121">Configure the server to accept encrypted connections</span></span>](#ConfigureServerConnections)  
  
     [<span data-ttu-id="5d3ed-122">Настройка клиента для запроса зашифрованных соединений</span><span class="sxs-lookup"><span data-stu-id="5d3ed-122">Configure the client to request encrypted connections</span></span>](#ConfigureClientConnections)  
  
     [<span data-ttu-id="5d3ed-123">Шифрование соединения из среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5d3ed-123">Encrypt a connection from SQL Server Management Studio</span></span>](#EncryptConnection)  
  
##  <a name="SSMSProcedure"></a>  
  
###  <a name="to-provision-install-a-certificate-on-the-server"></a><a name="Provision"></a> <span data-ttu-id="5d3ed-124">Назначение (установка) сертификата на сервер</span><span class="sxs-lookup"><span data-stu-id="5d3ed-124">To provision (install) a certificate on the server</span></span>  
  
1.  <span data-ttu-id="5d3ed-125">В меню **Пуск** выберите пункт **выполнить**, а затем в поле **Открыть** введите `MMC` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-125">On the **Start** menu, click **Run**, and in the **Open** box, type `MMC` and click **OK**.</span></span>  
  
2.  <span data-ttu-id="5d3ed-126">В консоли MMC в меню **Файл** выберите **Добавить или удалить оснастку**.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-126">In the MMC console, on the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
3.  <span data-ttu-id="5d3ed-127">В диалоговом окне **Добавление или удаление оснастки** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-127">In the **Add/Remove Snap-in** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="5d3ed-128">В диалоговом окне **Добавление изолированной оснастки** выберите **Сертификаты**и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-128">In the **Add Standalone Snap-in** dialog box, click **Certificates**, click **Add**.</span></span>  
  
5.  <span data-ttu-id="5d3ed-129">В диалоговом окне **Оснастка диспетчера сертификатов** выберите **Учетная запись компьютера**и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-129">In the **Certificates snap-in** dialog box, click **Computer account**, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="5d3ed-130">В диалоговом окне **Добавить изолированную оснастку** нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-130">In the **Add Standalone Snap-in** dialog box, click **Close.**</span></span>  
  
7.  <span data-ttu-id="5d3ed-131">В диалоговом окне **Добавление или удаление оснастки** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-131">In the **Add/Remove Snap-in** dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="5d3ed-132">В оснастке **Сертификаты** последовательно разверните узлы **Сертификаты**и **Личное**, а затем правой кнопкой мыши щелкните **Сертификаты**, выберите **Все задачи**и нажмите кнопку **Импорт**.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-132">In the **Certificates** snap-in, expand **Certificates**, expand **Personal**, and then right-click **Certificates**, point to **All Tasks**, and then click **Import**.</span></span>  
  
9. <span data-ttu-id="5d3ed-133">Чтобы добавить сертификат на компьютер, выполните **Мастер импорта сертификатов**и закройте консоль MMC.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-133">Complete the **Certificate Import Wizard**, to add a certificate to the computer, and close the MMC console.</span></span> <span data-ttu-id="5d3ed-134">Дополнительные сведения о добавлении сертификатов на компьютер см. в документации по Windows.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-134">For more information about adding a certificate to a computer, see your Windows documentation.</span></span>  
  
###  <a name="to-export-the-server-certificate"></a><a name="Export"></a> <span data-ttu-id="5d3ed-135">Экспорт сертификата сервера</span><span class="sxs-lookup"><span data-stu-id="5d3ed-135">To export the server certificate</span></span>  
  
1.  <span data-ttu-id="5d3ed-136">В оснастке **Сертификаты** найдите сертификат в папке **Сертификаты** / **Личное** , правой кнопкой мыши щелкните **Сертификат**, выберите **Все задачи**и нажмите **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-136">From the **Certificates** snap-in, locate the certificate in the **Certificates** / **Personal** folder, right-click the **Certificate**, point to **All Tasks**, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="5d3ed-137">Чтобы сохранить файл сертификата в удобном расположении, выполните **мастер экспорта сертификатов**.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-137">Complete the **Certificate Export Wizard**, storing the certificate file in a convenient location.</span></span>  
  
###  <a name="to-configure-the-server-to-accept-encrypted-connections"></a><a name="ConfigureServerConnections"></a> <span data-ttu-id="5d3ed-138">Настройка сервера на прием зашифрованных соединений</span><span class="sxs-lookup"><span data-stu-id="5d3ed-138">To configure the server to accept encrypted connections</span></span>  
  
1.  <span data-ttu-id="5d3ed-139">В окне **Диспетчер конфигурации SQL Server** разверните узел **Сетевая конфигурация SQL Server**, щелкните правой кнопкой мыши элемент **Протоколы для** _\<server instance>_ , затем выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-139">In **SQL Server Configuration Manager**, expand **SQL Server Network Configuration**, right-click **Protocols for** _\<server instance>_, and then select**Properties**.</span></span>  
  
2.  <span data-ttu-id="5d3ed-140">В диалоговом окне **протоколы для** _\<instance name>_ **свойств** на вкладке **сертификат** выберите нужный сертификат из раскрывающегося списка **сертификат** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-140">In the **Protocols for**_\<instance name>_ **Properties** dialog box, on the **Certificate** tab, select the desired certificate from the drop down for the **Certificate** box, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="5d3ed-141">На вкладке **Флаги** в поле **ForceEncryption** выберите **Да**, затем нажмите кнопку **ОК** , чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-141">On the **Flags** tab, in the **ForceEncryption** box, select **Yes**, and then click **OK** to close the dialog box.</span></span>  
  
4.  <span data-ttu-id="5d3ed-142">Перезапустите службу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d3ed-142">Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
###  <a name="to-configure-the-client-to-request-encrypted-connections"></a><a name="ConfigureClientConnections"></a> <span data-ttu-id="5d3ed-143">Настройка клиента на прием зашифрованных соединений</span><span class="sxs-lookup"><span data-stu-id="5d3ed-143">To configure the client to request encrypted connections</span></span>  
  
1.  <span data-ttu-id="5d3ed-144">Скопируйте на компьютер клиента исходный сертификат или экспортированный файл сертификата.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-144">Copy either the original certificate or the exported certificate file to the client computer.</span></span>  
  
2.  <span data-ttu-id="5d3ed-145">Чтобы установить корневой сертификат или экспортированный файл сертификата на клиентском компьютере, используйте оснастку **Сертификаты** .</span><span class="sxs-lookup"><span data-stu-id="5d3ed-145">On the client computer, use the **Certificates** snap-in to install either the root certificate or the exported certificate file.</span></span>  
  
3.  <span data-ttu-id="5d3ed-146">На панели консоли щелкните правой кнопкой мыши элемент **Конфигурация собственного клиента SQL Server**, затем нажмите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-146">In the console pane, right-click **SQL Server Native Client Configuration**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="5d3ed-147">На странице **Флаги** в диалоговом окне **Принудительное шифрование протокола** выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-147">On the **Flags** page, in the **Force protocol encryption** box, click **Yes**.</span></span>  
  
###  <a name="to-encrypt-a-connection-from-sql-server-management-studio"></a><a name="EncryptConnection"></a><span data-ttu-id="5d3ed-148">Шифрование соединения из SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5d3ed-148">To encrypt a connection from SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="5d3ed-149">На панели инструментов обозревателя объектов нажмите кнопку **Соединить**и выберите **Компонент Database Engine**.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-149">On the Object Explorer toolbar, click **Connect**, and then click **Database Engine**.</span></span>  
  
2.  <span data-ttu-id="5d3ed-150">В диалоговом окне **Соединение с сервером** введите все данные, необходимые для подключения, а затем нажмите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-150">In the **Connect to Server** dialog box, complete the connection information, and then click **Options**.</span></span>  
  
3.  <span data-ttu-id="5d3ed-151">На вкладке **Свойства соединения** щелкните **Шифровать соединение**.</span><span class="sxs-lookup"><span data-stu-id="5d3ed-151">On the **Connection Properties** tab, click **Encrypt connection**.</span></span>  
  
  
