---
title: Редактор диспетчера подключений SAP BW | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ec970319-e749-4753-8675-9cf76ed99669
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 527af979fc9c92062f24e1fe161b93e88ed4ab4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730830"
---
# <a name="sap-bw-connection-manager-editor"></a><span data-ttu-id="006d2-102">Редактор диспетчера соединений SAP BW</span><span class="sxs-lookup"><span data-stu-id="006d2-102">SAP BW Connection Manager Editor</span></span>
  <span data-ttu-id="006d2-103">Используйте **Редактор диспетчера соединений SAP BW** , чтобы указать свойства для подключения к системе SAP Netweaver BW версии 7.</span><span class="sxs-lookup"><span data-stu-id="006d2-103">Use the **SAP BW Connection Manager Editor** to specify the properties to use to connect to an SAP Netweaver BW version 7 system.</span></span>  
  
 <span data-ttu-id="006d2-104">Диспетчер соединений SAP BW обеспечивает возможность подключения к системе SAP Netweaver BW 7 для использования источником или назначением SAP BW.</span><span class="sxs-lookup"><span data-stu-id="006d2-104">The SAP BW connection manager provides connectivity to an SAP Netweaver BW 7 system for use by the SAP BW source or destination.</span></span> <span data-ttu-id="006d2-105">Для получения дополнительных сведений о диспетчере соединений Connector 1.1 для SAP BW [!INCLUDE[msCoName](../includes/msconame-md.md)] см. раздел [Диспетчер соединений SAP BW](connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="006d2-105">To learn more about the SAP BW connection manager of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Connection Manager](connection-manager/sap-bw-connection-manager.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="006d2-106">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="006d2-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="006d2-107">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="006d2-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="006d2-108">**Открытие редактора диспетчера соединений SAP BW**</span><span class="sxs-lookup"><span data-stu-id="006d2-108">**To open the SAP BW Connection Manager Editor**</span></span>  
  
1.  <span data-ttu-id="006d2-109">В [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий диспетчер соединений SAP BW.</span><span class="sxs-lookup"><span data-stu-id="006d2-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that contains the SAP BW connection manager.</span></span>  
  
2.  <span data-ttu-id="006d2-110">В области диспетчеров соединений на вкладке **Поток управления** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="006d2-110">In the Connection Managers area on the **Control Flow** tab, do one of the following steps:</span></span>  
  
    -   <span data-ttu-id="006d2-111">Дважды щелкните диспетчер соединений SAP BW.</span><span class="sxs-lookup"><span data-stu-id="006d2-111">Double-click the SAP BW connection manager.</span></span>  
  
         <span data-ttu-id="006d2-112">-или-</span><span class="sxs-lookup"><span data-stu-id="006d2-112">-or-</span></span>  
  
    -   <span data-ttu-id="006d2-113">Щелкните правой кнопкой мыши диспетчер соединений SAP BW, а затем выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="006d2-113">Right-click the SAP BW connection manager, and then select **Edit**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="006d2-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="006d2-114">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="006d2-115">Если вы не знаете все значения, необходимые для настройки диспетчера соединений, запросите их у администратора SAP.</span><span class="sxs-lookup"><span data-stu-id="006d2-115">If you do not know all the values that are required to configure the connection manager, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="006d2-116">**Клиент**</span><span class="sxs-lookup"><span data-stu-id="006d2-116">**Client**</span></span>  
 <span data-ttu-id="006d2-117">Укажите номер клиента системы.</span><span class="sxs-lookup"><span data-stu-id="006d2-117">Specify the client number of the system.</span></span>  
  
 <span data-ttu-id="006d2-118">**Язык**</span><span class="sxs-lookup"><span data-stu-id="006d2-118">**Language**</span></span>  
 <span data-ttu-id="006d2-119">Укажите язык, используемой системой.</span><span class="sxs-lookup"><span data-stu-id="006d2-119">Specify the language that the system uses.</span></span> <span data-ttu-id="006d2-120">Например, **EN** для английского языка.</span><span class="sxs-lookup"><span data-stu-id="006d2-120">For example, specify **EN** for English.</span></span>  
  
 <span data-ttu-id="006d2-121">**User name**</span><span class="sxs-lookup"><span data-stu-id="006d2-121">**User name**</span></span>  
 <span data-ttu-id="006d2-122">Укажите имя пользователя, которое будет использоваться для подключения к системе.</span><span class="sxs-lookup"><span data-stu-id="006d2-122">Specify the user name that will be used to connect to the system.</span></span>  
  
 <span data-ttu-id="006d2-123">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="006d2-123">**Password**</span></span>  
 <span data-ttu-id="006d2-124">Укажите пароль для использования с именем пользователя.</span><span class="sxs-lookup"><span data-stu-id="006d2-124">Specify the password that will be used with the user name.</span></span>  
  
 <span data-ttu-id="006d2-125">**Использовать единый сервер приложений**</span><span class="sxs-lookup"><span data-stu-id="006d2-125">**Use single application server**</span></span>  
 <span data-ttu-id="006d2-126">Подключитесь к одному серверу приложений.</span><span class="sxs-lookup"><span data-stu-id="006d2-126">Connect to a single application server.</span></span>  
  
 <span data-ttu-id="006d2-127">Вместо этого для подключения к группе серверов с балансировкой нагрузки серверы примените параметр **Использовать балансировку нагрузки** .</span><span class="sxs-lookup"><span data-stu-id="006d2-127">To connect to a group of load-balanced servers, use the **Use load balancing** option instead.</span></span>  
  
 <span data-ttu-id="006d2-128">**Узел**</span><span class="sxs-lookup"><span data-stu-id="006d2-128">**Host**</span></span>  
 <span data-ttu-id="006d2-129">При подключении к одному серверу приложений укажите имя узла.</span><span class="sxs-lookup"><span data-stu-id="006d2-129">If connecting to a single application server, specify the host name.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="006d2-130">Этот параметр доступен, только если выбран параметр **Использовать единый сервер приложений** .</span><span class="sxs-lookup"><span data-stu-id="006d2-130">This option is only available if you have selected the **Use single application server** option.</span></span>  
  
 <span data-ttu-id="006d2-131">**Номер системы**</span><span class="sxs-lookup"><span data-stu-id="006d2-131">**System number**</span></span>  
 <span data-ttu-id="006d2-132">При подключении к одному серверу приложений укажите номер системы.</span><span class="sxs-lookup"><span data-stu-id="006d2-132">If connecting to a single application server, specify the system number.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="006d2-133">Этот параметр доступен, только если выбран параметр **Использовать единый сервер приложений** .</span><span class="sxs-lookup"><span data-stu-id="006d2-133">This option is only available if you have selected the **Use single application server** option.</span></span>  
  
 <span data-ttu-id="006d2-134">**Использовать балансировку нагрузки**</span><span class="sxs-lookup"><span data-stu-id="006d2-134">**Use load balancing**</span></span>  
 <span data-ttu-id="006d2-135">Подключитесь к группе серверов с балансировкой нагрузки.</span><span class="sxs-lookup"><span data-stu-id="006d2-135">Connect to a group of load-balanced servers.</span></span>  
  
 <span data-ttu-id="006d2-136">Вместо этого для подключения к одному серверу приложений используйте параметр **Использовать единый сервер приложений** .</span><span class="sxs-lookup"><span data-stu-id="006d2-136">To connect to a single application server, use the **Use single application server** option instead.</span></span>  
  
 <span data-ttu-id="006d2-137">**Сервер сообщений**</span><span class="sxs-lookup"><span data-stu-id="006d2-137">**Message server**</span></span>  
 <span data-ttu-id="006d2-138">При подключении к группе серверов с выравниванием нагрузки укажите имя сервера сообщений.</span><span class="sxs-lookup"><span data-stu-id="006d2-138">If connecting to a group of load-balanced servers, specify the name of the message server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="006d2-139"> Этот параметр доступен, только если выбран параметр **Использовать балансировку нагрузки** .</span><span class="sxs-lookup"><span data-stu-id="006d2-139">This option is only available if you have selected the **Use load balancing** option.</span></span>  
  
 <span data-ttu-id="006d2-140">**Группа**</span><span class="sxs-lookup"><span data-stu-id="006d2-140">**Group**</span></span>  
 <span data-ttu-id="006d2-141">При подключении к группе серверов с выравниванием нагрузки укажите имя группы серверов.</span><span class="sxs-lookup"><span data-stu-id="006d2-141">If connecting to a group of load-balanced servers, specify the name of the server group name.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="006d2-142"> Этот параметр доступен, только если выбран параметр **Использовать балансировку нагрузки** .</span><span class="sxs-lookup"><span data-stu-id="006d2-142">This option is only available if you have selected the **Use load balancing** option.</span></span>  
  
 <span data-ttu-id="006d2-143">**ТРАНСЛЯЦИЮ**</span><span class="sxs-lookup"><span data-stu-id="006d2-143">**SID**</span></span>  
 <span data-ttu-id="006d2-144">При подключении к группе серверов с балансировкой нагрузки укажите системный идентификатор для соединения.</span><span class="sxs-lookup"><span data-stu-id="006d2-144">If connecting to a group of load-balanced servers, specify the System ID for the connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="006d2-145"> Этот параметр доступен, только если выбран параметр **Использовать балансировку нагрузки** .</span><span class="sxs-lookup"><span data-stu-id="006d2-145">This option is only available if you have selected the **Use load balancing** option.</span></span>  
  
 <span data-ttu-id="006d2-146">**Каталог журналов**</span><span class="sxs-lookup"><span data-stu-id="006d2-146">**Log directory**</span></span>  
 <span data-ttu-id="006d2-147">Включите ведение журнала для компонентов Connector 1.1 для SAP BW [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="006d2-147">Enable logging for the components of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
 <span data-ttu-id="006d2-148">Чтобы включить ведение журнала, укажите каталог для файлов журналов, созданных до и после каждого вызова функции RFC.</span><span class="sxs-lookup"><span data-stu-id="006d2-148">To enable logging, specify a directory for the log files that are created before and after each RFC function call.</span></span> <span data-ttu-id="006d2-149">(Эта функция ведения журнала создает большое количество файлов журнала в формате XML.</span><span class="sxs-lookup"><span data-stu-id="006d2-149">(This logging feature creates many log files in XML format.</span></span> <span data-ttu-id="006d2-150">Поскольку эти файлы журнала также содержат все передаваемые строки данных, для них может потребоваться много места на диске.)</span><span class="sxs-lookup"><span data-stu-id="006d2-150">As these log files also contain all the rows of data that are transferred, these log files may consume a large amount of disk space.)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="006d2-151">Если передаваемые данные содержат конфиденциальные данные, файлы журнала также будут содержать эти конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="006d2-151">If the data that is transferred contains sensitive information, the log files will also contain that sensitive information.</span></span>  
  
 <span data-ttu-id="006d2-152">Чтобы указать каталог журналов, можно ввести путь к каталогу вручную или щелкнуть **Обзор** для перехода к каталогу журнала.</span><span class="sxs-lookup"><span data-stu-id="006d2-152">To specify the log directory, you can either enter the directory path manually, or click **Browse** and browse to the log directory.</span></span>  
  
 <span data-ttu-id="006d2-153">Если не выбрать каталог журнала, ведение журналов не будет включено.</span><span class="sxs-lookup"><span data-stu-id="006d2-153">If you do not select a log directory, logging is not enabled.</span></span>  
  
 <span data-ttu-id="006d2-154">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="006d2-154">**Browse**</span></span>  
 <span data-ttu-id="006d2-155">Используйте функцию обзора, чтобы выбрать папку для каталога журналов.</span><span class="sxs-lookup"><span data-stu-id="006d2-155">Browse to select a folder for the log directory.</span></span>  
  
 <span data-ttu-id="006d2-156">**Проверка соединения**</span><span class="sxs-lookup"><span data-stu-id="006d2-156">**Test Connection**</span></span>  
 <span data-ttu-id="006d2-157">Выполните проверку подключения с указанными значениями.</span><span class="sxs-lookup"><span data-stu-id="006d2-157">Test the connection using the values that you have provided.</span></span> <span data-ttu-id="006d2-158">После щелчка **Проверка подключения**откроется окно сообщения, в котором будет указано, установлено ли подключение успешно или с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="006d2-158">After clicking **Test Connection**, a message box appears and indicates whether the connection succeeded or failed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="006d2-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="006d2-159">See Also</span></span>  
 [<span data-ttu-id="006d2-160">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="006d2-160">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](microsoft-connector-for-sap-bw-f1-help.md)  
  
  
